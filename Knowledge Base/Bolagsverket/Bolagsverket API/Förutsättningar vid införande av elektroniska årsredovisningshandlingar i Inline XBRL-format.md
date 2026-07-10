---
title: "Förutsättningar vid införande av elektroniska årsredovisningshandlingar i Inline XBRL-format"
source: "https://bolagsverket.se/apierochoppnadata/lamnaforetagsinformation/digitalinlamningavarsredovisningochrevisionsberattelse/forutsattningarvidinforandeavelektroniskaarsredovisningshandlingariinlinexbrlformat.5957.html"
author:
published: 2026-07-02
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
Det här är ett stöd till aktörer som vill upprätta eller konsumera årsredovisningshandlingar i Inline XBRL -format (iXBRL). Här beskriver vi grundläggande och väsentliga förutsättningar för att möjliggöra ett framgångsrikt införande.

Innan ni påbörjar er implementation av iXBRL -handlingar så bör ni ha läst samt analyserat punkterna på den här sidan. Punkterna är tänkta att fungera som ett komplement och behöver inte ersätta interna arbetssätt.

## Förutsättningar för en framgångsrik implementation

- Utbilda och förstå möjligheter samt begränsningar med XBRL / iXBRL -standarden.
	- Medlemmar inom projektgruppen bör ha kunskap om standarden.
		- Sprid kännedom om standarden och dess egenskaper till övriga delar inom organisationen.
- Medlemmar inom team för implementation, test och support bör bestå av en mix av teknisk- och redovisningskompetens som har kompetens inom standarden.
- Tillgång till internt XBRL-verktyg med stöd för validering av handlingar upprättade i iXBRL/XBRL-format.
- Tillgång till Bolagsverkets testbänk för validering.
	- Testbänken ska endast ses som ett komplement till ett internt XBRL-verktyg.
		- Testbänkens kontrollerar inte ”allt” utan genomför bara ett fåtal kontroller av struktur och innehåll. Kontrollernas huvudsakliga uppgift är att säkerställa att Bolagsverket kan handlägga handlingen samt att den inte innehåller information som är skadlig.
		- **Observera!** Testbänken innehåller inte kontroller som säkerställer att handlingen är 100 procent korrekt upprättat redovisningsmässigt eller tekniskt. Ansvaret med att säkerställa att iXBRL-handling är korrekt taggad och följer de tekniska samt redovisningsmässiga regler/standarder/anvisningar ligger på er organisation.
- Verifiera att den visuella informationen i Inline XBRL dokumentet är korrekt representerad även i instansdokumentet (XML-data).
- Säkerställ att iXBRL-filen kan producera en väl disponerad utskrift med sidbrytningar i olika webbläsare samt som pdf-fil i Bolagsverkets testbänk.

## Läs och analysera följande specifikationer, dokumentation och exempel

- [Allmänt om XBRL Länk till annan webbplats.](http://taxonomier.se/faq.html) i FAQ på taxonomier.se.
- [XBRL 2.1 Länk till annan webbplats.](https://specifications.xbrl.org/work-product-index-group-base-spec-base-spec.html) specifikationen på xbrl.org.
- [Inline XBRL 1.1 Länk till annan webbplats.](https://specifications.xbrl.org/spec-group-index-inline-xbrl.html) och [Transformation Registry Länk till annan webbplats.](https://specifications.xbrl.org/spec-group-index-inline-xbrl.html) specifikationerna på xbrl.org.
- Dokumentation för [aktuell taxonomi Länk till annan webbplats.](http://taxonomier.se/taxonomier.html) på taxonomier.se.
	- För innehåll och utformning någon av nedanstående:
		- Onlinepresentation av taxonomins innehåll och utformning.
				- Excelfil med enklare presentation av taxonomins innehåll och utformning.
		- För taxonomins struktur och uppbyggnad:
		- Översiktlig beskrivning av taxonomiramverkets tekniska arkitektur.
- Bolagsverkets [tillämpningsanvisningar](https://bolagsverket.se/apierochoppnadata/lamnaforetagsinformation/digitalinlamningavarsredovisningochrevisionsberattelse/tekniskdokumentationfordigitalinlamningavarsredovisning.5937.html) här på bolagsverket.se.
- [Tillämpningsexempel Länk till annan webbplats.](http://www.taxonomier.se/tillampning.html) på taxonomier.se. Exemplen är visuellt beskrivna samt taggade i iXBRL med exporterat data i form av ett instansdokument.
	- [Taggning av monetära värden Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-1/taggning-exempel-1.xhtml):
		- Beskriver taggning av belopp som redovisas i olika valutor, positiva/negativa värden samt redovisning i heltal, hundratal och tusental.
				- I exemplen tillämpas även format-attributet och Transformation Registry specifikationen.
				- Extraherat [instansdokument Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-1/taggning-exempel-1.xbrl).
		- [Tillämpning av sign-attribut i iXBRL Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-7/taggning-exempel-7.xhtml):
		- Beskriver hur sign-attributet ska tillämpas i iXBRL-filen. Attributet ska tillämpas när ett negativt värde förväntas i instansdokumentet(data-filen).
				- **Observera** att attributet kan tillämpas på samtliga numeriska begrepp.
				- Extraherat [instansdokument Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-7/taggning-exempel-7.xbrl).
		- [Taggning av procenttal Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-2/taggning-exempel-2.xhtml):
		- Beskrivning taggning av procenttal som är större/mindre än 100% samt positiva/negativa tal.
				- Extraherat [instansdokument Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-2/taggning-exempel-2.xbrl).
		- [Taggning av datum Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-3/taggning-exempel-3.xhtml):
		- Beskriver taggning av datumvärden med olika datumformat genom tillämpning av format-attributet och Transformation Registry specifikationen.
				- Extraherat [instansdokument Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-3/taggning-exempel-3.xbrl).
		- [Taggning av odefinierade begrepp (utökad information) Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-4/taggning-exempel-4.xhtml):
		- Taggning av data som saknar begrepp i taxonomin men har stor vikt för handlingen. Informationen bör taggas med taxonomin för utökad information för att förenkla maskinell tolkning av handlingar. Det finns exempel på hur man taggar monetära, numeriska, procenttal och textuella värden.
				- Extraherat [instansdokument Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-4/taggning-exempel-4.xbrl).
		- [Taggning av ändrade rubriker (utökad information) Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-5/taggning-exempel-5.xhtml):
		- Taggning av begrepp där radrubriken i Inline XBRL presentationen inte överensstämmer med radrubriken som definierats i taxonomin. Taggningen är väsentlig vid maskinell tolkning av informationen. Genom taggning kan en konsument av information avgöra om den nya radrubriken har påverkat betydelsen/omfattningen av den ursprungliga definitionen i taxonomin.
				- Extraherat [instansdokument Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-5/taggning-exempel-5.xbrl).
		- [Taggning av notkopplingar (utökad information) Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-6/taggning-exempel-6.xhtml):
		- Taggning av årsredovisningens visuella referenser mellan resultat- och balansräkning även kallade notkopplingar. Kopplingen möjliggör maskinell tolkning av dessa referenser för informationskonsumenter.
				- Extraherat [instansdokument Länk till annan webbplats.](http://xbrl.taxonomier.se/se/exempel/taggning/exempel-6/taggning-exempel-6.xbrl).
- [Tillämpning av XBRL och taxonomier i FAQ på taxonomier.se Länk till annan webbplats.](http://taxonomier.se/faq.html).
- [Exempel på årsredovisningshandlingar Länk till annan webbplats.](http://taxonomier.se/exempel.html) och de olika beståndsdelarna.