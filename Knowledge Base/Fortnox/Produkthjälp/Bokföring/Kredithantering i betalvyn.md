---
title: "Kredithantering i betalvyn"
source: "https://support.fortnox.se/produkthjalp/bokforing/betalningar-kredithantering"
author:
published: 2024-09-06
created: 2026-07-09
description: "Kredithantering i betalvyn"
tags:
  - "clippings"
---
## Betalningar - Kredithantering

Bokföring

## Betalningar - Kreditfakturor

Kopiera länk hit

En kreditfaktura kan även kallas för kreditnota, omvänd faktura eller minusfaktura. Den här typen av fakturor skickas vanligtvis ut när den ursprungliga fakturan är felaktig eller behöver justeras. Till exempel om en kund köpt en produkt som visar sig vara trasig eller felaktig, och som den därför inte ska betala för. Genomfördes köpet mot faktura kan utställande företag skicka en kreditfaktura så att kunden får ett tillgodohavande, som kan vara på delar av- eller hela beloppet på originalfakturan.

I och med det nya standardiserade filformatet, ISO20022, har arbetssättet kring hanteringen av kreditfakturor och dess regler i betalfil förändrats. Betalningen som hanteras av banken kommer kräva ett positivt belopp och själva kvitteringen kommer därmed behöva genomföras i Fortnox. Det medför att kreditfakturor inte kommer kunna skickas till banken för så kallad bevakning, när filformatet ISO20022 används.

Men du kan vara lugn, Fortnox hjälper dig med vilka kreditfakturor som kan nyttjas. Dessutom håller systemet koll på vilka regler som gäller för din bank.

## Regler för kredithantering i betalfil

Kopiera länk hit

När det gäller att nyttja kreditfakturor i betalfiler finns det regler att förhålla sig till. Reglerna kan variera beroende på bank och betaluppgifter men handlar generellt sätt om att:

- Max nyttja 5 kreditfakturor per debetfaktura
- Den totala summan av fakturorna måste vara positiv
- Debet- och kreditfakturorna måste ha samma betaldatum

Dessa regler hjälper Fortnox till att hålla reda på. Men du kan läsa mer om de här:  
[Kreditfakturor i betalfil](https://support.fortnox.se/produkthjalp/bankkopplingar/kreditfakturor-i-betalfil)

## Nyttja kreditfakturor i betalfil, Meny-Betalningar

Kopiera länk hit

Under **Meny - Betalningar** introduceras en smidigare kredithantering. För att nyttja kreditfakturor väljer du först de fakturor med positiva belopp du vill hantera i **Att betala** -listan. Därefter klickar du på **Fortsätt** för att ta dig till **checkouten**. I checkoutenfinns alternativet **Nyttja** **kreditfakturor** längst ner till höger i sammanfattningen.

![I checkouten finns alternativet Nyttja kreditfakturor längst ner till höger i sammanfattningen.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1504x809%2Ffa0d29f1d4%2Fkredithantering1.png%2Fm%2F&w=3840&q=75)

När du klickat på **Nyttja kreditfakturor** presenteras kreditfakturor du kan nyttja baserat på de leverantörsfakturor du valt i det tidigare steget i Att betala-listan. Fortnox tar hänsyn till de regler som finns och automatiskt föreslår vilka kreditfakturor som kan användas, för att underlätta din kredithantering.

När du har valt de kreditfakturor du vill nyttja, eller är nöjd med de som Fortnox har föreslagit, klickar du på **Lägg till** som finns längst ner till höger i rutan. Då kommer kreditfakturornas totala summa att visas i sammanfattningen, och beloppet att betala justeras automatiskt.

![När du har valt de kreditfakturor du vill nyttja, eller är nöjd med de som Fortnox har föreslagit, klickar du på Lägg till.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1420x752%2Fde3113584e%2Fkredithantering2.png%2Fm%2F&w=3840&q=75) ![Kreditfakturornas totala summa visas i sammanfattningen, och beloppet att betala justeras automatiskt.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1500x808%2F7a5da832c1%2Fkredithantering3.png%2Fm%2F&w=3840&q=75)

## Återrapportering

Kopiera länk hit

När dina betalningar väl har blivit genomförda på din bank, så kommer de att återrapporteras till ditt Fortnox. Via funktionen **Bokföring från kontoutdrag** kommer Fortnox automatiskt bokföra det belopp som nyttjats via kreditfakturorna samt det belopp som har betalats. Har hela beloppet på en kreditfaktura nyttjats, så kommer den att bli bokförd som slutbetald. Har ett mindre belopp nyttjats av kreditfakturan, så bokförs det belopp som har nyttjats och kreditfakturan får ett kvarvarande saldo som status **Obetald**, vilket du sedan kommer att kunna nyttja vid ny betalning.

Du kan läsa mer om den automatiska bokföringen här: [Bokföring från kontoutdrag](https://support.fortnox.se/produkthjalp/bokforing/bokforing-fran-kontoutdrag)

Dela denna artikel

Länk kopierad