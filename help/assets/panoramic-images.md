---
title: Panoramabilder
description: Lär dig hur du arbetar med panoramabilder i Dynamic Media.
contentOwner: Rick Brough
topic-tags: dynamic-media
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
exl-id: 51150d51-865e-4b8e-9990-ca755e4c7778
feature: Panoramic Images
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 2%

---

# Panoramabilder {#panoramic-images}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

I det här avsnittet beskrivs hur du arbetar med visningsprogrammet för panoramabilder för att återge sfäriska panoramabilder så att du får en totalupplevelse på 360° i ett rum, en egenskap, en plats eller ett landskap.

Se även [Hantera visningsförinställningar](managing-viewer-presets.md).

![panoramic-image2](assets/panoramic-image2.png)

## Överföra resurser som ska användas med panoramabildsvisningsprogrammet {#uploading-assets-for-use-with-the-panoramic-image-viewer}

För att en överförd resurs ska kvalificeras som en sfärisk panoramabild som du tänker använda med panoramabildsvisningsprogrammet måste resursen ha antingen ett eller båda av följande:

* Proportionerna 2.

   Du kan åsidosätta standardinställningen för proportioner på 2 tum **[!UICONTROL CRXDE Lite]** på följande sätt:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content`

* Taggad med nyckelorden `equirectangular`, eller `spherical`och `panorama`, eller `spherical` och `panoramic`. Se [Använda taggar](/help/sites-authoring/tags.md).

Både proportioner och nyckelordskriterier gäller för panoramaresurser för sidan med resursinformation och för **[!UICONTROL Panoramic Media]** -komponenten.

Information om hur du överför resurser som ska användas med visningsprogrammet för panoramabilder finns i [Överför resurser](managing-assets-touch-ui.md#uploading-assets).

## Konfigurera Dynamic Media Classic {#configuring-dynamic-media-classic-scene}

För att visningsprogrammet för panoramabilder ska fungera på rätt sätt i AEM måste du synkronisera förinställningarna för visningsprogrammet för panoramabilder med Dynamic Media Classic- och Dynamic Media Classic-specifika metadata så att visningsprogrammets förinställningar uppdateras i JCR-filen. Konfigurera Dynamic Media Classic på följande sätt för att uppnå detta:

1. [Logga in på ditt Dynamic Media Classic-program](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/intro/dynamic-media-classic-desktop-app.html#system-requirements-dmc-app) för varje företagskonto.

1. Klicka på **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]** i det övre högra hörnet på sidan.
1. På **[!UICONTROL Image Server Publish]** sida, från **[!UICONTROL Publish Context]** nedrullningsbar meny nära överkanten, välj **[!UICONTROL Image Serving]**.

1. På samma sätt **[!UICONTROL Image Server Publish]** sida, hitta rubriken **[!UICONTROL Request Attributes]**.
1. Under **[!UICONTROL Request Attributes]** rubrik, hitta **[!UICONTROL Reply Image Size Limit]**. I den associerade **[!UICONTROL Width]** och **[!UICONTROL Height]** i ökar du den största tillåtna bildstorleken för panoramabilder.

   Dynamic Media Classic har en begränsning på 25 000 000 pixlar. Den största tillåtna storleken för bilder med 2:1-proportioner är 7 000 x 3 500. För vanliga skärmar räcker det dock med 4 096 x 2 048 pixlar.

   >[!NOTE]
   >
   >Endast bilder som ligger inom den största tillåtna bildstorleken stöds. Begäran om bilder som är större än storleksgränsen resulterar i ett 403-svar.

1. Under **[Attribut för begäran]** gör du så här:

   * Ange **[!UICONTROL Request Obfuscation Mode]** till **[!UICONTROL Disabled]**.
   * Ange **[!UICONTROL Request Locking Mode]** till **[!UICONTROL Disabled]**.

   Dessa inställningar är nödvändiga för att du ska kunna använda **[!UICONTROL Panoramic Media]** i AEM.

1. Längst ned på **[!UICONTROL Image Server Publish]** till vänster trycker du på **[!UICONTROL Save]**.

1. Tryck på i det nedre högra hörnet **[!UICONTROL Close]**.

### Felsöka komponenten Panoramabildmedia {#troubleshooting-the-panoramic-media-wcm-component}

Om du har släppt en bild i **[!UICONTROL Panoramic Media]** -komponenten i WCM och komponentplatshållaren är komprimerade kan du felsöka följande:

* Om du får ett otillåtet fel 403 kan det bero på att den begärda bildstorleken är för stor. Granska *Storleksgräns för svarsbild* inställningar i [Konfigurera Dynamic Media Classic](#configuring-dynamic-media-classic-scene).

* För *Ogiltigt lås* på tillgången eller *Analysfel* visas på sidan, kontrollera **[!UICONTROL Request Obfuscation Mode]** och **[!UICONTROL Request Locking Mode]** för att säkerställa att de är inaktiverade.
* För ett fel på arbetsytan med färgton skapar du en **[!UICONTROL Rule Set Definition File Path and Invalidate CTN]** för tidigare begäranden om bildresursen.
* Om bildkvaliteten blir mycket låg efter en bildbegäran med en storlek som överskrider den gräns som stöds, kontrollerar du att **[!UICONTROL JPEG Encoding Attributes > Quality]** inställningen är inte tom. En typisk inställning för **[!UICONTROL Quality]** fältet är `95`. Du hittar inställningarna på **[!UICONTROL Image Server Publish]** sida. Information om hur du kommer åt sidan finns i [Konfigurera Dynamic Media Classic](#configuring-dynamic-media-classic-scene).

## Förhandsgranska panoramabilder {#previewing-panoramic-images}

Se [Förhandsgranska resurser](previewing-assets.md).

## Publicera panoramabilder {#publishing-panoramic-images}

Se [Publicera resurser](publishing-dynamicmedia-assets.md).
