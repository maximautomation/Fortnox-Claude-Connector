---
title: "Börja använda API:er"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier.4.77f3e230191ef88bf1d585.html"
author:
published:
created: 2026-07-09
description: "Börja med att ansöka om tillgång, skaffa någon form av elektronisk legitimation och implementera en säkerhetslösning. Följ våra guider för att komma igång."
tags:
  - "clippings"
---
Hur du använder våra API:er kan skilja sig åt beroende på vilket API det gäller, samt vilken miljö du vill använda. Du kan bland annat behöva ansöka om tillgång, skaffa någon form av elektronisk legitimation och implementera en säkerhetslösning.

- Följ våra guider för att komma igång

[Kom igång med kompletta testtjänster eller driftsatta tjänster](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier.4.77f3e230191ef88bf1d585.html#komplettatesttjansterellerdriftsattatjanster)

[Få Client ID och Client secret (API-nycklar)](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier.4.77f3e230191ef88bf1d585.html#ClientID)

[Om våra säkerhetslösningar](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier.4.77f3e230191ef88bf1d585.html#sakerhetslosningar)

[Se till att användaren av ditt system kan identifiera sig med e-legitimation eller organisationslegitimation](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier.4.77f3e230191ef88bf1d585.html#elegitimation)

[Se till att användaren av ditt affärs- eller lönesystem har rätt behörigheter](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier.4.77f3e230191ef88bf1d585.html#behorigheter)

- Kom igång med kompletta testtjänster eller driftsatta tjänster

För att använda våra kompletta testtjänster eller driftsatta tjänster behöver du begära tillgång. Det gör du genom att fylla i ett formulär. För våra driftsatta tjänster kommer du också behöva teckna ett avtal eller en överenskommelse med Skatteverket. Villkor och avtal kan skilja sig åt mellan olika API:er. Läs därför noga igenom avtal, villkor och förändringspolicy innan du begär tillgång till ett API. Du hittar alla dokument du behöver på respektive API:s sida på Utvecklarportalen.

På sidan Så kan du använda våra API-miljöer hittar du mer information om våra kompletta testtjänster och driftsatta tjänster.

- [Avtalsprocess för partner-API:er](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/avtalsprocessforpartnerapier.4.96cca41179bad4b1aacb46.html)
- [Så använder du våra API-miljöer](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/saanvanderduvaraapimiljoer.4.96cca41179bad4b1aacb56.html)
- [Utvecklarportalen Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen)

## Få Client ID och Client secret (API-nycklar)

När Skatteverket godkänt din förfrågan får du de så kallade API-nycklarna.

För kompletta testtjänster skickar vi nycklarna till e-postadressen du angett i formuläret. För driftsatta tjänster skickas nycklarna uppdelade. En nyckel skickas till mejl och en via sms enligt de kontaktuppgifter du lämnade i formuläret. API-nycklarna fungerar som ett id och lösenord kopplat till ditt affärs- eller lönesystem (API-konsument). Du kan aldrig använda samma API-nycklar för kompletta testtjänster och driftsatta tjänster.

Här kan du lära dig mer:

- [Så fungerar API-nycklar](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/safungerarapinycklar.4.96cca41179bad4b1aa9176.html)

### Olika scope för olika API:er

- Du kan använda API-nycklarna för mer än en driftsatt tjänst, förutsatt att de ska användas för samma system på din sida. Innan du kan göra det behöver vi först koppla ett nytt scope till din användare. Om du vill återanvända API-nycklar fyller du i fältet "Vill du återanvända API-nycklar?" i anslutningsformuläret.

- Om våra säkerhetslösningar

Det är viktigt att du känner till säkerhetsramverket OAuth2 eftersom det används för autentisering och auktorisation. Olika API:er använder olika flöden och kombinationer med antingen e-legitimation eller organisationslegitimation.

- [Så fungerar våra säkerhetslösningar](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/safungerarvarasakerhetslosningar.4.96cca41179bad4b1aa8e51.html)
- [Organisationslegitimation och ombudsrollen](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/organisationslegitimationochombudsrollen.4.7da1d2e118be03f8e4f8d63.html)

### Hämta ett testcertifikat eller en e-legitimation för test

För kompletta testtjänster kan du behöva ett testcertifikat eller en e-legitimation för test.

Ditt affärs- eller lönesystem kan även använda båda autentiseringsmetoderna och du behöver då både certifikat och e-legitimation.

För e-legitimation/personlig inloggning:

- [Använd Test bank-id Länk till annan webbplats.](https://www.bankid.com/utvecklare/test/skaffa-testbankid/test-bankid-get)

För närvarande utfärdar bara ett företag i Sverige organisationslegitimation.  
Ladda ner testorganisationscertifikatet hos Expisoft, under Testcertifikat server- och stämpellegitimationer.

- [Expisoft test Länk till annan webbplats.](https://eid.expisoft.se/expitrust-test-certifikat/)

### Börja testa

För att börja använda den kompletta testtjänsten klickar du på länken Utforska API-definitionen på respektive API:s sida på Utvecklarportalen. API:ets definition berättar i mer detalj hur det fungerar praktiskt. Med datan som presenteras i API-konsolen kan utvecklare snabbt få reda på vilka url:er som ska användas för att anropa API:et, vilken typ av anrop som ingår, vilka felkoder som finns och vad de kan bero på.

- [API-konsolen – så kan du använda den](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/apikonsolensafungerardenmedskatteverketsapier.4.6e8a1495181dad540845fb1.html)
- Bygg eller integrera ditt affärs- eller lönesystem
- När avtalet är påskrivet och du har fått API-nycklarna är det dags att antingen börja bygga ditt affärs- eller lönesystem eller integrera det system du redan har.

För att integrationen ska bli rätt bör du utgå från den tekniska beskrivningen i RAML-filen. Du bör också sätta dig in i tjänstebeskrivningen. Den beskriver verksamhetssammanhang, säkerhetsmekanismer och hur tjänsten är byggd.

Du hittar både RAML-fil och tjänstebeskrivning på respektive API:s sida på Utvecklarportalen.

- [Utvecklarportalen Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen)

- Se till att användaren av ditt system kan identifiera sig med e-legitimation eller organisationslegitimation

Användaren av ditt system kommer att behöva identifiera sig med antingen e-legitimation eller organisationslegitimation för att använda API:et.

### E-legitimation

Med den här tekniklösningen identifierar sig användaren av ditt system med en e-legitimation som är godkänd av Skatteverket. Du godkänner sedan att din programvara får tillgång till API:et för användarens räkning. Det finns flera leverantörer av e-legitimation att välja på.

- [Godkända e-legitimationer](https://www.skatteverket.se/privat/etjansterochblanketter/allaetjanster/omelegitimation.4.18e1b10334ebe8bc80004811.html)

### Organisationslegitimation

Med den här tekniklösningen identifieras ditt system med en organisationslegitimation. För närvarande accepterar Skatteverket endast organisationslegitimationer som är utfärdade av Expisoft.

- [Expisoft Länk till annan webbplats.](https://eid.expisoft.se/)

## Se till att användaren av ditt affärs- eller lönesystem har rätt behörigheter

Beroende på vilken tekniklösning du har valt så skiljer sig ombudsbehörigheterna åt.

För identifiering med e-legitimation krävs att användaren har antingen ombudsbehörigheten firmatecknare, deklarationsombud eller registreringsombud arbetsgivardeklaration.

För identifiering med organisationslegitimation krävs att användaren har ombudsbehörigheten Registreringsombud arbetsgivardeklaration. Du hittar all information om behörigheter på vår webbplats.

- [Ombudsbehörigheter](https://www.skatteverket.se/106.5a85666214dbad743ff145ea.html)