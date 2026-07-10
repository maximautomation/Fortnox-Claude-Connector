---
title: "Lämna momsdeklaration via fil i e-tjänsten"
source: "https://www.skatteverket.se/foretag/moms/deklareramoms/lamnamomsdeklarationviafilietjansten.4.2fb39afe18dabf1e4d223cc.html"
author:
published:
created: 2026-07-09
description: "Om du vill lämna momsdeklarationen via fil i Skatteverkets e-tjänst behöver filen skapas och se ut på ett visst sätt. Den ska sparas i XML-format."
tags:
  - "clippings"
---
Om du vill lämna momsdeklarationen via fil behöver filen skapas och se ut på ett visst sätt. Den ska sparas i XML-format. Du laddar upp den färdiga filen i tjänsten Lämna momsdeklaration.

## Så här gör du

För att lämna momsdeklarationen via fil till Skatteverket skapar du först en fil som du sedan laddar upp i tjänsten Lämna momsdeklaration. Sedan kontrolleras uppgifterna i tjänsten innan du kan signera och lämna in dem.

För att kunna lämna momsdeklarationen via filöverföring måste du identifiera dig med e-legitimation och vara behörig att företräda den som uppgifterna avser.

### Obligatoriska uppgifter

| Radnummer | XML-tagg | Information |
| --- | --- | --- |
| Rad 1 | <?xml version="1.0" encoding="ISO-8859-1"?> | Måste finnas med. |
| Rad 2 | \<eSKDUpload Version="6.0"> | Måste finnas med. |
| Rad 3 | \<OrgNr>556000-0175\</OrgNr> | Den momsregistrerades person-, samordnings- organisations- eller representantnummer. Ange numret med 10 siffror enligt formatet xxxxxx-xxxx, med bindestreck. Organisationsnumret i exemplet är påhittat. |
| Rad 4 | \<Moms> | Måste finnas med. |
| Rad 5 | \<Period>202501\</Period> | Redovisningsperiod. Använd följande format.  - Månadsredovisning: År och månad, 202501 (januari 2025) - Kvartalsredovisning: År och den sista månaden i aktuellt kvartal, 202503 (första kvartalet 2025) - Helt beskattningsår: År och den sista månaden i beskattningsåret, 202512 (om beskattningsår motsvaras av ett kalenderår motsvarar exemplet januari–december 2025). |

## Momsinformation

Den andra delen av filen består av de momsuppgifter du vill deklarera. Du kan läsa mer om vilken typ av information som ska ingå i de olika rutorna på sidan Fylla i momsdeklarationen.

- [Fylla i momsdeklarationen Länk till annan webbplats.](https://www.skatteverket.se/foretag/moms/deklareramoms/fyllaimomsdeklarationen.4.3a2a542410ab40a421c80004214.html)

### Momspliktig försäljning eller uttag

| Radnummer | XML-tagg | Avser |
| --- | --- | --- |
| Rad 6 | \<ForsMomsEjAnnan>100000\</ForsMomsEjAnnan> | Ruta 05: Momspliktig försäljning som inte ingår i ruta 06, 07 eller 08. |
| Rad 7 | \<UttagMoms>200000\</UttagMoms> | Ruta 06: Momspliktiga uttag. |
| Rad 8 | \<UlagMargbesk>300000\</UlagMargbesk> | Ruta 07: Beskattnings­-underlag vid vinstmarginal-beskattning. |
| Rad 9 | \<HyrinkomstFriv>400000\</HyrinkomstFriv> | Ruta 08: Hyresinkomster vid frivillig beskattning. |
| Rad 10 | \<MomsUtgHog>200000\</MomsUtgHog> | Ruta 10: Utgående moms 25 %. |
| Rad 11 | \<MomsUtgMedel>15000\</MomsUtgMedel> | Ruta 11: Utgående moms 12 %. |
| Rad 12 | \<MomsUtgLag>5000\</MomsUtgLag> | Ruta 12: Utgående moms 6 %. |

### Momspliktiga inköp vid omvänd betalningsskyldighet

| Radnummer | XML-tagg | Avser |
| --- | --- | --- |
| Rad 13 | \<InkopVaruAnnatEg>5000\</InkopVaruAnnatEg> | Ruta 20: Inköp av varor från ett annat EU-land. |
| Rad 14 | \<InkopTjanstAnnatEg>6000\</InkopTjanstAnnatEg> | Ruta 21: Inköp av tjänster från ett annat EU-land enligt huvudregeln. |
| Rad 15 | \<InkopTjanstUtomEg>7000\</InkopTjanstUtomEg> | Ruta 22: Inköp av tjänster från ett land utanför EU. |
| Rad 16 | \<InkopVaruSverige>8000\</InkopVaruSverige> | Ruta 23: Inköp av varor i Sverige som köparen är betalnings-skyldig för. |
| Rad 17 | \<InkopTjanstSverige>9000\</InkopTjanstSverige> | Ruta 24: Övriga inköp av tjänster i Sverige som köparen är betalnings-skyldig för. |
| Rad 18 | \<MomsInkopUtgHog>2500\</MomsInkopUtgHog> | Ruta 30: Utgående moms 25 %. |
| Rad 19 | \<MomsInkopUtgMedel>1000\</MomsInkopUtgMedel> | Ruta 31: Utgående moms 12 %. |
| Rad 20 | \<MomsInkopUtgLag>500\</MomsInkopUtgLag> | Ruta 32: Utgående moms 6 %. |

### Försäljning med mera som är undantagen från moms

| Radnummer | XML-tagg | Avser |
| --- | --- | --- |
| Rad 21 | \<ForsVaruAnnatEg>11000\</ForsVaruAnnatEg> | Ruta 35: Försäljning av varor till ett annat EU-land. |
| Rad 22 | \<ForsVaruUtomEg>12000\</ForsVaruUtomEg> | Ruta 36: Försäljning av varor utanför EU. |
| Rad 23 | \<InkopVaruMellan3p>13000\</InkopVaruMellan3p> | Ruta 37: Mellan-mans inköp av varor vid treparts-handel. |
| Rad 24 | \<ForsVaruMellan3p>14000\</ForsVaruMellan3p> | Ruta 38: Mellan-mans försäljning av varor vid treparts-handel. |
| Rad 25 | \<ForsTjSkskAnnatEg>15000\</ForsTjSkskAnnatEg> | Ruta 39: Försäljning av tjänster till beskatt-ningsbar person i annat EU-land enligt huvud-regeln. |
| Rad 26 | \<ForsTjOvrUtomEg>16000\</ForsTjOvrUtomEg> | Ruta 40: Övrig försäljning av tjänster som tillhanda-hållits utomlands. |
| Rad 27 | \<ForsKopareSkskSverige>17000\</ForsKopareSkskSverige> | Ruta 41: Försäljning när köparen är betalnings-skyldig i Sverige. |
| Rad 28 | \<ForsOvrigt>18000\</ForsOvrigt> | Ruta 42: Övrig försäljning m.m. |

### Import

| Radnummer | XML-tagg | Avser |
| --- | --- | --- |
| Rad 29 | \<MomsUlagImport>10000\</MomsUlagImport> | Ruta 50: Beskattnings-underlag vid import. |
| Rad 30 | \<MomsImportUtgHog>2000\</MomsImportUtgHog> | Ruta 60: Utgående moms 25 %. |
| Rad 31 | \<MomsImportUtgMedel>350\</MomsImportUtgMedel> | Ruta 61: Utgående moms 12 %. |
| Rad 32 | \<MomsImportUtgLag>150\</MomsImportUtgLag> | Ruta 62: Utgående moms 6 %. |

### Ingående moms

| Radnummer | XML-tagg | Avser |
| --- | --- | --- |
| Rad 33 | \<MomsIngAvdr>1000\</MomsIngAvdr> | Ruta 48: Ingående moms att dra av. |

När beloppet avser ingående moms att få tillbaka ska du inte ange något inledande tecken framför beloppet.

Om du däremot tagit emot en ändringsfaktura som innebär en kreditering av en tidigare utfärdad faktura ska du minska tidigare avdrag för ingående moms. Om en sådan minskning resulterar i att redovisningsperiodens sammanlagda ingående moms innebär att du har ingående moms att betala redovisar du det genom att ange ett minustecken (-) direkt innan beloppet, det vill säga utan mellanrum.

### Summering

| Radnummer | XML-tagg | Avser |
| --- | --- | --- |
| Rad 34 | \<MomsBetala>225500\</MomsBetala> | Ruta 49: Moms att betala eller få tillbaka |

- Ange moms att betala med endast belopp (utan inledande tecken).
- Ange moms att få tillbaka genom att skriva ett minustecken (-) direkt innan beloppet (inget mellanslag mellan minustecken och belopp).

### Upplysningar

| Radnummer | XML-tagg | Avser |
| --- | --- | --- |
| Rad 35 | \<TextUpplysningMoms>Din upplysning du vill lämna\</TextUpplysningMoms> | Upplysningar. Du kan ange maximalt 300 tecken. |

## Filens avslut

Filen ska avslutas med två rader, direkt efter all momsinformation:

- \</Moms>
- \</eSKDUpload>

## Lämna kontaktuppgifter i nästa steg

Du kan inte lämna kontaktuppgifter via fil. För att lägga till den typen av information laddar du först upp din fil, och går vidare till steget Granska och skicka in. Där kan du lägga till kontaktuppgifter i funktionen Rätta uppgifter manuellt.

## Ladda upp filen

Ladda upp filen i tjänsten Lämna momsdeklaration. Välj funktionen Deklarera via fil och välj den fil som du har skapat.

Du måste ha en e-legitimation och vara behörig att företräda det företag du vill lämna uppgifter för.

När uppgifterna har lästs in och kontrollerats visas de i deklarationsformuläret där du kan granska uppgifterna innan de skickas in. Är någon av uppgifterna felaktiga har du möjlighet att rätta uppgifterna manuellt. Om du inte har skrivit in uppgifterna på rätt sätt eller om någon uppgift saknas får du ett felmeddelande.

När du laddat upp och granskat din fil, och den inte innehåller felaktigheter som hindrar inlämning, kan du signera och skicka in momsdeklarationen. Då får du en kvittens.

Vill du inte skicka in uppgifterna kan du istället välja att spara uppgifterna om exempelvis du, eller någon annan, vill komplettera eller ändra underlaget vid ett senare tillfälle.

## Kontroll av mottagna uppgifter

Uppgifterna i den fil du laddar upp kontrolleras på flera olika sätt. Kontrollerna kan resultera i olika typer av fel.

### Avvisande fel

Uppgifter som innehåller avvisande fel, exempelvis fel som medför att XML-filen inte validerar, kan vi inte ta emot. Det går inte att ladda upp en fil med avvisande fel och uppgifterna i filen kan inte heller sparas i e-tjänsten.

Nedan beskrivs vilka avvisande fel som förekommer.

### Inledning (Headern)

- Obligatoriska uppgifter saknas.
- Den momsregistrerades organisationsnummer (eller motsvarande) har angetts i ett felaktigt format.
- Det organisationsnummer (eller motsvarande) som angetts motsvarar inte den du är behörig att företräda.
- Redovisningsperioden har angetts i ett felaktigt format.
- Den redovisningsperiod som angetts i filen motsvarar inte en redovisningsperiod som redovisning ska lämnas för.

### Momsinformation

- Beloppsuppgifter är angivna i fel format. Endast siffror (0–9) samt inledande plustecken (+) eller minustecken (-) tillåts. Belopp måste anges i heltal utan decimaler.
- Det saknas en summering i form av moms att betala eller återfå.

### Filens avslut

- Obligatoriska uppgifter saknas.

### Övriga fel

- Den uppladdade filen är i ett annat format än XML.
- Det finns felaktiga mellanslag eller tabbar i filen.
- Det finns otillåtna tecken i filen. Tillåtna tecken är bara bokstäver (A–Z), <, > samt /.
- En XML-tagg har angetts på ett annat sätt än det format som avsnittet Skapa en fil beskriver.

### Stoppande fel

Uppgifter som innehåller stoppande fel, exempelvis motstridiga eller saknade uppgifter, går att spara men felen måste rättas innan det går att skicka in momsdeklarationen till Skatteverket. Du rättar dessa fel genom att antingen ladda upp en rättad fil eller rätta de felaktiga uppgifterna manuellt via Rätta uppgifter manuellt.

### Rimlighetskontroll

Uppgifterna genomgår även en så kallad rimlighetskontroll, som säger till om exempelvis ett eller flera belopp är orimligt höga. Detta behöver inte betyda att uppgifterna är felaktiga, men de bör kontrolleras innan momsdeklarationen skickas in. Det går i dessa fall att skicka in momsdeklarationen utan att uppgifterna har ändrats. Om någon uppgift ska ändras gör du det manuellt via ”Rätta i formuläret”.

## Rätta fel i en inlämnad momsdeklaration via filöverföring

Om du upptäcker att du har gjort fel i en redan inlämnad momsdeklaration kan du skapa en ny fil för den perioden och lämna in på samma sätt som beskrivits ovan. Du behöver göra om hela deklarationen, inte bara de uppgifter som har ändrats.

## Exempel

Nedan följer ett antal olika exempel på hur en fil kan se ut. All information nedan är fiktiv och du måste anpassa den utifrån den som du ska lämna uppgifter för.

### Exempel 1: Moms att betala

Försäljning av varor inom Sverige med utgående moms om skattesats 25 % samt avdrag för ingående moms:

<?xml version="1.0" encoding="ISO-8859-1"?>

\<eSKDUpload Version="6.0">

\<OrgNr>556000-0175\</OrgNr>

\<Moms>

\<Period>202401\</Period>

\<ForsMomsEjAnnan>100000\</ForsMomsEjAnnan>

\<MomsUtgHog>25000\</MomsUtgHog>

\<MomsIngAvdr>1000\</MomsIngAvdr>

\<MomsBetala>24000\</MomsBetala>

\</Moms>

\</eSKDUpload>

### Exempel 2: Moms att återfå

Försäljning av varor inom Sverige med utgående moms om skattesats 25 % samt avdrag för ingående moms

<?xml version="1.0" encoding="ISO-8859-1"?>

\<eSKDUpload Version="6.0"> \<OrgNr>556000-0175\</OrgNr>

\<Moms>

\<Period>202401\</Period>

\<ForsMomsEjAnnan>100000\</ForsMomsEjAnnan>

\<MomsUtgHog>25000\</MomsUtgHog>

\<MomsIngAvdr>55000\</MomsIngAvdr>

\<MomsBetala>-30000\</MomsBetala>

\</Moms>

\</eSKDUpload>

### Exempel 3: Inget att deklarera

Det finns inga uppgifter att redovisa för perioden. Momsdeklaration måste ändå lämnas, men noll (0) redovisas.

<?xml version="1.0" encoding="ISO-8859-1"?>

\<eSKDUpload Version="6.0">

\<OrgNr>556000-0175\</OrgNr>

\<Moms>

\<Period>202401\</Period>

\<MomsBetala>0\</MomsBetala>

\</Moms>

\</eSKDUpload>

### Exempel 4: Handel med andra EU-länder

Försäljning av varor till annat EU-land samt inköp av varor från annat EU-land (skattesats 12 % och med full avdragsrätt)

<?xml version="1.0" encoding="ISO-8859-1"?>

\<eSKDUpload Version="6.0">

\<OrgNr>556000-0175\</OrgNr>

\<Moms>

\<Period>202401\</Period>

\<ForsVaruAnnatEg>11000\</ForsVaruAnnatEg>

\<InkopVaruAnnatEg>5000\</InkopVaruAnnatEg>

\<MomsInkopUtgMedel>600\</MomsInkopUtgMedel>

\<MomsIngAvdr>600\</MomsIngAvdr>

\<MomsBetala>0\</MomsBetala>

\</Moms>

\</eSKDUpload>

### Exempel 5: Lämnad upplysning

<?xml version="1.0" encoding="ISO-8859-1"?>

\<eSKDUpload Version="6.0">

\<OrgNr>556000-0175\</OrgNr>

\<Moms> \<Period>202401\</Period>

\<ForsMomsEjAnnan>100000\</ForsMomsEjAnnan>

\<MomsUtgHog>25000\</MomsUtgHog>

\<MomsIngAvdr>55000\</MomsIngAvdr>

\<MomsBetala>-30000\</MomsBetala>

\<TextUpplysningMoms>Skriv den upplysning du vill skicka in\</TextUpplysningMoms>

\</Moms>

\</eSKDUpload>

## Exempel 6: Deklaration med information i samtliga fält

Samtliga XML-taggar och övrig obligatorisk information, så att du kan kopiera innehållet och fylla i rätt uppgifter.

<?xml version="1.0" encoding="ISO-8859-1"?>

\<eSKDUpload Version="6.0">

\<OrgNr>556000-0175\</OrgNr>

\<Moms>

\<Period>202401\</Period>

\<ForsMomsEjAnnan>100000\</ForsMomsEjAnnan>

\<UttagMoms>200000\</UttagMoms>

\<UlagMargbesk>300000\</UlagMargbesk>

\<HyrinkomstFriv>400000\</HyrinkomstFriv>

\<InkopVaruAnnatEg>5000\</InkopVaruAnnatEg>

\<InkopTjanstAnnatEg>6000\</InkopTjanstAnnatEg>

\<InkopTjanstUtomEg>7000\</InkopTjanstUtomEg>

\<InkopVaruSverige>8000\</InkopVaruSverige>

\<InkopTjanstSverige>9000\</InkopTjanstSverige>

\<MomsUlagImport>10000\</MomsUlagImport>

\<ForsVaruAnnatEg>11000\</ForsVaruAnnatEg>

\<ForsVaruUtomEg>12000\</ForsVaruUtomEg>

\<InkopVaruMellan3p>13000\</InkopVaruMellan3p>

\<ForsVaruMellan3p>14000\</ForsVaruMellan3p>

\<ForsTjSkskAnnatEg>15000\</ForsTjSkskAnnatEg>

\<ForsTjOvrUtomEg>16000\</ForsTjOvrUtomEg>

\<ForsKopareSkskSverige>17000\</ForsKopareSkskSverige>

\<ForsOvrigt>18000\</ForsOvrigt>

\<MomsUtgHog>200000\</MomsUtgHog>

\<MomsUtgMedel>15000\</MomsUtgMedel>

\<MomsUtgLag>5000\</MomsUtgLag>

\<MomsInkopUtgHog>2500\</MomsInkopUtgHog>

\<MomsInkopUtgMedel>1000\</MomsInkopUtgMedel>

\<MomsInkopUtgLag>500\</MomsInkopUtgLag>

\<MomsImportUtgHog>2000\</MomsImportUtgHog>

\<MomsImportUtgMedel>350\</MomsImportUtgMedel>

\<MomsImportUtgLag>150\</MomsImportUtgLag>

\<MomsIngAvdr>1000\</MomsIngAvdr>

\<MomsBetala>225500\</MomsBetala>

\<TextUpplysningMoms>Skriv den upplysning du vill skicka in\</TextUpplysningMoms>

\</Moms>

\</eSKDUpload>