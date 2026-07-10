---
title: "Organisationslegitimation och ombudsrollen"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/organisationslegitimationochombudsrollen.4.7da1d2e118be03f8e4f8d63.html"
author:
published:
created: 2026-07-09
description: "Många av de säkerhetsflöden som Skatteverket använder kräver autentisering med någon form av elektronisk id-handling, utöver API-nycklar. För företag eller andra former av juridiska personer kallas den id-handlingen för organisationslegitimation eller organisationscertifikat.Vi guidar dig till vilken typ av organisationslegitimation du ska välja och hur legitimationen fungerar, både i de olika säkerhetsflödena och i olika typer av situationer."
tags:
  - "clippings"
---
Många av de säkerhetsflöden som Skatteverket använder kräver autentisering med en elektronisk id-handling, utöver API-nycklar. För företag kallas den id-handlingen för organisationslegitimation eller organisationscertifikat. Vi guidar dig till vilken typ av organisationslegitimation du ska välja och hur legitimationen fungerar, både i de olika säkerhetsflödena och i olika typer av situationer.

## Vad är organisationslegitimation?

Organisationslegitimation är en form av elektronisk legitimation och fungerar ungefär som ett bank-id – fast för företag eller andra former av juridiska personer. Legitimationen gör det möjligt att bekräfta identiteten för den juridiska personen över ett nätverk. Identiteten representeras av den juridiska personens organisationsnummer, på samma sätt som ett personnummer representerar en fysisk person.

Ett vanligt samlingsnamn för olika typer av elektroniska legitimationer är certifikat. De certifikat som Skatteverket använder bygger på ett system som kallas public key infrastructure (PKI). Certifikaten utfärdas och signeras av en certifikatutfärdare, Certification Authority (CA), som kontrollerar att den som har certifikatet har ett visst organisationsnummer.

## Organisationslegitimation för olika miljöer

För närvarande accepterar Skatteverket bara organisationslegitimationer som är utfärdade av Expisoft. Du beställer organisationslegitimationen på deras webbplats. Observera att du behöver olika legitimationer beroende på om du vill använda legitimationen för test- eller produktionsmiljö.

### Organisationslegitimation eller certifikat för testmiljö

För att kunna använda våra kompletta testtjänster kan du behöva ett testcertifikat eller en e-legitimation för test, beroende på vilken av våra säkerhetslösningar du använder.

När det gäller e-legitimation finns det flera leverantörer att välja på, till exempel Bank-id eller Freja e-id för test. När det gäller organisationslegitimation så accepterar Skatteverket endast organisationslegitimationer som är utfärdade av Expisoft. Observera att organisationslegitimationen för test hos Expisoft kallas testcertifikat. Du laddar ner den under Testcertifikat server- och stämpellegitimationer. Använd testcertifikat för Bolag A eller Kommun A.

Det går inte att använda en e-legitimation eller en organisationslegitimation för produktion i testtjänsten.

Här hittar du organisationslegitimation och e-legitimation för test:

- [Expisoft testcertifikat Länk till annan webbplats.](https://eid.expisoft.se/expitrust-test-certifikat/)
- [Bank-id för test Länk till annan webbplats.](https://demo.bankid.com/)
- [Freja e-id för test Länk till annan webbplats.](https://frejaeid.atlassian.net/wiki/spaces/DOC/pages/35029022/Freja+Mobile+Application+Testing+Instructions)

### Organisationslegitimation för produktionsmiljö

För att använda Skatteverkets driftsatta tjänster behövs en e-legitimation eller organisationslegitimation. För närvarande accepterar Skatteverket endast organisationslegitimationer som är utfärdade av Expisoft. Observera att organisationslegitimation för produktionsmiljö även kallas ”serverlegitimation” på Expisofts webbplats. Du beställer legitimationen via den här länken:

- [Expisoft organisationslegitimation/serverlegitimation Länk till annan webbplats.](https://eid.expisoft.se/products/certificates/?product_id=5)

## Två varianter av legitimation – valfri och utpekad organisationslegitimation

För Skatteverkets API:er finns två sätt som organisationslegitimation kan användas. Vi kallar de två varianterna för

1. valfri organisationslegitimation
2. utpekad organisationslegitimation.

Vilken variant som passar, beror på vad API:et du ska använda har stöd för. Ibland finns stöd för båda och då får du själv välja den variant som passar dina behov.

### Flöden med valfri organisationslegitimation

Flöden med valfri organisationslegitimation innebär att du kan skicka med vilken giltig organisationslegitimation som helst när du anropar API:et. För dessa flöden behöver du också autentisera dig med en client secret, som du får av oss.

Fördelen med denna variant är att du kan använda samma organisationslegitimation och API-nycklar för både Client Credentials Grant (CCG) och Authorization Code Grant (ACG), beroende på hur ni har utvecklat er lösning. Du kan också använda dina API-nycklar för att använda ACG med e-legitimation.

### Flöden med utpekad organisationslegitimation

Utpekad organisationslegitimation innebär att du behöver fylla i vilken organisationslegitimation du kommer att använda redan när du ansöker om att få ansluta till API:et.

Det OAuth2 client ID du får av oss kommer då vara knutet till just den organisationslegitimationen. Autentiseringen sker med kombinationen client ID och organisationslegitimationen.

Fördelen med den här lösningen är att den är snabb och enkel att implementera. Nackdelen är att du behöver uppdatera API-anslutningen och få nya API-nycklar och nytt applikations-ID om du vill använda ett annat säkerhetsflöde.

## Organisationslegitimation och ombudsrollen

Varje programvaruföretag som ska använda våra API:er måste ha en egen organisationslegitimation. Har ditt företag behov av att hämta ut information som tillhör någon av era kunder, behöver kunden först utse ditt företag till juridiskt läsombud. Behörigheten innebär att programvaruföretag i högre grad kan automatisera sina interna processer när de hämtar information från Skatteverkets API:er.

### Situationer när ombudsbehörighet kan behövas

- Tjänste- eller programvaruföretag vill automatiserat hämta eller läsa information från API:er för alla kunder, utan att representanter för kunderna behöver godkänna med privat e-legitimation.
- Ett moderbolag i en koncern vill automatiserat hämta eller läsa information för sina dotterbolag, utan att representanter för dessa behöver godkänna med privat e-legitimation.
- Tjänste- eller programvaruföretag har behov av att kunna kontrollera att rapporteringar och betalningar har utförts, samt skicka påminnelser i de fall någon försening har uppstått.
- Tjänste- eller programvaruföretag vill veta vilka kunder som ska rapportera vad – och vid vilken tidpunkt.

### Juridiskt läsombud

Tjänste- och programvaruföretag med programvara som Skatteverket har godkänt kan utses till juridiskt läsombud. Fysiska personer kan inte få behörighet som juridiskt läsombud. För att kunna använda behörigheten måste företaget:

- Ha tecknat avtal om att använda Skatteverkets API:er.
- Ha tillgång till en utfärdad och godkänd organisationslegitimation.

### Samma organisationsnummer för ombudsroll och organisationslegitimationen

För att kunna hämta information för någon av de kunder ni är ombud för, måste ombudsrollen och den organisationslegitimationen ni använder för att anropa API:et vara knutna till samma organisationsnummer.

### Att utse ett företag till juridiskt läsombud

Ditt företag kan bli juridiskt läsombud genom att din kund gör något av följande:

- Loggar in med e-legitimation i e-tjänsten "Ombud och behörigheter"
- Använder pappersblanketten
- Använder operationen Hämta djuplänk för att utse ombud i API:et Ombudshantering 2.0.

Dina kunder utser därefter ditt företag till att vara deras ombud.

Det enklaste och säkraste sättet är att kunder eller deras representanter använder e-tjänsten och lägger till de roller som behövs.

Via pappersblanketten tar processen att utse er till ombud cirka två veckor.

Väljer du att använda API:et Ombudshantering och hämtar en djuplänk, får du en länk till en sida i e-tjänsten "Ombud och behörigheter" där den önskade ombudsrollen är förvald. Detta gör det enklare för användaren att dela ut ombudsroller till er som programvaruföretag. Observera att den externa användaren behöver identifiera sig med organisationslegitimation för att kunna använda API:et Ombudshantering.

När ditt företag har registrerats som ombud får ni ett meddelande. Du kan även kontrollera vilka kunder som har tilldelat er behörigheten genom att ställa frågan i Skatteverkets API Ombudshantering.

- [Ombud och behörigheter - e-tjänst Länk till annan webbplats.](https://www.skatteverket.se/foretag/etjansterochblanketter/allaetjanster/tjanster/ombudochbehorigheter.4.18e1b10334ebe8bc80005609.html)
- [Ombud och behörigheter - blanketter Länk till annan webbplats.](https://www.skatteverket.se/foretag/etjansterochblanketter/allaetjanster/tjanster/ombudochbehorigheter.4.18e1b10334ebe8bc80005609.html#:~:text=f%C3%B6r%20omst%C3%A4llningsst%C3%B6d%20%2D%20Koncerningivare-,Blanketter,-Ans%C3%B6kan%20%E2%80%93%20Deklarationsombud%20\(SKV)
- [API:et Ombudshantering 2.0 Länk till annan webbplats.](https://www.skatteverket.se/foretag/etjansterochblanketter/allaetjanster/tjanster/ombudochbehorigheter.4.18e1b10334ebe8bc80005609.html#:~:text=f%C3%B6r%20omst%C3%A4llningsst%C3%B6d%20%2D%20Koncerningivare-,Blanketter,-Ans%C3%B6kan%20%E2%80%93%20Deklarationsombud%20\(SKV)