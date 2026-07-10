---
title: "Använd testpersonnummer med Bank-id"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/anvandtestpersonnummermedbankid.4.17b07b1e194a69bf276866.html"
author:
published:
created: 2026-07-09
description: "Genom att skapa en användare med ett testpersonnummer kan du testa att logga in på samma sätt som en privatperson skulle göra med e-legitimation. Följ guiden för att anropa det API där din testperson finns registrerad."
tags:
  - "clippings"
---
Genom att skapa en användare med ett personnummer anpassat för testning (testpersonnummer) kan du testa att logga in på samma sätt som en privatperson skulle göra med e-legitimation.

Du behöver både installera appen Bank-id i din miljö och skapa en så kallad testperson med ett testpersonnummer. Därefter kan du anropa det API där din testperson finns registrerad.

## Innan du börjar

Börja med att hämta appen Bank-id. Den hittar du på Bank-id:s webbplats (Demo bank). Följ de instruktioner som finns där för att installera appen.

I demobanken kan du testa:

- Verifiering av digitalt ID-kort.
- Signering för eID-tjänsten, med en egen beskrivande text.

[Demo Bank Länk till annan webbplats.](https://demo.bankid.com/)

[Bank-id developers-sajt Länk till annan webbplats.](https://developers.bankid.com/test-portal/test-information)

## Skapa din testperson

Grundläggande steg innan du börjar:

- Logga in på Bank-id:s demo bank.
- Klicka på **Production Bank-id**.
- Scanna qr-koden och logga in med ditt personliga Bank-id.

Skapa en testperson för din utvecklingsmiljö:

- Klicka på **Bank-id on file**.
- Fyll i personnummer och namn på din testperson. Du hittar testpersonnummer som öppna data på vår utvecklarportal. Vad testpersonen ska heta i för- och efternamn bestämmer du själv. Klicka på **Issue**.

[Testpersonnummer Länk till annan webbplats.](https://www7.skatteverket.se/portal/apier-och-oppna-data/utvecklarportalen/oppetdata/Test%C2%AD%C2%ADpersonnummer)

- På nästa sida behöver du antingen välja att ladda ner appen Bank-id eller fortsätta utan att ladda ner den. Välj att ladda ner appen om du inte redan gjort det.
- Klicka på **Continue** och **Start**.
- Fyll i lösenord.

Nu är testpersonen kopplad till Bank-id på fil.

## Gör ett anrop

Du behöver en access token för att kunna anropa det API där din testperson finns registrerad.

- Gör ett anrop mot auktorisationsservern med Client ID och Client secret. När du gjort det ska du ha fått en url i ditt anrop. Kopiera url:en och klistra in den i adressfältet på din webbläsare.
- Webbläsaren tar dig till en ny sida och en ny adress (url). I den nya url:en finns en kod som kommer synas efter ”code=”. Kopiera endast koden.
- Klistra sedan in koden i ditt nästa anrop där du hämtar ut en token under parametern "code".
- Skicka iväg anropet som innehåller den inklistrade koden. Du får tillbaka en access token som du sedan använder för att hämta information som är kopplad till din testanvändare.

Läs mer om testpersonnummer och om hur du använder säkerhetsflödet Authorization Code Grant med e-legitimation:

[Testpersonnummer som öppen data](https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraoppnadata/testpersonnummersomoppendata.4.5b35a6251761e6914202df9.html)

[Authorization Code Grant (ACG)](https://www.skatteverket.se/omoss/digitalasamarbeten/borjaanvandaapier/authorizationcodegrantacg.4.96cca41179bad4b1aa8f05.html)