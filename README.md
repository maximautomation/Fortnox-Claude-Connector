# AI-redovisning för svenskt aktiebolag

Ett arbetsutrymme för **Claude Code** som hjälper ett svenskt aktiebolag att sköta löpande
bokföring, moms, arbetsgivardeklaration, bokslut, **årsredovisning** och **Inkomstdeklaration 2**
— tillsammans med **Fortnox**. Tänkt som en återanvändbar mall: klona, lägg in ditt eget bolag,
och låt agenten agera som din semi-automatiska redovisningsbyrå.

> ⚠️ **Ansvarsfriskrivning:** Detta är ett hjälpmedel, inte auktoriserad redovisnings-, skatte- eller
> juridisk rådgivning. Du ansvarar själv för att uppgifter till Skatteverket och Bolagsverket är
> korrekta. Verifiera mot officiella källor och anlita vid behov redovisningskonsult/revisor.
> Gäller **svenska aktiebolag** (K2/K3).

## Vad du får
- **`Knowledge Base/`** — ~558 referenssidor från Skatteverket, Bolagsverket, Bokföringsnämnden och Fortnox (se `NOTICE.md`).
- **`Prompts/`** — 8 specialistprompter (bolagsrådgivare, årsredovisning, INK2, moms, Fortnox, integration, skribent, plan mode).
- **`CLAUDE.md`** — regelbok som styr hur agenten arbetar (svenska, gissa aldrig, semi-automatiskt, risknivåer, säkerhet).
- **Verktygsuppsättning** — Fortnox-connector (MCP), Playwright MCP (webbautomation), samt `pdf`- och `xlsx`-skills.

## Arbetssätt
Semi-automatiskt är standard: agenten **förbereder och kontrollerar**, användaren **godkänner och
signerar med BankID**. Agenten skickar aldrig in något till en myndighet själv — sista signaturen är
alltid användarens.

## Så skapas & lämnas årsredovisningen in (steg för steg)
Årsredovisningen byggs i **Fortnox Bokslut & Skatt** (webbmodul) som agenten
driver med **Playwright**, medan bokföringsdata läses/bokförs via **Fortnox
Claude Connector**. Grovt flöde:

1. **Agenten:** stämmer av bokföringen, bokför årets resultat, och fyller i hela
   årsredovisningen (K2, digital) + årsstämmoprotokoll i Bokslut & Skatt.
2. **Agenten:** kör "Kontroll mot Bolagsverket" och låser dokumenten.
3. **Du:** signerar årsredovisningen med **BankID**.
4. **Agenten:** förbereder den digitala inlämningen (fastställelseintyg,
   undertecknare, datum) och trycker "Lämna in" till Bolagsverket.
5. **Du:** får ett mejl och **BankID-signerar fastställelseintyget** i
   Bolagsverkets *Eget utrymme* inom 21 dagar → årsredovisningen registreras.

Den detaljerade exekverings-runbooken (stegordning, Playwright-mönster,
felsökningstabell) ligger i skillen **`.claude/skills/arsredovisning-fortnox/`**.
Metodiken/regelverket finns i `Prompts/arsredovisning-prompt.md`.

## Varför inte Agent SDK / context7 / pydantic?
- **Agent SDK** bygger *fristående produktionsagenter* (headless/CI-CD). Vår
  process kräver **människa + BankID** i loopen och partner-API:er → full
  automation är omöjlig. Claude Codes inbyggda **skills/hooks/subagents** ger
  samma nytta interaktivt utan API-nyckel/hosting.
- **context7** (dok-hämtare) behövs inte — domänreglerna täcks av `Knowledge
  Base/` + WebSearch. Kan återintroduceras om vi bygger Fortnox-API/n8n.
- **pydantic** (sifferkontroll) vore dubbelarbete: Fortnox-modulen och
  Bolagsverkets kontroll validerar redan siffrorna, och problemet var UI, inte
  numeriken. Projektet hålls kodfritt.

## Kom igång
1. **Klona** repot och öppna mappen i Claude Code.
2. **Lägg in ditt bolag:** kopiera `Om mig/EXEMPEL-Bolagsfakta.md` → `Om mig/Bolagsfakta.md` och fyll i.
   Lägg dina bolagsdokument (bolagsordning, registerutdrag m.m.) i `Om mig/` (gitignorerat).
3. **Anslut Fortnox:** connectorn är deklarerad **projekt-scopat** i `.mcp.json` (`fortnox`, http). Godkänn/OAuth:a den vid första körningen — **OAuth-token lagras av Claude Code, aldrig i repot**. Har du sedan tidigare samma connector i din *globala* config: ta bort den globala posten så du slipper dubblett (kör `--transport http`, inte stdio).
4. **Installera skills:** `npx skills add anthropics/skills@pdf` och `@xlsx` (se `skills-lock.json`).
5. *(Valfritt)* **Playwright** för webbautomation: finns i `.mcp.json`; kör `npx playwright install chromium` och starta om Claude Code.
6. Berätta för agenten vad du vill göra — den läser `CLAUDE.md`, `Om mig/` och `Knowledge Base/` först.

## Struktur
```
CLAUDE.md              Regelbok (läses först varje session)
README.md / NOTICE.md  Denna fil / källattribuering för KB
Knowledge Base/        Referenskunskap (Skatteverket, Bolagsverket, BFN, Fortnox)
Prompts/               8 specialistprompter
Arbete/                Genererade underlag (struktur spåras, skarpa siffror gitignoreras)
Om mig/                DITT bolags fakta (gitignorerat utom mall + README)
Underlag-*/            Bank/skattekonto/moms (gitignorerat)
Uppgifter att slutföra/ Myndighetsbrev (gitignorerat)
```

## Säkerhet (viktigt)
Repot är byggt så att **ingen privat data följer med publikt**. Gitignorerat: `Om mig/` (utom mall),
`Underlag-*/`, `Uppgifter att slutföra/`, skarpa `Arbete/`-filer, samt allt som ser ut som secrets
(`*.env`, `*token*`, `*secret*`, `*.key`, `*.pem`) och `.playwright-profile/`. **API-nycklar och
Fortnox-OAuth lagras aldrig i repot** — de ligger i användarens globala Claude-config. Kontrollera
alltid `git status` innan du pushar.
