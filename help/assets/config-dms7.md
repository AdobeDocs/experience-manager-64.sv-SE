---
title: Konfigurera Dynamic Media - Scene7-läge
description: Lär dig hur du konfigurerar läget Dynamic Media - Scene7.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: b0f0c6e4-77c8-40db-a9f4-699d1a633571
feature: Configuration,Scene7 Mode
role: Admin,User,Developer
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '5237'
ht-degree: 2%

---

# Konfigurera Dynamic Media - Scene7-läge {#configuring-dynamic-media-scene-mode}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Om du använder Adobe Experience Manager för olika miljöer, som utveckling, testning och liveproduktion, måste du konfigurera Dynamic Media-Cloud Services för varje miljö.

## Arkitekturdiagram över Dynamic Media - Scene7-läge {#architecture-diagram-of-dynamic-media-scene-mode}

I följande arkitekturdiagram beskrivs hur läget Dynamic Media - Scene7 fungerar.

Med den nya arkitekturen ansvarar Experience Manager för de viktigaste tillgångarna och synkningarna med Dynamic Media för bearbetning och publicering av mediefiler:

1. När den primära resursen överförs till Experience Manager replikeras den till Dynamic Media. Då hanterar Dynamic Media all bearbetning och generering av resurser, till exempel videokodning och dynamiska varianter av en bild.
1. När återgivningarna har genererats kan Experience Manager på ett säkert sätt komma åt och förhandsgranska Dynamic Media-fjärråtergivningarna (inga binärfiler skickas tillbaka till Experience Manager-instansen).
1. När innehållet är klart att publiceras och godkännas utlöses Dynamic Media-tjänsten att skicka ut innehåll till leveransservrar och cachelagra innehåll på CDN.

![chlimage_1](assets/chlimage_1.png)

## Aktivera Dynamic Media i Scene7-läge {#enabling-dynamic-media-in-scene-mode}

[Dynamic Media](https://www.adobe.com/marketing-cloud/enterprise-content-management/dynamic-media.html) är inaktiverat som standard. Om du vill utnyttja Dynamic Media funktioner måste du aktivera dem.

>[!WARNING]
>
>Dynamic Media - Scene7 *Endast författarinstans i Experience Manager*. Konfigurera `runmode=dynamicmedia_scene7`på Experience Manager Author-instansen, *not* Experience Manager Publish-instansen.

Om du vill aktivera Dynamic Media måste du börja använda Experience Manager med `dynamicmedia_scene7` körningsläge från kommandoraden genom att ange följande i ett terminalfönster (den exempelport som används är 4502):

```shell
java -Xms4096m -Xmx4096m -Doak.queryLimitInMemory=500000 -Doak.queryLimitReads=500000 -jar cq-quickstart-6.4.0.jar -gui -r author,dynamicmedia_scene7 -p 4502
```

## (Valfritt) Migrera förinställningar och konfigurationer för Dynamic Media från 6.3 till 6.4 utan driftstopp {#optional-migrating-dynamic-media-presets-and-configurations-from-to-zero-downtime}

Om du uppgraderar Experience Manager Dynamic Media från 6.3 till 6.4 (vilket inkluderar möjligheten till noll driftsättning under driftstopp) kör du följande kommando för att migrera alla dina förinställningar och konfigurationer från `/etc` till `/conf` i CRXDE Lite.

>[!NOTE]
>
>Om du kör Experience Manager-instansen i kompatibilitetsläge, d.v.s. har kompatibilitetspaketet installerat, behöver du inte köra dessa kommandon.

Migrera dina anpassade förinställningar och konfigurationer från `/etc` till `/conf`kör du följande Linux®-kommando:

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets.migratedmcontent.json`

För alla uppgraderingar, antingen med eller utan kompatibilitetspaketet, kan du kopiera förinställningarna för visningsprogrammet som inte är installerade genom att köra följande kommando:

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

## (Valfritt) Installera funktionspaket 18912 för migrering av bulkresurser {#installing-feature-pack}

Med funktionspaketet 18912 kan du antingen importera resurser gruppvis via FTP eller migrera resurser från antingen Dynamic Media - hybrid- eller Dynamic Media Classic till Dynamic Media - Scene7-läge på Experience Manager. Den kan fås från Adobe Professional Services.

Se [Installerar funktionspaket 18912 för migrering av gruppresurser](bulk-ingest-migrate.md) för mer information.

## Konfigurera Dynamic Media-Cloud Services {#configuring-dynamic-media-cloud-services}

Ändra lösenordet innan du konfigurerar Dynamic Media-Cloud Services. När du har fått ditt e-postmeddelande med Dynamic Media-autentiseringsuppgifter måste du [logga in](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/intro/dynamic-media-classic-desktop-app.html#system-requirements-dmc-app) till Dynamic Media Classic för att ändra ditt lösenord. Lösenordet som anges i e-postmeddelandet om etablering genereras av systemet och är endast avsett som ett tillfälligt lösenord. Det är viktigt att du uppdaterar lösenordet så att Dynamic Media Cloud Service har rätt autentiseringsuppgifter.

>[!NOTE]
>
>Som standard är konfigurationssökvägen för Cloud Services `/content/dam`. Andra konfigurationssökvägar stöds inte i Dynamic Media - Scene7-läge.

**Så här konfigurerar du Dynamic Media-Cloud Services:**

1. I Experience Manager Author-instansen trycker du på Experience Manager-logotypen för att komma åt den globala navigeringskonsolen och trycker på verktygsikonen. Tryck sedan på **[!UICONTROL Cloud Services]** > **[!UICONTROL Dynamic Media Configuration]**.
1. På sidan Dynamic Media Configuration Browser (Konfigurationsläsare) trycker du på **[!UICONTROL global]** och trycka **[!UICONTROL Create]**. Tryck inte på eller välj mappikonen till vänster om [!UICONTROL global].
1. På [!UICONTROL Create Dynamic Media Configuration] anger du en titel, e-postadress och lösenord för Dynamic Media-kontot. Välj region. Den här informationen tillhandahålls av Adobe i ditt e-postmeddelande om etablering. Kontakta Adobe kundsupport om du inte fått e-postmeddelandet.

   Tryck på **[!UICONTROL Connect to Dynamic Media]**.

   >[!NOTE]
   >
   >När du har fått ditt e-postmeddelande med Dynamic Media-autentiseringsuppgifter öppnar du [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started)och logga sedan in på ditt företagskonto för att ändra ditt lösenord. Lösenordet som anges i e-postmeddelandet om etablering genereras av systemet och är endast avsett som ett tillfälligt lösenord. Det är viktigt att du uppdaterar lösenordet så att Dynamic Media-Cloud Servicen har rätt autentiseringsuppgifter.

1. Om anslutningen lyckas kan du även ange följande:

   * **[!UICONTROL Company]** - namnet på Dynamic Media-kontot.

      >[!IMPORTANT]
      >
      >Endast en Dynamic Media-konfiguration i Cloud Services stöds i en instans av Experience Manager. lägger inte till mer än en konfiguration. Flera Dynamic Media-konfigurationer i en Experience Manager-instans är *not* som stöds eller rekommenderas av Adobe.<!-- CQDOC-19579 and CQDOC-19612 -->
   * **[!UICONTROL Company Root Folder Path]** - Sökväg till företagets rotmapp.
   * **[!UICONTROL Publishing Assets]** - alternativet **[!UICONTROL Immediately]** betyder att när resurser överförs, importeras resurserna och URL:en/inbäddningen anges omedelbart. Ingen användaråtgärd krävs för att publicera resurser. Alternativet **[!UICONTROL Upon Activation]** betyder att du måste publicera resursen explicit innan en URL/Embed-länk anges.
   * **[!UICONTROL Secure Preview Server]** - gör att du kan ange URL-sökvägen till förhandsgranskningsservern för säkra återgivningar. Det innebär att när återgivningarna har genererats kan Experience Manager på ett säkert sätt komma åt och förhandsgranska Dynamic Media-fjärråtergivningarna (inga binärfiler skickas tillbaka till Experience Manager-instansen).

      Om du inte har en särskild lösning för att använda ditt företags server eller en speciell server rekommenderar Adobe att du använder standardinställningen.
   >[!NOTE]
   >
   >Det finns inget stöd för versionshantering i DMS7. Dessutom gäller fördröjd aktivering endast om **[!UICONTROL Publish Assets]** i [!UICONTROL Edit Dynamic Media Configuration] sidan är inställd på **[!UICONTROL Upon Activation]** och sedan bara tills första gången tillgången aktiveras.
   >
   >När en mediefil har aktiverats publiceras uppdateringar direkt till S7 Delivery.

   ![dynamicmediaconfiguration2updated](assets/dynamicmediaconfiguration2updated.png)

1. Tryck på **[!UICONTROL Save]**.
1. Om du vill förhandsgranska Dynamic Media-innehåll på ett säkert sätt innan det publiceras måste du&quot;tillåtslista&quot; Experience Manager Author-instansen för att ansluta till Dynamic Media:

   * Öppna [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started)och logga sedan in på ditt konto. Dina autentiseringsuppgifter och inloggningsuppgifter tillhandahölls av Adobe vid tidpunkten för etableringen. Om du inte har den här informationen kontaktar du teknisk support.
   * Tryck på i navigeringsfältet uppe till höger på sidan **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]** > **[!UICONTROL Publish Setup]** > **[!UICONTROL Image Server]**.
   * På sidan Image Server Publish (Publicera kontext) väljer du **[!UICONTROL Test Image Serving]**.
   * Tryck på för klientadressfiltret **[!UICONTROL Add]**.
   * Markera kryssrutan om du vill aktivera (aktivera) adressen. Ange IP-adressen för Experience Manager Author-instansen (inte Dispatcher IP).
   * Tryck på **[!UICONTROL Save]**.

Du är nu klar med den grundläggande konfigurationen; är du redo att använda Dynamic Media - Scene7.

Om du vill anpassa konfigurationen ytterligare kan du utföra alla uppgifter under [(Valfritt) Konfigurera avancerade inställningar i Dynamic Media - Scene7-läge](#optional-configuring-advanced-settings-in-dynamic-media-scene-mode).

## (Valfritt) Konfigurera avancerade inställningar i Dynamic Media - Scene7-läge {#optional-configuring-advanced-settings-in-dynamic-media-scene-mode}

Om du vill anpassa konfigurationen och konfigurationen av Dynamic Media - Scene7 eller optimera prestandan ytterligare kan du utföra en eller flera av följande valfria uppgifter:

* [(Valfritt) Installation och konfiguration av Dynamic Media - inställningar för Scene7-läge](#optional-setup-and-configuration-of-dynamic-media-scene-mode-settings-p)

* [(Valfritt) Justera prestanda för Dynamic Media - Scene7-läge](#optional-tuning-the-performance-of-dynamic-media-scene-mode)
* [(Valfritt) Filtrera resurser för replikering](#optional-filtering-assets-for-replication)

### (Valfritt) Installation och konfiguration av Dynamic Media - inställningar för Scene7-läge</p> {#optional-setup-and-configuration-of-dynamic-media-scene-mode-settings-p}

När du är **dynamicmedia_scene7** i körläge använder du Dynamic Media Classic användargränssnitt för att ändra dina Dynamic Media-inställningar.

Vissa av ovanstående uppgifter kräver att du öppnar [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started)och logga sedan in på ditt konto.

Installations- och konfigureringsuppgifter är:

* [Publiceringskonfiguration för Image Server](#publishing-setup-for-image-server)
* [Konfigurera allmänna inställningar för programmet](#configuring-application-general-settings)
* [Konfigurera färghantering](#configuring-color-management)
* [Redigera MIME-typer för format som stöds](#editing-mime-types-for-supported-formats)
* [Lägga till MIME-typer för format som inte stöds](#adding-mime-types-for-unsupported-formats)
* [Skapa gruppuppsättningsförinställningar för automatisk generering av bilduppsättningar och snurpuppsättningar](#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets)

#### Publiceringskonfiguration för Image Server {#publishing-setup-for-image-server}

Publiceringsinställningarna avgör hur resurser levereras som standard från Dynamic Media. Om ingen inställning anges levererar Dynamic Media en resurs enligt standardinställningarna som definierats i Publiceringsinställningar. En begäran om att leverera en bild som inte innehåller ett upplösningsattribut ger till exempel en bild med inställningen för standardobjektupplösning.

Så här konfigurerar du publiceringsinställningar: i Dynamic Media Classic: tryck **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]** > **[!UICONTROL Publish Setup]** > **[!UICONTROL Image Server]**.

Bildserverskärmen anger standardinställningar för att leverera bilder. En beskrivning av varje inställning finns i användargränssnittet.

* **[!UICONTROL Request Attributes]** - De här inställningarna begränsar antalet bilder som kan levereras från servern.
* **[!UICONTROL Default Request Attributes]** - De här inställningarna gäller standardutseendet för bilder.
* **[!UICONTROL Common Thumbnail Attributes]** - De här inställningarna gäller för miniatyrbildernas standardutseende.
* **[!UICONTROL Defaults for Catalog Fields]** - De här inställningarna gäller bildernas upplösning och standardtyp av miniatyrbilder.
* **[!UICONTROL Color Management Attributes]** - De här inställningarna avgör vilka ICC-färgprofiler som används.
* **[!UICONTROL Compatibility Attributes]** - Den här inställningen gör att inledande och avslutande stycken i textlager kan hanteras som de var i version 3.6 för bakåtkompatibilitet.
* **[!UICONTROL Localization Support]** - Med de här inställningarna kan du hantera flera språkattribut. Här kan du också ange en sträng för språkområdeskarta så att du kan definiera vilka språk du vill ha stöd för de olika verktygstipsen i visningsprogram. Mer information om hur du konfigurerar stöd för lokalisering finns i [Viktiga överväganden vid implementering av lokaliseringsstöd](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/setup/publish-setup.html#image-server).

#### Konfigurera allmänna inställningar för programmet {#configuring-application-general-settings}

Öppna [!UICONTROL Application General Settings] i Dynamic Media Classic Global Navigation bar, tryck **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]** > **[!UICONTROL General Settings]**.

**[!UICONTROL Servers]** - Vid kontoetablering tillhandahåller Dynamic Media automatiskt de tilldelade servrarna för ditt företag. De här servrarna används för att skapa URL-strängar för din webbplats och dina program. Dessa URL-anrop är specifika för ditt konto. Ändra inte något av servernamnen om du inte uttryckligen har fått instruktioner om att göra det från Experience Manager.

**[!UICONTROL Overwrite Images]** - Dynamic Media tillåter inte att två filer har samma namn. Varje objekts URL-ID (filnamnet minus filtillägget) måste vara unikt. De här alternativen anger hur ersättningsresurser överförs: om de ersätter originalet eller blir dubbletter. Duplicerade resurser får ett nytt namn med namnet&quot;-1&quot; (till exempel heter stol.tif stol-1.tif). Dessa alternativ påverkar resurser som överförts till en annan mapp än den ursprungliga eller resurser med ett annat filnamnstillägg än den ursprungliga (till exempel JPG, TIF eller PNG).

* **[!UICONTROL Overwrite in current folder, same base image name/extension]** - Det här alternativet är den striktaste regeln för ersättning. Det kräver att du överför ersättningsbilden till samma mapp som originalbilden och att ersättningsbilden har samma filnamnstillägg som originalbilden. Om dessa krav inte uppfylls skapas en dubblett.

>[!NOTE]
>
>Om du vill vara konsekvent med Experience Manager väljer du **[!UICONTROL Overwrite in current folder, same base image name/extension]**.

* **[!UICONTROL Overwrite in any folder, same base asset name/extension]** - Kräver att ersättningsbilden har samma filnamnstillägg som originalbilden (till exempel `chair.jpg` Ersätter `chair.jpg` och inte `chair.tif`). Du kan dock överföra ersättningsbilden till en annan mapp än den ursprungliga. Den uppdaterade bilden finns i den nya mappen; filen inte längre kan hittas på sin ursprungliga plats.
* **[!UICONTROL Overwrite in any folder, same base asset name regardless of extension]** - Det här alternativet är den mest omfattande ersättningsregeln. Du kan överföra en ersättningsbild till en annan mapp än den ursprungliga, överföra en fil med ett annat filnamnstillägg och ersätta den ursprungliga filen. Om originalfilen finns i en annan mapp finns ersättningsbilden i den nya mappen som den överfördes till.

**[!UICONTROL Default Color Profiles]** - Se [Konfigurera färghantering](#configuring-color-management) för ytterligare information.

>[!NOTE]
>
>Som standard visas 15 återgivningar när du väljer **[!UICONTROL Renditions]** och 15 visningsförinställningar när du väljer **[!UICONTROL Viewers]** i resursens detaljvy. Du kan öka den här gränsen. Se [Öka antalet bildförinställningar som visas](managing-image-presets.md#increasing-or-decreasing-the-number-of-image-presets-that-display) eller [Öka antalet visningsförinställningar som visas](managing-viewer-presets.md#increasing-the-number-of-viewer-presets-that-display).

#### Konfigurera färghantering {#configuring-color-management}

Med dynamisk mediefärghantering kan du färgkorrigera resurser. Med färgkorrigering behåller inkapslade resurser sin färgmodell (RGB, CMYK, Grå) och inbäddad färgprofil. När du begär en dynamisk återgivning korrigeras bildfärgen till målfärgrymden med hjälp av CMYK-, RGB- eller grå utdata. Se [Konfigurera bildförinställningar](managing-image-presets.md).

**Så här konfigurerar du standardfärgegenskaperna så att färgkorrigering aktiveras när du begär bilder:**

1. Öppna [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started)loggar sedan in på ditt konto med de autentiseringsuppgifter som anges under etableringen. Navigera till **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]**.
1. Expandera området **[!UICONTROL Publish Setup]** och markera **[!UICONTROL Image Server]**. Ange **[!UICONTROL Publish Context]** som **[!UICONTROL Image Serving]** när du anger standardvärden för publiceringsinstanser.
1. Bläddra till den egenskap som du måste ändra. En egenskap i **[!UICONTROL Color Management Attributes]** område.

   Du kan ange följande egenskaper för färgkorrigering:

   * [!UICONTROL CMYK Default Color Space] - Namn på CMYK-standardfärgprofil
   * [!UICONTROL Gray-Scale Default Color Space] - Namn på standardfärgprofilen för gråskala
   * [!UICONTROL RGB Default Color Space] - Namn på standardfärgprofilen för RGB
   * [!UICONTROL Color Conversion Rendering Intent] - Anger återgivningsmetod. Godkända värden är `perceptual`, `relative` `colometric`, `saturation`och `absolute colometric`. Adobe rekommenderar `relative` som standard.

1. Tryck på **[!UICONTROL Save]**.

Du kan till exempel ställa in **[!UICONTROL RGB Default Color Space]** på `sRGB` och **[!UICONTROL CMYK Default Color Space]** på `WebCoated`.

Om du gör det gör du så här:

* Aktiverar färgkorrigering för RGB och CMYK-bilder.
* RGB-bilder som inte har någon färgprofil antas finnas i `sRGB` färgrymd.
* CMYK-bilder som inte har någon färgprofil antas finnas i `WebCoated` färgrymd.
* Dynamiska återgivningar som returnerar utdata från RGB, returnerar dem i dialogrutan `sRGB` färgrymd.
* Dynamiska återgivningar som returnerar CMYK-utdata, returnerar dem i `WebCoated` färgrymd.

#### Redigera MIME-typer för format som stöds {#editing-mime-types-for-supported-formats}

Du kan definiera vilka resurstyper som bearbetas av Dynamic Media och anpassa avancerade parametrar för resurshantering. Du kan till exempel ange parametrar för tillgångsbearbetning för att göra följande:

* Konvertera en Adobe PDF till en eCatalog-resurs.
* Konvertera ett Adobe Photoshop-dokument (.PSD) till en bannermallsresurs för personalisering.
* Rastrera en Adobe Illustrator-fil (.AI) eller en Adobe Photoshop Encapsulated PostScript®-fil (.EPS).
* [Videoprofiler](/help/assets/video-profiles.md) och [Bildprofiler](/help/assets/image-profiles.md) kan användas för att definiera bearbetning av videoklipp och bilder.

Se [Överför resurser](managing-assets-touch-ui.md#uploading-assets).

**Så här redigerar du MIME-typer för de format som stöds:**

1. I Experience Manager trycker du på Experience Manager-logotypen för att komma åt den globala navigeringskonsolen och sedan på **[!UICONTROL Tools]** (hammer) och navigera till **[!UICONTROL General]** > **[!UICONTROL CRXDE Lite]**.
1. Navigera till följande i den vänstra listen:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content/mimeTypes`

   ![mimetypes](assets/mimetypes.png)

1. Under `mimeTypes` väljer du en MIME-typ.
1. Till höger på CRXDE Lite-sidan i den nedre delen:

   * dubbelklicka på **[!UICONTROL enabled]** fält. Som standard är alla resursens MIME-typer aktiverade (inställda på **[!UICONTROL true]**), vilket innebär att resurserna synkroniseras till Dynamic Media för bearbetning. Om du vill utesluta den här resursens MIME-typ från bearbetningen ändrar du den här inställningen till **[!UICONTROL false]**.
   * dubbelklicka **[!UICONTROL jobParam]** för att öppna det tillhörande textfältet. Se [MIME-typer som stöds](assets-formats.md#supported-mime-types) för en lista över tillåtna värden för bearbetningsparametrar som du kan använda för en viss MIME-typ.

1. Gör något av följande:

   * Upprepa steg 3-4 för att redigera fler MIME-typer.
   * Tryck på **[!UICONTROL Save All]**.

1. Tryck på längst upp till vänster på sidan **[!UICONTROL CRXDE Lite]** för att återvända till Experience Manager.

#### Lägga till anpassade MIME-typer för format som inte stöds {#adding-custom-mime-types-for-unsupported-formats}

Du kan lägga till anpassade MIME-typer för format som inte stöds i Experience Manager Assets. Om du vill vara säker på att alla nya noder som du lägger till i CRXDE Lite inte tas bort av Experience Manager, flyttar du MIME-typen före **[!UICONTROL image_]** och dess aktiverade värde är **[!UICONTROL false]**.

**Så här lägger du till anpassade MIME-typer för format som inte stöds:**

1. Klicka på Experience Manager **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.

   ![Webbkonsol](assets/2019-08-02_16-13-14.png)

1. En ny flik i webbläsaren öppnas **[!UICONTROL Adobe Experience Manager Web Console Configuration]** sida.

   ![Konfiguration av Experience Manager Web Console](assets/2019-08-02_16-17-29.png)

1. Bläddra nedåt till namnet på sidan **[!UICONTROL Adobe CQ Scene7 Asset MIME type Service]**. Tryck till höger om namnet **[!UICONTROL Edit the configuration values]** (pennikon).

   ![Redigera konfigurationsvärdena](assets/2019-08-02_16-44-56.png)

1. På **[!UICONTROL Adobe CQ Scene7 Asset MIME type Service]** sida, klicka på en plusteckenikon `+`. Platsen i tabellen där du klickar på plustecknet för att lägga till den nya mime-typen är enkel.

   ![Plusteckenikon](assets/2019-08-02_16-27-27.png)

1. Typ `DWG=image/vnd.dwg` i det tomma textfältet som du just lade till.

   Exemplet `DWG=image/vnd.dwg` endast för demonstrationsändamål. MIME-typen som du lägger till här kan vara ett annat format som inte stöds.

   ![Exempel på MIME-typtillägg](assets/2019-08-02_16-36-36.png)

1. I sidans nedre högra hörn klickar du på **[!UICONTROL Save]**.

   Nu kan du stänga webbläsarfliken som har den öppna konfigurationssidan för Adobe Experience Manager Web Console.

1. Gå tillbaka till webbläsarfliken som har din öppna Experience Manager-konsol.

1. Klicka på Experience Manager **[!UICONTROL Tools]** > **[!UICONTROL General]** > **[!UICONTROL CRXDE Lite]**.

   ![CRXDE Lite page](assets/2019-08-02_16-55-41.png)

1. Navigera till följande i den vänstra listen:

   `conf/global/settings/cloudconfigs/dmscene7/jcr:content/mimeTypes`

1. Dra MIME-typen `image_vnd.dwg` och släpp det direkt ovanför `image_` i trädet.

   ![Dra Mime-typ](assets/CRXDELite_CQDOC-14627.png)

1. Med mime-typen `image_vnd.dwg` fortfarande markerad i trädet, från **[!UICONTROL Properties]** -fliken, i **[!UICONTROL enabled]** rad, under **[!UICONTROL Value]** kolumnrubrik, dubbelklicka på värdet för att öppna **[!UICONTROL Value]** nedrullningsbar lista.

1. Typ `false` i fältet (eller markera `false` från listrutan).

   ![Falskt värde](assets/2019-08-02_16_60_30.png)

1. Klicka på i det övre vänstra hörnet på CRXDE Lite-sidan **[!UICONTROL Save All]**.

#### Skapa gruppuppsättningsförinställningar för automatisk generering av bilduppsättningar och snurpuppsättningar {#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets}

Använd förinställningar för gruppuppsättningar för att automatisera skapandet av bilduppsättningar eller snurra uppsättningar medan resurserna överförs till Dynamic Media.

Definiera först namnkonventionen för hur resurser grupperas i en uppsättning. Du kan sedan skapa en gruppuppsättningsförinställning som är en unik, självständig uppsättning instruktioner som definierar hur uppsättningen ska skapas med bilder som matchar de definierade namnkonventionerna i förinställningsreceptet.

När du överför filer skapar Dynamic Media automatiskt en uppsättning med alla filer som matchar den definierade namnkonventionen i de aktiva förinställningarna.

**Konfigurerar standardnamngivning**

Skapa en standardnamnkonvention som används i alla förinställda gruppuppsättningar. Den standardnamnkonvention som valts i definitionen av gruppuppsättningsförinställningen är sannolikt allt som ditt företag behöver för att generera gruppuppsättningar. En gruppuppsättningsförinställning skapas för att använda den standardnamnkonvention som du definierar. Du kan skapa så många gruppuppsättningsförinställningar med alternativa, anpassade namnkonventioner som behövs för en viss uppsättning innehåll om det finns ett undantag från den företagsdefinierade standardnamngivningen.

När du behöver konfigurera en standardnamnkonvention behöver du inte använda funktionen för gruppuppsättningsförinställningar, men du kan använda den för att definiera så många element i namnkonventionen som du vill gruppera i en uppsättning. Det underlättar när du skapar gruppuppsättningar.

Du kan också använda **[!UICONTROL View Code]** utan formulärfält tillgängliga. I den här vyn skapar du namnkonventionens definitioner helt med hjälp av reguljära uttryck.

Det finns två definitionselement: **[!UICONTROL Match]** och **[!UICONTROL Base Name]**. Med dessa fält kan du definiera alla element i en namnkonvention och identifiera den del av konventionen som används för att namnge den uppsättning i vilken de finns. Ett företags personliga namnkonvention kan använda en eller flera definitionsrader för vart och ett av dessa element. Använd så många rader för din unika definition och gruppera dem i distinkta element. Exempel: Huvudbild, Färgelement, Alternativvy-element och Färgruteelement.

**Så här konfigurerar du standardnamn:**

1. Öppna [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started)och logga sedan in på ditt konto.

   Dina autentiseringsuppgifter och inloggningsuppgifter tillhandahölls av Adobe vid tidpunkten för etableringen. Om du inte har den här informationen kontaktar du teknisk support.

1. Tryck på **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]** > **[!UICONTROL Batch Set Presets]** > **[!UICONTROL Default Naming]**.
1. Välj **[!UICONTROL View Form]** eller **[!UICONTROL View Code]** för att ange hur du vill visa och ange information om varje element.

   Du kan välja **[!UICONTROL View Code]** om du vill visa värdeuppbyggnaden för reguljära uttryck tillsammans med dina formulärval. Du kan ange eller ändra dessa värden för att underlätta definitionen av elementen i namnkonventionen, om formulärvyn begränsar dig av någon anledning. Om dina värden inte kan tolkas i formulärvyn blir formulärfälten inaktiva.

   >[!NOTE]
   >
   >Inaktiverade formulärfält verifierar inte att reguljära uttryck är korrekta. Resultatet av det reguljära uttryck som du skapar för varje element efter resultatraden visas. Det fullständiga reguljära uttrycket visas längst ned på sidan.

1. Expandera varje element efter behov och ange de namnkonventioner som du vill använda.
1. Gör något av följande om det behövs:

   * Tryck **[!UICONTROL Add]** om du vill lägga till en annan namnkonvention för ett element.
   * Tryck **[!UICONTROL Remove]** om du vill ta bort en namnkonvention för ett element.

1. Gör något av följande:

   * Tryck **[!UICONTROL Save As]** och ange ett namn för förinställningen.
   * Tryck **[!UICONTROL Save]** om du redigerar en befintlig förinställning.

**Skapa en förinställning för gruppuppsättning**

I Dynamic Media används gruppuppsättningsförinställningar för att ordna resurser i uppsättningar med bilder (alternativa bilder, färgalternativ, 360 rotationer) för visning i visningsprogram. Förinställningarna för gruppuppsättningar körs automatiskt tillsammans med överföringsprocesserna för resurser i Dynamic Media.

Du kan skapa, redigera och hantera dina gruppuppsättningsförinställningar. Det finns två former av förinställda gruppuppsättningsdefinitioner: en för en standardnamnkonvention som du anger och en för anpassade namnkonventioner som du skapar direkt.

Du kan antingen använda formulärfältsmetoden för att definiera en gruppuppsättningsförinställning eller kodmetoden, som gör att du kan använda reguljära uttryck. Som i Standardnamngivning kan du välja [!UICONTROL View Code] samtidigt som du definierar i [!UICONTROL Form View] och använd reguljära uttryck för att bygga definitioner. Du kan också avmarkera en vy om du vill använda den ena eller den andra enbart.

**Så här skapar du en förinställning för gruppuppsättning:**

1. Öppna [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started)och logga sedan in på ditt konto.

   Dina autentiseringsuppgifter och inloggningsuppgifter tillhandahölls av Adobe vid tidpunkten för etableringen. Om du inte har den här informationen kontaktar du teknisk support.

1. Tryck på **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]** > **[!UICONTROL Batch Set Presets]** > **[!UICONTROL Batch Set Preset]**.

   [!UICONTROL View Form], enligt inställningen i det övre högra hörnet av [!UICONTROL Details] sida, är standardvy.

1. Tryck på panelen Förinställningslista **[!UICONTROL Add]** för att aktivera definitionsfälten i **[!UICONTROL Details]** till höger på skärmen.
1. I **[!UICONTROL Details]** på panelen **[!UICONTROL Preset Name]** anger du ett namn för förinställningen.
1. I **[!UICONTROL Batch Set Type]** väljer du en förinställningstyp.
1. Gör något av följande:

   * Om du använder en standardnamnkonvention som du tidigare ställt in under **[!UICONTROL Application Setup]** > **[!UICONTROL Batch Set Presets]** > **[!UICONTROL Default Naming]**, expandera **[!UICONTROL Asset Naming Conventions]** och sedan i **[!UICONTROL File Naming]** nedrullningsbar lista, knacka **[!UICONTROL Default]**.
   * Om du vill definiera en ny namnkonvention när du ställer in förinställningen, **[!UICONTROL Asset Naming Conventions]** och sedan i **[!UICONTROL File Naming]** nedrullningsbar lista, knacka **[!UICONTROL Custom]**.

1. För [!UICONTROL Sequence order]definierar du i vilken ordning bilderna ska visas när uppsättningen har grupperats i Dynamic Media.

   Som standard sorteras dina resurser alfanumeriskt. Du kan dock använda en kommaavgränsad lista med reguljära uttryck för att definiera ordningen.

1. För **[!UICONTROL Set Naming]** och **[!UICONTROL Creation Convention]** anger du suffixet eller prefixet för basnamnet som du definierade i **[!UICONTROL Asset Naming Convention]**. Ange också var uppsättningen ska skapas i mappstrukturen för Dynamic Media.

   Om du definierar ett stort antal uppsättningar ska du hålla dem åtskilda från de mappar som innehåller själva resurserna. Skapa till exempel en mapp för bilduppsättningar och placera genererade uppsättningar här.

1. I **[!UICONTROL Details]** panel, tryck **[!UICONTROL Save]**.
1. Tryck **[!UICONTROL Active]** bredvid den nya förinställningens namn.

   När du aktiverar förinställningen används den för att generera uppsättningen när du överför resurser till Dynamic Media.

**Skapa en gruppuppsättningsförinställning för automatisk generering av en 2D-snurpuppsättning**

Du kan använda gruppuppsättningstypen **[!UICONTROL Multi-Axis Spin Set]** för att skapa ett recept som automatiserar genereringen av tvådimensionella snurruppsättningar. Vid gruppering av bilder används reguljära uttryck för rad och kolumn så att bildresurserna justeras korrekt på motsvarande plats i den flerdimensionella arrayen. Det finns inget minsta eller högsta antal rader eller kolumner som du måste ha i en rotationsuppsättning med flera axlar.

Anta till exempel att du vill skapa en fleraxelsnurra med namnet `spin-2dspin`. Du har en uppsättning bilder med snurra uppsättningar som innehåller tre rader, med 12 bilder per rad. Bilderna får följande namn:

```
spin-01-01 
 spin-01-02 
 … 
 spin-01-12 
 spin-02-01 
 … 
 spin-03-12
```

Med den här informationen kan du [!UICONTROL Batch Set Type] recept kan skapas på följande sätt:

![chlimage_1-1](assets/chlimage_1-1.png)

Gruppering för den delade resursnamndelen i rotationsuppsättningen läggs till i **[!UICONTROL Match]** fält (markerat). Variabeldelen av resursnamnet som innehåller raden och kolumnen läggs till i **[!UICONTROL Row]** och **[!UICONTROL Column]** fält.

När snurruppsättningen överförs och publiceras aktiverar du namnet på det 2D-snurruppsättningsrecept som visas under **[!UICONTROL Batch Set Presets]** i **[!UICONTROL Upload Job Options]** -dialogrutan.

**Så här skapar du en gruppuppsättningsförinställning för automatisk generering av en 2D-snurpuppsättning:**

1. Öppna [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started)och logga sedan in på ditt konto.

   Dina autentiseringsuppgifter och inloggningsuppgifter tillhandahölls av Adobe vid tidpunkten för etableringen. Om du inte har den här informationen kontaktar du teknisk support.

1. Tryck på **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]** > **[!UICONTROL Batch Set Presets]** > **[!UICONTROL Batch Set Preset]**.

   [!UICONTROL View Form], enligt inställningen i det övre högra hörnet av [!UICONTROL Details] sida, är standardvy.

1. I **[!UICONTROL Preset List]** panel, tryck **[!UICONTROL Add]** för att aktivera definitionsfälten i **[!UICONTROL Details]** till höger på skärmen.
1. I **[!UICONTROL Details]** på panelen [!UICONTROL Preset Name] anger du ett namn för förinställningen.
1. I **[!UICONTROL Batch Set Type]** nedrullningsbar meny, välja **[!UICONTROL Asset Set]**.
1. I listrutan **[!UICONTROL Sub Type]** väljer du **[!UICONTROL Multi-Axis Spin Set]**.
1. Expandera **[!UICONTROL Asset Naming Conventions]** och sedan i **[!UICONTROL File Naming]** nedrullningsbar lista, knacka **[!UICONTROL Custom]**.
1. Använd attributen **[!UICONTROL Match]** och eventuellt **[!UICONTROL Base Name]** för att definiera ett reguljärt uttryck för namngivning av bildresurser som utgör grupperingen.

   Det reguljära uttrycket för literal Match kan till exempel se ut så här:

   `(w+)-w+-w+`

1. Expandera **[!UICONTROL Row Column Position]** och definierar sedan namnformatet för bildresursens position i 2D-rotationsmatrisen.

   Använd parentesen för att omsluta rad- eller kolumnpositionen i filnamnet.

   För en rad med ett reguljärt uttryck kan det se ut så här:

   `\w+-R([0-9]+)-\w+`

   eller

   `\w+-(\d+)-\w+`

   För det reguljära uttrycket i kolumnen kan det se ut så här:

   `\w+-\w+-C([0-9]+)`

   eller

   `\w+-\w+-C(\d+)`

   Kom ihåg att dessa uttryck bara är exempel för demonstrationssyften. Du kan skapa det reguljära uttrycket hur du vill.

   >[!NOTE]
   >
   >Om kombinationen av reguljära uttryck för rader och kolumner inte kan avgöra resursens position i den flerdimensionella rotationsuppsättningsarrayen, läggs resursen inte till i uppsättningen och ett fel loggas.

1. För **[!UICONTROL Set Naming]** och **[!UICONTROL Creation Convention]** anger du suffixet eller prefixet för basnamnet som du definierade i **[!UICONTROL Asset Naming Convention]**.

   Du kan också definiera var rotationsuppsättningen ska skapas i mappstrukturen för Dynamic Media Classic.

   Om du definierar ett stort antal uppsättningar ska du hålla dem åtskilda från de mappar som innehåller själva resurserna. Du kan till exempel skapa en mapp för snurruppsättningar där du kan placera genererade uppsättningar här.

1. I **[!UICONTROL Details]** panel, tryck **[!UICONTROL Save]**.
1. Tryck **[!UICONTROL Active]** bredvid den nya förinställningens namn.

   När du aktiverar förinställningen används den för att generera uppsättningen när du överför resurser till Dynamic Media.

### (Valfritt) Justera prestanda för Dynamic Media - Scene7-läge {#optional-tuning-the-performance-of-dynamic-media-scene-mode}

Adobe rekommenderar följande finjusteringstips för synkroniseringsprestanda/skalbarhet för att Dynamic Media - Scene7-läget ska fungera smidigt:

* Uppdaterar de fördefinierade jobbparametrarna för bearbetning av olika filformat.
* Uppdaterar de fördefinierade arbetstrådarna för Granite-arbetsflödet (videoresurser).
* Uppdaterar det fördefinierade tillfälliga Granite-arbetsflödet (bilder och icke-videomaterial) för köarbetstrådar.
* Uppdaterar de maximala överföringsanslutningarna till Dynamic Media Classic-servern.

#### Uppdatera de fördefinierade jobbparametrarna för bearbetning av olika filformat

Du kan justera jobbparametrar för snabbare bearbetning när du överför filer. Om du till exempel överför PSD-filer, men inte vill bearbeta dem som mallar, kan du ange att lagerextraheringen ska vara false (av). I så fall visas den justerade jobbparametern enligt följande: `process=None&createTemplate=false`.

Om du vill aktivera mallskapande använder du följande parametrar: `process=MaintainLayers&layerNaming=AppendName&createTemplate=true`.

<!-- REMOVED BASED ON CQDOC-17657 You can tune job parameters for faster processing when you upload files. For example, if you are uploading PSD files, but do not want to process them as templates, you can set layer extraction to false (off). In such case, the tuned job parameter would appear as `process=None&createTemplate=false`. -->

Adobe rekommenderar att du använder följande &quot;justerade&quot; jobbparametrar för PDF, PostScript® och PSD:

<!-- OLD PDF JOB PARAMETERS `pdfprocess=Rasterize&resolution=150&colorspace=Auto&pdfbrochure=false&keywords=false&links=false` -->

<!-- OLD POSTSCRIPT JOB PARAMETERS `psprocess=Rasterize&psresolution=150&pscolorspace=Auto&psalpha=false&psextractsearchwords=false&aiprocess=Rasterize&airesolution=150&aicolorspace=Auto&aialpha=false` -->

| Filtyp | Rekommenderade jobbparametrar |
| ---| ---|
| PDF | `pdfprocess=Thumbnail&resolution=150&colorspace=Auto&pdfbrochure=false&keywords=false&links=false` |
| PostScript® | `psprocess=Rasterize&psresolution=150&pscolorspace=Auto&psalpha=false&psextractsearchwords=false&aiprocess=Thumbnail&airesolution=150&aicolorspace=Auto&aialpha=false` |
| PSD | `process=None&layerNaming=AppendName&anchor=Center&createTemplate=false&extractText=false&extendLayers=false` |

<!-- CQDOC-17657 for PSD entry in table above -->

Om du vill uppdatera någon av de här parametrarna följer du stegen i [Aktivera stöd för MIME-typbaserade resurser/Dynamic Media Classic överföringsjobbparametrar](/help/sites-administering/scene7.md#enabling-mime-type-based-assets-scene-upload-job-parameter-support).

#### Uppdaterar kön för Granska tillfälligt arbetsflöde {#updating-the-granite-transient-workflow-queue}

Kön för Bevilja övergång används för **[!UICONTROL DAM Update Asset]** arbetsflöde. I Dynamic Media används den för bildhantering.

**Så här uppdaterar du kön för Granska tillfälligt arbetsflöde:**

1. Navigera till [https://&lt;server>/system/console/configMgr](http://localhost:4502/system/console/configMgr) och söka efter **[!UICONTROL Queue: Granite Transient Workflow Queue]**.

   >[!NOTE]
   >
   >En textsökning är nödvändig i stället för en direkt URL eftersom OSGi PID genereras dynamiskt.

1. I **[!UICONTROL Maximum Parallel Jobs]** ändrar du talet till önskat värde.

   Du kan öka **[!UICONTROL Maximum Parallel Jobs]** för att ge adekvat stöd för överföring av stora mängder filer till Dynamic Media. Det exakta värdet beror på maskinvarukapaciteten. I vissa scenarier, t.ex. en inledande migrering eller en massöverföring som görs en gång, kan du använda ett stort värde. Tänk dock på att användning av ett stort värde (till exempel två gånger antalet kärnor) kan ha negativa effekter på andra samtidiga aktiviteter. Testa och justera värdet utifrån ditt specifika användningsfall.

<!--    By default, the maximum number of parallel jobs depends on the number of available CPU cores. For example, on a 4-core server, it assigns 2 worker threads. (A value between 0.0 and 1.0 is ratio based, or any numbers greater than 1 will assign the number of worker threads.)

   Adobe recommends that 32 **[!UICONTROL Maximum Parallel Jobs]** be configured to adequately support heavy upload of files to Dynamic Media Classic. -->

![chlimage_1](assets/chlimage_1.jpeg)

1. Tryck på **[!UICONTROL Save]**.

#### Uppdaterar kön för Granite-arbetsflöde {#updating-the-granite-workflow-queue}

Beviljad arbetsflödeskö används för icke-tillfälliga arbetsflöden. I Dynamic Media bearbetar man video med **[!UICONTROL Dynamic Media Encode Video]** arbetsflöde.

**Så här uppdaterar du arbetsflödeskön för Granite:**

1. Navigera till `https://<server>/system/console/configMgr` och söka efter **[!UICONTROL Queue: Granite Workflow Queue]**.

   >[!NOTE]
   >
   >En textsökning är nödvändig i stället för en direkt URL eftersom OSGi PID genereras dynamiskt.

1. I **[!UICONTROL Maximum Parallel Jobs]** ändrar du talet till önskat värde.

   Som standard beror det maximala antalet parallella jobb på antalet tillgängliga processorkärnor. På en server med fyra kärnor tilldelas till exempel två arbetstrådar. (Ett värde mellan 0,0 och 1,0 är kvotbaserat, eller ett tal större än ett tilldelar antalet arbetstrådar.)

   I de flesta fall räcker standardinställningen 0,5.

   ![chlimage_1-1](assets/chlimage_1-1.jpeg)

1. Tryck på **[!UICONTROL Save]**.

#### Uppdaterar Scene7 överföringsanslutning {#updating-the-scene-upload-connection}

Inställningen Scene7 Upload Connection synkroniserar Experience Manager Assets med Dynamic Media Classic-servrar.

**Så här uppdaterar du Scene7 överföringsanslutning:**

1. Navigera till `https://<server>/system/console/configMgr/com.day.cq.dam.scene7.impl.Scene7UploadServiceImpl`
1. I [!UICONTROL Number of connections] fält och/eller [!UICONTROL Active job timeout] ändrar du talet.

   The **[!UICONTROL Number of connections]** Inställningen styr det högsta tillåtna antalet HTTP-anslutningar för överföring från Experience Manager till Dynamic Media. vanligtvis räcker det fördefinierade värdet på tio anslutningar.

   The **[!UICONTROL Active job timeout]** inställningen avgör väntetiden för överförda Dynamic Media-resurser som ska publiceras på leveransservern. Det här värdet är som standard 2 100 sekunder eller 35 minuter.

   I de flesta fall räcker det med inställningen 2 100.

   ![chlimage_1-2](assets/chlimage_1-2.jpeg)

1. Tryck på **[!UICONTROL Save]**.

### (Valfritt) Filtrera resurser för replikering {#optional-filtering-assets-for-replication}

I distributioner som inte är från Dynamic Media replikerar du *alla* resurser (både bilder och video) från Experience Manager Author-miljön till Experience Manager Publish-noden. Det här arbetsflödet är nödvändigt eftersom publiceringsservrarna i Experience Manager också levererar resurserna.

I Dynamic Media-distributioner finns det dock inget behov av att replikera samma resurser till publiceringsnoderna i Experience Manager eftersom resurserna levereras via Cloud Servicen. Ett sådant&quot;hybridpubliceringsarbetsflöde&quot; undviker extra lagringskostnader och längre bearbetningstider för att replikera resurser. Annat innehåll, t.ex. webbplatssidor, fortsätter att hanteras från Experience Manager-publiceringsnoderna.

Med filtren kan du *exclude* resurser från att replikeras till publiceringsnoden Experience Manager.

#### Använda standardresursfilter för replikering {#using-default-asset-filters-for-replication}

Om du använder Dynamic Media för bildbehandling, video eller båda, kan du använda standardfiltren som finns i Adobe. Följande filter är aktiva som standard:

<table> 
 <tbody> 
  <tr> 
   <td> </td> 
   <td><strong>Filter</strong></td> 
   <td><strong>MimeterType</strong></td> 
   <td><strong>Återgivningar</strong></td> 
  </tr> 
  <tr> 
   <td>Dynamic Media Image Delivery</td> 
   <td><p>filterbilder</p> <p>filteruppsättningar</p> <p> </p> </td> 
   <td><p>Börjar med <strong>bild/</strong></p> <p>Innehåller <strong>program/</strong> och slutar med <strong>set</strong>.</p> </td> 
   <td>De färdiga filterbilderna (gäller för enstaka bildresurser, inklusive interaktiva bilder) och "filteruppsättningar" (gäller Spin Sets, Image Sets, Mixed Media Sets och Carousel Sets) kommer att 
    <ul> 
     <li>Uteslut den ursprungliga bilden och statiska bildåtergivningar från replikering.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Dynamic Media Video Delivery</td> 
   <td>filter-video</td> 
   <td>Börjar med <strong>video/</strong></td> 
   <td>"filter-video" som är klar att användas: 
    <ul> 
     <li>Undanta återgivningar av originalvideo och statiska miniatyrer från replikering.<br /> <br /> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Filter gäller för MIME-typer och kan inte vara sökvägsspecifika.

#### Anpassa resursfilter för replikering {#customizing-asset-filters-for-replication}

1. I Experience Manager trycker du på Experience Manager-logotypen för att komma åt den globala navigeringskonsolen och trycker på **[!UICONTROL Tools]** och navigera till **[!UICONTROL General]** > **[!UICONTROL CRXDE Lite]**.
1. I det vänstra mappträdet navigerar du till `/etc/replication/agents.author/publish/jcr:content/damRenditionFilters` för att granska filtren.

   ![chlimage_1-2](assets/chlimage_1-2.png)

1. Du definierar Mime-typen för filtret genom att leta reda på Mime-typen enligt följande:

   Expandera i den vänstra listen **[!UICONTROL content]** > **[!UICONTROL dam]** > **[!UICONTROL <`locate_your_asset`>]** > **[!UICONTROL jcr:content]** > **[!UICONTROL metadata]** och sedan i tabellen till höger letar du reda på **[!UICONTROL dc:format]**.

   Följande bild är ett exempel på en resurs sökväg till dc:format.

   ![chlimage_1-3](assets/chlimage_1-3.png)

   Observera att `dc:format` för tillgången `Fiji Red.jpg` är `image/jpeg`.

   Om du vill att det här filtret ska gälla för alla bilder, oavsett format, anger du värdet till `image/*` där `*` är ett reguljärt uttryck som används på alla bilder i alla format.

   Om du bara vill att filtret ska gälla för bilder av typen JPEG anger du värdet `image/jpeg`.

1. Definiera vilka renderingar du vill inkludera eller exkludera från replikering.

   Följande tecken kan användas för att filtrera replikering:

   <table> 
    <tbody> 
    <tr> 
    <td><strong>Tecken som ska användas</strong></td> 
    <td><strong>Så här filtrerar du resurser för replikering</strong></td> 
    </tr> 
    <tr> 
    <td>*</td> 
    <td>Jokertecken<br /> </td> 
    </tr> 
    <tr> 
    <td>+</td> 
    <td>Innehåller resurser för replikering.</td> 
    </tr> 
    <tr> 
    <td>-</td> 
    <td>Exkluderar resurser från replikering.</td> 
    </tr> 
    </tbody> 
   </table>

   Navigera till **content/dam/&lt;`locate your asset`>/jcr:content/renditions**.

   Följande grafik är ett exempel på en resurs återgivningar.

   ![chlimage_1-4](assets/chlimage_1-4.png)

   Om du bara vill replikera originalet skriver du `+original`.
