---
title: "Ny moms på mat från 1 april 2026"
source: "https://support.fortnox.se/produkthjalp/bokforing/ny-moms-pa-mat-fran-1-april-2026#2-justera-regelverk-och-mallar"
author:
published: 2026-03-16
created: 2026-07-09
description: "Gäller från 1 april 2026. Från och med den 1 april 2026 sänks momsen på livsmedel från  12 % till 6 % ."
tags:
  - "clippings"
---
Bokföring

Notera att momsen för restaurang- och cateringtjänster kvarstår på **12 %** (äter du på restaurang gäller 12% moms, tar du med dig maten hem gäller 6% moms). För att din bokföring ska bli korrekt från dag ett kan du behöva se över några inställningar.

***Tips:*** *Är du osäker på om din verksamhet säljer en vara (6 %) eller en tjänst (12 %)? Dubbelkolla alltid de senaste definitionerna hos* [Skatteverket](https://skatteverket.se/) *.*

## 1\. Uppdatera eller skapa nya artiklar

Kopiera länk hit

Arbetar du med artiklar är det viktigt att du har rätt försäljningskonto angivet på de artiklar som påverkas av den sänkta momsen.

Det finns några olika metoder du kan välja på för att korrigera detta:

**Skapa nya:**  
Vi rekommenderar att skapa nya artiklar för att ha en tydlig historik. Såhär gör du:

1. Gå in på en befintlig artikel du vill uppdatera.
2. Klicka på **kopiera artikeln**.
3. Längst ner på den nya artikeln finner du B **okföringsuppgifter**, där finns fältet **Försäljning**.
4. I fältet **Försäljning** anger du ett försäljningskonto som avser 6% moms.
5. Spara.

**Uppdatera befintliga:**  
Om du väljer att ändra i befintliga artiklar istället för att skapa ny, gör detta tidigast den 1 april för att inte påverka mars månads försäljning. Såhär gör du:

1. Gå in på en befintlig artikel du vill uppdatera.
2. Längst ner inne på artikeln finner du **Bokföringsuppgifter**, där finns fältet **Försäljning**.
3. I fältet **Försäljning** anger du ett försäljningskonto som avser 6% moms.
4. Spara.

*Observera att försäljningskontot behöver bytas tillbaka efter tidsbegränsningen om du valt att uppdatera en befintlig artikel.*

**Massuppdatera:**  
Om du har ett stort antal artiklar som behöver justeras är det smidigast att använda Fortnox importfunktion. Genom att arbeta i en Excel-fil kan du snabbt skapa nya artiklar eller uppdatera försäljningskonton på befintliga artiklar i en enda import.

**Läs mer här:** [Import av artikelregister](https://support.fortnox.se/produkthjalp/fakturering/import-av-artikelregister)

## 2\. Justera regelverk och mallar

Kopiera länk hit

Om du använder automatiseringar behöver dessa bokföringskonton också bytas ut för att undvika differenser.

### Arbetar du med Transaktioner:

**Regelverk - inbetalningar**

1. Gå till **Meny > Transaktioner > Regelverk**.
2. Klicka på en regel som innefattar försäljning av livsmedel.
3. Klicka på **Lägg till fler motkonton**.
4. Klicka på papperskorgen för de försäljnings- och momskonton som avser 12% moms.
5. Lägg därefter till nya bokföringskonton som avser 6% moms.
6. Ange rätt procentuell fördelning för 6%.
7. Avsluta med att **Spara**.

**Regelverk - utbetalningar**

1. Gå till **Meny > Transaktioner > Regelverk**.
2. Klicka på en regel som innefattar inköp av livsmedel.
3. Klicka på **Lägg till fler motkonton**.
4. Klicka på procentfördelningen på momskonton och ändra från 12% till 6%.
5. Avsluta med att **Spara**.

### Arbetar du med konteringsmall:

**Konteringsmall - inbetalning**

1. Gå till **kugghjulet (Inställningar) > Bokföring > Konteringsmallar**.
2. Klicka på en konteringsmall som innefattar försäljning av livsmedel.
3. Byt ut bokföringskontona som avser 12% moms till 6% moms.
4. Justera formen så att 6% moms beräknas istället för 12%.
5. Avsluta med att **Spara**.

**Konteringsmall - utbetalningar**

1. Gå till **kugghjulet (Inställningar) > Bokföring > Konteringsmallar**.
2. Klicka på en konteringsmall som innefattar inköp av livsmedel.
3. Justera formeln så momsen beräknas som 6% moms istället för 12%.
4. Avsluta med att **Spara**.

### Arbetar du med automatkontering:

**Automatkontering - inbetalning**

1. Gå till **kugghjulet (Inställningar) > Bokföring > Automatkontering**.
2. Klicka på en automatkontering som innefattar försäljning av livsmedel.
3. Byt ut bokföringskontona som avser 12% moms till 6% moms.
4. Justera procentsatsen så 6% moms beräknas istället för 12%.
5. Avsluta med att **Spara**.

**Automatkontering - utbetalningar**

1. Gå till **kugghjulet (Inställningar) > Bokföring > Konteringsmallar**.
2. Klicka på en automatkontering som innefattar inköp av livsmedel.
3. Justera procentsatsen så 6% moms beräknas istället för 12%.
4. Avsluta med att **Spara**.

## 3\. Kontrollera dina integrationer

Kopiera länk hit

Om du använder ett externt kassasystem, en webbshop eller ett annat försystem som skickar data till Fortnox är det viktigt att ändringen görs där också. Behöver du hjälp med detta, kontaktar din integratör.

Flera av våra partners inom kassasystem har anpassat sina system och gränssnitt för att underlätta hanteringen.

För alla företag som kör [Kassacentralen](https://www.fortnox.se/integrationer/integration/kassacentralen-i-skane-ab/truepos-by-kassacentralen) väljer du Avhämtningsfunktionen så ändras automatisk momssatsen i TruePos, och följer med till bokföringen i [Fortnox.https://www.kassacentralen.se/matmoms/](https://www.kassacentralen.se/matmoms/)

Även kassalösningen [Yabie](https://www.fortnox.se/integrationer/integration/yabie-ab/yabie) hanterar momssatsen direkt i kassan beroende på om det är ett takeaway-köp eller inte. Transaktionerna bokförs sedan korrekt i Fortnox — utan manuella justeringar, utan merarbete.

Dela denna artikel

Länk kopierad