---
title: Panoramabilder
description: Lär dig hur du arbetar med panoramabilder i Dynamic Media.
contentOwner: Rick Brough
topic-tags: dynamic-media
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
exl-id: 51150d51-865e-4b8e-9990-ca755e4c7778
feature: Panoramabilder
role: Business Practitioner
translation-type: tm+mt
source-git-commit: 489a4b42bdd5895186ba885b9a1dc33b49427e8d
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 2%

---

# Panoramabilder {#panoramic-images}

I det här avsnittet beskrivs hur du arbetar med visningsprogrammet för panoramabilder för att återge sfäriska panoramabilder så att du får en totalupplevelse på 360° i ett rum, en egenskap, en plats eller ett landskap.

Se även [Hantera visningsförinställningar](managing-viewer-presets.md).

![panoramabild2](assets/panoramic-image2.png)

## Överföra resurser som ska användas med panoramabildsvisningsprogrammet {#uploading-assets-for-use-with-the-panoramic-image-viewer}

För att en överförd resurs ska kvalificeras som en sfärisk panoramabild som du tänker använda med panoramabildsvisningsprogrammet måste resursen ha antingen ett eller båda av följande:

* Proportionerna 2.

   Du kan åsidosätta standardinställningen för proportioner på 2 i **[!UICONTROL CRXDE Lite]** på följande sätt:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content`

* Taggad med nyckelorden `equirectangular`, `spherical`och `panorama`, eller `spherical` och `panoramic`. Se [Använda taggar](/help/sites-authoring/tags.md).

Både proportioner och nyckelordskriterier gäller för panoramaresurser för sidan med resursinformation och komponenten **[!UICONTROL Panoramic Media]**.

Information om hur du överför resurser som ska användas med visningsprogrammet för panoramabilder finns i [Överföra resurser](managing-assets-touch-ui.md#uploading-assets).

## Konfigurerar Dynamic Media Classic {#configuring-dynamic-media-classic-scene}

För att visningsprogrammet för panoramabilder ska fungera på rätt sätt i AEM måste du synkronisera förinställningarna för visningsprogrammet för panoramabilder med Dynamic Media Classic och Dynamic Media Classic-specifika metadata så att visningsförinställningarna uppdateras i JCR-filen. Konfigurera Dynamic Media Classic på följande sätt:

1. [Logga in på ditt Dynamic Media Classic-datorprogram ](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/intro/dynamic-media-classic-desktop-app.html?lang=en#system-requirements-dmc-app) för varje företagskonto.

1. Klicka på **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]** i det övre högra hörnet på sidan.
1. På sidan **[!UICONTROL Image Server Publish]** väljer du **[!UICONTROL Image Serving]** i listrutan **[!UICONTROL Publish Context]**.

1. På samma **[!UICONTROL Image Server Publish]**-sida hittar du rubriken **[!UICONTROL Request Attributes]**.
1. Gå till **[!UICONTROL Reply Image Size Limit]** under rubriken **[!UICONTROL Request Attributes]**. I de associerade fälten **[!UICONTROL Width]** och **[!UICONTROL Height]** ökar du den största tillåtna bildstorleken för panoramabilder.

   Dynamic Media Classic har en begränsning på 25 000 000 pixlar. Den största tillåtna storleken för bilder med 2:1-proportioner är 7 000 x 3 500. För vanliga skärmar räcker det dock med 4 096 x 2 048 pixlar.

   >[!NOTE]
   >
   >Endast bilder som ligger inom den största tillåtna bildstorleken stöds. Begäran om bilder som är större än storleksgränsen resulterar i ett 403-svar.

1. Gör följande under rubriken **[Begär attribut]**:

   * Ange **[!UICONTROL Request Obfuscation Mode]** till **[!UICONTROL Disabled]**.
   * Ange **[!UICONTROL Request Locking Mode]** till **[!UICONTROL Disabled]**.

   Dessa inställningar är nödvändiga för att du ska kunna använda komponenten **[!UICONTROL Panoramic Media]** i AEM.

1. Tryck på **[!UICONTROL Save]** längst ned på sidan **[!UICONTROL Image Server Publish]** till vänster.

1. Tryck på **[!UICONTROL Close]** i det nedre högra hörnet.

### Felsökning av komponenten Panoramabildmedia {#troubleshooting-the-panoramic-media-wcm-component}

Om du släppte en bild i **[!UICONTROL Panoramic Media]**-komponenten i WCM-filen och platshållaren för komponenten är komprimerad kan du felsöka följande:

* Om du får ett otillåtet fel 403 kan det bero på att den begärda bildstorleken är för stor. Granska *Reply Image Size Limit*-inställningarna i [Configuring Dynamic Media Classic](#configuring-dynamic-media-classic-scene).

* Om du vill ha ett *ogiltigt lås* för resursen eller *tolkningsfel* som visas på sidan kontrollerar du att **[!UICONTROL Request Obfuscation Mode]** och **[!UICONTROL Request Locking Mode]** är inaktiverade.
* Om det är ett fel på arbetsytan med färgton ska du ställa in en **[!UICONTROL Rule Set Definition File Path and Invalidate CTN]** för föregående begäranden för bildresursen.
* Om bildkvaliteten blir mycket låg efter en bildbegäran med en storlek över den gräns som stöds, kontrollerar du att inställningen **[!UICONTROL JPEG Encoding Attributes > Quality]** inte är tom. En typisk inställning för fältet **[!UICONTROL Quality]** är `95`. Du hittar inställningen på sidan **[!UICONTROL Image Server Publish]**. Mer information finns i [Konfigurera Dynamic Media Classic](#configuring-dynamic-media-classic-scene).

## Förhandsgranska panoramabilder {#previewing-panoramic-images}

Se [Förhandsgranska resurser](previewing-assets.md).

## Publicerar panoramabilder {#publishing-panoramic-images}

Se [Publicera resurser](publishing-dynamicmedia-assets.md).
