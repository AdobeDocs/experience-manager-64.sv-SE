---
title: Panoramabilder
seo-title: Panoramabilder
description: Lär dig hur du arbetar med panoramabilder i Dynamic Media.
seo-description: Lär dig hur du arbetar med panoramabilder i Dynamic Media.
uuid: dfd7a55c-7bcc-4d62-8c3a-a73726881103
contentOwner: Rick Brough
topic-tags: dynamic-media
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: fc285b25-2bce-493c-87bc-5f1a8a26eb42
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 2%

---


# Panoramabilder {#panoramic-images}

I det här avsnittet beskrivs hur du arbetar med visningsprogrammet för panoramabilder för att återge sfäriska panoramabilder så att du får en totalupplevelse på 360° i ett rum, en egenskap, en plats eller ett landskap.

Se även [Hantera visningsförinställningar](managing-viewer-presets.md).

![panoramic-image2](assets/panoramic-image2.png)

## Överföra resurser som ska användas med panoramabildsvisningsprogrammet {#uploading-assets-for-use-with-the-panoramic-image-viewer}

För att en överförd resurs ska kvalificeras som en sfärisk panoramabild som du tänker använda med panoramabildsvisningsprogrammet måste resursen ha antingen ett eller båda av följande:

* Proportionerna 2.

   Du kan åsidosätta standardinställningen för proportioner på 2 tum **[!UICONTROL CRXDE Lite]** enligt följande:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content`

* Taggad med nyckelorden `equirectangular`, eller `spherical`och `panorama`, eller `spherical` och `panoramic`. Se [Använda taggar](/help/sites-authoring/tags.md).

Both the aspect ratio and keyword criteria apply to panoramic assets for the asset details page and the **[!UICONTROL Panoramic Media]** component.

Information om hur du överför resurser som ska användas med panoramabildsvisningsprogrammet finns i [Överföra resurser](managing-assets-touch-ui.md#uploading-assets).

## Konfigurera Dynamic Media Classic {#configuring-dynamic-media-classic-scene}

För att visningsprogrammet för panoramabilder ska fungera på rätt sätt i AEM måste du synkronisera förinställningarna för visningsprogrammet för panoramabilder med metadata som är specifika för Dynamic Media Classic och Dynamic Media Classic, så att visningsförinställningarna uppdateras i JCR. Konfigurera Dynamic Media Classic på följande sätt:

1. [Logga in i din instans av Dynamic Media Classic](https://www.adobe.com/marketing-cloud/experience-manager/scene7-login.html) för varje företagskonto.

1. Klicka på **[!UICONTROL Setup > Application Setup > Publish Setup > Image Server]** i det övre högra hörnet på sidan.
1. På **[!UICONTROL Image Server Publish]** sidan väljer du **[!UICONTROL Publish Context]** i den **[!UICONTROL Image Serving]** nedrullningsbara menyn nära överkanten.

1. På samma **[!UICONTROL Image Server Publish]** sida hittar du rubriken **[!UICONTROL Request Attributes]**.
1. Under **[!UICONTROL Request Attributes]** rubriken, gå till **[!UICONTROL Reply Image Size Limit]**. I associerade **[!UICONTROL Width]** - och **[!UICONTROL Height]** -fält ökar du den största tillåtna bildstorleken för panoramabilder.

   Dynamic Media Classic har en begränsning på 25 000 000 pixlar. Den största tillåtna storleken för bilder med 2:1-proportioner är 7 000 x 3 500. För vanliga skärmar räcker det dock med 4 096 x 2 048 pixlar.

   >[!NOTE]
   >
   >Endast bilder som ligger inom den största tillåtna bildstorleken stöds. Begäran om bilder som är större än storleksgränsen resulterar i ett 403-svar.

1. Gör följande under **Request Attributes]** :

   * Ange **[!UICONTROL Request Obfuscation Mode]** till **[!UICONTROL Disabled]**.
   * Ange **[!UICONTROL Request Locking Mode]** till **[!UICONTROL Disabled]**.

   Dessa inställningar är nödvändiga för att du ska kunna använda **[!UICONTROL Panoramic Media]** komponenten i AEM.

1. Tryck på längst ned på **[!UICONTROL Image Server Publish]** sidan till vänster **[!UICONTROL Save]**.

1. Tryck på i det nedre högra hörnet **[!UICONTROL Close]**.

### Felsöka komponenten Panoramabildmedia {#troubleshooting-the-panoramic-media-wcm-component}

Om du har släppt en bild i **[!UICONTROL Panoramic Media]** komponenten i WCM och platshållaren för komponenten är komprimerad kanske du vill felsöka följande:

* Om du får ett otillåtet fel 403 kan det bero på att den begärda bildstorleken är för stor. Granska inställningarna för *Reply Image Size* (Gräns för svarsbildstorlek) i [Configuring Dynamic Media Classic (Scene7)](#configuring-dynamic-media-classic-scene).

* Om det finns ett *ogiltigt lås* på resursen eller ett *tolkningsfel* som visas på sidan kontrollerar **[!UICONTROL Request Obfuscation Mode]** och **[!UICONTROL Request Locking Mode]** kontrollerar du att de är inaktiverade.
* Om det är ett fel på arbetsytan med färgton ska du ställa in en **[!UICONTROL Rule Set Definition File Path and Invalidate CTN]** för föregående begäranden för bildresursen.
* Om bildkvaliteten blir mycket låg efter en bildbegäran med en storlek som ligger över den gräns som stöds, kontrollerar du att **[!UICONTROL JPEG Encoding Attributes > Quality]** inställningen inte är tom. En typisk inställning för **[!UICONTROL Quality]** fältet är `95`. Inställningen finns på **[!UICONTROL Image Server Publish]** sidan. Mer information om hur du öppnar sidan finns i [Konfigurera Dynamic Media Classic](#configuring-dynamic-media-classic-scene).

## Förhandsgranska panoramabilder {#previewing-panoramic-images}

Se [Förhandsgranska resurser](previewing-assets.md).

## Publicera panoramabilder {#publishing-panoramic-images}

Se [Publicera resurser](publishing-dynamicmedia-assets.md).
