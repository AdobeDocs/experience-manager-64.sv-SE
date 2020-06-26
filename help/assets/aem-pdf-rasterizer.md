---
title: Använd PDF-rastrering
description: Generera högkvalitativa miniatyrbilder och renderingar med hjälp av Adobe PDF Rasterizer-biblioteket.
contentOwner: AG
translation-type: tm+mt
source-git-commit: dea673f8999656a5c5364f74f45eba41dd17b947
workflow-type: tm+mt
source-wordcount: '687'
ht-degree: 0%

---


# Använda PDF-rastrering {#using-pdf-rasterizer}

När du överför stora, innehållsintensiva PDF- eller AI-filer till Adobe Experience Manager-resurser (AEM) kanske standardbiblioteket inte genererar korrekta utdata. I sådana fall kan Adobes PDF Rasterizer-bibliotek generera tillförlitligare och exaktare utdata jämfört med utdata från ett standardbibliotek.

Adobe rekommenderar att du använder PDF-rastreringsbiblioteket för följande:

* Tung, innehållsintensiv AI- eller PDF-fil.
* AI- eller PDF-filer med miniatyrer som inte genererats direkt.
* AI-filer med Pantone Matching System-färger (PMS).

Miniatyrbilder och förhandsgranskningar som genererats med PDF Rasterizer har bättre kvalitet jämfört med färdiga utdata och ger därför en konsekvent visningsupplevelse på olika enheter. Adobe PDF Rasterizer-biblioteket har inte stöd för konvertering av färgrymd. Det skrivs alltid ut på RGB, oavsett källfilens färgrymd.

1. Installera PDF Rasterizer-paketet på din AEM-instans från [programvarudistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/product/assets/aem-assets-pdf-rasterizer-pkg).

   >[!NOTE]
   >
   >PDF Rasterizer-biblioteket är endast tillgängligt för Windows och Linux.

1. Gå till arbetsflödeskonsolen för AEM Assets från `https://[AEM_server]:[port]/workflow`.
1. Öppna **[!UICONTROL DAM Update Asset]** arbetsflödessidan.
1. Konfigurera följande för att hoppa över standardgenerering av miniatyrbilder och webbåtergivning för PDF- och AI-filer:

   * Öppna **[!UICONTROL Thumbnail Process]** steget och lägg till `application/pdf` eller `application/postscript` i **[!UICONTROL Skip Mime Types]** fältet.
   ![skip_mime_types-2](assets/skip_mime_types-2.png)

   * Lägg till **[!UICONTROL Web Enabled Image]** eller `application/pdf` under på `application/postscript` fliken **[!UICONTROL Skip List]** beroende på dina behov.
   ![web_enabled_imageskiplist](assets/web_enabled_imageskiplist.png)

1. Öppna **[!UICONTROL Rasterize PDF/AI Image Preview Rendition]** steget och ta bort MIME-typen som du vill hoppa över standardgenereringen av förhandsvisningsbildåtergivningar för. Du kan till exempel ta bort MIME-typen *application/pdf*, ** application/postscript eller *application/illustrator* från **[!UICONTROL MIME Types]** listan.

   ![process_arguments](assets/process_arguments.png)

1. Dra **[!UICONTROL PDF Rasterizer Handler]** steget från sidopanelen till nedanför **[!UICONTROL Process Thumbnails]** steget.
1. Konfigurera följande argument för **[!UICONTROL PDF Rasterizer Handler]** steget:

   * Mime-typer: *application/pdf* or *application/postscript*
   * Kommandon: `PDFRasterizer -d -p 1 -s 1280 -t PNG -i ${file}`
   * Lägg till miniatyrstorlekar: 319:319, 140:100, 48:48. Lägg till anpassad miniatyrkonfiguration, om det behövs.
   Kommandoradsargumenten för `PDFRasterizer` kommandot kan innehålla följande:

   **-d**: Flagga för smidig återgivning av text, vektorgrafik och bilder. Skapar bilder med bättre kvalitet. Om du tar med den här parametern körs kommandot långsamt och bildstorleken ökar.

   `-p`: Sidnummer. Standardvärdet är alla sidor. * betecknar alla sidor.

   **-s**: Största bilddimension (höjd eller bredd). Detta konverteras till DPI för varje sida. Om sidorna har olika storlek kan varje sida eventuellt skalas med olika mängd. Standardvärdet är faktisk sidstorlek.

   **-t**: Typ av utdatabild. Giltiga typer är JPEG, PNG, GIF och BMP. Standardvärdet är JPEG.

   **-i**: Sökväg för PDF-indata. Det är en obligatorisk parameter.

   `-h`: Hjälp

1. Om du vill ta bort mellanliggande återgivningar markerar du **[!UICONTROL Delete Generated Rendition]**.
1. Om du vill att PDF-rastrering ska generera webbåtergivningar väljer du **[!UICONTROL Generate Web Rendition]**.

   ![generate_web_renditions1](assets/generate_web_renditions1.png)

1. Ange inställningarna på **[!UICONTROL Web Enabled Image]** fliken.

   ![web_enabled_image1](assets/web_enabled_image1.png)

1. Spara arbetsflödet.
1. Om du vill att PDF-rastreraren ska kunna bearbeta PDF-sidor med PDF-bibliotek öppnar du **[!UICONTROL DAM Process Subasset]** modellen från arbetsflödeskonsolen.
1. Dra steget PDF-rastreringshanteraren från sidopanelen under **[!UICONTROL Create Web-Enabled Image Rendition]** steget.
1. Konfigurera följande argument för **[!UICONTROL PDF Rasterizer Handler]** steget:

   * Mime-typer: `application/pdf` eller `application/postscript`
   * Kommandon: `PDFRasterizer -d -p 1 -s 1280 -t PNG -i ${file}`
   * Lägg till miniatyrstorlekar: 319:319, 140:100, 48:48. Lägg till anpassad miniatyrkonfiguration, om det behövs.
   Kommandoradsargumenten för PDFRasterizer-kommandot kan innehålla följande:

   **-d**: Flagga för smidig återgivning av text, vektorgrafik och bilder. Skapar bilder med bättre kvalitet. Om du tar med den här parametern körs kommandot långsamt och bildstorleken ökar.

   **-p**: Sidnummer. Standardvärdet är alla sidor. En asterisk `*` betecknar alla sidor.

   **-s**: Största bilddimension (höjd eller bredd). Detta konverteras till DPI för varje sida. Om sidorna har olika storlek kan varje sida eventuellt skalas med olika mängd. Standardvärdet är faktisk sidstorlek.

   **-t**: Typ av utdatabild. Giltiga typer är JPEG, PNG, GIF och BMP. Standardvärdet är JPEG.

   **-i**: Sökväg för PDF-indata. Det är en obligatorisk parameter.

   **-h**: Hjälp

1. Om du vill ta bort mellanliggande återgivningar markerar du **[!UICONTROL Delete Generated Rendition]**.
1. Om du vill att PDF-rastrering ska generera webbåtergivningar väljer du **[!UICONTROL Generate Web Rendition]**.

   ![generate_web_renditions](assets/generate_web_renditions.png)

1. Ange inställningarna i **[!UICONTROL Web Enabled Image tab]**.

   ![web_enabled_image-1](assets/web_enabled_image-1.png)

1. Spara arbetsflödet.
1. Överför en PDF-fil eller en AI-fil till AEM Assets. I PDF-rastreraren genereras miniatyrbilder och webbåtergivningar för filen.
