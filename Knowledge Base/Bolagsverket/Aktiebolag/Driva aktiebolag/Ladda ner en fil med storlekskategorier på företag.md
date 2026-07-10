---
title: "Ladda ner en fil med storlekskategorier på företag"
source: "https://bolagsverket.se/foretag/aktiebolag/drivaaktiebolag/storaforetagskarapporterabetalningstider/laddanerenfilmedstorlekskategorierpaforetag.4716.html"
author:
published: 2023-06-30
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
För att ni som rapporteringsskyldigt företag ska kunna sammanställa era uppgifter måste en företrädare, med svensk e-legitimation, logga in i vår digitala tjänst och hämta uppgifter om storlekskategorier för de leverantörer ni har.

[Hämta storlekskategori Länk till annan webbplats.](https://betalningstider.bolagsverket.se/)

I tjänsten kan ni ladda ner en lista (i CSV -format) över storlekskategorier för samtliga företag i Sverige som har färre än 250 anställda. Med hjälp av filen matchar ni sedan en betalning i ert ekonomisystem mot de uppgifter om leverantörsstorlek som ni hämtat. Därefter sammanställer ni era betalningstider och rapporterar in dem.

## Ny fil varje år

Varje år innan rapporteringsperioden skapar vi filen som ni sedan kan hämta i tjänsten. För att underlätta för er att särskilja filer för olika år kommer filnamnet att innehålla information om vilket år filen avser samt datum när filen skapades.

Exempel: leverantorsinformation\_2023\_20230630.csv

## Om CSV-filen

Filens format är en flat fil, där varje rad innehåller information om ett företag. Filen innehåller mellan 1,5–2 miljoner företag och filstorleken kommer att vara cirka 120 MB. Filen innehåller även en inledande rad med rubriker med beskrivande namn på informationen i filen.

Informationen på en rad är uppdelad på termer som är separerade med tab-tecknet. Anledningen till det är att informationen i filen inte kan innehålla tab-tecken, men däremot andra vanliga separatortecken som exempelvis semikolon, kolon, kommatecken och blanktecken.

## Testfil för dig som vill testa funktionen

Här finns en testfil enligt ovanstående format som ni kan använda om ni vill testa funktionen.

Testfilen innehåller

- tre företag med organisationsnummer
- tre med personnummer
- tre med samordningsnummer.

Varje typ av företag finns representerad i de tre olika storleksklasserna.

De nio identitetsbeteckningar som finns i testfilen är avsedda för test och ger exempelvis dig som utvecklar programvara möjlighet att testa dina tjänster med definitionsmässigt korrekta beteckningar.

För att matcha ett företag i ditt ekonomisystem mot testfilen, måste du komplettera filen med information om de leverantörer du vill använda i dina tester.

**Filnamn**: [leverantorsinformation\_test\_20230101.csv csv, 702 bytes.](https://bolagsverket.se/download/18.5480e1ea1848204e424bc/1669639040848/leverantorsinformation_test_20230101.csv)  
**Filbeskrivning**: [Excelfil som beskriver innehållet i testfilen xlsx, 11 kB.](https://bolagsverket.se/download/18.5480e1ea1848204e424d1/1669625620660/beskrivning_csv-fil_antalanstalldaforetag_20221111.xlsx)  
**Beskrivning**: Information om antal anställda per företag med färre än 250 anställda.  
**Format**: CSV