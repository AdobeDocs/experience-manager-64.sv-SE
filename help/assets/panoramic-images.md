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

---


# Panoramabilder {#panoramic-images}

I det här avsnittet beskrivs hur du arbetar med visningsprogrammet för panoramabilder för att återge sfäriska panoramabilder så att du får en totalupplevelse på 360° i ett rum, en egenskap, en plats eller ett landskap.

Se även [Hantera visningsförinställningar](managing-viewer-presets.md).

![panoramic-image2](assets/panoramic-image2.png)

## Överföra resurser som ska användas med panoramabildsvisningsprogrammet {#uploading-assets-for-use-with-the-panoramic-image-viewer}

För att en överförd resurs ska kvalificeras som en sfärisk panoramabild som du tänker använda med panoramabildsvisningsprogrammet måste resursen ha antingen ett eller båda av följande:

* Proportionerna 2.

   Du kan åsidosätta standardinställningen för proportioner på 2 i **[!UICONTROL CRXDE Lite]** enligt följande:

   `/conf/global/settings/cloudconfigs/dmscene7/jcr:content`

* Taggad med nyckelorden `equirectangular`, eller `spherical`och `panorama`, eller `spherical` och `panoramic`. Se [Använda taggar](/help/sites-authoring/tags.md).

Både proportioner och nyckelordskriterier gäller för panoramaresurser för sidan med resursinformation och för komponenten **[!UICONTROL Panoramabildmedia]** .

Information om hur du överför resurser som ska användas med panoramabildsvisningsprogrammet finns i [Överföra resurser](managing-assets-touch-ui.md#uploading-assets).

## Konfigurera Dynamic Media Classic {#configuring-dynamic-media-classic-scene}

För att visningsprogrammet för panoramabilder ska fungera på rätt sätt i AEM måste du synkronisera förinställningarna för visningsprogrammet för panoramabilder med metadata som är specifika för Dynamic Media Classic och Dynamic Media Classic, så att visningsförinställningarna uppdateras i JCR. Konfigurera Dynamic Media Classic på följande sätt:

1. [Logga in i din instans av Dynamic Media Classic](https://www.adobe.com/marketing-cloud/experience-manager/scene7-login.html) för varje företagskonto.

1. I det övre högra hörnet av sidan klickar du på **[!UICONTROL Konfigurera > Programinställningar > Publiceringsinställningar > Bildserver]**.
1. På **[!UICONTROL Image Server Publish]** -sidan väljer du **[!UICONTROL Image Serving]** i listrutan **[!UICONTROL Publish Context]**(Publiceringskontext) längst upp.

1. På samma **[!UICONTROL Image Server Publish]** -sida hittar du rubriken **[!UICONTROL Request Attributes]**.
1. Under rubriken **[!UICONTROL Attribut]** för begäran går du till Storleksgräns för **[!UICONTROL svarsbild]**. I de associerade fälten **[!UICONTROL Bredd]** och **[!UICONTROL Höjd]** ökar du den största tillåtna bildstorleken för panoramabilder.

   Dynamic Media Classic har en begränsning på 25 000 000 pixlar. Den största tillåtna storleken för bilder med 2:1-proportioner är 7 000 x 3 500. För vanliga skärmar räcker det dock med 4 096 x 2 048 pixlar.

   >[!NOTE]
   >
   >Endast bilder som ligger inom den största tillåtna bildstorleken stöds. Begäran om bilder som är större än storleksgränsen resulterar i ett 403-svar.

1. Gör följande under **Request Attributes]** :

   * Ställ in **[!UICONTROL begäranobfuktningsläget]** till **[!UICONTROL Inaktiverat]**.
   * Ange **[!UICONTROL låsläge]** för begäran till **[!UICONTROL Inaktiverat]**.
   De här inställningarna är nödvändiga för att använda **[!UICONTROL panoramamediekomponenten]** i AEM.

1. Längst ned på **[!UICONTROL Image Server Publish]** -sidan trycker du på **[!UICONTROL Save]**.

1. Tryck på **[!UICONTROL Stäng]** i det nedre högra hörnet.

### Felsöka komponenten Panoramabildmedia {#troubleshooting-the-panoramic-media-wcm-component}

Om du har släppt en bild i **[!UICONTROL panoramamediakomponenten]** i WCM och komponentens platshållare är komprimerade kan du felsöka följande:

* Om du får ett otillåtet fel 403 kan det bero på att den begärda bildstorleken är för stor. Granska inställningarna för *Reply Image Size* (Gräns för svarsbildstorlek) i [Configuring Dynamic Media Classic (Scene7)](#configuring-dynamic-media-classic-scene).

* Om det finns ett *ogiltigt lås* för resursen eller det *tolkningsfel* som visas på sidan kontrollerar du **[!UICONTROL läget]** för begäran om obfuktion och läget **[!UICONTROL för]** begäran om låsning för att se till att de är inaktiverade.
* Om det uppstår ett fel på arbetsytan för en målad arbetsyta skapar du en sökväg till en **[!UICONTROL regeluppsättningsdefinitionsfil och validerar CTN]** för föregående begäranden för bildresursen.
* Om bildkvaliteten blir mycket låg efter en bildbegäran med en storlek över den gräns som stöds, kontrollerar du att **[!UICONTROL JPEG-kodningsattribut > Kvalitet]** inte är tom. En typisk inställning för fältet **[!UICONTROL Kvalitet]** är `95`. Inställningen finns på **[!UICONTROL sidan Image Server Publish]** . Mer information om hur du öppnar sidan finns i [Konfigurera Dynamic Media Classic](#configuring-dynamic-media-classic-scene).

## Förhandsgranska panoramabilder {#previewing-panoramic-images}

Se [Förhandsgranska resurser](previewing-assets.md).

## Publicera panoramabilder {#publishing-panoramic-images}

Se [Publicera resurser](publishing-dynamicmedia-assets.md).
