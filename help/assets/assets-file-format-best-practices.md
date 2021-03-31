---
title: Bästa metoder för att använda filformat
description: Bästa tillvägagångssätt för filstöd i AEM Assets.
contentOwner: AG
feature: Resurshantering,Utvecklarverktyg
role: Administratör
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Metodtips för resursfilformat {#assets-file-format-best-practices}

AEM Assets har stöd för många egna bibliotek och bibliotek för tredjepartsfilformat som tillgodoser olika krav från användarna. Bland de Adobe-bibliotek som stöds finns Adobe Camera Raw, Gibson, Adobe PDF Rasterizer och Adobe InDesign Server. Dessutom har AEM Assets stöd för bibliotek från tredje part, inklusive ImageMagick, TwelveMonkeys och så vidare.

Information om vilka filformat som stöds finns i [Format för resurser som stöds](assets-formats.md).

## Adobe Camera Raw library {#adobe-camera-raw-library}

För optimala prestanda rekommenderar Adobe att du använder Adobe Camera Raw-biblioteket för:

* RAW
* DNG

Adobe Camera Raw-biblioteket stöder CMYK-färgprofil som indata. Däremot genereras utdata i RGB-färgrymd och endast JPEG-format stöds. Källfilens färgrymd (till exempel CMYK) behålls inte i miniatyrbilderna.

Mer information finns i [Camera Raw support](camera-raw.md) i AEM Assets.

## Adobe PDF Rasterizer-bibliotek {#adobe-pdf-rasterizer-library}

För att få bästa möjliga resultat rekommenderar Adobe att du använder Adobe PDF rastreringsbibliotek för följande filer:

* Tunga, innehållsintensiva PDF-filer
* AI-filer med miniatyrbilder som inte genererats direkt från paketet
* För AI-filer med SPOT-färger (PMS)

Miniatyrbilder och förhandsgranskningar som genererats med PDF Rasterizer har bättre kvalitet än färdiga rasterutdata. Adobe PDF Rasterizer-biblioteket har inte stöd för någon färgmodellskonvertering. Oavsett färgrymden i PDF-källfilen genererar Adobe PDF Rasterizer endast RGB-utdata.

## Adobe InDesign server {#adobe-indesign-cc-server}

Adobe rekommenderar att du använder Adobe InDesign server för att extrahera Adobe InDesign-specifika återgivningar som IDML och HTML. Mer information finns i [Lägga till AEM resurser som referenser i Adobe InDesign](managing-linked-subassets.md#add-aem-assets-as-references-in-adobe-indesign).

## Dynamic Media  {#dynamic-media}

Dynamic Media genererar och levererar flera varianter av multimedieinnehåll i realtid via sitt globala, skalbara och prestandaoptimerade nätverk. Det levererar interaktiva tittarupplevelser och effektiviserar den digitala kampanjhanteringsprocessen. Mer information om hur du aktiverar Dynamic Media finns i [Konfigurera Dynamic Media](config-dynamic.md).

För närvarande har Dynamic Media stöd för videoklipp på upp till 15 GB per fil.

## ImageMagick library {#imagemagick-library}

Adobe rekommenderar att du använder ImageMagick-biblioteket i följande scenarier:

* Generera miniatyrrenderingar för EPS-filer
* Bevara bildprofilsinformation
* Bevara genomskinlighet
* Bearbeta PSD- och PSB-filer

Mer information om hur du konfigurerar ImageMagic-biblioteket i AEM finns i [Använda ImageMagick](media-handlers.md#an-example-using-imagemagick). Mer information finns i [Bästa metoder för att konfigurera ImageMagick](best-practices-for-imagemagick.md).

## Bildomkodningsbibliotek {#image-transcoding-library}

Adobe Imaging Transcoding Library är en bildbehandlingslösning som utför viktiga bildhanteringsfunktioner, till exempel bildkodning, omkodning, omsampling, storleksändring osv.

Bildkodningsbiblioteket stöder följande MIME-typer:

* JPG/JPEG
* PNG (8 och 16 bitar)
* GIF
* BMP
* TIFF/Komprimerad TIFF (förutom 32-bitars tips och PTiff).
* ICO
* ICN

Mer information finns i [Imaging Transcoding Library](imaging-transcoding-library.md).
