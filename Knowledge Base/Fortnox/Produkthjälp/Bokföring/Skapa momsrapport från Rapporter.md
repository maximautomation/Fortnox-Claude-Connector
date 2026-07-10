---
title: "Skapa momsrapport från Rapporter"
source: "https://support.fortnox.se/produkthjalp/bokforing/skapa-momsrapport-fran-rapporter"
author:
published: 2024-03-19
created: 2026-07-09
description: "I denna artikel går vi igenom hur du skapar en momsrapport från  Rapporter  i Fortnox."
tags:
  - "clippings"
---
Bokföring

Det är också möjligt att skapa en momsrapport från vyn **Meny** - **Bokföring** - **Moms** om du föredrar det. Här kan du läsa mer om hur du arbetar med momsredovisning i Fortnox Bokföring istället: [Skapa momsrapport från Bokföring](https://support.fortnox.se/produkthjalp/bokforing/momsredovisning)

## Inställningar - Momskoder

Kopiera länk hit

Vilket/vilka belopp som läggs på varje ruta på din momsrapport beror på vilken momskod som du har satt på dina konton i kontoplanen. Så här blir redovisningen på en skattedeklaration (baserat på varje momskod):

![Moms att deklarera för, i Skattedeklarationen.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F780x883%2F6f419e5aaf%2Fskapa-momsrapport3.png%2Fm%2F&w=1920&q=75)

Till exempel kommer alla konton som har momskoden " **I** (48)" att summeras och visas på rad 48 i momsrapporten för den valda perioden.

Du ser och redigerar momskoderna i din kontoplan under **Register** - **Kontoplan och typ av köp**.

Om något ser fel ut i momsrapporten kan det bero på att momskoderna inte är rätt inställda i kontoplanen. För hjälp med att kontrollera detta, följ stegen under rubriken " *Momsrapporten visar fel saldo* " i vår guide: [Felsökningsguide - Att felsöka en momsrapport](https://support.fortnox.se/produkthjalp/bokforing/felsokningsguide-att-felsoka-en-momsrapport#momsrapporten-visar-fel-saldo)

För fler inställningar avseende moms för kund och leverantörsfakturor i systemet kan du läsa mer här: [Inställningar - Moms](https://support.fortnox.se/produkthjalp/bokforing/installningar-moms)

![Ta ut momsrapporten under Rapporter - Momsrapport.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1901x819%2Fc6409ce0d3%2Fskapa-momsrapport1.jpeg%2Fm%2F&w=3840&q=75)

## Öppna momsrapport

Kopiera länk hit

För att öppna en momsrapport från rapporter börjar du med att klicka på **Rapporter** - **Momsrapport** , välj därefter intervallet för den period du vill ta ut momrapporten för.

Den period du väljer kommer att sparas och nästa gång du tar ut din momsrapport kommer nästkommande period föreslås för din moms.

![Välj intervall för den period du vill ta ut momrapporten för.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F528x247%2F5e782deac7%2Fskapa-momsrapport2.png%2Fm%2F&w=1080&q=75)

Om du har ett brutet räkenskapsår och rapporterar momsen kvartalsvis kommer du behöva ta ut två momsrapporter, en för varje räkenskapsår. Om ditt räkenskapsår slutar 31 augusti tar du först ut en momsrapport för juli och augusti, och i nästa räkenskapsår tar du ut en momsrapport i september. Detta kommer då att generera 2 momsverifikationer, en i varje räkenskapsår. Momsrapporterna behöver sedan summeras för att manuellt registreras hos Skatteverket då en eSKD-fil för perioden inte kan tas ut.

För att få ut och bokföra en sammanhängande rapport för hela kvartalet mellan räkenskapsåren kan du göra detta om du skapa och bokföra momsrapporten från momsvyn under, **Meny** - **Bokföring** - **Moms** istället.

Läs mer om hur denna momsvyn funkar här: [Skapa momsrapport från Bokföring](https://support.fortnox.se/produkthjalp/bokforing/momsredovisning)

## Avvikelserapport

Kopiera länk hit

När du öppnat momsrapporten via Rapporter hittar du länken **Kör momsavvikelserapport** längst ner på sidan. Klicka där för att visa eventuella avvikelser.

För att återgå till momsrapporten efter att ha granskat avvikelserna, kan du högerklicka på skärmen och välja “Bakåt”.

Momsavvikelserapporten visar potentiella avvikelser i momsrapporteringen enligt två kriterier:

1. Om en post i ett verifikat har momskod MP1, MP2, MP3 eller HFS men saknar post med motsvarande momskod U1, U2 eller U3.
2. Om ett verifikat har motsvarande MP och U poster men dess värde skiljer sig från aktuell momssats +/- 1%-enhet.

Det kan förekomma avvikelser som enbart visas för att de ligger utanför systemets fördefinierade kriterier. Om du bedömer att dessa avvikelser är korrekt bokförda kan du bortse från dem och fortsätta med att godkänna och bokföra momsrapporten.

## Bokföra momsrapporten

Kopiera länk hit

För att bokföra momsrapporten behöver du godkänna den. När du öppnar momsrapporten visas ett separat fönster med frågan:

”Vill du godkänna momsrapporten och registrera bokföringsunderlaget?”

Väljer du Ja kommer rapporten att bokföras och bokföringsunderlaget registreras automatiskt.

![Du får frågan Vill du godkänna momsrapporten och registrera bokföringsunderlaget?](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F494x233%2F37c759bcad%2Fskapa-momsrapport4.png%2Fm%2F&w=1080&q=75)

Du kan alltid öppna upp momsrapporten på nytt för att få frågan igen om du vill bokföra den senare.

## Skapa eSKD-fil

Kopiera länk hit

Efter att du bokfört momsrapporten får du möjlighet att skapa en eSKD-fil som du sedan kan ladda upp på Skatteverkets hemsida. För att göra detta behöver du ett BankID eller en giltig e-legitimation.

Har du missat att ta ut eSKD-filen för perioden så kan du gå igenom alla stegen en gång till för samma period. Om inga nya ändringar har tillkommit i perioden så kommer ingen ny verifikation bokföras även om du svarar **Ja** på frågan om att registrera bokföringsunderlaget.

![Efter att du bokfört momsrapporten får du möjlighet att skapa en eSKD-fil som du sedan kan ladda upp på Skatteverkets hemsida.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F490x226%2F887c6d8113%2Fskapa-momsrapport5.png%2Fm%2F&w=1080&q=75)

## Korrigera redan bokförd momsrapport

Kopiera länk hit

Om du behöver bokföra om en redan bokförd momsrapport finns två alternativ:

- Radera det senaste verifikatet manuellt
- Bokföra om momsrapporten direkt, vilket skapar en ändringsverifikation automatiskt

Läs mer om hur det fungerar här: [Korrigera redan bokförd momsrapport](https://support.fortnox.se/produkthjalp/bokforing/felsokningsguide-att-felsoka-en-momsrapport#korrigera-redan-bokford-momsrapport)

## Felsökning av momsrapport

Kopiera länk hit

Om du tagit ut en momsrapport som inte stämmer, läs här:

[Felsökningsguide - Att felsöka en momsrapport](https://support.fortnox.se/produkthjalp/bokforing/felsokningsguide-att-felsoka-en-momsrapport)

## Moms på frakt och fakturaavgifter

Kopiera länk hit

Tänk också på att momssatsen för frakt- och fakturaavgiften på fakturan/fakturorna blir den momssats som du har på flest antal artiklar på din faktura. Ifall du inte vill att det ska bli på det viset så kan du lägga din moms för dessa avgifter som artiklar på fakturan istället. Detta är viktigt för enligt mervärdesskattelagen ska beskattningsunderlaget för fraktkostnad och fakturaavgift fördelas på beskattningsunderlaget för respektive vara. Det innebär att du behöver fördela frakt och fakturaavgifter på olika momssatser.

Rekommendationen blir därför att ta bort frakt och fakturaavgift från fakturans fot och istället lägga upp dem som flera olika artikelrader med olika momssatser. Fördelningen görs utifrån en relation mellan beskattningsunderlaget för respektive vara och det totala beskattningsunderlaget för varorna.

## Film: momsrapport i Fortnox Bokföring

Kopiera länk hit

<iframe title="Fortnox Video" allow="autoplay" src="https://player.vimeo.com/video/584874135?&amp;chapters=0" allowfullscreen=""></iframe>

Dela denna artikel

Länk kopierad