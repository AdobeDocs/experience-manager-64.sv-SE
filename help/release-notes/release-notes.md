---
title: Allmän versionsinformation för Adobe Experience Manager 6.4
seo-title: Versionsinformation
description: 'Adobe Experience Manager 6.4 visar versionsinformation, nyheter, hur man installerar och detaljerade ändringslistor. '
seo-description: 'Adobe Experience Manager 6.4 visar versionsinformation, nyheter, hur man installerar och detaljerade ändringslistor. '
uuid: 5a220301-2727-4078-ba19-4a2dbf9657f4
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 2be468e7-2b4e-4e04-881b-b9bdd1f55e57
translation-type: tm+mt
source-git-commit: f1bf1545689b977a0f5074954df224db58cbd695
workflow-type: tm+mt
source-wordcount: '2745'
ht-degree: 1%

---


# Allmän versionsinformation för Adobe Experience Manager 6.4 {#general-release-notes-for-adobe-experience-manager}

## Versionsinformation {#release-information}

<table> 
 <tbody>
  <tr>
   <th>Produkt</th> 
   <td>Adobe Experience Manager<br /> </td> 
  </tr>
  <tr>
   <th>Version</th> 
   <td>6.4</td> 
  </tr>
  <tr>
   <th>Typ</th> 
   <td>Större release</td> 
  </tr>
  <tr>
   <th>Allmänt tillgänglighetsdatum</th> 
   <td>4 april 2018<br /> </td> 
  </tr>
  <tr>
   <th>Rekommenderade uppdateringar</th> 
   <td>Se <a href="https://helpx.adobe.com/experience-manager/aem-releases-updates.html">AEM-versioner och uppdateringar</a></td> 
  </tr>
 </tbody>
</table>

### Trivia {#trivia}

Versionscykeln för den här versionen av Adobe Experience Manager började den 27 april 2017, genomgick 22 versioner av kvalitetssäkring och felkorrigering och avslutades den 22 mars 2018. Det totala antalet kundrelaterade problem, inklusive förbättringar och nya funktioner som har korrigerats i den här versionen, är 704.

Adobe Experience Manager 6.4 är generellt tillgängligt sedan 4 april 2018.

>[!NOTE]
>
>Adobe rekommenderar att du installerar det senaste Service Pack-versionen eftersom alla nya funktionspaket endast levereras via [Service Pack](https://helpx.adobe.com/experience-manager/maintenance-releases-roadmap.html).

## What&#39;s new {#what-s-new}

Adobe Experience Manager 6.4 är en uppgraderingsversion till kodbasen Adobe Experience Manager 6.3. Den innehåller nya och förbättrade funktioner, viktiga kundkorrigeringar, högprioriterade kundförbättringar och allmänna felkorrigeringar som är inriktade på produktstabilisering. Det innehåller även merparten av alla funktionspaket, hot fix och Service Pack för Adobe Experience Manager 6.3.

Listan nedan innehåller en översikt, medan de efterföljande sidorna innehåller fullständig information.

### Experience Manager Foundation {#experience-manager-foundation}

Fullständig lista över ändringar i [AEM Foundation](wcm-platform.md).

Plattformen för Adobe Experience Manager 6.4 bygger på uppdaterade versioner av det OSGi-baserade ramverket (Apache Sling och Apache Felix) och Java Content Repository: Apache Jackrabbit Oak 1.8.2.

Quickstart använder Eclipse Jetty 9.3.22 som servermotor.

#### Användargränssnitt {#user-interface}

Ett antal förbättringar har gjorts i användargränssnittet för att göra det mer produktivt och enklare att använda.

* [Ny innehållsträd](/help/sites-authoring/basic-handling.md#content-tree) för att snabbt navigera i en hierarki. I kombination med listvyn återställs interaktionsmodellen för klassiskt användargränssnitt.
* Förbättrad bläddringsupplevelse på kort- och listvyn för stora mappar.
* [Förbättrad interaktion med sökresultaten](/help/sites-authoring/search.md) - knappen Bakåt återställer det tidigare sökresultatet.
* [Ytterligare kortkommandon](/help/sites-authoring/keyboard-shortcuts.md)för de flesta vanliga åtgärder, till exempel att öppna en viss räl, redigera, flytta och ta bort objekt eller öppna egenskaper.
* [Möjlighet att inaktivera kortkommandon](/help/sites-authoring/user-properties.md) (aktivera/inaktivera i Inställningar).
* [Sluta visa tidsstämplar i alla användargränssnittets](/help/sites-authoring/user-properties.md) relativa efter 7 dagar (ange som standard i Inställningar).

Mer information om dessa funktioner finns i [redigeringsdokumentationen](/help/sites-authoring/home.md) .

>[!CAUTION]
>
>Adobe planerar inte att göra fler förbättringar av det klassiska användargränssnittet. AEM 6.4 har det klassiska användargränssnittet och kunder som uppgraderar från tidigare versioner kan fortsätta använda det som det är. Observera att Classic-användargränssnittet fortfarande stöds fullt ut när det är inaktuellt. [Läs mer](/help/sites-deploying/ui-recommendations.md).

#### Innehållsdatabas {#content-repository}

* Snabbare och effektivare komprimering med onlineredigering. Interna tester visar att den nya svansen är upp till 10 gånger snabbare och kan frigöra mer diskutrymme med mindre IOPS jämfört med AEM 6.3. Detta resulterar i mindre prestandapåverkan när onlinerevideringsrensningen körs. Mer information finns [på dokumentationssidan](/help/sites-deploying/revision-cleanup.md#full-and-tail-compaction-modes).

* Continuous Revision Cleanup for MongoMK ersätter planerat rensningsunderhåll
* Förbättrad effektivitet vid rensning av revisioner i dokumentnoder

#### Sökning och indexering {#search-indexing}

* Förbättrat stöd för indexering via ekkörning (CLI):

   * Konsekvenskontroll för index
   * Indexeringsstatistik
   * Indexkonfiguration - IME/Export
   * Omindexering

* Minskad Lucene-relaterad databastillväxt för bättre systemprestanda

Mer information finns på [den här dokumentationssidan](/help/sites-deploying/indexing-via-the-oak-run-jar.md).

#### Övervakning {#monitoring}

* En ny [systemöversikt](/help/sites-administering/operations-dashboard.md#system-overview) ger en ögonblicksbild av all prestandarelaterad systemstatus och alla prestandarelaterade aktiviteter
* En ny uppsättning [hälsokontroller](/help/sites-administering/operations-dashboard.md#health-checks) för indexering, frågor och underhåll

#### Projekt och arbetsflöden {#projects-and-workflows}

* Helt nya [arbetsflödesredigeraren för att skapa och redigera arbetsflödesmodeller](/help/sites-developing/workflows-models.md).

![screen_shot_2018-04-04at71143am](assets/screen_shot_2018-04-04at71143am.png)

#### Uppgradera från tidigare version {#upgrade-from-earlier-version}

* [Bakåtkompatibilitet](/help/sites-deploying/backward-compatibility.md): Bakåtkompatibla funktioner i 6.4 hjälper din anpassade kod att förbli kompatibel i de flesta fall och minskar uppgraderingsbehovet.
* [Utvärdering](/help/sites-deploying/pattern-detector.md)av komplexitet för uppgradering: Det nya mönsteravkännarverktyget kontrollerar komplexiteten hos dina uppgraderingar innan du uppgraderar.
* [Omstrukturering](/help/sites-deploying/repository-restructuring.md)av lager: betydande omstrukturering (främst /etc) för att underlätta enklare uppgraderingar och främja bästa praxis för genomförandet
* Mer allmän information om uppgraderingar finns på [den här sidan](/help/sites-deploying/upgrade.md) .

### Experience Manager Sites {#experience-manager-sites}

Fullständig lista över ändringar i [AEM Sites och tillägg](sites.md).

#### Flytande upplevelser {#fluid-experiences}

Införandet av flytande upplevelser i början av 2017, med stöd av innehållsfragment, upplevelsefragment och innehållstjänster som bas, var början till en innehållshantering som tar flera kanaler i första rummet. AEM 6.4 utökar var och en av områdena avsevärt:

**[Innehållsfragment](/help/assets/content-fragments.md)**

Nyheter i 6.4 är en redigerare för visuell [innehållsmodell](/help/assets/content-fragments-models.md) och en ny [konfigurerbar komponent](https://helpx.adobe.com/experience-manager/core-components/using/content-fragment-component.html) för flexibel HTML-utskrift och JSON som ska ingå i Content Services.

**Experience Fragments**

Tack vare funktionen Byggblock kan du nu skapa variationer i ett fragment med samma innehåll men med olika layout mer effektivt. Förutom att skicka Experience Fragments till Facebook och Pinterest är det nu möjligt att skicka dem till Adobe Target som ett erbjudande.

**Innehållstjänster**

Olika förbättringar av Sling Model Exporter och Core Components ingår för att tillhandahålla stabila JSON-utdata för att bädda in innehåll i mobilappar och upplevelser som byggs med single page-appar.

#### Snabbare hämtning av webbplatser {#gettings-sites-built-quicker}

AEM 6.4 slutför omvandlingen till nästa generations komponentmodell. Core Components-konceptet som introducerades i AEM 6.3, och nu förenas med Style System, är ett effektivt sätt att bygga nya och utöka befintliga webbplatser.

Rekommenderad självstudiekurs för att lära dig hur du bäst utnyttjar den nya komponentmodellen: [Komma igång med AEM Sites - WKND självstudiekurs](https://helpx.adobe.com/experience-manager/kt/sites/using/getting-started-wknd-tutorial-develop.html)

#### Tillägget Skärmar {#screens-add-on}

Att leverera ett enhetligt budskap i alla marknadsföringskanaler, inklusive digitala signaturer och kiosknätverk, är vad AEM Screens står för. AEM 6.4 har stöd för att köra signeringsspelaren på maskinvaran för Microsoft Windows och Google Chrome OS. Dessutom finns det förbättringar av enhetshantering och scheman (grupper av kanaler) på fjärrbasis.

Mer information om skärmuppdateringar finns i [AEM Screens användarhandbok](https://docs.adobe.com/content/help/en/experience-manager-screens/user-guide/aem-screens-introduction.html).

### Experience Manager Communities {#experience-manager-communities}

AEM 6.4 har många nya funktioner och förbättringar i Communities. En fullständig lista över ändringarna finns i [AEM Communities](communities-release-notes.md). Högdagrar för den här versionen är:

#### Förbättringar av moderering {#enhancements-to-moderation}

**Automatisk identifiering av skräppost**

Ny motor för skräppostavkänning har tillhandahållits för att filtrera bort oönskat användargenererat innehåll på communitywebbplatser och grupper. När den har aktiverats från system/console/configMgr markeras ett användargenererat innehåll som skräppost baserat på en fördefinierad uppsättning skräppostord. Mer information om motorn för skräppostavkänning finns i [Automating Community User Generating Content](/help/communities/moderate-ugc.md#spam-detection).

![skräppidentifiering](assets/spamdetection.png)

**Nya filter för QnA**

Nya filter, som heter Answered och Not Answered, har lagts till i masmodereringskonsolen för att filtrera QnA-frågor. Om du vill veta hur statusfiltren Svarat och Obesvarat fungerar läser du [moderera användargenererat innehåll](/help/communities/moderation.md#main-pars-note-521961797)gruppvis.

**Kontrollfilter för bokmärken**

Det finns möjlighet att bokmärka de fördefinierade modereringsfiltren på modereringskonsolen. Dessa filter läggs till i slutet av URL-strängen och kan därför delas, återanvändas och granskas senare. Ta reda på hur du bokmärker filter i en [masmodereringskonsol](/help/communities/moderation.md#main-pars-note-429176623).

#### Ta bort användarprofiler och användarprofiler {#delete-ugc-and-user-profiles}

AEM 6.4 Communities visar [användningsklara API:er](/help/communities/user-ugc-management-service.md) och [exempelservrar](https://github.com/Adobe-Marketing-Cloud/aem-communities-ugc-migration/tree/master/bundles/communities-ugc-management-servlet) så att slutanvändarna får kontroll över sina data. Dessa API:er gör det även möjligt för databehandlings- och datakontrollorganisationer att hantera EU:s GDPR-kompatibilitetsbegäran.

#### Förbättringar av plats- och grupphantering {#enhancements-to-site-and-group-management}

**Skapa grupper med flera språkområden i ett enda steg**

Möjlighet att skapa flerspråkiga grupper med en enda åtgärd har tillhandahållits. Om du vill skapa sådana grupper kan användarna navigera till gruppsamlingen för den önskade communitywebbplatsen från webbplatskonsolen. Skapa en grupp och ange önskade språk på mallsidan för communitygrupper. Mer information om den här funktionen finns i [communitygruppskonsolen](/help/communities/groups.md).

![flerspråkig grupp](assets/multilingualgroup.png)

**[Ta bort communitysajter och grupper med ett klick](/help/communities/groups.md)**

Ikonen Ta bort är nu tillgänglig på respektive webbplats och i respektive grupp, vid navigering från global navigering. Med den här ikonen tas alla objekt och allt innehåll som är kopplat till platsen eller gruppen bort, och alla användarassociationer tas bort. Mer information om den här funktionen finns i [Hantera communitysajter](/help/communities/create-site.md#main-pars-text-fe17) och [Hantera communitygrupper](/help/communities/groups.md#main-pars-text-5e8c).

#### Förbättringar av aktivering {#enhancements-to-enablement}

Tilldelnings- och katalogfunktionerna är nu tillgängliga i grupper. Detta gör att utbildningsinnehåll kan skapas, hanteras och publiceras för en viss uppsättning målgruppsmedlemmar. Mer information om att aktivera communitygrupper finns i [Hantera aktiveringsresurser](/help/communities/resource.md).

![tilldelningskatalog](assets/assignmentcatalog.png)

### Experience Manager Assets {#experience-manager-assets}

AEM 6.4 har flera nya funktioner och förbättringar av Assets, bland annat ny, förbättrad Creative Cloud-integrering, viktiga innovationer inom artificiell intelligens, förbättrad metadatahantering, förbättrade rapporter och förbättringar av användarupplevelsen. Den fullständiga listan över tillgängliga ändringar i [AEM Assets](assets.md). Versionens högdagrar är:

**Adobe Asset Link**

Adobe Asset Link i Creative Cloud for enterprise effektiviserar samarbetet mellan kreatörer och marknadsförare vid skapandet av innehåll. Det är en ny inbyggd funktion i Creative Cloud for enterprise som kopplar ihop Photoshop CC, Illustrator CC och InDesign CC till AEM - utan att kreatörerna behöver lämna sina valverktyg.

Mer information om denna funktion, de krav som ställs och hur du får tillgång till den finns i [Adobe Asset Link](https://www.adobe.com/creativecloud/business/enterprise/adobe-asset-link.html).

![adobe_asset_link](assets/adobe_asset_link.png)

**AEM-skrivbordsapp**

AEM-datorprogrammet har uppdaterats till version 1.8, som är kompatibel med AEM 6.4. En fullständig lista över ändringar för AEM-datorprogrammet finns i ett dedikerat dokument med versionsinformation [för](https://helpx.adobe.com/experience-manager/desktop-app/release-notes.html) AEM-skrivbordsappen.

De förbättringar som har gjorts sedan AEM 6.3-versionen omfattar möjligheten att överföra hierarkiska mappar i bakgrunden, ett nytt användargränssnitt för att övervaka bakgrundsåtgärder för resurser, förbättrad cachelagring, nätverk och inloggning samt övergripande stabilitetsförbättringar. Dokumentationen innehåller även en guide till [bästa praxis](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html).

**Adobe Sensei Services**

De nya funktionerna är bland annat Förbättrade smarta taggar, med möjlighet att lära sig kundens taxonomi, att automatiskt tagga digitala resurser med kundspecifika taggar och Smart Translation Search, som förbättrar upptäckbarheten på flera språk genom att översätta söktermer direkt. Mer information om den här funktionen finns i [Förbättrade smarta taggar](/help/assets/enhanced-smart-tags.md).

![enhanced_smart_tags2](assets/enhanced_smart_tags2.png)

**Metadata**

Ett antal förbättringar är möjligheten att importera och exportera metadata samtidigt för ett stort antal resurser och avancerade metadatakonstruktioner, till exempel [Cascading Metadata](/help/assets/cascading-metadata.md).

**Rapporter**

Resursrapporteringen genomgick en stor översyn i AEM 6.4 med nya rapporteringsramverk, användarupplevelser och fler OTB-rapporter för kundanvändning. Mer information om hur du skapar olika rapporter finns i [Resursrapporter](/help/assets/asset-reports.md).

**Användarupplevelse**

Flera förbättringar som förbättrar surfning, sökning och administration för Assets-användare som bläddring, bakåtsökning, förbättrade sökfilter och mycket annat. Den fullständiga listan i [AEM Assets](assets.md).

**Varumärkesportal**

Olika förbättringar inom områden som metadata, rapportering, digitala rättigheter, inloggningsupplevelser och publiceringsprestanda för mediedistribution. Mer information om de nya förbättringarna och funktionerna finns i [Nyheter i AEM Assets Brand Portal](https://helpx.adobe.com/experience-manager/brand-portal/using/whats-new.html).

#### Dynamic Media Add-on {#dynamic-media-add-on}

AEM 6.4 innehåller många nya funktioner och förbättringar av Dynamic Media. Den fullständiga listan finns i [AEM Assets](assets.md). Viktiga högdagrar är följande:

**Smart beskärning**

Smart Crop, som drivs av Adobe Sensei, ger automatiskt icke-förstörande beskärning av bilder och bevarar intressepunkten för responsiv design. Du kan förhandsgranska förslag på beskurna bilder och manuellt justera dem om det behövs. Den här funktionen möjliggör även automatisk generering av färgrutor för produktbilder.

Mer information om hur du använder smart beskärning finns i dokumentationen [Bildprofiler](/help/assets/image-profiles.md) .

Mer information om hur du arbetar med smart beskärning i Dynamic Media finns i [Lägga till Dynamic Media-resurser på sidor](/help/assets/adding-dynamic-media-assets-to-pages.md) .

**Smart bildbehandling**

Smart bildbehandling utnyttjar varje användares unika visningsegenskaper för att automatiskt leverera bilder som är optimerade för sin upplevelse, vilket ger bättre prestanda och engagemang.

Mer information finns i dokumentationen för [Smart](/help/assets/imaging-faq.md) Imaging.

![smart_crop](assets/smart_crop.png)

**Förbättringar av nya media och visningsprogram**

Med nya visningsprogram, bland annat panoraman och VR, kan du skapa mer engagerande upplevelser.

Mer information finns i dokumentationen för [panoramabilder](/help/assets/panoramic-images.md) .

**3D-resurser**

Ny integrering med [Adobe Dimension CC](https://www.adobe.com/products/dimension.html), ett Creative Cloud-program för att skapa 3D-upplevelser.

Mer information finns i [Arbeta med 3D-resurser](/help/assets/assets-3d.md) .

![do-not-localize/3d](assets/do-not-localize/3d.png)

### Experience Manager Forms {#experience-manager-forms}

AEM 6.4 Forms innehåller flera nya funktioner och förbättringar. Högdagrarna är följande:

* Interaktiv kommunikation i flera kanaler
* Förifyll interaktiv kommunikation från affärsapplikationer
* Modernisering av arbetsflödet och stöd för mobila arbetare
* Lazy loading av fragment
* Uppgradering från LiveCycle till Experience Manager Forms 6.4

Mer information om [AEM Forms](forms.md) versionsinformation. Se även [Sammanfattning av nya funktioner och förbättringar i AEM 6.4-formulär](/help/forms/using/whats-new.md) för information om nya och förbättrade funktioner och dokumentationsresurser.

### Experience Manager Livefyre {#experience-manager-livefyre}

Du kan integrera Livefyre med din AEM 6.4-instans. Information om hur du integrerar Livefyre med AEM finns här:

* [Integrera Livefyre](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html)

### Utnyttja kundfokuserad utveckling {#leverage-customer-focused-development}

Adobe använder en kundfokuserad utvecklingsmodell som gör det möjligt för kunderna att bidra till alla faser i utvecklingsprocessen, under specifikation, utveckling och testning. Vi tackar alla kunder och partners som deltar i den här processen.

Adobe har de rutiner och processer som krävs för att möjliggöra insamling, prioritering och spårning av kundfokuserad fellösning och utveckling av förbättringsförfrågningar. Supportportalen [för](https://helpx.adobe.com/marketing-cloud/contact-support.html) Adobe Marketing Cloud är integrerad med Adobe Enhancement &amp; Defect Tracking System. Kundfrågor identifieras och löses med kundtjänst där det är möjligt. När den eskaleras till FoU hämtas all kundinformation in och används för prioritering och rapportering. Vid utveckling ges prioritet åt betald support och garantifrågor samt betalda kundförbättringar.

Denna prioriteringsprocess har resulterat i över 500 kundfokuserade förändringar som korrigerats i AEM 6.4.

## Lista över filer som ingår i releasen {#list-of-files-that-are-part-of-the-release}

**Foundation**

* Fristående QuickStart: cq-quickstart-6.4.0.jar
* Snabbstart för programserver: cq-quickstart-6.4.0.war
* Dispatcher 4.3.1 eller senare för olika webbservrar och plattformar ([nedladdningslänk](https://helpx.adobe.com/experience-manager/dispatcher/release-notes.html))
* Plugin för Eclipse IDE ([läs mer och ladda ned](/help/sites-developing/aem-eclipse.md))

* Tillägg för Brackets Code Editor ([läs mer och ladda ned](/help/sites-developing/aem-brackets.md))
* Maven/Gradle-beroenden ([nedladdningslänk](https://repo.adobe.com/nexus/content/repositories/releases/com/adobe/aem/uber-jar/6.1.0/))

**Sites**

* Kärnkomponenter ([GitHub-projekt](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components))
* Implementering av referens för butik ([läs mer](/help/sites-developing/we-retail.md))
* Project Blueprint Archetype ([GitHub-projekt](https://github.com/Adobe-Marketing-Cloud/aem-project-archetype))
* AEM Screens Players for various target platforms ([download](https://download.macromedia.com/screens/))
* Språkmodeller för smart innehåll. Engelska är förinstallerat - fler språk kan hämtas

   * [Tyska](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/smartcontent-model-de)
   * [Spanska](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/smartcontent-model-es)
   * [Italienska](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/smartcontent-model-it)
   * [Franska](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/smartcontent-model-fr)

* [Dialogrutekonverteringsverktyg](/help/sites-developing/dialog-conversion.md) för att migrera klassiska användargränssnittskomponenter till Coral 3

**Assets**

* Adobe Experience Manager datorprogram ([läs mer](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html) och [ladda ned](https://helpx.adobe.com/experience-manager/kb/download-companion-app.html))

* Paket för att lägga till förbättrad PDF-rastrerare ([läs mer](/help/assets/aem-pdf-rasterizer.md) och [ladda ned](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/assets/aem-assets-pdf-rasterizer-pkg))

* Paket för att lägga till stöd för utökad RAW-bild ([läs mer](/help/assets/camera-raw.md))

**Formulär**

* Paket för AEM Forms:

   * [adobe-aemfd-aix-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-AIX)
   * [adobe-aemfd-linux-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-LX)
   * [adobe-aemfd-solaris-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-SOL)
   * [adobe-aemfd-win-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-WIN)
   * [adobe-aemfd-osx-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/fd/AEM-FORMS-6.4-OSX)

## Språk {#languages}

Användargränssnittet finns på följande språk:

* Engelska
* Tyska
* Franska
* Spanska
* Italienska
* Brasiliansk portugisiska
* Japanska
* Förenklad kinesiska
* Traditionell kinesiska (begränsat stöd)
* Koreanska

Experience Manager 6.4 har certifierats för GB18030-2005 CITS att använda den kinesiska kodningsstandarden.

## Installera och uppdatera {#install-update}

Se [installationsanvisningarna](/help/sites-deploying/custom-standalone-install.md) för installationskrav.

Mer information finns i [uppgraderingsdokumentationen](/help/sites-deploying/upgrade.md) .

## Plattformar som stöds {#supported-platforms}

Den fullständiga matrisen med plattformar som stöds finns här. Supportnivå för [AEM 6.4 - tekniska krav](/help/sites-deploying/technical-requirements.md)

>[!NOTE]
>
>Oracle har flyttat till en LTS-modell (Long Term Support) för Oracle Java SE-produkter. Java 9 och 10 är icke-LTS-versioner från Oracle (se [Oracle Java SE support roadmap](https://www.oracle.com/technetwork/java/eol-135779.html)). Adobe ger endast stöd för LTS-versioner av Java för att köra AEM i produktionen. Därför rekommenderas Java 8 för AEM 6.4.

## Föråldrade och borttagna funktioner {#deprecated-and-removed-features}

Adobe utvärderar ständigt funktionerna i produkten och planerar att ersätta funktioner med kraftfullare versioner, eller bestämmer sig för att omimplementera utvalda delar så att de blir bättre förberedda för framtida förväntningar eller tillägg.

I Adobe Experience Manager 6.4 [finns en lista över borttagna funktioner](deprecated-removed-features.md)som tagits bort. Sidan innehåller även förhandsmeddelanden om ändringar under 2019 och viktiga meddelanden för kunder som uppdaterar från tidigare versioner.

## Detaljerade ändringslistor {#detailed-changes-lists}

[AEM Sites](sites.md)

[AEM Assets](assets.md)

[AEM Communities](communities-release-notes.md)

[AEM Forms](forms.md)

[AEM Foundation](wcm-platform.md)

## Kända fel {#known-issues}

[Lista över kända fel](known-issues.md)

### Nedladdning och support av produkter (begränsade platser) {#product-download-and-support-restricted-sites}

Dessa webbplatser är bara tillgängliga för kunder. Om du är kund och behöver åtkomst kontaktar du din kontoansvarige på Adobe.

* [](https://daycare.day.com) [Produktnedladdning på licensing.adobe.com](https://licensing.adobe.com/)

* [Kundsupport på day.day.com](https://daycare.day.com)

