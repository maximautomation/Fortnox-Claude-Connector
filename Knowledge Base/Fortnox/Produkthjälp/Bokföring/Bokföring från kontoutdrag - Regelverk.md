---
title: "Bokföring från kontoutdrag - Regelverk"
source: "https://support.fortnox.se/produkthjalp/bokforing/bokforing-fran-kontoutdrag-regelverk"
author:
published: 2024-03-19
created: 2026-07-09
description: "För en automatiserad och effektiv hantering av de transaktioner som inte matchar med en faktura eller befintligt verifikat, rekommenderar vi dig att skapa regelverk. Ett regelverk innebär att du kan skapa förutsättningar för hur transaktioner ska hanteras och bokföras med hjälp av olika parametrar, gränser och konton."
tags:
  - "clippings"
---
Bokföring

För en automatiserad och effektiv hantering av de transaktioner som inte matchar med en faktura eller befintligt verifikat, rekommenderar vi dig att skapa regelverk. Ett regelverk innebär att du kan skapa förutsättningar för hur transaktioner ska hanteras och bokföras med hjälp av olika parametrar, gränser och konton.

## Skapa regelverk

Kopiera länk hit

Du skapar regelverk under fliken **Regelverk** som du finner i vyn **Meny - Transaktioner**.

![Skapa regelverk under fliken Regelverk som du finner i vyn Meny - Transaktioner.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2560x484%2F7fb56de057%2Fregelverk1.png%2Fm%2F&w=3840&q=75)

När en transaktion återrapporteras från banken som uppfyller samtliga av de krav som du ställt in, skapas ett bokföringsverifikat i den verifikationsserie och med det motkonto du valt - helt automatiskt.

![När en transaktion återrapporteras från banken som uppfyller samtliga av de krav som du ställt in, skapas ett bokföringsverifikat i den verifikationsserie och med det motkonto du valt - helt automatiskt.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1884x1106%2Fd35f5ab944%2Fregelverk2.png%2Fm%2F&w=3840&q=75)

**Matchade transaktioner**  
Här visualiseras det antal transaktioner som finns i din Att göra-lista som regelverket matchar. När du sparar ditt regelverk kommer transaktionerna att bokföras automatiskt utefter de parametrar du lagt in, så som beloppsgränser, motkonton och verifikationsserie.

**Namn på regel**  
Här bestämmer du både vad regeln ska kallas internt och vilken beskrivning verifikationen får vid utförandet av bokföringen. I övrigt har namnet ingen påverkan utan fungerar främst för att tydliggöra vad för typ av regel det avser.

**Transaktionskonto**  
Oavsett om du har ett eller flera transaktionskonton, behöver du ange vilket konto transaktionen kommer återrapporteras ifrån. Du kan välja ett transaktionskonto, eller Alla.

**Transaktionstyp**  
Här väljer du vad det är för typ av transaktion, antingen in-eller utbetalning.

**Från dag i månad - Till dag i månad**  
Återkommande transaktioner har som oftast även ett återkommande transaktionsdatum. För ytterligare villkor och ökad säkerhet kan du därför ange det datumintervallet för den specifika transaktionen.

**Belopp valuta min - Belopp valuta max**  
Genom att ange beloppsintervall i önskad valuta säkerställer du att rätt summa bokförs. Samtidigt som du ökar kontrollen genom att avvikande belopp hamnar i din Att göra-lista och hanteras med manuell handpåläggning.

**Följande ord/fras nämns i transaktionen**  
I princip alla transaktioner innehåller någon typ av referens. Genom att ange det referensord/nyckelord som förekommer i transaktionen du önskar automatisera, ökar du sannolikheten att rätt transaktion med rätt belopp bokförs enligt dina villkor.

**Gäller tom - from**  
Här kan du ange ett start-och slutdatum för vilket regelverket ska gälla. Du kan spara en regel utan att ange någon period, då tillämpas regelverket för framtida och eventuella inlästa transaktioner i Att göra-listan.

**Verifikationsserie och Motkonto**  
I det sista steget behöver du ange verifikationsserien som transaktionen ska bokföras i och kontot som transaktionen ska bokföras mot. Du får även en förhandsgranskning för hur verifikationen kommer att se ut innan du sparar regeln.

**Kostnadsställe och Projekt**  
Om du använder kostnadsställe och/eller projekt i din redovisning finns det stöd för att regeln konterar respektive dimension.  
Kostnadsställe och/eller projekt kommer att anges på varje konteringsrad.

OBS! Regelverk kan inte skapas för kredittransaktioner eller för annan valuta än SEK.

## Lägg till fler nyckelord

Kopiera länk hit

Räcker det inte med ett nyckelord finns det möjlighet att lägga till flera nyckelord till ditt regelverk.

När du fyllt i fältet för Nyckelord kommer du kunna klicka på **Lägg till fler nyckelord**.

![När du fyllt i fältet för Nyckelord kommer du kunna klicka på Lägg till fler nyckelord.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F748x866%2Fdbd0a1ae8e%2Fregelverk-fler-nyckelord.png%2Fm%2F&w=1920&q=75)

En ny sida visas där du kan göra olika val för de villkor du vill ha för att regeln ska matcha din transaktionstyp.

![En ny sida visas där du kan göra olika val för de villkor du vill ha för att regeln ska matcha din transaktionstyp.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1753x922%2F5adcfcc031%2Fregelverk-fler-nyckelord2.png%2Fm%2F&w=3840&q=75)

**Så fungerar villkoren:**

Villkoret uppfylls om ett nyckelord matchar transaktionens referens på något av följande sätt:

- Innehåller nyckelordet
- Börjar med nyckelordet
- Slutar med nyckelordet
- Inte innehåller nyckelordet

**När använder man "Eller"?**

Du använder funktionen **Eller** när du vill att samma bokföringsregel ska gälla för flera helt olika typer av transaktioner.

Exempel: Du har skapat ett villkor för en viss sorts transaktion. Genom att klicka på **Eller** kan du lägga till en helt ny uppsättning sökord för en annan typ av transaktion, men båda kommer att bokföras på exakt samma sätt.

## Lägg till fler motkonton

Kopiera länk hit

När det krävs att regeln bokför en transaktion på flera olika konton kan du fördela beloppet med hjälp av procent. Den procentsats du anger för varje motkonto tillämpas sedan på verifikatet.

Det är också möjligt att ange en procentsats som överstiger 100% totalt. Till exempel vid kontering av särskild löneskatt eller omvänd skattskyldighet.

När du fyllt i alla fält på din regel kommer du att kunna klicka på knappen **Lägg till fler motkonton**.

![När du fyllt i alla fält kommer du att kunna klicka på knappen Lägg till fler motkonton.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1912x1152%2F4f50712ff9%2Fregelverk2b.png%2Fm%2F&w=3840&q=75)

Där kan du ange de procent, kostnadsställen & projekt samt bokföringskonto du önskar.

![Här kan du ange de procent, kostnadsställen & projekt samt bokföringskonto du önskar.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1906x1150%2F9885c8f830%2Fregelverk2c.png%2Fm%2F&w=3840&q=75)

## Regelverk & Valuta

Kopiera länk hit

Om du har transaktioner i en annan valuta än SEK kan du styra dina regler per valuta. Du väljer valuta i samband med när du skapar regler.

De valutor du kan välja styrs av inställningen under **Kugghjulet** - **Bokföring** - **Valutor**.

Beloppet du ser vid “Uppskattat SEK-belopp” visar ditt max-belopp omräknat till dagens valutakurs. Detta ger dig en indikation på hur stort beloppet kan bli på verifikatet när en transaktion matchar regeln.

![Om du har transaktioner i en annan valuta än SEK kan du styra dina regler per valuta.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1709x1185%2F507cf145a4%2Fregelverk-valutaregeln1.png%2Fm%2F&w=3840&q=75)

## Föreslå momssats

Kopiera länk hit

När du skapar en regel som innehåller momskonton föreslår vi färdiga momssatser för att underlätta beräkningen av baklängesmoms. Välj den momssats som gäller för transaktionen (exempelvis 25 %), så räknar systemet om det till rätt procentsats av totalbeloppet (20 %)

Förslagen visas för konton med momskoderna **U1, U2, U3** och **I** som styrs under **Register** - **Kontoplan**. Det går även bra att skriva in en valfri procentsats manuellt om man inte vill nyttja någon av momssatserna.

Baklängesmoms beräknas enligt följande:  
25% blir 20%  
12% blir 10.71%  
6% blir 5,66%

![När du skapar en regel som innehåller momskonton föreslår vi färdiga momssatser för att underlätta beräkningen av baklängesmoms.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1692x848%2F6dd20eab36%2Fregelverk-valutaregeln2.png%2Fm%2F&w=3840&q=75)

## Bokföring

Kopiera länk hit

Regelverk du skapar kommer automatiskt bokföra både framtida och redan inlästa transaktioner i din Att-göra lista, förutsatt att dessa inte matchar mot en faktura eller verifikation.  
Eftersom verifikatet skapas automatiskt kan du därför behöva komplettera med ett underlag för transaktionen i efterhand, utöver bankfilen som bifogas på verifikationen.

![Eftersom verifikatet skapas automatiskt kan du därför behöva komplettera med ett underlag för transaktionen i efterhand, utöver bankfilen som bifogas på verifikationen.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2714x877%2F2304eb161e%2Fregelverk3.jpeg%2Fm%2F&w=3840&q=75)

## Historik

Kopiera länk hit

I vyn **Meny** - **Transaktioner** - **Historik** kommer du kunna filtrera på de transaktioner som har bokförts med hjälp av regelverk, för att få en bra överblick för vilka transaktioner som bokförts på vilket sätt.

![I historikvyn kommer du kunna filtrera på de transaktioner som har bokförts med hjälp av regelverk, för att få en bra överblick för vilka transaktioner som bokförts på vilket sätt.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1833x880%2Fcc5e104fd6%2Fregelverk4.png%2Fm%2F&w=3840&q=75)

**Regelverk, Skapat nytt verifikat** är det hanteringssätt som händelsen får när en transaktion bokförs via ett regelverk.

Klickar du på en av dessa händelser kan du på transaktionskortet se vilken regel som applicerats samt matchade referenser och nyckelord.

![På transaktionskortet ser du vilken regel som applicerats samt matchade referenser och nyckelord.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F915x835%2F645806583a%2Fregelverk5.png%2Fm%2F&w=1920&q=75)

## Regelverkspaket

Kopiera länk hit

För att göra det ännu enklare att skapa ett automatiserat transaktionskonto finns det färdiga regelverkspaket som du kan aktivera. Du hittar dessa under **Meny - Transaktioner - Regelverk**.

Vi har förifyllt de vanligaste inställningarna för varje regelverk – såsom verifikationsserie, motkonto och beloppsgräns – men du kan självklart anpassa dem efter dina behov. Du väljer själv vilka regelverk du vill aktivera och från vilket datum de ska börja gälla för dina transaktioner.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x1236%2F35580b56cb%2Fregelverk5a.png%2Fm%2F&w=3840&q=75)

### Företagskort

Reglerna automatiserar återbetalning av kredit, månadsavgift och överföringar från banken till kort-kontot.  
Underlaget från Mynt skickas med på transaktionen och kopplas till verifikatet när regeln matchar utbetalningarna.

![Reglerna automatiserar återbetalning av kredit, månadsavgift och överföringar från banken till kort-kontot.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1764x989%2Ffd93bca4e3%2Fregelverk-foretagskort.png%2Fm%2F&w=3840&q=75)

### Skatteverket

För dig med integration till Skatteverket finns ett paket tillgängligt innehållande 13 st regelverk.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F678x278%2Fe7dd678a83%2Fregelverk5b.png%2Fm%2F&w=1920&q=75)
- Momsfordran
- Momsskuld
- Debiterad preliminärskatt
- Arbetsgivaravgift
- Avdragen skatt
- Tillgodoförd debiterad preliminärskatt
- Slutlig skatt
- Inbetalning till Skatteverket
- Utbetalning från Skatteverket
- Intäktsränta
- Kostnadsränta
- Korrigerad intäktsränta
- Korrigerad kostnadsränta

Verifikationsserie är förinställd på den första verifikationsserien med “Manuell kontering” påslaget och beloppsgränsen är förvald på 200 000 kr.

Läs mer om integrationen till Skatteverket här: [Koppla ihop Skatteverket med Fortnox](https://support.fortnox.se/produkthjalp/bokforing/koppla-ihop-skatteverket-med-fortnox)

### Bank

För dig med bankintegration finns olika paket tillgängliga, anpassade efter de avgifter som din bank tar ut för sina tjänster.

### Handelsbanken

För Handelsbanken finns det 4 stycken regelverk för att automatisera följande avgifter.

1. Bankintegration
2. Företagspaket
3. Bankavgifter
4. Engagemangsrapport

Verifikationsserien är förinställd på A-redovisning och beloppsgräns på 10 000kr.

Läs mer om integrationen till Handelsbanken: [Automatisk koppling till Handelsbanken](https://support.fortnox.se/produkthjalp/bankkopplingar/automatisk-koppling-till-handelsbanken) .

### Swedbank

För Swedbank finns det 2 stycken regelverk för att automatisera följande avgifter.

1. Banktjänster
2. Bankavgifter
![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1999x1236%2F35580b56cb%2Fregelverk5a.png%2Fm%2F&w=3840&q=75)

Verifikationsserien är förinställd på A-redovisning och beloppsgräns på 10 000kr.

Läs mer om integrationen till Swedbank: [Automatisk koppling till Swedbank och Sparbankerna](https://support.fortnox.se/produkthjalp/bankkopplingar/automatisk-koppling-till-swedbank-och-sparbankerna) .

## Kostnadsställe & Projekt

Kopiera länk hit

För dig som arbetar med **Projekt** och/eller **Kostnadsställe** kan även dessa anges i regeln. Registrerade projekt och/eller kostnadsställen kommer att anges på samtliga konteringsrader när regeln bokför och skapar verifikatet.

![För dig som arbetar med Projekt och/eller Kostnadsställe kan även dessa anges i regeln.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2058x1126%2F156f6ddf16%2Fregelverk8.png%2Fm%2F&w=3840&q=75)

Vill du kunna fördela olika kostnadsställen/projekt på flera konton kan du göra detta genom att lägga till fler motkonton.

![Vill du kunna fördela olika kostnadsställen/projekt på flera konton kan du göra detta genom att lägga till fler motkonton.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1782x1135%2Ff33301b309%2Fregelverk8b.png%2Fm%2F&w=3840&q=75)

## Behörigheter

Kopiera länk hit

För att få tillgång till att skapa **Regelverk** behöver du som användare behörighet för **Verifikationer - Bokför**.

## Exempel på en regel

Kopiera länk hit

I vårt fall är bankavgifter för vårt Företagspaket en återkommande transaktion som alltid inkommer under samma datum- och beloppsintervall samt alltid bokförs på konto 6570 i serie A.

![Exempel på bankavgifter för vårt Företagspaket är en återkommande transaktion som alltid inkommer under samma datum- och beloppsintervall samt alltid bokförs på konto 6570 i serie A.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1821x1099%2F562d2908d3%2Fregelverk9.png%2Fm%2F&w=3840&q=75) ![Transaktionen debiteras vårt Huvudkonto och transaktionstypen är därför en utbetalning.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1082x448%2Feef5b83263%2Fregelverk10.png%2Fm%2F&w=3840&q=75)

Transaktionen debiteras vårt Huvudkonto och transaktionstypen är därför en utbetalning. Vidare anges datumintervallet 1-10, eftersom beloppet alltid dras mellan dessa dagar den första månaden vid varje nytt år. Beloppet för vårt företagspaket är 2 000kr, vilket vi också anger som maxbelopp för transaktionen.

Referensen som banken skickar med i återrapporteringen till Fortnox, beskrivs fördelaktigt med “Företagspaket”, så därmed anges det också under vårt Nyckelord. Eftersom serie A och konto 6570 ska appliceras väljs det som verifikationsserie och vårt motkonto.

Så här ser verifikationen ut när regeln bokför transaktionen:  
1930 - kredit  
6570 - debet

![Exempel på verifikation när regeln bokför transaktionen.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2714x877%2F1ca99bc18d%2Fregelverk11.jpeg%2Fm%2F&w=3840&q=75)

Dela denna artikel

Länk kopierad