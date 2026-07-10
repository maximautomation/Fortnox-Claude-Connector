---
title: "Överenskommelse om anslutning av Bolagsverket till Motparts system för behörighetsverifiering"
source: "https://bolagsverket.se/apierochoppnadata/hamtaforetagsinformation/hamtainformationomverklighuvudman/overenskommelseomanslutningavbolagsverkettillmotpartssystemforbehorighetsverifiering.6037.html"
author:
published: 2026-06-24
created: 2026-07-09
description: "Bolagsverket registrerar företag och tillhandahåller aktuell företagsinformation, för ett enklare företagande och ett tryggt näringsliv."
tags:
  - "clippings"
---
## 1 Parter

Bolagsverket, organisationsnummer 202100-5489, och **\[Motpartens namn\]**, organisationsnummer \[xxxxxx-xxxx\], (nedan kallad ”Motparten”).

## 2 Syfte och omfattning

Registret över verkliga huvudmän förs av Bolagsverket med stöd av lag (2017:631) om registrering av verkliga huvudmän. Avsikten med registret är att tillgängliggöra informationen i registret och att därigenom bidra till arbetet mot penningtvätt och finansiering av terrorism. Bolagsverket är personuppgiftsansvarig avseende behandlingen av personuppgifter i registret och myndigheten ska se till att det inte uppkommer något otillbörligt intrång i de registrerades personliga integritet eller några risker från säkerhetssynpunkt.

Utlämnande av uppgifter från registret i elektroniskt format regleras i lagen (2017:631) om registrering av verkliga huvudmän. För att säkerställa att utlämnandet av uppgifter från registret överensstämmer med de författningsreglerade kraven krävs det en behörighetskontroll innan uppgifter får lämnas ut från registret. Detta avtal skapar tekniska förutsättningar för en sådan behörighetskontroll.

Denna överenskommelse möjliggör för Bolagsverket att verifiera att en viss identifierad fysisk person är behörig att för Motpartens räkning få åtkomst till uppgifter ur registret.

Motparten, det vill säga en part som avses i art. 11.2-3 och art. 12.2 i direktiv (EU) 2024/1640 (6:e penningtvättsdirektivet), ska tillhandahålla uppgift från ett internt behörighetsregister till Bolagsverket. Behörighetsregistret ska utvisa om en person är behörig att för Motpartens räkning hämta information från registret över verkliga huvudmän. Uppgift ur behörighetsregistret ska tillhandahållas efter särskild fråga från Bolagsverket genom ett API enligt denna överenskommelse.

Bolagsverket ska endast ställa frågor om huruvida viss identifierad person förekommer i behörighetsregistret eller inte. Bolagsverket förfrågan ska således vara binär.

API:et får inte användas för något annat ändamål än att verifiera legitimerad användares behörighet.

## 3 Motpartens behörighetsregister

Motparten ska ha ett behörighetsregister där personer som ska utföra arbete eller uppdrag för Motpartens verksamhet, och där åtkomst till registret över verkliga huvudmän krävs, registreras.

Motparten ansvarar självständigt för att:

- upprätta och förvalta sitt behörighetsregister
- registrera och avregistrera behöriga personer i behörighetsregistret
- att behandling av personuppgifter sker i enlighet med vid var tid gällande rätt
- att åtkomst till uppgifter om verkliga huvudmän endast sker för sådana ändamål och under sådana förutsättningar som följer av tillämplig reglering
- självständigt prövar förutsättningarna för utlämnande från behörighetsregistret till Bolagsverket.

Bolagsverket ansvarar inte för innehållet i Motpartens behörighetsregister eller för Motpartens bedömningar enligt första och andra stycket i detta avsnitt.

## 5 Tekniska krav och anslutning

Frågor till API:et får ske med hjälp av identifieringsuppgifter enligt format som anges i implementationsanvisningen här på bolagsverket.se.

Bolagsverket har rätt att uppdatera tekniska specifikationer och säkerhetskrav.

## 6 Bolagsverkets åtagande

Bolagsverket åtar sig att:

- endast använda svar från API:et vid behörighetskontroll för åtkomst till registret över verkliga huvudmän
- hålla detaljerade tekniska krav tillgängliga på bolagsverket.se
- meddela Motparten i skälig tid innan förändringar av tekniska specifikationer och säkerhetskrav träder i kraft.

## 7 Motpartens åtagande

Motparten åtar sig att:

- tillhandahålla ett API enligt den tekniska specifikation, säkerhetsmodell och kommunikationsstandard som Bolagsverket publicerar eller meddelar
- säkerställa att API:et håller sådan tillgänglighet att Bolagsverket utan oskäligt avbrott kan genomföra behörighetsverifiering.
- meddela Bolagsverket om planerade driftavbrott i skälig tid
- utan oskäligt dröjsmål informera Bolagsverket om incidenter eller störningar som kan påverka tjänstens funktion, säkerhet eller tillgänglighet.

Närmare krav på tillgänglighet och support framgår bolagsverket.se.

## 8 Informationssäkerhet

Parterna ska vidta lämpliga tekniska och organisatoriska säkerhetsåtgärder för att skydda information och kommunikation enligt denna överenskommelse.

Detaljerad beskrivning av hantering av informationssäkerhet finns i implementationsanvisningen på bolagsverket.se.

## 9 Personuppgiftsansvar

Bolagsverket respektive Motparten är var för sig personuppgiftsansvariga för den behandling av personuppgifter som respektive aktör utför.

## 10 Ändringar

Om Motpartens användning, rättsliga förutsättningar eller verksamhet förändras på sådant sätt att förutsättningarna för denna överenskommelse påverkas ska Motparten utan dröjsmål underrätta Bolagsverket.

Bolagsverket har rätt att ompröva anslutningen vid förändrade rättsliga, tekniska eller säkerhetsmässiga förutsättningar.

## 11 Skada och ansvar

Part ansvarar för skada som denne genom försummelse eller bristande efterlevnad av överenskommelsen orsakar den andra parten, med de begränsningar som anges i detta avsnitt.

Parternas skadeståndsansvar är begränsat till ansvar för direkt skada som denne vållar annan Part genom vårdslöshet. Part ansvarar inte för indirekt skada eller förlust, den andra partens eventuella ersättningsskyldighet gentemot tredje man eller för skador som tredje man orsakat.

Parts skadeståndsansvar per skadetillfälle är begränsat till ansvar för skada uppgående till ett belopp som maximalt motsvarar 10 prisbasbelopp enligt socialförsäkringsbalken (2010:110). Begränsningarna som anges här ska inte gälla om uppsåt eller grov vårdslöshet föreligger.

Part ska skriftligen framställa ersättningsanspråk senast sex (6) månader efter det att denne uppmärksammat att grund för krav föreligger för att inte förlora sin rätt till talan rörande sådant anspråk.

## 12 Force majeure

Om part är förhindrad att fullgöra sina överenskomna förpliktelser till följd av omständigheter utanför partens kontroll och som parten inte skäligen kunde förväntas ha räknat med vid överenskommelsens ingående och vars följder parten inte heller skäligen kunde ha undvikit eller övervunnit, till exempel krig, eldsvåda, översvämning, avbrott i allmänna kommunikationer, avbrott i den allmänna energiförsörjningen eller därmed jämställd omständighet, ska detta utgöra grund för befrielse från eventuella påföljder.

Ifråga om strejk, lockout och blockad gäller första stycket även om det är parten själv som vidtar eller är föremål för sådan konfliktåtgärd.

Part som önskar åberopa force majeure ska omedelbart underrätta den andra parten när det finns risk att viss förpliktelse inte kan infrias eller bli fördröjd därav. Underlåtelse att lämna meddelande i tid medför skyldighet att ersätta den skada som hade kunnat undvikas om meddelande lämnats i tid.

Part som till befrielse åberopar force majeure ska vidta alla rimliga ansträngningar för att begränsa följderna och skadan av att överenskommelsen inte kan fullgöras såsom överenskommits mellan parterna.

## 13 Överenskommelsens giltighetstid och uppsägning

Denna överenskommelse träder i kraft när Bolagsverket har mottagit en undertecknad överenskommelse och gäller tills vidare. Båda parter har rätt att när som helst säga upp överenskommelsen skriftligen. Uppsägningstiden börjar gälla från och med att den skriftliga uppsägningen har nått överenskommelsepart. Oavsett vem som säger upp överenskommelsen slutar den att gälla vid efterföljande månadsskifte.

Bolagsverket har rätt att med omedelbar verkan stänga av anslutningen eller säga upp överenskommelsen om:

- Motparten bryter mot denna överenskommelse.
- En säkerhetsrisk föreligger.
- Motparten behandlar uppgifter i strid med tillämplig reglering.
- Motparten inte längre kan antas omfattas av 6:e penningtvättsdirektivet.
- Rättsliga förutsättningar för att lämna ut uppgifter till Motparten har förändrats.
- API:et inte uppfyller överenskomna tekniska eller säkerhetsmässiga krav.

Datum, ort och underskrifter av registrerad firmatecknare eller firmatecknare genom fullmakt