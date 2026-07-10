---
title: "Importera SIE-fil"
source: "https://support.fortnox.se/produkthjalp/bokforing/importera-sie-fil"
author:
published: 2024-03-19
created: 2026-07-09
description: "I denna artikel beskriver vi vilken information som finns i SIE-filer och hur du gör för att importera dem i Fortnox program."
tags:
  - "clippings"
---
Bokföring

I denna artikel beskriver vi vilken information som finns i SIE-filer och hur du gör för att importera dem i Fortnox program.

## Vad är SIE-fil?

Kopiera länk hit

SIE-formatet är en standard framtagen för att enkelt kunna flytta bokföringsdata mellan olika bokföringssystem. Har du använt dig av ett annat program tidigare och vill föra över din bokföringsdata till Fortnox program så kan du enkelt importera en SIE-fil.

Det finns 4 olika typer av SIE-filer som kan läsas in i Fortnox, som alla innehåller olika information.

**SIE1** - Årssaldon. Innehåller årets ingående och utgående saldon för samtliga konton i kontoplanen.  
  
**SIE2** - Periodsaldon. Innehåller all information från typ 1 samt månadsvisa saldoförändringar för samtliga konton.  
  
**SIE3** - Objektsaldon. Identisk med typ 2, men saldon finns även på objektnivå, t ex kostnadsställen och projekt.  
  
**SIE4** - Transaktioner. Identisk med typ 3, men innehåller även samtliga verifikationer för räkenskapsåret. Detta är den vanligaste typen.

## Film: Importera SIE-fil i Fortnox Bokföring

Kopiera länk hit

<iframe title="Fortnox Video" allow="autoplay" src="https://player.vimeo.com/video/1156424681?&amp;chapters=0" allowfullscreen=""></iframe>

## Importera SIE-fil

Kopiera länk hit

För att importera en SIE-fil klickar du på ditt företagsnamn längst upp i programmet och väljer alternativet **Import.**

![För att importera SIE klickar du på företagsnamnet och väljer Import.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F317x460%2F10e845d78b%2Fimportera-sie1.png%2Fm%2F&w=640&q=75)

Du kan antingen läsa in SIE-filen via knappen **Läs in fil** eller genom att dra filen från din dator in till import-vyn i Fortnox.

![Klicka på Läs in fil eller dra in filen.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2451x928%2Ffcfe74ca38%2Fimportera-sie2.png%2Fm%2F&w=3840&q=75)

### Räkenskapsår

När filen är inläst får du i olika block information om vad filen innehåller och om du redan har ett räkenskapsår upplagt kommer du se hur de olika kontona och de eventuella kostnadsställena och projekten har matchats.

![När SIE-filen är inläst får du i olika block information om vad filen innehåller.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2430x470%2F363a3ad8ca%2Fimportera-sie3.png%2Fm%2F&w=3840&q=75)

Om du har ett rött kryss längst ut till höger på någon av raderna behöver du kontrollera det innan du kan importera filen. Om du öppnar upp den del där du fått ett rött kryss får du ett felmeddelande om varför det inte går att läsa in informationen. Ett exempel är om du försöker lägga upp ett projekt med samma kod som ett redan existerande projekt.

### Koppling av konton/kontoplan

När du har laddat upp filen öppnar du blocket **Konton** för att styra hur kontona och dess inställningar kommer att importeras.

Du kan välja att:

- Endast importera använda konton eller alla
- Använda benämningen på konton från SIE-filen eller den befintliga kontoplanen
- Använda SRU från SIE-filen eller den befintliga kontoplanen

Om det i filen importeras ett kontonummer som redan existerar i den befintliga kontoplanen så kommer åtgärden automatiskt att bli **Koppla**, till höger ser du då vilken benämning kontot kommer att importeras med baserat på vad du valt i inställningen ovan. Finns inte kontot i den befintliga kontoplanen så kommer **Skapa nytt** att bli åtgärden. Du kan också välja att **Ignorera** ett konto i fall du inte vill att det ska importeras.

![Välj åtgärd, Koppla, Skapa nytt eller Ignorera konto.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x865%2F9113f1ce70%2Fimportera-sie4.jpeg%2Fm%2F&w=3840&q=75)

### Lägg till momskod

För att få rätt belopp i rätt ruta i din momsrapport behöver konton ha en momskod i kontoplanen. Momskoder följer inte med i en SIE-fil, men du kan manuellt lägga in momskod på ett eller flera konton i samband med SIE-importen. Val av momskod sparas och uppdateras på rätt konton i kontoplanen för det räkenskapsår SIE-filen avser. Du behöver då inte lägga till momskoder manuellt i kontoplanen senare.

Obs! Om du importerar en SIE-fil för befintligt räkenskapsår där ett eller flera konton redan har en vald momskod i kontoplanen, kommer dessa inte synas i denna lista. Samtliga fält för momskod visas tomma. Om du inte vill lägga till eller byta momskod för ett konto, lämnar du fältet tomt.

![För att få rätt belopp i rätt ruta i din momsrapport behöver konton ha en momskod i kontoplanen.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x816%2F40453364a9%2Fimportera-sie5.jpeg%2Fm%2F&w=3840&q=75)

### Ingående balanser

I delen för ingående balanser väljer du om du vill att de konton som har en ingående balans ska uppdateras eller inte. Om du inte vill föra över de ingående balanserna i samband med SIE-importen kan du göra det vid ett senare tillfälle. Du går i så fall till **Register - Kontoplan** och klickar på verktyget **Överför balanser från föregående år** uppe till höger. Tänk på att du ska ha det räkenskapsåret som du vill överföra balanserna till öppet. I menyn längst upp till höger ser du vilket år som är öppet.

![Välj om du vill att de konton som har en ingående balans ska uppdateras eller inte.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x180%2F3db1c74f57%2Fimportera-sie6.jpeg%2Fm%2F&w=3840&q=75)

### Budget

Har du budget upplagt i en SIE-fil går det att importera den i Fortnox.

Budget definieras som “#PBUDGET 0” i SIE-filen, vilket du exempelvis kan se om du gör en SIE-export i Fortnox. När Budget finns definierad i SIE-filen får du möjlighet att välja JA/NEJ till att importera budgeten eller inte vid importen.

![Välj om SIE-filens budget ska uppdatera den budget som är kopplad till dina olika konton.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x140%2F9fed027b32%2Fimportera-sie7.jpeg%2Fm%2F&w=3840&q=75)

**Observera** att vid import av SIE-fil ska intäktskonton ha ett negativt budgetsaldo och kostnadskonton ett positivt. Detta är tvärtom mot när du manuellt lägger upp budget i Fortnox.

Vill du inte göra budgetuppdateringen i samband med importen kan du göra det vid ett senare tillfälle manuellt. Du går i så fall till **Register - Kontoplan** och söker fram det konto du vill uppdatera budgeten på.

### Verifikationsserier

Under blocket för transaktioner väljer du hur du vill att dina verifikationsserier ska kopplas och du har även möjlighet att göra ett urval på vilka verifikationer du vill ta med i importen, se nedanstående bild.

![Under Transaktioner väljer du hur verifikationsserier ska kopplas.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x647%2Fac1cf9935d%2Fimportera-sie8.jpeg%2Fm%2F&w=3840&q=75)

När alla block har en grön bock ute till höger så kan filen importeras via knappen Importera nere till höger. Vilka verifikationer som skapats framgår sedan tydligt även i behandlingshistoriken.

## Om SIE-filen köas

Kopiera länk hit

Om SIE-filen är för stor för att importeras direkt kommer den att köas. När filen importerats får du en notis uppe i programmets högra hörn.

![När filen importerats får du en notis uppe i programmets högra hörn.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x207%2Fe92c73fb8f%2Fimportera-sie9.jpeg%2Fm%2F&w=3840&q=75)

## Om importen misslyckas

Kopiera länk hit

Om du får ett felmeddelande när du importerar filen kan du behöva göra någon ändring i ditt program för att den ska kunna läsas in. För att läsa mer om eventuella felmeddelanden och lösningar på dessa, läs mer här: [Felsökningsguide - SIE-fil](https://support.fortnox.se/produkthjalp/bokforing/felsokningsguide-sie-fil)

## Ångra/ta bort en SIE-import

Kopiera länk hit

Om du efter en import av en SIE-fil märker att verifikationer har lagts in dubbelt eller felaktig SIE-fil har använts finns det möjlighet att ångra en SIE-import som genomförts. För att ångra den och radera alla verifikationer som importerats klickar du på ditt företagsnamn uppe till höger och väljer **Import**.

På sidan för SIE-Import klickar du på verktyget **Ångra SIE** längst ut till höger.

![Du kan Ångra SIE under företagsnamnet - Import.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x395%2F0b5f95f625%2Fimportera-sie10.jpeg%2Fm%2F&w=3840&q=75)

Då visas en lista över de SIE-importer som har genomförts.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1302x528%2Fa34fa14171%2Fimportera-sie11.jpeg%2Fm%2F&w=3840&q=75)

Listan informerar om datum, klockslag, filens namn, användaren som genomförde importen samt antalet verifikationer som importerades.

Det är alltid verifikationerna från den senast genomförda SIE importen som kan ångras. För att ångra, klicka på soptunnan längst till höger på raden och bekräfta att du vill radera alla verifikationer från SIE-importen.

Observera att det endast är verifikationerna som tas bort vid en ångrad/borttagen SIE-fil. Annan information som importerats behöver korrigeras eller tas bort manuellt.  
  
Vilka verifikationer som tagits bort framgår sedan tydligt även i behandlingshistoriken. Efter att du raderat den senast genomförda SIE-importen kan du på nytt klicka på *Ångra SIE* för att få möjlighet att radera den näst senaste. På så sätt har du möjlighet att steg för steg radera flera, vid olika tillfällen, importerade SIE-filer. Observera att du inte kan radera SIE-Importerade verifikationer om du har bokfört verifikationer i samma verifikationsserie efter att importen genomförts.

Dela denna artikel

Länk kopierad