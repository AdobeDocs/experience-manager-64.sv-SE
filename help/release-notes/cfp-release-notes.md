---
title: AEM 6.4 Cumulative Fix Pack Release Notes
description: Versionsinformation om Adobe Experience Manager 6.4 Cumulative Fix Packs.
contentOwner: AK
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: 3a8fefc8a580d41d327cf7acbf8e4b0440fea604
workflow-type: tm+mt
source-wordcount: '4347'
ht-degree: 0%

---


# AEM 6.4 Cumulative Fix Pack Release Notes {#aem-cumulative-fix-pack-release-notes}

## Versionsinformation {#release-information}

<!-- TBD: Update the SD URL. -->

| Produkter | **Adobe Experience Manager (AEM) 6.4** |
|---|---|
| Version | 6.4.8.4 |
| Typ | Kumulativt korrigeringspaket |
| Date | 25 februari 2021 |
| Förutsättning | [AEM 6.4 Service Pack 8 (6.4.8.0)](sp-release-notes.md) |
| Hämta URL | [Programvarudistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-4.0.zip) |

## Vad ingår i AEM 6.4.8.4 {#what-s-included-in-aem}

AEM Cumulative Fix Pack 6.4.8.4 är en viktig uppdatering som innehåller flera interna korrigeringar och kundkorrigeringar sedan den allmänna tillgängligheten av 6.4 Service Pack 8 (6.4.8.0) i mars 2020.

AEM 6.4.8.4 är ett Cumulative Fix Pack (CFP) som är beroende av AEM 6.4 Service Pack 8. Installera CFP när du har installerat AEM 6.4 Service Pack 8.

I AEM 6.4.8.4 uppdateras den inbyggda databasen (Apache Jackrabbit Oak) till version 1.8.24.

Information om CFP och andra typer av releaser finns i [AEM Update Release Vehicle Definitions](https://experienceleague.adobe.com/docs/experience-manager-release-information/aem-release-updates/update-release-vehicle-definitions.html?lang=en)

Adobe Experience Manager 6.4.8.4 innehåller korrigeringar för följande problem.

### Sites {#sites-6484}

* Efter installation av Experience Manager Service Pack 6.4.8.2 kan användare inte redigera modeller för innehållsfragment och uppleva följande fel:

   `Uncaught TypeError: Cannot read property 'debounce' of undefined` (NPR-35312)
* När en användare klickar på utloggningsknappen loggas användaren inte ut från Package Manager. (NPR-35161)
* Efter uppgradering från Experience Manager 6.4.x till Experience Manager 6.4.8.3 kan man inte publicera en sida via Hantera publikationer. (CQ-4312511)
* När du flyttar tillbaka en underordnad ritningssida till den ursprungliga platsen tas inte konfigurationen cq:liveSyncConfig bort från en underordnad live-kopiesida. (NPR-35900)
* När du flyttar en ritning som innehåller live-kopior fram och tillbaka fungerar bara den första flyttningen, den misslyckas och inget felmeddelande visas. (NPR-35899)


### [!DNL Assets] {#assets-6484}

* `IndexWriter.merge` orsakar  `OutOfMemoryError` fel eftersom funktionen för smart taggning skapar stora  `/oak:index/lucene` värden och  `/oak:index/ntBaseLucene` index (NPR-35650).
* Användare kan inte checka in resurser efter att ha redigerat dem i [!DNL Adobe InDesign] och få felmeddelanden om bristande behörigheter (NPR-35340).
* När en ny version av en befintlig resurs skapas efter att namnkonflikten har lösts, skrivs metadata för den ursprungliga resursen över (NPR-35939).
* Automatiskt genererade grupper för privata mappar bevaras inte och tas inte bort när du tar bort mappen eller uppdaterar mappen med alternativet [!UICONTROL Remove Private Folder Restrictions] inställt (NPR-35625).

#### [!DNL Dynamic Media] {#dynamic-media}

* Intermittent ImageServer-fel orsakar 403-svar och efterföljande fel i några funktioner i [!DNL Experience Manager]. (CQ-4308565)

### Integreringar {#integrations-6484}

* När du öppnar egenskaperna för en sida efter att ha uppgraderat till Experience Manager 6.4.8.3, visas JavaScript-fel i konsolen (NPR-35649).

### Forms {#forms-6484}

>[!NOTE]
>
>[!DNL Experience Manager Forms] släpper tilläggspaketen en vecka efter det schemalagda  [!DNL Experience Manager] Cumulative Fix Pack-frisläppningsdatumet.

Mer information om säkerhetsuppdateringar finns på [Experience Manager-säkerhetsbulletinsidan](https://helpx.adobe.com/security/products/experience-manager.html).

## Programfixar och funktionspaket som ingår i tidigare Cumulative Fix-paket {#hotfixes-and-feature-packs-included-in-previous-cumulative-fix-packs}

### Adobe Experience Manager 6.4.8.3 {#experience-manager-6483}

AEM Cumulative Fix Pack 6.4.8.3 är en viktig uppdatering som innehåller flera interna korrigeringar och kundkorrigeringar sedan den allmänna tillgängligheten av 6.4 Service Pack 8 (6.4.8.0) i mars 2020.

AEM 6.4.8.3 är ett Cumulative Fix Pack (CFP) som är beroende av AEM 6.4 Service Pack 8. Installera CFP när du har installerat AEM 6.4 Service Pack 8.

I AEM 6.4.8.3 uppdateras den inbyggda databasen (Apache Jackrabbit Oak) till version 1.8.23.

Information om CFP och andra typer av releaser finns i [AEM Update Release Vehicle Definitions](https://docs.adobe.com/content/help/en/experience-manager-65/deploying/deploying/update-release-vehicle-definitions.html)

Adobe Experience Manager 6.4.8.3 innehåller korrigeringar för följande problem.

#### Platser {#sites-6483}

* När du uppdaterar texten för en variant av ett innehållsfragment uppdateras innehållet i det överordnad innehållsfragmentet i stället för variationen (NPR-35080).

* När du anger ett numeriskt värde för egenskapen String type label för en komponent, tar bort komponenten och använder alternativet undo för att få tillbaka den, ändras egenskapen type för label automatiskt från String till Long (NPR-34738).

* När du lägger till en File Upload-komponent i flera fält lagras bildsökvägen i komponentnoden i stället för i Multi-Field-noden (NPR-34423).

* I guiden Flytta sida är nästa knapp aktiverad även om inget mål är markerat (NPR-34460).

* När den överordnade komponenten innehåller egenskapen `cq:isContainer` inkluderas inte egenskapen automatiskt i den ärvda komponenten (CQ-4308409).

* När du använder CSS-minification med funktionen `calc()` tas blankstegen runt `+`-tecknet bort (NPR-34991).

* När du startar en AEM visas inte komponenterna `com.adobe.granite.maintenance.impl.MaintenanceTaskManagerImpl` och `com.adobe.granite.maintenance.impl.TaskScheduler` i läget `Active` (NPR-34952).

#### [!DNL Assets] {#assets-6483}

* När du skapar en version av en befintlig resurs kommer användaren inte att uppdatera metadata om en metadataprofil används för mappen (NPR-34833).
* När du använder [!DNL Adobe Asset Link] med [!DNL Adobe InDesign] innehåller sökresultaten inte mappar och samlingar, utan bara resurser (NPR-34700).
* När du drar en resurs till en mapp för att flytta den visas även alternativet [!UICONTROL Drop in Lightbox] och [!UICONTROL Drop in Collection] i användargränssnittet. Även om flyttåtgärden avbryts fortsätter användargränssnittet att visa de senare två alternativen (NPR-34525).
* När gränssnittet Hantera publikation är öppet är alternativet Publicera inte tillgängligt och när du väljer alternativet för att avpublicera är scopesidan tom (CQ-4302509).

##### [!DNL Dynamic Media] {#dynamic-media-6483}

* När alternativet [!UICONTROL Enable JPG Chrominance Downsampling] är avmarkerat i [!DNL Experience Manager] i inställningarna för Bildförinställning synkroniseras inte ändringen med [!DNL Dynamic Media] (NPR-34284).
* I [!UICONTROL Viewer Presets Editor] är modifieringsetiketten `PANORAMICVIEW_AUTOROTATE` inte tillgänglig när du redigerar [!UICONTROL PanoramicImage/PanoramicImage_VR]-förinställningen i `PanoramicView`-komponenten (CQ-4302043).
* Om du avpublicerar en video från [!DNL Experience Manager] avpubliceras inte den adaptiva videouppsättningen på den konfigurerade Dynamic Media Classic. (CQ-4304405).

#### Plattform {#platform-6483}

* Flaggan `emitUseStrict` läggs till i GCC-processorfunktionen (Google Closure Compiler) `com.adobe.granite.ui.clientlibs.impl.HtmlLibraryManagerImpl`. Flaggan undertrycker utdata från `use strict`-instruktionen (NPR-34830).
* Ett `NullPointerException` returneras vid start av dagliga eller veckovisa underhållsuppgifter (NPR-34702).
* Verktyget [!DNL Apache Sling Health Check] är föråldrat. Använd i stället [Mönsteravkännare](https://experienceleague.adobe.com/docs/experience-manager-64/deploying/upgrading/pattern-detector.html) för att identifiera innehållsfel (NPR-33929).

#### Integreringar {#integrations-6483}

* Knappen [!UICONTROL Create] visas på sidan [!UICONTROL Audiences] när du navigerar från en mapp till sidan [!UICONTROL Audiences] (NPR-35152).

#### Användargränssnitt {#ui-6483}

* Sökpanelen [!UICONTROL Filters] i användargränssnittet [!UICONTROL Omnisearch] returnerar även resultat från andra platser än de där sökningen körs (NPR-34877).
* När du stänger panelen [!UICONTROL Filters] i användargränssnittet [!UICONTROL Omnisearch] återställs inte den vänstra listen till [!UICONTROL Content]-markeringen, vilket förhindrar att panelen [!UICONTROL Filters] öppnas igen (NPR-34483).
* Ett `NullPointerException` returneras vid åtkomst av sidegenskaperna (NPR-34509).

#### Communities {#communities-6483}

<!-- Following fixes of 6483 are documented on Nov 11 20202 by Vishabh. 
-->

* Alla fall av orättvis terminologi i produkten ska ersättas med vedertagna motsvarigheter (NPR-34506).

#### Handel {#commerce-6483}

* När det finns fler än 15 produkter i en samling visas endast de första 15 produkterna (NPR-34494).

#### Forms {#forms-6483}

>[!NOTE]
>
>[!DNL Experience Manager Forms] släpper tilläggspaketen en vecka efter det schemalagda  [!DNL Experience Manager] Cumulative Fix Pack-frisläppningsdatumet.

>[!NOTE]
>
>[!DNL Experience Manager] Kumulativt korrigeringspaket innehåller inte korrigeringar för  [!DNL Experience Manager Forms]. De levereras med ett separat [!DNL Forms]-tilläggspaket. Dessutom släpps ett kumulativt installationsprogram som innehåller korrigeringar för [!DNL Experience Manager Forms] på JEE. Mer information finns i [Installera AEM Forms-tilläggspaket](#install-aem-forms-add-on-package) och [Installera AEM Forms JEE-installationsprogrammet](#install-aem-forms-jee-installer).

**Adaptiv Forms**

* Det går inte att redigera ett anpassat formulär med hjälp av det klassiska användargränssnittet när du har använt [!DNL Experience Manager] Cumulative Fix Pack (NPR-35127).

* Fragment tar längre tid att läsa in i anpassad form på grund av cacheogiltigförklaring (NPR-34655).

* Tillgänglighet: Tabbnavigering fungerar inte korrekt för skärmläsare i anpassad form (NPR-34550).

**Korrespondenshantering**

* När du migrerar resurserna från ES3 innehåller resurserna två icke-redigerbara standardvillkor (NPR-34971).

**Foundation JEE**

* Migrera [!DNL AEM Forms]-användare från Flash till HTML (CQ-4304075).

### Adobe Experience Manager 6.4.8.2 {#experience-manager-6482}

AEM Cumulative Fix Pack 6.4.8.2 är en viktig uppdatering som innehåller flera interna korrigeringar och kundkorrigeringar sedan den allmänna tillgängligheten av 6.4 Service Pack 8 (6.4.8.0) i mars 2020.

AEM 6.4.8.2 är ett Cumulative Fix Pack (CFP) som är beroende av AEM 6.4 Service Pack 8. Installera CFP när du har installerat AEM 6.4 Service Pack 8.

I AEM 6.4.8.2 uppdateras den inbyggda databasen (Apache Jackrabbit Oak) till version 1.8.22.

Information om CFP och andra typer av releaser finns i [AEM Update Release Vehicle Definitions](https://docs.adobe.com/content/help/en/experience-manager-65/deploying/deploying/update-release-vehicle-definitions.html)

Adobe Experience Manager 6.4.8.2 innehåller korrigeringar för följande problem.

#### Platser {#sites-6482}

* Om `RolloutConfigManagerFactoryImpl` inte kan läsa in en rollout-konfiguration försöker den inte läsa in de saknade konfigurationerna. Den returnerar de cachelagrade konfigurationerna (NPR-34091).
* I huvudkomponenten för text tas klassen från taggen `em` bort (NPR-34080) när du har använt HTML-källredigeringsalternativet.
* När du uppgraderar från Experience Manager 6.2 till Experience Manager 6.5 visas inte Parsys-komponenten för statiska mallar korrekt. Höjden på komponenten Parsys är inställd på 0 och komponenterna i den är inte synliga (NPR-34044).
* Etikettinformationen visas inte för de tillåtna komponenterna i mallredigeraren (NPR-33908).

   ![Etiketter saknas i layoutbehållaren](assets/33908_missing_labels.png)

* Användare kan inte lägga till eller redigera komponenter i parsytan efter den fjärde nivån med kapslade komponenter (NPR-33873).
* Om det ursprungliga innehållet i en redigerbar mall ändras och sedan mallen publiceras, visar alla nya sidor som skapas med den här mallen mallens publiceringsdatum även om sidorna inte publiceras (NPR-33822).
* Egenskaperna `cq:acLinks` och `cq:acUUID` för [!DNL Adobe Campaign] på kopian tas bort under kopiera- och klistra in-åtgärden (NPR-33793).
* På fliken [!UICONTROL Live Usage] visas bara 49 resultat. Den visar inte all användning för komponenten (NPR-33710).
* En webbsida med ett `/`-tecken i URL:en slutar att svara vid utvecklingen. När en komponent läggs till under utvecklingen ökar processoranvändningen och webbläsaren slutar svara (NPR-33625).
* I infogat redigeringsläge i [!DNL RTE] fungerar inte det att dra en bild för textkomponenten (NPR-33579).
* Det går att skapa en komponent på en ritningssida med samma namn som sidnamnet. Under utrullningen byter en sådan komponent namn med suffixet `_msm_moved`. Komponenten flyttas dock till slutet av [!UICONTROL Paragraph System] (NPR-33534).
* Starthöjningen publicerar inte sidor när egenskapen [!UICONTROL include subpages] inte är markerad i den första innehållsroten (NPR-33533).
* Omdirigering till [!DNL Experience Manager]-sida med ankarpunkt fungerar inte på Author-instansen eftersom `PageRedirectServlets` placerar frågesträngen efter ett URL-fragment eller ett ankare (NPR-34287).
* `PageRedirectServlet` läggs till  `.html` efter Sling-mappning som leder till länkfel (NPR-34271).
* Du kan göra uppehåll i [!DNL Live Copy] för en sida och arv bryts i enligt vad som visas i redigeringsläget. I sidegenskaperna indikerar ikonen som representerar arv felaktigt att arvet finns och inte är brutet (NPR-34096).
* Problem med visning av tillåtna komponenter på mallsidan Redigera (CQ-4297295).
* När du har uppgraderat Chrome och Firefox fungerar inte snabbmenyerna som förväntat. När du läser in sidegenskaperna visas inte panelen när det finns data i den (CQ-4292995).
* Flera instanser av korsskriptning mellan webbplatser i [!DNL Experience Manager Sites]-komponenter (NPR-33926).
* Användarindata är inte korrekt kodade för olika komponenter när information skickas till klienten (NPR-33696).
* En URL som slutar med `childrenlist.html` visar en HTML-sida i stället för ett 404-svar. Sådana URL:er är sårbara för serveröverskridande skriptning (NPR-33441).

#### Assets {#assets-6482}

* Textextrahering för de överförda PDF-filerna fungerar inte och fulltextsökning för vissa ord i en PDF-fil misslyckas med att hämta PDF-filen (NPR-34165).

   >[!NOTE]
   >Om du vill att den här korrigeringen ska fungera startar du om Adobe Experience Manager-instansen när du har installerat Service Pack 6.4.8.2.

* Omvända snedstreck läggs till före specialtecken i sökförslag för resurser, som har specialtecken i sitt namn (NPR-33833).

* De anpassade filtren som sparas som smarta samlingar används inte korrekt på resurser, och sökresultaten är därför inte korrekta   (NPR-33725).

* Tidslinjen för en resurs i en mapp som har ändrats visar att resursen har flyttats (NPR-33580).

* Om du avpublicerar resurser i grupp från [!DNL Brand Portal] uppstår ett `Request-URI Too Long`-fel (NPR-34158).

* I kolumnvyn: om användaren väljer alternativet [!UICONTROL Filter] efter att ha valt en uppsättning resurser (resurserna inaktiveras) och sedan väljer en annan uppsättning resurser att flytta, flyttas även de tidigare markerade resurserna till den nya platsen (NPR-34018).

* Rullningslisten visas inte i listvyn, även om det finns många resurser att passa in på sidan (NPR-34156).

* Sidan [!UICONTROL Manage Publication] för resurser är bruten och alternativen däri fungerar inte (CQ-4302509).

**Dynamic Media**

* Funktionen för smart beskärning misslyckas med fel när en bildprofil läggs till i en mapp med flera (till exempel 11) proportioner (NPR-34083).

* Ändringar av bildförinställningar i [!UICONTROL Adobe Experience Manager] synkroniseras inte med Dynamic Media Classic (NPR-34284, CQ-4299713).

* Modifieretiketten [!UICONTROL PANORAMICVIEW_AUTOROTATE] saknas på fliken [!UICONTROL Behavior] på sidan [!UICONTROL Viewer Preset Editor] (CQ-4302043).

#### Plattform {#platform-6482}

* Standardvärdena för inställningarna **[!UICONTROL Connect Timeout]** och **[!UICONTROL Socket Timeout]** för standardagentkonfigurationen (publicering) har inte angetts (NPR-33708).
* Schemaläggaren för underhållsaktiviteter startar och stoppar underhållsaktiviteter för ofta än vad som har konfigurerats (NPR-33520).
* Det går inte att hämta loggar med diagnosverktyget på en uppgraderad Experience Manager-instans (NPR-34419).

#### Integreringar {#integrations-6482}

* Värdet `library_path` beaktas inte när du genererar [!DNL Adobe Launch] biblioteks-URL för bibliotek som migrerats från [!DNL Adobe Dynamic Tag Management]. Dessutom använder de migrerade biblioteken ett annat prefix än [!DNL Adobe Launch]-biblioteken. (NPR-34238).
* Egenskaperna som ärvs från en molntjänst bevaras inte när sidegenskaperna uppdateras (NPR-33865).

#### Användargränssnitt {#ui-6482}

* Antalet markerade resurser på en söksida visas felaktigt (NPR-33540).

#### Communities {#communities-6482}

* Befintliga användare i en community-grupp som lagts till via Admin Console tas bort från användarlistan vid ändringar i community-gruppkonsolen (NPR-34312).

#### Forms {#forms-6482}

>[!NOTE]
>
>[!DNL Experience Manager] Kumulativt korrigeringspaket innehåller inte korrigeringar för  [!DNL Experience Manager Forms]. De levereras med ett separat [!DNL Forms]-tilläggspaket. Dessutom släpps ett kumulativt installationsprogram som innehåller korrigeringar för [!DNL Experience Manager Forms] på JEE. Mer information finns i [Installera AEM Forms-tilläggspaket](#install-aem-forms-add-on-package) och [Installera AEM Forms JEE-installationsprogrammet](#install-aem-forms-jee-installer).

**Adaptiv Forms**

* Om det saknas ett adaptivt formulärfragment återges inte det adaptiva formuläret (NPR-34303).

* Hjälpinnehållsbeskrivningen för adaptiva formulärfält visar en HTML-stycketagg (NPR-34117).

* När du lägger till en Forms-behållare på en [!DNL Experience Manager Sites]-sida visas följande felmeddelande på sidan och du kan inte lägga till nya komponenter (NPR-33858):

   `DevTools failed to load SourceMap: Could not load content for <Link>. HTTP error: status code 404, net::ERR_HTTP_RESPONSE_CODE_FAILURE`

* När du väljer egenskapen **[!UICONTROL Revalidate on Server]** och överför flera bilagor, skickas inte det adaptiva formuläret (NPR-33701).

* När du väljer alternativen **[!UICONTROL Use Page Language]** och **[!UICONTROL Form covers entire width of the Page]** i [!DNL Experience Manager Forms]-komponenten på en [!DNL Experience Manager Sites]-sida kan sidan inte översättas (NPR-33641).

* När du skickar ett analysaktiverat adaptivt formulär inbäddat på en [!DNL Experience Manager Sites]-sida fungerar inte analysen korrekt (NPR-31359).

* Tog bort beroenden för [!DNL Lodash]- och [!DNL backbone]-bibliotek (NPR-33458).

* Överföringsåtgärden **[!UICONTROL Submit to REST endpoint]** fungerar inte för en adaptiv form (NPR-34513).

* Tillgänglighet: När du försöker skicka ett anpassat formulär utan att överföra en bilaga för ett obligatoriskt fält flyttas fokus inte automatiskt till bilagefältet (NPR-34511).

* Användarindata är inte korrekt kodade för [!DNL Forms]-komponenter när information skickas till klienten (NPR-33611).

**Arbetsflöde**

* [!DNL Experience Manager] Åtgärd för tömning av arbetsflöde misslyckas och följande felmeddelande visas (NPR-33576):

   `java.lang.UnsupportedOperationException: The query read more than 500000 nodes in memory`

* När du installerar [!DNL Experience Manager] 6.4.8.1 visas inte objektlistan [!UICONTROL To Do] som länkar. Texten för [!UICONTROL To Do]-objekten innehåller HTML-taggar (NPR-34318).

**BackendIntegration**

* Det går inte att konfigurera en formulärdatamodell i en AWS-miljö som är värd [!DNL Experience Manager Forms Linux] (NPR-33617).

**Designer**

* När [!DNL Acrobat DC] är installerat på en [!DNL Experience Manager] Forms-server är alternativet **[!UICONTROL Distribute Form]** inte tillgängligt i [!DNL Experience Manager Designer] version 6.x (NPR-34325).

**Dokumentsäkerhet**

* Det går inte att utföra signeringsåtgärden med HSM-baserade certifikat i en PDF-fil efter installation av [!DNL Experience Manager] 6.4.8.0 (NPR-34309).

**Uppgradera**

* När du uppgraderar versionen [!DNL JBoss] till 7.0.9 för [!DNL Experience Manager Forms] med Document Security i en [!DNL Linux]-miljö resulterar det i ett fel (CQ-4300546).

Mer information om säkerhetsuppdateringar finns på [Experience Manager-säkerhetsbulletinsidan](https://helpx.adobe.com/security/products/experience-manager.html).

### Adobe Experience Manager 6.4.8.1 {#experience-manager-6481}

AEM Cumulative Fix Pack 6.4.8.1 är en viktig uppdatering som innehåller flera interna korrigeringar och kundkorrigeringar sedan den allmänna tillgängligheten av 6.4 Service Pack 8 (6.4.8.0) i mars 2020.

AEM Kumulativt korrigeringspaket 6.4.8.1 är beroende av AEM 6.4 Service Pack 8. Du måste därför installera AEM Cumulative Fix Pack 6.4.8.1-paketet när du har installerat AEM 6.4 Service Pack 8.

Några viktiga högdagrar i AEM 6.4.8.1 är:

* Anonym åtkomst till CRXDE Lite är inte tillåten för att öka säkerheten. I stället dirigeras användarna till inloggningsskärmen. Se [Utveckla med CRXDE Lite](/help/sites-developing/developing-with-crxde-lite.md).
* Borttagen Paketdelningsintegrering med Adobe Experience Manager.
* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.21.

Information om CFP och andra typer av releaser finns i [AEM Update Release Vehicle Definitions](https://docs.adobe.com/content/help/en/experience-manager-65/deploying/deploying/update-release-vehicle-definitions.html)

Adobe Experience Manager 6.4.8.1 innehåller korrigeringar av följande problem.

#### Platser {#sites-6481}

* Anonyma användare har tillgång till CRX DE Lite-funktioner (NPR-33522).
* När namnet på en lokal komponent i en LiveCopy är identiskt med namnet på en komponent i utkastet och komponenten rullas ut från utkast, läggs termen _msm_move inte till i namnet på den lokala komponenten (NPR-33207).
* Parametrarna som läggs till i den ursprungliga begäran ingår inte i omdirigerings-URL:en (NPR-33174).
* När alternativet Coral.Select anger emptyOption=true eller innehåller ett standardobjekt med värdet = &quot;&quot;, kommer filen dropdownshowhide.js att stöta på ett fel: Uncaught TypeError: component.getValue är inte en funktion (NPR-33163).
* När en komponent innehåller en annan komponent som en dataunderordnad resurs ersätts platshållaren för den överordnade behållarkomponenten med platshållaren för de inre komponenterna (NPR-33119).
* När du baserar ett innehållsfragment på ett schema och det innehåller ett obligatoriskt textområde eller ett sökvägsfält, kan innehållsfragmentet inte sparas (NPR-33007)
* När du skapar en anpassad komponent med hjälp av körningsfragmentkomponenten och använder den på AEM Sites-sidor, visas inga referenser (användning) för den anpassade komponenten (NPR-32852) i AEM.
* När en AEM Sites-sida är en del av en stor innehållsuppsättning med flera live-kopior går det inte att läsa in förhandsgranskningen av sidversionshistoriken (NPR-32772).
* När du befordrar en programstart läggs&quot;cq:LiveRelationship&quot;-blandningen till i alla komponenter som läggs till vid programstarten. Det påverkar alla starter oavsett om en start skapas med eller utan att alternativet - Inherit source page live data - (NPR-32664) väljs.
* När sidnumreringen startar läses inte Experience Fragments Picker in alla objekt (NPR-32605).
* Det går inte att skapa en startsida för en AEM Sites-sida. Startskapande resulterar i ett fel (NPR-32544).
* Hantera publikation innehåller inte refererade resurser i begäran om aktiveringsarbetsflöde (NPR-32463).
* Hälsokontrollen för utskickaren visar `Invalid cookie header`-varningsmeddelandet i loggfilerna (NPR-33630).
* Salesforce-integrering är sårbar för SSRF (NPR-32671).
* Speglad XSS i PreferencesServlet (NPR-33439).

#### Resurser {#assets-6481}

* Antalet resurser ändras inte enligt ändringen i urvalet i listvyn (NPR-33285).

* Knappen Nästa aktiveras inte när du väljer överordnad nod (där en underordnad mapp visas) och sedan väljer underordnad mapp (NPR-33284).

* Touchgränssnittet återges inte (med fel) för användare som inte har läsåtkomst i databasroten när DMS7- eller hybridläget är aktiverat (NPR-33175).

* De GB18030-tecken som finns i mapp- och resursnamn ändras till tomma i de hämtade zip-filerna (NPR-33150).

* En extra mapp skapas vid smart beskärning av en resurs som finns i en överordnad mapp med punkten `.` i namnet (NPR-32755).

* Lazy-inläsning aktiveras inte och högst 100 resurser visas när du väljer att granska uppgifter från meddelandeinkorgen (NPR-32749).

* Länksidan till delningssamlingen har brutits på grund av ändringar i koralinformationen (NPR-32510).

* Resursbearbetning när massöverföring fastnar (CQ-4293916).

* SSRF-sårbarhet i Experience Manager (NPR-33437).

#### Plattform {#platform-6481}

* Filtret [!DNL Sling] anropas inte om mappningsposten `sling:match` skapas under `/etc/maps` (NPR-33308).
* Alla rensningsagenter aktiveras när en sida inaktiveras (NPR-32941).
* När du använder `ScriptProcessor`-API:t för att miniera ett JavaScript-bibliotek visas ett felmeddelande i loggfilen som anger att JavaScript-koden inte är kompatibel med strikt läge. API:t har inget alternativ för att aktivera eller inaktivera strikt läge. (NPR-32746).
* När en SQL-fråga körs längre, till exempel 7 timmar, slutar AEM svara (NPR-33043).

#### Användargränssnitt {#ui-6481}

* När du söker efter eller bläddrar i en bana med hjälp av en markeringsdialogruta visas allt innehåll i den valda JCR-noden i stället för att bara visa bilderna (NPR-32712).

#### Översättningsprojekt {#tranlation-6481}

* Ett `NullPointerException`-fel visas i loggarna när ett översättningsjobb körs (NPR-3220).

#### Integreringar {#integrations-6481}

* Serveröverskridande skriptning för JSON (NPR-32745).

#### Communities {#communities-6481}

* Författare som har skapat en ny grupp omdirigeras inte till avsnittet [!UICONTROL Community Group] i [!DNL Internet Explorer] 11 (NPR-33202).
* Ett fel inträffar vid åtkomst till sidan [!UICONTROL Activity Stream] (NPR-33152).
* Om du redigerar en [!DNL Communities]-grupp och ändrar miniatyrbilden uppdateras inte gruppens miniatyrbild (NPR-32603).
* När du skapar en version av meddelanden och prenumerationer på användargenererat innehåll (UGC) lagras ett felaktigt ID för källsidan (CQ-4289703).
* Serveröverskridande skriptproblem (NPR-33212).

#### Arbetsflöde {#workflow-6481}

* Vissa komponenter visas inte i den dialogruta som öppnas när en användare slutför ett arbetsflöde som innehåller en [!UICONTROL Dialog Participant step] (NPR-32989).

* Alternativet [!UICONTROL Timeline] i den vänstra listen tar längre tid att läsa in än förväntat (NPR-32850).

#### Forms {#forms-6481}

>[!NOTE]
>
>AEM Cumulative Fix Pack innehåller inte korrigeringar för AEM Forms. De levereras med ett separat Forms-tilläggspaket. Dessutom släpps ett kumulativt installationsprogram med korrigeringar för AEM Forms på JEE. Mer information finns i [Installera AEM Forms-tilläggspaket](#install-aem-forms-add-on-package) och [Installera AEM Forms JEE-installationsprogrammet](#install-aem-forms-jee-installer).

* Korrespondenshantering: När en användare klistrar in innehåll från ett [!DNL Word]-dokument behåller textdokumentfragmentet inte formateringen (NPR-33213).
* Adaptiv Forms: En ny rad i en sträng i en ordlista med adaptiva formulär lägger till `&#xa;` tecken i ordlistan (NPR-33265).
* Adaptiv Forms: Användaren kan inte spara ett anpassat formulär med mer än en bifogad fil (NPR-33214).
* Adaptiv Forms: Metoderna `AddInstance` och `RemoveInstance` för klassen Instance Manager lägger inte till dynamiskt antal instanser för lazy load-fragment på [!DNL Internet Explorer 11] (NPR-33201).
* Adaptiv Forms: Analyser som är aktiverade på ett adaptivt formulär inbäddat på en [!DNL Sites]-sida registrerar inte data för händelserna Submit och Abandon (NPR-31359).
* Adaptiv Forms: När en användare klistrar in innehållet från ett [!DNL Word]-dokument i ett adaptivt formulär och skickar det innehåller det skickade adaptiva formuläret unicode-tecken. Dessutom misslyckas konverteringen av PDF till PDF/A på grund av Unicode-tecken (NPR-33348).
* BackendIntegration: Begäranden från formulärdatamodellen misslyckas eftersom uppdateringstoken förfaller på grund av ett inaktivt tillstånd (NPR-33168).
* Dokumenttjänster: Konvertering av PDF-tjänst kan inte konvertera PDF-dokument till PostScript eftersom Gibson-jars saknas för [!DNL WebLogic] på [!DNL Linux]-servern (NPR-33515, CQ-4292239).
* Dokumenttjänster: När en användare konverterar en textfil till en PDF-fil återges inte japanska tecken korrekt (NPR-33239).
* Lagrade XSS med GuideSOMProviderServlet (NPR-32701).

## Installera 6.4.8.4 {#install}

### Installationskrav {#setup-requirements}

<!--

>[!NOTE]
>
>For successful installation of AEM 6.4.6.0 on the instance, it is strongly recommended to upgrade the version of com.adobe.granite.oak.s3connector to 1.8.4 for the customers who are on the older version of s3 connector.
>The process of upgrading the com.adobe.granite.oak.s3connector is available at [https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html](https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html).
>Download the latest version of com.adobe.granite.oak.s3connector from: [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/)

-->

>[!CAUTION]
>
>För kunder med funktionspaket installerade på AEM 6.4. De tillvalsfunktioner som tillhandahålls av Adobe är beroende av releaseversion och servicepaket. Om du har något funktionspaket installerat kontaktar du AEM kundtjänst för att kontrollera om dessa funktionspaket är kompatibla med detta kumulativa korrigeringspaket för AEM 6.4.

* AEM 6.4.8.4 kräver AEM 6.4.8.0. Mer information finns i [uppgraderingsdokumentationen](../sites-deploying/upgrade.md).
* Installera AEM 6.4.8.4 i en distribution med MongoDB och flera instanser med hjälp av Package Manager.
* Innan du installerar det kumulativa korrigeringspaketet måste du se till att du har en ögonblicksbild eller en ny säkerhetskopia av AEM.
* Starta om instansen innan du installerar den. Detta behövs bara när instansen fortfarande är i uppdateringsläge (och detta är fallet när instansen precis uppdaterades från en tidigare version), men rekommenderas vanligtvis om instansen kördes under en längre tidsperiod.

>[!NOTE]
>
>Adobe rekommenderar inte att AEM 6.4.8.4-paketet tas bort eller avinstalleras.

### Installera det kumulativa korrigeringspaketet {#install-cumulative-fix-pack}

Så här installerar du Cumulative Fix Pack på en befintlig AEM 6.4.8.0-instans:

1. Klicka på länken [Programdistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-4.0.zip) för att hämta paketet.

1. Öppna [Pakethanteraren](http://localhost:4502/crx/packmgr/index.jsp) och klicka på **[!UICONTROL Upload Package]** för att överföra paketet.

1. Markera paketnamnet och klicka på **[!UICONTROL Install]**.

>[!NOTE]
>
>**Dialogrutan för Package Manager-gränssnittet avslutas ibland på ett felaktigt sätt under installationen av 6.4.8.4**
>
>Därför rekommenderar vi att du väntar på att felloggarna ska stabiliseras innan du får åtkomst till instansen. Användaren måste vänta på specifika loggar för avinstallation av uppdateringspaketet innan den kan vara säker på att installationen lyckas. Det händer vanligtvis på Safari, men kan hända i olika webbläsare.

### Automatisk installation {#auto-installation}

Det finns två sätt att automatiskt installera AEM 6.4.8.4 i en instans som körs:

S. Placera paketet i ..*/crx-quickstart/* installfolder när servern körs. Paketet installeras automatiskt.

B. Använd [HTTP-API:t från Package Manager](https://docs.adobe.com/content/docs/en/crx/2-3/how_to/package_manager.html) - kontrollera att du använder `cmd=install&recursive=true` - så att det kapslade paketet installeras.

>[!NOTE]
>
>AEM 6.4.8.4 stöder inte installation av Bootstrap.

### Verifiera installation {#validate-install}

1. Produktinformationssidan (*/system/console/productinfo*) ska nu visa den uppdaterade versionssträngen &quot;Adobe Experience Manager, Version 6.4.8.4&quot; under Installerade produkter.
1. Alla OSGI-paket är antingen AKTIVA eller FRAGMENT i OSGI-konsolen (Använd webbkonsolen: /system/console/bundles).
1. OSGI-paketet org.apache.jackrabbit.oak-core finns i version 1.8.17 eller senare (Använd webbkonsol: /system/console/bundles).

Information om vilken certifierad plattform som används i den här versionen av AEM Sites och Assets finns i [Tekniska krav](../sites-deploying/technical-requirements.md).

>[!NOTE]
>När paketet har installerats visas ett informationsmeddelande som anger att innehållspaketet har installerats, t.ex. **&quot;Innehållspaket AEM-6.4-Service-Pack-8 har installerats.&quot;**

### Uppdatera Dynamic Media-visningsprogram (5.10.1) {#update-dynamic-media-viewers}

AEM 6.4.8.4 innehåller en ny version av Dynamic Media-visningsprogram (5.10.1) som gör det möjligt att kontrollera om det finns dubblettnamn på sidan Bildförinställning. Dynamic Media-kunder uppmanas att köra följande kommando för att få fram aktuella visningsinställningar för boxen.

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

som kopierar nya visningsförinställningar till /conf-platsen.

### Installera AEM för formulärtillägg {#install-aem-forms-add-on-package}

>[!NOTE]
>
>[!DNL Experience Manager Forms] släpper tilläggspaketen en vecka efter det schemalagda  [!DNL Experience Manager] Cumulative Fix Pack-frisläppningsdatumet.

### Uber Jar {#uber-jar}

Uber Jar för AEM 6.4.8.4 finns i [Maven Central-databasen](https://repo.maven.apache.org/maven2/com/adobe/aem/uber-jar/6.4.8.4/).

Om du vill använda Uber Jar i ett Maven-projekt kan du läsa artikeln [Använda Uber jar](../sites-developing/ht-projects-maven.md) och inkludera följande beroende i projektstrukturen:

```shell
<dependency>
      <groupId>com.adobe.aem</groupId>
      <artifactId>uber-jar</artifactId>
      <version>6.4.8.4</version>
      <scope>provided</scope>  
</dependency>
```

>[!NOTE]
>
>UberJar och andra relaterade artefakter finns tillgängliga i Maven Central Repository i stället för i Adobe Public Maven-databasen (repo.adobe.com). Huvudfilen för UberJar har bytt namn till `uber-jar-<version>.jar`. Därför finns det ingen `classifier` med `apis` som värde för taggen `dependency`.

## Borttagna/inaktuella funktioner {#removed-deprecated-features}

I det här avsnittet visas funktioner som har tagits bort eller tagits bort från AEM 6.4.

| Yta | Funktion | Ersättning | Version |
|---|---|---|---|
| Assets | Hantera taggåtgärd för underresurser | Ingen ersättning | AEM 6.4.2.0 |
| Resurser och integrering med Adobe Creative Cloud | [AEM till ](https://docs.adobe.com/content/help/en/experience-manager-64/assets/administer/aem-cc-folder-sharing-best-practices.html) mappdelning mellan Creative Cloud introducerades i AEM 6.2 som ett sätt att ge kreativa användare tillgång till resurser från AEM. En ny funktion i Creative Cloud, Adobe Asset Link, ger en mycket bättre användarupplevelse och kraftfullare åtkomst till AEM direkt inifrån Photoshop, InDesign och Illustrator. Adobe kommer inte att förbättra mappdelningsfunktionen ytterligare. Funktionen ingår i AEM, men kunderna rekommenderas att använda ersättaren. | Adobe Asset Link eller datorprogram. Mer information finns i [AEM Creative Cloud-integrering](/help/assets/aem-cc-integration-best-practices.md)-artikeln. | AEM 6.4.4.0 |

## Kända fel {#known-issues}

* Om du uppgraderar från [!DNL Experience Manager] 6.4 till [!DNL Experience Manager] 6.5 kanske vissa av paketen inte visar sin status som `Active`. Installera det senaste [!DNL Experience Manager] 6.5 Service Pack-meddelandet för att lösa problemet.

Information om kända fel i AEM 6.4.8.0 Service Pack finns i [AEM 6.4.8.0 Service Pack Release Notes](sp-release-notes.md).

## OSGi-paket och innehållspaket som ingår {#osgi-bundles-and-content-packages-included}

Följande textdokument listar de OSGi-paket och innehållspaket som ingår i AEM 6.4.8.4.

Förteckning över OSGi-paket som ingår i AEM 6.4.8.4

[Hämta fil](assets/6.4.8.4_osgi_bundles.txt)

Förteckning över innehållspaket som ingår i AEM 6.4.8.4

[Hämta fil](assets/6.4.8.4_content_packages.txt)

## Användbara resurser {#helpful-resources}

* [Versionsinformation för AEM 6.4](../release-notes/release-notes.md)
* [AEM produktsida](https://www.adobe.com/solutions/web-experience-management.html)
* [AEM 6.4-dokumentation](https://helpx.adobe.com/support/experience-manager/6-4.html)
* Prenumerera på [produktuppdateringar med Adobe prioritet](https://www.adobe.com/subscription/priority-product-update.html)

## Begränsade platser {#restricted-sites-new}

Dessa webbplatser är bara tillgängliga för kunder. Om du är kund och behöver åtkomst kontaktar du din kontoansvarige på Adobe.

* [Nedladdning av produkt på licensing.adobe.com](https://licensing.adobe.com/)
* [Kontakta kundsupport](https://docs.adobe.com/content/help/en/customer-one/using/home.html)
