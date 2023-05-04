---
title: Integrera [!DNL Experience Manager] Resurser med Adobe InDesign Server
description: Integrera [!DNL Experience Manager] Resurser med InDesign Server.
contentOwner: AG
feature: Publishing
role: Admin
exl-id: d80562f7-071c-460a-9c68-65f48d36fbd9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1682'
ht-degree: 1%

---

# Integrera resurser med Adobe InDesign Server {#integrating-aem-assets-with-indesign-server}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets använder:

* En proxy som distribuerar inläsningen av vissa bearbetningsuppgifter. En proxy är en [!DNL Experience Manager] instans som kommunicerar med en proxyarbetare för att utföra en viss uppgift, och andra [!DNL Experience Manager] -instanser för att leverera resultaten.
* En proxyarbetare som definierar och hanterar en viss uppgift.

Dessa kan omfatta en mängd olika arbetsuppgifter. till exempel använda en Adobe InDesign Server för att bearbeta filer.

Så här överför du filer helt till [!DNL Experience Manager] Resurser som du har skapat med Adobe InDesign som proxy används. Detta använder en proxyarbetare för att kommunicera med Adobe InDesign Server, där [skript](https://www.adobe.com/devnet/indesign/documentation.html#idscripting) körs för att extrahera metadata och generera olika renderingar för [!DNL Experience Manager] Resurser. Proxyarbetaren möjliggör tvåvägskommunikation mellan InDesign Server och [!DNL Experience Manager] instanser i en molnkonfiguration.

>[!NOTE]
>
>Adobe InDesign finns som två produkter:
>
>* [InDesign](https://www.adobe.com/products/indesign.html)\
   >  På så sätt kan du designa sidlayouter för tryck och/eller digital distribution.
>
>* [InDesign Server](https://www.adobe.com/products/indesignserver.html)\
   >  Med den här motorn kan du programmatiskt skapa automatiserade dokument baserat på vad du har skapat med InDesign. Den fungerar som en tjänst som erbjuder ett gränssnitt till dess [ExtendScript](https://www.adobe.com/devnet/scripting.html) motor.\
   >  Skripten skrivs i ExtendScript och liknar JavaScript. Mer information om Adobe InDesign-skript finns i [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting).
>


## Hur extraheringen fungerar {#how-the-extraction-works}

InDesign Server kan integreras med [!DNL Experience Manager] Resurser så att filer som skapats med InDesign ( `.indd`) kan överföras, återgivningar genereras, *alla* media som extraherats (till exempel video) och sparats som resurser:

>[!NOTE]
>
>Tidigare versioner av [!DNL Experience Manager] kunde extrahera XMP och miniatyrbilden, nu kan alla media extraheras.

1. Ladda upp `.indd` fil till [!DNL Experience Manager] Resurser.
1. Ett ramverk skickar kommandoskript till InDesign Server via SOAP (Simple Object Access Protocol).

   Detta kommandoskript kommer att:

   * Hämta `.indd` -fil.
   * Kör InDesign Server-kommandon:

      * Strukturen, texten och eventuella mediefiler extraheras.
      * PDF och JPG genereras.
      * HTML och IDML-renderingar genereras.
   * Lägg tillbaka de resulterande filerna i [!DNL Experience Manager] Resurser.

   >[!NOTE]
   >
   >IDML är ett XML-baserat format som återger *allt* i filen InDesign. Det lagras som ett komprimerat paket med [Postnummer](https://www.techterms.com/definition/zip) komprimering.
   >
   >Se [Adobe InDesign Interchange Formats INX och IDML](https://www.peachpit.com/articles/article.aspx?p=1381880&amp;seqNum=8) för ytterligare information.

   >[!CAUTION]
   >
   >Om InDesign Server inte är installerat eller inte konfigurerat kan du ändå överföra en `.indd` till [!DNL Experience Manager]. De återgivningar som skapas begränsas dock till `png` och `jpeg`kommer du inte att kunna generera `html`, `idml` eller sidåtergivningarna.

1. Efter extraheringen och renderingen:

   * Strukturen replikeras till en `cq:Page` (typ av återgivning).
   * Den extraherade texten och filerna lagras i [!DNL Experience Manager] Resurser.
   * Alla återgivningar lagras i [!DNL Experience Manager] Tillgångar, i själva tillgången.

## Integrera InDesign Server med [!DNL Experience Manager] {#integrating-the-indesign-server-with-aem}

Integrera InDesign Server för användning med [!DNL Experience Manager] Resurser och efter att du har konfigurerat din proxy måste du:

1. [Installera InDesign Server](#installing-the-indesign-server).
1. Om det behövs, [konfigurera [!DNL Experience Manager] Arbetsflöde för resurser](#configuring-the-aem-assets-workflow).

   Detta är bara nödvändigt om standardvärdena inte passar för din instans.

1. Konfigurera en [proxyarbetare för InDesign Server](#configuring-the-proxy-worker-for-indesign-server).

### Installera InDesign Server {#installing-the-indesign-server}

Installera och starta InDesign Server för användning med [!DNL Experience Manager]:

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

### Konfigurera [!DNL Experience Manager] Arbetsflöde för resurser {#configuring-the-aem-assets-workflow}

[!DNL Experience Manager] Resurserna har ett förkonfigurerat arbetsflöde **DAM-uppdateringsresurs**, som har flera processsteg särskilt för InDesign:

* [Medieextrahering](#media-extraction)
* [Sidextrahering](#page-extraction)

Det här arbetsflödet är konfigurerat med standardvärden som kan anpassas för dina inställningar för de olika författarinstanserna (det här är ett standardarbetsflöde, så mer information finns under [Redigera ett arbetsflöde](/help/sites-developing/workflows-models.md#configuring-a-workflow-step)). Om du använder standardvärdena (inklusive SOAP-porten) behövs ingen konfiguration.

Efter installationen överför du InDesign-filer till [!DNL Experience Manager] Resurser (enligt någon av de vanliga metoderna) utlöser det arbetsflöde som krävs för att bearbeta resursen och förbereda de olika återgivningarna. Testa konfigurationen genom att överföra en `.indd` till [!DNL Experience Manager] Assets som bekräftar att du ser de olika renderingar som har skapats av IDS under `<*your_asset*>.indd/Renditions`

#### Medieextrahering {#media-extraction}

Det här steget styr extraheringen av media från `.indd` -fil.

Om du vill anpassa kan du redigera **[!UICONTROL Arguments]** -fliken i **[!UICONTROL Media Extraction]** steg.

![Medieextraheringsargument och skriptsökvägar](assets/media_extraction_arguments_scripts.png)

Medieextraheringsargument och skriptsökvägar

* **ExtendScript-bibliotek**: Detta är ett enkelt http get/post-metodbibliotek som krävs av de andra skripten.

* **Utöka skript**: Här kan du ange olika skriptkombinationer. Om du vill att dina egna skript ska köras på InDesign Server sparar du skripten på `/apps/settings/dam/indesign/scripts`.

   Mer information om skript i InDesign finns i [https://www.adobe.com/devnet/indesign/documentation.html#idscripting](https://www.adobe.com/devnet/indesign/documentation.html#idscripting).

>[!CAUTION]
>
>Ändra inte ExtendScript-biblioteket. Biblioteket innehåller de HTTP-funktioner som krävs för att kommunicera med Sling. Den här inställningen anger vilket bibliotek som ska skickas till Adobe InDesign Server för användning där.

The `ThumbnailExport.jsx` skript som körs i arbetsflödessteget för medieextrahering genererar en miniatyrrendering i JPG-format. Den här återgivningen används i arbetsflödessteget Bearbeta miniatyrbilder för att generera de statiska återgivningar som krävs av [!DNL Experience Manager].

Du kan konfigurera arbetsflödessteget Bearbeta miniatyrbilder för att generera statiska återgivningar i olika storlekar. Se till att du inte tar bort standardinställningarna eftersom de krävs av [!DNL Experience Manager] Resurser, användargränssnitt. Arbetsflödessteget Ta bort återgivning av bildförhandsvisning tar bort återgivningen av .jpg-miniatyrer eftersom den inte längre behövs.

#### Sidextrahering {#page-extraction}

Detta skapar en [!DNL Experience Manager] sida från de extraherade elementen. En extraheringshanterare används för att extrahera data från en återgivning (för närvarande HTML eller IDML). Dessa data används sedan för att skapa en sida med PageBuilder.

Om du vill anpassa kan du redigera **[!UICONTROL Arguments]** -fliken i **Sidextrahering** steg.

![chlimage_1-289](assets/chlimage_1-289.png)

* **Extraheringshanterare för sida**: Välj den hanterare som du vill använda i listrutan. En extraheringshanterare fungerar på en viss återgivning, som väljs av en relaterad `RenditionPicker` (se API:t för `ExtractionHandler`).
Som standard är Extraction Handler för IDML-export tillgänglig. Det är `IDML` återgivning genererad i MediaExtract-steget.

* **Sidnamn**: Ange det namn som du vill tilldela den resulterande sidan. Om det lämnas tomt är namnet&quot;page&quot; (eller ett derivat om&quot;page&quot; redan finns).

* **Sidrubrik**: Ange den titel som du vill tilldela den resulterande sidan.

* **Sidrotsökväg**: Sökvägen till rotplatsen för den resulterande sidan. Om den lämnas tom används den nod som innehåller resursens återgivningar.

* **Sidmall**: Den mall som ska användas när den resulterande sidan genereras.

* **Siddesign**: Den siddesign som ska användas när den resulterande sidan genereras.

### Konfigurera proxyarbetaren för InDesign Server {#configuring-the-proxy-worker-for-indesign-server}

>[!NOTE]
>
>Arbetaren finns på proxyinstansen.

1. Expandera i verktygskonsolen **[!UICONTROL Cloud Services Configurations]** i den vänstra rutan. Expandera **[!UICONTROL Cloud Proxy Configuration]**.

1. Dubbelklicka på **[!UICONTROL IDS worker]** för att öppna för konfiguration.

1. Klicka **[!UICONTROL Edit]** för att öppna konfigurationsdialogrutan och definiera de nödvändiga inställningarna:

   ![proxy_idsworkerconfig](assets/proxy_idsworkerconfig.png)

   * **IDS-pool**: SOAP-slutpunkterna som ska användas för kommunikation med InDesign Server. Du kan lägga till, ta bort och beställa objekt.

1. Klicka **[!UICONTROL OK]** att spara.

### Configuring Day CQ Link Externalizer {#configuring-day-cq-link-externalizer}

Om InDesign Server och [!DNL Experience Manager] finns på olika värdar eller ett eller båda av dessa program fungerar inte på standardportar, konfigurera **Day CQ Link Externalizer** för att ange värdnamn, port och innehållssökväg för InDesign Server.

1. Öppna Configuration Manager på URL:en `https://[AEM_server]:[port]/system/console/configMgr`.
1. Leta reda på konfigurationen **[!UICONTROL Day CQ Link Externalizer]**. Klicka **[!UICONTROL Edit]** att öppna.
1. Inställningarna för länkutjämnaren hjälper dig att skapa absoluta URL:er för [!DNL Experience Manager] driftsättning och [!DNL InDesign Server]. Använd **[!UICONTROL Domains]** fält för att ange värdnamnet och kontextsökvägen för [!DNL Adobe InDesign Server]. Följ instruktionerna på skärmen. Klicka på **[!UICONTROL Save]**.

   ![Inställningar för extern länkning](assets/link-externalizer-config.png)

### Aktivera parallell jobbbearbetning för InDesign Server {#enabling-parallel-job-processing-for-indesign-server}

Nu kan du aktivera parallell jobbbearbetning för IDS.

Först måste du bestämma det maximala antalet parallella jobb ( `x`) kan InDesign Server bearbeta

* På en enda multiprocessordator är det maximala antalet parallella jobb (x) som en InDesign Server kan bearbeta ett mindre än antalet processorer som kör IDS.
* När du kör IDS på flera datorer måste du räkna antalet tillgängliga processorer (t.ex. på alla datorer) och sedan subtrahera det totala antalet datorer.

Så här konfigurerar du antalet parallella IDS-jobb:

1. Öppna **[!UICONTROL Configurations]** fliken i Felix Console, till exempel:

   `http://localhost:4502/system/console/configMgr`

1. Välj IDS-bearbetningskön under:

   `Apache Sling Job Queue Configuration`

1. Uppsättning:

   * **[!UICONTROL Type]** - `Parallel`
   * **[!UICONTROL Maximum Parallel Jobs]** - `<*x*>` (enligt beräkning ovan)

1. Spara dessa ändringar.
1. Om du vill aktivera stöd för flera sessioner för Adobe CS6 och senare ska du kontrollera `enable.multisession.name` kryssruta under `com.day.cq.dam.ids.impl.IDSJobProcessor.name configuration`.
1. Skapa en [pool med &lt; `*x*>` IDS-arbetare genom att lägga till SOAP-slutpunkter i IDS Worker-konfigurationen](#configuring-the-proxy-worker-for-indesign-server).

   Om det finns flera datorer som kör InDesign Server lägger du till SOAP-slutpunkter (antal processorer per dator -1) för varje dator.

   >[!NOTE]
   >
   >När du arbetar med en grupp arbetare kan du aktivera blockeringslista för IDS-arbetare.
   >
   >Om du vill göra det aktiverar du kryssrutan&quot;enable.retry.name&quot; under `com.day.cq.dam.ids.impl.IDSJobProcessor.name` konfiguration, vilket möjliggör omprövningar av IDS-jobb.
   >
   >Under `com.day.cq.dam.ids.impl.IDSPoolImpl.name` konfiguration, ange ett positivt värde för `max.errors.to.blacklist` parameter som bestämmer antalet jobbomprövningar innan ett ID tas bort från jobbarbetslistan
   >
   >Som standard, efter den konfigurerbara`retry.interval.to.whitelist.name`) tid i minuter som IDS-arbetaren valideras. Om arbetaren hittas online tas den bort från blockeringslista.

<!-- TBD: Make updates to configurations for allow and block list after product updates are done. See CQ-4298427.
-->

## Aktivera stöd för Adobe InDesign server 10.0 eller senare {#enabling-support-for-indesign-server-or-higher}

För InDesign server 10.0 eller senare utför du följande steg för att aktivera stöd för flera sessioner.

1. Öppna Configuration Manager från din [!DNL Assets] instance `https://[aem_server]:[port]/system/console/configMgr`.
1. Redigera konfigurationen `com.day.cq.dam.ids.impl.IDSJobProcessor.name`.
1. Välj **[!UICONTROL ids.cc.enable]** och klicka **[!UICONTROL Save]**.

>[!NOTE]
>
>För [!DNL InDesign Server] integrering med [!DNL Assets]använder du en flerkärnig processor eftersom den sessionsstödfunktion som krävs för integreringen inte stöds på enskilda kärnsystem.

## Konfigurera autentiseringsuppgifter för Experience Manager {#configure-aem-credentials}

Du kan ändra administratörsinloggningarna (användarnamn och lösenord) för att komma åt InDesign-servern från din [!DNL Experience Manager] utan att integreringen med Adobe InDesign-servern bryts.

1. Gå till `/etc/cloudservices/proxy.html`.
1. Ange det nya användarnamnet och lösenordet i dialogrutan.
1. Spara inloggningsuppgifterna.
