---
title: "Debiterad preliminärskatt (F-skatt)"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/utvecklingsomraden/debiteradpreliminarskattfskatt.4.7da1d2e118be03f8e4fb7e.html"
author:
published:
created: 2026-07-09
description: "Målet med debiterad preliminärskatt är att differensen med slutskatten ska vara så liten som möjligt."
tags:
  - "clippings"
---
Med en preliminärdeklaration (PD) kan företag få besked om en preliminärskatt som inte kommer bli för hög, eller för låg, i förhållande till vad slutskatten sedan landar på.

## Kort om utvecklingsområdet

Tanken med den debiterade preliminärskatten (PD) är att det varje månad under året ska betalas in preliminärskatt för det förväntade resultatet i verksamheten. Den skattskyldige ska varje år betala så mycket preliminär skatt, under det år som hen har en inkomst, som hen ska betala i slutlig skatt för samma år.

Målet är att differensen mellan preliminärskatten och slutskatten vid slutskatteuttaget ska vara antingen noll, eller försumbar.

## Befintliga API:er och API:er under utveckling

Idag finns vissa relevanta kundhändelser om debiterad preliminärskatt tillgängliga via två av våra API:er.

### API:et Kundhändelser

Det gäller följande händelser:

- Kundhändelse för ”Preliminärdeklaration (PD) mottagen"
- Kundhändelse om ”Tips att lämna preliminärdeklaration (PD)”

Händelsen ”Tips om att lämna preliminärdeklaration” genereras inför en schablonkörning, när Skatteverket fastställer preliminärskatten för företagets nästkommande år.

Vi ser gärna att ditt företag skickar in en preliminärdeklaration innan schablonkörningen körs. Det kommer nämligen göra att schablonkörningen blir mer precis i sitt resultat, och ni får besked om en preliminärskatt som inte kommer bli för hög, eller för låg, i förhållande till vad slutskatten sedan landar på.

### API:et Skattekonto

API:et ger dig möjlighet att, i god tid före en specifik månads preliminärskatt ska betalas, se vad som ska betalas. Det ger dig också en ytterligare möjlighet att bedöma ifall det är en för låg eller för hög preliminärskatt.

Med dessa två API:er; [Kundhändelser Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen?q=kundh%C3%A4ndelser) och [Skattekonto Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen?q=skattekonto&dataresurs=partner-api), har ni alltså redan idag möjlighet till en viss löpande avstämning inbyggd i bokföringssystemen.

## API:er som planeras i framtiden

I dagsläget är ett partner-API för inlämning av preliminära deklarationer inte under utveckling. Det är heller inte planerat för när en sådan utveckling skulle kunna påbörjas. Vi tar gärna in synpunkter, behov och hör mer om vad du kan se för nytta av ett sådant API. Detta kan vi nämligen ta med oss när vi diskuterar fortsatt planering och prioritering.

Företag som ska deklarera har ofta bra koll på om preliminärskatten är för hög eller för låg. Vi skulle därför gärna utveckla ett partner API som möjliggör inlämning av en preliminär deklaration via programvaruföretagens lösningar. Lösningar som gör inlämnandet av en preliminärskatt (PD) enklare och snabbare är av stor vikt för att uppnå Skatteverkets slutmål; att slutskatten stämmer överens med preliminärskatten.

Utöver ett inlämnings-API ser vi att vi också kommer behöva erbjuda en fråga-/svar-tjänst där företag kan fråga vad det aktuella och historiska debiteringsbeslutet är.

**Vill du bidra till utvecklingen?**

Vi gör bättre saker när vi jobbar tillsammans! Hör gärna av dig till oss för att bidra till utvecklingen.

[Kontakta oss för samarbeten](https://www.skatteverket.se/omoss/digitalasamarbeten/samarbeten/kontaktaossforsamarbeten.4.7c708f0e16bed42cd055c16.html)