# CLAUDE.md — AI-redovisning för svenskt aktiebolag

Arbetsutrymme för att sköta administration, löpande bokföring, moms, arbetsgivardeklaration,
bokslut, årsredovisning, Inkomstdeklaration 2 och myndighetskontakt för ett **svenskt aktiebolag**
med hjälp av Claude Code + Fortnox. **Läs detta först varje session.**

> **Mall/återanvändning:** Detta repo är byggt för att kunna klonas och återanvändas av andra bolag.
> Alla bolagsspecifika fakta ligger i den **gitignorerade** mappen `Om mig/`. Klonar du repot:
> kopiera `Om mig/EXEMPEL-Bolagsfakta.md` → `Om mig/Bolagsfakta.md` och fyll i ditt eget bolag.
> Se `README.md` för uppsättning och säkerhetsmodell.

## Läs först varje session (obligatoriskt)
1. **`Om mig/Bolagsfakta.md`** + övriga `Om mig/`-filer — bolagets faktiska uppgifter (känsligt).
2. **Projektminnet** (`MEMORY.md` som laddas in) — aktuellt arbetsläge, vad som är klart, nästa steg.
3. **`Uppgifter att slutföra/`** — akuta myndighetsuppgifter som styr prioritet.

## Bolaget
Se **`Om mig/Bolagsfakta.md`**. **Gissa aldrig** org.nr, datum, räkenskapsår, regelverk (K2/K3),
momsperiod, faktureringsmetod eller registreringar — läs dem där eller fråga.

## Arbetsregler (viktigast)
1. **Svara alltid på svenska.** Pedagogiskt och stegvis — anta att användaren är ny inom företagande.
2. **Gissa aldrig** regler, datum, siffror, fält, momssatser, gränsvärden, scopes eller myndighetsprocesser. **Sök först i `Knowledge Base/`** (karta nedan) och verifiera mot officiella källor.
3. **Semi-automatiskt för myndighetsärenden:** inför inlämning till Skatteverket/Bolagsverket förbereder och kontrollerar jag; användaren godkänner och signerar med **BankID**.
4. **Fortnox-bokföring:** om användaren gett **stående godkännande** får verifikat skapas/ändras/raderas via connectorn utan att fråga varje gång — men **redovisa alltid verifikatnr + effekt**, och **fråga ändå först vid:** (a) inlämning till myndighet (kräver BankID), (b) misstänkta/oväntade/högriskposter, (c) borttag av data jag inte själv skapat som motsäger underlagen. *(Stående godkännande finns i detta projekt fr.o.m. 2026-07-10.)*
5. **Exponera aldrig** secrets, tokens, API-nycklar, personnummer, skattekontodata eller känsliga bolagsuppgifter — vare sig i svar, filer eller commits.
6. Markera **risknivå** (low / check required / high) vid skatt, juridiskt ansvar, kapitalbrist, revision eller myndighetsärende.
7. Redovisa **källa/underlag** per steg. Stanna för godkännande vid varje större steg.
8. **Autha inte** mot Skatteverket/Bolagsverket utan överenskommelse. Fortnox är authad med skrivbehörighet enligt användarens medgivande.

## Knowledge Base — använd den, gissa inte (~558 filer)
Primär kunskapskälla. **Sök här FÖRST** innan du svarar på regel-/skatte-/redovisningsfrågor. Struktur:
- **`Knowledge Base/Skatteverket/`** — Moms, Skatter och avdrag, Aktiebolag, Inkomstdeklaration, Statligt stöd, samt Skatteverket API.
- **`Knowledge Base/Bolagsverket/`** — Aktiebolag (Driva aktiebolag), Årsredovisning för aktiebolag, Bolagsverket API.
- **`Knowledge Base/Fortnox/`** — Produkthjälp (Bokföring, Bokslut & Skatt, m.m.).
- **`Knowledge Base/Bokföringsnämnden/`** — Att Föra Bok, Årsredovisning i mindre företag (K2).

Innehållet är klippt från officiella källor för referens (se `NOTICE.md`). Verifiera mot aktuell officiell källa vid osäkerhet — regler och belopp ändras.

## Källprioritet
1. `Om mig/` (bolagsspecifika fakta) och `Uppgifter att slutföra/` (myndighetsbrev).
2. Faktiska underlag: bankutdrag, skattekonto, momsdeklarationer, Fortnox-exporter (`Arbete/`, `Underlag-*/`).
3. `Knowledge Base/` (kartan ovan).
4. Officiella källor / aktuell dokumentation (verifiera vid osäkerhet).
5. Generell kunskap endast när primära källor saknas — markera då osäkerhet.

## Promptkarta (`Prompts/`)
| Uppgift | Använd prompt |
|---|---|
| Oklar fråga / orkestrering / riskbedömning / roll som redovisningsbyrå | `bolagsradgivare-prompt.md` |
| Årsredovisning | `arsredovisning-prompt.md` |
| Inkomstdeklaration 2 | `inkomstdeklaration2-prompt.md` |
| Momsdeklaration | `momsdeklaration-prompt.md` |
| Arbete/kontroll i Fortnox | `fortnox-prompt.md` |
| Integrationer / n8n / MCP / API / verktyg | `integration-prompt.md` |
| Myndighetsmejl och brev | `skribent-prompt.md` |
| Plan mode | `ab-planmode-prompt.md` |

## Mappstruktur
- `Om mig/` — bolagsspecifika fakta (**känsligt, gitignorerat** utom mall + README).
- `Uppgifter att slutföra/` — akuta myndighetsuppgifter (**gitignorerat**).
- `Underlag-*/` — bank-, skattekonto- och momsunderlag (**känsligt, gitignorerat**).
- `Knowledge Base/` — primär kunskapskälla (spårad).
- `Prompts/` — specialistprompter (spårad).
- `Arbete/` — genererade underlag och arbetsfiler. Mappstruktur + README spåras; **skarpa filer med verkliga siffror gitignoreras.**

## Verktyg (MCP & skills)
- **Fortnox Claude Connector** (MCP) — läser bokföring/konton/SIE och kan skapa/ändra verifikat (per godkännande). OAuth ligger i användarens globala Claude-config, **inte i repot**.
- **Playwright MCP** (`.mcp.json`) — webbautomation för att fylla i Fortnox Bokslut & Skatt och myndighets-e-tjänster. Kräver omstart för att laddas; inloggning + BankID görs av användaren.
- **Skills:** `pdf` och `xlsx` (Anthropic) — läsa/fylla PDF (kvitton, deklarationer) och bygga kalkyler. Installeras med `npx skills add anthropics/skills@pdf` / `@xlsx` (se `skills-lock.json`).
- **Kvittotolkning:** använd inbyggd bildläsning + `pdf`-skillen → föreslå verifikation → bokför via connectorn (semi-auto).

## Säkerhet & git
- Känsliga mappar/filer gitignoreras (se `.gitignore`): `Om mig/`, `Underlag-*/`, `Uppgifter att slutföra/`, skarpa `Arbete/`-filer, samt `*.env`, secrets, tokens, nycklar och `.playwright-profile/`.
- **Ladda aldrig upp personuppgifter, kontouppgifter eller API-nycklar publikt.** Repot är byggt så att andra kan klona strukturen utan tillgång till något bolags privata data.

## Automation
Full autonom myndighetsinlämning är **inte** möjlig: sista signaturen kräver användarens BankID som
firmatecknare, och myndighets-API:er är partner-API:er. Realistisk väg = connectorn (read-only först)
för att hämta data och förbereda underlag; Playwright för att fylla i webbmoduler; **användaren
signerar och skickar in.** Semi-automatiskt är standard för allt myndighets- och bokföringsnära arbete.
