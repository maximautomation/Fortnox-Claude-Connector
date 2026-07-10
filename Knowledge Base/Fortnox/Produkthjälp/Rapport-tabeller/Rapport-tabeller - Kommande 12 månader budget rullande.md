---
title: "Rapport-tabeller - Kommande 12 månader budget rullande"
source: "https://support.fortnox.se/produkthjalp/koncern/rapport-tabeller-kommande-12-manader-budget-rullande"
author:
published: 2024-04-12
created: 2026-07-09
description: "Ackumulerat  För att se kommande 12 månaders budget ackumulerat i en kolumn rullande, alltså oberoende av räkenskapsår, ställer du in kolumnen enligt bilden:"
tags:
  - "clippings"
---
Koncern, Rapport & Analys

**Ackumulerat**  
För att se kommande 12 månaders budget ackumulerat i en kolumn rullande, alltså oberoende av räkenskapsår, ställer du in kolumnen enligt bilden:

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2457x1277%2F59c27409c3%2Fbudget12bild1.png%2Fm%2F&w=3840&q=75)

Alltså:

- Intervall: Relativ
- Upplösning: Månad
- Från: 1 Månad
- Till: +12 Månader
- Kolumnformel: Egen: SumLast(Budget(RowFormula),12)

Detta kräver att det finns en aktiv budget för de månader som ska täckas in. Det går självfallet att öka antalet månader, men då behöver man ändra både Till-värdet och i Kolumnformeln.

**Månadsvisa kolumner**  
För att få ut samma värden men månad för månad så anger du samma inställningar men utan SumLast() i kolumnformeln, alltså:

- Kolumnformel: Egen: Budget(RowFormula)

**Resultat**  
Så här ser en tabell ut med bägge dessa kolumninställningar som visar budget från första juli 2021 till sista juni 2022:

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2070x728%2F9e5356d84f%2Fbild-2.png%2Fm%2F&w=3840&q=75)

Dela denna artikel

Länk kopierad