---
title: "Authorization Code Grant (ACG)"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/authorizationcodegrantacg.4.96cca41179bad4b1aa8f05.html"
author:
published:
created: 2026-07-09
description: "Authorization Code Grant är ett av de OAuth2-flöden som Skatteverket använder för att du ska få tillgång till våra API:er."
tags:
  - "clippings"
---
Authorization Code Grant är ett av de OAuth2-flöden som Skatteverket använder för att du ska få tillgång till våra API:er. Våra steg för steg-guider förklarar hur flödet fungerar tillsammans med API-nycklar och organisationslegitimation eller e-legitimation.

## Bra att veta innan du börjar

Din programvara måste kunna generera ett unikt värde för varje enskilt anrop till API:et, ett så kallat korrelations-id. Med hjälp av korrelations-id kan vi följa anropet i loggar och därmed felsöka lättare. Ett korrelations-id ska vara en max 36 tecken lång textsträng. Du skickar med värdet när du anropar API:et.

Programvaran måste också generera så kallade state-parametrar. State-parametern är ett slumpmässigt värde som skickas mellan programvaran och auktorisationsservern för att förhindra så kallade CSRF-attacker (Cross-Site Request Forgery).

## Så använder du flödet ACG

ACG-flödet används främst när den anropande programvaran är serverbaserad. I stora drag går det ut på att en organisation eller person autentiserar sig med hjälp av antingen organisationslegitimation eller e-legitimation mot Skatteverkets auktorisationsserver. Om det är en person som autentiserar sig med en e-legitimation behöver hen också lämna ett medgivande. När det är gjort får programvaran en auktorisationskod som den i sin tur växlar mot en access token (ett slags behörighetsbiljett) i auktorisationsservern. Med hjälp av access token får användaren slutligen åtkomst till API:et.

Kommunikationen mellan programvaran och API:et ska alltid vara krypterad med https och användaren kan använda en webbläsare, mobilapp eller vanlig klientprogramvara (som körs på till exempel Windows, OSx eller Linux) för att kommunicera med programvaran.

Varje partner-API är knutet till ett eller flera specifika säkerhetsflöden och autentiseringsmetoder, du kan alltså inte välja fritt. Inom ACG-flödet finns det två olika autentiseringsmetoder:

- Autentisering med client ID, client secret och organisationslegitimation
- Autentisering med client ID, client secret och e-legitimation

Vad som gäller för respektive API kan du läsa om här:

- [Säkerhet och API:er](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/safungerarvarasakerhetslosningar.4.96cca41179bad4b1aa8e51.html)
- [Auktorisationsflöden per API](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/auktorisationsflodenperapi.4.7da1d2e118be03f8e4f8246.html)

## För dig som använder client ID, client secret och organisationslegitimation

### Steg 1. Autentisera organisationen och begär en auktorisationskod

Vid anropet behöver du använda en organisationslegitimation från Expisoft för att autentisera organisationen.

Autentiseringen mot Skatteverket börjar genom att användaren av programvaran klickar på en länk som leder till ett GET-anrop mot authorize-ändpunkten hos Skatteverkets auktorisationsserver. Se även under rubriken "Så här ska anropet se ut". Auktorisationsservern kontrollerar organisationslegitimationen och omdirigerar svaret till den redirect-URI som angetts i anropet.

<table><thead><tr><th colspan="2"><p>Anropet ska innehålla:</p></th></tr></thead><tbody><tr><td><p>OAuth2 client ID</p></td><td><p>En del av dina API-nycklar.</p></td></tr><tr><td><p>State-parameter</p></td><td><p>State-parametern är ett slumpmässigt värde som skickas mellan programvaran och auktorisationsservern för att för att förhindra så kallade CSRF-attacker (Cross-Site Request Forgery).</p></td></tr><tr><td><p>Scope</p></td><td><p>Välj det scope som står i API-beskrivningen på Utvecklarportalen.</p></td></tr><tr><td><p>Redirect-URI</p></td><td><p>Välj den redirect-URI som du kopplade till API-nycklarna i samband med registreringen. Du måste alltid skriva redirect-URI:n på exakt samma sätt som du gjorde när du registrerade den hos oss.</p></td></tr></tbody></table>

#### Så ska anropet se ut

**Testmiljö:** GET https://orgoauth2.test.skatteverket.se/oauth2/v1/org/authorize?client\_id=\<OAUTH2 CLIENT ID>&response\_type=code&state=\<STATE-PARAMETER>&redirect\_uri=\<REDIRECT-URI>&scope=\<API SCOPE>  
**Produktionsmiljö:** GET https://orgoauth2.skatteverket.se/oauth2/v1/org/authorize?client\_id=\<OAUTH2 CLIENT ID>&response\_type=code&state=\<STATE-PARAMETER>&redirect\_uri=\<REDIRECT-URI>&scope=\<API SCOPE>

#### Testa att hämta auktorisationskod med curl

Du kan hämta en auktorisationskod med ett curl-anrop. På så sätt kan du kontrollera att anslutningen till API:et fungerar. Ersätt bara orden inom vinkelparenteserna med dina uppgifter:

\# curl -c "cookies.txt" -L --request GET --cert <SÖKVÄG-TILL-ORGCERT>:<PINKOD-FÖR-ORGCERT> --cert-type P12 "<ÄNDPUNKT-FÖR-AUTHORIZE-ANROP>?client\_id=\<OAUTH2-CLIENT-ID>&response\_type=code&state=1234567&redirect\_uri=\<DIN-REGISTRERADE-REDIRECT-URI>" -v

Svaret i exemplet ovan kommer att omdirigeras till den redirect-URI som du har angett, med auktorisationskoden som värde på query-parametern "code". Det är detta värde som plockas ut och används i nästa steg. För att få ett resultat med en tydligare utskrift kan du lägga till "2>&1 | grep "code=" sist i anropet ovan.

Förklaring av vinkelparenteserna:

- SÖKVÄG-TILL-ORGCERT: Sökväg till giltig organisationslegitimation
- PINKOD-FÖR-ORGCERT: Pinkoden till organisationslegitimationen.
- ÄNDPUNKT-FÖR-AUTHORIZE-ANROP: Adress till ändpunkt för authorize (anpassa för anrop till test- eller produktionsmiljö).
- DIN-REGISTRERADE-REDIRECT-URI: Den redirect som är registrerad som kopplad till API-nycklarna

Här under ser du hur anropet kan se ut i testmiljö. Observera att värden på parametrar för pinkod, client id och client secret är ofullständiga i exemplet.

\# curl -c "cookies.txt" -L --request GET --cert./bolagA/6489...f69.p12:8433...335 --cert-type P12 "https://orgoauth2.test.skatteverket.se/oauth2/v1/org/authorize?client\_id=6dba...75a&response\_type=code&state=1234567&redirect\_uri=https://localhost/test" -v 2>&1 | grep "code="

#### Om du använder curl på Windowsdator

Observera! Den version av curl som följer med Windows kan ge felmeddelandet "schannel: AcquireCredentialsHandle failed: SEC\_E\_NO\_CREDENTIALS (0x8009030E) - No credentials are available in the security package". Det enklaste sättet att lösa problemet är att ladda ner en standardversion av curl.

- [Curl for Windows Länk till annan webbplats.](https://curl.se/windows/)

### Steg 2. Ta emot en auktorisationskod

När autentiseringen är klar omdirigeras klienten till URI:n du angett i anropet och lägger samtidigt till en auktorisationskod som query-parameter tillsammans med state-parametern. Din programvara tar emot anropet på samma URI och kontrollerar att state-parametern är identisk med den som skickades med i anropet till auktorisationsservern.

Tänk på att en auktorisationskod bara är giltig i fem minuter.

**Exempel på omdirigering**

\<REDIRECT-URI>:?code=\<AUKTORISATIONSKOD>&state=\<STATE-PARAMETER>

Här är ett verkligt exempel på omdirigeringen:

https://localhost/test?code=9096c9acb71a97359deb1dc201b53907db2de1f31d67156eae3c1ff68c150507&state=1234567

### Steg 3. Använd din auktorisationskod för att begära en access token

I nästa steg anropar programvaran auktorisationsservern (ändpunkten Token endpoint) med auktorisationskoden du just fått.

<table><thead><tr><th colspan="2"><p>Anropet ska innehålla:</p></th></tr></thead><tbody><tr><td><p>Auktorisationskod</p></td><td><p>Den du precis fått, används för att få en access token.</p></td></tr><tr><td><p>OAuth2 client ID</p></td><td><p>En del av dina API-nycklar. Den är märkt med OAuth2.</p></td></tr><tr><td><p>OAuth2 client secret</p></td><td><p>En del av dina API-nycklar. Den är märkt med OAuth2.</p></td></tr><tr><td><p>Redirect-URI</p></td><td><p>Välj den redirect-URI som du kopplade till API-nycklarna i samband med registreringen. Du måste alltid skriva redirect-URI:n på exakt samma sätt som du gjorde när du registrerade den hos oss.</p></td></tr></tbody></table>

#### Så ska anropet se ut

**Ändpunkt för access token i testmiljö:** POST https://orgoauth2.test.skatteverket.se/oauth2/v1/org/token  
**Ändpunkt för access token i testmiljö:** POST https://orgoauth2.skatteverket.se/oauth2/v1/org/token  
**HTTP-header:** Content-Type: application/x-www-form-urlencoded;charset=UTF-8  
**Body:** grant\_type=authorization\_code&client\_id=\<OAUTH2 CLIENT ID>&client\_secret=\<OAUTH2 CLIENT SECRET>&redirect\_uri=\<REDIRECT-URI>&code=\<AUKTORISATIONSKOD>

TIPS! Du kan använda din access token till flera tjänster genom att inkludera flera scope i bodyn.

#### Testa att hämta access token med curl

Du kan hämta en access token med ett curl-anrop. På så sätt kan du kontrollera att anslutningen till API:et fungerar. Ersätt orden inom vinkelparenteserna med dina uppgifter, samt den authorization code som hämtats i anropet ovan.

\# curl --request POST --cert <SÖKVÄG-TILL-ORGCERT>:<PINKOD-FÖR-ORGCERT> --cert-type P12 <ÄNDPUNKT-FÖR-ACCESS-TOKEN> -H "Content-Type: application/x-www-form-urlencoded;charset=UTF-8" -d "grant\_type=authorization\_code&scope=foo&client\_id=\<OAUTH2-CLIENT-ID>&client\_secret=\<OAUTH2-CLIENT-SECRET>&code=<AUTHORIZATION-CODE-FRÅN-FÖREGÅENDE-ANROP>&state=1234567&redirect\_uri=\<DIN-REGISTRERADE-REDIRECT-URI>"

Förklaring av vinkelparenteserna:

- SÖKVÄG-TILL-ORGCERT: Sökväg till giltig organisationslegitimation
- PINKOD-FÖR-ORGCERT: Pinkoden till organisationslegitimationen.
- ÄNDPUNKT-FÖR-ACCESS-TOKEN: Adress till ändpunkt för att hämta token (anpassa för anrop till test- eller produktionsmiljö).
- DIN-REGISTRERADE-REDIRECT-URI: Den redirect som är registrerad som kopplad till API-nycklarna

Här under ser du hur anropet kan se ut i testmiljö. Observera att värden på parametrar för pinkod, client id och client secret är ofullständiga i exemplet.

\# curl --request POST --cert./bolagA/6489...f69.p12:8433...335 --cert-type P12 https://orgoauth2.test.skatteverket.se/oauth2/v1/org/token -H "Content-Type: application/x-www-form-urlencoded;charset=UTF-8" -d "grant\_type=authorization\_code&scope=foo&client\_id=6dba...75a&client\_secret=6c9e...75a&code=6bfc...980&state=1234567&redirect\_uri=https://localhost/test"

### Steg 4. Ta emot en access token

Efter att auktorisationsservern stämt av uppgifterna du skickade i anropet får du ett svar i form av en JSON-body. Bodyn innehåller din access token. Svaret innehåller också det eller de scope du har begärt. Det är bra om du verifierar att det stämmer med anropet du skickade.

**Exempelsvar**

200 OK

Content-Type: application/json; charset=UTF-8  
{  
"access\_token":\<ACCESS TOKEN>,  
"expires\_in":3600,  
"token\_type":"Bearer",  
"scope":"\<API SCOPE>"  
}

Här är ett exempel med riktiga värden:

{  
"access\_token": "79ab042fc076a755b58cf649458efffad2868caeb2f978a3d1ec19b2405295a6",  
"expires\_in":3600,  
"token\_type":"Bearer",  
"scope":"foo"  
}

Du kan bara använda en access token under den tid som anges i svaret. Det är angett i sekunder på raden "expires in" i exemplet ovan. När tiden har gått ut måste du hämta en ny access token. Det är viktigt att du utnyttjar hela giltighetstiden och inte hämtar nya access tokens för varje anrop.

VIKTIGT! Tänk på att din access token är en värdehandling.

### Steg 5. Anropa API:et

Nu när du har access token kan du anropa API:et. Du använder den som värde i en HTTP-header som du skickar med i anropet. API:et kontrollerar vid varje anrop att uppgifterna i access token stämmer.

<table><thead><tr><th colspan="2"><p>Anropet ska innehålla:</p></th></tr></thead><tbody><tr><td><p>Access token</p></td><td><p>Den du precis fått. Tänk på att du bara kan använda samma access token under den tid som anges i svaret.</p></td></tr><tr><td><p>APIgw client ID</p></td><td><p>Den andra delen av dina API-nycklar, som är märkt med APIgw.</p></td></tr><tr><td><p>APIgw client secret</p></td><td><p>Den andra delen av dina API-nycklar, som är märkt med APIgw.</p></td></tr><tr><td><p>Korrelations-id</p></td><td><p>Din programvara måste kunna generera ett unikt värde för varje enskilt anrop till API:et, ett så kallat korrelations-id. Ett korrelations-id ska vara en max 36 tecken lång textsträng.</p></td></tr></tbody></table>

#### Så ska dina HTTP-headers se ut

Authorization: Bearer \<Access token>  
Client\_Id: \<APIgw Client ID>  
Client\_Secret: \<APIgw Client secret>  
skv\_client\_correlation\_id: \<Korrelations-id>

Här ser du bara de parametrar som är gemensamma för alla Skatteverkets API:er. För specifika API:er kan det krävas fler parametrar. Du hittar dem i tjänstebeskrivningen för respektive API. I tjänstebeskrivningen kan du också kontrollera parametern för korrelations-id, eftersom den finns i flera versioner.

VIKTIGT! Skicka endast med de header-parametrar som är angivna för respektive tjänst, annars kan anropet blockeras.

Här är ett exempel på hur HTTP-headers för anropet kan se ut. Observera att värden på parametrar för client id och client secret är ofullständiga i exemplet.

...  
authorization: Bearer 79ab042fc076a755b58cf649458efffad2868caeb2f978a3d1ec19b2405295a6  
client\_id: b175a...g14c  
client\_secret: c0122...bcaed  
skv\_client\_correlation\_id: 5d93e201-ba43-40ff-ae52-c95d9f21d4e1  
...

## För dig som använder client ID, client secret och e-legitimation

### Steg 1. Autentisera användaren och begär en auktorisationskod

Autentiseringen mot Skatteverket börjar genom att användaren av programvaran klickar på en länk som leder till ett GET-anrop mot authorize-ändpunkten hos Skatteverkets auktorisationsserver. Se även under rubriken "Så här ska anropet se ut".

<table><thead><tr><th colspan="2"><p>Anropet ska innehålla:</p></th></tr></thead><tbody><tr><td><p>OAuth2 client ID</p></td><td><p>En del av dina API-nycklar.</p></td></tr><tr><td><p>State-parameter</p></td><td><p>State-parametern är ett slumpmässigt värde som skickas mellan programvaran och auktorisationsservern för att för att förhindra så kallade CSRF-attacker (Cross-Site Request Forgery).</p></td></tr><tr><td><p>Scope</p></td><td><p>Välj det scope som står i API-beskrivningen på Utvecklarportalen.</p></td></tr><tr><td><p>Redirect-URI</p></td><td><p>Välj den redirect-URI som du kopplade till API-nycklarna i samband med registreringen. Du måste alltid skriva redirect-URI:n på exakt samma sätt som du gjorde när du registrerade den hos oss.</p></td></tr></tbody></table>

#### Så här ska anropet se ut

**Testmiljö:** GET https://peroauth2.test.skatteverket.se/oauth2/v1/per/authorize?client\_id=\<OAUTH2 CLIENT ID>&response\_type=code&state=\<STATE-PARAMETER>&redirect\_uri=\<REDIRECT-URI>&scope=\<API SCOPE>  
**Produktionsmiljö:** GET https://peroauth2.skatteverket.se/oauth2/v1/per/authorize?client\_id=\<OAUTH2 CLIENT ID>&response\_type=code&state=\<STATE-PARAMETER>&redirect\_uri=<redirect\_uri>&scope=\<API SCOPE>

Auktorisationsservern skickar användaren vidare till Skatteverkets inloggningssidor där hen autentiserar sig med en godkänd e-legitimation. Efter inloggning dirigeras användaren till en sida där hen får godkänna att programvaran anropar API:et för användarens räkning.

Observera att det inte går att testa detta flöde med hjälp av curl.

### Steg 2. Ta emot auktorisationskoden

När autentiseringen är klar omdirigeras klienten till URI:n du angett i anropet och lägger samtidigt till en auktorisationskod som query-parameter tillsammans med state-parametern. Din programvara tar emot anropet på samma URI och kontrollerar att state-parametern är identisk med den som skickades med i anropet till auktorisationsservern.

Tänk på att en auktorisationskod bara är giltig i fem minuter.

**Exempelsvar**

Adressen som klienten omdirigerar till har format enligt nedan.

\<REDIRECT-URI>:?code=\<AUKTORISATIONSKOD>&state=\<STATE-PARAMETER>

Ett verkligt exempel kan se ut så här:

https://localhost/my-redirect-uri?code=025bfd37f99c7caca886a12c17f87d33598d2ac7a3f2b031d16c6314b79e3cac&state=12345678901234567890123456789012345678901234567890123456789012345678901234567890YY

### Steg 3. Använd din auktorisationskod för att begära en access token

I nästa steg anropar programvaran auktorisationsservern (ändpunkten Token endpoint) med auktorisationskoden du just fått.

<table><thead><tr><th colspan="2"><p>Anropet ska innehålla:</p></th></tr></thead><tbody><tr><td><p>Auktorisationskod</p></td><td><p>Den du precis fått, används för att få en access token.</p></td></tr><tr><td><p>OAuth2 client ID</p></td><td><p>En del av dina API-nycklar. Den är märkt med OAuth2.</p></td></tr><tr><td><p>OAuth2 client secret</p></td><td><p>En del av dina API-nycklar. Den är märkt med OAuth2.</p></td></tr><tr><td><p>Redirect-URI</p></td><td><p>Välj den redirect-URI som du kopplade till API-nycklarna i samband med registreringen. Du måste alltid skriva redirect-URI:n på exakt samma sätt som du gjorde när du registrerade den hos oss.</p></td></tr></tbody></table>

#### Så ska anropet se ut

**Testmiljö:** POST https://peroauth2.test.skatteverket.se/oauth2/v1/per/token  
**Produktionsmiljö:** POST https://peroauth2.skatteverket.se/oauth2/v1/per/token  
**HTTP-header:** Content-Type: application/x-www-form-urlencoded;charset=UTF-8  
**Body:** grant\_type=authorization\_code&client\_id=\<OAUTH2 CLIENT ID>&client\_secret=\<OAUTH2 CLIENT SECRET>&redirect\_uri=\<REDIRECT-URI>&code=\<AUKTORISATIONSKOD>

TIPS! Du kan använda din access token till flera tjänster genom att inkludera flera scope i bodyn.

### Steg 4. Ta emot en access token

Efter att auktorisationsservern stämt av uppgifterna du skickade i anropet får du ett svar i form av en JSON-body. Bodyn innehåller din access token. Svaret innehåller också det eller de scope du har begärt. Det är bra om du verifierar att det stämmer med anropet du skickade.

**Exempelsvar**

200 OK

Content-Type: application/json; charset=UTF-8  
{  
"access\_token":"\<ACCESS TOKEN>",  
"expires\_in":3600,  
"token\_type":"Bearer",  
"scope":"\<API SCOPE>",  
"refresh\_token":"\<REFRESH TOKEN>"  
}

Här är ett exempel med riktiga värden:

{  
"access\_token": "96381c2d9d66464b427897347bc3aeaa8cd560246800dc60e673e417a0b43b18",  
"expires\_in": 3600,  
"token\_type": "Bearer",  
"scope": "foo",  
"refresh\_token": "08168e505b80fc7454f4ff2a1c74232cf7ff1d012b66c89eb529e6d96c9ca197"  
}

Tänk på att du bara kan använda en access token under den tid som anges i svaret (expires in). Det är viktigt att du utnyttjar den här tiden och inte hämtar nya access tokens för varje anrop. När giltighetstiden gått ut kan du hämta en ny access token med hjälp av en refresh token.

Fördelen med refresh token är att slutanvändaren inte behöver legitimera sig igen när en ny access token hämtas. Du använder den genom att anropa auktorisationsservern och lägga till refresh token i anropet. Auktorisationsservern svarar då med en ny access token. Refresh token har en giltighetstid på 65 minuter. Det går att hämta maximalt 10 refresh tokens per användare under en pågående session

VIKTIGT! Tänk på att din access token är en värdehandling.

### Steg 5. Anropa API:et

Nu när du har access token kan du anropa API:et. Du använder den som värde i en HTTP-header som du skickar med i anropet. API:et kontrollerar vid varje anrop att uppgifterna i access token stämmer.

<table><thead><tr><th colspan="2"><p>Anropet ska innehålla:</p></th></tr></thead><tbody><tr><td><p>Access token</p></td><td><p>Den du precis fått. Tänk på att du bara kan använda samma access token under den tid som anges i svaret.</p></td></tr><tr><td><p>APIgw client ID</p></td><td><p>Den andra delen av dina API-nycklar, som är märkt med APIgw.</p></td></tr><tr><td><p>APIgw client secret</p></td><td><p>Den andra delen av dina API-nycklar, som är märkt med APIgw.</p></td></tr><tr><td><p>Korrelations-id</p></td><td><p>Din programvara måste kunna generera ett unikt värde för varje enskilt anrop till API:et, ett så kallat korrelations-id. Ett korrelations-id ska vara en max 36 tecken lång textsträng.</p></td></tr></tbody></table>

#### Så ska dina HTTP-headers se ut

Authorization: Bearer \<Access token>  
Client\_Id: \<APIgw Client ID>  
Client\_Secret: \<APIgw Client secret>  
skv\_client\_correlation\_id: \<Korrelations-id>

Här ser du bara de parametrar som är gemensamma för alla Skatteverkets API:er. För specifika API:er kan det krävas fler parametrar. Du hittar dem i tjänstebeskrivningen för respektive API. I tjänstebeskrivningen kan du också kontrollera parametern för korrelations-id, eftersom den finns i flera versioner.

VIKTIGT! Skicka endast med de header-parametrar som är angivna för respektive tjänst, annars kan anropet blockeras.

Här är ett exempel på hur HTTP-headers för anropet kan se ut. Observera att värden på parametrar för client id och client secret är ofullständiga i exemplet.

...  
authorization: Bearer 79ab042fc076a755b58cf649458efffad2868caeb2f978a3d1ec19b2405295a6  
client\_id: b175a...g14c  
client\_secret: c0122...bcaed  
skv\_client\_correlation\_id: 5d93e201-ba43-40ff-ae52-c95d9f21d4e1  
...

## Vi hjälper dig gärna vid frågor

Våra kunniga utvecklare på supporten hjälper dig gärna om du har frågor. Du kan även höra av dig till oss om du vill ha de gamla säkerhetsdokumenten som tidigare hittades på Utvecklarportalen i pdf-format.

- [Ställ en fråga](https://www.skatteverket.se/omoss/digitalasamarbeten/anslutningochsupportforvaraapierochoppnadata/stallenfragaomoppnadataelleroppnadataapier.4.7c708f0e16bed42cd055c73.html)

## Relaterat innehåll

- [Client Credentials Grant (CCG)](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/clientcredentialsgrantccg.4.96cca41179bad4b1aa8ec8.html)
- [Organisationslegitimation och ombudsrollen](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/organisationslegitimationochombudsrollen.4.7da1d2e118be03f8e4f8d63.html)
- [Så fungerar access tokens](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/safungeraraccesstokens.4.7da1d2e118be03f8e4f94e9.html)
- [Använd testpersonnummer med Bank-id](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/anvandtestpersonnummermedbankid.4.17b07b1e194a69bf276866.html)