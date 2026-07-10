---
title: "Vanliga begrepp"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/vanligabegrepp.4.96cca41179bad4b1aac4eb.html"
author:
published:
created: 2026-07-09
description: "Vanligt förekommande ord och begrepp som rör API:er och öppna data."
tags:
  - "clippings"
---
På den här sidan har vi samlat vanligt förekommande ord och begrepp som du kan stöta på när du använder våra öppna data eller API:er.

## A

**Access token**

En access token kan liknas med att ha en behörighetsbiljett till auktorisationsservern. Den krävs för att användaren av din programvara på ett säkert och verifierat sätt ska få åtkomst till API:et. Access token kan hämtas på olika vis, beroende på vilken säkerhetslösning som används för API:et. Utförligare beskrivningar av vad access tokens är, samt hur de hämtas beskrivs på sidan Så fungerar access tokens.

- [Så fungerar access tokens](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/safungeraraccesstokens.4.7da1d2e118be03f8e4f94e9.html)

**API  
**Förkortningen API står för Application Programming Interface. Det är ett numera standardiserat sätt att överföra information på.

- [Vad är ett API](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/vadarettapi.4.96cca41179bad4b1aaa4b8.html)
- **API-konsol**
- API-konsolen är ett verktyg där du kan få mer information om ett enskilt API. För enkla testtjänster kan du göra testanrop via API-konsolen. För kompletta testtjänster och driftsatta tjänster går det tyvärr inte att göra testanrop. Du kan däremot se dokumentation om
- vilka URL:er du ska använda för att anropa API:et
- vilka parametrar som behövs.

Du kommer till API-konsolen genom att klicka på knappen "Utforska API-definitionen" på respektive API:s sida på Utvecklarportalen.

- [API-konsolen - så fungerar den med Skatteverkets API:er](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/apikonsolensafungerardenmedskatteverketsapier.4.6e8a1495181dad540845fb1.html)
- **API-nycklar**

Unik identifikation och lösenord för en specifik programvara som används för autentisering mot Skatteverkets auktorisationsserver. Kallas ofta Client ID och Client Secret.

- [Så fungerar API-nycklar](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/safungerarapinycklar.4.96cca41179bad4b1aa9176.html)

**Applikations-id/applikationsnamn**

När vi registrerar din ansökan om tillgång till något av våra API:er skapar vi ett unikt applikations-id för din applikation. De API-nycklar du får av oss kommer vara knutna till ditt applikations-id. Om du vill kan du återanvända API-nycklarna för fler API:er. Då behöver du ange ditt befintliga applikations-id när du ansöker om tillgång till API:et.

**Auktorisationsserver**  
Ett system hos Skatteverket för autentisering och auktorisation av API-användare. Består av ändpunkterna Authorization Endpoint och Token Endpoint som används inom OAuth 2.

## D

**Driftmeddelandetyper: Driftinformation, Driftstörning och Uppdatering**

Skatteverket använder sig av tre olika driftmeddelandetyper. Här är en kort förklaring av de olika typerna:

- Driftinformation används för exempelvis planerat underhåll av ett API
- Driftstörning innebär exempelvis att ett API ligger nere
- Uppdatering kan innebära till exempel ny säkerhetsinformation för ett API.

**Driftsatt tjänst**

Skatteverket använder begreppet driftsatt tjänst för alla API:er som finns tillgängliga i vår produktionsmiljö.

## E

**E-legitimation**

En elektronisk id-handling, till exempel Bank-ID. På Skatteverket använder vi begreppet e-legitimation för privatpersoner och begreppet organisationslegitimation för elektroniska ID-handlingar för andra juridiska personer.

## K

**Komplett testtjänst**

Den kompletta testtjänsten (sandbox) innehåller dynamiska data och levererar olika svar beroende på vilka datavärden du anger i anropen. Du kan använda den för att testa API:ets innehåll och uppbyggnad.

**Korrelations-id**

Ett korrelations-id genereras av din programvara och är ett unikt värde för varje enskilt anrop till API:et. Ett korrelations-id ska vara en max 36 tecken lång textsträng.

## O

**OAuth2**

OAuth2 står för "Open Authorization" och är ett öppet säkerhetsramverk som kan användas för behörighet och åtkomst mellan olika komponenter. Varje partner-API som Skatteverket tillhandahåller är knutet till ett eller flera specifika OAuth2-flöden och autentiseringsmetoder.

- [Så fungerar våra säkerhetslösningar](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/safungerarvarasakerhetslosningar.4.96cca41179bad4b1aa8e51.html)

**Organisationslegitimation**

Organisationslegitimation eller organisationscertifikat är en elektronisk ID-handling för företag eller andra former av juridiska personer. Den används för autentisering tillsammans med API-nycklar.

- [Organisationslegitimation och ombudsrollen](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/organisationslegitimationochombudsrollen.4.7da1d2e118be03f8e4f8d63.html)

## P

**Partner-API  
**API:er som kan användas av exempelvis programvaruföretag, myndigheter eller organisationer som uppfyller de avtal, överenskommelser och villkor som finns kopplat till API:et. Partner-API:erna finns under fliken API:er på Utvecklarportalen.

## R

**RAML-fil**

RAML står för RESTful API Modeling Language och är ett YAML-baserat språk som används för att beskriva statiska API:er. I den tekniska beskrivningen i RAML-filen hittar du

- adresserna som du kan anropa API:et och dess operationer på
- vilka svar API:et skickar
- information om hur parametrar och data som skickas till API:et behöver se ut.

**Redirect-URI**

Redirect-URI kan översättas till omdirigeringsadress på svenska. Redirect-URI används i säkerhetsflödet Authorization Code Grant. Du ska fylla i en eller flera sådana adresser redan när du ansöker om API:er som använder detta säkerhetsflöde. När du gör anrop mot auktorisationsservern skickar du med en av de redirect-URI:er som du har fyllt i i ansökan. När din programvara har autentiserats jämförs denna adress med den eller dem som du fyllt i i ansökan. Om de stämmer överens kommer användaren skickas till redirect-URI:en. På detta sätt kan vi skydda era användare från att omdirigeras till andra främmande adresser efter autentiseringen.

**Riktat API  
**API:er som är skräddarsydda för specifika behov. De är ofta beställda av andra myndigheter eftersom informationen som skickas via API:et kräver särskilda rättigheter för att få ta del av.

## S

**Scope**

Varje API har ett scope. De API-nycklar du får av oss kan du använda för mer än ett API, förutsatt att de ska användas för samma applikation. I så fall kan Skatteverket koppla ett nytt scope till din användare.

## T

**Tjänstebeskrivning**

Varje API har en tjänstebeskrivning. Tjänstebeskrivningen innehåller teknisk information, samt beskriver verksamhetssammanhang och hur tjänsten är byggd. Du hittar tjänstebeskrivningen under respektive API på vår Utvecklarportal.

## Ö

**Öppna data  
**Öppna data är digitaliserad, offentlig information som vem som helst kan ta del av och använda till valfritt ändamål.

- [Vad är öppna data?](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraoppnadata/vadaroppnadata.4.96cca41179bad4b1aa68ec.html)

**Öppna data-API  
**API:er som är fria att använda precis hur du vill. De har ingen utpekad målgrupp och kan därför användas av myndigheter likväl som privatpersoner och företag. Du behöver inte skriva på något avtal eller betala för att använda dem. Du hittar dem på vår Utvecklarportal under filtret Öppna data-API:er.