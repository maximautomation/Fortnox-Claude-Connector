---
title: "Kom igång med utvecklarportalen"
source: "https://support.fortnox.se/kom-igang/integrationer/kom-igang-med-utvecklarportalen"
author:
published: 2024-04-15
created: 2026-07-09
description: "Utvecklarportalen är en kostnadsfri modul som används för att skapa och administrera såväl integrationer som testmiljöer."
tags:
  - "clippings"
---
Integration

Utvecklarportalen är en kostnadsfri modul som används för att skapa och administrera såväl integrationer som testmiljöer.

För att få tillgång till utvecklarportalen kan du registrera dig som utvecklare på vår hemsida:

[https://www.fortnox.se/developer](https://www.fortnox.se/developer)

![För att få tillgång till utvecklarportalen kan du registrera dig som utvecklare på vår hemsida, www.fortnox.se/developer](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2489x1192%2Fbfbc1a7df2%2Futvecklarportalen1.png%2Fm%2F&w=3840&q=75)

Om du har ett befintligt abonnemang och vill lägga till licensen behöver en systemadministratör skapa ett supportärende, så hjälper vi dig vidare.

Här kan du läsa mer om hur du skapar ett supportärende: [Fortnox Support](https://support.fortnox.se/hantera-fortnox/allman-info/fortnox-support#sjalvservice-kontakta-oss-pagaende-chatt)

När du fått licenserna tillagda behöver behöver du tilldela dessa licenser till de användare som ska ha tillgång till utvecklarportalen.

Här kan du läsa mer om hur du tilldelar licenser: [Administrera användare](https://support.fortnox.se/hantera-fortnox/administrera-anvandare/nya-administrera-anvandare)

Efter att användaren loggat ut och in igen finns utvecklarportalen under **Meny** uppe till vänster.

## Integrationer

Kopiera länk hit

För att skapa en integration behöver du först ta dig till utvecklarportalen genom att klicka på **Meny** uppe till vänster och välja just **Utvecklarportal**.

Här kan du klicka på **Skapa integration**. När du har angett ett namn skapas integrationen, och du kan sedan redigera inställningarna.

![Här kan du klicka på Skapa integration. När du har angett ett namn skapas integrationen, och du kan sedan redigera inställningarna.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2536x1206%2Fe00610dafe%2Futvecklarportalen2.png%2Fm%2F&w=3840&q=75)

### Oauth

Under menyvalet **Oauth** kan du se och justera de värden som används vid aktiveringen av din integration.

Ditt Client ID samt Client Secret är en publik respektive en hemlig nyckel för din integration.

I fältet för din Redirect URI kan du ange den URI som användaren kommer att dirigeras till efter att autentisering genomförts och integrationens behörigheter godkänts. Det är också på denna sida som din **Authorization code** visas som en parameter i länken.

Längst ner på denna sida hittar du slutligen inställningar för de behörigheter som integrationen ska kunna efterfråga, också känt som scopes.

Ändrar du dessa behörigheter för en integration som redan används kommer behörigheterna inte påverkas för de befintliga kopplingarna. Integrationen behåller alltså de behörigheter som gällde vid aktiveringen. Om du vill justera behörigheterna behöver integrationen aktiveras på nytt.

### Publicering av integration

Under menyvalen **Integration, Bilder, Texter, Prismodell** samt **Publicering** kan du lägga till och justera information som används vid publiceringen av din integration.

Om du inte önskar publicera integrationen fungerar det alltså utmärkt att bortse från dessa flikar.

Här kan du läsa mer om hur du publicerar din integration:[För utvecklare - Publicera er integration](https://support.fortnox.se/hantera-fortnox/integrationer/for-utvecklare-publicera-er-integration)

## Riskzon

Kopiera länk hit

![Den sista fliken har två funktioner, att rotera Client Secret samt att radera integrationen.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F1723x826%2F87ee957752%2Futvecklarportalen3.png%2Fm%2F&w=3840&q=75)

Den sista fliken har två funktioner, att rotera Client Secret samt att radera integrationen.

Önskar du rotera din Client Secret är det bra att tänka på att användare av integrationen inte kan logga in förrän du uppdaterat ditt Client Secret i integrationen.

Integrationen kommer också behöva aktiveras på nytt av samtliga kunder för att ni ska få ut nya fungerande tokens.

Det är även från denna fliken som det går att radera integrationen. Om du har en publicerad integration skulle den först behöva avpubliceras innan den går att radera.

Tänk även på att meddela dina användare i god tid innan en integration tas bort.

## Testmiljöer

Kopiera länk hit

Vi tillhandahåller testmiljöer för att du ska kunna testa din kod i en säker miljö innan du ansluter mot dina kunder.

Du kan skapa upp till 30 olika testmiljöer samtidigt för att testa och demonstrera din integrations funktionalitet i gränssnittet.

![Vi tillhandahåller testmiljöer för att du ska kunna testa din kod i en säker miljö innan du ansluter mot dina kunder.](https://support.fortnox.se/_next/image?url=https%3A%2F%2Fa.storyblok.com%2Ff%2F197721%2F2556x907%2F1efdae5147%2Futvecklarportalen4.png%2Fm%2F&w=3840&q=75)

För att skapa en testmiljö klickar du först på fliken **Testmiljöer** uppe till vänster. Du kan därefter välja **Skapa testmiljö** till höger för att skapa miljön.

Testmiljön skapas med en användare som har samma mailadress som den användare som skapade miljön.

Ett inbjudningsmail skickas till den e-postadressen. Efter att du accepterat inbjudan har du därefter åtkomst till testmiljön och möjlighet att aktivera integrationer.

Du administrerar testmiljöerna precis på samma sätt som ett vanligt bolag i Fortnox.

Skulle du vilja radera en testmiljö kan du enkelt klicka på den och sedan välja **Ta bort testmiljö**.

## Publicera integration

Kopiera länk hit

Resterande flikar, det vill säga **Statistik, Försäljning, Utvecklarprofil** och **Marknadsföring** gäller alla publiceringen av integrationer.

Här kan du läsa mer om övriga flikarna i utvecklarportalen: [För utvecklare: Publicera er integration](https://support.fortnox.se/hantera-fortnox/integrationer/for-utvecklare-publicera-er-integration)

Dela denna artikel

Länk kopierad