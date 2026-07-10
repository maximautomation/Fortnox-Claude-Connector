---
title: "Så fungerar API-nycklar"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/safungerarapinycklar.4.96cca41179bad4b1aa9176.html"
author:
published:
created: 2026-07-09
description: "API-nycklarna, eller client ID och client secret som de ofta kallas, fungerar som en unik identifikation och ett lösenord för just din programvara."
tags:
  - "clippings"
---
Du behöver API-nycklar för att kunna använda Skatteverkets partner-API:er. Med hjälp av nycklarna kan vi sedan identifiera din programvara vilket behövs när du hämtar en access token från vår auktorisationsserver. Du får oftast två uppsättningar nycklar.

## Vad är egentligen API-nycklar?

API-nycklarna, eller Client ID och Client secret som de ofta kallas, fungerar som en unik identifikation och ett lösenord för just din programvara. Du får dem oftast i två uppsättningar och du använder dem i olika delar av autentiseringsflödet:

**OAuth Client ID och Client secret**  
Nycklarna används i den första delen av autentiseringsflödet, mot auktorisationsservern.

**APIgw Client ID och Client secret  
**Nycklarna används i ett senare skede av autentiseringsflödet då du ska anropa API:et via Skatteverkets API-gateway.

API-nycklarna är en del av en textfil som Skatteverket av säkerhetsskäl skickar ut i två delar via två separata kommunikationskanaler. Textfilen innehåller bland annat två uppsättningar API-nycklar och information om scope. Scopet talar om vilket eller vilka API:er dina nycklar är kopplade till.

## Begär tillgång till API:et först och få nycklar sedan

Du får API-nycklar genom att begära tillgång till ett API. Om det är en komplett testtjänst du begär tillgång till får du oftast API-nycklarna inom några dagar, men för API:er i produktionsmiljö behöver du ingå avtal med Skatteverket först. Det tar oftast några veckor.

## Återanvända API-nycklar eller få nya

Det går oftast bra att använda samma API-nycklar för flera API:er. När du begär tillgång till ett nytt API meddelar du oss att du redan använder ett annat API och därför vill återanvända befintliga nycklar. Använd fältet "vill du återanvända API-nycklar".

Det finns dock två situationer då du behöver helt nya API-nycklar.

1. **Du använder en testmiljö och vill gå över till att använda produktionsmiljön.** Det går nämligen inte att använda API-nycklar avsedda för testmiljöer i produktionsmiljö (och vice versa).
2. **Du använder säkerhetslösningen Client Credentials Grant tillsammans med organisationslegitimation.** Just det här flödet kräver att du kopplar ihop ditt OAuth Client ID med organisationslegitimationen du vill använda. När kopplingen är gjord ersätter organisationslegitimationen din Oauth Client Secret, som alltså inte kan användas.

När du använder en testmiljö och vill gå över till att använda produktionsmiljön måste du alltid skaffa nya nycklar. Det går nämligen inte att använda API-nycklar avsedda för testmiljöer i produktionsmiljö (och vice versa).

## Lär dig mer

- [Vad är ett API](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/vadarettapi.4.96cca41179bad4b1aaa4b8.html)
- [Vad är öppna data?](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraoppnadata/vadaroppnadata.4.96cca41179bad4b1aa68ec.html)