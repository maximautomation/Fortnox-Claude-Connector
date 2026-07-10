---
title: "Skapa och använd Rapport-tabeller i Rapport & Analys/Koncern"
source: "https://support.fortnox.se/produkthjalp/koncern/skapa-och-anvand-rapport-tabeller-i-rapport-analys-koncern"
author:
published: 2025-06-11
created: 2026-07-09
description: "Om du har tillgång till produkten Rapport & Analys eller Koncern kan du skapa egna Rapport-tabeller som därefter kan användas i rapporter eller dashboards."
tags:
  - "clippings"
---
Koncern, Rapport & Analys

Om du har tillgång till produkten Rapport & Analys eller Koncern kan du skapa egna Rapport-tabeller som därefter kan användas i rapporter eller dashboards.

Klicka på **Ekonomi** - **Komponenter** - **Rapport-tabeller** - **Ny rapport-tabell** för att skapa en egen Rapport-tabell. Under fliken **Rapport-tabeller** hittar du även tidigare egenskapade Rapport-tabeller.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x881%2Fbf807e7faa%2Fskapa-anvand-rapport-tabeller1.png%2Fm%2F&w=3840&q=75)

När du klickar på fliken **Ny rapport-tabell** öppnas en vy där du kan välja att utgå från en befintlig rapport-tabell eller radmall, eller skapa en helt ny rapport-tabell från grunden – helt utifrån dina behov.

Se avsnitten [Hur redigerar jag en befintlig rapport-tabell](https://support.fortnox.se/produkthjalp/koncern/rapport-tabeller-hur-redigerar-jag-en-befintlig-tabell-och-sparar-den-som-en-egen) samt [Hur skapar jag en rapport-tabell från en radmall](https://support.fortnox.se/produkthjalp/koncern/rapport-tabeller-hur-skapar-man-en-tabell-fran-en-radmall) för vägledning om hur du går tillväga när du vill utgå från en befintlig rapport-tabell.

## Skapa rader

Kopiera länk hit

Vill du bygga en helt egen rapport-tabell ska du använda dig av knapparna **Ny rad, Ny kolumn** samt **Ny summering.** Börja med att klicka på **Ny rad** för att lägga till den första raden i rapport-tabellen.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1850x585%2F1ddadc05d8%2Fskapa-anvand-rapport-tabeller2.png%2Fm%2F&w=3840&q=75)

När du har klickat på **Ny rad** behöver du göra vissa inställningar för att konfigurera raden enligt dina behov.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F577x921%2F2b0f6ea2e0%2Fskapa-anvand-rapport-tabeller3.png%2Fm%2F&w=1200&q=75)

**Rubrik:** Ange vad raden ska heta.

**Formel**: I fältet **Formel** anger du den formel som ska gälla för raden. Mer information hittar du i guiden [Introduktion till formler](https://support.fortnox.se/produkthjalp/koncern/formler-introduktion-till-formler) . På radnivå kan du till exempel visa beloppet för ett specifikt bokföringskonto eller ett intervall, men även ekonomiska nyckeltal som bruttomarginal eller egna nyckeltal, såsom antal anställda.

**Tom rad:** Kryssa i detta alternativ för att bara skapa en tom rad. Detta är användbart när du vill ha en rubrik i rapport-tabellen.

**Expandera rader**: Kryssa i detta alternativ för att expandera raden på konto- eller affärsområde/dotterbolagnivå från start.

**Visa framtida data**: Om det finns data även efter det angivna slutdatumet kommer den att visas.

**Visa ofullständig data:** Visar data som systemet annars bedömer som ofullständig, exempelvis när det inte finns bokföringsdata för hela månaden som är vald.

**Välj affärsområden:** Välj om raden ska avse hela organisationen eller ett specifikt affärsområde (kostnadsställe eller projekt)

**Enhet**: Detta fält är alltid förifyllt med alternativet **Auto**, vilket innebär att systemet automatiskt väljer den enhet som passar bäst. Du kan även välja en enhet manuellt från listan nedan.

- Valuta
- %
- Ingen
- Egen (ange enheten)

**Textstil**: Textstilen kan vara Normal eller Rubrik 1.

**Extra marginal:** Välj bland följande:

- Ovanför
- Under
- Vänster (indrag)

Klicka sedan på **Lägg till** för att raden ska skapas. Alla inställningar kan ändras i efterhand genom att trycka på pennan till bredvid respektive rad.

## Skapa kolumner

Kopiera länk hit

När du är nöjd med vilka rader som finns med i rapport-tabellen kan du klicka på **Ny kolumn** för att välja vilket tidsintervall och vilken formel som ska visas för raderna.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1847x1010%2F2a5e3c0179%2Fskapa-anvand-rapport-tabeller4.png%2Fm%2F&w=3840&q=75)

När du skapar en kolumn behöver du göra vissa inställningar för att anpassa den efter rapportens innehåll och syfte.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F584x948%2Ffbd02a567b%2Fskapa-anvand-rapport-tabeller5.png%2Fm%2F&w=1200&q=75)

**Titel**: Ange rubrik för kolumnen

**Intervall och upplösning**: Intervall anger den tidsperiod som datan ska baseras på och kan vara År, Tertial, Kvartal, Månad, Vecka, Dag och Relativ. Upplösningen – alltså hur detaljerat datan ska visas – kan anges i samma perioder men får aldrig överstiga det valda intervallet. Det innebär att om intervallet är Kvartal, kan upplösningen inte vara År*.*

Om Månad väljs som upplösning kan upp till 12 kolumner skapas, beroende på var i året datan visas. För Kvartal är motsvarande maximalt 4 kolumner.

**Ackumulerat:** När alternativet **Ackumulerat** är valt visas summerad data i kolumnen.

Exempel: Om **Intervall** är satt till *År* och *Upplösning* till *Månad*, kommer ett ackumulerat val att visa det sammanlagda värdet för hela året i en enda kolumn. Utan detta val visas istället varje månads värde i varsin kolumn – totalt upp till 12 kolumner.

**Visa framtida data:** Detta alternativ väljs för att kunna visa data som ligger framåt i tiden, till exempel budgetvärden. Om det inte är valt, visas enbart data fram till det datum bokföringsinformationen sträcker sig.

**Ofullständig data**: Väljs för att kunna visa bokföringsdata för månader som inte är kompletta.

**Välj affärsområden**: Välj om kolumnen ska avse hela organisationen eller ett specifikt affärsområde (kostnadsställe eller projekt) **Kolumnformel:** Välj om kolumnen ska ha en specifik formel. Är inget angivet här så visar kolumnen utfallet som standard. Läs artikeln [Formler i kolumner](https://support.fortnox.se/produkthjalp/koncern/hur-anvands-formler-i-kolumner) för ytterligare information om vilka formler som går att använda sig av

**Enhet:** Detta fält är alltid förifyllt med alternativet **Auto**, vilket innebär att systemet automatiskt väljer den enhet som passar bäst. Du kan även välja en enhet manuellt från listan nedan.

- Valuta
- %
- Ingen
- Egen (ange enheten)

**Visas tillsammans med**: Här kan du ange om en kolumn ska kopplas samman med en annan.

**Expandera kolumner**: Välj antingen **Ingen** eller att varje affärsområde eller dotterbolag ska visas separat.

**Visa datum:** Förvald inställning som visar perioden för datan under rubriken i kolumnen

**Visa hjälptext**: En egen text kan anges som placeras som ett frågetecken till vänster om kolumnens titel

Klicka sedan på **Lägg till** för att kolumnen ska skapas. Alla inställningar kan ändras i efterhand genom att trycka på pennan ovanför respektive kolumn.

Du kan skapa hur många kolumner och rader som du vill och redigera dem i efterhand genom att klicka på redigeringspennan bredvid raden eller kolumnen.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1817x1103%2Fe0a38f726d%2Fskapa-anvand-rapport-tabeller6.png%2Fm%2F&w=3840&q=75)

## Skapa summering

Kopiera länk hit

Genom att klicka på **Ny summering** Går det att summera befintliga rader.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F583x759%2F1b3883b282%2Fskapa-anvand-rapport-tabeller7.png%2Fm%2F&w=1200&q=75)

Välj vilka rader som ska summeras. Klicka sedan på **Lägg till** för att spara summeringen.

## Flytta rad/kolumn

Kopiera länk hit

Bredvid varje rad och kolumn finns en kryssruta som du kan markera. När den är markerad kan du flytta, radera eller kopiera den aktuella raden eller kolumnen.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1826x1091%2F72fd5417f2%2Fskapa-anvand-rapport-tabeller8.png%2Fm%2F&w=3840&q=75)

## Ytterligare inställningar för rapport-tabeller

Kopiera länk hit

Uppe till höger kan du även välja vilken period och vilket affärsområde rapport-tabellen ska visa data för, genom fälten **Välj affärsområde** och **Välj sista datum i perioden**.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1919x1053%2F37b9a48bb0%2Fskapa-anvand-rapport-tabeller9.png%2Fm%2F&w=3840&q=75)

Under fliken **Inställningar** finns ytterligare alternativ för att anpassa rapport-tabellen. För mer information, läs här: [Inställningar i rapport-tabeller](https://support.fortnox.se/produkthjalp/koncern/rapport-tabeller-installningar-i-rapport-tabeller) .

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1897x747%2Fdd2d27df83%2Fskapa-anvand-rapport-tabeller10.png%2Fm%2F&w=3840&q=75)

Under fliken **Kontoanalys** får du en översikt över vilka konton som används i rapport-tabellen. För mer information, läs här: [Kontoanalys i rapport-tabeller](https://support.fortnox.se/produkthjalp/koncern/rapport-tabeller-kontoanalys-i-rapport-tabeller) [.](https://support.fortnox.se/produkthjalp/koncern/rapport-tabeller-kontoanalys-i-rapport-tabeller)

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1907x946%2F1578cdf3f1%2Fskapa-anvand-rapport-tabeller11.png%2Fm%2F&w=3840&q=75)

Klicka på **Spara** när du är färdig med rapport-tabellen. Den kommer sedan finnas tillgänglig i rullistan som hittas genom att klicka på **Lägg till element - Rapport-tabeller- Välj rapport-tabell** när du skapar egna rapporter eller dashboards.

Dela denna artikel

Länk kopierad