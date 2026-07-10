---
title: "Att byta kontoplan"
source: "https://support.fortnox.se/produkthjalp/bokforing/att-byta-kontoplan"
author:
published: 2024-04-15
created: 2026-07-09
description: "I samband med att du skapar ett nytt räkenskapsår har du möjlighet att byta till en annan kontoplan."
tags:
  - "clippings"
---
Bokföring

I samband med att du skapar ett nytt räkenskapsår har du möjlighet att byta till en annan kontoplan.

## Byta kontoplan i samband med nytt räkenskapsår

Kopiera länk hit

För att skapa ett nytt räkenskapsår klickar du på ditt nuvarande räkenskapsår som du hittar uppe i programmets högra hörn. Välj sedan **Hantera räkenskapsår**. Alternativt går du till **Inställningar**, väljer **Bokföring** och sedan **Räkenskapsår**.

Du kommer då till inställningarna där du klickar på knappen **Skapa nytt**.

![Klicka på ditt räkenskapsår, välj Hantera räkenskapsår och Skapa nytt.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1003x213%2F1d31c2e26f%2Fbyta-kontoplan2.png%2Fm%2F&w=2048&q=75)

När du skapar ditt nya räkenskapsår väljer du vilken kontoplan du vill använda, du får även möjlighet att välja om du vill använda kontobenämningen från den föregående kontoplanen eller den nya.

![Välj kontoplan för det nya räkenskapsåret.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1103x351%2Fa5d56e4a8b%2Fbyta-kontoplan1.png%2Fm%2F&w=3840&q=75)

Väljer du att inte använda samma kontoplan som föregående år är det ett par saker du bör tänka på:

- Om den nya kontoplanen innehåller andra intäkts- och/eller kostnadskonton än föregående räkenskapsår så kommer du inte att kunna jämföra **Period** mot **Period fg år** i en resultatrapport. Värdena kommer inte att stämma överens då det är andra konton som har använts. Vill du jämföra behöver du istället skriva ut en resultatrapport för respektive år och jämföra kolumnen **Period**.
![Om det är andra intäkts- och/eller kostnadskonton än föregående räkenskapsår så kommer du inte att kunna jämföra Period mot Period fg år i en resultatrapport.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1900x798%2F397c899001%2Fbyta-kontoplan4.png%2Fm%2F&w=3840&q=75)
- När du sparar det nya räkenskapsåret kan du välja att de ingående balanserna ska föras över med automatik, det innebär att programmet för över den utgående balansen från ett konto i föregående år till motsvarande kontos ingående balans i det nya räkenskapsåret.  
	Om du väljer att använda dig av en ny kontoplan kan det vara så att vissa kontonummer inte har samma betydelse. I sådana fall ska du alltså inte välja att föra över de ingående balanserna med automatik. Du får istället ange det ingående saldot manuellt under **Register - Kontoplan** på dina nya kontonummer. I kolumnen för **Ingående balans** skriver du själv in hur mycket den ingående balansen är för respektive konto.
![I kolumnen för Ingående balans skriver du själv in hur mycket den ingående balansen är för respektive konto.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2410x533%2Fff5fee43d4%2Fbyta-kontoplan5.png%2Fm%2F&w=3840&q=75)
- Om du i den kontoplanen du byter till har ett annat kontonummer för kundfordringar och/eller leverantörsskulder samtidigt som du har obetalda fakturor, innebär det att du kommer att behöva byta konto på verifikationerna som skapas när du bokför en betalning på dessa fakturor. Detta eftersom programmet kommer att använda det nya kontot man har lagt till i inställningen **Förvalda konton** för kundfordringar/leverantörsskulder när betalningen bokförs.  
	Korrigera fordrings-/skuldkonto genom att skapa ett manuellt verifikat på samma datum som betalningsverifikatet och vänd bokningen från det nya kontot till kontot som användes när fakturan bokfördes.  
	  
	Observera att du enbart behöver göra denna justering på de betalningsverifikationer som tillhör de fakturor som var obetalda när du bytte kontoplan.
![Korrigera fordrings-/skuldkonto i ett manuellt verifikat.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1262x744%2Fc13d36d818%2Fbyta-kontoplan6.png%2Fm%2F&w=3840&q=75)
- När du skapat det nya året bör du gå igenom följande inställningar för att kontrollera så att rätt konton används enligt den nya kontoplanen: Automatkontering, Avvikelser/bortskrivningar, Betalsätt och betalningsvillkor, Förvalda konton samt Konteringsmallar.

## Importera kontoplan med SIE-fil

Kopiera länk hit

Du kan importera kontoplan i samband med att du importerar en SIE-fil. Klicka på ditt företagsnamn uppe i högra hörnet och välj **Import**.  
  
Finns det redan räkenskapsår i abonnemanget kan du komplettera den tidigare kontoplanen med fler kontonummer eller byta benämning på befintliga konton.

Skapas räkenskapsåret i samband med att filen importeras kommer kontoplanen hämtas från föregående räkenskapsår och kompletteras av filens konton enligt ovan.

I de fall det inte finns något räkenskapsår att hämta föregående års kontoplan från, kommer kontoplanen endast att omfattas av de konton som finns i SIE-filen.

När du har laddat upp filen öppnar du blocket **Konton** för att styra hur kontona och dess inställningar kommer att importeras. Du kan välja att:

- Endast importera använda konton eller alla
- Använda benämningen på konton från SIE-filen eller den befintliga kontoplanen
- Använda SRU från SIE-filen eller den befintliga kontoplanen

Om det i filen importeras ett kontonummer som redan existerar i den befintliga kontoplanen så kommer åtgärden automatiskt att bli **Koppla**, till höger ser du då vilken benämning kontot kommer att importeras med baserat på vad du valt i inställningen ovan. Finns inte kontot i den befintliga kontoplanen så kommer **Skapa nytt** att bli åtgärden. Du kan också välja att **Ignorera** ett konto i fall du inte vill att det ska importeras.

![Välj åtgärder för de konton som importeras.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2441x1045%2Fc18a0677e8%2Fbyta-kontoplan7.png%2Fm%2F&w=3840&q=75)

I blocket **Ingående balanser** får du välja om balanserna från SIE-filen ska importeras och appliceras eller inte för det räkenskapsår du importerar.

Avsluta med att klicka på **Importera**.

Dela denna artikel

Länk kopierad