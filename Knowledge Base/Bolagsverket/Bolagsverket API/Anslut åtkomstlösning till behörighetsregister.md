---
title: "Anslut åtkomstlösning till behörighetsregister"
source: "https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/hamtainformationomverklighuvudman/anslutatkomstlosningtillbehorighetsregister.6011.html"
author:
published: 2026-06-24
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
Här hittar du information och stöd för myndigheter och verksamhetsutövare som vill ansluta egna behörighetsregister till Bolagsverkets åtkomstlösning för att behöriga personer ska kunna hämta information ur registret om verkliga huvudmän.

## Innehåll på sidan

![En person jobbar vid en laptop.](https://bolagsverket.se/images/18.5adc45011861b9c868f9b/1675942545138/en-person-jobbar-vid-en-laptop.jpg)

## Gör så här för att ansluta ditt behörighetsregister

1. **Läs igenom villkoren i våra avtal**
2. **Skicka in kundanmälan  
	**Fyll i och skicka in [kundanmälan](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/hamtainformationomverklighuvudman/kundanmalanforattbolagsverketsatkomstlosningskaanslutastillerorganisationsbehorighetsregister.6012.html).
3. **Ha en teknisk dialog  
	**Vi har en gemensam genomgång av förutsättningar och förväntningar.
4. **Teckna avtal  
	**Vi skickar ett avtal till dig.
5. **Verifiera uppkoppling mot ert register  
	**När det tekniska stödet är färdigt enligt specifikationen kontaktar ni oss för verifiering.
6. **Produktionssätta  
	**Vi produktionssätter anslutningen från Bolagsverkets åtkomstlösning mot ert behörighetsregister.

## Pris för att ansluta ditt behörighetsregister

Du betalar en anslutningsavgift när du vill att ditt behörighetsregister ska anslutas till åtkomstlösningen.

## Vad behöver du tänka på innan anslutning

Organisationer som vill hantera behörigheter lokalt behöver etablera ett eget register över personer som ska kunna få åtkomst till information om verkliga huvudmän.

Registret ska kunna:

- identifiera användare
- verifiera behörighet
- hantera förändringar i behörighet
- exponeras via API för integration med åtkomstlösningens proxy.

## Varför ansluta ett eget behörighetsregister?

Genom att använda ett eget register kan ni:

- minska administrationen kring ansökningar om att få tillgång till information om verkliga huvudmän
- få snabbare hantering av behörigheter
- ha full kontroll över användare och åtkomster.

## Teknisk anslutning

För att ansluta ett eget behörighetsregister behöver organisationen tillhandahålla ett API som gör det möjligt för Bolagsverkets åtkomstlösning att kontrollera användares behörighet i realtid.

API:et används endast för att besvara frågan om en identifierad användare är behörig eller inte.

För att genomföra en anslutning behöver organisationen:

- tillhandahålla ett behörighetsregister
- exponera ett API för behörighetskontroll
- etablera nödvändig säkerhetslösning
- genomföra verifiering i testmiljö.

Detaljerade tekniska krav, API-kontrakt, säkerhetskrav och exempel finns i implementationsanvisningen.

### Teknisk dokumentation

För att implementera integrationen behöver organisationen ta del av följande dokumentation:

- [Implementationsansvisning pdf, 216 kB.](https://bolagsverket.se/download/18.5eedd89a19ebd3e8ea54/1781678503241/implementationsanvisning_behorighetskontroll_v_0.5.pdf)
- Exempel: [swaggerfil/OpenAPI-fil yaml, 8 kB.](https://bolagsverket.se/download/18.37b754ba19ceb00666abcbb2/1781251693807/exempel_swagger_atp.yaml)

### Säker anslutning

Åtkomstlösningen använder etablerade säkerhetsmekanismer för att säkerställa att endast behöriga system kan utbyta information.

Kommunikationen mellan Bolagsverket och anslutna organisationer skyddas genom autentisering, behörighetskontroll och krypterad kommunikation.

Detaljerade säkerhetskrav beskrivs i implementationsanvisningen.

### Skydd av personuppgifter

Lösningen är utformad för att minimera spridning av känsliga personuppgifter.

Den person som ska söka efter information om verkliga huvudmän väljer själv vilken organisation som ska verifiera behörigheten innan uppgifter delas mellan systemen.

Organisationen med behörighetsregister ansvarar för att:

- behandla personuppgifter enligt gällande regelverk
- skydda behörighetsinformation
- säkerställa korrekt hantering av användardata.

### Förändringar av tekniska dokumentationen

Bolagsverket informerar anslutna organisationer om planerade förändringar i god tid innan de träder i kraft. Informationen kan exempelvis omfatta:

- nya API-versioner
- ändringar i informationsmodeller
- uppdaterade säkerhetskrav
- nya eller förändrade attribut
- ändringar i autentisering eller certifikathantering
- ändringar i test- och produktionsmiljöer.

## Drift och tillgänglighet

Organisationen ansvarar för att det anslutna behörighetsregistret är tillgängligt så att användares behörigheter kan verifieras när tjänsten används.

Organisationen ansvarar även för:

- övervakning av integrationen
- hantering av driftstörningar
- administration av behörigheter
- kommunikation vid större incidenter.

Detaljerade tekniska krav på tillgänglighet och svarstider finns i implementationsanvisningen.

## Test och verifiering

Innan en anslutning kan tas i produktion genomförs tester tillsammans med Bolagsverket.

Verifieringen syftar till att säkerställa att:

- integrationen fungerar enligt specifikationen
- säkerhetslösningen fungerar korrekt
- behörighetskontroller kan genomföras
- felhantering fungerar som förväntat.

Organisationen behöver tillhandahålla relevanta testdata och testanvändare i testmiljö.

Detaljerade testfall och verifieringskrav finns i implementationsanvisningen.

![Illustration för drift och support](https://bolagsverket.se/images/18.3bd0e5b6199877ec1a41ad65/1761309878491/support-illustration.png)

## Drift och support

Här hittar du information om driftstatus, planerade förändringar, supportnivåer och tekniska resurser. Du kan också läsa vanliga frågor, se servicetider och prenumerera på nyhetsflöden.