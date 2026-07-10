---
title: "Så här kan du använda regelfiler och regelmotor"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/saharkanduanvandaregelfilerochregelmotor.4.13948c0e18e810bfa0c28a4.html"
author:
published:
created: 2026-07-09
description: "Skatteverkets regelfiler och regelmotor kan beskrivas som en mikrotjänst. Här förklarar vi på ett enkelt sätt hur \"mikrotjänsten\" fungerar och hur du kan använda den i din applikation."
tags:
  - "clippings"
---
## Så använder du regelfiler och regelmotor - guide till Rättsliga regler

Inom området Exponera regler i kundens miljö erbjuder Skatteverket ett API, regelfiler och en regelmotor. Regelfiler och regelmotor kan beskrivas som en mikrotjänst, som du kan använda i din applikation.

## API:et Rättsliga regler

API:et Rättsliga regler riktar sig till dig som utvecklar programvara som hanterar skatteregler. Du hittar en utförligare beskrivning av API:et, samt regelfiler, på vår Utvecklarportal.

- [Rättsliga regler (Utvecklarportalen) Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen?q=R%C3%A4ttsliga%20regler&dataresurs=partner-api)
- [Rättsliga regelfiler (Utvecklarportalen) Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen/oppetdata/R%C3%A4ttsliga%20regelfiler)

## Översikt över begreppen

| Begrepp | **Betydelse** |
| --- | --- |
| **Regelmotorn** | Själva regelmotorn är en funktion i en tjänst som du sedan själv bygger. Den regelmotor som Skatteverkets regelfiler är anpassade för heter Json-rules-engine. |
| **Regel** | En uppsättning villkor. Skatteverkets regler är uppbyggda av frågor och svar. |
| **Facts** | De villkor som du uppfyller och som regelmotorn matchar mot reglerna. |

## Varför använda regelfiler och regelmotor?

Syftet med att använda Skatteverkets regelfiler och regelmotor är att separera den juridiska logiken från applikationslogiken. Det finns ett antal fördelar med detta, till exempel

- Enklare teknisk förvaltning och testning. Skatteverket sköter uppdateringarna av regler, så att du slipper uppdatera koden i din applikation varje gång en lagändring sker.
- Ökad skalbarhet. Samma juridiska logik kan återanvändas i flera applikationer.
- Ökad transparens. Det blir enklare för dig som utvecklare att förstå juridiken och implementera den som villkor (regler).
- Enklare att underhålla. Genom att reglerna kan visas upp i ett gränssnitt snarare än direkt i koden, blir de även enklare att granska och uppdatera för jurister och andra domänexperter.

### Så hänger regelfiler och regelmotor ihop

Regelfilerna och regelmotorn är ingen färdig tjänst och kan inte användas av en slutkund. Våra illustrationer visar hur regelmotorn och regelfilerna hänger ihop och hur de kan passa in i din applikation.

#### Bild 1. Logik för rättsliga regler

Facts och regler matas in i regelmotorn, som genererar utdata i form av en textsträng. Utdatan skulle till exempel kunna vara "Skattefri ersättning kan betalas ut med 25 kronor per mil." Detta är endast ett lager logik som du som utvecklare kan använda i din applikation.

![](https://www.skatteverket.se/images/18.13948c0e18e810bfa0c28b5/1713786418278/rattsligaregler1.png)

#### Bild 2. Din applikation

Din applikation samverkar med regelmotorn och regelfilerna enligt illustrationen nedan. Tänk att det till exempel är en räknesnurra som ska visa ersättning för antal mil. I applikationen finns möjlighet att lämna ytterligare indata, till exempel "10 mil" och "100 dagar". Slutanvändaren kan då få utdata i stil med att "Ersättningen blir 25 000 kronor". Hur denna in- och utdata lämnas respektive presenteras är separerat från den juridiska logiken.

![](https://www.skatteverket.se/images/18.13948c0e18e810bfa0c28b9/1713786611941/rattsligaregler2.png)

## Så kan du använda regelfilerna

En regelfil innehåller en uppsättning regler. Regelfiler är grupperade i regelområden, som till exempel "Reseräkning". Varje regelfil får också ett mer preciserande namn, till exempel "Logikostnader".

Skatteverkets regelfiler innehåller generiska data, men i kundens miljö kan du som utvecklare lägga till värden och funktioner som är specifika för din applikation.

#### Teknisk genomgång i fyra punkter:

Här är några saker du kan vara uppmärksam på när du ska börja använda filerna:

1. Facts i kundens miljö kan skilja sig från hur värdena ser ut i Skatteverkets regelfiler. Det löser du genom mappning. Mappning är beskrivet i en av exempelfilerna i mappen JsonREexempel.zip som du hittar på dataresursen Rättsliga regelfilers sida på Utvecklarportalen, under rubriken Exempelfiler - teknisk guide.
2. I regelfilerna finns villkor för en regel samlade i en array med nyckeln "all". Det är en följd av strukturen i regelmotorn Json-rules-engine som möjliggör kapsling.
3. I dagsläget använder Skatteverket inte kapslade (nested) regler. Det beror på att vi vill hålla de tekniska reglerna så enkla som möjligt för att de ska kunna skapas och läsas av människor.
4. Den datatyp som används är alltid string. Operator är alltid equal som en följd av att datatypen alltid är string. I framtiden kan även andra datatyper komma att användas.
- [Rättsliga regelfiler Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen/oppetdata/R%C3%A4ttsliga%20regelfiler)
- [Exempelfiler, teknisk guide (zip-fil) Länk till annan webbplats.](https://skatteverket.entryscape.net/store/9/resource/2275)

### Så fungerar regelmotorn

Regelmotorns funktion är att ta facts och matcha (evaluera) dem mot reglerna. När dina facts matchar reglerna triggas ett success event och du får då tillgång till den information som finns lagrad i regelns event-objekt. Utdatan du får från regelmotorn är alltid en textsträng. Den innehåller vanligtvis en juridisk förklaring och källhänvisningar, men kan även innehålla till exempel värden för belopp.

Hur du väljer att använda och visa tillgänglig information är upp till dig som skapar tjänsten. Numeriska värden kan du använda till beräkningar. Vill du visa en text eller ett belopp i en applikation som visas på en slutanvändares skärm kan du göra det. Du kan också skicka vidare informationen till något annat system. Att visa källhänvisningar kan vara onödigt i en tjänst där slutanvändaren inte är jurist. Men för jurister kan källhänvisningarna i stället vara det viktigaste att visa.

#### Kodexempel

På vår Utvecklarportal, på API-sidan för Rättsliga regler under fliken Exempel, hittar du ett enkelt kodexempel.

- [Rättsliga regler Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen/api/regelverk-rattsliga-regler/1.0.2/Exempel)

## Håll koll på vad som är på gång

På sidan ”Exponera regler i kundens miljö” under sektionen Utvecklingsområden i vänstermenyn hittar du information om vilken utveckling som är på gång för API:et Rättsliga regler samt regelfilerna.

- [Exponera regler i kundens miljö](https://www.skatteverket.se/omoss/digitalasamarbeten/utvecklingsomraden/exponerareglerikundensmiljo.4.7c708f0e16bed42cd05558e.html)