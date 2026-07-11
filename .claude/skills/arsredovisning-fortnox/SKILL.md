---
name: arsredovisning-fortnox
description: >-
  Använd när uppgiften rör att upprätta, kontrollera, signera eller digitalt
  lämna in en svensk K2-årsredovisning i Fortnox "Bokslut & Skatt", driva
  Bokslut & Skatt via webben med Playwright, eller digital inlämning av
  årsredovisning till Bolagsverket. Kräver Fortnox Claude Connector + Playwright
  MCP. Generell — inga bolagsuppgifter.
metadata:
  type: reference
---

# Årsredovisning i Fortnox Bokslut & Skatt — praktisk runbook

Detta är **exekveringslagret** (hur man gör). Regelverk/metodik finns i
`Prompts/arsredovisning-prompt.md`; siffrorna ska redan vara avstämda i
bokföringen innan webbmodulen öppnas.

## Princip
Snabbast + säkrast + minst tokens **utan kvalitetstapp**. Semi-automatiskt:
agenten fyller i och kontrollerar; **användaren signerar med BankID och gör den
slutliga "Lämna in".** Redovisa alltid verifikatnr + effekt vid bokföring.

## 0. Preflight (kör först)
1. Verifiera att både **Fortnox-connectorn** (MCP) och **Playwright** är
   "connected" (`/mcp`). Utan dem kan jobbet inte göras — stanna och be
   användaren ansluta.
2. Läs bolagets fakta (säte, regelverk, räkenskapsår, revisor, aktiekapital,
   styrelse/firmatecknare) ur projektets `Om mig/`. **Gissa aldrig.**
3. Bekräfta via connectorn att bokföringen balanserar och att årets resultat är
   bokfört innan du rör webbmodulen (`fortnox_get accounts/<konto>`,
   `fortnox_list vouchers`, ev. SIE).

## 1. Arkitektur att känna till (annars slösas tokens)
- Bokslut & Skatt är en **nästlad iframe-SPA** (`iframe title="App"`).
- **Referenser (`f2e…`/`f38e…`) är flyktiga** och regenereras vid varje render
  och navigering. **Håll aldrig en ref mellan två åtgärder.** Vid "Ref not
  found": ta en ny riktad snapshot eller använd text/roll-selektor.
- Navigera via **URL** när sökvägen är känd
  (`…/year/managementReport|incomeStatement|balanceSheet|notes|signatures|confirmAnnualReportMenu|annualGeneralMeeting|confirmAnnualGeneralMeeting|sign|BVdigitalSubmission`)
  — snabbare och stabilare än menyklick.

## 2. Token-effektiva Playwright-mönster
- **Sticky headers + toaster (`fixedDrawers`/snackbar) fångar klick.** När
  `browser_click` timeoutar med "intercepts pointer events" → klicka via
  `browser_evaluate` med rå `el.click()` (kringgår aktiverbarhetskontrollen).
- **Batcha i `browser_evaluate`:** läs/agera på många element i ETT anrop
  (t.ex. status på alla perioder, hitta+klicka menyval på text, hitta spara-
  knapp via ikon-path). Sparar många snapshot-rundor.
- **Riktade snapshots:** använd `browser_snapshot` med `target`/region eller
  `filename` istället för hela sidan. Full-page-snapshots är dyra.
- **Öppna menyer/dropdowns** renderas i portal ovanpå allt → menyvalen går att
  klicka normalt även när periodkortet under är blockerat.

## 3. Stegordning (klick-för-klick)
1. **Klientinställningar** — Företagsform=Aktiebolag, Om verksamheten, säte,
   Avstämningsperiod, Momsperiod, Bokslutsmånad, **Startdatum = räkenskapsårets
   första dag** (krävs för att skapa årsdokument). Funktionärer: styrelse (+VD
   om registrerad) med pnr + e-post (e-post krävs för digital signering).
2. **Bokslut → Bokslutsplanering/Skatteberäkning** — klicka **"Uppdatera mot
   bokföring"** först (annars visar allt 0). Kontrollera årets resultat, skatt.
   Bokför "Årets skatt" (om >0) och **"Årets resultat" (8999/2099)** — välj
   verifikationsserie **A**, klicka Bokför.
3. **Årsredovisning → Inställningar** — K2, **Digital inlämning**, digital
   signering (BankID), ingen revisor (om ej revisionsplikt), hela kronor,
   jämförelseår 0. *(Byte digital/manuell efter ifyllnad återställer mallen —
   välj rätt FÖRST.)*
4. **Förvaltningsberättelse / RR / BR / Noter / Undertecknare** — kontrollera
   auto-siffror mot bokslutet. Fyll ingress, säte, EK-tabell (se fällor),
   resultatdisposition, Not 1 (K2), medelantal anställda. Undertecknare = alla
   styrelseledamöter (+ VD om sådan finns).
5. **Granska och lås** → **Kontroll mot Bolagsverket** (godkänn ev.
   Eget-utrymme-avtal = användarens medgivande) → **Lås årsredovisning**.
6. **Årsstämmoprotokoll** → fyll ort/datum/röstlängd/ordförande/protokollförare/
   arvode/revisor → **Granska och lås**.
7. **Signering** → "Skicka för signering" → **användaren signerar med BankID.**
8. **Digital inlämning till Bolagsverket** → fyll fastställelseintygets
   **undertecknare + datum för signering** → **Kontroll mot Bolagsverket** →
   **Lås fastställelseintyg** → **Lämna in årsredovisning** → undertecknaren får
   mejl och **BankID-signerar fastställelseintyget inom 21 dagar** (användaren).

## 4. Kända fel → fix (felsökningstabell)
| Symptom | Orsak & fix |
|---|---|
| Skatteberäkning visar allt **0** | Modulen ej synkad → klicka **"Uppdatera mot bokföring"**. |
| Bokför-fel: *"Aktivera Manuell kontering för verifikationsserien"* | Välj serie **A** i verifikatet (Redigera), eller aktivera manuell kontering i Fortnox Inställningar → Bokföring → Verifikationsserier. |
| Företagsform står **"Övrigt"** | Ändra till **Aktiebolag** i klientinställningar (SCB-koden "49 Övriga aktiebolag" mappar dit). |
| **"Bolaget har sitt säte i ."** (tomt) i förvaltningsberättelsen | Sätet hämtas från klientinställningar/Fortnox (postorten ≠ säte). **Säte = registrerad säteskommun ur bolagsordningen.** Sätt vid källan; texten kan **återgå till tomt vid låsning** → **verifiera alltid i Förhandsvisning** innan lås. |
| Förändringar i EK visar **aktiekapital 0** (första året) | Aktiekapitalet bokfördes inom året (IB 0) → i EK-tabellen: aktivera **"Nyemission"**-raden så utgående EK = aktiekapital + årets resultat. |
| Kontroll flaggar *"Företrädare stämmer inte"* (t.ex. även **VD**) | Bolagsverkets register är facit → **"Uppdatera klientinställningar"**. Ingress + undertecknare måste matcha; finns VD **måste** hen skriva under och ingressen säga "Styrelsen och verkställande direktören…". Kontrollera att e-post finns på båda funktionärsposterna. |
| "Låst" är **gråmarkerad** på en avstämningsperiod | Perioden måste först sättas **"Klar"**, sedan **"Låst"** (och i **kronologisk ordning**). Öppna statusmenyn genom att klicka periodetiketten; klicka menyvalen via `browser_evaluate` om sticky header blockerar. |
| Varning: *"Datum för underskrifter saknas"* | **Ofarlig** — datumet sätts av den elektroniska signaturen. Blockerar inte. |
| Varning: *"Jämförelsesiffror saknas"* | **Ofarlig första året** — gäller ej förlängt/första räkenskapsår. |
| Signeringssidan visar **"Ej skickad"** trots signering | Vilseledande. **Inlämningssidans ("BVdigitalSubmission") "Årsredovisningen är signerad" gäller.** Ladda om vid tvivel. |
| Inlämning blockerad: *"undertecknare/datum saknas i fastställelseintyget"* | Lägg till undertecknare (behörig företrädare) + Datum för signering, sedan Kontroll → Lås → Lämna in. |
| Bolagsverkets **Eget utrymme-avtal**-dialog | Juridiskt avtal i bolagets namn → **kräver användarens uttryckliga godkännande** (stanna och fråga). |

## 5. Verifieringsgrindar (kör före lås/inlämning)
- **BR balanserar:** Summa tillgångar = Summa eget kapital och skulder.
- **EK stämmer:** Summa eget kapital = aktiekapital + balanserat + årets resultat.
- **Resultat konsekvent:** RR:s årets resultat = BR:s = resultatdispositionen.
- **Kontroll mot Bolagsverket** = "utan anmärkningar" (varningar ovan är OK).
- **Slutlig PDF via Förhandsvisning** (speed-dial) — läs särskilt **sätet** och
  underskriftsraden (roller: Styrelseledamot / VD).

## 6. Gränser (stanna alltid här)
- **BankID-signering** och slutlig **"Lämna in"** samt **fastställelseintygets
  BankID** är användarens — förbered fram till knappen, stanna och be om
  bekräftelse.
- Godkänn aldrig myndighetsavtal (Bolagsverkets Eget utrymme) utan användarens ja.
- Efter inlämning: uppdatera projektminnet (status + ev. verifikatnr).
