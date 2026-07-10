---
title: "Hämta information om verklig huvudman"
source: "https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/hamtainformationomverklighuvudman.6009.html"
author:
published: 2026-06-24
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
Från och med den 1 juli 2026 justeras tillgången till uppgifter ur registret över verkliga huvudmän. Det är till följd av EU:s nya penningtvättsdirektiv. Lagförändringarna innebär bland annat striktare regler om hur den som efterfrågar informationen kan få ta del av uppgifter ur registret elektroniskt.

## De olika alternativen för att hämta information om verkliga huvudmän

[API för att hämta företagsinformation](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation.3988.html) För företag, privatpersoner och offentlig verksamhet som vill hämta information direkt till egna verksamhetssystem.

[Sök verklig huvudman](https://bolagsverket.se/sjalvservice/etjanster/verklighuvudman/sokverklighuvudman.3084.html) För företag, privatpersoner och offentlig verksamhet som vill använda en e-tjänst för att hämta information.

[Anslut åtkomstlösning till behörighetsregister](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/hamtainformationomverklighuvudman/anslutatkomstlosningtillbehorighetsregister.6011.html) För myndigheter och verksamhetsutövare som vill hämta information via e-tjänsten Sök verklig huvudman och har eget behörighetsregister.

## Användare av informationen delas upp i tre grupper

**Grupp 1** är myndigheter som antingen är brottsbekämpande, utövar tillsyn inom penningtvättsområdet eller andra myndigheter som har uppgifter som kopplas till att förebygga, upptäcka eller utreder penningtvätt och finansiering av terrorism.

**Grupp 2** omfattar verksamhetsutövare som enligt penningtvättsregelverket behöver kontrollera information om verkliga huvudmän som en del av kundkännedomsprocessen (KYC).

**Grupp 3** är svenska myndigheter, vissa utländska myndigheter och verksamhetsutövare, organisationer i det civila samhället, journalister, forskare, media och övriga som kan uppvisa ett berättigat intresse. Det berättigade intresset ska vanligtvis kopplas till ändamål som berör att motverka penningtvätt, finansiering av terrorism och annan brottslighet.

## Vilken lösning passar min organisation om jag har behov av information om verkliga huvudmän?

### Identifiera vilken användarkategori din organisation tillhör

Vilka möjligheter som finns för att få tillgång till information om verkliga huvudmän beror på vilken användarkategori er organisation tillhör enligt penningtvättsregelverket.

## Grupp 1 – Myndigheter

Myndigheter som antingen är brottsbekämpande, utövar tillsyn inom penningtvättsområdet eller andra myndigheter som har uppgifter som kopplas till att förebygga, upptäcka eller utreder penningtvätt och finansiering av terrorism.

Myndigheter inom denna grupp har omedelbar, fullständig och avgiftsfri tillgång till information om verkliga huvudmän.

### Typiska behov

Myndigheter inom gruppen behöver ofta:

- integrera information i egna verksamhetssystem
- genomföra automatiserade kontroller
- ge många användare åtkomst
- hantera behörigheter internt.

### Vilka alternativ finns för Grupp 1?

#### Alternativ 1 – Direkt integration mot Bolagsverkets API för att hämta företagsinformation

Det här alternativet passar myndigheter som vill hämta information direkt till egna verksamhetssystem.

Passar särskilt bra om ni:

- har egna handläggnings- eller utredningssystem
- vill automatisera informationshämtning
- endast behöver information om svenska företag
- inte har behov av att använda Bolagsverkets användargränssnitt.

##### Fördelar

- Enkel system-till-system-integration.
- Ingen hantering av individuella användarbehörigheter via åtkomstlösningens proxy.
- Informationen kan användas direkt i egna processer och system.

##### Att tänka på

Myndigheten ansvarar själv för:

- intern behörighetsstyrning
- informationssäkerhet
- korrekt användning av informationen.

Läs mer på sidan [API för att hämta företagsinformation](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation.3988.html).

#### Alternativ 2 – Anslut åtkomstlösning till ert behörighetsregister för att hämta information med e-tjänsten Sök verklig huvudman

Det här alternativet passar myndigheter som vill använda Bolagsverkets e-tjänst Sök verklig huvudman eller EU:s tjänst e-juridikportalen.

Passar särskilt bra om ni:

- har många användare
- vill hantera behörigheter själva
- redan har Identity and Access Management -(IAM-) eller behörighetslösningar.

##### Fördelar

- Full kontroll över användarbehörigheter.
- Snabb administration av användare.
- Ingen central ansökningshantering hos Bolagsverket.

##### Det här behöver ni göra

- Etablera ett register över behöriga användare.
- Tillgängliggöra behörighetsregistret via API.
- Hantera administration och uppdatering av behörigheter.

Läs mer på sidan [Anslut åtkomstlösning till behörighetsregister](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/hamtainformationomverklighuvudman/anslutatkomstlosningtillbehorighetsregister.6011.html).

## Grupp 2 – Verksamhetsutövare enligt penningtvättsregelverket

Grupp 2 omfattar verksamhetsutövare som enligt penningtvättsregelverket behöver kontrollera information om verkliga huvudmän som en del av kundkännedomsprocessen (KYC).

### Typiska behov

Verksamhetsutövare behöver ofta:

- genomföra kundkontroller
- ge användare snabb åtkomst till information
- integrera information i befintliga processer
- hantera olika typer av användare och roller.

### Vilka alternativ finns för Grupp 2?

#### Alternativ 1 – Direkt integration mot Bolagsverkets API för att hämta företagsinformation

Det här alternativet passar verksamhetsutövare som vill integrera information direkt i sina egna system och processer.

Passar särskilt bra om ni:

- har egna KYC- eller complianceplattformar
- vill automatisera kontroller
- har hög användningsvolym
- vill minimera manuella moment.

##### Fördelar

- Effektiv integration i befintliga arbetsflöden.
- Automatiserade kontroller och processer.
- Ingen användning av separat e-tjänst.

Läs mer på sidan [API för att hämta företagsinformation](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation.3988.html).

#### Alternativ 2 – Anslut åtkomstlösning till ert behörighetsregister för att hämta information med e-tjänsten Sök verklig huvudman

Det här alternativet passar verksamhetsutövare som vill använda Bolagsverkets tjänst Sök verklig huvudman men själva hantera användarbehörigheter.

Passar särskilt bra om ni:

- har många användare
- vill kontrollera behörigheter internt
- redan har IAM-lösningar.

##### Fördelar

- Bättre kontroll över användarbehörigheter.
- Snabb hantering av förändringar.
- Minskad administration jämfört med individuell ansökan.

Läs mer på sidan [Anslut åtkomstlösning till behörighetsregister](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/hamtainformationomverklighuvudman/anslutatkomstlosningtillbehorighetsregister.6011.html).

#### Alternativ 3 – Ansök om tillgång till uppgifter om verkliga huvudmän via Bolagsverkets e-tjänst för att kunna hämta information med e-tjänsten Sök verklig huvudman

Bolagsverkets e-tjänst för att ansöka om tillgång till uppgifter om verkliga huvudmän kommer hösten 2026.

Det här alternativet passar verksamhetsutövare som inte vill bygga integrationer eller hantera egna register.

Passar särskilt bra om ni:

- har få användare
- saknar integrationsmöjligheter
- vill komma igång snabbt.

##### Att tänka på

Organisationen behöver hantera:

- interna godkännanden, signering av firmatecknare vid behov
- administration av användare
- eventuella avgifter

## Grupp 3 – Övriga användare med berättigat intresse

Grupp 3 är svenska myndigheter, vissa utländska myndigheter och verksamhetsutövare, organisationer i det civila samhället, journalister, forskare, media och övriga som kan uppvisa ett berättigat intresse.

Det berättigade intresset ska vanligtvis kopplas till ändamål som berör att motverka penningtvätt, finansiering av terrorism och annan brottslighet. För att avgöra om aktören har ett berättigat intresse kommer en prövning genomföras i varje enskilt ärende.

Tillgången är:

- begränsad
- avgiftsbelagd
- kopplad till enskilda ärenden eller företag.

### Alternativet för Grupp 3

#### Ansök om tillgång till uppgifter om verkliga huvudmän via Bolagsverkets e-tjänst för att kunna hämta information med e-tjänsten Sök verklig huvudman

## Jämför alternativen

| Alternativ | Passar bäst för | Teknisk integration | Hantering av behörigheter |
| --- | --- | --- | --- |
| Alternativ 1 – Direkt integration mot Bolagsverkets API för att hämta företagsinformation | Myndigheter och större verksamhetsutövare. | Ja | Hanteras internt hos er |
| Alternativ 2 – Anslut åtkomstlösning till ert behörighetsregister för att hämta information med e-tjänsten Sök verklig huvudman | Det här alternativet passar verksamhetsutövare som vill använda Bolagsverkets tjänst Sök verklig huvudman men själva hantera användarbehörigheter. | Ja | Hanteras internt hos er |
| Alternativ 3 – Ansök om tillgång till uppgifter om verkliga huvudmän via Bolagsverkets e-tjänst för att kunna hämta information med e-tjänsten Sök verklig huvudman | Mindre organisationer och enskilda användare | Nej | Hanteras av Bolagsverket |