---
title: Aktivera resursinsikter via DTM
description: Lär dig hur du använder Adobe Dynamic Tag Management (DTM) för att aktivera Assets Insights.
contentOwner: AG
feature: Asset Insights,Asset Reports
role: User,Admin
exl-id: d19cea4d-5395-479d-b303-4529ae2c0bf2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 1%

---

# Aktivera resursinsikter via DTM {#enabling-asset-insights-through-dtm}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Dynamic Tag Management är ett verktyg som aktiverar era verktyg för digital marknadsföring. Det tillhandahålls kostnadsfritt till Adobe Analytics-kunder. Du kan antingen anpassa din spårningskod för att aktivera CMS-lösningar från tredje part för att använda Assets Insights eller så kan du använda DTM för att infoga Assets Insights-taggar. Insikter stöds endast och tillhandahålls för bilder.

>[!CAUTION]
>
>Adobe DTM är ersatt med [!DNL Adobe Experience Platform] och kommer snart att nå [livstid](https://medium.com/launch-by-adobe/dtm-plans-for-a-sunset-3c6aab003a6f). Adobe rekommenderar att du [use [!DNL Adobe Experience Platform] för resursinsikter](https://experienceleague.adobe.com/docs/experience-manager-learn/assets/advanced/asset-insights-launch-tutorial.html).

Utför dessa steg för att aktivera Assets Insights via DTM:

1. Tryck/klicka på [!DNL Experience Manager] logotyp och gå till **[!UICONTROL Tools]** > **[!UICONTROL Assets]** > **[!UICONTROL Insights Configuration]**.
1. [Konfigurera [!DNL Experience Manager] instans med DTM-Cloud Service](../sites-administering/dtm.md)

   API-token bör vara tillgänglig när du loggar in på [https://dtm.adobe.com](https://dtm.adobe.com/) och besök **[!UICONTROL Account Settings]** från profilikonen. Detta steg är inte nödvändigt från Assets Insights-synpunkt eftersom integreringen av [!DNL Experience Manager Sites] med Assets Insights är fortfarande på gång.

1. Logga in på [https://dtm.adobe.com](https://dtm.adobe.com/)och välj ett företag.
1. Skapa/öppna en befintlig webbegenskap

   * Välj **[!UICONTROL Web Properties]** och sedan trycka/klicka **[!UICONTROL Add Property]**.
   * Uppdatera fälten efter behov och tryck/klicka **[!UICONTROL Create Property]** (se [dokumentation](https://helpx.adobe.com/experience-manager/using/dtm.html)).

   ![chlimage_1-193](assets/chlimage_1-193.png)

1. I **[!UICONTROL Rules]** flik, välja **[!UICONTROL Page Load Rules]** i navigeringsrutan och tryck/klicka **[!UICONTROL Create New Rule]**.

   ![chlimage_1-194](assets/chlimage_1-194.png)

1. Expandera **[!UICONTROL Javascript /Third Party Tags]**. Tryck sedan på/klicka **[!UICONTROL Add New Script]** i **[!UICONTROL Sequential HTML]** för att öppna skriptdialogrutan.

   ![chlimage_1-195](assets/chlimage_1-195.png)

1. Tryck/klicka på [!DNL Experience Manager] logotyp och gå till **[!UICONTROL Tools > Assets]**.
1. Tryck/klicka **[!UICONTROL Insights Page Tracker]** kopierar du spårningskoden och klistrar sedan in den i skriptdialogrutan som du öppnade i steg 6. Spara ändringarna.

   >[!NOTE]
   >
   >* `AppMeasurement.js` har tagits bort. Den förväntas bli tillgänglig via DTM:s Adobe Analytics-verktyg.
   >* Samtalet till `assetAnalytics.dispatcher.init()` tas bort. Funktionen förväntas anropas när inläsningen av DTM:s Adobe Analytics-verktyg är klar.
   >* Beroende på var Assets Insights Page Tracker finns (till exempel AEM, CDN och så vidare) kan skriptkällans ursprung kräva ändringar.
   >* För AEM sidspåraren ska källan peka på en publiceringsinstans med hjälp av värdnamnet för dispatcher-instansen.


1. Öppna [https://dtm.adobe.com](https://dtm.adobe.com). Klicka på Översikt i webbegenskapen och klicka på Lägg till verktyg eller öppna ett befintligt Adobe Analytics-verktyg. När du skapar verktyget kan du ställa in konfigurationsmetoden till Automatisk.

   ![chlimage_1-196](assets/chlimage_1-196.png)

   Välj rapportsviter för mellanlagring/produktion efter behov.

1. Expandera **[!UICONTROL Library Management]** och se till att **[!UICONTROL Load Library at]** är inställd på **[!UICONTROL Page Top]**.

   ![chlimage_1-197](assets/chlimage_1-197.png)

1. Expandera **[!UICONTROL Customize Page Code]** och klicka eller peka **[!UICONTROL Open Editor]**.

   ![chlimage_1-198](assets/chlimage_1-198.png)

1. Klistra in följande kod i fönstret:

   ```java
   var sObj;
   
   if (arguments.length > 0) {
     sObj = arguments[0];
   } else {
     sObj = _satellite.getToolsByType('sc')[0].getS();
   }
   _satellite.notify('in assetAnalytics customInit');
   (function initializeAssetAnalytics() {
     if ((!!window.assetAnalytics) && (!!assetAnalytics.dispatcher)) {
       _satellite.notify('assetAnalytics ready');
       /** NOTE:
           Copy over the call to 'assetAnalytics.dispatcher.init()' from Assets Pagetracker
           Be mindful about changing the AppMeasurement object as retrieved above.
       */
       assetAnalytics.dispatcher.init(
             "",  /** RSID to send tracking-call to */
             "",  /** Tracking Server to send tracking-call to */
             "",  /** Visitor Namespace to send tracking-call to */
             "",  /** listVar to put comma-separated-list of Asset IDs for Asset Impression Events in tracking-call, e.g. 'listVar1' */
             "",  /** eVar to put Asset ID for Asset Click Events in, e.g. 'eVar3' */
             "",  /** event to include in tracking-calls for Asset Impression Events, e.g. 'event8' */
             "",  /** event to include in tracking-calls for Asset Click Events, e.g. 'event7' */
             sObj  /** [OPTIONAL] if the webpage already has an AppMeasurement object, please include the object here. If unspecified, Pagetracker Core shall create its own AppMeasurement object */
             );
       sObj.usePlugins = true;
       sObj.doPlugins = assetAnalytics.core.updateContextData;
       assetAnalytics.core.optimizedAssetInsights();
     }
     else {
       _satellite.notify('assetAnalytics not available. Consider updating the Custom Page Code', 4);
     }
   })();
   ```

   * Sidinläsningsregeln i DTM inkluderar bara koden pagetracker.js. Alla `assetAnalytics` -fält betraktas som åsidosättningar för standardvärden. De är inte obligatoriska som standard.
   * Kodanrop `assetAnalytics.dispatcher.init()` efter att ha kontrollerat att `_satellite.getToolsByType('sc')[0].getS()` initieras och `assetAnalytics,dispatcher.init` är tillgängligt. Du kan därför hoppa över att lägga till den i steg 11.
   * Enligt kommentarerna i Insights Page Tracker-koden (**[!UICONTROL Tools > Assets > Insights Page Tracker]**), när sidspåraren inte skapar en `AppMeasurement` är de tre första argumenten (RSID, Tracking Server och Visitor Namespace) irrelevanta. Tomma strängar skickas i stället för att markera detta.

      De återstående argumenten motsvarar konfigurationen på sidan Insights Configuration (**[!UICONTROL Tools > Assets > Insights Configuration]**).

   * AppMeasurement-objektet hämtas genom en fråga `satelliteLib` för alla tillgängliga SiteCatalyst-motorer. Om flera taggar har konfigurerats ändrar du indexvärdet för arrayväljaren på rätt sätt. Posterna i arrayen ordnas enligt de SiteCatalyst-verktyg som finns i DTM-gränssnittet.

1. Spara och stäng fönstret Kodredigeraren och spara sedan ändringarna i verktygskonfigurationen.
1. I **[!UICONTROL Approvals]** godkänner du båda väntande godkännanden. DTM-taggen kan infogas på webbsidan. Mer information om hur du infogar DTM-taggar på webbsidor finns på den arkiverade sidan om [integrera DTM i anpassade sidmallar](https://web.archive.org/web/20180816221834/https://blogs.adobe.com/experiencedelivers/experience-management/integrating-dtm-custom-aem6-page-template).
