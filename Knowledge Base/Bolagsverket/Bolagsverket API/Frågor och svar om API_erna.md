---
title: "Frågor och svar om API:erna"
source: "https://bolagsverket.se/apierochoppnadata/driftochsupport/fragorochsvaromapierna.4611.html"
author:
published: 2026-05-06
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
## Frågor och svar om våra API:er

Här hittar du frågor om API:er och öppna data.

## API för att hämta företagsinformation

## Teknik och utveckling

### Vilken teknik används i API:er från Bolagsverket?

Den förnyelse som nu genomförs på Bolagsverket innebär att nya API:er som vi tar fram är så kallade REST-API:er.

### Har API:et en tillförlitlig datakvalitet?

Den data som kommer förmedlas via den nya versionen av API:er kommer hålla samma datakvalitet som dagens lösning via XML -paket och motsvarar den information som finns registrerad hos Bolagsverket.

### Krävs det utveckling från vår sida?

Ja, för att kunna använda ett API krävs att du bygger en teknisk lösning eller applikation där API:et används.

Ja, de nycklar som behövs för vårt API kan användas av flera applikationer samtidigt hos varje kund.

### Hur lång är svarstiden i produktion?

Den genomsnittliga svarstiden från API:et är under 200 millisekunder.

### Finns det någon testmiljö för API:et?

Vi har en testmiljö där du kan testa din integration mot vårt API när du har tecknat avtal med oss. Testmiljön innehåller ett antal testföretag och testpersoner och där kan du verifiera svaren du får från API:ets operationer. Du hittar mer information om testmiljön och vårt testdata i menyn i vår [utvecklarportal Länk till annan webbplats.](https://portal-accept2.api.bolagsverket.se/devportal/apis/2d897bb7-36b2-4c91-87b4-b7bbc1211f05/overview).

### Kommer de gamla SOAP-tjänsterna ("XML-paketen") leva kvar och i så fall hur länge?

Till en början kommer tjänsterna att finnas kvar. Men de kommer att fasas ut när motsvarande funktionalitet finns i det nya API:et. Vi vet inte exakt när, men vi kommer att informera i god tid innan vi stänger XML-tjänsten.

### Finns informationen på engelska?

Nej, information/data från oss finns bara på svenska. Vi har dock beskrivande tekniska instruktioner på engelska för integrationen mot oss via API.

### Kommer utvecklingen av API:et att påverka tjänsten för att skapa lagerbolag?

Tjänsten för att registrera lagerbolag i Företagsärenden för ombud kommer att finnas kvar tillsvidare.

## Transaktioner och kostnader

### Vad kostar API:et?

Kostnaden är en anslutningsavgift som du betalar en gång. Efter det betalar du en månadsavgift för de antal transaktioner du vill kunna göra per månad.

Du hittar all information om pris på sidan [API för att hämta företagsinformation](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation.3988.html).

### Jag undrar hur ni definierar en transaktion?

En fråga är en transaktion. Frågar du efter all information i en fråga är det en transaktion. Ställer du två frågor, varav en där du frågar efter namnet och en annan där du frågar efter verksamhetsbeskrivningen blir det två transaktioner.

### Kan jag ändra nivå av tillgängliga transaktioner om det behövs?

Ja, det går lätt att ändra från en dag till den andra men vi ändrar vår fakturering en gång i månaden. Du måste skriva under ett tillägg till vårt avtal. Hör av dig via formuläret [Kontakta oss om API:er och öppna data](https://bolagsverket.se/apierochoppnadata/driftochsupport/kontaktaossomapierochoppnadata.3996.html) så hjälper vi dig!

### Om jag hämtar data som pekats ut som värdefull kommer det att räknas av från min pott av transaktioner som inkluderas i min månadsavgift?

För att den information som pekats ut som värdefull ska bli gratis behöver du använda operationerna som ingår i API för värdefulla data.

#### Exempel

Om du använder operationen/organisationer som ingår i API:et värdefulla data för att hämta information som klassas som värdefull, räknas det **inte** av från din pott av transaktioner som ingår i månadsavgiften.

Om du däremot använder operationen/organisationer som ingår i API:et för företagsinformation räknas det **alltid** av från din pott av transaktioner, oavsett om du bara hämtar information som pekats ut som värdefull.

## Information och data

### Kan jag hämta information om verklig huvudman via API?

Ja, uppgiften finns i API Företagsinformation, läs mer på sidan [API för att hämta företagsinformation](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation.3988.html).

### Kan jag hämta bolagsordning och registreringsbevis via API?

Ja. Läs mer på sidan [API för att hämta företagsinformation](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation.3988.html).

### Kommer aviseringar ändras för verklig huvudman så att det finns annat alternativ att bevaka ändringar än att få XML-filer dagligen?

Vi kommer att se över aviseringarna och hur de ska fungera, vi påbörjar en utredning under 2026.

### Kan jag hämta information om aktiekapitalförändringar i API:et?

Du kan hämta information om aktiekapitalförändringar från år 2003 och framåt.

### Vilka organisationsformer finns med i API:et?

Se fullständig lista på sidan [API för att hämta företagsinformation](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation.3988.html), vilka företagsformer som finns med i API:et.

### Kan jag söka på företagsnamn via API?

Vi vet om att det finns behov att söka på företagsnamn och det finns med bland de förbättringar som vi ska ta fram. Det finns inget planerat datum för det än.

### Finns det möjlighet att fråga om information på flera organisationer?

Nej, du kan bara fråga och få information på ett organisationsnummer åt gången.

## Övriga frågor om API:er och öppna data

### När kommer det att finnas API:er för att registrera information hos Bolagsverket?

Vårt API för att registrera företagsinformation kommer att lanseras senare än vad vi tidigare har kommunicerat. API är fortfarande en viktig del i Bolagsverkets arbete mot ett förenklat och digitalt företagande. Lanseringen senareläggs på grund av andra utvecklingsinsatser men innebär att kvaliteten ökar och att vi kan erbjuda en förbättrad upplevelse och en komplett tjänst.

Vi kan i dagsläget inte säga när lanseringen av API för att registrera företagsinformation blir. Skicka in en intresseanmälan via länken nedan så informerar vi er när det är dags.

[Kontakta oss om API:er och öppna data](https://bolagsverket.se/apierochoppnadata/driftochsupport/kontaktaossomapierochoppnadata.3996.html)

### Kan jag anmäla emissioner, fusioner, likvidationer och minskningar digitalt till Bolagsverket?

I dagsläget planerar vi inte några maskin-till-maskintjänster för dessa ärendetyper, men redan idag kan man lämna in digitalt signerade handlingar för dessa ärendetyper via verksamt.se.

### Jag har hört att man ska kunna hämta informationen utan kostnad. Stämmer det?

Viss data tillhandahålls avgiftsfritt från och med den 3 februari 2025. Läs mer på sidan [Värdefulla datamängder](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/vardefulladatamangder.5294.html).

### Kommer avgifterna för andra API:er och tjänster att ändras när årsredovisningar blir gratis?

EU-kommissionens beslut påverkar inte avgifter som idag finns vid användande av andra API:er och tjänster där information om företag och företagande förmedlas från Bolagsverket.

## API för att hämta värdefulla datamängder

### Hur får jag tillgång till värdefulla datamängder?

För att få tillgång till API:et som tillhandahåller värdefulla datamängder behöver du ange en e-postadress och ett telefonnummer dit användaruppgifterna kan skickas. Det kan du göra via [Kundanmälan till API för värdefulla datamängder](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/vardefulladatamangder/kundanmalantillapiforvardefulladatamangder.5528.html).

Finns det en testmiljö?

Ja, när vi har mottagit din kundanmälan får du tillgång till testmiljön för värdefulla datamängder.

### I vilket format är värdefulla datamängder tillgängligt?

Bolagsverket använder ett REST API med svar i JSON-format för årsredovisningar är formatet iXBRL.

### Är det Bolagsverket som har tagit beslut om värdefulla datamängder?

Det är EU-kommissionen som har tagit beslut om detta. [Värdefulla datamängder.](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/vardefulladatamangder.5294.html)

### Är det möjligt att hämta årsredovisningar som inskannade pdf-filer gratis, exempelvis zip-filer?

Det är inte möjligt att hämta inskannade årsredovisningar i pdf-format. De filer som skapas veckovis är zip-filer som innehåller alla digitalt inlämnade årsredovisningar via iXBRL -format.

### Kan jag hämta alla årsredovisningar för alla svenska företag gratis?

Du kan hämta årsredovisningar som är digitalt inlämnade i iXBRL format från och med 2020 då de första årsredovisningarna lämnades in i det formatet.

### Kan jag hämta årsredovisningar för bostadsrättsföreningar gratis?

Nej, i dagsläget kan bostadsrättsföreningar inte lämna in sin årsredovisning i formatet iXBRL.