---
name: momsdeklaration-fortnox
description: >-
  Använd när uppgiften rör löpande bokföring och svensk momsdeklaration
  (kvartals-/månadsmoms) i Fortnox: granska/bokföra verifikat via Fortnox Claude
  Connector, avgöra momsbehandling per faktura (svensk moms vs omvänd
  skattskyldighet), bygga och kontrollera momsrapporten, samt hantera
  momsredovisningsperioder i Fortnox webb (Playwright) inför användarens manuella
  inlämning hos Skatteverket. Kräver Fortnox Claude Connector + Playwright MCP.
  Generell — inga bolagsuppgifter.
metadata:
  type: reference
---

# Momsdeklaration i Fortnox — praktisk runbook

**Exekveringslagret** (hur man gör). Regelverk/fältlogik finns i
`Prompts/momsdeklaration-prompt.md` och `Knowledge Base/Skatteverket/Moms/`.
Delade Fortnox-/Playwright-mönster (iframe-SPA, flyktiga refs, URL-navigering,
SIE-nedladdning) är samma som [[arsredovisning-fortnox]] och
[[inkomstdeklaration2-fortnox]] — läs dem och återanvänd mönstren.

## Princip
Semi-automatiskt: agenten läser, bokför (stående godkännande), bygger och
kontrollerar momsrapporten; **användaren lämnar in och signerar med BankID hos
Skatteverket.** Under **kontantmetoden** redovisas moms och kostnad vid
**betalning** (kortdragningsdatum), inte fakturadatum.

## 0. Preflight
1. `/mcp` → **Fortnox-connector** + **Playwright** = "connected". Annars stanna.
2. Läs `Om mig/`: **bokföringsmetod** (kontant/faktura), **momsperiod**
   (månad/kvartal), momsregistrering, om frivillig skattskyldighet. **Gissa aldrig.**
3. Du behöver **inte** be användaren exportera transaktioner — connectorn läser
   allt live. Flaskhalsen är **kvitton/fakturor** (behövs för momsbehandling).

## 1. Underlag och arbetssätt (leant)
- **Transaktioner:** läs live via connectorn (`fortnox_list vouchers financialyear=<id>`)
  eller hämta **SIE** (`fortnox_download_file sie/4`, query `financialyear`).
  SIE kommer base64 i JSON → **avkoda cp437**; stora filer sparas till fil av
  runtimen → parsa lokalt med python (räkna momsrörelser per konto och period).
- **Kvitton:** låt användaren fota in i Fortnox (Kvitto & Utlägg / inkorg) eller
  lägga i `Underlag-<år>/Kvitton/Q#/`. **Fortnox voucher-inkorg har en e-post-in-adress**
  (`inbox.ver.<databasnr>@arkivplats.se`) — visas i verifikationslistan.
- **Skattekonto:** utdraget ("Bokförda transaktioner" från Skatteverket) är
  **facit** för vad som faktiskt deklarerats/betalats per period. Läs det.

## 2. Momsbehandling avgörs PER FAKTURA (viktigast)
Anta **aldrig** att "utländsk leverantör = omvänd skattskyldighet". Läs varje faktura:
- **Utländsk leverantör som debiterar SVENSK moms** (ofta via OSS; står "VAT Sweden
  25 %"/"moms 25 %" med leverantörens momsnr) → vanlig **ingående moms, konto 2641**,
  dras av i **ruta 48**. Vanligt för Apple/iCloud, Google/YouTube, OpenAI (ibland),
  ElevenLabs, Udemy m.fl.
- **Omvänd skattskyldighet** (fakturan: 0 % moms, "reverse charge"/"Customer to
  account for VAT"/"Tax to be paid on reverse charge basis") → förvärvsmoms:
  - **Bokför kostnaden på förvärvskontot** så beskattningsunderlaget hamnar rätt:
    - **4531** "Inköp tjänst utanför EU" (VATCode ITGLOB) → **ruta 22**
    - **4535** "Inköp tjänst annat EU-land" (VATCode ITEU) → **ruta 21**
  - **Utgående förvärvsmoms 2614** → ruta 30; **beräknad ingående 2645** → ruta 48.
  - ⚠️ **Vanlig bugg:** om kostnaden bokförs på ett vanligt kostnadskonto (t.ex.
    6540) i stället för 4531/4535 blir **ruta 21/22 = 0** medan ruta 30 har moms —
    deklarationen blir inkonsekvent. Kontrollera `fortnox_get accounts/<nr>`:
    **VATCode** ska vara ITGLOB/ITEU. Ruta 30 läses från konto **2614** (inte
    auto-genererad av 4531), så en ren omklassning `Debet 4531/4535 / Kredit 6540`
    fyller basen **utan** att dubbla momsen — verifiera i momsrapporten efteråt.
- **Svensk leverantör** → 2641 som vanligt.
- **Representation (mat/dryck vid kundträff/kundevent):** måltid är **ej
  avdragsgill** i inkomstskatten → konto **6072**. Moms får dras av på underlag
  **max 300 kr/person och tillfälle** (livsmedel 6 % → 18 kr/pers; restaurang 36
  kr/pers, eller schablon 46 kr/pers vid mat+alkohol) **men bara med momskvitto +
  deltagarantal**. Saknas det → bokför utan momsavdrag (konservativt).
- **Böter/förseningsavgift/skattetillägg:** ej avdragsgill, ingen moms → 6992/6072.

## 3. Privat kort vs företagskort
- **Privatkortsutlägg** → motkonto **2893** (skuld till närstående/ägaren). Håll koll
  på saldot: **vänder det till debet lånar bolaget ut till ägaren = förbjudet lån (ABL 21)**.
- **Företagskort/bankkonto** → motkonto det aktuella bankkontot (t.ex. 1930).
- Redovisa alltid verifikatnr + effekt vid bokföring.

## 4. Bygg och kontrollera momsrapporten
- Räkna en **kontrollberäkning** från huvudboken/SIE per period: ruta 05/10
  (försäljning + utg moms), 21/22 + 30 (förvärv), 48 (ingående = 2641+2645), 49.
- **Öppna Fortnox momsrapport** (Playwright, se §5) och stäm av rad för rad mot
  kontrollberäkningen. Ruta 05×0,25 = ruta 10; förvärvsbas×0,25 = ruta 30;
  förvärvsmomsen tar ut sig (ruta 30 = del av ruta 48) → nettokostnad 0.

## 5. Fortnox webb (Playwright) — momsredovisningsperioder
- Sätt **rätt räkenskapsår** i årsväljaren (uppe till höger) först.
- Moms-översikt: `…/vat/`. En period: `…/vat/vatperiod/YYYY-MM` (YYYY-MM = periodens
  första månad, t.ex. `2026-04` för apr–jun).
- Periodsidan visar **rutorna** (A/B/C/D/F/G). **"Visa momsrapport"** öppnar hela
  blanketten med alla ruttal (05,10,20–24,30,48,49) — läs av dem för användarens
  **manuella inlämning**.
- **"Godkänn och bokför"** skapar M-verifikatet och **klarmarkerar** perioden.
  Den är **spärrad tills tidigare perioder är hanterade** (kedja, äldst först).
- **Direkt till Skatteverket:** kortet "Skicka in direkt / Kom igång" är Fortnox
  integration (kräver att firmatecknare ger ombudsbehörighet via BankID). Vill
  användaren lämna in **manuellt** matar hen bara in ruttalen på skatteverket.se.

## 6. Återöppnade perioder / bokslutsartefakter (check required, HÖG)
- En momsperiod **återöppnas** om ett nytt verifikat dateras i den. **Bokslutets
  rättelseverifikat** (daterade sista dagen i ett redan rapporterat kvartal) som rör
  momskonton (t.ex. 2641) får Fortnox att **räkna om perioden till ett högre belopp**
  än det som deklarerades.
- **Detta är ofta en artefakt, inte en verklig skuld.** Verifiera mot
  **skattekontoutdraget**: det som deklarerats + betalats där är den sanna siffran.
  Är det ett **fastställt/inlämnat år** → **bokför inte om** till den felaktiga
  siffran (det skapar en falsk skuld och rör årsredovisningen). Stanna och förklara;
  rättelse i det stängda året kräver användarens uttryckliga ok (och ev. omprövning).

## 7. Kända buggar / friktion (och kringgång)
- **Kvittobifogning via Playwright funkar inte:** Fortnox verifikat-bilagefält är ett
  native filfält utan handtag i tillgänglighetsträdet → filväljaren går inte att
  öppna programmatiskt. Låt användaren dra in kvitton (de har redan en karta), eller
  använd e-post-in-adressen. **Undvik base64-uppladdning via connectorn för många
  filer** (token-tungt + trunkeringsrisk som tyst korrumperar filen).
- **Verifikat-beskrivning:** connectorn nekar vissa tecken (t.ex. `>`), fel
  `code 2000359` → använd "till" i stället för "->".
- **Verifikat är oföränderliga** → rätta med nytt (omklassnings-/rättelse)verifikat.
- **Playwright-sessionen stängs** ibland → navigera om, användaren loggar in på nytt.
- **iframe-refs (`fNNe…`) blir inaktuella** vid omrendering → ta färsk snapshot
  precis före klick; verifikatvyns URL är deterministisk (`…/bf/voucher/A-<nr>`).

## 8. Gränser (stanna alltid)
- **Ingen inlämning till Skatteverket utan användarens BankID.** Förbered ruttalen,
  ge grön signal.
- Stående skrivgodkännande täcker löpande bokföring/rättelse/momsrapport — men
  **fråga ändå vid** misstänkta/oväntade poster, representation, **åtgärder i
  fastställt år**, och borttag av data du inte skapat.
- Exponera aldrig personnummer/bolagsuppgifter/belopp i repo-spårade filer/commits.
- Efter klar period: uppdatera projektminnet (belopp, deadline, ev. artefakter/öppna
  poster) och spara underlag i `Underlag-<år>/`.
