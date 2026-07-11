---
name: inkomstdeklaration2-fortnox
description: >-
  Använd när uppgiften rör att upprätta, kontrollera, fylla i eller digitalt
  lämna in en svensk Inkomstdeklaration 2 (INK2 med INK2R + INK2S) i Fortnox
  "Bokslut & Skatt" → Skatt-modulen, driva den via webben med Playwright, samt
  digital inlämning till Skatteverket (direkt-API eller SRU-filöverföring).
  Kräver Fortnox Claude Connector + Playwright MCP. Generell — inga bolagsuppgifter.
metadata:
  type: reference
---

# Inkomstdeklaration 2 i Fortnox Bokslut & Skatt — praktisk runbook

**Exekveringslagret** (hur man gör). Regelverk/metodik finns i
`Prompts/inkomstdeklaration2-prompt.md`; siffrorna ska redan vara avstämda och
bokslutet klart innan Skatt-modulen öppnas. Delade Fortnox-/Playwright-mönster
(iframe-SPA, flyktiga refs, URL-navigering, `browser_evaluate`-batchning, sticky
headers) är samma som för [[arsredovisning-fortnox]] — läs den skillen först och
återanvänd mönstren istället för att upprepa dem.

## Princip
Semi-automatiskt: agenten bygger, kontrollerar och fyller i; **användaren
signerar med BankID och gör den slutliga "Skriv under och skicka in".** INK2
bygger på det **stängda bokslutet** — årsredovisning/bokslut ska vara klart och
låst först (INK2R hämtas därifrån).

## 0. Preflight
1. `/mcp` → **Fortnox-connector** + **Playwright** = "connected". Annars stanna.
2. Läs bolagets fakta ur `Om mig/` (säte, firmatecknare/VD, org.nr, regelverk). **Gissa aldrig.**
3. Bekräfta via connectorn att bokföringen balanserar och att årets resultat är
   bokfört. Hämta gärna SIE (`sie/4`) och gör en **torrkörning** (INK2R rad för
   rad, INK2S-justeringar, skatteberäkning) som användaren godkänner **innan**
   webbmodulen rörs. Spara i `Arbete/Inkomstdeklaration2/` (gitignorerad).

## 1. Torrkörning: vad Fortnox gör automatiskt vs manuellt
- **INK2R (räkenskapsschema) auto-hämtas** helt från bokslutet via SRU-koder.
- Fortnox **auto-hanterar även vissa INK2S-justeringar** från skatteberäkningen,
  t.ex. **ej avdragsgill räntekostnad på skattekonto** (konto 8423 → 4.3c) och
  **skattefri ränteintäkt på skattekonto** (konto 8314 → 4.5c). Läs därför av
  det **auto-beräknade underskottet/överskottet** och lägg bara till det Fortnox
  **missar**.
- **Vanliga poster Fortnox missar** (måste läggas manuellt):
  - **Representationsmåltider** (lunch/middag) bokförda på ett konto som heter
    "avdragsgill" (t.ex. 6071): ej avdragsgilla för inkomstskatt (bara enklare
    förtäring ≤ 60 kr/pers) → återläggs i **4.3c**. Fortnox litar på kontots
    "avdragsgill"-etikett och återlägger dem inte.
  - **4.20 Lån från aktieägare (fysisk person)** vid årets utgång — upplysning,
    fylls sällan automatiskt.
  - **Upplysningar om årsredovisningen:** "Uppdragstagare har biträtt" (Ja/Nej)
    och "Årsredovisningen reviderad" (Ja/Nej).
  - **4.14a Outnyttjat underskott från föregående år** (om sådant finns).
- Markera risknivå; ej avdragsgilla poster är den vanligaste **check required**.

## 2. Stegordning i Skatt-modulen (klick-för-klick)
1. **Bokslut & skatt** → välj **rätt räkenskapsår** (periodväljaren, t.ex. "-25")
   → flik **Skatt** (URL slutar `…/<datum>/taxdeclaration`).
2. Deklarationen kan redan vara **auto-skapad** (kort "INK2 / Inkomstdeklaration 2").
   Annars **+Deklaration** → bocka **Inkomstdeklaration 2** → **Skapa blankett**.
   Lägg bilagor (N3B/N4/N7/N8/N9) bara om de faktiskt behövs.
3. **Öppna blanketten genom att klicka på RADEN/kortet** — inte på "Redigera"
   (den knappen byter bara namn på kortet). URL får en `#form-…`-hash.
4. Kontrollera **auto-hämtade INK2R-siffror** mot torrkörningen (nettoomsättning,
   kostnadsrader, årets resultat, BR-summor). Ska stämma exakt.
5. Fyll de manuella INK2S-fälten (se nedan om hur) och upplysningarna.
6. Kontrollera **"Slutlig sammanställning skatt"** (sista sidan): slutlig skatt,
   preliminär skatt, belopp att betala/få tillbaka.

## 3. Blanketten är en PDF-overlay — så hittar och redigerar du fält
- Fälten är **absolut-positionerade `<input>`** ovanpå en bakgrundsbild.
  **Fältkoderna (3.1, 4.3c …) finns i bilden, inte i DOM-texten** → du kan inte
  hitta ett fält via etikettext.
- **Lokalisera fält via värde + kolumnposition** (`getBoundingClientRect` i
  `browser_evaluate`): läs alla `input` med `{x,y,value}`, sortera på `y`, och
  mappa mot blankettens fältordning. **Bekräfta alltid med en skärmbild** innan du
  skriver — vid minsta tvekan **rita en färgad `outline`/bakgrund på
  kandidatfälten** och ta en skärmbild för att se exakt vilken rad varje ligger på.
- **Redigering av textfält: native value-setter FASTNAR INTE** (React återställer
  fältet). Använd **äkta tangentbord**:
  1. `browser_evaluate`: hitta rätt input, `el.focus(); el.select();`
  2. `browser_press_key`: `ControlOrMeta+a` → `Delete` → siffror en och en → `Tab`.
  3. Läs `activeElement.value` före `Tab`, och verifiera att beroende summor
     (t.ex. 4.16 underskott) **räknar om** efteråt.
- **Kryssrutor:** `el.click()` i `browser_evaluate` fungerar (fyrar rätt events).
- Efter en manuell override visar högerpanelen "Fältändringar" vilka fält som
  ändrats — bra kvittens på att overriden registrerats.

## 4. Inlämning — två vägar (signering alltid användarens BankID)
**A. Direkt-API (nyast, rekommenderas — färre steg):**
1. Flik **"Inlämning"** → per blankett **"Markera som klar"** (intern status,
   inget skickas). Blanketter som inte är "klara" kommer inte med.
2. **"Lämna in till Skatteverket"** → underlaget skickas via Skatteverkets API
   till bolagets **egna utrymme** (ett **utkast** — inget är signerat än).
   Obs: **bara ett utkast åt gången** i egna utrymmet; en ny inlämning **ersätter**
   det förra → inkludera **alla** blanketter vid varje inlämning.
3. **"Direktlänk till eget utrymme hos Skatteverket"** öppnar Skatteverkets
   "Granska och skicka in" (ny flik). **Användaren loggar in med BankID.**
4. **Verifieringsgrind:** läs Skatteverkets granskningssida **post för post** mot
   torrkörningen/bokslutet och ge **grön signal** innan signering.
5. Användaren bockar "Jag har granskat uppgifterna" → **"Skriv under och skicka
   in"** → BankID → **kvittensnummer**. Spara kvittensen.

**B. SRU-filöverföring (alternativ):** i blanketten **"Hämta SRU"**
(`blanketter.sru` + `info.sru`) → Skatteverkets **Filöverföring** → användaren
laddar upp → signerar på **Mina sidor** med BankID. Använd om direkt-API inte är
tillgängligt.

## 5. Verifieringsgrindar (före signering)
- **INK2R stämmer mot bokslutet:** RR:s årets resultat = BR:s; BR balanserar
  (tillgångar = EK + skulder).
- **INK2S konsekvent:** 4.1-4.2 = årets resultat; 4.15-4.16 = det som förs till
  förstasidans 1.1/1.2.
- **Skatteberäkning** rimlig (0 skatt vid underskott; kontrollera annars satsen).
- **Skatteverkets granskningssida** genomläst rad för rad = matchar.
- **Behörig undertecknare:** firmatecknare/VD registrerad hos Bolagsverket.

## 6. Gränser (stanna alltid)
- **BankID-inloggning och "Skriv under och skicka in"** är enbart användarens —
  förbered fram till knappen, stanna, ge grön signal, be om bekräftelse.
- Klicka inte "Lämna in till Skatteverket"/skicka SRU utan användarens uttryckliga ja
  (myndighetsåtgärd).
- Exponera aldrig personnummer/kvittensdata i repo-spårade filer eller commits.
- Efter inlämning: uppdatera projektminnet (kvittensnummer, datum, sparat
  outnyttjat underskott till nästa år) och spara underlag i `Underlag-*/`.
