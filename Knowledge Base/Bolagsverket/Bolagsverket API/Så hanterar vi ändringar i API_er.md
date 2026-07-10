---
title: "Så hanterar vi ändringar i API:er"
source: "https://bolagsverket.se/apierochoppnadata/driftochsupport/sahanterarviandringariapier.4811.html"
author:
published: 2025-11-21
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
Här beskrivs vilka slags förändringar som kan bli aktuella, hur dessa kommuniceras samt med vilken framförhållning förändringarna meddelas. Rutinen gäller för våra API:er.

Avsteg från Bolagsverkets utfästelse rörande förändringar kan ske med anledning av säkerhetsskäl, ny författningsreglering, beslut av domstol eller annan myndighet eller annat särskilt skäl.

## Typer av förändring

Vi skiljer på mindre förändringar och större förändringar baserat på vilken insats det medför för dig som använder API:et.

För att ange en viss version av ett API används två siffror. Första siffran representerar en större förändring kallat huvudversion. Andra siffran representerar en mindre förändring i aktuell huvudversion.

En API-version är då uppbyggd på följande sätt; \<API namn> \<huvudversion>.\<mindre förändring>

### Exempel

API Företagsinformation 1.0  
Observera att namnsättningen av API:et i en URL kommer att vara spårbar mot versionen.

Företagsinformation kan exempelvis ha "…/V1/…” i URL och motsvarar då huvudversion.

Använder du ett API för första gången ska du välja den högsta tillgängliga huvudversionen.

## 1.1 Mindre förändring

En mindre förändring är bakåtkompatibel, vilket innebär att du inte måste göra några kodmodifieringar för att fortsätta att använda dig av API:et. Tillgängliggörande av en mindre förändring innebär att den föregående förändringen direkt upphör att gälla.

Exempel på mindre förändringar:

- funktionalitetsförändringar där API:ets beteende är opåverkat
- ny metod i API:et
- nytt icke obligatoriskt attribut i API:et
- utökad information från API:et.

Meddelande om kommande förändringar av detta slag publiceras som en nyhet i anslutning till att förändringen för aktuellt API blir verklighet.

[Nyheter och releaser för våra API:er](https://bolagsverket.se/apierochoppnadata/nyheterochreleaser.5497.html)

## 1.2 Större förändring

En större förändring är inte bakåtkompatibel, vilket kräver att du gör förändringar i din kod för att använda dig av den nya versionen av API:et. Tillgängliggörande av en version med större förändring innebär att den tidigare huvudversionen samexisterar med den nya huvudversionen under en viss tid.

Observera att vi erbjuder maximalt **två** samtidigt pågående huvudversioner under maximalt **18 månader** av våra API:er.

Vid en större förändring ökar huvudversionen av API:et.

Exempel på större förändringar:

- funktionalitetsförändringar som ändrar API:ets beteende
- namnbyte på befintlig metod i API:et
- borttagning av API metod
- nytt obligatoriskt attribut i API:et.

Meddelande om kommande förändringar av detta slag publiceras i anslutning till aktuellt API en tid innan förändringen blir verklighet. Vid avveckling av en huvudversion meddelas detta minst **sex månader** innan definitiv borttagning sker.