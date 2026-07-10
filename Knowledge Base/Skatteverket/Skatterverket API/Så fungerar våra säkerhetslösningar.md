---
title: "Så fungerar våra säkerhetslösningar"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/safungerarvarasakerhetslosningar.4.96cca41179bad4b1aa8e51.html"
author:
published:
created: 2026-07-09
description: "För att få tillgång till Skatteverkets API:er behöver du ansluta enligt våra etablerade säkerhetslösningar."
tags:
  - "clippings"
---
För att få tillgång till de flesta av Skatteverkets partner-API:er behöver du autentisera programvaran enligt säkerhetsramverket OAuth 2. I vissa fall ska din slutanvändare också autentiseras med ett organisationslegitimation eller en godkänd e-legitimation.

Varje partner-API är knutet till ett eller flera specifika Oauth2-flöden och autentiseringsmetoder. Skatteverket använder flödena Client Credentials Grant (CCG) och Authorization Code Grant (ACG). Vilken lösning som gäller för respektive API hittar du i beskrivningen av API:et på Utvecklarportalen eller på sidan:

- [Auktorisationsflöden per API](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/auktorisationsflodenperapi.4.7da1d2e118be03f8e4f8246.html)

### Rekommendationer för dig som ska välja säkerhetslösning

- Behöver du en lösning med organisationslegitimation rekommenderar vi i första hand ett av CCG-flödena. De erbjuder samma säkerhet som ACG men är enklare att implementera. ACG tillsammans med organisationslegitimation är komplext och rekommenderas därför främst för erfarna utvecklare.
- Behöver du en lösning med e-legitimation är ACG det enda alternativet.

### För dig som vill använda CCG med utpekad organisationslegitimation

Notera att autentiseringsuppgifterna för flödet Client Credentials Grant med utpekad organisationslegitimation inte går att återanvända för något annat säkerhetsflöde. Vill du byta till eller från det flödet behöver du kontakta oss. Det kan du göra via formuläret Uppdatera anslutning till API. I formuläret fyller du i vilken organisationslegitimation du vill använda. Det OAuth2 client ID du får av oss kommer vara knutet till just den organisationslegitimationen.

Läs mer om de olika OAuth2-flödena och hur du implementerar dem:

- [Client Credential Grant (CCG)](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/clientcredentialsgrantccg.4.96cca41179bad4b1aa8ec8.html)
- [Authorization Code Grant (ACG)](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/authorizationcodegrantacg.4.96cca41179bad4b1aa8f05.html)

## Auktorisationsflöden och autentiseringsmetoder

I tabellerna ser du alla flöden, respektive autentiseringsmetod samt tekniska detaljer som är bra att ha koll på för implementationen. När du gör ett anrop är det väldigt viktigt att du skriver rätt adress till auktorisationsservern, annars kommer säkerhetslösningen inte att fungera. Du hittar rätt adresser i tabellerna eller i beskrivningen av respektive flöde.

<table><tbody><tr><td colspan="3"><p><strong>Authorization Code Grant (ACG)</strong></p></td></tr><tr><td><p><strong>Autentisering av programvaran</strong></p></td><td><p>Client ID + client<br>secret</p></td><td><p>Client ID + client<br>secret</p></td></tr><tr><td><p><strong>Autentisering av slut</strong> <strong>användare</strong></p></td><td><p>E-legitimation</p></td><td><p>Organisationslegitimation</p></td></tr><tr><td><p><strong>Auktorisationsserver</strong></p></td><td><p>peroauth2.skatteverket.se</p></td><td><p>orgoauth2.skatteverket.se</p></td></tr><tr><td><p><strong>Krävs redirect-URI?</strong></p></td><td><p>Ja</p></td><td><p>Ja</p></td></tr><tr><td><p><strong>Kan API-nycklarna användas i andra säkerhetsflöden?</strong></p></td><td><p>Ja</p></td><td><p>Ja</p></td></tr></tbody></table>

<table><thead><tr><th colspan="4"><p><strong>Client Credential Grant (CCG)</strong></p></th></tr></thead><tbody><tr><td><p><strong>Autentisering av programvaran</strong></p></td><td><p>Client ID + client<br>secret</p></td><td><p>Client ID + utpekad org.leg.</p></td><td><p>Client ID + client secret + valfri org.leg.</p></td></tr><tr><td><p><strong>Autentisering av slut</strong> <strong>användare</strong></p></td><td><p>Nej</p></td><td><p>Organisations-legitimation</p></td><td><p>Organisations-</p><p>legitimation</p></td></tr><tr><td><p><strong>Auktorisationsserver</strong></p></td><td><p>sysoauth2.<br>skatteverket.se</p></td><td><p>sysorgoauth2.<br>skatteverket.se</p></td><td><p>sysorgoauth2.<br>skatteverket.se</p></td></tr><tr><td><p><strong>Krävs redirect-URI?</strong></p></td><td><p>Nej</p></td><td><p>Nej</p></td><td><p>Nej</p></td></tr><tr><td><p><strong>Kan API-nycklarna användas i andra säkerhetsflöden?</strong></p></td><td><p>Ja</p></td><td><p>Nej, lösningen kan inte användas i andra flöden.</p></td><td><p>Ja</p></td></tr></tbody></table>

## Vad är OAuth 2?

OAuth2 är ett öppet säkerhetsramverk som kan användas för behörighet och åtkomst mellan olika komponenter. Ramverket innehåller olika flöden beroende på vilka komponenter som ska kommunicera med varandra. Skatteverket använder flödena Client Credentials Grant (CCG) och Authorization Code Grant (ACG) i de allra flesta av våra API-lösningar. Både CCG och ACG kräver att du har API-nycklar i autentiseringen mot Skatteverkets auktorisationsserver. Om du använder ACG-flödet och användaren autentiserar sig med en e-legitimation krävs dessutom att användaren ger sitt medgivande för att programvaran ska kunna anropa API:et.

Här kan du läsa mer om nycklarna:

- [Så fungerar API-nycklar](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/safungerarapinycklar.4.96cca41179bad4b1aa9176.html)