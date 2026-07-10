---
title: "Rapport-tabeller - Visa alla konton i tabeller"
source: "https://support.fortnox.se/produkthjalp/koncern/rapport-tabeller-visa-alla-konton-i-tabeller"
author:
published: 2024-04-12
created: 2026-07-09
description: "Finns det konton i den bokföringsdata som är inläst men som inte visas i en tabell?"
tags:
  - "clippings"
---
Koncern, Rapport & Analys

Finns det konton i den bokföringsdata som är inläst men som inte visas i en tabell?

Då beror det antagligen på att skalningen i tabellen (dvs om det ska vara SEK, KSEK eller MSEK) skalar ner beloppet till noll, kombinerat med att tabellen inte visar noll-rader.

Det finns tre lösningar på detta problem:

- Ställa in att noll-rader ska visas (resultat: värdena kommer fortfarande skalas till 0 men raden kommer visas)
- Ställa in skalningen för en enskild tabell (resultat: alla rader i denna tabell kommer visas)
- Ställa in skalningen generellt i organisationen (resultat: alla rader i alla tabeller kommer visas)

Gäller det Fortnox inbyggda tabeller så går dessa inte att redigera, så då är det bara det tredje alternativet som löser problemet.

**Ställ in att noll-rader ska visas**  
Gå in i redigeringsläget för tabellen (man hittar organisationens egna tabeller via **Ekonomi - Komponenter - Rapport-tabeller**), klicka på Inställningar, klicka i **Visa noll-rader** och spara tabellen:

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2272x829%2F09e6e3cc0a%2Fvisaallakontonbild1.png%2Fm%2F&w=3840&q=75)

**Ställ in skalningen i en enskild tabell**  
I redigeringsläget väljer man Inställningar och sedan det alternativ under Nummerskalning som ger önskat resultat. Anges t ex värden i KSEK men man vill ha SEK så ställ in Nummerskalning:  
Ingen enligt nedan:

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2001x694%2Fdb9a5979c6%2Fvisaallakontonbild2.png%2Fm%2F&w=3840&q=75)

**Ställ in skalningen generellt**  
För att göra ovanstående inställning generellt i organisationens tabeller (och grafer) så går man till **Administration - Inställningar - Ekonomi**. Under **Anpassa skalning av ekonomiobjekt** väljer man önskad inställning för skalning och precis som i exemplet ovan så ger alternativet "Ingen skalning" att alla värden anges i SEK (om SEK är aktuell valuta):

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2880x1584%2F9dd86494e8%2Fbild-3.png%2Fm%2F&w=3840&q=75)

Dela denna artikel

Länk kopierad