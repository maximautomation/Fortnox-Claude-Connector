---
title: "KONTOPLAN BAS 2026"
source_type: "PDF"
source_name: "BAS_kontoplan_2026_v2.pdf"
version: "v 1.1"
language: "Svenska"
topic: "BAS-kontoplan 2026"
intended_use: "Coding agent knowledge base"
confidence: "High"
conversion_note: "Clean structured Markdown. Alla konton som kunde extraheras från PDF:en är med. Sidnummer, layoutskräp och extraktionsartefakter har rensats. Konton markerade med # i källan är markerade som ej för K2."
---

# KONTOPLAN BAS 2026

## Source Notes

- Version: v 1.1.
- # = Konton som inte ska användas när K2 tillämpas.
- För ändringar jämfört med 2025 hänvisar källan till webbsidan där man under Jämför kontoplaner hittar en excelfil där skillnaderna presenteras.
- Den här filen är strukturerad för att en coding agent ska kunna söka fram och välja konto utifrån kontonummer, kontonamn och kontogrupp.

## Agent Usage Rules

- Välj alltid ett konto från tabellen. Hitta inte på egna kontonummer.
- Om ett konto är markerat med `Ja` under `Ej K2`, ska kontot inte användas när K2 tillämpas.
- Om flera konton verkar möjliga ska agenten välja det mest specifika kontot, inte gruppkontot.
- Om underlaget inte visar momssats, transaktionstyp, land eller omvänd betalningsskyldighet ska agenten fråga efter det innan konto väljs.
- Om samma kontonummer förekommer med olika namn ska agenten inte gissa; flagga konflikt och be om manuell kontroll.

## Kontoklasser - snabbguide

| Klass | Område | Användning för konto-val |
|---|---|---|
| 1xxx | Tillgångar | Anläggningstillgångar, kundfordringar, skattekonto, momsfordran, bank och kassa. |
| 2xxx | Eget kapital och skulder | Eget kapital, skatteskulder, moms, arbetsgivaravgifter, leverantörsskulder och upplupna kostnader. |
| 3xxx | Intäkter | Försäljning, fakturerade kostnader, rörelsens sidointäkter och övriga rörelseintäkter. |
| 4xxx | Inköp och varukostnader | Inköp av handelsvaror, material, tjänster, import, EU-inköp och omvänd betalningsskyldighet. |
| 5xxx | Lokaler, drift och försäljning | Lokalkostnader, transport, resor, reklam och PR. |
| 6xxx | Övriga externa kostnader | Kontorsmaterial, tele/data/post, försäkringar, externa tjänster, bankkostnader, konsultarvoden. |
| 7xxx | Personalkostnader | Löner, förmåner, pensionskostnader, arbetsgivaravgifter och övriga personalkostnader. |
| 8xxx | Finansiella poster och resultat | Ränteintäkter, räntekostnader, bokslutsdispositioner, skatt och årets resultat. |

## Momsregistrering - praktisk konto-vägledning

Den här sektionen är endast en vägledning för konto-val i en coding agent. Den ersätter inte bokföringsbedömning.

| Situation | Börja kontrollera dessa konton |
|---|---|
| Svensk försäljning med 25 % moms | 3001 och 2611 |
| Svensk försäljning med 12 % moms | 3002 och 2621 |
| Svensk försäljning med 6 % moms | 3003 och 2631 |
| Svensk momsfri försäljning | 3004 |
| Ingående moms på inköp | 2641 eller relevant 264x-konto |
| Redovisningskonto för moms | 2650 |
| Momsfordran | 1650 |
| Skattekonto | 1630 eller 2850 beroende på fordran/skuld-kontext |
| Inköp av tjänster från annat EU-land | 4535, 4536, 4537 eller 4538 beroende på momssats/momsfrihet |
| Inköp av tjänster från land utanför EU | 4531, 4532 eller 4533 beroende på momssats |
| Inköp i Sverige med omvänd betalningsskyldighet | 4425, 4426 eller 4427 beroende på momssats |

## Dubbletter eller konflikter i källan

| Konto | Namn i källan |
|---|---|
| 2087 | Bunden överkursfond; Insatsemission |
| 2120 | Periodiseringsfond 2020 |
| 2130 | Periodiseringsfond 2020 – nr 2 |

## Momsrelaterade konton

| Konto | Kontonamn | Kontogrupp | Ej K2 |
|---:|---|---|---|
| 1650 | Momsfordran | 16 ÖVRIGA KORTFRISTIGA FORDRINGAR | Nej |
| 2610 | Utgående moms, 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2611 | Utgående moms på försäljning inom Sverige, 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2612 | Utgående moms på egna uttag, 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2613 | Utgående moms för uthyrning, 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2614 | Utgående moms omvänd betalskyldighet, 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2615 | Utgående moms import av varor, 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2616 | Utgående moms VMB 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2618 | Vilande utgående moms, 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2620 | Utgående moms, 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2621 | Utgående moms på försäljning inom Sverige, 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2622 | Utgående moms på egna uttag, 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2623 | Utgående moms för uthyrning, 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2624 | Utgående moms omvänd betalningsskyldighet 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2625 | Utgående moms import av varor, 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2626 | Utgående moms VMB 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2628 | Vilande utgående moms, 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2630 | Utgående moms, 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2631 | Utgående moms på försäljning inom Sverige, 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2632 | Utgående moms på egna uttag, 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2633 | Utgående moms för uthyrning, 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2634 | Utgående moms omvänd betalningsskyldighet, 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2635 | Utgående moms import av varor, 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2636 | Utgående moms VMB 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2638 | Vilande utgående moms, 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2640 | Ingående moms | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2641 | Debiterad ingående moms | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2642 | Debiterad ingående moms i anslutning till frivillig betalningsskyldighet | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2645 | Beräknad ingående moms på förvärv från utlandet | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2646 | Ingående moms på uthyrning | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2647 | Ingående moms omvänd betalningsskyldighet varor och tjänster i Sverige | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2648 | Vilande ingående moms | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2649 | Ingående moms, blandad verksamhet | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2650 | Redovisningskonto för moms | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2660 | Punktskatter | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2670 | Utgående moms på försäljning inom EU, OSS | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2852 | Anståndsbelopp för moms, arbetsgivaravgifter och personalskatt | 28 ÖVRIGA KORTFRISTIGA SKULDER | Nej |
| 3001 | Försäljning inom Sverige, 25 % moms | 30 HUVUDINTÄKTER | Nej |
| 3002 | Försäljning inom Sverige, 12 % moms | 30 HUVUDINTÄKTER | Nej |
| 3003 | Försäljning inom Sverige, 6 % moms | 30 HUVUDINTÄKTER | Nej |
| 3004 | Försäljning inom Sverige, momsfri | 30 HUVUDINTÄKTER | Nej |
| 3106 | Försäljning varor till annat EU-land, momspliktig | 31  | Nej |
| 3108 | Försäljning varor till annat EU-land, momsfri | 31  | Nej |
| 3200 | Försäljning VMB och omvänd moms | 32  | Nej |
| 3231 | Försäljning inom byggsektorn, omvänd betalningsskyldighet moms | 32  | Nej |
| 3401 | Egna uttag momspliktiga, 25 % | 34  | Nej |
| 3402 | Egna uttag momspliktiga, 12 % | 34  | Nej |
| 3403 | Egna uttag momspliktiga, 6 % | 34  | Nej |
| 3404 | Egna uttag, momsfria | 34  | Nej |
| 3913 | Frivilligt momspliktiga hyresintäkter | 39 ÖVRIGA RÖRELSEINTÄKTER | Nej |
| 3914 | Övriga momspliktiga hyresintäkter | 39 ÖVRIGA RÖRELSEINTÄKTER | Nej |
| 4065 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 25 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4066 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 12 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4067 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 6 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4075 | Inköp av handelsvaror från annat EU- land, 25 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4076 | Inköp av handelsvaror från annat EU- land, 12 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4077 | Inköp av handelsvaror från annat EU- land, 6 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4078 | Inköp av handelsvaror från annat EU- land, momsfri | 40 INKÖP AV HANDELSVAROR | Nej |
| 4085 | Import av handelsvaror, 25 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4086 | Import av handelsvaror, 12 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4087 | Import av handelsvaror, 6 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4415 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 25 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4416 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 12 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4417 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 6 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4425 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 25 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4426 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 12 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4427 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 6 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4518 | Inköp av råvaror och material från annat EU-land, momsfri | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4531 | Inköp av tjänster från ett land utanför EU, 25 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4532 | Inköp av tjänster från ett land utanför EU, 12 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4533 | Inköp av tjänster från ett land utanför EU, 6 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4538 | Inköp av tjänster från annat EU-land, momsfri | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4545 | Import av råvaror och material, 25 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4546 | Import av råvaror och material, 12 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4547 | Import av råvaror och material, 6 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 6998 | Utländsk moms | 69 ÖVRIGA EXTERNA KOSTNADER | Nej |
| 6999 | Ingående moms, blandad verksamhet | 69 ÖVRIGA EXTERNA KOSTNADER | Nej |

## Försäljningskonton

| Konto | Kontonamn | Kontogrupp | Ej K2 |
|---:|---|---|---|
| 2611 | Utgående moms på försäljning inom Sverige, 25 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2621 | Utgående moms på försäljning inom Sverige, 12 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2631 | Utgående moms på försäljning inom Sverige, 6 % | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2670 | Utgående moms på försäljning inom EU, OSS | 26 MOMS OCH PUNKTSKATTER | Nej |
| 3000 | Försäljning inom Sverige | 30 HUVUDINTÄKTER | Nej |
| 3001 | Försäljning inom Sverige, 25 % moms | 30 HUVUDINTÄKTER | Nej |
| 3002 | Försäljning inom Sverige, 12 % moms | 30 HUVUDINTÄKTER | Nej |
| 3003 | Försäljning inom Sverige, 6 % moms | 30 HUVUDINTÄKTER | Nej |
| 3004 | Försäljning inom Sverige, momsfri | 30 HUVUDINTÄKTER | Nej |
| 3100 | Försäljning av varor utanför Sverige | 31  | Nej |
| 3105 | Försäljning varor till land utanför EU | 31  | Nej |
| 3106 | Försäljning varor till annat EU-land, momspliktig | 31  | Nej |
| 3108 | Försäljning varor till annat EU-land, momsfri | 31  | Nej |
| 3200 | Försäljning VMB och omvänd moms | 32  | Nej |
| 3211 | Försäljning positiv VMB 25 % | 32  | Nej |
| 3212 | Försäljning negativ VMB 25 % | 32  | Nej |
| 3231 | Försäljning inom byggsektorn, omvänd betalningsskyldighet moms | 32  | Nej |
| 3300 | Försäljning av tjänster utanför Sverige | 33  | Nej |
| 3305 | Försäljning tjänster till land utanför EU | 33  | Nej |
| 3308 | Försäljning tjänster till annat EU-land | 33  | Nej |
| 3400 | Försäljning, egna uttag | 34  | Nej |
| 3401 | Egna uttag momspliktiga, 25 % | 34  | Nej |
| 3402 | Egna uttag momspliktiga, 12 % | 34  | Nej |
| 3403 | Egna uttag momspliktiga, 6 % | 34  | Nej |
| 3404 | Egna uttag, momsfria | 34  | Nej |
| 3610 | Försäljning av material | 36 RÖRELSENS SIDOINTÄKTER | Nej |
| 3611 | Försäljning av råmaterial | 36 RÖRELSENS SIDOINTÄKTER | Nej |
| 3612 | Försäljning av skrot | 36 RÖRELSENS SIDOINTÄKTER | Nej |
| 3613 | Försäljning av förbrukningsmaterial | 36 RÖRELSENS SIDOINTÄKTER | Nej |
| 3619 | Försäljning av övrigt material | 36 RÖRELSENS SIDOINTÄKTER | Nej |
| 3671 | Försäljning av värdepapper | 36 RÖRELSENS SIDOINTÄKTER | Nej |
| 6000 | Övriga försäljningskostnader (gruppkonto) | 60 ÖVRIGA FÖRSÄLJNINGSKOSTNADER | Nej |
| 6050 | Försäljningsprovisioner | 60 ÖVRIGA FÖRSÄLJNINGSKOSTNADER | Nej |
| 6059 | Övriga försäljningsprovisionskostnader | 60 ÖVRIGA FÖRSÄLJNINGSKOSTNADER | Nej |
| 6060 | Kreditförsäljningskostnader | 60 ÖVRIGA FÖRSÄLJNINGSKOSTNADER | Nej |
| 6069 | Övriga kreditförsäljningskostnader | 60 ÖVRIGA FÖRSÄLJNINGSKOSTNADER | Nej |
| 6090 | Övriga försäljningskostnader | 60 ÖVRIGA FÖRSÄLJNINGSKOSTNADER | Nej |
| 6860 | Inhyrd marknads- och försäljningspersonal | 68 INHYRD PERSONAL | Nej |
| 8020 | Resultat vid försäljning av andelar i koncernföretag | 80 RESULTAT FRÅN ANDELAR I KONCERNFÖRETAG | Nej |
| 8120 | Resultat vid försäljning av andelar i intresseföretag och gemensamt styrda företag samt övriga företag som det finns ett ägarintresse i | 81 RESULTAT FRÅN ANDELAR I INTRESSEFÖRETAG OCH GEMENSAMT STYRDA FÖRETAG SAMT ÖVRIGA FÖRETAG SOM DET FINNS ETT ÄGARINTRESSE I | Nej |
| 8121 | Resultat vid försäljning av andelar i intresseföretag | 81 RESULTAT FRÅN ANDELAR I INTRESSEFÖRETAG OCH GEMENSAMT STYRDA FÖRETAG SAMT ÖVRIGA FÖRETAG SOM DET FINNS ETT ÄGARINTRESSE I | Nej |
| 8122 | Resultat vid försäljning av andelar i gemensamt styrda företag | 81 RESULTAT FRÅN ANDELAR I INTRESSEFÖRETAG OCH GEMENSAMT STYRDA FÖRETAG SAMT ÖVRIGA FÖRETAG SOM DET FINNS ETT ÄGARINTRESSE I | Nej |
| 8123 | Resultat vid försäljning av andelar i övriga företag som det finns ett ägarintresse i | 81 RESULTAT FRÅN ANDELAR I INTRESSEFÖRETAG OCH GEMENSAMT STYRDA FÖRETAG SAMT ÖVRIGA FÖRETAG SOM DET FINNS ETT ÄGARINTRESSE I | Nej |
| 8220 | Resultat vid försäljning av värdepapper i och långfristiga fordringar hos andra företag | 82 RESULTAT FRÅN ÖVRIGA VÄRDEPAPPER OCH LÅNGFRISTIGA FORDRINGAR (ANLÄGGNINGSTILLGÅNGAR) | Nej |
| 8221 | Resultat vid försäljning av andelar i andra företag | 82 RESULTAT FRÅN ÖVRIGA VÄRDEPAPPER OCH LÅNGFRISTIGA FORDRINGAR (ANLÄGGNINGSTILLGÅNGAR) | Nej |
| 8222 | Resultat vid försäljning av långfristiga fordringar hos andra företag | 82 RESULTAT FRÅN ÖVRIGA VÄRDEPAPPER OCH LÅNGFRISTIGA FORDRINGAR (ANLÄGGNINGSTILLGÅNGAR) | Nej |
| 8223 | Resultat vid försäljning av derivat (långfristiga värdepappersinnehav) | 82 RESULTAT FRÅN ÖVRIGA VÄRDEPAPPER OCH LÅNGFRISTIGA FORDRINGAR (ANLÄGGNINGSTILLGÅNGAR) | Nej |
| 8350 | Resultat vid försäljning av kortfristiga placeringar | 83 ÖVRIGA RÄNTEINTÄKTER OCH LIKNANDE RESULTATPOSTER | Nej |

## Inköpskonton

| Konto | Kontonamn | Kontogrupp | Ej K2 |
|---:|---|---|---|
| 4000 | Inköp av handelsvaror (gruppkonto) | 40 INKÖP AV HANDELSVAROR | Nej |
| 4010 | Inköp av handelsvaror i Sverige | 40 INKÖP AV HANDELSVAROR | Nej |
| 4060 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet | 40 INKÖP AV HANDELSVAROR | Nej |
| 4065 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 25 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4066 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 12 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4067 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 6 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4070 | Inköp av handelsvaror från annat EU-land | 40 INKÖP AV HANDELSVAROR | Nej |
| 4075 | Inköp av handelsvaror från annat EU- land, 25 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4076 | Inköp av handelsvaror från annat EU- land, 12 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4077 | Inköp av handelsvaror från annat EU- land, 6 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4078 | Inköp av handelsvaror från annat EU- land, momsfri | 40 INKÖP AV HANDELSVAROR | Nej |
| 4080 | Import av handelsvaror | 40 INKÖP AV HANDELSVAROR | Nej |
| 4085 | Import av handelsvaror, 25 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4086 | Import av handelsvaror, 12 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4087 | Import av handelsvaror, 6 % moms | 40 INKÖP AV HANDELSVAROR | Nej |
| 4090 | Erhållna rabatter (Handelsvaror) | 40 INKÖP AV HANDELSVAROR | Nej |
| 4091 | Erhållna kassarabatter (Handelsvaror) | 40 INKÖP AV HANDELSVAROR | Nej |
| 4092 | Erhållna mängdrabatter (inkl. bonus) (Handelsvaror) | 40 INKÖP AV HANDELSVAROR | Nej |
| 4099 | Övriga reduktioner av inköpspriser (Handelsvaror) | 40 INKÖP AV HANDELSVAROR | Nej |
| 4300 | Inköp av råvaror och material i Sverige (gruppkonto) | 43 INKÖP AV RÅVAROR OCH MATERIAL I SVERIGE (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4310 | Inköp av råvaror och material i Sverige | 43 INKÖP AV RÅVAROR OCH MATERIAL I SVERIGE (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4400 | Inköp av råvaror och material, tjänster m.m. i Sverige, omvänd betalningsskyldighet (gruppkonto) | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4410 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4415 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 25 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4416 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 12 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4417 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 6 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4420 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4425 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 25 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4426 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 12 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4427 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 6 % moms | 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4500 | Inköp av råvaror och material, tjänster m.m. från utlandet (gruppkonto) | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4510 | Inköp av råvaror och material från annat EU-land | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4515 | Inköp av råvaror och material från annat EU-land, 25 % | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4516 | Inköp av råvaror och material från annat EU-land, 12 % | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4517 | Inköp av råvaror och material från annat EU-land, 6 % | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4518 | Inköp av råvaror och material från annat EU-land, momsfri | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4530 | Inköp av tjänster m.m. från utlandet | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4531 | Inköp av tjänster från ett land utanför EU, 25 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4532 | Inköp av tjänster från ett land utanför EU, 12 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4533 | Inköp av tjänster från ett land utanför EU, 6 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4535 | Inköp av tjänster från annat EU-land, 25 % | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4536 | Inköp av tjänster från annat EU-land, 12 % | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4537 | Inköp av tjänster från annat EU-land, 6 % | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4538 | Inköp av tjänster från annat EU-land, momsfri | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4540 | Import av råvaror och material | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4545 | Import av råvaror och material, 25 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4546 | Import av råvaror och material, 12 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4547 | Import av råvaror och material, 6 % moms | 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4600 | Inköp av tjänster, underentreprenader och legoarbeten i Sverige (gruppkonto) | 46 INKÖP AV TJÄNSTER, UNDERENTREPRENADER OCH LEGOARBETEN I SVERIGE (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4610 | Inköp av tjänster och underentreprenader | 46 INKÖP AV TJÄNSTER, UNDERENTREPRENADER OCH LEGOARBETEN I SVERIGE (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4670 | Inköp av legoarbeten | 46 INKÖP AV TJÄNSTER, UNDERENTREPRENADER OCH LEGOARBETEN I SVERIGE (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4700 | Reduktion av inköpspriser (gruppkonto) | 47 REDUKTION AV INKÖPSPRISER (RÅVAROR OCH FÖRNÖDENHETER) | Nej |
| 4739 | Övriga reduktioner av inköpspriser (Råvaror och förnödenheter) | 47 REDUKTION AV INKÖPSPRISER (RÅVAROR OCH FÖRNÖDENHETER) | Nej |

## Skattekonton och skatteskulder

| Konto | Kontonamn | Kontogrupp | Ej K2 |
|---:|---|---|---|
| 1370 | Uppskjuten skattefordran | 13 FINANSIELLA ANLÄGGNINGSTILLGÅNGAR | Ja |
| 1630 | Avräkning för skatter och avgifter (skattekonto) | 16 ÖVRIGA KORTFRISTIGA FORDRINGAR | Nej |
| 1640 | Skattefordringar | 16 ÖVRIGA KORTFRISTIGA FORDRINGAR | Nej |
| 2190 | Övriga obeskattade reserver | 21 OBESKATTADE RESERVER | Nej |
| 2199 | Övriga obeskattade reserver | 21 OBESKATTADE RESERVER | Nej |
| 2240 | Avsättningar för uppskjutna skatter | 22 AVSÄTTNINGAR | Ja |
| 2250 | Övriga avsättningar för skatter | 22 AVSÄTTNINGAR | Nej |
| 2252 | Avsättningar för tvistiga skatter | 22 AVSÄTTNINGAR | Nej |
| 2253 | Avsättningar särskild löneskatt, deklarationspost | 22 AVSÄTTNINGAR | Nej |
| 2510 | Skatteskulder | 25 SKATTESKULDER | Nej |
| 2512 | Beräknad inkomstskatt | 25 SKATTESKULDER | Nej |
| 2513 | Beräknad fastighetsskatt/fastighetsavgift | 25 SKATTESKULDER | Nej |
| 2514 | Beräknad särskild löneskatt på pensionskostnader | 25 SKATTESKULDER | Nej |
| 2515 | Beräknad avkastningsskatt | 25 SKATTESKULDER | Nej |
| 2517 | Beräknad utländsk skatt | 25 SKATTESKULDER | Nej |
| 2518 | Betald F-skatt | 25 SKATTESKULDER | Nej |
| 2660 | Punktskatter | 26 MOMS OCH PUNKTSKATTER | Nej |
| 2710 | Personalskatt | 27 PERSONALENS SKATTER, AVGIFTER OCH LÖNEAVDRAG | Nej |
| 2730 | Lagstadgade sociala avgifter och särskild löneskatt | 27 PERSONALENS SKATTER, AVGIFTER OCH LÖNEAVDRAG | Nej |
| 2732 | Avräkning särskild löneskatt | 27 PERSONALENS SKATTER, AVGIFTER OCH LÖNEAVDRAG | Nej |
| 2850 | Avräkning för skatter och avgifter (skattekonto) | 28 ÖVRIGA KORTFRISTIGA SKULDER | Nej |
| 2852 | Anståndsbelopp för moms, arbetsgivaravgifter och personalskatt | 28 ÖVRIGA KORTFRISTIGA SKULDER | Nej |
| 2942 | Beräknad upplupen särskild löneskatt | 29 UPPLUPNA KOSTNADER OCH FÖRUTBETALDA INTÄKTER | Nej |
| 2943 | Beräknad upplupen särskild löneskatt på pensionskostnader, deklarationspost | 29 UPPLUPNA KOSTNADER OCH FÖRUTBETALDA INTÄKTER | Nej |
| 2944 | Beräknad upplupen avkastningsskatt på pensionskostnader | 29 UPPLUPNA KOSTNADER OCH FÖRUTBETALDA INTÄKTER | Nej |
| 3750 | Punktskatter | 37 INTÄKTSKORRIGERINGAR | Nej |
| 3751 | Intäktsförda punktskatter (kreditkonto) | 37 INTÄKTSKORRIGERINGAR | Nej |
| 3752 | Skuldförda punktskatter (debetkonto) | 37 INTÄKTSKORRIGERINGAR | Nej |
| 5191 | Fastighetsskatt/fastighetsavgift | 51 FASTIGHETSKOSTNADER | Nej |
| 5612 | Försäkring och skatt för personbilar, mc, m.m. | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5616 | Trängselskatt personbilar | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5622 | Försäkring och skatt lastbilar och bussar | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5626 | Trängselskatt lastbilar och bussar | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5632 | Försäkring och skatt truckar | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5642 | Försäkring och skatt arbetsmaskiner | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5646 | Trängselskatt arbetsmaskiner | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5652 | Försäkring och skatt traktorer | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5656 | Trängselskatt traktorer | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5672 | Försäkring och skatt fartyg och luftfartyg | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5682 | Försäkring och skatt rälsfordon | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5692 | Försäkring och skatt övriga transportmedel | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 5696 | Trängselskatt övriga transportmedel | 56 KOSTNADER FÖR TRANSPORTMEDEL | Nej |
| 6423 | Skatterådgivning – revisor | 64 FÖRVALTNINGSKOSTNADER | Nej |
| 6555 | Skatterådgivning inkl. insolvens- och konkursförv. | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6996 | Betald utländsk inkomstskatt | 69 ÖVRIGA EXTERNA KOSTNADER | Nej |
| 6997 | Obetald utländsk inkomstskatt | 69 ÖVRIGA EXTERNA KOSTNADER | Nej |
| 7321 | Skattefria traktamenten, Sverige | 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER | Nej |
| 7322 | Skattepliktiga traktamenten, Sverige | 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER | Nej |
| 7323 | Skattefria traktamenten, utlandet | 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER | Nej |
| 7324 | Skattepliktiga traktamenten, utlandet | 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER | Nej |
| 7331 | Skattefria bilersättningar | 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER | Nej |
| 7332 | Skattepliktiga bilersättningar | 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER | Nej |
| 7333 | Ersättning för trängselskatt, skattefri | 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER | Nej |
| 7391 | Kostnad för trängselskatteförmån | 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER | Nej |
| 7515 | Arbetsgivaravgifter på skattepliktiga kostnadsersättningar | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7530 | Särskild löneskatt | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7531 | Särskild löneskatt för vissa försäkringsersättningar m.m. | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7532 | Särskild löneskatt pensionskostnader, deklarationspost | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7533 | Särskild löneskatt för pensionskostnader | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7550 | Avkastningsskatt på pensionsmedel | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7551 | Avkastningsskatt 15 % försäkringsföretag m.fl. samt avsatt till pensioner | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7552 | Avkastningsskatt 15 % utländska pensionsförsäkringar | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7553 | Avkastningsskatt 30 % utländska försäkringsföretag m.fl. | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 7554 | Avkastningsskatt 30 % utländska kapitalförsäkringar | 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL | Nej |
| 8254 | Skattefria ränteintäkter, långfristiga tillgångar | 82 RESULTAT FRÅN ÖVRIGA VÄRDEPAPPER OCH LÅNGFRISTIGA FORDRINGAR (ANLÄGGNINGSTILLGÅNGAR) | Nej |
| 8255 | Avkastningsskatt kapitalplacering | 82 RESULTAT FRÅN ÖVRIGA VÄRDEPAPPER OCH LÅNGFRISTIGA FORDRINGAR (ANLÄGGNINGSTILLGÅNGAR) | Nej |
| 8314 | Skattefria ränteintäkter | 83 ÖVRIGA RÄNTEINTÄKTER OCH LIKNANDE RESULTATPOSTER | Nej |
| 8423 | Räntekostnader för skatter och avgifter | 84 RÄNTEKOSTNADER OCH LIKNANDE RESULTATPOSTER | Nej |
| 8910 | Skatt som belastar årets resultat | 89 SKATTER OCH ÅRETS RESULTAT | Nej |
| 8920 | Skatt på grund av ändrad beskattning | 89 SKATTER OCH ÅRETS RESULTAT | Nej |
| 8930 | Restituerad skatt | 89 SKATTER OCH ÅRETS RESULTAT | Nej |
| 8940 | Uppskjuten skatt | 89 SKATTER OCH ÅRETS RESULTAT | Ja |
| 8980 | Övriga skatter | 89 SKATTER OCH ÅRETS RESULTAT | Nej |

## Reklam, PR och marketing-kostnader

| Konto | Kontonamn | Kontogrupp | Ej K2 |
|---:|---|---|---|
| 3996 | Erhållna reklambidrag | 39 ÖVRIGA RÖRELSEINTÄKTER | Nej |
| 5900 | Reklam och PR (gruppkonto) | 59 REKLAM OCH PR | Nej |
| 5910 | Annonsering | 59 REKLAM OCH PR | Nej |
| 5920 | Utomhus- och trafikreklam | 59 REKLAM OCH PR | Nej |
| 5930 | Reklamtrycksaker och direktreklam | 59 REKLAM OCH PR | Nej |
| 5940 | Utställningar och mässor | 59 REKLAM OCH PR | Nej |
| 5950 | Butiksreklam och återförsäljarreklam | 59 REKLAM OCH PR | Nej |
| 5960 | Varuprover, reklamgåvor, presentreklam och tävlingar | 59 REKLAM OCH PR | Nej |
| 5970 | Film-, radio-, TV- och Internetreklam | 59 REKLAM OCH PR | Nej |
| 5980 | Sponsring | 59 REKLAM OCH PR | Nej |
| 5981 | Avdragsgill sponsring | 59 REKLAM OCH PR | Nej |
| 5982 | Ej avdragsgill sponsring | 59 REKLAM OCH PR | Nej |
| 5990 | Övriga kostnader för reklam och PR | 59 REKLAM OCH PR | Nej |

## Externa tjänster, IT och konsultarvoden

| Konto | Kontonamn | Kontogrupp | Ej K2 |
|---:|---|---|---|
| 6500 | Övriga externa tjänster (gruppkonto) | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6510 | Mätningskostnader | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6520 | Ritnings- och kopieringskostnader | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6530 | Redovisningstjänster | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6540 | IT-tjänster | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6550 | Konsultarvoden | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6551 | Arkitekttjänster | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6552 | Teknisk provning och analys | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6553 | Tekniska konsulttjänster | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6554 | Finansiell- och övrig ekonomisk rådgivning | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6555 | Skatterådgivning inkl. insolvens- och konkursförv. | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6556 | Köpta tjänster avseende forskning och utveckling | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6559 | Övriga konsultarvoden | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6560 | Serviceavgifter till branschorganisationer | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6570 | Bankkostnader | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6580 | Advokat- och rättegångskostnader | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |
| 6590 | Övriga externa tjänster | 65 ÖVRIGA EXTERNA TJÄNSTER | Nej |

# Fullständig BAS-kontoplan 2026

## 10 IMMATERIELLA ANLÄGGNINGSTILLGÅNGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1010 | Utvecklingsutgifter | Ja |
| 1011 | Balanserade utgifter för forskning och utveckling | Ja |
| 1012 | Balanserade utgifter för programvaror | Ja |
| 1018 | Ackumulerade nedskrivningar på balanserade utgifter | Ja |
| 1019 | Ackumulerade avskrivningar på balanserade utgifter | Ja |
| 1020 | Koncessioner m.m. | Nej |
| 1028 | Ackumulerade nedskrivningar på koncessioner m.m. | Nej |
| 1029 | Ackumulerade avskrivningar på koncessioner m.m. | Nej |
| 1030 | Patent | Nej |
| 1038 | Ackumulerade nedskrivningar på patent | Nej |
| 1039 | Ackumulerade avskrivningar på patent | Nej |
| 1040 | Licenser | Nej |
| 1048 | Ackumulerade nedskrivningar på licenser | Nej |
| 1049 | Ackumulerade avskrivningar på licenser | Nej |
| 1050 | Varumärken | Nej |
| 1058 | Ackumulerade nedskrivningar på varumärken | Nej |
| 1059 | Ackumulerade avskrivningar på varumärken | Nej |
| 1060 | Hyresrätter och liknande | Nej |
| 1068 | Ackumulerade nedskrivningar på hyresrätter och liknande | Nej |
| 1069 | Ackumulerade avskrivningar på hyresrätter och liknande | Nej |
| 1070 | Goodwill | Nej |
| 1078 | Ackumulerade nedskrivningar på goodwill | Nej |
| 1079 | Ackumulerade avskrivningar på goodwill | Nej |
| 1080 | Pågående projekt och förskott för immateriella anläggningstillgångar | Nej |
| 1081 | Pågående projekt för immateriella anläggningstillgångar | Nej |
| 1088 | Förskott för immateriella anläggningstillgångar | Nej |
| 1090 | Övriga immateriella anläggningstillgångar | Nej |
| 1092 | Tomträtter | Nej |
| 1098 | Ackumulerade nedskrivningar på övriga immateriella anläggningstillgångar | Nej |
| 1099 | Ackumulerade avskrivningar på övriga immateriella anläggningstillgångar | Nej |

## 11 BYGGNADER OCH MARK

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1110 | Byggnader | Nej |
| 1111 | Byggnader på egen mark | Nej |
| 1112 | Byggnader på annans mark | Nej |
| 1118 | Ackumulerade nedskrivningar på byggnader | Nej |
| 1119 | Ackumulerade avskrivningar på byggnader | Nej |
| 1120 | Förbättringsutgifter på annans fastighet | Nej |
| 1129 | Ackumulerade avskrivningar på förbättringsutgifter på annans fastighet | Nej |
| 1130 | Mark | Nej |
| 1140 | Tomter och obebyggda markområden | Nej |
| 1150 | Markanläggningar | Nej |
| 1158 | Ackumulerade nedskrivningar på markanläggningar | Nej |
| 1159 | Ackumulerade avskrivningar på markanläggningar | Nej |
| 1180 | Pågående nyanläggningar och förskott för byggnader och mark | Nej |
| 1181 | Pågående ny-, till- och ombyggnad | Nej |
| 1188 | Förskott för byggnader och mark | Nej |

## 12 MASKINER RESPEKTIVE INVENTARIER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1210 | Maskiner och andra tekniska anläggningar | Nej |
| 1211 | Maskiner och andra tekniska anläggningar i övrigt | Nej |
| 1212 | Byggnads- och markinventarier (för produktion) | Nej |
| 1214 | Datorer (för produktion) | Nej |
| 1216 | Arbetsfordon | Nej |
| 1217 | Finansiellt leasade maskiner | Nej |
| 1218 | Ackumulerade nedskrivningar på maskiner och andra tekniska anläggningar | Nej |
| 1219 | Ackumulerade avskrivningar på maskiner och andra tekniska anläggningar | Nej |
| 1220 | Inventarier, verktyg och installationer | Nej |
| 1221 | Inventarier, verktyg och installationer i övrigt | Nej |
| 1222 | Byggnads- och markinventarier (ej för produktion) | Nej |
| 1224 | Datorer (ej för produktion) | Nej |
| 1226 | Bilar och transportmedel (ej för produktion) | Nej |
| 1227 | Finansiellt leasade inventarier | Nej |
| 1228 | Ackumulerade nedskrivningar på inventarier, verktyg och installationer | Nej |
| 1229 | Ackumulerade avskrivningar på inventarier, verktyg och installationer | Nej |
| 1230 | (Fritt konto för Maskiner och andra tekniska anläggningar) | Nej |
| 1240 | (Fritt konto för Maskiner och andra tekniska anläggningar) | Nej |
| 1250 | (Fritt konto för Inventarier, verktyg och installationer) | Nej |
| 1260 | (Fritt konto för Inventarier, verktyg och installationer) | Nej |
| 1280 | Pågående nyanläggningar och förskott för maskiner respektive inventarier | Nej |
| 1281 | Pågående nyanläggningar, maskiner respektive inventarier | Nej |
| 1288 | Förskott för maskiner respektive inventarier | Nej |
| 1290 | Övriga materiella anläggningstillgångar | Nej |
| 1291 | Konst och liknande tillgångar | Nej |
| 1292 | Djur som klassificeras som anläggningstillgång | Nej |
| 1298 | Ackumulerade nedskrivningar på övriga materiella anläggningstillgångar | Nej |
| 1299 | Ackumulerade avskrivningar på övriga materiella anläggningstillgångar | Nej |

## 13 FINANSIELLA ANLÄGGNINGSTILLGÅNGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1310 | Andelar i koncernföretag | Nej |
| 1311 | Aktier i noterade svenska koncernföretag | Nej |
| 1312 | Aktier i onoterade svenska koncernföretag | Nej |
| 1313 | Aktier i noterade utländska koncernföretag | Nej |
| 1314 | Aktier i onoterade utländska koncernföretag | Nej |
| 1316 | Andra andelar i svenska koncernföretag | Nej |
| 1317 | Andra andelar i utländska koncernförertag | Nej |
| 1318 | Ackumulerade nedskrivningar av andelar i koncernföretag | Nej |
| 1320 | Långfristiga fordringar hos koncernföretag | Nej |
| 1321 | Långfristiga fordringar hos moderföretag | Nej |
| 1322 | Långfristiga fordringar hos dotterföretag | Nej |
| 1323 | Långfristiga fordringar hos andra koncernföretag | Nej |
| 1328 | Ackumulerade nedskrivningar av långfristiga fordringar hos koncernföretag | Nej |
| 1330 | Andelar i intresseföretag och gemensamt styrda företag samt övriga företag som det finns ett ägarintresse i | Nej |
| 1331 | Andelar i intresseföretag | Nej |
| 1332 | Ackumulerade nedskrivningar av andelar i intresseföretag | Nej |
| 1333 | Andelar i gemensamt styrda företag | Nej |
| 1334 | Ackumulerade nedskrivningar av andelar i gemensamt styrda företag | Nej |
| 1336 | Andelar i övriga företag som det finns ett ägarintresse i | Nej |
| 1337 | Ackumulerade nedskrivningar av andelar i övriga företag som det finns ett ägarintresse i | Nej |
| 1340 | Långfristiga fordringar hos intresseföretag och gemensamt styrda företag samt övriga företag som det finns ett ägarintresse i | Nej |
| 1341 | Långfristiga fordringar hos intresseföretag | Nej |
| 1342 | Ackumulerade nedskrivningar av långfristiga fordringar hos intresseföretag | Nej |
| 1343 | Långfristiga fordringar hos gemensamt styrda företag | Nej |
| 1344 | Ackumulerade nedskrivningar av långfristiga fordringar hos gemensamt styrda företag | Nej |
| 1346 | Långfristiga fordringar hos övriga företag som det finns ett ägarintresse i | Nej |
| 1347 | Ackumulerade nedskrivningar av långfristiga fordringar hos övriga företag som det finns ett ägarintresse i | Nej |
| 1350 | Andra långfristiga värdepappersinnehav | Nej |
| 1351 | Andelar i noterade företag | Nej |
| 1352 | Andra andelar | Nej |
| 1353 | Andelar i bostadsrättsföreningar | Nej |
| 1354 | Obligationer | Nej |
| 1356 | Andelar i ekonomiska föreningar | Nej |
| 1357 | Andelar i handelsbolag | Nej |
| 1358 | Ackumulerade nedskrivningar av andra långfristiga värdepappersinnehav | Nej |
| 1360 | Lån till delägare eller närstående, långfristig del | Nej |
| 1369 | Ackumulerade nedskrivningar av lån till delägare eller närstående, långfristig del | Nej |
| 1370 | Uppskjuten skattefordran | Ja |
| 1380 | Andra långfristiga fordringar | Nej |
| 1381 | Långfristiga reversfordringar | Nej |
| 1382 | Långfristiga fordringar hos anställda | Nej |
| 1383 | Lämnade depositioner, långfristiga | Nej |
| 1384 | Derivat | Nej |
| 1385 | Kapitalförsäkring | Nej |
| 1387 | Långfristiga kontraktsfordringar | Nej |
| 1388 | Långfristiga kundfordringar | Nej |
| 1389 | Ackumulerade nedskrivningar av andra långfristiga fordringar | Nej |

## 14 LAGER, PRODUKTER I ARBETE OCH PÅGÅENDE ARBETEN

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1410 | Lager av råvaror | Nej |
| 1419 | Förändring av lager av råvaror | Nej |
| 1420 | Lager av tillsatsmaterial och förnödenheter | Nej |
| 1429 | Förändring av lager av tillsatsmaterial och förnödenheter | Nej |
| 1440 | Produkter i arbete | Nej |
| 1449 | Förändring av produkter i arbete | Nej |
| 1450 | Lager av färdiga varor | Nej |
| 1459 | Förändring av lager av färdiga varor | Nej |
| 1460 | Lager av handelsvaror | Nej |
| 1465 | Lager av varor VMB | Nej |
| 1466 | Nedskrivning av varor VMB | Nej |
| 1467 | Lager av varor VMB förenklad | Nej |
| 1469 | Förändring av lager av handelsvaror | Nej |
| 1470 | Pågående arbeten | Nej |
| 1471 | Pågående arbeten, nedlagda kostnader | Nej |
| 1478 | Pågående arbeten, fakturering | Nej |
| 1479 | Förändring av pågående arbeten | Nej |
| 1480 | Förskott för varor och tjänster | Nej |
| 1481 | Remburser | Nej |
| 1489 | Övriga förskott till leverantörer | Nej |
| 1490 | Övriga lagertillgångar | Nej |
| 1491 | Lager av värdepapper | Nej |
| 1492 | Lager av fastigheter | Nej |
| 1493 | Djur som klassificeras som omsättningstillgång | Nej |

## 15 KUNDFORDRINGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1510 | Kundfordringar | Nej |
| 1511 | Kundfordringar | Nej |
| 1512 | Belånade kundfordringar (factoring) | Nej |
| 1513 | Kundfordringar – delad faktura | Nej |
| 1516 | Tvistiga kundfordringar | Nej |
| 1518 | Ej reskontraförda kundfordringar | Ja |
| 1519 | Nedskrivning av kundfordringar | Nej |
| 1520 | Växelfordringar | Nej |
| 1525 | Osäkra växelfordringar | Nej |
| 1529 | Nedskrivning av växelfordringar | Nej |
| 1530 | Kontraktsfordringar | Nej |
| 1531 | Kontraktsfordringar | Nej |
| 1532 | Belånade kontraktsfordringar | Nej |
| 1536 | Tvistiga kontraktsfordringar | Nej |
| 1539 | Nedskrivning av kontraktsfordringar | Nej |
| 1550 | Konsignationsfordringar | Nej |
| 1560 | Kundfordringar hos koncernföretag | Nej |
| 1561 | Kundfordringar hos moderföretag | Nej |
| 1562 | Kundfordringar hos dotterföretag | Nej |
| 1563 | Kundfordringar hos andra koncernföretag | Nej |
| 1568 | Ej reskontraförda kundfordringar hos koncernföretag | Nej |
| 1569 | Nedskrivning av kundfordringar hos koncernföretag | Nej |
| 1570 | Kundfordringar hos intresseföretag, gemensamt styrda företag och övriga företag som det finns ett ägarintresse i | Nej |
| 1571 | Kundfordringar hos intresseföretag | Nej |
| 1572 | Kundfordringar hos gemensamt styrda företag | Nej |
| 1573 | Kundfordringar hos övriga företag som det finns ett ägarintresse i | Nej |

## 16 ÖVRIGA KORTFRISTIGA FORDRINGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1610 | Kortfristiga fordringar hos anställda | Nej |
| 1611 | Reseförskott | Nej |
| 1612 | Kassaförskott | Nej |
| 1613 | Övriga förskott | Nej |
| 1614 | Tillfälliga lån till anställda | Nej |
| 1619 | Övriga fordringar hos anställda | Nej |
| 1620 | Upparbetad men ej fakturerad intäkt | Nej |
| 1630 | Avräkning för skatter och avgifter (skattekonto) | Nej |
| 1640 | Skattefordringar | Nej |
| 1650 | Momsfordran | Nej |
| 1660 | Kortfristiga fordringar hos koncernföretag | Nej |
| 1661 | Kortfristiga fordringar hos moderföretag | Nej |
| 1662 | Kortfristiga fordringar hos dotterföretag | Nej |
| 1663 | Kortfristiga fordringar hos andra koncernföretag | Nej |
| 1670 | Kortfristiga fordringar hos intresseföretag, gemensamt styrda företag och övriga företag som det finns ett ägarintresse i | Nej |
| 1671 | Kortfristiga fordringar hos intresseföretag | Nej |
| 1672 | Kortfristiga fordringar hos gemensamt styrda företag | Nej |
| 1673 | Kortfristiga fordringar hos övriga företag som det finns ett ägarintresse i | Nej |
| 1680 | Andra kortfristiga fordringar | Nej |
| 1681 | Utlägg för kunder | Nej |
| 1682 | Kortfristiga lånefordringar | Nej |
| 1683 | Derivat | Nej |
| 1684 | Kortfristiga fordringar hos leverantörer | Nej |
| 1685 | Kortfristiga fordringar hos delägare eller närstående | Nej |
| 1686 | Fordringar för kontokort och kuponger | Nej |
| 1687 | Kortfristig del av långfristiga fordringar | Nej |
| 1688 | Fordran arbetsmarknadsförsäkringar | Nej |
| 1689 | Övriga kortfristiga fordringar | Nej |
| 1690 | Fordringar för tecknat men ej inbetalt aktiekapital | Nej |

## 17 FÖRUTBETALDA KOSTNADER OCH UPPLUPNA INTÄKTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1710 | Förutbetalda hyreskostnader | Nej |
| 1720 | Förutbetalda leasingavgifter | Nej |
| 1730 | Förutbetalda försäkringspremier | Nej |
| 1740 | Förutbetalda räntekostnader | Nej |
| 1750 | Upplupna hyresintäkter | Nej |
| 1760 | Upplupna ränteintäkter | Nej |
| 1770 | Tillgångar av kostnadsnatur | Nej |
| 1780 | Upplupna avtalsintäkter | Nej |
| 1790 | Övriga förutbetalda kostnader och upplupna intäkter | Nej |

## 18 KORTFRISTIGA PLACERINGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1810 | Andelar i börsnoterade företag | Nej |
| 1820 | Obligationer | Nej |
| 1830 | Konvertibla skuldebrev | Nej |
| 1860 | Andelar i koncernföretag, kortfristigt | Nej |
| 1880 | Andra kortfristiga placeringar | Nej |
| 1886 | Derivat | Nej |
| 1889 | Andelar i övriga företag | Nej |
| 1890 | Nedskrivning av kortfristiga placeringar | Nej |

## 19 KASSA OCH BANK

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 1910 | Kassa | Nej |
| 1911 | Huvudkassa | Nej |
| 1912 | Kassa 2 | Nej |
| 1913 | Kassa 3 | Nej |
| 1920 | PlusGiro | Nej |
| 1930 | Företagskonto | Nej |
| 1940 | Övriga bankkonton | Nej |
| 1950 | Bankcertifikat | Nej |
| 1960 | Koncernkonto moderföretag | Nej |
| 1970 | Särskilda bankkonton | Nej |
| 1972 | Upphovsmannakonto | Nej |
| 1973 | Skogskonto | Nej |
| 1974 | Spärrade bankmedel | Nej |
| 1979 | Övriga särskilda bankkonton | Nej |
| 1980 | Valutakonton | Nej |
| 1990 | Redovisningsmedel | Nej |

## 20 EGET KAPITAL

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2010 | Eget kapital | Nej |
| 2011 | Egna varuuttag | Nej |
| 2013 | Övriga egna uttag | Nej |
| 2017 | Årets kapitaltillskott | Nej |
| 2018 | Övriga egna insättningar | Nej |
| 2019 | Årets resultat, delägare 1 | Nej |
| 2020 | Eget kapital | Nej |
| 2021 | Egna varuuttag | Nej |
| 2023 | Övriga egna uttag | Nej |
| 2027 | Årets kapitaltillskott | Nej |
| 2028 | Övriga egna insättningar | Nej |
| 2029 | Årets resultat, delägare 2 | Nej |
| 2030 | Eget kapital | Nej |
| 2031 | Egna varuuttag | Nej |
| 2033 | Övriga egna uttag | Nej |
| 2037 | Årets kapitaltillskott | Nej |
| 2038 | Övriga egna insättningar | Nej |
| 2039 | Årets resultat, delägare 3 | Nej |
| 2040 | Eget kapital | Nej |
| 2041 | Egna varuuttag | Nej |
| 2043 | Övriga egna uttag | Nej |
| 2047 | Årets kapitaltillskott | Nej |
| 2048 | Övriga egna insättningar | Nej |
| 2049 | Årets resultat, delägare 4 | Nej |
| 2050 | Avsättning till expansionsfond | Nej |
| 2060 | Eget kapital i ideella föreningar, stiftelser och registrerade trossamfund | Nej |
| 2061 | Kapital/stiftelsekapital/grundkapital | Nej |
| 2064 | Ackumulerat realisationsresultat | Nej |
| 2065 | Fond för verkligt värde | Nej |
| 2066 | Värdesäkringsfond | Nej |
| 2067 | Balanserat överskott eller underskott | Nej |
| 2068 | Överskott eller underskott från föregående år | Nej |
| 2069 | Årets resultat | Nej |
| 2070 | Ändamålsbestämda medel | Nej |
| 2071 | Ändamål 1 | Nej |
| 2072 | Ändamål 2 | Nej |
| 2080 | Bundet eget kapital | Nej |
| 2081 | Aktiekapital | Nej |
| 2082 | Ej registrerat aktiekapital | Nej |
| 2083 | Medlemsinsatser | Nej |
| 2084 | Förlagsinsatser | Nej |
| 2085 | Uppskrivningsfond | Nej |
| 2086 | Reservfond | Nej |
| 2087 | Bunden överkursfond | Nej |
| 2087 | Insatsemission | Nej |
| 2088 | Fond för yttre underhåll | Nej |
| 2089 | Fond för utvecklingsutgifter | Ja |
| 2090 | Fritt eget kapital | Nej |
| 2091 | Balanserad vinst eller förlust | Nej |
| 2092 | Mottagna/lämnade koncernbidrag | Ja |
| 2093 | Erhållna aktieägartillskott | Nej |
| 2094 | Egna aktier | Nej |
| 2095 | Fusionsresultat | Nej |
| 2096 | Fond för verkligt värde | Ja |
| 2097 | Fri överkursfond | Nej |
| 2098 | Vinst eller förlust från föregående år | Nej |
| 2099 | Årets resultat | Nej |

## 21 OBESKATTADE RESERVER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2110 | Periodiseringsfonder | Nej |
| 2120 | Periodiseringsfond 2020 | Nej |
| 2120 | Periodiseringsfond 2020 | Nej |
| 2121 | Periodiseringsfond 2021 | Nej |
| 2122 | Periodiseringsfond 2022 | Nej |
| 2123 | Periodiseringsfond 2023 | Nej |
| 2124 | Periodiseringsfond 2024 | Nej |
| 2125 | Periodiseringsfond 2025 | Nej |
| 2126 | Periodiseringsfond 2026 | Nej |
| 2127 | Periodiseringsfond 2027 | Nej |
| 2129 | Periodiseringsfond 2019 | Nej |
| 2130 | Periodiseringsfond 2020 – nr 2 | Nej |
| 2130 | Periodiseringsfond 2020 – nr 2 | Nej |
| 2131 | Periodiseringsfond 2021 – nr 2 | Nej |
| 2132 | Periodiseringsfond 2022 – nr 2 | Nej |
| 2133 | Periodiseringsfond 2023 – nr 2 | Nej |
| 2134 | Periodiseringsfond 2024 – nr 2 | Nej |
| 2135 | Periodiseringsfond 2025 - nr 2 | Nej |
| 2136 | Periodiseringsfond 2026 – nr 2 | Nej |
| 2137 | Periodiseringsfond 2027 - nr 2 | Nej |
| 2139 | Periodiseringsfond 2019 – nr 2 | Nej |
| 2150 | Ackumulerade överavskrivningar | Nej |
| 2151 | Ackumulerade överavskrivningar på immateriella anläggningstillgångar | Nej |
| 2152 | Ackumulerade överavskrivningar på byggnader och markanläggningar | Nej |
| 2153 | Ackumulerade överavskrivningar på maskiner respektive inventarier | Nej |
| 2160 | Ersättningsfond | Nej |
| 2161 | Ersättningsfond maskiner och inventarier | Nej |
| 2162 | Ersättningsfond byggnader och markanläggningar | Nej |
| 2164 | Ersättningsfond för djurlager i jordbruk och renskötsel | Nej |
| 2190 | Övriga obeskattade reserver | Nej |
| 2196 | Lagerreserv | Nej |
| 2199 | Övriga obeskattade reserver | Nej |

## 22 AVSÄTTNINGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2210 | Avsättningar för pensioner enligt tryggandelagen | Nej |
| 2220 | Avsättningar för garantier | Nej |
| 2230 | Övriga avsättningar för pensioner och liknande förpliktelser | Nej |
| 2240 | Avsättningar för uppskjutna skatter | Ja |
| 2250 | Övriga avsättningar för skatter | Nej |
| 2252 | Avsättningar för tvistiga skatter | Nej |
| 2253 | Avsättningar särskild löneskatt, deklarationspost | Nej |
| 2290 | Övriga avsättningar | Nej |

## 23 LÅNGFRISTIGA SKULDER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2310 | Obligations- och förlagslån | Nej |
| 2320 | Konvertibla lån och liknande | Nej |
| 2321 | Konvertibla lån | Nej |
| 2322 | Lån förenade med optionsrätt | Nej |
| 2323 | Vinstandelslån | Nej |
| 2324 | Kapitalandelslån | Nej |
| 2330 | Kontokredit | Nej |
| 2340 | Byggnadskreditiv | Nej |
| 2350 | Andra långfristiga skulder till kreditinstitut | Nej |
| 2351 | Fastighetslån, långfristig del | Nej |
| 2355 | Långfristiga lån i utländsk valuta från kreditinstitut | Nej |
| 2359 | Övriga långfristiga lån från kreditinstitut | Nej |
| 2360 | Långfristiga skulder till koncernföretag | Nej |
| 2361 | Långfristiga skulder till moderföretag | Nej |
| 2362 | Långfristiga skulder till dotterföretag | Nej |
| 2363 | Långfristiga skulder till andra koncernföretag | Nej |
| 2370 | Långfristiga skulder till intresseföretag, gemensamt styrda företag och övriga företag som det finns ett ägarintresse i | Nej |
| 2371 | Långfristiga skulder till intresseföretag | Nej |
| 2372 | Långfristiga skulder till gemensamt styrda företag | Nej |
| 2373 | Långfristiga skulder till övriga företag som det finns ett ägarintresse i | Nej |
| 2390 | Övriga långfristiga skulder | Nej |
| 2391 | Avbetalningskontrakt, långfristig del | Nej |
| 2392 | Villkorliga långfristiga skulder | Nej |
| 2393 | Lån från närstående personer, långfristig del | Nej |
| 2394 | Långfristiga leverantörskrediter | Nej |
| 2395 | Andra långfristiga lån i utländsk valuta | Nej |
| 2396 | Derivat | Nej |
| 2397 | Mottagna depositioner, långfristiga | Nej |
| 2399 | Övriga långfristiga skulder | Nej |

## 24 KORTFRISTIGA SKULDER TILL KREDITINSTITUT, KUNDER OCH LEVERANTÖRER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2410 | Andra kortfristiga låneskulder till kreditinstitut | Nej |
| 2411 | Kortfristiga lån från kreditinstitut | Nej |
| 2412 | Byggnadskreditiv, kortfristig del | Nej |
| 2417 | Kortfristig del av långfristiga skulder till kreditinstitut | Nej |
| 2419 | Övriga kortfristiga skulder till kreditinstitut | Nej |
| 2420 | Förskott från kunder | Nej |
| 2421 | Ej inlösta presentkort | Nej |
| 2429 | Övriga förskott från kunder | Nej |
| 2430 | Pågående arbeten | Nej |
| 2431 | Pågående arbeten, fakturering | Nej |
| 2438 | Pågående arbeten, nedlagda kostnader | Nej |
| 2439 | Beräknad förändring av pågående arbeten | Nej |
| 2440 | Leverantörsskulder | Nej |
| 2441 | Leverantörsskulder | Nej |
| 2443 | Konsignationsskulder | Nej |
| 2445 | Tvistiga leverantörsskulder | Nej |
| 2448 | Ej reskontraförda leverantörsskulder | Ja |
| 2450 | Fakturerad men ej upparbetad intäkt | Nej |
| 2460 | Leverantörsskulder till koncernföretag | Nej |
| 2461 | Leverantörsskulder till moderföretag | Nej |
| 2462 | Leverantörsskulder till dotterföretag | Nej |
| 2463 | Leverantörsskulder till andra koncernföretag | Nej |
| 2470 | Leverantörsskulder till intresseföretag, gemensamt styrda företag och övriga företag som det finns ett ägarintresse i | Nej |
| 2471 | Leverantörsskulder till intresseföretag | Nej |
| 2472 | Leverantörsskulder till gemensamt styrda företag | Nej |
| 2473 | Leverantörsskulder till övriga företag som det finns ett ägarintresse i | Nej |
| 2480 | Kontokredit, kortfristig | Nej |
| 2490 | Övriga kortfristiga skulder till kreditinstitut, kunder och leverantörer | Nej |
| 2491 | Avräkning spelarrangörer | Nej |
| 2492 | Växelskulder | Nej |
| 2499 | Andra övriga kortfristiga skulder | Nej |

## 25 SKATTESKULDER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2510 | Skatteskulder | Nej |
| 2512 | Beräknad inkomstskatt | Nej |
| 2513 | Beräknad fastighetsskatt/fastighetsavgift | Nej |
| 2514 | Beräknad särskild löneskatt på pensionskostnader | Nej |
| 2515 | Beräknad avkastningsskatt | Nej |
| 2517 | Beräknad utländsk skatt | Nej |
| 2518 | Betald F-skatt | Nej |

## 26 MOMS OCH PUNKTSKATTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2610 | Utgående moms, 25 % | Nej |
| 2611 | Utgående moms på försäljning inom Sverige, 25 % | Nej |
| 2612 | Utgående moms på egna uttag, 25 % | Nej |
| 2613 | Utgående moms för uthyrning, 25 % | Nej |
| 2614 | Utgående moms omvänd betalskyldighet, 25 % | Nej |
| 2615 | Utgående moms import av varor, 25 % | Nej |
| 2616 | Utgående moms VMB 25 % | Nej |
| 2618 | Vilande utgående moms, 25 % | Nej |
| 2620 | Utgående moms, 12 % | Nej |
| 2621 | Utgående moms på försäljning inom Sverige, 12 % | Nej |
| 2622 | Utgående moms på egna uttag, 12 % | Nej |
| 2623 | Utgående moms för uthyrning, 12 % | Nej |
| 2624 | Utgående moms omvänd betalningsskyldighet 12 % | Nej |
| 2625 | Utgående moms import av varor, 12 % | Nej |
| 2626 | Utgående moms VMB 12 % | Nej |
| 2628 | Vilande utgående moms, 12 % | Nej |
| 2630 | Utgående moms, 6 % | Nej |
| 2631 | Utgående moms på försäljning inom Sverige, 6 % | Nej |
| 2632 | Utgående moms på egna uttag, 6 % | Nej |
| 2633 | Utgående moms för uthyrning, 6 % | Nej |
| 2634 | Utgående moms omvänd betalningsskyldighet, 6 % | Nej |
| 2635 | Utgående moms import av varor, 6 % | Nej |
| 2636 | Utgående moms VMB 6 % | Nej |
| 2638 | Vilande utgående moms, 6 % | Nej |
| 2640 | Ingående moms | Nej |
| 2641 | Debiterad ingående moms | Nej |
| 2642 | Debiterad ingående moms i anslutning till frivillig betalningsskyldighet | Nej |
| 2645 | Beräknad ingående moms på förvärv från utlandet | Nej |
| 2646 | Ingående moms på uthyrning | Nej |
| 2647 | Ingående moms omvänd betalningsskyldighet varor och tjänster i Sverige | Nej |
| 2648 | Vilande ingående moms | Nej |
| 2649 | Ingående moms, blandad verksamhet | Nej |
| 2650 | Redovisningskonto för moms | Nej |
| 2660 | Punktskatter | Nej |
| 2670 | Utgående moms på försäljning inom EU, OSS | Nej |

## 27 PERSONALENS SKATTER, AVGIFTER OCH LÖNEAVDRAG

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2710 | Personalskatt | Nej |
| 2730 | Lagstadgade sociala avgifter och särskild löneskatt | Nej |
| 2731 | Avräkning lagstadgade sociala avgifter | Nej |
| 2732 | Avräkning särskild löneskatt | Nej |
| 2740 | Avtalade sociala avgifter | Nej |
| 2750 | Utmätning i lön m.m. | Nej |
| 2760 | Semestermedel | Nej |
| 2761 | Avräkning semesterlöner | Nej |
| 2762 | Semesterlönekassa | Nej |
| 2790 | Övriga löneavdrag | Nej |
| 2791 | Personalens intressekonto | Nej |
| 2792 | Lönsparande | Nej |
| 2793 | försäkringspremier | Nej |
| 2794 | Fackföreningsavgifter | Nej |
| 2795 | Mätnings- och granskningsarvoden | Nej |
| 2799 | Övriga löneavdrag | Nej |

## 28 ÖVRIGA KORTFRISTIGA SKULDER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2810 | Avräkning för factoring och belånade kontraktsfordringar | Nej |
| 2811 | Avräkning för factoring | Nej |
| 2812 | Avräkning för belånade kontraktsfordringar | Nej |
| 2820 | Kortfristiga skulder till anställda | Nej |
| 2821 | Löneskulder | Nej |
| 2822 | Reseräkningar | Nej |
| 2823 | Tantiem, gratifikationer | Nej |
| 2829 | Övriga kortfristiga skulder till anställda | Nej |
| 2830 | Avräkning för annans räkning | Nej |
| 2840 | Kortfristiga låneskulder | Nej |
| 2841 | Kortfristig del av långfristiga skulder | Nej |
| 2849 | Övriga kortfristiga låneskulder | Nej |
| 2850 | Avräkning för skatter och avgifter (skattekonto) | Nej |
| 2852 | Anståndsbelopp för moms, arbetsgivaravgifter och personalskatt | Nej |
| 2860 | Kortfristiga skulder till koncernföretag | Nej |
| 2861 | Kortfristiga skulder till moderföretag | Nej |
| 2862 | Kortfristiga skulder till dotterföretag | Nej |
| 2863 | Kortfristiga skulder till andra koncernföretag | Nej |
| 2870 | Kortfristiga skulder till intresseföretag, gemensamt styrda företag och övriga företag som det finns ett ägarintresse i | Nej |
| 2871 | Kortfristiga skulder till intresseföretag | Nej |
| 2872 | Kortfristiga skulder till gemensamt styrda företag | Nej |
| 2873 | Kortfristiga skulder till övriga företag som det finns ett ägarintresse i | Nej |
| 2880 | Skuld erhållna bidrag | Nej |
| 2890 | Övriga kortfristiga skulder | Nej |
| 2891 | Skulder under indrivning | Nej |
| 2892 | Inre reparationsfond/underhållsfond | Nej |
| 2893 | Skulder till närstående personer, kortfristig del | Nej |
| 2895 | Derivat (kortfristiga skulder) | Nej |
| 2897 | Mottagna depositioner, kortfristiga | Nej |
| 2898 | Outtagen vinstutdelning | Nej |
| 2899 | Övriga kortfristiga skulder | Nej |

## 29 UPPLUPNA KOSTNADER OCH FÖRUTBETALDA INTÄKTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 2910 | Upplupna löner | Nej |
| 2911 | Löneskulder | Nej |
| 2912 | Ackordsöverskott | Nej |
| 2919 | Övriga upplupna löner | Nej |
| 2920 | Upplupna semesterlöner | Nej |
| 2930 | Upplupna pensionskostnader | Nej |
| 2931 | Upplupna pensionsutbetalningar | Nej |
| 2940 | Upplupna lagstadgade sociala och andra avgifter | Nej |
| 2941 | Beräknade upplupna lagstadgade sociala avgifter | Nej |
| 2942 | Beräknad upplupen särskild löneskatt | Nej |
| 2943 | Beräknad upplupen särskild löneskatt på pensionskostnader, deklarationspost | Nej |
| 2944 | Beräknad upplupen avkastningsskatt på pensionskostnader | Nej |
| 2950 | Upplupna avtalade sociala avgifter | Nej |
| 2951 | Upplupna avtalade arbetsmarknadsförsäkringar | Nej |
| 2959 | Upplupna avtalade pensionsförsäkringsavgifter, deklarationspost | Nej |
| 2960 | Upplupna räntekostnader | Nej |
| 2970 | Förutbetalda intäkter | Nej |
| 2971 | Förutbetalda hyresintäkter | Nej |
| 2972 | Förutbetalda medlemsavgifter | Nej |
| 2979 | Övriga förutbetalda intäkter | Nej |
| 2980 | Upplupna avtalskostnader | Nej |
| 2990 | Övriga upplupna kostnader och förutbetalda intäkter | Nej |
| 2991 | Beräknat arvode för bokslut | Nej |
| 2992 | Beräknat arvode för revision | Nej |
| 2993 | Ospecificerad skuld till leverantörer | Nej |
| 2995 | Ej ankomna leverantörsfakturor | Nej |
| 2998 | Övriga upplupna kostnader och förutbetalda intäkter | Nej |
| 2999 | OBS-konto | Nej |

## 30 HUVUDINTÄKTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3000 | Försäljning inom Sverige | Nej |
| 3001 | Försäljning inom Sverige, 25 % moms | Nej |
| 3002 | Försäljning inom Sverige, 12 % moms | Nej |
| 3003 | Försäljning inom Sverige, 6 % moms | Nej |
| 3004 | Försäljning inom Sverige, momsfri | Nej |

## 31 

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3100 | Försäljning av varor utanför Sverige | Nej |
| 3105 | Försäljning varor till land utanför EU | Nej |
| 3106 | Försäljning varor till annat EU-land, momspliktig | Nej |
| 3108 | Försäljning varor till annat EU-land, momsfri | Nej |

## 32 

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3200 | Försäljning VMB och omvänd moms | Nej |
| 3211 | Försäljning positiv VMB 25 % | Nej |
| 3212 | Försäljning negativ VMB 25 % | Nej |
| 3231 | Försäljning inom byggsektorn, omvänd betalningsskyldighet moms | Nej |

## 33 

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3300 | Försäljning av tjänster utanför Sverige | Nej |
| 3305 | Försäljning tjänster till land utanför EU | Nej |
| 3308 | Försäljning tjänster till annat EU-land | Nej |

## 34 

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3400 | Försäljning, egna uttag | Nej |
| 3401 | Egna uttag momspliktiga, 25 % | Nej |
| 3402 | Egna uttag momspliktiga, 12 % | Nej |
| 3403 | Egna uttag momspliktiga, 6 % | Nej |
| 3404 | Egna uttag, momsfria | Nej |

## 35 FAKTURERADE KOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3500 | Fakturerade kostnader (gruppkonto) | Nej |
| 3510 | Fakturerat emballage | Nej |
| 3511 | Fakturerat emballage | Nej |
| 3518 | Returnerat emballage | Nej |
| 3520 | Fakturerade frakter | Nej |
| 3521 | Fakturerade frakter, EU-land | Nej |
| 3522 | Fakturerade frakter, export | Nej |
| 3530 | Fakturerade tull- och speditionskostnader m.m. | Nej |
| 3540 | Faktureringsavgifter | Nej |
| 3541 | Faktureringsavgifter, EU-land | Nej |
| 3542 | Faktureringsavgifter, export | Nej |
| 3550 | Fakturerade resekostnader | Nej |
| 3560 | Fakturerade kostnader till koncernföretag | Nej |
| 3561 | Fakturerade kostnader till moderföretag | Nej |
| 3562 | Fakturerade kostnader till dotterföretag | Nej |
| 3563 | Fakturerade kostnader till andra koncernföretag | Nej |
| 3570 | Fakturerade kostnader till intresseföretag, gemensamt styrda företag och övriga företag som det finns ett ägarintresse i | Nej |
| 3590 | Övriga fakturerade kostnader | Nej |

## 36 RÖRELSENS SIDOINTÄKTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3600 | Rörelsens sidointäkter (gruppkonto) | Nej |
| 3610 | Försäljning av material | Nej |
| 3611 | Försäljning av råmaterial | Nej |
| 3612 | Försäljning av skrot | Nej |
| 3613 | Försäljning av förbrukningsmaterial | Nej |
| 3619 | Försäljning av övrigt material | Nej |
| 3620 | Tillfällig uthyrning av personal | Nej |
| 3630 | Tillfällig uthyrning av transportmedel | Nej |
| 3670 | Intäkter från värdepapper | Nej |
| 3671 | Försäljning av värdepapper | Nej |
| 3672 | Utdelning från värdepapper | Nej |
| 3679 | Övriga intäkter från värdepapper | Nej |
| 3680 | Management fees | Nej |
| 3690 | Övriga sidointäkter | Nej |

## 37 INTÄKTSKORRIGERINGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3700 | Intäktskorrigeringar (gruppkonto) | Nej |
| 3710 | Ofördelade intäktsreduktioner | Nej |
| 3730 | Lämnade rabatter | Nej |
| 3731 | Lämnade kassarabatter | Nej |
| 3732 | Lämnade mängdrabatter | Nej |
| 3740 | Öres- och kronutjämning | Nej |
| 3750 | Punktskatter | Nej |
| 3751 | Intäktsförda punktskatter (kreditkonto) | Nej |
| 3752 | Skuldförda punktskatter (debetkonto) | Nej |
| 3790 | Övriga intäktskorrigeringar | Nej |

## 38 AKTIVERAT ARBETE FÖR EGEN RÄKNING

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3800 | Aktiverat arbete för egen räkning (gruppkonto) | Nej |
| 3840 | Aktiverat arbete (material) | Nej |
| 3850 | Aktiverat arbete (omkostnader) | Nej |
| 3870 | Aktiverat arbete (personal) | Nej |

## 39 ÖVRIGA RÖRELSEINTÄKTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 3900 | Övriga rörelseintäkter (gruppkonto) | Nej |
| 3910 | Hyres- och arrendeintäkter | Nej |
| 3911 | Hyresintäkter | Nej |
| 3912 | Arrendeintäkter | Nej |
| 3913 | Frivilligt momspliktiga hyresintäkter | Nej |
| 3914 | Övriga momspliktiga hyresintäkter | Nej |
| 3920 | Provisionsintäkter, licensintäkter och royalties | Nej |
| 3921 | Provisionsintäkter | Nej |
| 3922 | Licensintäkter och royalties | Nej |
| 3925 | Franchiseintäkter | Nej |
| 3940 | Orealiserade negativa/positiva värdeförändringar på säkringsinstrument | Ja |
| 3950 | Återvunna, tidigare avskrivna kundfordringar | Nej |
| 3960 | Valutakursvinster på fordringar och skulder av rörelsekaraktär | Nej |
| 3970 | Vinst vid avyttring av immateriella och materiella anläggningstillgångar | Nej |
| 3971 | Vinst vid avyttring av immateriella anläggningstillgångar | Nej |
| 3972 | Vinst vid avyttring av byggnader och mark | Nej |
| 3973 | Vinst vid avyttring av maskiner och inventarier | Nej |
| 3980 | Erhållna offentliga bidrag | Nej |
| 3981 | Erhållna EU-bidrag | Nej |
| 3985 | Erhållna statliga bidrag | Nej |
| 3987 | Erhållna kommunala bidrag | Nej |
| 3988 | Erhållna offentliga bidrag för personal | Nej |
| 3989 | Övriga erhållna offentliga bidrag | Nej |
| 3990 | Övriga ersättningar, bidrag och intäkter | Nej |
| 3991 | Konfliktersättning | Nej |
| 3992 | Erhållna skadestånd | Nej |
| 3993 | Erhållna donationer och gåvor | Nej |
| 3994 | Försäkringsersättningar | Nej |
| 3995 | Erhållet ackord på skulder av rörelsekaraktär | Nej |
| 3996 | Erhållna reklambidrag | Nej |
| 3997 | Sjuklöneersättning | Nej |
| 3998 | Återbäring av överskott från försäkringsföretag | Nej |
| 3999 | Övriga rörelseintäkter | Nej |

## 40 INKÖP AV HANDELSVAROR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4000 | Inköp av handelsvaror (gruppkonto) | Nej |
| 4010 | Inköp av handelsvaror i Sverige | Nej |
| 4060 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet | Nej |
| 4065 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 25 % moms | Nej |
| 4066 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 12 % moms | Nej |
| 4067 | Inköp av handelsvaror i Sverige, omvänd betalningsskyldighet, 6 % moms | Nej |
| 4070 | Inköp av handelsvaror från annat EU-land | Nej |
| 4075 | Inköp av handelsvaror från annat EU- land, 25 % moms | Nej |
| 4076 | Inköp av handelsvaror från annat EU- land, 12 % moms | Nej |
| 4077 | Inköp av handelsvaror från annat EU- land, 6 % moms | Nej |
| 4078 | Inköp av handelsvaror från annat EU- land, momsfri | Nej |
| 4080 | Import av handelsvaror | Nej |
| 4085 | Import av handelsvaror, 25 % moms | Nej |
| 4086 | Import av handelsvaror, 12 % moms | Nej |
| 4087 | Import av handelsvaror, 6 % moms | Nej |
| 4090 | Erhållna rabatter (Handelsvaror) | Nej |
| 4091 | Erhållna kassarabatter (Handelsvaror) | Nej |
| 4092 | Erhållna mängdrabatter (inkl. bonus) (Handelsvaror) | Nej |
| 4099 | Övriga reduktioner av inköpspriser (Handelsvaror) | Nej |

## 42 SÅLDA HANDELSVAROR VMB

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4200 | Sålda handelsvaror VMB (gruppkonto) | Nej |
| 4210 | Sålda handelsvaror VMB | Nej |
| 4211 | Sålda handelsvaror positiv VMB 25 % | Nej |
| 4212 | Sålda handelsvaror negativ VMB 25 % | Nej |

## 43 INKÖP AV RÅVAROR OCH MATERIAL I SVERIGE (RÅVAROR OCH FÖRNÖDENHETER)

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4300 | Inköp av råvaror och material i Sverige (gruppkonto) | Nej |
| 4310 | Inköp av råvaror och material i Sverige | Nej |

## 44 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. I SVERIGE, OMVÄND BETALNINGSSKYLDIGHET (RÅVAROR OCH FÖRNÖDENHETER)

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4400 | Inköp av råvaror och material, tjänster m.m. i Sverige, omvänd betalningsskyldighet (gruppkonto) | Nej |
| 4410 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet | Nej |
| 4415 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 25 % moms | Nej |
| 4416 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 12 % moms | Nej |
| 4417 | Inköp av råvaror och material i Sverige, omvänd betalningsskyldighet, 6 % moms | Nej |
| 4420 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet | Nej |
| 4425 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 25 % moms | Nej |
| 4426 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 12 % moms | Nej |
| 4427 | Inköp av tjänster i Sverige, omvänd betalningsskyldighet, 6 % moms | Nej |

## 45 INKÖP AV RÅVAROR OCH MATERIAL, TJÄNSTER M.M. FRÅN UTLANDET (RÅVAROR OCH FÖRNÖDENHETER)

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4500 | Inköp av råvaror och material, tjänster m.m. från utlandet (gruppkonto) | Nej |
| 4510 | Inköp av råvaror och material från annat EU-land | Nej |
| 4515 | Inköp av råvaror och material från annat EU-land, 25 % | Nej |
| 4516 | Inköp av råvaror och material från annat EU-land, 12 % | Nej |
| 4517 | Inköp av råvaror och material från annat EU-land, 6 % | Nej |
| 4518 | Inköp av råvaror och material från annat EU-land, momsfri | Nej |
| 4530 | Inköp av tjänster m.m. från utlandet | Nej |
| 4531 | Inköp av tjänster från ett land utanför EU, 25 % moms | Nej |
| 4532 | Inköp av tjänster från ett land utanför EU, 12 % moms | Nej |
| 4533 | Inköp av tjänster från ett land utanför EU, 6 % moms | Nej |
| 4535 | Inköp av tjänster från annat EU-land, 25 % | Nej |
| 4536 | Inköp av tjänster från annat EU-land, 12 % | Nej |
| 4537 | Inköp av tjänster från annat EU-land, 6 % | Nej |
| 4538 | Inköp av tjänster från annat EU-land, momsfri | Nej |
| 4540 | Import av råvaror och material | Nej |
| 4545 | Import av råvaror och material, 25 % moms | Nej |
| 4546 | Import av råvaror och material, 12 % moms | Nej |
| 4547 | Import av råvaror och material, 6 % moms | Nej |

## 46 INKÖP AV TJÄNSTER, UNDERENTREPRENADER OCH LEGOARBETEN I SVERIGE (RÅVAROR OCH FÖRNÖDENHETER)

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4600 | Inköp av tjänster, underentreprenader och legoarbeten i Sverige (gruppkonto) | Nej |
| 4610 | Inköp av tjänster och underentreprenader | Nej |
| 4670 | Inköp av legoarbeten | Nej |

## 47 REDUKTION AV INKÖPSPRISER (RÅVAROR OCH FÖRNÖDENHETER)

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4700 | Reduktion av inköpspriser (gruppkonto) | Nej |
| 4730 | Erhållna rabatter (Råvaror och förnödenheter) | Nej |
| 4731 | Erhållna kassarabatter (Råvaror och förnödenheter) | Nej |
| 4732 | Erhållna mängdrabatter (inkl. bonus) (Råvaror och förnödenheter) | Nej |
| 4739 | Övriga reduktioner av inköpspriser (Råvaror och förnödenheter) | Nej |

## 48 ANDRA PRODUKTIONSKOSTNADER (RÅVAROR OCH FÖRNÖDENHETER)

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4800 | Andra produktionskostnader (gruppkonto) | Nej |
| 4810 | Kostnader för energi (Råvaror och förnödenheter) | Nej |
| 4820 | Kostnader för drivmedel (Råvaror och förnödenheter) | Nej |
| 4830 | Kostnader för resor (Råvaror och förnödenheter) | Nej |
| 4840 | Kostnader för hyra av utrustning (Råvaror och förnödenheter) | Nej |
| 4890 | Övriga produktionskostnader (Råvaror och förnödenheter) | Nej |

## 49 FÖRÄNDRING AV LAGER, PRODUKTER I ARBETE OCH PÅGÅENDE ARBETEN

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 4900 | Förändring av lager (gruppkonto) | Nej |
| 4910 | Förändring av lager av råvaror | Nej |
| 4920 | Förändring av lager av tillsatsmaterial och förnödenheter | Nej |
| 4940 | Förändring av produkter i arbete | Nej |
| 4944 | Förändring av produkter i arbete, material och utlägg | Nej |
| 4945 | Förändring av produkter i arbete, omkostnader | Nej |
| 4947 | Förändring av produkter i arbete, personalkostnader | Nej |
| 4950 | Förändring av lager av färdiga varor | Nej |
| 4960 | Förändring av lager av handelsvaror | Nej |
| 4970 | Förändring av pågående arbeten, nedlagda kostnader | Nej |
| 4974 | Förändring av pågående arbeten, material och utlägg | Nej |
| 4975 | Förändring av pågående arbeten, omkostnader | Nej |
| 4977 | Förändring av pågående arbeten, personalkostnader | Nej |
| 4980 | Förändring av lager av värdepapper (Handelsvaror) | Nej |
| 4981 | Sålda värdepappers anskaffningsvärde (Handelsvaror) | Nej |
| 4987 | Nedskrivning av värdepapper (Handelsvaror) | Nej |
| 4988 | Återföring av nedskrivning av värdepapper (Handelsvaror) | Nej |

## 50 LOKALKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5000 | Lokalkostnader (gruppkonto) | Nej |
| 5010 | Lokalhyra | Nej |
| 5011 | Hyra för kontorslokaler | Nej |
| 5012 | Hyra för garage | Nej |
| 5013 | Hyra för lagerlokaler | Nej |
| 5019 | Övriga kostnader för lokalhyra | Nej |
| 5020 | El | Nej |
| 5030 | Värme | Nej |
| 5040 | Vatten och avlopp | Nej |
| 5050 | Lokaltillbehör | Nej |
| 5060 | Städning och renhållning | Nej |
| 5061 | Städning | Nej |
| 5062 | Sophämtning | Nej |
| 5064 | Snöröjning | Nej |
| 5065 | Trädgårdsskötsel | Nej |
| 5069 | Övriga kostnader för städning och underhåll | Nej |
| 5070 | Reparation och underhåll av lokaler | Nej |
| 5090 | Övriga lokalkostnader | Nej |

## 51 FASTIGHETSKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5100 | Fastighetskostnader (gruppkonto) | Nej |
| 5110 | Tomträttsavgäld/arrende | Nej |
| 5120 | El | Nej |
| 5130 | Värme | Nej |
| 5131 | Uppvärmning | Nej |
| 5132 | Sotning | Nej |
| 5139 | Övriga kostnader för värme | Nej |
| 5140 | Vatten och avlopp | Nej |
| 5160 | Städning och renhållning | Nej |
| 5161 | Städning | Nej |
| 5162 | Sophämtning | Nej |
| 5164 | Snöröjning | Nej |
| 5165 | Trädgårdsskötsel | Nej |
| 5169 | Övriga kostnader för städning och renhållning | Nej |
| 5170 | Reparation och underhåll av fastighet | Nej |
| 5190 | Övriga fastighetskostnader | Nej |
| 5191 | Fastighetsskatt/fastighetsavgift | Nej |
| 5192 | Fastighetsförsäkringspremier | Nej |
| 5193 | Fastighetsskötsel och förvaltning | Nej |
| 5198 | Övriga fastighetskostnader | Nej |

## 52 HYRA AV ANLÄGGNINGSTILLGÅNGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5200 | Hyra av anläggningstillgångar (gruppkonto) | Nej |
| 5210 | Hyra av maskiner och andra tekniska anläggningar, ej datorer och fordon | Nej |
| 5220 | Hyra av inventarier och verktyg, ej datorer och fordon | Nej |
| 5250 | Hyra av datorer | Nej |
| 5290 | Hyra av övriga anläggningstillgångar, ej datorer och fordon | Nej |

## 53 ENERGIKOSTNADER FÖR DRIFT (EJ RÅVAROR OCH FÖRNÖDENHETER)

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5300 | Energikostnader för drift (gruppkonto) (ej råvaror och förnödenheter) | Nej |
| 5310 | El för drift (ej råvaror och förnödenheter) | Nej |
| 5320 | Gas för drift (ej råvaror och förnödenheter) | Nej |
| 5330 | Eldningsolja för drift (ej råvaror och förnödenheter) | Nej |
| 5340 | Stenkol och koks för drift (ej råvaror och förnödenheter) | Nej |
| 5350 | Torv, träkol, ved, m.m. för drift (ej råvaror och förnödenheter) | Nej |
| 5360 | Bensin, fotogen och motorbrännolja för drift (ej råvaror och förnödenheter) | Nej |
| 5370 | Fjärrvärme, kyla och ånga för drift (ej råvaror och förnödenheter) | Nej |
| 5380 | Vatten för drift (ej råvaror och förnödenheter) | Nej |
| 5390 | Övriga energikostnader för drift (ej råvaror och förnödenheter) | Nej |

## 54 FÖRBRUKNINGSINVENTARIER OCH FÖRBRUKNINGSMATERIAL

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5400 | Förbrukningsinventarier och förbrukningsmaterial (gruppkonto) | Nej |
| 5410 | Förbrukningsinventarier | Nej |
| 5411 | Förbrukningsinv med en livslängd på mer än ett år | Nej |
| 5412 | Förbrukningsinv med en livslängd om högst ett år | Nej |
| 5420 | Programvaror | Nej |
| 5430 | Transportinventarier | Nej |
| 5440 | Förbrukningsemballage | Nej |
| 5460 | Förbrukningsmaterial | Nej |
| 5480 | Arbetskläder och skyddsmaterial | Nej |

## 55 REPARATION OCH UNDERHÅLL

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5500 | Reparation och underhåll (gruppkonto) | Nej |
| 5510 | Reparation och underhåll av maskiner och andra tekniska anläggningar | Nej |
| 5520 | Reparation och underhåll av inventarier, verktyg och datorer m.m. | Nej |
| 5530 | Reparation och underhåll byggnads- och markinventarier | Nej |
| 5550 | Reparation och underhåll av förbrukningsinventarier | Nej |
| 5580 | Underhåll och tvätt av arbetskläder | Nej |
| 5590 | Övriga kostnader för reparation och underhåll | Nej |

## 56 KOSTNADER FÖR TRANSPORTMEDEL

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5600 | Kostnader för transportmedel (gruppkonto) | Nej |
| 5610 | Personbils- och mc-kostnader, m.m. | Nej |
| 5611 | Drivmedel för personbilar, mc, m.m. | Nej |
| 5612 | Försäkring och skatt för personbilar, mc, m.m. | Nej |
| 5613 | Reparation och underhåll av personbilar, mc, m.m. | Nej |
| 5615 | Leasing av personbilar, mc, m.m. | Nej |
| 5616 | Trängselskatt personbilar | Nej |
| 5619 | Övriga kostnader för personbilar och mc, m.m. | Nej |
| 5620 | Lastbils- och busskostnader, m.m. | Nej |
| 5621 | Drivmedel lastbilar och bussar | Nej |
| 5622 | Försäkring och skatt lastbilar och bussar | Nej |
| 5623 | Reparation och underhåll lastbilar och bussar | Nej |
| 5625 | Leasing lastbilar och bussar | Nej |
| 5626 | Trängselskatt lastbilar och bussar | Nej |
| 5629 | Övriga lastbils- och busskostnader | Nej |
| 5630 | Truckkostnader | Nej |
| 5631 | Drivmedel truckar | Nej |
| 5632 | Försäkring och skatt truckar | Nej |
| 5633 | Reparation och underhåll truckar | Nej |
| 5635 | Leasing truckar | Nej |
| 5639 | Övriga kostnader för truckar | Nej |
| 5640 | Kostnader för arbetsmaskiner | Nej |
| 5641 | Drivmedel arbetsmaskiner | Nej |
| 5642 | Försäkring och skatt arbetsmaskiner | Nej |
| 5643 | Reparation och underhåll arbetsmaskiner | Nej |
| 5645 | Leasing arbetsmaskiner | Nej |
| 5646 | Trängselskatt arbetsmaskiner | Nej |
| 5649 | Övriga kostnader för arbetsmaskiner | Nej |
| 5650 | Traktorkostnader | Nej |
| 5651 | Drivmedel traktorer | Nej |
| 5652 | Försäkring och skatt traktorer | Nej |
| 5653 | Reparation och underhåll traktorer | Nej |
| 5655 | Leasing traktorer | Nej |
| 5656 | Trängselskatt traktorer | Nej |
| 5659 | Övriga kostnader för traktorer | Nej |
| 5670 | Kostnader för fartyg och luftfartyg | Nej |
| 5671 | Drivmedel fartyg och luftfartyg | Nej |
| 5672 | Försäkring och skatt fartyg och luftfartyg | Nej |
| 5673 | Reparation och underhåll fartyg och luftfartyg | Nej |
| 5675 | Leasing fartyg och luftfartyg | Nej |
| 5679 | Övriga kostnader för fartyg och luftfartyg | Nej |
| 5680 | Kostnader för rälsfordon | Nej |
| 5681 | Drivmedel rälsfordon | Nej |
| 5682 | Försäkring och skatt rälsfordon | Nej |
| 5683 | Reparation och underhåll rälsfordon | Nej |
| 5685 | Leasing rälsfordon | Nej |
| 5689 | Övriga kostnader för rälsfordon | Nej |
| 5690 | Kostnader för övriga transportmedel | Nej |
| 5691 | Drivmedel övriga transportmedel | Nej |
| 5692 | Försäkring och skatt övriga transportmedel | Nej |
| 5693 | Reparation och underhåll övriga transportmedel | Nej |
| 5695 | Leasing övriga transportmedel | Nej |
| 5696 | Trängselskatt övriga transportmedel | Nej |
| 5699 | Övriga kostnader för övriga transportmedel | Nej |

## 57 FRAKTER OCH TRANSPORTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5700 | Frakter och transporter (gruppkonto) | Nej |
| 5710 | Frakter och försäkringar vid varudistribution | Nej |
| 5711 | Fraktkostnader | Nej |
| 5712 | Försäkringar vid frakter | Nej |
| 5720 | Tull- och speditionskostnader m.m. | Nej |
| 5721 | Tullkostnader | Nej |
| 5722 | Speditionskostnader | Nej |
| 5729 | Övriga tull- och speditionskostnader m.m. | Nej |
| 5730 | Arbetstransporter | Nej |
| 5790 | Övriga kostnader för frakter och transporter | Nej |

## 58 RESEKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5800 | Resekostnader (gruppkonto) | Nej |
| 5810 | Biljetter | Nej |
| 5820 | Hyrbilskostnader | Nej |
| 5830 | Kost och logi | Nej |
| 5831 | Kost och logi i Sverige | Nej |
| 5832 | Kost och logi i utlandet | Nej |
| 5890 | Övriga resekostnader | Nej |

## 59 REKLAM OCH PR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 5900 | Reklam och PR (gruppkonto) | Nej |
| 5910 | Annonsering | Nej |
| 5920 | Utomhus- och trafikreklam | Nej |
| 5930 | Reklamtrycksaker och direktreklam | Nej |
| 5940 | Utställningar och mässor | Nej |
| 5950 | Butiksreklam och återförsäljarreklam | Nej |
| 5960 | Varuprover, reklamgåvor, presentreklam och tävlingar | Nej |
| 5970 | Film-, radio-, TV- och Internetreklam | Nej |
| 5980 | Sponsring | Nej |
| 5981 | Avdragsgill sponsring | Nej |
| 5982 | Ej avdragsgill sponsring | Nej |
| 5990 | Övriga kostnader för reklam och PR | Nej |

## 60 ÖVRIGA FÖRSÄLJNINGSKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6000 | Övriga försäljningskostnader (gruppkonto) | Nej |
| 6010 | Kataloger, prislistor m.m. | Nej |
| 6020 | Egna facktidskrifter | Nej |
| 6030 | Speciella orderkostnader | Nej |
| 6040 | Kontokortsavgifter | Nej |
| 6050 | Försäljningsprovisioner | Nej |
| 6055 | Franchisekostnader | Nej |
| 6059 | Övriga försäljningsprovisionskostnader | Nej |
| 6060 | Kreditförsäljningskostnader | Nej |
| 6061 | Kreditupplysning | Nej |
| 6062 | Inkasso och KFM-avgifter | Nej |
| 6063 | Kreditförsäkringspremier | Nej |
| 6064 | Factoringavgifter | Nej |
| 6069 | Övriga kreditförsäljningskostnader | Nej |
| 6070 | Representation | Nej |
| 6071 | Representation, avdragsgill | Nej |
| 6072 | Representation, ej avdragsgill | Nej |
| 6080 | Bankgarantier | Nej |
| 6090 | Övriga försäljningskostnader | Nej |

## 61 KONTORSMATERIAL OCH TRYCKSAKER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6100 | Kontorsmateriel och trycksaker (gruppkonto) | Nej |
| 6110 | Kontorsmateriel | Nej |
| 6150 | Trycksaker | Nej |

## 62 TELE, DATA OCH POST

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6200 | Tele, data och post (gruppkonto) | Nej |
| 6210 | Telekommunikation | Nej |
| 6211 | Fast telefoni | Nej |
| 6212 | Mobiltelefon | Nej |
| 6219 | Övriga kostnader för telekommunikation | Nej |
| 6230 | Datakommunikation | Nej |
| 6250 | Porto | Nej |
| 6290 | Övriga tele-, data- och postkostnader | Nej |

## 63 FÖRETAGSFÖRSÄKRINGAR OCH ÖVRIGA RISKKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6300 | Företagsförsäkringar och övriga riskkostnader (gruppkonto) | Nej |
| 6310 | Företagsförsäkringar | Nej |
| 6320 | Självrisker vid skada | Nej |
| 6330 | Förluster i pågående arbeten | Nej |
| 6340 | Lämnade skadestånd | Nej |
| 6341 | Lämnade skadestånd, avdragsgilla | Nej |
| 6342 | Lämnade skadestånd, ej avdragsgilla | Nej |
| 6350 | Förluster på kundfordringar | Nej |
| 6351 | Konstaterade förluster på kundfordringar | Nej |
| 6352 | Befarade förluster på kundfordringar | Nej |
| 6360 | Garantikostnader | Nej |
| 6361 | Förändring av garantiavsättning | Nej |
| 6362 | Faktiska garantikostnader | Nej |
| 6370 | Kostnader för bevakning och larm | Nej |
| 6380 | Förluster på övriga kortfristiga fordringar | Nej |
| 6390 | Övriga riskkostnader | Nej |
| 6391 | Övriga riskkostnader, avdragsgilla | Nej |
| 6392 | Övriga riskkostnader, ej avdragsgilla | Nej |

## 64 FÖRVALTNINGSKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6400 | Förvaltningskostnader (gruppkonto) | Nej |
| 6420 | Ersättningar till revisor | Nej |
| 6421 | Revision | Nej |
| 6422 | Revisonsverksamhet utöver revision | Nej |
| 6423 | Skatterådgivning – revisor | Nej |
| 6424 | Övriga tjänster – revisor | Nej |
| 6430 | Management fees | Nej |
| 6440 | Årsredovisning och delårsrapporter | Nej |
| 6450 | Bolagsstämma/års- eller föreningsstämma | Nej |
| 6490 | Övriga förvaltningskostnader | Nej |

## 65 ÖVRIGA EXTERNA TJÄNSTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6500 | Övriga externa tjänster (gruppkonto) | Nej |
| 6510 | Mätningskostnader | Nej |
| 6520 | Ritnings- och kopieringskostnader | Nej |
| 6530 | Redovisningstjänster | Nej |
| 6540 | IT-tjänster | Nej |
| 6550 | Konsultarvoden | Nej |
| 6551 | Arkitekttjänster | Nej |
| 6552 | Teknisk provning och analys | Nej |
| 6553 | Tekniska konsulttjänster | Nej |
| 6554 | Finansiell- och övrig ekonomisk rådgivning | Nej |
| 6555 | Skatterådgivning inkl. insolvens- och konkursförv. | Nej |
| 6556 | Köpta tjänster avseende forskning och utveckling | Nej |
| 6559 | Övriga konsultarvoden | Nej |
| 6560 | Serviceavgifter till branschorganisationer | Nej |
| 6570 | Bankkostnader | Nej |
| 6580 | Advokat- och rättegångskostnader | Nej |
| 6590 | Övriga externa tjänster | Nej |

## 67 SÄRSKILT FÖR IDEELLA FÖRENINGAR OCH STIFTELSER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6700 | Särskilt för ideella föreningar och stiftelser (gruppkonto) | Nej |
| 6710 | Lämnade bidrag | Nej |

## 68 INHYRD PERSONAL

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6800 | Inhyrd personal (gruppkonto) | Nej |
| 6810 | Inhyrd produktionspersonal | Nej |
| 6820 | Inhyrd lagerpersonal | Nej |
| 6830 | Inhyrd transportpersonal | Nej |
| 6840 | Inhyrd kontors- och ekonomipersonal | Nej |
| 6850 | Inhyrd IT-personal | Nej |
| 6860 | Inhyrd marknads- och försäljningspersonal | Nej |
| 6870 | Inhyrd restaurang- och butikspersonal | Nej |
| 6880 | Inhyrda företagsledare | Nej |
| 6890 | Övrig inhyrd personal | Nej |

## 69 ÖVRIGA EXTERNA KOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 6900 | Övriga externa kostnader (gruppkonto) | Nej |
| 6910 | Licensavgifter och royalties | Nej |
| 6920 | Kostnader för egna patent | Nej |
| 6930 | Kostnader för varumärken m.m. | Nej |
| 6940 | Kontroll-, provnings- och stämpelavgifter | Nej |
| 6950 | Tillsynsavgifter myndigheter | Nej |
| 6970 | Tidningar, facklitteratur, m.m. | Nej |
| 6980 | Föreningsavgifter | Nej |
| 6981 | Föreningsavgifter, avdragsgilla | Nej |
| 6982 | Föreningsavgifter, ej avdragsgilla | Nej |
| 6990 | Övriga externa kostnader | Nej |
| 6991 | Övriga externa kostnader, avdragsgilla | Nej |
| 6992 | Övriga externa kostnader, ej avdragsgilla | Nej |
| 6993 | Lämnade bidrag och gåvor | Nej |
| 6996 | Betald utländsk inkomstskatt | Nej |
| 6997 | Obetald utländsk inkomstskatt | Nej |
| 6998 | Utländsk moms | Nej |
| 6999 | Ingående moms, blandad verksamhet | Nej |

## 70 LÖNER TILL KOLLEKTIVANSTÄLLDA

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7000 | Löner till kollektivanställda (gruppkonto) | Nej |
| 7010 | Löner till kollektivanställda | Nej |
| 7011 | Löner till kollektivanställda | Nej |
| 7012 | Vinstandelar till kollektivanställda | Nej |
| 7013 | Lön växa-stöd kollektivanställda 10,21 % | Nej |
| 7017 | Avgångsvederlag till kollektivanställda | Nej |
| 7018 | Bruttolöneavdrag, kollektivanställda | Nej |
| 7019 | Upplupna löner och vinstandelar till kollektivanställda | Nej |
| 7030 | Löner till kollektivanställda (utlandsanställda) | Nej |
| 7031 | Löner till kollektivanställda (utlandsanställda) | Nej |
| 7032 | Vinstandelar till kollektivanställda (utlandsanställda) | Nej |
| 7037 | Avgångsvederlag till kollektivanställda (utlandsanställda) | Nej |
| 7038 | Bruttolöneavdrag, kollektivanställda (utlandsanställda) | Nej |
| 7039 | Upplupna löner och vinstandelar till kollektivanställda (utlandsanställda) | Nej |
| 7080 | Löner till kollektivanställda för ej arbetad tid | Nej |
| 7081 | Sjuklöner till kollektivanställda | Nej |
| 7082 | Semesterlöner till kollektivanställda | Nej |
| 7083 | Föräldraersättning till kollektivanställda | Nej |
| 7089 | Övriga löner till kollektivanställda för ej arbetad tid | Nej |
| 7090 | Förändring av semesterlöneskuld | Nej |

## 72 LÖNER TILL TJÄNSTEMÄN OCH FÖRETAGSLEDARE

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7200 | Löner till tjänstemän och företagsledare (gruppkonto) | Nej |
| 7210 | Löner till tjänstemän | Nej |
| 7211 | Löner till tjänstemän | Nej |
| 7212 | Vinstandelar till tjänstemän | Nej |
| 7213 | Lön växa-stöd tjänstemän 10,21 % | Nej |
| 7217 | Avgångsvederlag till tjänstemän | Nej |
| 7218 | Bruttolöneavdrag, tjänstemän | Nej |
| 7219 | Upplupna löner och vinstandelar till tjänstemän | Nej |
| 7220 | Löner till företagsledare | Nej |
| 7221 | Löner till företagsledare | Nej |
| 7222 | Tantiem till företagsledare | Nej |
| 7227 | Avgångsvederlag till företagsledare | Nej |
| 7228 | Bruttolöneavdrag, företagsledare | Nej |
| 7229 | Upplupna löner och tantiem till företagsledare | Nej |
| 7230 | Löner till tjänstemän och ftgsledare (utlandsanställda) | Nej |
| 7231 | Löner till tjänstemän och ftgsledare (utlandsanställda) | Nej |
| 7232 | Vinstandelar till tjänstemän och ftgsledare (utlandsanställda) | Nej |
| 7237 | Avgångsvederlag till tjänstemän och ftgsledare (utlandsanställda) | Nej |
| 7238 | Bruttolöneavdrag, tjänstemän och ftgsledare (utlandsanställda) | Nej |
| 7239 | Upplupna löner och vinstandelar till tjänstemän och ftgsledare (utlandsanställda) | Nej |
| 7240 | Styrelsearvoden | Nej |
| 7280 | Löner till tjänstemän och företagsledare för ej arbetad tid | Nej |
| 7281 | Sjuklöner till tjänstemän | Nej |
| 7282 | Sjuklöner till företagsledare | Nej |
| 7283 | Föräldraersättning till tjänstemän | Nej |
| 7284 | Föräldraersättning till företagsledare | Nej |
| 7285 | Semesterlöner till tjänstemän | Nej |
| 7286 | Semesterlöner till företagsledare | Nej |
| 7288 | Övriga löner till tjänstemän för ej arbetad tid | Nej |
| 7289 | Övriga löner till företagsledare för ej arbetad tid | Nej |
| 7290 | Förändring av semesterlöneskuld | Nej |
| 7291 | Förändring av semesterlöneskuld till tjänstemän | Nej |
| 7292 | Förändring av semesterlöneskuld till företagsledare | Nej |

## 73 KOSTNADSERSÄTTNINGAR OCH FÖRMÅNER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7300 | Kostnadsersättningar och förmåner (gruppkonto) | Nej |
| 7310 | Kontanta extraersättningar | Nej |
| 7311 | Ersättningar för sammanträden m.m. | Nej |
| 7312 | Ersättningar för förslagsverksamhet och uppfinningar | Nej |
| 7313 | Ersättningar för/bidrag till bostadskostnader | Nej |
| 7314 | Ersättningar för/bidrag till måltidskostnader | Nej |
| 7315 | Ersättningar för/bidrag till resor till och från arbetsplatsen | Nej |
| 7316 | Ersättningar för/bidrag till arbetskläder | Nej |
| 7317 | Ersättningar för/bidrag till arbetsmaterial och arbetsverktyg | Nej |
| 7318 | Felräkningspengar | Nej |
| 7319 | Övriga kontanta extraersättningar | Nej |
| 7320 | Traktamenten vid tjänsteresa | Nej |
| 7321 | Skattefria traktamenten, Sverige | Nej |
| 7322 | Skattepliktiga traktamenten, Sverige | Nej |
| 7323 | Skattefria traktamenten, utlandet | Nej |
| 7324 | Skattepliktiga traktamenten, utlandet | Nej |
| 7330 | Bilersättningar | Nej |
| 7331 | Skattefria bilersättningar | Nej |
| 7332 | Skattepliktiga bilersättningar | Nej |
| 7333 | Ersättning för trängselskatt, skattefri | Nej |
| 7350 | Ersättningar för föreskrivna arbetskläder | Nej |
| 7370 | Representationsersättningar | Nej |
| 7380 | Kostnader för förmåner till anställda | Nej |
| 7381 | Kostnader för fri bostad | Nej |
| 7382 | Kostnader för fria eller subventionerade måltider | Nej |
| 7383 | Kostnader för fria resor till och från arbetsplatsen | Nej |
| 7384 | Kostnader för fria eller subventionerade arbetskläder | Nej |
| 7385 | Kostnader för fri bil | Nej |
| 7386 | Subventionerad ränta | Nej |
| 7387 | Kostnader för lånedatorer | Nej |
| 7388 | Anställdas ersättning för erhållna förmåner | Nej |
| 7389 | Övriga kostnader för förmåner | Nej |
| 7390 | Övriga kostnadsersättningar och förmåner | Nej |
| 7391 | Kostnad för trängselskatteförmån | Nej |
| 7392 | Kostnad för förmån av hushållsnära tjänster | Nej |

## 74 PENSIONSKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7400 | Pensionskostnader (gruppkonto) | Nej |
| 7410 | Pensionsförsäkringspremier | Nej |
| 7411 | Premier för kollektiva pensionsförsäkringar | Nej |
| 7412 | Premier för individuella pensionsförsäkringar | Nej |
| 7420 | Förändring av pensionsskuld | Nej |
| 7430 | Avdrag för räntedel i pensionskostnad | Nej |
| 7440 | Förändring av pensionsstiftelsekapital | Nej |
| 7441 | Överföring av medel till pensionsstiftelse | Nej |
| 7448 | Gottgörelse från pensionsstiftelse | Nej |
| 7460 | Pensionsutbetalningar | Nej |
| 7461 | Pensionsutbetalningar till f.d. kollektivanställda | Nej |
| 7462 | Pensionsutbetalningar till f.d. tjänstemän | Nej |
| 7463 | Pensionsutbetalningar till f.d. företagsledare | Nej |
| 7470 | Förvaltnings- och kreditförsäkringsavgifter | Nej |
| 7490 | Övriga pensionskostnader | Nej |

## 75 SOCIALA OCH ANDRA AVGIFTER ENLIGT LAG OCH AVTAL

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7500 | Sociala och andra avgifter enligt lag och avtal (gruppkonto) | Nej |
| 7510 | Arbetsgivaravgifter 31,42 % | Nej |
| 7511 | Arbetsgivaravgifter för löner och ersättningar | Nej |
| 7512 | Arbetsgivaravgifter för förmånsvärden | Nej |
| 7515 | Arbetsgivaravgifter på skattepliktiga kostnadsersättningar | Nej |
| 7516 | Arbetsgivaravgifter på arvoden | Nej |
| 7518 | Arbetsgivaravgifter på bruttolöneavdrag m.m. | Nej |
| 7519 | Arbetsgivaravgifter för semester- och löneskulder | Nej |
| 7530 | Särskild löneskatt | Nej |
| 7531 | Särskild löneskatt för vissa försäkringsersättningar m.m. | Nej |
| 7532 | Särskild löneskatt pensionskostnader, deklarationspost | Nej |
| 7533 | Särskild löneskatt för pensionskostnader | Nej |
| 7550 | Avkastningsskatt på pensionsmedel | Nej |
| 7551 | Avkastningsskatt 15 % försäkringsföretag m.fl. samt avsatt till pensioner | Nej |
| 7552 | Avkastningsskatt 15 % utländska pensionsförsäkringar | Nej |
| 7553 | Avkastningsskatt 30 % utländska försäkringsföretag m.fl. | Nej |
| 7554 | Avkastningsskatt 30 % utländska kapitalförsäkringar | Nej |
| 7570 | Premier för arbetsmarknadsförsäkringar | Nej |
| 7571 | Arbetsmarknadsförsäkringar | Nej |
| 7572 | Arbetsmarknadsförsäkringar pensionsförsäkringspremier, deklarationspost | Nej |
| 7580 | Gruppförsäkringspremier | Nej |
| 7581 | Grupplivförsäkringspremier | Nej |
| 7582 | Gruppsjukförsäkringspremier | Nej |
| 7583 | Gruppolycksfallsförsäkringspremier | Nej |
| 7589 | Övriga gruppförsäkringspremier | Nej |
| 7590 | Övriga sociala och andra avgifter enligt lag och avtal | Nej |

## 76 ÖVRIGA PERSONALKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7600 | Övriga personalkostnader (gruppkonto) | Nej |
| 7610 | Utbildning | Nej |
| 7620 | Sjuk- och hälsovård | Nej |
| 7621 | Sjuk- och hälsovård, avdragsgill | Nej |
| 7622 | Sjuk- och hälsovård, ej avdragsgill | Nej |
| 7623 | Sjukvårdsförsäkring, ej avdragsgill | Nej |
| 7630 | Personalrepresentation | Nej |
| 7631 | Personalrepresentation, avdragsgill | Nej |
| 7632 | Personalrepresentation, ej avdragsgill | Nej |
| 7650 | Sjuklöneförsäkring | Nej |
| 7670 | Förändring av personalstiftelsekapital | Nej |
| 7671 | Avsättning till personalstiftelse | Nej |
| 7678 | Gottgörelse från personalstiftelse | Nej |
| 7690 | Övriga personalkostnader | Nej |
| 7691 | Personalrekrytering | Nej |
| 7692 | Begravningshjälp | Nej |
| 7693 | Fritidsverksamhet | Nej |
| 7699 | Övriga personalkostnader | Nej |

## 77 NEDSKRIVNINGAR OCH ÅTERFÖRING AV NEDSKRIVNINGAR

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7710 | Nedskrivningar av immateriella anläggningstillgångar | Nej |
| 7720 | Nedskrivningar av byggnader och mark | Nej |
| 7730 | Nedskrivningar av maskiner respektive inventarier | Nej |
| 7731 | Nedskrivningar av maskiner och andra tekniska anläggningar | Nej |
| 7732 | Nedskrivningar av inventarier, verktyg och installationer | Nej |
| 7733 | Nedskrivningar av övriga materiella anläggningstillgångar | Nej |
| 7740 | Nedskrivningar av vissa omsättningstillgångar | Nej |
| 7760 | Återföring av nedskrivningar av immateriella anläggningstillgångar | Nej |
| 7770 | Återföring av nedskrivningar av byggnader och mark | Nej |
| 7780 | Återföring av nedskrivningar av maskiner respektive inventarier | Nej |
| 7781 | Återföring av nedskrivningar av maskiner och andra tekniska anläggningar | Nej |
| 7782 | Återföring av nedskrivningar av inventarier, verktyg och installationer | Nej |
| 7783 | Återföring av nedskrivningar av övriga materiella anläggningstillgångar | Nej |
| 7790 | Återföring av nedskrivningar av vissa omsättningstillgångar | Nej |

## 78 AVSKRIVNINGAR ENLIGT PLAN

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7810 | Avskrivningar på immateriella anläggningstillgångar | Nej |
| 7811 | Avskrivningar på balanserade utgifter | Nej |
| 7812 | Avskrivningar på koncessioner m.m. | Nej |
| 7813 | Avskrivningar på patent | Nej |
| 7814 | Avskrivningar på licenser | Nej |
| 7815 | Avskrivningar på varumärken | Nej |
| 7816 | Avskrivningar på hyresrätter | Nej |
| 7817 | Avskrivningar på goodwill | Nej |
| 7819 | Avskrivningar på övriga immateriella anläggningstillgångar | Nej |
| 7820 | Avskrivningar på byggnader och markanläggningar | Nej |
| 7821 | Avskrivningar på byggnader | Nej |
| 7824 | Avskrivningar på markanläggningar | Nej |
| 7829 | Avskrivningar på övriga byggnader | Nej |
| 7830 | Avskrivningar på maskiner respektive inventarier | Nej |
| 7831 | Avskrivningar på maskiner och andra tekniska anläggningar | Nej |
| 7832 | Avskrivningar på inventarier, verktyg och installationer | Nej |
| 7836 | Avskrivningar på leasade tillgångar | Nej |
| 7839 | Avskrivningar på övriga materiella anläggningstillgångar | Nej |
| 7840 | Avskrivningar på förbättringsutgifter på annans fastighet | Nej |

## 79 ÖVRIGA RÖRELSEKOSTNADER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 7940 | Orealiserade positiva/negativa värdeförändringar på säkringsinstrument | Ja |
| 7960 | Valutakursförluster på fordringar och skulder av rörelsekaraktär | Nej |
| 7970 | Förlust vid avyttring av immateriella och materiella anläggningstillgångar | Nej |
| 7971 | Förlust vid avyttring av immateriella anläggningstillgångar | Nej |
| 7972 | Förlust vid avyttring av byggnader och mark | Nej |
| 7973 | Förlust vid avyttring av maskiner och inventarier | Nej |
| 7990 | Övriga rörelsekostnader | Nej |

## 80 RESULTAT FRÅN ANDELAR I KONCERNFÖRETAG

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 8010 | Utdelning på andelar i koncernföretag | Nej |
| 8012 | Utdelning på andelar i dotterföretag | Nej |
| 8016 | Emissionsinsats, koncernföretag | Nej |
| 8020 | Resultat vid försäljning av andelar i koncernföretag | Nej |
| 8030 | Resultatandelar från handelsbolag (dotterföretag) | Nej |
| 8070 | Nedskrivningar av andelar i och långfristiga fordringar hos koncernföretag | Nej |
| 8072 | Nedskrivningar av andelar i dotterföretag | Nej |
| 8076 | Nedskrivningar av långfristiga fordringar hos moderföretag | Nej |
| 8077 | Nedskrivningar av långfristiga fordringar hos dotterföretag | Nej |
| 8080 | Återföringar av nedskrivningar av andelar i och långfristiga fordringar hos koncernföretag | Nej |
| 8082 | Återföringar av nedskrivningar av andelar i dotterföretag | Nej |
| 8086 | Återföringar av nedskrivningar av långfristiga fordringar hos moderföretag | Nej |
| 8087 | Återföringar av nedskrivningar av långfristiga fordringar hos dotterföretag | Nej |

## 81 RESULTAT FRÅN ANDELAR I INTRESSEFÖRETAG OCH GEMENSAMT STYRDA FÖRETAG SAMT ÖVRIGA FÖRETAG SOM DET FINNS ETT ÄGARINTRESSE I

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 8110 | Utdelningar på andelar i intresseföretag och gemensamt styrda företag samt övriga företag som det finns ett ägarintresse i | Nej |
| 8111 | Utdelningar på andelar i intresseföretag | Nej |
| 8112 | Utdelningar på andelar i gemensamt styrda företag | Nej |
| 8113 | Utdelningar på andelar i övriga företag som det finns ett ägarintresse i | Nej |
| 8116 | Emissionsinsats, intresseföretag | Nej |
| 8117 | Emissionsinsats, gemensamt styrda företag | Nej |
| 8118 | Emissionsinsats, övriga företag som det finns ett ägarintresse i | Nej |
| 8120 | Resultat vid försäljning av andelar i intresseföretag och gemensamt styrda företag samt övriga företag som det finns ett ägarintresse i | Nej |
| 8121 | Resultat vid försäljning av andelar i intresseföretag | Nej |
| 8122 | Resultat vid försäljning av andelar i gemensamt styrda företag | Nej |
| 8123 | Resultat vid försäljning av andelar i övriga företag som det finns ett ägarintresse i | Nej |
| 8130 | Resultatandelar från handelsbolag (intresseföretag och gemensamt styrda företag samt övriga företag som det finns ett ägarintresse i) | Nej |
| 8131 | Resultatandelar från handelsbolag (intresseföretag) | Nej |
| 8132 | Resultatandelar från handelsbolag (gemensamt styrda företag) | Nej |
| 8133 | Resultatandelar från handelsbolag (övriga företag som det finns ett ägarintresse i) | Nej |
| 8170 | Nedskrivningar av andelar i och långfristiga fordringar hos intresseföretag och gemensamt styrda företag samt övriga företag som det finns ett ägarintresse i | Nej |
| 8171 | Nedskrivningar av andelar i intresseföretag | Nej |
| 8172 | Nedskrivningar av långfristiga fordringar hos intresseföretag | Nej |
| 8173 | Nedskrivningar av andelar i gemensamt styrda företag | Nej |
| 8174 | Nedskrivningar av långfristiga fordringar hos gemensamt styrda företag | Nej |
| 8176 | Nedskrivningar av andelar i övriga företag som det finns ett ägarintresse i | Nej |
| 8177 | Nedskrivningar av långfristiga fordringar hos övriga företag som det finns ett ägarintresse i | Nej |
| 8180 | Återföringar av nedskrivningar av andelar i och långfristiga fordringar hos intresseföretag och gemensamt styrda företag samt övriga företag som det finns ett ägarintresse i | Nej |
| 8181 | Återföringar av nedskrivningar av andelar i intresseföretag | Nej |
| 8182 | Återföringar av nedskrivningar av långfristiga fordringar hos intresseföretag | Nej |
| 8183 | Återföringar av nedskrivningar av andelar i gemensamt styrda företag | Nej |
| 8184 | Återföringar av nedskrivningar av långfristiga fordringar hos gemensamt styrda företag | Nej |
| 8186 | Återföringar av nedskrivningar av andelar i övriga företag som det finns ett ägarintresse i | Nej |
| 8187 | Återföringar av nedskrivningar av långfristiga fordringar hos övriga företag som det finns ett ägarintresse i | Nej |

## 82 RESULTAT FRÅN ÖVRIGA VÄRDEPAPPER OCH LÅNGFRISTIGA FORDRINGAR (ANLÄGGNINGSTILLGÅNGAR)

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 8210 | Utdelningar på andelar i andra företag | Nej |
| 8212 | Utdelningar, andra företag | Nej |
| 8216 | Insatsemissioner, andra företag | Nej |
| 8220 | Resultat vid försäljning av värdepapper i och långfristiga fordringar hos andra företag | Nej |
| 8221 | Resultat vid försäljning av andelar i andra företag | Nej |
| 8222 | Resultat vid försäljning av långfristiga fordringar hos andra företag | Nej |
| 8223 | Resultat vid försäljning av derivat (långfristiga värdepappersinnehav) | Nej |
| 8230 | Valutakursdifferenser på långfristiga fordringar | Nej |
| 8231 | Valutakursvinster på långfristiga fordringar | Nej |
| 8236 | Valutakursförluster på långfristiga fordringar | Nej |
| 8240 | Resultatandelar från handelsbolag (andra företag) | Nej |
| 8250 | Ränteintäkter från långfristiga fordringar hos och värdepapper i andra företag | Nej |
| 8251 | Ränteintäkter från långfristiga fordringar | Nej |
| 8252 | Ränteintäkter från övriga värdepapper | Nej |
| 8254 | Skattefria ränteintäkter, långfristiga tillgångar | Nej |
| 8255 | Avkastningsskatt kapitalplacering | Nej |
| 8260 | Ränteintäkter från långfristiga fordringar hos koncernföretag | Nej |
| 8261 | Ränteintäkter från långfristiga fordringar hos moderföretag | Nej |
| 8262 | Ränteintäkter från långfristiga fordringar hos dotterföretag | Nej |
| 8263 | Ränteintäkter från långfristiga fordringar hos andra koncernföretag | Nej |
| 8270 | Nedskrivningar av innehav av andelar i och långfristiga fordringar hos andra företag | Nej |
| 8271 | Nedskrivningar av andelar i andra företag | Nej |
| 8272 | Nedskrivningar av långfristiga fordringar hos andra företag | Nej |
| 8273 | Nedskrivningar av övriga värdepapper hos andra företag | Nej |
| 8280 | Återföringar av nedskrivningar av andelar i och långfristiga fordringar hos andra företag | Nej |
| 8281 | Återföringar av nedskrivningar av andelar i andra företag | Nej |
| 8282 | Återföringar av nedskrivningar av långfristiga fordringar hos andra företag | Nej |
| 8283 | Återföringar av nedskrivningar av övriga värdepapper i andra företag | Nej |
| 8290 | Värdering till verkligt värde, anläggningstillgångar | Ja |
| 8291 | Orealiserade värdeförändringar på anläggningstillgångar | Ja |
| 8295 | Orealiserade värdeförändringar på derivatinstrument | Ja |

## 83 ÖVRIGA RÄNTEINTÄKTER OCH LIKNANDE RESULTATPOSTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 8310 | Ränteintäkter från omsättningstillgångar | Nej |
| 8311 | Ränteintäkter från bank | Nej |
| 8312 | Ränteintäkter från kortfristiga placeringar | Nej |
| 8313 | Ränteintäkter från kortfristiga fordringar | Nej |
| 8314 | Skattefria ränteintäkter | Nej |
| 8317 | Ränteintäkter för dold räntekompensation | Nej |
| 8319 | Övriga ränteintäkter från omsättningstillgångar | Nej |
| 8320 | Värdering till verkligt värde, omsättningstillgångar | Ja |
| 8321 | Orealiserade värdeförändringar på omsättningstillgångar | Ja |
| 8325 | Orealiserade värdeförändringar på derivatinstrument (oms.-tillg.) | Ja |
| 8330 | Valutakursdifferenser på kortfristiga fordringar och placeringar | Nej |
| 8331 | Valutakursvinster på kortfristiga fordringar och placeringar | Nej |
| 8336 | Valutakursförluster på kortfristiga fordringar och placeringar | Nej |
| 8340 | Utdelningar på kortfristiga placeringar | Nej |
| 8350 | Resultat vid försäljning av kortfristiga placeringar | Nej |
| 8360 | Övriga ränteintäkter från koncernföretag | Nej |
| 8361 | Övriga ränteintäkter från moderföretag | Nej |
| 8362 | Övriga ränteintäkter från dotterföretag | Nej |
| 8363 | Övriga ränteintäkter från andra koncernföretag | Nej |
| 8370 | Nedskrivningar av kortfristiga placeringar | Nej |
| 8380 | Återföringar av nedskrivningar av kortfristiga placeringar | Nej |
| 8390 | Övriga finansiella intäkter | Nej |

## 84 RÄNTEKOSTNADER OCH LIKNANDE RESULTATPOSTER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 8400 | Räntekostnader (gruppkonto) | Nej |
| 8410 | Räntekostnader för långfristiga skulder | Nej |
| 8411 | Räntekostnader för obligations-, förlags- och konvertibla lån | Nej |
| 8412 | Räntedel i årets pensionskostnad | Nej |
| 8413 | Räntekostnader för kontokredit | Nej |
| 8415 | Räntekostnader för andra skulder till kreditinstitut | Nej |
| 8417 | Räntekostnader för dold räntekompensation m.m. | Ja |
| 8418 | Avdragspost för räntesubventioner | Nej |
| 8419 | Övriga räntekostnader för långfristiga skulder | Nej |
| 8420 | Räntekostnader för kortfristiga skulder | Nej |
| 8421 | Räntekostnader till kreditinstitut | Nej |
| 8422 | Dröjsmålsräntor för leverantörsskulder | Nej |
| 8423 | Räntekostnader för skatter och avgifter | Nej |
| 8424 | Räntekostnader byggnadskreditiv | Nej |
| 8429 | Övriga räntekostnader för kortfristiga skulder | Nej |
| 8430 | Valutakursdifferenser på skulder | Nej |
| 8431 | Valutakursvinster på skulder | Nej |
| 8436 | Valutakursförluster på skulder | Nej |
| 8440 | Erhållna räntebidrag | Nej |
| 8450 | Orealiserade värdeförändringar på skulder | Ja |
| 8451 | Orealiserade värdeförändringar på skulder | Ja |
| 8455 | Orealiserade värdeförändringar på säkringsinstrument | Ja |
| 8460 | Räntekostnader till koncernföretag | Nej |
| 8461 | Räntekostnader till moderföretag | Nej |
| 8462 | Räntekostnader till dotterföretag | Nej |
| 8463 | Räntekostnader till andra koncernföretag | Nej |
| 8480 | Aktiverade ränteutgifter | Ja |
| 8490 | Övriga skuldrelaterade poster | Nej |
| 8491 | Erhållet ackord på skulder till kreditinstitut m.m. | Nej |

## 88 BOKSLUTSDISPOSITIONER

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 8810 | Förändring av periodiseringsfond | Nej |
| 8811 | Avsättning till periodiseringsfond | Nej |
| 8819 | Återföring från periodiseringsfond | Nej |
| 8820 | Mottagna koncernbidrag | Nej |
| 8830 | Lämnade koncernbidrag | Nej |
| 8840 | Lämnade gottgörelser | Nej |
| 8850 | Förändring av överavskrivningar | Nej |
| 8851 | Förändring av överavskrivningar, immateriella anläggningstillgångar | Nej |
| 8852 | Förändring av överavskrivningar, byggnader och markanläggningar | Nej |
| 8853 | Förändring av överavskrivningar, maskiner respektive inventarier | Nej |
| 8860 | Förändring av ersättningsfond | Nej |
| 8861 | Avsättning till ersättningsfond för inventarier | Nej |
| 8862 | Avsättning till ersättningsfond för byggnader och markanläggningar | Nej |
| 8864 | Avsättning till ersättningsfond för djurlager i jordbruk och renskötsel | Nej |
| 8865 | Ianspråktagande av ersättningsfond för avskrivningar | Nej |
| 8866 | Ianspråktagande av ersättningsfond för annat än avskrivningar | Nej |
| 8869 | Återföring från ersättningsfond | Nej |
| 8890 | Övriga bokslutsdispositioner | Nej |
| 8892 | Nedskrivningar av konsolideringskaraktär av anläggningstillgångar | Nej |
| 8896 | Förändring av lagerreserv | Nej |
| 8899 | Övriga bokslutsdispositioner | Nej |

## 89 SKATTER OCH ÅRETS RESULTAT

| Konto | Kontonamn | Ej K2 |
|---:|---|---|
| 8910 | Skatt som belastar årets resultat | Nej |
| 8920 | Skatt på grund av ändrad beskattning | Nej |
| 8930 | Restituerad skatt | Nej |
| 8940 | Uppskjuten skatt | Ja |
| 8980 | Övriga skatter | Nej |
| 8990 | Resultat | Nej |
| 8999 | Årets resultat | Nej |
