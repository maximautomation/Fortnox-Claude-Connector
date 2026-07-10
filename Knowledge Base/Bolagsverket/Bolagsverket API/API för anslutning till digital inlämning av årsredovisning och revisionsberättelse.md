---
title: "API för anslutning till digital inlämning av årsredovisning och revisionsberättelse"
source: "https://bolagsverket.se/apierochoppnadata/lamnaforetagsinformation/digitalinlamningavarsredovisningochrevisionsberattelse/apiforanslutningtilldigitalinlamningavarsredovisningochrevisionsberattelse.5936.html"
author:
published: 2026-07-02
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
Vill du utveckla stöd för digital inlämning av årsredovisning och revisionsberättelse? Här kan du läsa om förutsättningarna och hur anslutningsprocessen går till.

## Hög belastning i anslutningsprocessen

Just nu har vi kö i vår granskning av testfiler. Vi hanterar förfrågningar om anslutning och uppstartsmöte löpande och så fort vi kan.

2026-07-02

## Så här går det till att ansluta till tjänsten Lämna in årsredovisningen digitalt

### Förbered – inget avtal krävs

Ta del av den [tekniska dokumentationen](https://bolagsverket.se/apierochoppnadata/lamnaforetagsinformation/digitalinlamningavarsredovisningochrevisionsberattelse/tekniskdokumentationfordigitalinlamningavarsredovisning.5937.html) och de tips vi har gällande taggning av data med mera på sidan [Förutsättningar vid införande av elektroniska årsredovisningshandlingar i Inline XBRL-format](https://bolagsverket.se/apierochoppnadata/lamnaforetagsinformation/digitalinlamningavarsredovisningochrevisionsberattelse/forutsattningarvidinforandeavelektroniskaarsredovisningshandlingariinlinexbrlformat.5957.html). Information om publicerade taxonomier finns på [taxonomier.se Länk till annan webbplats.](http://taxonomier.se/).  
  
Med dokumentationen som stöd skapar du sedan testfiler med eget testdata som motsvarar verklig redovisning och innehållet i en årsredovisning.

#### Testa i testbänk

För att testa filerna från ert program eller tjänst kan du använda vår testbänk. Det är viktigt att testfilen validerar och att du uppmärksammar eventuella varningar och hinder som faller ut.  
  
Tjänsten består av två delar:

- Webbsida för att kontrollera iXBRL (Inline Extensible Business Reporting Language)-dokument.
- Testversionerna för tjänsterna av digital inlämning.

För att ni ska komma åt [testbänken Länk till annan webbplats.](https://arsredovisning-accept2.bolagsverket.se/arsredovisning-ingivning-testbank-web/). behöver er publika ip-adress läggas till i Bolagsverkets brandvägg. Kontakta oss via formuläret [Kontakta oss om API:er och öppna data](https://bolagsverket.se/apierochoppnadata/driftochsupport/kontaktaossomapierochoppnadata.3996.html) och ange organisationsnummer, namn på ert företag, kontaktuppgifter samt er publika ip-adress så återkommer vi så snart vi kan.

#### Förväntat resultat i testbänken

Innan du kan gå vidare i anslutningsprocessen behöver du ha skapat exempelfiler med innehållet taggat och där filen validerar utan valideringsfel i testbänken. Tänk på att värdena i filerna ska bygga på en sammanhållande bokföring. Gör en fullständig årsredovisning i Inline XBRL (iXBRL) taggad med en gällande taxonomi.

När du är klar med ovanstående och känner dej redo för att ta nästa steg, kontakta oss igen via formuläret [Kontakta oss om API:er och öppna data](https://bolagsverket.se/apierochoppnadata/driftochsupport/kontaktaossomapierochoppnadata.3996.html) och begär en tid för uppstartsmöte.

### Ha uppstartsmöte när du är klar med förberedelserna i föregående steg

På uppstartsmötet berättar du om din systemlösning och vad du kommer erbjuda dina användare. Du ska också visa minst en fullständig årsredovisning som du skapat – här får du en första feedback på innehållet. Vi berättar mer om den granskningsprocess som följer i nästa steg.

### Skriva avtal – krävs för att ta nästa steg

För att kunna gå vidare i processen behöver ni skriva under ett avtal som vi skickar till er efter uppstartsmötet. Vi skriver endast avtal med juridisk person där verksamhetsbeskrivningen är relevant för uppdraget.

#### Tillgång till fullständig testmiljö

När vi tagit emot ett korrekt underskrivet avtal öppnar vi till fullständig testmiljö i vår testbänk och tillhörande stöd-API:er. Nu kan du testa funktionalitet i tjänsten full ut med tillgång till mer testdata.

#### Granskningsprocess av testfiler

För att få tillgång till produktionsmiljön måste dina testfiler uppfylla vissa krav. Efter uppstartsmötet får du ett testprotokoll som beskriver vad nästa uppsättning av testfiler ska innehålla. Du skickar dem till oss för en fullständig granskning. Det här är en process som ofta tar flera månader att genomföra beroende på hur mycket som behöver justeras och kompletteras med nya testfiler. Vi gör granskningen för att säkerställa kvalitén i det taggade datat och att tillämningen av taxonomin är korrekt.

### Ansluta till produktionsmiljö

När samtliga testfiler godkänts får du tillgång till produktionsmiljön och anslutningen är klar. Om du vill kan ditt företag synas här på Bolagsverkets webbplats på sidan [Program och tjänster för att kunna skicka in årsredovisningen digitalt](https://bolagsverket.se/sjalvservice/etjanster/lamnainarsredovisningendigitalt/programochtjansterforattkunnaskickainarsredovisningendigitalt.1669.html).