---
title: Camera Raw stöd
description: Lär dig hur du aktiverar Camera Raw support i Adobe Experience Manager Assets.
contentOwner: AG
translation-type: tm+mt
source-git-commit: dea673f8999656a5c5364f74f45eba41dd17b947
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 1%

---


# Använda Camera Raw för att bearbeta bilder {#camera-raw-support}

Du kan aktivera det Camera Raw stödet för att bearbeta råfilsformat, t.ex. CR2, NEF och RAF, och återge bilderna i JPEG-format. Funktionen stöds i Adobe Experience Manager Assets med det [Camera Raw paket](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem630/product/assets/aem-assets-cameraraw-pkg) som finns tillgängligt från Software Distribution.

>[!NOTE]
>
>Funktionen stöder endast JPEG-återgivningar. Det stöds i Windows 64-bitars, Mac OS och RHEL 7.x.

Så här aktiverar du Camera Raw support i Adobe Experience Manager Assets:

1. Hämta det [Camera Raw paketet](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/aem630/product/assets/aem-assets-cameraraw-pkg) från Software Distribution.

1. Öppna `https://[aem_server]:[port]/workflow`. Öppna **[!UICONTROL DAM Update Asset]** arbetsflödet.

1. Öppna **[!UICONTROL Process Thumbnails]** steget.

1. Ange följande konfiguration på **[!UICONTROL Thumbnails]** fliken:

   * **[!UICONTROL Thumbnails]**: `140:100:false, 48:48:false, 319:319:false`
   * **[!UICONTROL Skip Mime Types]**: `skip:image/dng, skip:image/x-raw-(.*)`

   ![klibbig](assets/chlimage_1-334.png)

1. Ange **[!UICONTROL Web Enabled Image]** på fliken i **[!UICONTROL Skip List]** `audio/mpeg, video/(.*), image/dng, image/x-raw-(.*)`fältet.

   ![klibbig](assets/chlimage_1-335.png)

1. På sidopanelen lägger du till **[!UICONTROL Camera Raw/DNG Handler]** steget under **[!UICONTROL Thumbnail creation]** steget.

1. I **[!UICONTROL Camera Raw/DNG Handler]** steget lägger du till följande konfiguration på **[!UICONTROL Arguments]** fliken:

   * **[!UICONTROL Mime Types]**: `image/dng` och `image/x-raw-(.*)`
   * **[!UICONTROL Command]**:

      * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.web.1280.1280.jpeg 1280 1280`
      * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.319.319.jpeg 319 319`
      * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.140.100.jpeg 140 100`
      * `DAM_Raw_Converter ${directory}/${filename} ${directory} cq5dam.thumbnail.48.48.jpeg 48 48`

   ![chlimage_1-336](assets/chlimage_1-336.png)

1. Klicka på **[!UICONTROL Save]**.

>[!NOTE]
>
>Kontrollera att konfigurationen ovan är densamma som **[!UICONTROL Sample DAM Update Asset With Camera RAW and DNG Handling Step]** konfigurationen.

Nu kan du importera Camera Raw-filer till AEM Assets. När du har installerat det Camera Raw paketet och konfigurerat arbetsflödet visas **[!UICONTROL Image Adjust]** alternativet i listan över sidorutor.

![chlimage_1-337](assets/chlimage_1-337.png)

*Bild: Alternativ i sidopanelen*

![chlimage_1-338](assets/chlimage_1-338.png)

*Bild: Använd det här alternativet om du vill göra små ändringar i dina bilder*

När du har sparat redigeringarna i en Camera Raw bild `AdjustedPreview.jpg` skapas en ny återgivning för bilden. För andra bildtyper, förutom Camera Raw, återspeglas ändringarna i alla återgivningar.

## God praxis, kända problem och begränsningar {#best-practices}

Funktionen har följande begränsningar:

* Funktionen stöder endast JPEG-återgivningar. Det stöds i Windows 64-bitars, Mac OS och RHEL 7.x.
* Metadatatillbakaskrivning stöds inte för RAW- och DNG-format.
* Det Camera Raw biblioteket har begränsningar för det totala antalet pixlar som kan bearbetas samtidigt. För närvarande kan programmet bearbeta maximalt 65 000 pixlar på den långa sidan av en fil eller 512 MP, oavsett vilket villkor som påträffas först.
