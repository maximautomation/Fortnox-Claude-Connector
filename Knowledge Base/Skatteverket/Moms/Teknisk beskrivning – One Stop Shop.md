---
title: "Teknisk beskrivning – One Stop Shop"
source: "https://www.skatteverket.se/foretag/moms/deklareramoms/ansokomattredovisadistansforsaljningionestopshoposs/tekniskbeskrivningonestopshop.4.96cca41179bad4b1aa1d6.html"
author:
published:
created: 2026-07-09
description: "Om du har ett stort antal deklarationsrader kan de registreras i förväg i en fil."
tags:
  - "clippings"
---
Om du har ett stort antal deklarationsrader kan de registreras i förväg i en fil. Deklarationsraderna kan sedan läsas in direkt i e-tjänstens deklarationsformulär.

## Så här gör du

Du behöver skapa en fil i ett ordbehandlingsprogram där uppgifterna kan sparas som oformaterad text. Filen laddar du upp i e-tjänstens sida Deklarera.

### Skapa en fil med deklarationsuppgifterna

Filen med deklarationsuppgifterna ska vara en semikolonavgränsad textfil. Det innebär att du fyller i uppgifterna för varje deklarationsrad på en rad i en särskild ordning. Varje uppgift ska avgränsas med ett semikolon. Du kan fritt välja ett namn på filen då namnet inte har någon betydelse för e-tjänstens funktion.

Så här skriver du innehållet i filen:

Först anges den försäljningen som avser den aktuella perioden enligt följande:

| Rad 1 | Rad 2 | Rad 3 fram till rättningar |
| --- | --- | --- |
| Ange ”OSS\_001” | Identifieringsnummer med inledande prefix. | ”SE” (med versaler) för omsättning från Sverige. Vid omsättning från ett medlemsland där du har en fast etablering/lager, ange landskod (med versaler) och registreringsnummer för denna. Om en vara försänds eller transporteras från ett annat medlemsland där du inte har något registreringsnummer för mervärdesskatt eller skatteregistreringsnummer ska en "landsdeklaration" lämnas genom att ange landskod (med versaler) för det land som varan skickats ifrån. |
|  | Deklarationsperiod, kvartal (1,2,3 eller 4) eller månad för importordningen (01-12). | Landskod för konsumtionslandet (MSCON) Använd versaler. |
|  | Deklarationsperiod, år (format: ÅÅÅÅ). | Skattesats. Ange med två decimaler och kommatecken som decimalavskiljare. |
|  |  | Skattepliktig omsättning, > 0. Ange belopp med två decimaler med kommatecken som decimalavskiljare. |
|  |  | Skatt att betala, > 0. Ange belopp med två decimaler med kommatecken som decimalavskiljare. |
|  |  | Om redovisning avser försäljning av vara eller tjänst. Anges med "GOODS" eller "SERVICES" |

Om du ska göra rättningar för tidigare perioder gör du det i samma fil. Alla rader som avser den aktuella perioden ska anges innan eventuella rättningar som avser tidigare perioder anges, se exempel nedan. Rättningar anges enligt följande:

| Rad 1 för rättningar | Rad 2 och framåt för rättningar |
| --- | --- |
| Ange "CORRECTIONS" | Redovisningsperiod rättningen avser. Anges med årtal och deklarationsperiod. T.ex. 2021Q1 för kvartal och 2021M02 för månad. |
|  | Landskod för konsumtionslandet (MSCON) rättningen avser. Använd versaler. |
|  | Justering av skatt att betala för angiven deklarationsperiod och konsumtionsland. Vid sänkning anges ett minustecken framför beloppet. |

Sätt ett semikolon mellan uppgifterna på samma rad, se exempel nedan. Avsluta raderna med \<CR> (Carriage Return) och \<LF> (Line Feed). En symbol syns då vid varje radslut. Skriv tecknen i enlighet med standarder för teckenkodning för västeuropeiska språk (ISO/EIC 8859-1, ”ANSI” eller “Windows”).

Spara filen som en oformaterad textfil. Om du har använt till exempel Microsoft Excel behöver du tänka på att den sparade textfilen inte får innehålla några formler.

Så här kan en korrekt fil för unionsordningen se ut:

OSS\_001;◄  
SE556000016701;2;2022;◄  
SE;DK;25,00;50000,00;12500,00;GOODS;◄  
SE;FI;24,00;10060,56;2414,53;GOODS;◄  
SE;DE;19,00;20015,00;3802,85;SERVICES;◄  
DK12345690;DE;19,00;15090,00;2867,10;SERVICES;◄  
DK;DE;19,00;11250,00;2137,50;GOODS;◄  
CORRECTIONS◄  
2021Q3;FR;500;◄

Så här kan en korrekt fil för importordningen se ut:

OSS\_001;◄  
IM7520000000;01;2022;◄  
SE;DK;25,00;50000,00;12500,00;GOODS;◄  
SE;FI;24,00;10060,56;2414,53;GOODS;◄  
CORRECTIONS◄  
2021M09;FR;500;◄

Du ska bara ange uppgifter för de länder du har haft försäljning till. Ange aldrig beloppet 0 som värde för skattepliktig omsättning, skatt för landet eller justering av skatt att betala.

### Ladda upp filen i e-tjänsten

Du laddar upp filen med uppgifterna i e-tjänstens sida ”Deklarera”. Välj funktionen ”Läs in från fil” och välj filen som du har skapat. När uppgifterna har lästs in och kontrollerats visas de i deklarationsformuläret. Tänk på att de nya uppgifterna skriver över och ersätter uppgifter som eventuellt redan lagts in i formuläret.

#### Om du får ett felmeddelande

Om du inte har skrivit in uppgifterna på rätt sätt eller om någon uppgift saknas, får du ett felmeddelande. Finns det felaktigheter i formuläret sparas inte uppgifterna i e-tjänsten. Du behöver först åtgärda felet och ladda upp filen på nytt.

I tabellen nedan ser du orsaken till olika felkoder.

| Felkod | Orsak |
| --- | --- |
| 100 | Filen innehåller för lite information. |
| 101 | Filen måste börja med ”OSS\_001” |
| 201 | Filen ska avse valt företag. Kontrollera registreringsnumret. |
| 202 | Filen ska avse vald deklarationsperiod. Kontrollera deklarationsperioden i filen. |
| 301 | Omsättningsland ska vara ett giltigt EU-land eller momsregistreringsnummer för registrerad fast etablering. |
| 302 | Den fasta etableringen måste ha varit registrerad under den valda deklarationsperioden. |
| 303 | Landskoden för omsättningsland ska alltid vara ‘SE’ i tredjelandsordningen. |
| 304 | Landskoden för konsumtionsland (MSCON) ska avse ett giltigt EU-land. |
| 305 | Landskoden för konsumtionsland (MSCON) får inte vara ’SE’ för svenska företag. |
| 311 | Fel skattesats. Skattesatsen ska vara giltig för valt konsumtionsland (MSCON) och deklarationsperiod. |
| 321 | Du behöver fylla i skattepliktig omsättning eftersom du fyllt i ett belopp i 'Skatt att betala'. Använd positiva heltal eller två decimaler, kommatecken som decimaltecken. |
| 322 | Du behöver fylla i skatt att betala eftersom du fyllt i ett belopp i 'Skattepliktig omsättning'. Använd positiva heltal eller två decimaler, kommatecken som decimaltecken. |
| 324 | Du har fyllt i samma kombination av försäljningsland, konsumtionsland och skattesats på flera rader. Kontrollera innehållet på raderna. |
| 400 | Det saknas information om rättelsen. Kontrollera uppgifterna. |
| 401 | Du kan bara göra rättelser på perioder som företaget tidigare deklarerat. |
| 402 | Du kan bara göra rättelser mot medlemsländer som var aktuella för den valda perioden. |
| 403 | Filen får inte innehålla rättelser för tidigare perioder. |
| 424 | Dubblettkontroll, man kan inte ange flera rader med samma konsumtionsland och ändring i skatt. |
| 425 | Du kan bara ange positiva heltal eller två decimaler för “Skattepliktig omsättning”, eller “Skatt att betala”. |

### Behöver du ta reda på en landskod?

EU listar alla landskoder på sin hemsida.

- [Hitta rätt landskod på EU:s hemsida Länk till annan webbplats.](https://ec.europa.eu/eurostat/statistics-explained/index.php?title=Glossary:Country_codes)

### Behöver du ändra i deklarationen?

Behöver du göra en ändring i en redan inskickad deklaration görs det i deklarationen för en kommande redovisningsperiod. Rättelsen görs i avsnittet ”CORRECTIONS”. Ange vilken period och vilket land rättelsen avser samt en justering av skatt att betala.