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

## Kom igång
1. **Klona** repot och öppna mappen i Claude Code.
2. **Lägg in ditt bolag:** kopiera `Om mig/EXEMPEL-Bolagsfakta.md` → `Om mig/Bolagsfakta.md` och fyll i.
   Lägg dina bolagsdokument (bolagsordning, registerutdrag m.m.) i `Om mig/` (gitignorerat).
3. **Anslut Fortnox** via din Fortnox-MCP-connector (OAuth ligger i din globala Claude-config, aldrig i repot).
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
