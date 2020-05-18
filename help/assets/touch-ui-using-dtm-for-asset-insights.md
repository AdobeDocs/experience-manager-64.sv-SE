---
title: Aktivera tillgångsinsikter via DTM
description: Lär dig hur du använder Adobe Dynamic Tag Management (DTM) för att aktivera tillgångsinsikter.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0560d47dcffbf9b74a36ea00e118f8a176adafcd
workflow-type: tm+mt
source-wordcount: '574'
ht-degree: 3%

---


# Aktivera tillgångsinsikter via DTM {#enabling-asset-insights-through-dtm}

Adobe Dynamic Tag Management är ett verktyg som aktiverar era digitala marknadsföringsverktyg. Den tillhandahålls kostnadsfritt till Adobe Analytics-kunder.

Även om du kan anpassa din spårningskod så att CMS-lösningar från tredje part kan använda resursinsikter, rekommenderar Adobe att du använder DTM för att infoga resursinsikter-taggar.

Gör så här för att aktivera tillgångsinsikter via DTM:

1. Tryck/klicka på AEM-logotypen och gå till **[!UICONTROL Tools > Assets > Insights Configuration]**.
1. [Konfigurera AEM-instans med DTM Cloud-tjänsten](../sites-administering/dtm.md)

   API-token bör vara tillgänglig när du har loggat in på [https://dtm.adobe.com](https://dtm.adobe.com/) och går **[!UICONTROL Account Settings]** till Profilikonen. Detta steg är inte nödvändigt från tillgångsinsikter eftersom integrationen av AEM Sites med tillgångsinsikter fortfarande pågår.

1. Logga in på [https://dtm.adobe.com](https://dtm.adobe.com/)och välj ett företag.
1. Skapa/öppna en befintlig webbegenskap

   * Markera **[!UICONTROL Web Properties]** fliken och tryck/klicka sedan på **[!UICONTROL Add Property]**.
   * Uppdatera fälten efter behov och tryck/klicka **[!UICONTROL Create Property]** (se [dokumentationen](https://helpx.adobe.com/experience-manager/using/dtm.html)).
   ![chlimage_1-193](assets/chlimage_1-193.png)

1. På **[!UICONTROL Rules]** fliken väljer du **[!UICONTROL Page Load Rules]** i navigeringsrutan och trycker/klickar på **[!UICONTROL Create New Rule]**.

   ![chlimage_1-194](assets/chlimage_1-194.png)

1. Expandera **[!UICONTROL Javascript /Third Party Tags]**. Tryck/klicka sedan **[!UICONTROL Add New Script]** på **[!UICONTROL Sequential HTML]** fliken för att öppna skriptdialogrutan.

   ![chlimage_1-195](assets/chlimage_1-195.png)

1. Tryck/klicka på AEM-logotypen och gå till **[!UICONTROL Tools > Assets]**.
1. Tryck/klicka **[!UICONTROL Insights Page Tracker]**, kopiera spårningskoden och klistra sedan in den i skriptdialogrutan som du öppnade i steg 6. Spara ändringarna.

   >[!NOTE]
   >
   >* `AppMeasurement.js` har tagits bort. Den förväntas bli tillgänglig via DTM:s Adobe Analytics-verktyg.
   >* Anropet till `assetAnalytics.dispatcher.init()` tas bort. Funktionen förväntas anropas när inläsningen av DTM:s Adobe Analytics-verktyg är klar.
   >* Beroende på var sidspåraren för tillgångsinsikter finns (till exempel AEM, CDN och så vidare) kan skriptkällans ursprung kräva ändringar.
   >* För AEM-värdbaserad sidspårare ska källan peka på en publiceringsinstans med värdnamnet för dispatcher-instansen.



1. Öppna [https://dtm.adobe.com](https://dtm.adobe.com). Klicka på Översikt i webbegenskapen och klicka på Lägg till verktyg eller öppna ett befintligt Adobe Analytics-verktyg. När du skapar verktyget kan du ställa in konfigurationsmetoden till Automatisk.

   ![chlimage_1-196](assets/chlimage_1-196.png)

   Välj rapportsviter för mellanlagring/produktion efter behov.

1. Expandera **[!UICONTROL Library Management]** och kontrollera att **[!UICONTROL Load Library at]** är inställt på **[!UICONTROL Page Top]**.

   ![chlimage_1-197](assets/chlimage_1-197.png)

1. Expandera **[!UICONTROL Customize Page Code]** och klicka eller tryck **[!UICONTROL Open Editor]**.

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

   * Sidinläsningsregeln i DTM inkluderar bara koden pagetracker.js. Alla `assetAnalytics` fält betraktas som åsidosättningar för standardvärden. De är inte obligatoriska som standard.
   * Kodanropet `assetAnalytics.dispatcher.init()` efter att du har kontrollerat att `_satellite.getToolsByType('sc')[0].getS()` är initierad och `assetAnalytics,dispatcher.init` tillgänglig. Du kan därför hoppa över att lägga till den i steg 11.
   * Om sidspåraren inte skapar ett **[!UICONTROL Tools > Assets > Insights Page Tracker]** objekt är de första tre argumenten (RSID, Tracking Server och Visitor Namespace) irrelevanta, vilket anges i kommentarerna i koden för sidspåraren ( `AppMeasurement` ). Tomma strängar skickas i stället för att markera detta.

      De återstående argumenten motsvarar konfigurationen på sidan Insights Configuration (**[!UICONTROL Tools > Assets > Insights Configuration]**).

   * AppMeasurement-objektet hämtas genom att en fråga skickas `satelliteLib` till alla tillgängliga SiteCatalyst-motorer. Om flera taggar har konfigurerats ändrar du indexvärdet för arrayväljaren på rätt sätt. Posterna i arrayen ordnas enligt de SiteCatalyst-verktyg som finns i DTM-gränssnittet.

1. Spara och stäng fönstret Kodredigeraren och spara sedan ändringarna i verktygskonfigurationen.
1. Godkänn båda väntande godkännanden på **[!UICONTROL Approvals]** fliken. DTM-taggen kan infogas på webbsidan. Mer information om hur du infogar DTM-taggar på webbsidor finns i [Integrera DTM i anpassade sidmallar](https://blogs.adobe.com/experiencedelivers/experience-management/integrating-dtm-custom-aem6-page-template/).
