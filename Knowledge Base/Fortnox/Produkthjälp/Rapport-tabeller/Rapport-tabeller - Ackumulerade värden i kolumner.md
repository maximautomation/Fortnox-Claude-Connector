---
title: "Rapport-tabeller - Ackumulerade värden i kolumner"
source: "https://support.fortnox.se/produkthjalp/koncern/rapport-tabeller-ackumulerade-varden-i-kolumner"
author:
published: 2024-04-12
created: 2026-07-09
description: "Börja med att klicka på  Ekonomi - Komponenter  och sedan på  Ny rapport-tabell  eller välj befintlig tabell."
tags:
  - "clippings"
---
Koncern, Rapport & Analys

Börja med att klicka på **Ekonomi - Komponenter** och sedan på **Ny rapport-tabell** eller välj befintlig tabell.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2272x804%2F0f929800c0%2Fackkolumn1.png%2Fm%2F&w=3840&q=75)

Det finns några olika sätt att skapa en kolumn med ackumulerade värden, här är några vanliga exempel:

1. Kolumn med ackumulerat utfall till rapportdatum
2. Kolumn med ackumulerad budget eller prognos till räkenskapsårets slut
3. Kolumn med utfall till rapportdatum och sedan budget eller prognos till räkenskapsårets slut
4. Rullande ackumulerat utfall oberoende av räkenskapsår
5. Diff mellan budget och budget+utfall till årets slut.

Du kan antingen redigera en kolumn, alternativt skapa en helt ny kolumn. För att redigera en kolumn, klicka på pennan över kolumnen du vill ändra. För att skapa en ny kolumn trycker du på knappen **Ny kolumn**.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2269x1263%2F204f97fafb%2Fackkolumn2.png%2Fm%2F&w=3840&q=75)

1\. Kolumn med ackumulerat utfall till rapportdatum.

Ange dessa inställningar i kolumnen för att månadsvis få ut ackumulerat utfall från raden:

- Intervall: År
- Upplösning: Månad
- Klicka i **Ackumulerat**

*Att klicka i* ***Ackumulerat*** *motsvaras av kolumnformeln Ack(Rowformula).*

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F535x829%2Fe3b8619166%2Fackkolumn3.png%2Fm%2F&w=1080&q=75)

2\. Kolumn med ackumulerad budget eller prognos till räkenskapsårets slut.

Ange dessa inställningar för Budget till årets slut:

- Intervall: År
- Upplösning: Månad
- Klicka i **Ackumulerat**
- Klicka i **Visa framtida data**
- Välj Kolumnformel: Budget
![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F535x830%2Fbbdca57ee1%2Fackkolumn4.png%2Fm%2F&w=1080&q=75)

Ange dessa inställningar för Prognos (som inte tar hänsyn till utfall utan bara visar inläst data för den gällande aktiva prognosen) till årets slut:

- Intervall: År
- Upplösning: Månad
- Klicka i **Ackumulerat**
- Klicka i **Visa framtida data**
- Välj Kolumnformel: Budget
- Välj Budget: Prognos
![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F537x831%2Fd1b2c9ea7f%2Fackkolumn5.png%2Fm%2F&w=1080&q=75)

3\. Kolumn med utfall till rapportdatum och sedan budget eller prognos till räkenskapsårets slut.

Kolumnformel: Prognos visar utfall till rapportdatum och sedan prognos-data om det finns en prognos, annars budget-data.

Om det bara finns en aktiv budget (men inte en prognos) för räkenskapsåret ställer du in så här:

- Intervall: År
- Upplösning: Månad
- Klicka i **Ackumulerat**
- Klicka i **Visa framtida data**
- Välj Kolumnformel: Prognos
![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F537x830%2F11cfa63da3%2Fackkolumn6.png%2Fm%2F&w=1080&q=75)

Om det finns både en aktiv budget och en prognos för räkenskapsåret ställer du in likadant som ovan om du vill ha utfall till rapportdatum + prognosdata, men om du vill ha utfall till rapportdatum + budgetdata ställer du in så här:

- Intervall: År
- Upplösning: Månad
- Klicka i Ackumulerat
- Klicka i Visa framtida data
- Välj Kolumnformel: Prognos
- Välj Budget: Aktiv
![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F534x831%2F20b66b2435%2Fackkolumn7.png%2Fm%2F&w=1080&q=75)

4\. Rullande ackumulerat utfall oberoende av räkenskapsår.

Ställ in så här:

- Intervall: Månad
- Upplösning: Månad
- Välj: Kolumnformel: Egen
- Ange kolumnformel: SumLast(Rowformula,12,1)

Vill man visa rullande snitt anger man denna kolumnformel istället: SumLast(RowFormula,12,1)/12

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F535x889%2F9b72a4a24e%2Fackkolumn8.png%2Fm%2F&w=1080&q=75)

5\. Diff mellan budget och budget+utfall till årets slut.

Om man har en kolumn med ackumulerad budget för innevarande räkenskapsår en kolumn med prognos som visar utfall till rapportdatum och sedan budgetdata ackumulerat till årets slut så kan man ange dessa inställningar för att se vad som är budgeterat minus vad som är utfall+budget:

- Intervall: Månad
- Upplösning: Månad
- Klicka i “Visa framtida data”
- Kolumnformel: Egen
- Kolumnformel: Ack(Budget(RowFormula))-Ack(Forecast(RowFormula,@active))
![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F541x896%2F8ecae8d6d9%2Fackkolumn9.png%2Fm%2F&w=1200&q=75)

Dela denna artikel

Länk kopierad