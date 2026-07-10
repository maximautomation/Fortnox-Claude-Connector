---
title: "API för att hämta företagsinformation"
source: "https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation.3988.html"
author:
published: 2026-07-01
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
Vill du få aktuell och tillförlitlig företagsinformation direkt in i dina system? Med vårt API hämtar du uppgifter som speglar verkliga förhållanden, en bra grund för smarta och effektiva digitala tjänster.

## Gör så här för att få tillgång till API:et

1. **Läs igenom villkoren i våra avtal.**
2. **Begär tillgång**
	1. Fyll i och skicka in [kundanmälan](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation/kundanmalantillapiforatthamtaforetagsinformation.4708.html).
3. **Avtala med oss**
	1. Vi skickar ett avtal till dig.
		2. Du fyller i den nivå av transaktioner som ni önskar teckna avtalet för. Skriv under och skicka tillbaka avtalet till oss med post.
4. **Få API -nycklar (client\_id och client\_secret) till testmiljön**
	1. När vi har mottagit avtalet får du så kallade API-nycklar till testmiljön skickade till dig via mejl och sms enligt de kontaktuppgifter du lämnade i formuläret.
5. **Koppla upp och testa**
	1. I testmiljön kan du säkerställa att du kan koppla upp dina applikationer mot vårt API och att det fungerar som du har tänkt dig. Under tiden som du bara har tillgång till testmiljön faktureras inte månadsavgiften.
6. **Få API -nycklar (client id och client secret) till produktionsmiljön**
	1. Hör du av dig till oss när du är klar med dina tester och vill få tillgång till produktionsmiljön.
		2. Du får nya API-nycklar (client\_id och client\_secret) att använda i produktionsmiljön.
7. **Kostnad och faktura**
	1. När du har tillgång till produktionsmiljön kommer vi att börja fakturera den avtalade månadsavgiften och sedan är det bara för dig att börja använda tjänsten och tillgodogöra dig vår information om företag och företagande.
		2. Om du inte hört av dig till oss inom 3 månader kommer vi automatiskt att ge dig tillgång till produktionsmiljön.
8. **Använd vårt data!**
	1. Nu kan du använda vårt API i dina system och i din verksamhet!

## Vilken information kan jag få via API:et?

Du ställer en fråga via API:et och skickar in ett organisationsnummer eller ett personnummer. Du får då tillgång till grundläggande information om företag och företagande i Sverige.

Även den information som inkluderas i API:et för värdefulla datamängder ingår när du får tillgång till denna tjänst. Informationen du kan hämta via det API:et kan du läsa mer om på sidan [API för värdefulla datamängder](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/vardefulladatamangder/apiforvardefulladatamangder.5513.html).

### Organisationsformer

- AB: Aktiebolag
- KB: Kommanditbolag
- HB: Handelsbolag
- FL: Filialer
- BRF: Bostadsrättsföreningar
- EK: Ekonomisk förening
- E: Enskild firma
- BAB: Bankaktiebolag
- FAB: Försäkringsaktiebolag
- TPAB: Tjänstepensionsaktiebolag
- SE: Europabolag
- FOF: Försäkringsförening
- TPF: Tjänstepensionsförening
- BF: Bostadsförening
- KHF Kooperativ hyresrättsförening
- SF: Sambruksförening
- BFL: Utländsk banks filial
- MB: Medlemsbank
- SCE: Europakooperativ
- SB: Sparbank
- TSF: Trossamfund
- I: Ideell förening som bedriver näring
- S: Stiftelse som bedriver näring
- OTBP: Ömsesidigt tjänstepensionsbolag
- OFB: Ömsesidigt försäkringsbolag

### Information om företag

Genom att skicka in ett organisationsnummer eller ett ärendenummer till API:et kan du exempelvis få svar på:

- företagets namn, organisationsnummer och vilken verksamhet de bedriver
- vilka som sitter i företagets styrelse
- upplysning om företaget gått i likvidation eller konkurs

I det fall man vill veta vilken information som var gällande vid en specifikt tidpunkt så kan du skicka med en tidpunkt i frågan och få den information som gällde då.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| **GRUNDINFORMATION** | Information that always is included in the answer. |
| IDENTITETSBETECKNING | Company registration number |
| NAMNSKYDDSLÖPNUMMER | Used to separate companies for organisation types that can have more than one company on the same company registration number |
| ARENDE | Includes information to when (date) the information for the organisation was last changed and what ärendenummer initiated the change |
| ORGANISATIONSNAMN | Name of organisation |
| ORGANISATIONSFORM | Code and text |
| ORGANISATIONSSTATUSAR | Code, text and date |
| **ENSKILDA INFORMATIONSMÄNGDER** |  |
| ORGANISATIONSDATUM | Different dates regarding the company (registreringsdatum and bildatdatum) |
| HEMVISTKOMMUN | Domicile for the company |
| RAKENSKAPSAR | Financial year, when it start and when it ends |
| VERKSAMHETSBESKRIVNING | Description of the business activities |
| ORGANISATIONSADRESSER | Postal address and email address |
| FIRMATECKNING | Description of signatory power   prokuratext |
| SAMTLIGA\_ORGANISATIONSNAMN | Includes a list of information connected to the organisations different names, (särskilt företagsnamn, in other languages etc.) |
| FUNKTIOARER | Company officers:   new information: representerasAV, insats, anteckning |
| TILLSTÅND | Valid for some types of organisations (banks, insurance companies etc.) |
| ORGANISATIONSADRESSER | Postal address and email address |
| FIRMATECKNING | Signatory power:   new information: prokuratext |
| FUNKTIONARER | Company officers:   representerasAV, insats, anteckning |
| ORGANISATIONSENGAGEMANG | A company’s assignments in other companies |
| AKTIEINFORMATION | - information about stocks in the company - aktiekapital - antalaktier - aktiegranser - aktieslag - fritext |
| OVRIG\_ORGANISATIONSINFORMATION | External notes and other registration information |
| ORGANISATIONSMARKERING | Code and organisation marking in text |
| VAKANSER\_OCH\_UPPLYSNINGAR | Code, text and date for vacancies and information |
| BESTAMMELSER | Code, text, dates, approval instance etc. |
| EKONOMISK\_PLAN | Registration date. valid for ekonomiska föreningar/bostadsrättsföreningar |
| UTLÄNDSK\_FILIALAGANDE\_ORGANISATION | Company registration number, name of organisation, description of the business activities, location etc. |
| FINANSIELLA\_RAPPORTER | FINANSIELLA\_RAPPORTER Information about financial reports  - Årsredovisning /Annual report - Årsredovisning på annat språk/Annual report in other language - Delårsrapport/interim report - Vinstutdelning beslutad extra bolagsstämma/dividend, distribution of profits decided at extra ordinary general meeting, EGM - Slutredovisning/Final report - Fortsatt bolagsstämma/resumed shareholders’ meeting |
| UTLÄNDSKA\_FILIALER | Company registration number, name of organisation, adress etc. |

Mer teknisk information hittar du inne i vår [utvecklarportal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

### Information om ärende

Genom att skicka in ett organisationsnummer, och i vissa fall även datum, till API:et kan du få information om ärenden kopplade till organisationsnumret, exempelvis:

- öppna och stängda ärenden för aktuellt organisationsnummer.

Observera att information om ärenden på aktiebolag endast går att få från år 2003 och framåt.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| ARENDELISTA | List of all open and closed cases. |

Mer teknisk information hittar du inne i vår [API-portal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

### Information om aktiekapital

Genom att skicka in ett organisationsnummer till API:et kan du få information om:

- gällande aktieinformation
- aktiekapitalförändringar
- skuldebrev
- bemyndiganden.

Du kan ange datumintervall för den tidsperiod av aktiekapitalförändringar som du är intresserad av. Observera att information om aktiekapitalförändringar endast går att få från år 2003 och framåt.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| **GRUNDINFORMATION** | Information that always is included in the answer |
| IDENTITETSBETECKNING | Company registration number |
| NAMNSKYDDSLÖPNUMMER | Used to separate companies for organisation types that can have more than one company on the same company registration number |
| ORGANISATIONSNAMN | Name of organisation |
| ORGANISATIONSFORM | Code and text |
| ORGANISATIONSSTATUSAR | Code, text and date |
| ARENDE | Includes information to when (date) the information for the organisation was last changed and what ärendenummer initiated the change |
| **GÄLLANDE AKTIEINFORMATION** | Information about the share capital that is valid at the point ot the API request  Share capital  Number of shares  Class of shares  Minimum and maximum share capital |
| **AKTIEKAPITALFÖRÄNDRINGAR** | Share capital changes over time |
| **SKULDEBREV** | Debt instrument changes over time |
| **BEMYNDIGANDEN** | Authorisation changes over time |

### Information om personer

Genom att skicka in ett personnummer till API:et kan också få svar på exempelvis:

- vilka uppdrag en person har kopplat till ett företag
- om personen har näringsförbud
- om personen har gått i konkurs.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| ORGANISATIONSENGAGEMANG | Showing a person’s assignments in companies. |
| PERSONLIG\_KONKURS | Personal bankruptcy. |
| BITRADESFORBUD | Prohibition of financial assistance. |
| NARINGSFORBUD | Trade ban (prohibition to carry on business). |

Mer teknisk information hittar du inne i vår [API-portal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

### Information om vem som har rätt att skriva under

Genom att skicka in ett personnummer och ett organisationsnummer kan du få veta på vilka sätt personen har rätt att skriva under i företagets namn med rättslig verkan (firmateckning).

Informationen om vem eller vilka som är firmatecknare är viktig exempelvis när avtal ska tecknas, andra handlingar i företaget ska signeras eller när företaget ska företrädas hos domstolar eller myndigheter.

Du får veta om personen ifråga har rätt att teckna firman och på vilket sätt, exempelvis:

- ensam
- tillsammans med andra (deras personnummer)
- inte alls.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| JA ENSAM | The company officer has signatory power alone. |
| JA TILLSAMMANS | The company officer has signatory power together with other company officers (all combinations of other company officers are listed here). |
| JA LOPANDE | The managing director is entitled to sign on behalf of the company in the course of normal business activities. |
| JA FULLMAKT | The company officer has signatory power with a power of attorney. Bolagsverket has not the power of attorney registered. |
| NEJ | The company officer does not have signatory power. The reason is one of the below:  - The company does not exist or is deregistered. - The company officer has no role in this company - The company officer has a role in this company but the company officer has no signatory power. |

Mer teknisk information hittar du inne i vår [API-portal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

### Information om organisationsengagemang

Genom att ange ett personnummer eller ett organisationsnummer får du tillbaka en lista över de engagemang som personen eller organisationen har i andra organisationer.

Om engagemanget innebär att personen eller organisationen är en del av firmateckningen framgår även detta i svaret.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| ORGANISATIONSENGAGEMANG | List of A person´s assignments in companies or a company’s assignments in other companies |
| ORGANISATION | Company in which the person or the company is a company officer |
| FUNKTIONÄRSINFORMATION | Information about the company officer, ex what roles and if the company officer has the right to sign for the company |

Mer teknisk information hittar du inne i vår [API-portal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

### Information om finansiella rapporter

Genom att skicka in ett organisationsnummer, och i vissa fall även datum, till API:et kan du få information om företagets finansiella rapporter. De finansiella rapporterna presenteras per räkenskapsperiod.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| ÅRSREDOVISNING | Annual report (including interim report). The period for the financial report, type of report, arrival date, registration date, information if the financial report is including sustainability report, consolidated accounts or dividend, deficiencies and date when the processing is complete. |
| ÅRSREDOVISNINGSPÅMINNELSE | Reminder to submit annual report. Date for reminder and type of reminder. |
| VINSTUTDELNING | Distribution of profits. Date of decision, currency and amount. |
| FORTSATT STÄMMA | Resumed shareholders’ or members' meeting. |

Mer teknisk information hittar du inne i vår [API-portal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

### Information om detaljerad status

Genom att skicka in ett organisationsnummer till API:et kan du få information om:

- Avregistrerad organisation
	- Företaget är avregistrerat, information om datum och anledningen till avregistrering.
- Förfarande för avveckling eller omstrukturering  
	- Företaget befinner sig i pågående konkurs, likvidation, företagsrekonstruktion.
		- Information om datum, beslutsfattare (exempelvis vilken domstol som beslutat om konkurs), funktionärer (konkursförvaltare, likvidatorer) med mera.
- Förfarande för fusion, delning eller ombildning  
	- Företaget befinner sig i någon av dessa förfaranden.
		- Information om datum, övertagande och överlåtande företag med mera.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| DETALJERAD\_STATUS | - Avregistrerad organisation:   	Date of deregistration, reason for deregistration, notes. - Förfarande för avveckling eller omstrukturering:   	A list of winding-up or restructuring procedures – dates, type (bankruptcy, liquidation, business reconstruction, composition negotiation, resolution), decision-making authority etc. - Förfarande för fusion, delning eller ombildning:   	A list of merger, conversion or restructuring procedure – dates. Transferring organizations, acquiring organizations etc. |

Mer teknisk information hittar du inne i vår [API-portal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

### Notifieringar om förändringar

Notifieringar om förändringar är en tjänst som gör det möjligt att få information när något ändras för ett företag som är registrerad hos Bolagsverket.

En notifiering innehåller bland annat organisationsnummer, organisationsform, ärendenummer samt en sakfråga som visar vad förändringen gäller. Det innebär att du får kännedom om när en förändring har skett och kan därefter hämta den information som är intressant med hjälp av Företagsinformation via API.

Notifieringar om förändringar erbjuds och ingår kostnadsfritt för dig som väljer 3 000 transaktioner per månad eller mer.

### Registret över verkliga huvudmän

En verklig huvudman är den eller de **personer** som ytterst äger eller kontrollerar exempelvis ett företag eller en förening. En verklig huvudman kan också vara den eller de personer som tjänar på att någon annan agerar åt dem. Läs om specifika [Regler för olika företags- och föreningsformer](https://bolagsverket.se/omoss/flerverksamheter/omverklighuvudman/regleromverklighuvudmanforolikaforetagsochforeningsformer.2541.html).

#### Information om rättsliga förutsättningar för åtkomst till information ur registret för verkliga huvudmän

Registret över verkliga huvudmän förs av Bolagsverket med stöd av förordning (2017:667) om registrering av verkliga huvudmän och informationen i registret hålls tillgänglig hos myndigheten. Avsikten med registret är att tillgängliggöra informationen i registret och att därigenom bidra till arbetet mot penningtvätt och finansiering av terrorism. I fråga om personuppgifter ska registret ha till ändamål att tillhandahålla uppgifter för bland annat:

- verksamhet som myndigheter bedriver och
- åtgärder för kundkännedom enligt lagen (2017:630) om åtgärder mot penningtvätt och finansiering av terrorism.

Punkterna ovan motsvarar art. 11 (2) och 11 (3) i direktiv 2024/1640 om de mekanismer som medlemsstaterna ska inrätta för att förhindra att det finansiella systemet används för penningtvätt eller finansiering av terrorism, om ändring av direktiv (EU) 2019/1937 och om ändring och upphävande av direktiv (EU) 2015/849 (6:e penningtvättsdirektivet).

För att få tillträde till det API som Bolagsverket använder för att tillgängliggöra information ur registret över verkliga huvudmän krävs att informationsmottagaren tillhör någon av aktörerna enligt ovan, alternativt är ett företag som förmedlar sådan information till någon av aktörerna som anges ovan.

#### Information om verkliga huvudmän

Genom att skicka in ett organisationsnummer till API:et kan du få information om företagets verkliga huvudmän. Du kan också skicka in ett personnummer till API:et för att få information om alla företag där en person är verklig huvudman.

#### Detaljerad lista

### Information om företagsinteckningar

Genom att skicka in ett organisationsnummer eller personnummer eller inteckningsnummer eller inteckningsid kan du få information om organisationens företagsinteckningar.

Svaret innehåller en lista med alla företagsinteckningar den identitetsbeteckningen har. Eller en företagsinteckning om man söker med inteckningsnummer eller inteckningsid.

#### Detaljerad lista

### Dokument och handlingar

#### Information om dokument och handlingar

Genom att skicka in ett organisationsnummer, och i vissa fall även datum, till API:et kan du få information om företagets nedladdningsbara dokument och handlingar. Handlingarna har ett dokumentID som du sedan kan använda för att ladda ner ett dokument.

#### Detaljerad lista

| Informationsmängd | Beskrivning |
| --- | --- |
| Bolagsordning | Articles of association |
| Ekonomisk plan (för bostadsrättsförening) | Financial plan |
| Inkomstskatterapport | Income tax report |
| Stadgar | Statutes |
| Registreringsbevis (de som är skapade i samband med att ett ärende stängs och registreras, de har alltså inte dagens datum om de inte hämtas samma dag som registrering) | Certificate of registration |
| Årsredovisningar inklusive delårsrapporter | Annual report Interim report |

Mer teknisk information hittar du inne i vår [API-portal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

## Priser för att använda API:et

Du betalar en anslutningsavgift när du ansluter till API:et. Därefter betalar du för det antal transaktioner\* du vill kunna göra per månad. Transaktioner som ingår i API:et för värdefulla datamängder är gratis.

\* Med transaktion menar vi de frågor du skickar till API:ets operationer med ett organisationsnummer eller personnummer.

### Pris för att ansluta till API:et

| Anslutning | Pris i kronor   exklusive moms | Pris i kronor   inklusive moms |
| --- | --- | --- |
| Anslutningsavgift¹ | 5 000 | 6 250 |

¹ Faktureras när avtalet är underskrivet.

### Priser för transaktioner per månad

| Antal transaktioner per månad³ | Pris i kronor per månad exklusive moms² | Pris i kronor per månad inklusive moms² |
| --- | --- | --- |
| 500 transaktioner | 1 000 | 1 250 |
| 3 000 transaktioner | 5 000 | 6 250 |
| 8 000 transaktioner | 13 000 | 16 250 |
| 15 000 transaktioner | 24 000 | 30 000 |

### Priser för dokument och handlingar per månad

| Antal dokument och handlingar per månad³ | Pris i kronor per månad exklusive moms² | Pris i kronor per månad inklusive moms² |
| --- | --- | --- |
| 100 transaktioner | 4 000 | 5 000 |
| 1 000 transaktioner | 40 000 | 50 000 |
| 5 000 transaktioner | 200 000 | 250 000 |

² Vi skickar den första månadsfakturan efter att du har fått tillgång till produktionsmiljön, men senast tre månader efter att avtalet har godkänts.

³ En månad räknas från första till sista dagen i månaden. Oanvända transaktioner kan inte sparas till nästa månad.

## Teknik

Vårt API är en REST-tjänst baserad på HTTP och JSON. All kommunikation med tjänsten ska krypteras via HTTPS. Auktorisation av API-anrop görs med hjälp av OAuth 2.

Åtkomst till informationen skyddas med etablerade autentiserings- och auktoriseringsmekanismer. Beroende på vilken information som efterfrågas krävs OAuth 2.0-baserad autentisering antingen med hjälp av Client ID och Client Secret eller klientcertifikat (mTLS). För API för att hämta företagsinformation används generellt Client ID/Client Secret utom för att få tillgång till information om verkliga huvudmän där klientcertifikat används. Mer om vilken säkerhetslösning som gäller framgår av respektive API-dokumentation.

Prestandan för detta API tillåter varje användare att göra 20 anrop per sekund.

En mer [detaljerad beskrivning Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview) av våra API:er finns i vår utvecklarportal i WSO2. All dokumentation är samlad där, och du behöver inte logga in för att ta del av innehållet.

### Förändringar i våra API:er

När det sker förändringar i våra API:er så hanterar vi det enligt rutin du kan läsa om på sidan [Så hanterar vi ändringar i API:er](https://bolagsverket.se/apierochoppnadata/driftochsupport/sahanterarviandringariapier.4811.html).

### Servicenivåer

För information om servicenivåerna för API:erna läs på sidan [Servicenivåer för API:er som hämtar företagsinformation](https://bolagsverket.se/apierochoppnadata/driftochsupport/servicenivaerforapiersomhamtarforetagsinformation.5424.html).

## Testmiljö

I vår testmiljö kan du testa din integration mot vårt API när du har tecknat avtal med oss. Testmiljön innehåller ett antal testföretag och testpersoner och där kan du verifiera svaren du får från API:ets operationer. Observera att testmiljön inte innehåller alla möjliga kombinationer av alla informationsmängder och organisationsformer. Du hittar mer information om testmiljön och vårt testdata under Dokumentation i vår [utvecklarportal Länk till annan webbplats.](https://portal.api.bolagsverket.se/devportal/apis/3e90ead0-d992-49cc-a02d-7984c27c2164/overview).

## Avtal

För att du ska kunna använda vårt API behöver du skriva ett [avtal](https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/apiforatthamtaforetagsinformation/avtalforapiforatthamtaforetagsinformation.3990.html) med oss där vi säkerställer att våra användarvillkor uppfylls.

![Illustration för drift och support](https://bolagsverket.se/images/18.3bd0e5b6199877ec1a41ad65/1761309878491/support-illustration.png)

## Drift och support

Här hittar du information om driftstatus, planerade förändringar, supportnivåer och tekniska resurser. Du kan också läsa vanliga frågor, se servicetider och prenumerera på nyhetsflöden.