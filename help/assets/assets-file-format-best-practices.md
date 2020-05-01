---
title: Bästa metoder för att använda filformat
description: Metodtips för filstöd i AEM Assets.
contentOwner: AG
translation-type: tm+mt
source-git-commit: a892ef7ab018aca715693125808d7ade540c8242

---


# Bästa metoder för att använda filformat {#assets-file-format-best-practices}

AEM Assets stöder många egna och tredjepartsbibliotek för filformat för att tillgodose olika användarbehov. De Adobe-bibliotek som stöds är bland annat Adobe Camera Raw, Gibson, Adobe PDF Rasterizer och Adobe InDesign Server. Dessutom har AEM Assets stöd för tredjepartsbibliotek som ImageMagick, TwelveMonkeys och så vidare.

Information om vilka filformat som stöds finns i Format [som stöds för](assets-formats.md)resurser.

## Adobe Camera Raw-bibliotek {#adobe-camera-raw-library}

För bästa prestanda rekommenderar Adobe att du använder Adobe Camera Raw-biblioteket för:

* RAW
* DNG

Adobe Camera Raw-biblioteket stöder CMYK-färgprofil som indata. Däremot genereras utdata i RGB-färgrymd och endast JPEG-format stöds. Källfilens färgrymd (till exempel CMYK) behålls inte i miniatyrbilderna.

Mer information finns i [Camera Raw-stöd](camera-raw.md) i AEM Resurser.

## Adobe PDF Rasterizer-bibliotek {#adobe-pdf-rasterizer-library}

För bästa resultat bör du använda Adobe PDF-rastreringsbiblioteket för följande filer:

* Tunga, innehållsintensiva PDF-filer
* AI-filer med miniatyrbilder som inte genererats direkt från paketet
* För AI-filer med SPOT-färger (PMS)

Miniatyrbilder och förhandsgranskningar som genererats med PDF Rasterizer har bättre kvalitet än färdiga rasterutdata. Adobe PDF Rasterizer-biblioteket har inte stöd för konvertering av färgrymd. Oberoende av färgrymden i PDF-källfilen genererar Adobe PDF Rasterizer endast RGB-utdata.

## Adobe InDesign-server {#adobe-indesign-cc-server}

Adobe rekommenderar att du använder Adobe InDesign Server för att extrahera Adobe InDesign-specifika återgivningar som IDML och HTML. Mer information finns i [Lägga till AEM-resurser som referenser i Adobe InDesign](managing-linked-subassets.md#add-aem-assets-as-references-in-adobe-indesign).

## Dynamic Media  {#dynamic-media}

Dynamic Media genererar och levererar flera varianter av multimedieinnehåll i realtid via sitt globala, skalbara och prestandaoptimerade nätverk. Det levererar interaktiva tittarupplevelser och effektiviserar den digitala kampanjhanteringsprocessen. Mer information om hur du aktiverar dynamiska media finns i [Konfigurera dynamiska media](config-dynamic.md).

För närvarande har Dynamic Media stöd för videor på upp till 15 GB innehåll per fil.

## ImageMagick Library {#imagemagick-library}

Adobe rekommenderar att du använder ImageMagick-biblioteket i följande scenarier:

* Generera miniatyrrenderingar för EPS-filer
* Bevara bildprofilsinformation
* Bevara genomskinlighet
* Bearbeta PSD- och PSB-filer

Mer information om hur du konfigurerar ImageMagic-biblioteket i AEM finns i [Använda ImageMagick](media-handlers.md#an-example-using-imagemagick). Mer information finns i [Bästa metoder för att konfigurera ImageMagick](best-practices-for-imagemagick.md).

## Bildomkodningsbibliotek {#image-transcoding-library}

Adobe Imaging Transcoding Library är en bildbehandlingslösning som utför grundläggande bildhanteringsfunktioner, som bildkodning, omkodning, omsampling, storleksändring med mera.

Bildkodningsbiblioteket stöder följande MIME-typer:

* JPG/JPEG
* PNG (8 och 16 bitar)
* GIF
* BMP
* TIFF/Komprimerad TIFF (förutom 32-bitars tips och PTiff).
* ICO
* ICN

Mer information finns i [Bildkonverteringsbibliotek](imaging-transcoding-library.md).
