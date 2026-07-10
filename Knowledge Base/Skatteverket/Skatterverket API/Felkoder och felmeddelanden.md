---
title: "Felkoder och felmeddelanden"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/felkoderochfelmeddelanden.4.7da1d2e118be03f8e4fa2fa.html"
author:
published:
created: 2026-07-09
description: "Det finns några vanliga felkoder och felmeddelanden som uppstår när du antingen anropat ett API eller försökt hämta en access token och det av någon anledning inte lyckats. Vi listar och förklarar vad de olika svaren betyder, vad de beror på och vad du kan göra för att lösa problemet."
tags:
  - "clippings"
---
Det finns några vanliga felkoder och felmeddelanden som uppstår när du antingen anropat ett API eller försökt hämta en access token och det av någon anledning inte lyckats. Vi listar och förklarar vad de olika felkoderna betyder, vad de beror på och vad du kan göra för att lösa problemet.

## Gå direkt till den felkod och det eller de felmeddelanden du har fått:

## Felkoder som returneras när du försöker anropa ett API

### Felkod: (403 Forbidden) Invalid\_scope: The required scope \[uppgett scope i anropet\] has been requested for that access token

Programvaran som anropar API:et har uppgett ett access token som saknar det scope som krävs för det aktuella API:et. Kontrollera att svaret från auktorisationsservern innehåller exakt det scope som krävs. Du hittar scopet i den tjänstebeskrivning som hör till varje enskilt API.

### Felkod: (403 Forbidden) Invalid\_client: Wrong client\_id or client\_secret

Programvaran som anropar API:et har uppgett ett felaktigt APIgw client ID eller APIgw client secret. Kontrollera att API-nycklarna i anropet är samma som det du fått från Skatteverket när du ansökte om tillgång till API:et.

### Felkod: (401 Unauthorized) Invalid token

Programvaran som anropar API:et har uppgett en ogiltig/felaktig access token. Kontrollera att access token är samma som den som hämtades.

## Felkod (400 Bad Request) som returneras när du försöker hämta access token

### Felmeddelande: Access\_denied: Admin policy denied access

Detta felmeddelande innebär att något av följande hänt:

- Programvaran som hämtar access token uppger inte organisationslegitimation vid anropet till auktorisationsservern.
- Organisationslegitimationen är spärrad.
- Organisationslegitimationen har passerat sin sista giltighetsdag.
- Organisationslegitimationen har inte börjat gälla än.

### Felmeddelande: Invalid\_client: Invalid client\_id xyz...

Programvaran som hämtar access token har uppgett ett Oauth2 client ID som inte är registrerat för den aktuella auktorisationsservern. Kontrollera att Oauth2 client ID i anropet är samma som det du fått från Skatteverket när du ansökte om tillgång till API:et.

### Felmeddelande: Unauthorized\_client: Client app (id = xyz...) access is not allowed through this endpoint

Programvaran som hämtar access token har uppgett ett Oauth2 client ID som är korrekt men är inte registrerat för det aktuella säkerhetsflödet. Kontrollera att Oauth2 client ID i anropet är samma som det du fått från Skatteverket när du ansökte om tillgång till API:et.

### Felmeddelande: Invalid\_client: Client authentication (client\_secret) failed

Programvaran som hämtar token har uppgett ett Oauth2 client secret som inte stämmer med Oauth2 client ID. Kontrollera att API-nycklarna i anropet stämmer med de du fått från Skatteverket när du ansökte om tillgång till API:et.

### Felmeddelande: Invalid\_request: The client app does not support ROPC grant

Svaret betyder att ett fel uppstått när Skatteverket registrerat din applikation. Vi vill gärna att du gör en felanmälan till oss om du får detta felsvar. Använd vårt formulär för att felanmäla API:er som kräver avtal eller överenskommelse för att få använda:

- [Felanmäl API:er Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/felanmal-api)

### Felmeddelande: Invalid\_request: Redirect-URI (https://server/fel) does not match with client app configuration

Programvaran som hämtar access token har uppgett en redirect-URI som inte är registrerat för den programvaran. Kontrollera att redirect-URI:n du uppgett stämmer med någon av de redirect-URI:er som du har uppgav i ansökan.

### Felmeddelande: Invalid\_request: Required parameter (response\_type) is missing

Programvaran som hämtar access token har inte uppgett query-parametern response\_type i anropet. Lägg till response\_type som query-parameter och försök igen.

### Felmeddelande: Invalid\_request: Unsupported value for response\_type (felresponsetype)

Programvaran som hämtar access token har uppgett fel response\_type. Ändra till response\_type=code i anropet och försök igen.

### Felmeddelande: Invalid\_client: The client app does not support implicit grant

Programvaran som hämtar access token har uppgett response\_type=token, vilket inte stöds av Skatteverket. Ändra till response\_type=code och försök igen.

### Felmeddelande: Invalid\_request: This user has reached configured access token limit

Programvaran som försöker hämta access tokens har nått maxgränsen för hur många access tokens som kan lämnas ut för denna auktorisationsserver. Det är viktigt att använda access token under hela dess giltighetstid. Giltighetstiden ser du i svaret när du hämtat din access token. Det är angett i sekunder på raden "expires in".