---
title: AEM Communities - översikt
seo-title: AEM Communities Overview
description: En översikt över AEM Communities funktioner och inställningar
seo-description: An overview of AEM Communities features and setup
uuid: 6e3ac9d2-ca31-40ea-8cab-b8451074c498
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 418cc919-0ae3-4c6c-8566-7e9a206f02a8
exl-id: 3a8b21f8-75da-4867-9a8a-80fddf7946ed
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1432'
ht-degree: 0%

---

# AEM Communities - översikt {#aem-communities-overview}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager (AEM) Communities ger möjlighet att snabbt skapa en lokal communitysajt som har förbättrade prestanda, förbättrad webbplatshantering och uppmuntrar till konvertering av besökare till värdefulla communitymedlemmar.

<!--
Contact your account representative for information regarding licensing of AEM Communities as well as additional licensing for enablement features and Adobe Analytics.
-->

## Funktioner i Communities {#communities-features}

Med AEM Communities kan man utveckla en relation med besökare på en webbplats som informerar genom bloggar, frågor och svar och händelsekalendrar, samtidigt som man får insikter genom forum, kommentarer och annat communityinnehåll, som ofta kallas användargenererat innehåll (UGC).

Dessutom tillåter AEM Communities moderering av betrodda medlemmar i publiceringsmiljön, social inloggning med Twitter och Facebook, intern översättning av communityinnehåll, skapande av communitygrupper från den publicerade communitysajten, poängsättning till prisutmärkelser, fildelning, meddelanden och aktivitetsströmmar.

Funktioner i Communities kan visas med [AEM Demo Machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki) som är tillgängliga offentligt på GitHub.com eller med den nya implementeringen av referensen We.Retail.

## Community Sites {#community-sites}

En communitywebbplats är en AEM webbplats som skapats med en enkel guide som ger en webbplats med många vanliga funktioner som är förkopplade till webbplatsen.

The [guide för att skapa webbplatser](sites-console.md):

* Sammanställer funktioner för webbplatsen, baserat på det valda [mall för communitywebbplats](sites.md) som
   * Skapat från [communityfunktioner](#community-functions)
   * Valfritt [communitygrupper](#communitygroups) funktion
* Använder inställningar för att konfigurera:
   * Moderering
   * Inloggning
   * Översättning
* Innehåller viktiga funktioner:
   * Responsiv design: Användningsområden [Twitter Bootstrap-teman](https://getbootstrap.com)
   * Inloggning: Självregistrering, [social inloggning](social-login.md), användarprofiler
   * Meddelanden: Medlemmarna ser händelser som är relevanta för dem
   * Meddelanden: Medlemmar kan skicka eller ta emot meddelanden på communitywebbplatsen
   * Sök: Möjlighet att söka på communitywebbplatsen
   * Språkväxling: Möjlighet att välja språk för [flerspråkig plats](../../help/sites-administering/translation.md)
   * Administration: Tillgång för behöriga medlemmar att moderera och hantera användare på communitywebbplatsen
* Eliminerar många steg i utvecklingen på sidnivå:
   * Varumärke: Valfri överföring av en banderollbild för visning på alla sidor i communitywebbplatsen
   * Navigeringsmeny: Navigeringslänkar finns för de funktioner som ingår i communitywebbplatsmallen

Om du snabbt vill skapa en ny community-webbplats kan du besöka [Komma igång med AEM Communities](getting-started.md).

## Community Content Persistence {#community-content-persistence}

För att förbättra prestanda och synkronisering av communityinnehåll behöver AEM Communities en gemensam lagringsplats för användargenererat innehåll (UGC) som delas mellan alla AEM (författare och publicering) instanser.

Community-innehåll är enkelt att komma åt via lagringsresursens leverantör (SRP), som tillhandahåller ett lager som åtskiljer åtkomsten från den underliggande topologin och stöder en gemensam lagringsplats för UGC.

Mer information om innehållets uthållighet och rekommenderade installationer finns på:

* [Community-innehåll](working-with-srp.md): diskuterar de tillgängliga SRP-lagringsalternativen för UGC
* [Rekommenderade topologier](topologies.md): diskuterar topologier baserat på användningsfall och SRP-val
* [Uppgradera till AEM 6.3 Communities](upgrade.md): ger användbar information om UGC vid övergång till AEM 6.3.

## Communities-konsoler {#communities-consoles}

I författarmiljön ger den globala navigeringskonsolen åtkomst till [Communities-konsol](consoles.md), som innehåller:

* [Webbplatser](sites-console.md) konsol

   * Skapa webbplats
   * Webbplatsredigering
   * Platshantering
   * [Community-grupper](groups.md) konsol

* [Moderering](moderation.md) konsol

   * Vanligt gränssnitt för massmoderering för skribent- och publiceringsmiljöer
   * Nya filtervillkor

* [Medlemmar och grupper](members.md) hanteringskonsoler

   * Ger möjlighet att skapa och hantera användare på publiceringssidan (medlemmar) från redigeringsmiljön
   * Möjlighet att förbjuda medlemmar
   * Ger möjlighet att skapa och hantera användargrupper på publiceringssidan (medlemsgrupper) från redigeringsmiljön

* [Rapporter](reports.md) konsol

   * Ger möjlighet att generera rapporter om uppdrag, inlägg och vyer

* [Resurser](resources.md) konsol

   * Möjlighet att skapa aktiveringsresurser och utbildningsvägar
   * Ger tillgång till rapporter om aktiveringsresurser och utbildningsvägar

Den globala verktygskonsolen ger tillgång till följande verktyg för communities:

* [Webbplatsmallar](tools.md#sitetemplatesconsole) konsol

   * Skapa och hantera communitymallar

* [Gruppmallar](tools.md#grouptemplatesconsole) konsol

   * Skapa och hantera communitygruppsmallar

* [Community-funktioner](tools.md#communityfunctionsconsole) konsol

   * Skapa och hantera communityfunktioner

* [Lagringskonfiguration](tools.md#storageconfiguratonconsole) konsol

   * Välj och konfigurera [gemensam lagringsplats](working-with-srp.md) för webbplatsen

* [Komponentguide](components-guide.md)

   * En exempelplats, [Community-komponenter](http://localhost:4502/editor.html/content/community-components/en.html), som innehåller ett exempel på alla Communities-komponenter med deras standardkonfiguration och möjlighet att experimentera med dem

## Mallar för communitywebbplatser {#community-site-templates}

Skapandet av communitysajter bygger på ett urval av mallar för communitysajter som snabbt skapar en community som är oberoende av valfri exempelwebbplats.

En mall för communitysajter, som består av communityfunktioner och mallar för communitygrupper, innehåller en struktur för en community-webbplats som inloggning, användarprofiler, meddelanden, webbplatsmeny, sökning, teman och varumärken.

Se [Konsol för webbplatsmallar](sites.md).

## Community-funktioner {#community-functions}

De funktioner som förväntas av en community-upplevelse är välkända. Med AEM Communities finns dessa funktioner som byggstenar, så kallade communityfunktioner.

Community-funktioner är vanliga AEM sidor som består av komponenter som är kopplade till en funktion som enkelt kan integreras i en viss webbplatsmall.

Se [Konsol för communityfunktioner](functions.md).

## Community-grupper och gruppmallar {#community-groups-and-group-templates}

Funktionen för communitygrupper är möjligheten för en undercommunity att skapas dynamiskt på en community-webbplats av behöriga användare och communitymedlemmar från både författarmiljön och publiceringsmiljön.

I författarmiljön kan communitygrupper (undergrupper) skapas inom en befintlig communitywebbplats eller kapslas inom en befintlig grupp när mallstrukturen innehåller [Funktionen Grupper](functions.md#groups-function).

När du skapar en community-grupp måste du välja en community-gruppmall som innehåller designen för communitygruppssidorna. När en gruppfunktion läggs till i en mallstruktur konfigureras den att antingen ange en gruppmall eller välja mallar när en ny gruppgrupp skapas.

Se även:

* [Konsol för webbplatsgrupper](groups.md) - skapa undergrupper i författarmiljön
* [Konsolen Gruppmallar](tools-groups.md) - skapa platsstruktur för grupper
* [Komma igång med AEM Communities](getting-started.md) - självstudiekurs för att snabbt skapa en communitysajt med kapslade grupper

## Community-komponenter {#community-components}

The [communitykomponenter](author-communities.md) från vilken en communitywebbplats byggs kan användas för att lägga till communityfunktioner till valfri AEM.

The [communitykomponentguide](components-guide.md) finns för interaktiv utforskning av komponenterna.

## Typ av Communities {#types-of-communities}

### Engagement Community {#engagement-community}

En engagemangscommunity är en communitywebbplats som fokuserar på att engagera kunder för att informera, begära feedback och låta kunderna interagera som communitymedlemmar.

En engagemangscommunity kan innehålla:

* Inloggning
* Meddelanden
* Forum
* Kommentarer
* Recensioner
* Klassificeringar
* Omröstning
* Bloggar
* Grupper
* Kalendrar
* Översättning
* Moderering
* Meddelanden
* Betyg och emblem
* Analysrapporter

Om du snabbt vill skapa en ny engagemangscommunity kan du besöka [Komma igång med AEM Communities](getting-started.md).

### Aktivera community {#enablement-community}

En community för hjälpsystem är en communitywebbplats som innehåller funktioner för onlineutbildning.

En community för aktivering kan innehålla:

* Alla funktioner i [engagemangscommunity](#engagement-community)
* Möjlighet att tilldela innehåll och utbildningsresurser till medlemmar och medlemsgrupper
* Stöder SCORM-innehåll, t.ex. frågor och tester
* Spåra slutförda tilldelningar
* Tillgång till rapporter och analyser
* Möjlighet att diskutera en utbildningsresurs via forum, meddelanden, kommentarer och omdömen

En aktiveringscommunity kan skapas när [Tillägget Aktivera är konfigurerat](enablement.md)som kräver ytterligare licenser för användning i produktionsmiljö. En webbplats för aktiveringscommunityn kommer att innehålla [tilldelningsfunktion](#community-functions).

Om du enkelt vill skapa en ny aktiveringscommunity går du till [Komma igång med AEM Communities för aktivering](getting-started-enablement.md).

## AEM Demo Machine {#aem-demo-machine}

The [AEM Demo Machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine) hanterar och kör demonstrationer för AEM [Webbplatser](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Sites), [Resurser](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Assets), [Communities](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Communities), [Appar](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Apps) och [Forms](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Scenario%20Forms), som ofta kräver mer konfiguration än att bara starta en QuickStart-instans. AEM Demo Machine konfigurerar ytterligare [infrastruktur](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Infrastructure) som MongoDB-, Solr-, MySQL-, FFmpeg- och e-postservrar.

AEM Demo Machine består av

* A [grafiskt användargränssnitt](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/User%20Interface)
* Apache ANT-skript med konfigurerbara [egenskaper](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Properties) och [mål](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki/Command%20Line)
* Paket för installation Den AEM demodatorn har testats med CQ 5.5, CQ 5.6.1, AEM 6.0, AEM 6.1, AEM 6.2 och AEM 6.3 i Windows, MacOS och Linux.

AEM Demo Machine kräver en giltig AEM.

>[!NOTE]
>
>Visa en [videointroduktion](https://www.youtube.com/watch?v=zEE_zkR9fVQ&amp;feature=youtu.be) till AEM Demo Machine (13:26).

## AEM Communities Documentation {#aem-communities-documentation}

* Besök [Distribuera webbgrupper](deploy-communities.md) om du vill veta mer om rekommenderade distributioner.

* Besök [Administrera webbgruppsplatser](administer-landing.md) om du vill veta mer om hur du skapar en community-webbplats, lägger till communitygrupper, konfigurerar mallar för communitywebbplatser, modererar communityinnehåll, hanterar medlemmar, taggning, meddelanden, poängsättning och emblem.

* Besök [Utveckla webbgrupper](communities.md) om du vill veta mer om ramverket för sociala komponenter (SCF) och hur du anpassar komponenter och funktioner i Communities.

* Besök [Komponenter i redigeringsgrupper](author-communities.md) om du vill lära dig hur du redigerar med och konfigurerar Communities-komponenter.
