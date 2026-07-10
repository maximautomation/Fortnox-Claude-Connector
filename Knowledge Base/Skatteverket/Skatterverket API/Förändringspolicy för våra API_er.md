---
title: "Förändringspolicy för våra API:er"
source: "https://www.skatteverket.se/omoss/digitalasamarbeten/omvaraapier/forandringspolicyforvaraapier.4.96cca41179bad4b1aaa558.html"
author:
published:
created: 2026-07-09
description: "Här beskrivs vilka slags förändringar som kan bli aktuella rörande våra riktade API:er, hur de kommuniceras samt när förändringarna meddelas."
tags:
  - "clippings"
---
Här beskrivs vilka slags förändringar som kan bli aktuella, hur dessa kommuniceras samt med vilken framförhållning förändringarna meddelas. Policyn gäller för både partner-API:er och riktade API:er.

Avsteg från Skatteverkets utfästelse rörande förändringar kan ske med anledning av säkerhetsskäl, ny författningsreglering, beslut av domstol eller annan myndighet eller annat särskilt skäl.

## Typer av förändring

Vi skiljer på mindre förändringar och större förändringar baserat på vilken insats det medför för dig som använder API:et.

För att ange en viss version av ett API används två siffror. Första siffran representerar en större förändring kallat huvudversion. Andra siffran representerar en mindre förändring i aktuell huvudversion.

Således är en API version uppbyggd på följande sätt; \<API namn> \<huvudversion>.\<mindre förändring>  
  
**Exempel:** Skattekonto 1.0  
Observera att namnsättningen av API:et i en URI kommer att vara spårbar mot versionen. Skattekonto kan t.ex. ha "…/V1/…” i URI och motsvarar då huvudversion.

Använder du ett API för första gången ska du välja den högsta tillgängliga huvudversionen.

## 1.1 Mindre förändring

En mindre förändring är bakåtkompatibel, vilket innebär att du inte måste göra några kodmodifieringar för att fortsätta att använda dig av API:et. Tillgängliggörande av en mindre förändring innebär att den föregående förändringen direkt upphör att gälla.  
  
Exempel på mindre förändringar:

- Funktionalitetsförändringar där API:ets beteende är opåverkat
- Ny metod i API:et
- Nytt icke obligatoriskt attribut i API:et
- Utökad information från API:et

Meddelande om kommande förändringar av detta slag publiceras i anslutning till aktuellt API en tid innan förändringen blir verklighet.

## 1.2 Större förändring

En större förändring är inte bakåtkompatibel, vilket kräver att du gör förändringar i din kod för att använda dig av den nya versionen av API:et. Tillgängliggörande av en version med större förändring innebär att den tidigare huvudversionen samexisterar med den nya huvudversionen under en viss tid. Vi eftersträvar ett läge där vi erbjuder maximalt två huvudversioner.

Vid en större förändring ökar huvudversionen av API:et.

Exempel på större förändringar:

- Funktionalitetsförändringar som ändrar API:ets beteende
- Namnbyte på befintlig metod i API:et
- Borttagning av API metod
- Nytt obligatoriskt attribut i API:et

Meddelande om kommande förändringar av detta slag publiceras i anslutning till aktuellt API minst sex månader innan förändringen blir verklighet. Vid avveckling av en huvudversion meddelas även detta minst sex månader innan definitiv borttagning sker.