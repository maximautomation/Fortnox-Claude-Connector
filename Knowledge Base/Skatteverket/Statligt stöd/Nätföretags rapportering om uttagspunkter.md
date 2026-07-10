---
title: "Nätföretags rapportering om uttagspunkter"
source: "https://www.skatteverket.se/foretag/drivaforetag/statligtstod/natforetagsrapporteringomuttagspunkter.4.48cfd212185efbb440b8252.html"
author:
published:
created: 2026-07-09
description: "Elnätsföretag ska rapportera in uppgifter via en e-tjänst som öppnar 10 maj."
tags:
  - "clippings"
---
Skatteverket har fått i uppdrag att hantera ansökan om elstöd till företag. Elnätsföretagen har varit skyldiga att rapportera in uppgifter om uttagspunkter till Skatteverket via e-tjänsten ”Lämna in uppgifter om uttagspunkter”.

Alla uttagspunkter skulle rapporteras, även om det inte har varit någon förbrukning.

Skatteverket får inte bevilja elstöd efter den 31 december 2023. Skatteverket kan dock fortfarande betala ut stöd i följande fall:

- vid verkställande av dom från domstol
- vid återförvisning av ärende från domstol
- vid minskat återkrav av elstöd.

Den som har tillgodoräknats elstöd är återbetalningsskyldig om stödet har tillgodoräknats felaktigt eller med ett för högt belopp, eller villkoren för stödet inte har följts. I så fall får Skatteverket besluta att återkräva det felaktigt tillgodoräknade beloppet.

Uppgifter kan tills vidare korrigeras eller tas bort även efter det att e-tjänsten för att ansöka om elstöd har stängt den 25 september 2023.

- [Korrigera inlämnade uppgifter](https://www.skatteverket.se/foretag/drivaforetag/statligtstod/natforetagsrapporteringomuttagspunkter.4.48cfd212185efbb440b8252.html#Korrigerainlamnadeuppgifter)
- [Ta bort inlämnade uppgifter](https://www.skatteverket.se/foretag/drivaforetag/statligtstod/natforetagsrapporteringomuttagspunkter.4.48cfd212185efbb440b8252.html#Tabortinlamnadeuppgifter)

På denna sida finns en teknisk beskrivning av hur uppgifterna ska rapporteras in i e-tjänsten.

## Ombud för att rapportera nätföretags uppgifter

Elnätsföretaget behöver ha ett ombud registrerat hos Skatteverket för att kunna lämna in, korrigera eller ta bort uppgifter i e-tjänsten. Behöver du anmäla ombud måste du kontakta Skatteverket för att få en särskild blankett för detta.

Behörigheten ”Elstöd företag, rapportering nätföretag” ger ombudet rätt att i Skatteverkets e-tjänst ”Lämna in uppgifter om uttagspunkter” lämna in nätföretagets uppgifter om uttagspunkter för företag som är elslutkunder.

## Uppgifter som inte ska lämnas in

- Uppgifter för en uttagspunkt, om den som tagit ut el har bedömts vara berättigad till elstöd enligt förordningen (2022:1872) om elstöd till konsumenter för oktober 2021–september 2022 för den uttagspunkten.
- Uppgifter för statliga myndigheter.
- Uppgifter om uttagspunkter för elslutkunder om uppgifterna är klassificerade som säkerhetsskyddade. Detta enligt elstödsförordningen (2023:233) och säkerhetsskyddslagen (2018:585). Nätföretag som har elslutkunder som omfattas av säkerhetsskyddet blir kontaktade av Skatteverket för att lämna dessa uppgifter separat.

## Vilket filformat ska filen ha?

Filen ska vara i zip-format och innehålla xml-filer. Varje xml‑fil måste följa ett fastställt xsd‑schema, annars kommer filen inte att accepteras.

- [Xsd-schema och exempelfil finns att ladda ned](https://www.skatteverket.se/foretag/drivaforetag/statligtstod/natforetagsrapporteringomuttagspunkter.4.48cfd212185efbb440b8252.html#Underlagattladdaned)

## Kan flera elområden ingå i samma xml-fil?

Nej, det ska vara en xml-fil per elområde.

## Kan flera elområden ingå i samma zip-fil?

Ja, flera elområden kan ingå i samma zip-fil.

## Hur stora får filerna vara?

Varje fil får vara maximalt 10 MB stor. Om filen blir för stor när den innehåller alla uttagspunkter för ett elområde kan du skapa flera xml-filer för samma elområde. Därefter kan du packa ihop flera xml-filer i en zip-fil. Flera zip-filer kan skickas in och du använder då tjänsten flera gånger. Varje zip-fil får vara maximalt 10 MB stor.

## Vilka uppgifter måste finnas i filerna?

Varje xml-fil måste innehålla följande information:

- nätföretagets organisationsnummer
- periodstart för referensperiod
- periodslut för referensperiod
- elområde
- datum när filen skapades
- totalt antal poster i den aktuella xml-filen
- total förbrukning i den aktuella xml-filen.

Dessutom ska följande information anges för varje uttagspunkt:

- anläggningsidentitet för uttagspunkten
- totala mängden el som har tagits ut för förbrukning i uttagspunkten under 1 oktober 2021 till och med den 30 september 2022
- namn och id (person-, organisations- eller samordningsnummer) för den som hade rätt att ta ut el i uttagspunkten enligt ett avtal med nätföretaget den 17 november 2022.

**Observera att det är mycket viktigt att ett korrekt person-, organisations- eller samordningsnummer anges för att de inskickade uppgifterna ska kunna användas vid ansökningstillfället. Personnummer och samordningsnummer ska alltid skrivas med 12 siffror.**

## Korrigera inlämnade uppgifter

Om du vill korrigera tidigare inlämnade uppgifter behöver du ladda upp en ny fil med korrekta uppgifter för de anläggnings-id som ändringen gäller.

En korrigering av en uttagspunkt kan påverka ett företags rätt till stöd eller stödets storlek. Företag som berörs av en korrigering eller en borttagen uttagspunkt är välkomna att kontakta Skatteverket vid eventuella frågor.

## Ta bort inlämnade uppgifter

Om du vill ta bort en uttagspunkt som du tidigare har rapporterat gör du det i e-tjänsten Lämna in uppgifter om uttagspunkter. En borttagen uttagspunkt kan påverka ett företags rätt till stöd eller stödets storlek. Företag som berörs av en borttagen uttagspunkt är välkomna att kontakta Skatteverket vid eventuella frågor.

Observera att du inte kan genomföra ändringen genom att ladda upp samma anläggnings-id med noll i förbrukning.

## Underlag att ladda ned

- [Xsd-schema för nätföretags rapportering om uttagspunkter, version 1 (xsd) xsd, 9 kB.](https://www.skatteverket.se/download/18.48cfd212185efbb440b977d/1681738403969/elstod_foretag_v1_0.xsd)
- [Exempelfil xml för nätföretags rapportering om uttagspunkter (xml) xml, 2 kB.](https://www.skatteverket.se/download/18.48cfd212185efbb440b977f/1681738448199/exempelfil-korrekt-xml.xml)

## E-tjänst för inrapportering

[Lämna in uppgifter om uttagspunkter Länk till annan webbplats.](https://www7.skatteverket.se/portal/uttagspunkter/)

## Rättsinformation

- [Uppgiftslämnande till Skatteverket (Rättslig vägledning) Länk till annan webbplats.](https://www4.skatteverket.se/rattsligvagledning/429542.html)