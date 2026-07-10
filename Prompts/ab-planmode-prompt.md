# AB Plan Mode Prompt

Du är i Plan Mode. Ändra inga filer, radera inget, skapa inget och kör inga riskabla kommandon ännu. Din första uppgift är att förstå projektet `AB`, inspektera hela mappstrukturen och skapa en genomtänkt arbetsplan innan implementation.

# Projektets syfte

Detta projekt ska hjälpa mig att hantera administration, redovisning, moms, årsredovisning, Inkomstdeklaration 2, myndighetskontakt och möjliga integrationer/automationer för ett svenskt aktiebolag.

Jag är ny både inom företagande, årsredovisning, Inkomstdeklaration 2 och delar av Claude Code/automation. Därför måste arbetet vara pedagogiskt, stegvis, försiktigt och tydligt. Kör inte på rakt igenom. Ställ många följdfrågor när något är oklart.

# Viktig bolagskontext

Jag driver ett svenskt aktiebolag som startades i november 2024.

Bolaget har fått förlängt första räkenskapsår: från november 2024 till 31 december 2025.

Det viktigaste första arbetet är:

1. Förstå exakt vad som måste göras.
2. Göra årsredovisningen först.
3. Därefter förbereda och göra Inkomstdeklaration 2.
4. Fortsätta använda projektet för kvartalsvis momsredovisning.
5. På sikt automatisera så mycket som möjligt via Fortnox, Skatteverket, Bolagsverket, n8n, MCP, Claude Code och relevanta API:er.

Jag tror att Inkomstdeklaration 2 i praktiken inte kan göras korrekt innan årsredovisningen/bokslutsunderlaget är klart. Kontrollera detta mot projektets källor och officiell dokumentation.

# Projektstruktur

Inspektera hela mappen `AB`.

Den innehåller fyra huvudmappar:

1. `Uppgifter att utföra`
   - Innehåller aktuella uppgifter.
   - Just nu finns brev/påminnelser från Skatteverket och Bolagsverket.
   - Denna mapp ska styra vad som är mest akut.

2. `Knowledge Base`
   - Största mappen.
   - Innehåller dokumentation och kunskap från bland annat:
     - Bolagsverket
     - Bokföringsnämnden
     - Skatteverket
     - Fortnox
   - Den har flera undermappar och underkategorier.
   - Den ska användas som primär kunskapskälla.

3. `Om mig`
   - Innehåller information om mig, mitt bolag och juridiska fakta om företaget.
   - Här finns bolagsspecifika dokument och fakta.
   - Använd denna mapp för faktisk bolagskontext, men exponera inte känslig information i onödan.

4. `Prompts`
   - Innehåller åtta specialistprompts.
   - Gå igenom dessa och föreslå hur de ska användas i arbetsflödet.
   - Bedöm om de är rätt placerade, om någon ska uppdateras, och hur de ska kopplas till olika typer av uppgifter.

# Viktiga frågor att analysera i Plan Mode

Du ska planera projektet innan något görs.

Analysera:

- Vilka filer och mappar finns?
- Är nuvarande mappstruktur bra för bästa möjliga output?
- Ska jag behålla allt i samma lokala folder?
- Behöver jag skapa vector database, till exempel Pinecone?
- Är Obsidian vault bättre för detta material?
- Eller är nuvarande mappstruktur med Markdown-filer tillräcklig och bäst?
- Hur ska knowledge base organiseras för att Claude Code ska kunna använda den effektivt?
- Hur ska specialistprompts användas praktiskt?
- Vilken ordning ska arbetet göras i?
- Vad är akut på grund av Skatteverket/Bolagsverket-brev?
- Vilka delar kan automatiseras?
- Vilka delar bör endast vara semi-automatiska med mänsklig kontroll?
- Vilka delar får aldrig automatiseras utan uttryckligt godkännande?
- Vilka integrationer/API:er är realistiska?
- Vilka API:er kräver avtal, auth, scopes, e-legitimation, testmiljö eller manuell inloggning?
- Hur ska Fortnox kopplas in praktiskt?
- Vad kan Claude Code faktiskt göra säkert?
- Vad måste göras manuellt i Skatteverkets eller Bolagsverkets e-tjänster?

# Integrationer och automation

Jag vill automatisera så mycket som möjligt, men säkert.

Knowledge Base innehåller dokumentation om API:er och integrationer för bland annat:

- Fortnox
- Skatteverket
- Bolagsverket
- Claude Code
- MCP
- n8n
- eventuellt ChatGPT/Fortnox-kopplingar

Analysera vad som faktiskt är möjligt.

Dela upp allt i:

## Manual

Användaren gör själv, men agenten förklarar, kontrollerar och skapar underlag.

## Semi-automatic

Agenten hämtar/läser/kontrollerar data och skapar underlag, men användaren godkänner och skickar in.

## Automatic

Workflow utför åtgärden själv, men endast där risk, auth, rollback och behörigheter är tydligt verifierade.

För årsredovisning, Inkomstdeklaration 2, momsdeklarationer, bokföring, myndighetskontakt och skattedata ska semi-automatic vara default tills annat är säkert verifierat.

# Säkerhet och begränsningar

- Ändra inga filer i Plan Mode.
- Radera inget.
- Skapa inga nya integrationer ännu.
- Autha inte mot Fortnox, Skatteverket eller Bolagsverket ännu.
- Skicka inte in något.
- Bokför inget.
- Skapa inte fakturor.
- Gör inga API write-actions.
- Exponera inte secrets, tokens, klienthemligheter, API-nycklar, personuppgifter eller känsliga bolagsuppgifter.
- Gissa inte regler, datum, fält, API:er, scopes eller myndighetsprocesser.
- Om något är oklart, fråga.
- Om en fråga kan påverka skatt, juridiskt ansvar, årsredovisning, deklaration, revision, kapitalbrist eller myndighetsärende: markera risknivå tydligt.

# Arbetsmetod

1. Inspektera först hela `AB`-mappen.
2. Skapa en tydlig inventory över mappar och viktiga filer.
3. Identifiera vilka dokument som är bolagsspecifika och vilka som är generell knowledge base.
4. Identifiera vilka uppgifter som är akuta.
5. Gå igenom alla åtta prompts och föreslå hur de ska användas.
6. Bedöm om nuvarande filstruktur är tillräcklig eller om annan lösning behövs.
7. Föreslå bästa projektarkitektur för lokal Claude Code-användning i VS Code/CLI.
8. Skapa en steg-för-steg-plan för årsredovisning först.
9. Skapa därefter plan för Inkomstdeklaration 2.
10. Skapa plan för kvartalsvis momsredovisning.
11. Skapa plan för Fortnox- och API-integrationer.
12. Lista följdfrågor innan implementation.

Tänk mycket noga innan du svarar. Det här är ett stort projekt och första planen ska vara genomtänkt.

# Följdfrågor

Ställ så många följdfrågor som krävs för ett korrekt upplägg. Begränsa inte frågorna om de behövs för resultatet.

Prioritera frågor om:

- deadline för Bolagsverket och Skatteverket
- räkenskapsår
- om bokföringen är klar
- om Fortnox används fullt ut
- om momsrapporter finns
- om bank och skattekonto är avstämda
- om bokslutsunderlag finns
- om årsredovisning redan är påbörjad
- om bolaget har revisor eller är revisionspliktigt
- om Fortnox API/auth finns
- om n8n ska användas lokalt eller cloud
- om integrationer ska vara read-only först
- om användaren vill ha utbildande förklaring steg för steg

# Förväntad output i Plan Mode

Svara på svenska och skapa en plan med denna struktur:

## 1. Kort förståelse av projektet

Sammanfatta vad projektet ska göra och vilken ordning arbetet bör ha.

## 2. Inventory av mappstrukturen

Lista huvudmappar, undermappar och viktiga filer som du hittar.

## 3. Akuta uppgifter

Identifiera vad i `Uppgifter att utföra` som måste hanteras först.

## 4. Rekommenderad arbetsordning

Ge en prioriterad ordning, t.ex.:

1. Projektstruktur och källkontroll
2. Årsredovisning
3. Inkomstdeklaration 2
4. Momsredovisning
5. Fortnox/exporter
6. Integrationer och automation
7. Löpande arbetsrutiner

Justera efter vad filerna visar.

## 5. Bedömning av knowledge-struktur

Jämför alternativen:

- behålla Markdown-filer i lokal folder
- Obsidian vault
- vector database/Pinecone
- annan lösning

Ge en konkret rekommendation med fördelar, nackdelar och risker.

## 6. Specialistprompts

Lista de åtta prompts du hittar och föreslå när varje prompt ska användas.

## 7. Årsredovisningsplan

Skapa en konkret plan för första årsredovisningen för svenskt aktiebolag med förlängt första räkenskapsår.

## 8. Inkomstdeklaration 2-plan

Skapa plan för vad som krävs efter årsredovisningen/bokslutsunderlaget.

## 9. Momsplan

Skapa plan för kvartalsvis momsredovisning och vilka Fortnox-rapporter/underlag som behövs.

## 10. Integrations- och automationsplan

Dela upp möjliga flöden i manual / semi-automatic / automatic.

## 11. Risker och gränser

Lista risker, särskilt kring skatt, myndigheter, API write-access, auth och felaktiga underlag.

## 12. Frågor till mig innan implementation

Ställ alla frågor som behövs för att planen ska bli korrekt.

## 13. Nästa steg

Föreslå exakt vad vi ska göra efter att jag godkänt planen.

# Viktig slutregel

Stanna i Plan Mode. Målet med första svaret är inte att börja göra årsredovisningen, utan att skapa en korrekt helhetsplan för hur projektet ska användas och byggas vidare.
