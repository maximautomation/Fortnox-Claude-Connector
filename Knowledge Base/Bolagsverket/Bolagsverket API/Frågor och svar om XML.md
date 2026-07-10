---
title: "Frågor och svar om XML"
source: "https://bolagsverket.se/apierochoppnadata/driftochsupport/fragorochsvaromxml.5844.html"
author:
published: 2025-11-21
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
Här samlar vi vanliga frågor om XML.

## Beställning

## Hur beställer jag XML-paket från Bolagsverket?

Du [kontaktar oss](https://bolagsverket.se/apierochoppnadata/driftochsupport/kontaktaossomapierochoppnadata.3996.html) via vårt formulär.

## Registret över verkliga huvudmän (RVH)

## Vanliga frågor från allmänheten?

Läs mer på sidan: [Vanliga frågor från allmänheten om verklig huvudman.](https://bolagsverket.se/omoss/flerverksamheter/omverklighuvudman/vanligafragorfranallmanhetenomverklighuvudman.2543.html)

## Vanliga frågor från ombud och rådgivare?

Läs mer på sidan: [Vanliga frågor från ombud/rådgivare om verklig huvudman.](https://bolagsverket.se/omoss/flerverksamheter/omverklighuvudman/vanligafragorfranombudradgivareomverklighuvudman.2545.html)

## Test och utveckling

## Hur kommer jag åt testmiljön för XML-paket på Bolagsverket?

När du beställer tjänsten kommer att Bolagsverket skicka inloggningsuppgifter och adresser för att test ska kunna påbörjas.

## Varför fungerar inte valideringen av min XML-kod?

Om valideringen inte lyckas är ett vanligt misstag att du har ett teckenfel eller ett ogiltigt organisationsnummer.

XML-koden är teckenkänslig och ger felmeddelande när element och attribut inte överensstämmer med våra exempel. Viktigt att tänka på är att alla organisationsnummer i våra exempel är fiktiva. Se därför till att ersätta dem med giltiga organisationsnummer.

## Web Service kan använda både GET och POST. Vilket anrop rekommenderas?

Anrop mot XML-paket på Bolagsverket kräver POST-anrop för att fungera.

## Klientcertifikat

## Hur får jag ett klientcertifikat för Bolagsverkets XML-tjänst?

Du beställer själv ett certifikat hos Expisoft. Observera att hos Expisoft heter certifikatet **serverlegitimation**. Under Externa länkar finns länk till Expisoft webbplats.

## Vad kostar ett klientcertifikat och tar det lång tid att få?

Normalt tar det ett par veckor att få sitt certifikat. Se aktuell prislista på Expisoft webbplats som du hittar under Externa länkar.

## Behöver jag olika certifikat i produktion och i test?

Nej. Du kan använda samma certifikat både i produktion och i test.

## Måste jag installera certifikatet på den dator som anropar Bolagsverkets e-tjänst?

Nej. Du behöver inte installera certifikatet utan det skickas med i varje https-request (anrop) till Bolagsverket.

I parametern certId fyller du i ditt serienummer (16 + organisationsnummer).

Exempel för Bolagsverket: 162021005489.

## Måste vi beställa ett certifikat till varje server?

Nej. Det går bra att installera samma certifikat på flera servrar.

## Övriga frågor

## Var vänder jag mig ifall jag får problem och behöver hjälp?

För felanmälan och övriga frågor [kontaktar du oss](https://bolagsverket.se/apierochoppnadata/driftochsupport/kontaktaossomapierochoppnadata.3996.html) via vårt formulär.