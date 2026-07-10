---
title: "Bokföring från kontoutdrag - Inställningar och behörigheter"
source: "https://support.fortnox.se/produkthjalp/bokforing/bokforing-fran-kontoutdrag-installningar-och-behorigheter"
author:
published: 2024-03-19
created: 2026-07-09
description: "Under Inställningar i Bokföring från kontoutdrag kan du själv välja hur dina transaktioner ska hanteras. Du hittar inställningarna genom att klicka på kugghjulet uppe till höger."
tags:
  - "clippings"
---
Bokföring

Under Inställningar i Bokföring från kontoutdrag kan du själv välja hur dina transaktioner ska hanteras. Du hittar inställningarna genom att klicka på kugghjulet uppe till höger.

![Du hittar inställningarna genom att klicka på kugghjulet uppe till höger.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2544x814%2F5bf85ec9cb%2Finstallningar-bokforing-kontoutdrag1.png%2Fm%2F&w=3840&q=75)

## Bokför automatiskt

Kopiera länk hit

Du som användare kan själv reglera om du vill använda dig av den automatiska bokföringen. Om du väljer att stänga av automatiken innebär det att du behöver hantera varje transaktion manuellt i Bokföring från kontoutdrag under menyvalet **Transaktioner**.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1070x912%2Fa80d21e03b%2Fny-bokfor-automatiskt.png%2Fm%2F&w=3840&q=75)

## Bokför öresavrundning automatiskt

Kopiera länk hit

Med funktionen **Bokför öresavrundning automatiskt** aktiv under **Kugghjulet > Transaktioner** automatiseras din bokföring ytterligare. Systemet hanterar då transaktioner som diffar med 1–99 öre helt automatiskt genom att bokföra mellanskillnaden som en öresavrundning.

Kontot för denna avrundning hämtas från de inställningar som finns under **Kugghjulet > Leverantörsfakturor/Fakturering > Förvalda konton > Avrundning.**

***Observera*** att om inget konto är förvalt här kommer öresavrundningen inte att kunna bokföras.

## Bokför automatiskt vid påminnelse

Kopiera länk hit

Du som användare kan reglera om du vill använda dig av den automatiska bokföringen trots att transaktionen avser en inbetalning exklusive skickad påminnelseavgift.

Aktiveras inställningen kommer Fortnox att bokföra automatiskt vid unik match på faktura. Detta kommer leda till att fakturan blir slutbetald och påminnelseavgiften förväntas inte att drivas in.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1077x926%2F946d5133b1%2Fny-vid-paminnelse.png%2Fm%2F&w=3840&q=75)

## Ignorera transaktioner

Kopiera länk hit

Det finns möjlighet att välja att inte hantera en transaktion på ditt bankkonto, då använder du funktionen Ignorera transaktion. Fortnox rekommenderar att alla transaktioner hanteras eftersom det finns risk att bokföringen och transaktionerna på ditt bankkonto inte stämmer överens om en transaktion ignoreras. Att ignorera en transaktion innebär att den inte kopplas ihop med din bokföring, innan du ignorerar transaktionen bör du vara noga med att kontrollera att bokföringen är korrekt.

För att tillgängliggöra detta hanteringssätt behöver inställningen **Ignorera transaktion** aktiveras och användaren som ska ignorera transaktionen behöver ha behörighet att **Ta bort banktransaktioner**. Behörigheter regleras under [Administrera användare](https://support.fortnox.se/hantera-fortnox/administrera-anvandare/administrera-anvandare) .

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1060x916%2Fd08e44721c%2Fny-ignorera.png%2Fm%2F&w=3840&q=75)

## Koppla automatiskt

Kopiera länk hit

Inställningen möjliggör för fler typer av transaktioner att automatiseras. När inställningen aktiveras och en transaktion inte matchar mot en faktura, matchar Fortnox istället mot befintliga verifikationer och vid unik matchning genomförs kopplingen automatiskt.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1075x906%2Fb024fdf819%2Fny-koppla.png%2Fm%2F&w=3840&q=75)

## Välj tidsintervall

Kopiera länk hit

Inställningen **Välj tidsintervall** är en förlängning på Koppla automatiskt och innebär att transaktioner kan kopplas mot verifikat inom större intervall. Antalet som anges gäller för hur många dagar det får skilja mellan transaktions-och bokföringsdatum.

Om antalet anges till 0 dagar, kopplas transaktioner endast automatiskt mot verifikationer om summan är unik aktuell dag + att transaktionsdatum är samma som verifikationens bokföringsdatum.

Intervallet kan anges mellan 0-6 dagar och möjliggör således för transaktioner att kopplas mot verifikat där det finns en unik match på summa max 6 dagar innan-och efter transaktionsdatumet.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1090x915%2F664288b728%2Fny-intervall.png%2Fm%2F&w=3840&q=75)

## Regelverk

Kopiera länk hit

För en automatiserad och effektiv hantering av de transaktioner som inte matchar med en faktura eller befintligt verifikat, rekommenderar vi dig att skapa regelverk.

Ett regelverk innebär att du kan skapa diverse förutsättningar för hur transaktioner ska hanteras och bokföras med hjälp av olika parametrar, gränser och konton.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1614x776%2Fe31ed8cc01%2Fny-regel.png%2Fm%2F&w=3840&q=75)

Läs mer här: [Regelverk för automatisk bokföring](https://support.fortnox.se/produkthjalp/bokforing/regelverk-for-automatisk-bokforing)

## Behörigheter

Kopiera länk hit

Om användaren har behörighet till **Verifikationer** och **Bokför** så kommer användaren att kunna skapa och koppla verifikat.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F425x392%2Fb800b1fc1e%2Fny-verifikationer.png%2Fm%2F&w=1080&q=75)

Om användaren har behörighet till både in- och utbetalningar, alternativt till vyn **Stäm av konto**, så ser användaren alla transaktioner.

![](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F411x131%2F515edc9dcc%2Fny-stam-av-konto.png%2Fm%2F&w=828&q=75)

Om användaren har behörighet till **Inbetalningar** och **Kundfakturor** ser hen alla transaktioner som är inbetalningar. Användaren kan koppla och bokföra inbetalningarna.

Om användaren har behörighet till **Utbetalninga** r och **Leverantörsfakturor** ser hen alla transaktioner som är utbetalningar. Användaren kan koppla och bokföra utbetalningarna.

Om användaren har behörighet till **Stäm av konto** och **Ta bort banktransaktioner** kommer hen kunna ignorera transaktion.

Dela denna artikel

Länk kopierad