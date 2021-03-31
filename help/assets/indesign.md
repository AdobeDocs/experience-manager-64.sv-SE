---
title: Integrera AEM Assets med Adobe InDesign Server
description: Lär dig hur du integrerar AEM Assets med InDesign Server.
contentOwner: AG
feature: Publicering
role: Administratör
translation-type: tm+mt
source-git-commit: 4acf159ae1b9923a9c93fa15faa38c7f4bc9f759
workflow-type: tm+mt
source-wordcount: '1676'
ht-degree: 1%

---


# Integrera AEM Assets med Adobe InDesign Server {#integrating-aem-assets-with-indesign-server}

Adobe Experience Manager (AEM) Assets använder:

* En proxy som distribuerar inläsningen av vissa bearbetningsuppgifter. En proxy är en AEM som kommunicerar med en proxyarbetare för att utföra en viss uppgift och andra AEM instanser för att leverera resultatet.
* En proxyarbetare som definierar och hanterar en viss uppgift.

Dessa kan omfatta en mängd olika arbetsuppgifter. till exempel använda en Adobe InDesign Server för att bearbeta filer.

För att överföra filer till AEM Assets som du har skapat med Adobe InDesign används en proxy. Detta använder en proxyarbetare för att kommunicera med Adobe InDesign Server, där [skript](https://www.adobe.com/devnet/indesign/documentation.html#idscripting) körs för att extrahera metadata och generera olika renderingar för AEM Assets. Proxyarbetaren möjliggör tvåvägskommunikation mellan InDesign Server och AEM i en molnkonfiguration.

>[!NOTE]
>
>Adobe InDesign finns som två produkter:
>
>* [InDesign](https://www.adobe.com/products/indesign.html)\
   >  På så sätt kan du designa sidlayouter för tryck och/eller digital distribution.
   >
   >
* [InDesign Server](https://www.adobe.com/products/indesignserver.html)\
   >  Med den här motorn kan du programmatiskt skapa automatiserade dokument baserat på vad du har skapat med InDesign. Den fungerar som en tjänst som erbjuder ett gränssnitt till sin [ExtendScript](https://www.adobe.com/devnet/scripting.html)-motor.\
   >  Skripten skrivs i ExtendScript, som liknar javascript. Mer information om InDesign-skript finns i [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting).

>



## Så här fungerar extraheringen {#how-the-extraction-works}

InDesign Server kan integreras med AEM Assets så att filer som skapats med InDesign ( `.indd`) kan överföras, återgivningar genereras, *alla*-media kan extraheras (till exempel video) och lagras som resurser:

>[!NOTE]
>
>Tidigare versioner av AEM kunde extrahera XMP och miniatyrbilden, nu kan alla media extraheras.

1. Överför din `.indd`-fil till AEM Assets.
1. Ett ramverk skickar kommandoskript till InDesign Server via SOAP (Simple Object Access Protocol).

   Detta kommandoskript kommer att:

   * Hämta filen `.indd`.
   * Kör InDesign Server-kommandon:

      * Strukturen, texten och eventuella mediefiler extraheras.
      * PDF- och JPG-renderingar genereras.
      * HTML- och IDML-renderingar genereras.
   * Lägg tillbaka de färdiga filerna på AEM Assets.

   >[!NOTE]
   >
   >IDML är ett XML-baserat format som återger *allt* i filen InDesign. Den lagras som ett komprimerat paket med [Zip](https://www.techterms.com/definition/zip)-komprimering.
   >
   >Mer information finns i [Adobe InDesign Interchange Formats INX och IDML](http://www.peachpit.com/articles/article.aspx?p=1381880&amp;seqNum=8).

   >[!CAUTION]
   >
   >Om InDesign Server inte är installerat eller inte konfigurerat kan du ändå överföra en `.indd`-fil till AEM. De återgivningar som skapas begränsas dock till `png` och `jpeg`, du kommer inte att kunna generera `html`, `idml` eller sidåtergivningarna.

1. Efter extraheringen och renderingen:

   * Strukturen replikeras till en `cq:Page` (typ av återgivning).
   * Den extraherade texten och filerna lagras i AEM Assets.
   * Alla återgivningar lagras i AEM Assets, i själva resursen.

## Integrera InDesign Server med AEM {#integrating-the-indesign-server-with-aem}

Om du vill integrera InDesign Server för användning med AEM Assets och efter att du har konfigurerat din proxy måste du:

1. [Installera InDesign Server](#installing-the-indesign-server).
1. [Konfigurera AEM Assets Workflow](#configuring-the-aem-assets-workflow) om det behövs.

   Detta är bara nödvändigt om standardvärdena inte passar för din instans.

1. Konfigurera en [proxyarbetare för InDesign Server](#configuring-the-proxy-worker-for-indesign-server).

### Installera InDesign Server {#installing-the-indesign-server}

Så här installerar och startar du InDesign Server för användning med AEM:

1. Hämta och installera Adobe InDesign Server.

   >[!NOTE]
   >
   >InDesign Server (CS6 och senare).

1. Om det behövs kan du anpassa konfigurationen för din InDesign Server-instans.

1. Starta servern från kommandoraden:

   `<*ids-installation-dir*>/InDesignServer.com -port 8080`

   Detta startar servern med SOAP-pluginprogrammet som lyssnar på port 8080. Alla loggmeddelanden och utdata skrivs direkt till kommandofönstret.

   >[!NOTE]
   >
   >Om du vill spara utdatameddelandena i en fil använder du omdirigering; under Windows:
   >
   >`<ids-installation-dir>/InDesignServer.com -port 8080 > ~/temp/INDD-logfile.txt 2>&1`

### Konfigurera AEM Assets Workflow {#configuring-the-aem-assets-workflow}

AEM Assets har ett förkonfigurerat arbetsflöde **DAM Update Asset**, som har flera processsteg speciellt för InDesign:

* [Medieextrahering](#media-extraction)
* [Sidextrahering](#page-extraction)

Det här arbetsflödet är konfigurerat med standardvärden som kan anpassas för konfigurationen för de olika författarinstanserna (det här är ett standardarbetsflöde, så mer information finns under [Redigera ett arbetsflöde](/help/sites-developing/workflows-models.md#configuring-a-workflow-step)). Om du använder standardvärdena (inklusive SOAP-porten) behövs ingen konfiguration.

Efter installationen utlöses det arbetsflöde som krävs för att bearbeta resursen och de olika återgivningarna när du överför InDesign-filer till AEM Assets (på något av de vanliga sätten). Testa konfigurationen genom att överföra en `.indd`-fil till AEM Assets för att bekräfta att du ser de olika återgivningar som skapas av IDS under `<*your_asset*>.indd/Renditions`

#### Medieextrahering {#media-extraction}

Det här steget styr extraheringen av media från `.indd`-filen.

Om du vill anpassa kan du redigera fliken **[!UICONTROL Arguments]** i **[!UICONTROL Media Extraction]**-steget.

![Medieextraheringsargument och skriptsökvägar](assets/media_extraction_arguments_scripts.png)

Medieextraheringsargument och skriptsökvägar

* **ExtendScript-bibliotek**: Detta är ett enkelt http get/post-metodbibliotek som krävs av de andra skripten.

* **Utöka skript**: Här kan du ange olika skriptkombinationer. Om du vill att dina egna skript ska köras på InDesign Server sparar du skripten på `/apps/settings/dam/indesign/scripts`.

   Mer information om InDesign-skript finns i [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting).

>[!CAUTION]
>
>Ändra inte ExtendScript-biblioteket. Biblioteket innehåller de HTTP-funktioner som krävs för att kommunicera med Sling. Den här inställningen anger vilket bibliotek som ska skickas till Adobe InDesign Server för användning där.

Skriptet `ThumbnailExport.jsx` som körs i arbetsflödessteget Medieextrahering genererar en miniatyrrendering i JPG-format. Den här återgivningen används i arbetsflödet Bearbeta miniatyrbilder för att generera de statiska återgivningar som AEM kräver.

Du kan konfigurera arbetsflödessteget Bearbeta miniatyrbilder för att generera statiska återgivningar i olika storlekar. Se till att du inte tar bort standardinställningarna eftersom de krävs av AEM Assets-gränssnittet. Arbetsflödessteget Ta bort återgivning av bildförhandsvisning tar bort återgivningen av .jpg-miniatyrer eftersom den inte längre behövs.

#### Sidextrahering {#page-extraction}

Då skapas en AEM sida av de extraherade elementen. En extraheringshanterare används för att extrahera data från en återgivning (för närvarande HTML eller IDML). Dessa data används sedan för att skapa en sida med PageBuilder.

Om du vill anpassa kan du redigera fliken **[!UICONTROL Arguments]** i steget **Sidextrahering**.

![chlimage_1-289](assets/chlimage_1-289.png)

* **Extraheringshanterare** för sida: Välj den hanterare som du vill använda i listrutan. En extraheringshanterare fungerar på en viss återgivning, som väljs av en relaterad `RenditionPicker` (se API:t för `ExtractionHandler`).
Som standard är Extraction Handler för IDML-export tillgänglig. Det fungerar på den `IDML`-rendering som genereras i MediaExtract-steget.

* **Sidnamn**: Ange det namn som du vill tilldela den resulterande sidan. Om det lämnas tomt är namnet&quot;page&quot; (eller ett derivat om&quot;page&quot; redan finns).

* **Sidrubrik**: Ange den titel som du vill tilldela den resulterande sidan.

* **Sidrotsökväg**: Sökvägen till rotplatsen för den resulterande sidan. Om den lämnas tom används den nod som innehåller resursens återgivningar.

* **Sidmall**: Den mall som ska användas när den resulterande sidan genereras.

* **Siddesign**: Den siddesign som ska användas när den resulterande sidan genereras.

### Konfigurera proxyarbetaren för InDesign Server {#configuring-the-proxy-worker-for-indesign-server}

>[!NOTE]
>
>Arbetaren finns på proxyinstansen.

1. Expandera **[!UICONTROL Cloud Services Configurations]** i den vänstra rutan i verktygskonsolen. Expandera sedan **[!UICONTROL Cloud Proxy Configuration]**.

1. Dubbelklicka på **[!UICONTROL IDS worker]** för att öppna konfigurationen.

1. Klicka på **[!UICONTROL Edit]** för att öppna konfigurationsdialogrutan och definiera de nödvändiga inställningarna:

   ![proxy_idsworkerconfig](assets/proxy_idsworkerconfig.png)

   * **IDS-pool**: SOAP-slutpunkterna som ska användas för kommunikation med InDesign Server. Du kan lägga till, ta bort och beställa objekt.

1. Klicka på **[!UICONTROL OK]** för att spara.

### Configuring Day CQ Link Externalizer {#configuring-day-cq-link-externalizer}

Om InDesign Server och AEM finns på olika värdar eller om ett eller båda av dessa program inte fungerar på standardportar konfigurerar du **Day CQ Link Externalizer** för att ange värdnamn, port och innehållssökväg för InDesign Server.

1. Öppna Configuration Manager på URL:en `https://[AEM_server]:[port]/system/console/configMgr`.
1. Leta reda på konfigurationen **[!UICONTROL Day CQ Link Externalizer]**. Klicka på **[!UICONTROL Edit]** för att öppna.
1. Med inställningarna för länkutjämnaren kan du skapa absoluta URL:er för [!DNL Experience Manager]-distributionen och för [!DNL InDesign Server]. Använd fältet **[!UICONTROL Domains]** för att ange värdnamnet och kontextsökvägen för [!DNL Adobe InDesign Server]. Följ instruktionerna på skärmen. Klicka på **[!UICONTROL Save]**.

   ![Inställningar för extern länkning](assets/link-externalizer-config.png)

### Aktivera parallell jobbbearbetning för InDesign Server {#enabling-parallel-job-processing-for-indesign-server}

Nu kan du aktivera parallell jobbbearbetning för IDS.

Först måste du fastställa det maximala antalet parallella jobb ( `x`) som InDesign Server kan bearbeta:

* På en enda multiprocessordator är det maximala antalet parallella jobb (x) som en InDesign Server kan bearbeta ett mindre än antalet processorer som kör IDS.
* När du kör IDS på flera datorer måste du räkna antalet tillgängliga processorer (t.ex. på alla datorer) och sedan subtrahera det totala antalet datorer.

Så här konfigurerar du antalet parallella IDS-jobb:

1. Öppna fliken **[!UICONTROL Configurations]** i Felix Console; till exempel:

   `http://localhost:4502/system/console/configMgr`

1. Välj IDS-bearbetningskön under:

   `Apache Sling Job Queue Configuration`

1. Uppsättning:

   * **[!UICONTROL Type]** - `Parallel`
   * **[!UICONTROL Maximum Parallel Jobs]** -  `<*x*>` (enligt beräkning ovan)

1. Spara dessa ändringar.
1. Om du vill aktivera stöd för flera sessioner för Adobe CS6 och senare markerar du kryssrutan `enable.multisession.name` under `com.day.cq.dam.ids.impl.IDSJobProcessor.name configuration`.
1. Skapa en [pool med &lt;`*x*>` IDS-arbetare genom att lägga till SOAP-slutpunkter i IDS Worker-konfigurationen](#configuring-the-proxy-worker-for-indesign-server).

   Om det finns flera datorer som kör InDesign Server lägger du till SOAP-slutpunkter (antal processorer per dator -1) för varje dator.

   >[!NOTE]
   >
   >När du arbetar med en grupp arbetare kan du aktivera blockeringslista för IDS-arbetare.
   >
   >Om du vill göra det aktiverar du kryssrutan&quot;enable.retry.name&quot;, under `com.day.cq.dam.ids.impl.IDSJobProcessor.name`-konfigurationen, som aktiverar omprövningar av IDS-jobb.
   >
   >Under konfigurationen `com.day.cq.dam.ids.impl.IDSPoolImpl.name` anger du dessutom ett positivt värde för parametern `max.errors.to.blacklist` som bestämmer antalet jobbomprövningar innan du tar bort ett ID från jobbarbetslistan
   >
   >Som standard valideras IDS-arbetaren efter den konfigurerbara tiden (`retry.interval.to.whitelist.name`) i minuter. Om arbetaren hittas online tas den bort från blockeringslista.

<!-- TBD: Make updates to configurations for allow and block list after product updates are done. See CQ-4298427.
-->

## Aktivera stöd för Adobe InDesign server 10.0 eller senare {#enabling-support-for-indesign-server-or-higher}

För InDesign server 10.0 eller senare utför du följande steg för att aktivera stöd för flera sessioner.

1. Öppna Configuration Manager från din [!DNL Assets]-instans `https://[aem_server]:[port]/system/console/configMgr`.
1. Redigera konfigurationen `com.day.cq.dam.ids.impl.IDSJobProcessor.name`.
1. Välj alternativet **[!UICONTROL ids.cc.enable]** och klicka på **[!UICONTROL Save]**.

>[!NOTE]
>
>För [!DNL InDesign Server]-integrering med [!DNL Assets] använder du en flerkärnig processor eftersom den sessionsstödfunktion som krävs för integreringen inte stöds på enkärniga system.

## Konfigurera autentiseringsuppgifter för Experience Manager {#configure-aem-credentials}

Du kan ändra administratörens standardautentiseringsuppgifter (användarnamn och lösenord) för att komma åt InDesign-servern från din AEM utan att integreringen med Adobe InDesign-servern avbryts.

1. Gå till `/etc/cloudservices/proxy.html`.
1. Ange det nya användarnamnet och lösenordet i dialogrutan.
1. Spara inloggningsuppgifterna.
