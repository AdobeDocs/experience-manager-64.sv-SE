---
title: Filformat som stöds i AEM Assets
description: Lista över filformat och MIME-typer som stöds av AEM Assets och de funktioner som stöds för varje format.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 2baa172088f646752e85168d432d46942ac8244e
workflow-type: tm+mt
source-wordcount: '1696'
ht-degree: 2%

---


# Filformat som stöds i AEM Assets {#assets-supported-formats}

AEM Assets har stöd för ett stort antal filformat och alla funktioner har olika stöd för olika MIME-typer.

Om du vill integrera AEM Assets med andra standardbaserade DAM-lösningar (Digital Asset Management) och datorprogram använder du Adobes Extensible Metadata Platform (XMP).

Använd teckenförklaringen för att förstå supportnivån.

| Supportnivå | Beskrivning |
|:---:|---|
| ✓ | Stöds |
| * | Stöds med tilläggsfunktioner |
| − | Ej relevant |

## Rasterbildformat {#supported-raster-image-formats}

Följande rasterbildformat stöds för filhanteringsfunktioner:

| Format | Lagring | Metadatahantering | Extrahering av metadata | Generering av miniatyrbilder | Interaktiv redigering | Återskrivning av metadata | Insikter |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| PNG | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| GIF | ✓ | ✓ | ✓ | ✓ | ✓ |  | ✓ |
| TIFF | ✓ | ✓ | ✓ | ✓ |  | ✓ | ✓ |
| JPEG | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| BMP | ✓ | ✓ | ✓ | ✓ | ✓ |  | ✓ |
| PNM | ✓ | ✓ |  |  |  |  | ✓ |
| PGM | ✓ | ✓ |  |  |  |  | ✓ |
| PBM | ✓ | ✓ |  |  |  |  | ✓ |
| PPM | ✓ | ✓ |  |  |  |  | ✓ |
| PSD **‡** | ✓ | ✓ | ✓ | ✓ |  |  | ✓ |
| [EPS](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ | ✓ | ✓ |  | ✓ |  |
| PICT |  |  |  |  |  |  | ✓ |
| PSB | ✓ | ✓ | ✓ | ✓ |  |  |  |

**‡** Den sammanfogade bilden extraheras från PSD-filen. Det är en bild som genereras av Adobe Photoshop och inkluderas i PSD-filen. Beroende på inställningarna kan den sammanfogade bilden vara den faktiska bilden eller inte.

Följande rasterbildformat stöds för Dynamic Media-funktioner:

| Format | Överför<br> (indataformat) | Skapa<br> bildförinställning<br><br> (utdataformat) | Förhandsgranska<br> dynamisk<br> återgivning | Leverera<br> dynamisk<br> återgivning | Hämta<br> dynamisk<br> återgivning |
|---|:---:|:---:|:---:|:---:|:---:|
| PNG | ✓ | ✓ | ✓ | ✓ | ✓ |
| GIF | ✓ | ✓ | ✓ | ✓ | ✓ |
| TIFF | ✓ | ✓ | ✓ | ✓ | ✓ |
| JPEG | ✓ | ✓ | ✓ | ✓ | ✓ |
| BMP | ✓ |  |  |  |  |
| PNM |  |  |  |  |  |
| PGM |  |  |  |  |  |
| PBM |  |  |  |  |  |
| PPM |  |  |  |  |  |
| PSD **‡** | ✓ |  |  |  |  |
| [EPS](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ | ✓ | ✓ | ✓ |
| PICT | ✓ |  |  |  |  |
| PSB |  |  |  |  |  |

**‡** Den sammanfogade bilden extraheras från PSD-filen. Det är en bild som genereras av Adobe Photoshop och inkluderas i PSD-filen. Beroende på inställningarna kan den sammanfogade bilden vara den faktiska bilden eller inte.

Utöver informationen ovan bör du tänka på följande:

* Stödet för EPS-filer gäller endast för rasterbilder. Generering av miniatyrbilder för EPS-vektorbilder stöds till exempel inte som standard. Om du vill lägga till stöd [konfigurerar du ImageMagick](best-practices-for-imagemagick.md). Information om hur du integrerar tredjepartsverktyg för att aktivera ytterligare funktioner finns i [Kommandoradsbaserad mediehanterare](media-handlers.md#command-line-based-media-handler).

* Metadatatillbakaskrivning fungerar för PSB-filformat när det läggs till i `NComm` hanteraren.

* Information om hur du använder Dynamic Media för att förhandsgranska och generera dynamiska renderingar för EPS-filer finns i [Adobe Illustrator (AI), PostScript (EPS) och PDF-filformat.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* För EPS-filer stöds tillbakaskrivning av metadata i PostScript Document Structuring Convention (PS-Adobe) version 3.0 eller senare.

## Rasterbildformat som inte stöds i Dynamic Media {#unsupported-image-formats-dynamic-media}

I följande lista beskrivs de undertyper av rasterbildfilformat som *inte* stöds i Dynamic Media.

Se även [Identifiera filformat som inte stöds för Dynamic Media](https://helpx.adobe.com/experience-manager/kb/detect-unsupported-assets-for-dynamic-media.html).

* PNG-filer som har en IDAT-segmentstorlek som är större än 100 MB.
* PSB-filer.
* PSD-filer med en annan färgrymd än CMYK, RGB, Gråskala eller Bitmapp stöds inte. Färgrymderna DuoTone, Lab och Indexed stöds inte.
* PSD-filer med ett bitdjup som är större än 16.
* TIFF-filer som har flyttalsdata.
* TIFF-filer med Lab-färgrymd.

## PDF Rasterizer-bibliotek {#supported-pdf-rasterizer-library}

Adobe PDF Rasterizer-biblioteket genererar högkvalitativa miniatyrbilder och förhandsgranskningar för stora och innehållsintensiva Adobe Illustrator- och PDF-filer. Adobe rekommenderar att du använder PDF-rastreringsbiblioteket för följande:

* Innehållsintensiva AI/PDF-filer som är resurskrävande att bearbeta.
* AI/PDF-filer, för vilka miniatyrer inte genereras som standard.
* AI-filer med Pantone Matching System-färger (PMS).

Se [Använda PDF-rastrering](aem-pdf-rasterizer.md).

## Bildomkodningsbibliotek {#supported-image-transcoding-library}

Adobe Imaging Transcoding Library är en bildbehandlingslösning som utför viktiga bildhanteringsfunktioner, som kodning, omkodning, omsampling och storleksändring.

Bildkonverteringsbiblioteket stöder JPG/JPEG, PNG (8-bitars och 16-bitars), GIF, BMP, TIFF/komprimerad TIFF (förutom 32-bitars TIFF-filer och PTIFF-filer), ICO och ICN MIME-typer.

Se [Bildkonverteringsbibliotek](imaging-transcoding-library.md).

## Camera Raw {#supported-camera-raw}

Med Adobe Camera Raw-biblioteket kan AEM Assets importera råbilder. Se [Stöd](camera-raw.md)för Camera Raw.

## Dokumentformat {#supported-document-formats}

Dokumentformat som stöds för filhanteringsfunktioner är följande:

| Format | Lagring | Metadatahantering<br> | Extrahering av<br> fulltext | Extrahering av metadata<br> | Generering av miniatyrbilder<br> | Subasset<br> extraction | Metadata<br> -tillbakaskrivning |
|---|:---:|:---:|:---:|:---:|:---:|:---:|:---:|
| [AI](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ |  | ✓ | ✓ | ✓ | ✓ |
| DOC | ✓ | ✓ | ✓ | ✓ |  |  |  |
| DOCX | ✓ | ✓ | ✓ | ✓ |  |  |  |
| ODT | ✓ | ✓ | ✓ |  |  |  |  |
| [PDF](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| HTML | ✓ | ✓ | ✓ |  |  |  |  |
| RTF | ✓ | ✓ | ✓ |  |  |  |  |
| TXT | ✓ | ✓ | ✓ |  |  |  |  |
| XLS | ✓ | ✓ | ✓ |  |  |  |  |
| XLSX | ✓ | ✓ | ✓ | ✓ |  |  |  |
| ODS | ✓ | ✓ | ✓ |  |  |  |  |
| PPT | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| PPTX | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| ODP | ✓ | ✓ | ✓ |  |  |  |  |
| [INDD](managing-image-presets.md#indesign-indd-file-format) | ✓ | ✓ |  | ✓ | ✓ | ✓ | ✓ |
| PS | ✓ | ✓ |  |  |  |  |  |
| QXP | ✓ | ✓ |  |  |  |  |  |
| EPUB | ✓ | ✓ |  | ✓ | ✓ |  |  |

Dokumentformat som stöds för Dynamic Media-funktioner är följande:

| Format | Överför<br> (indataformat) | Skapa<br> bildförinställning<br><br> (utdataformat) | Förhandsgranska<br> dynamisk<br> återgivning | Leverera<br> dynamisk<br> återgivning | Hämta<br> dynamisk<br> återgivning |
|---|:---:|:---:|:---:|:---:|:---:|
| [AI](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ |  |  |  |  |
| DOC |  |  |  |  |  |
| DOCX |  |  |  |  |  |
| ODT |  |  |  |  |  |
| [PDF](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ | ✓ | ✓ | ✓ | ✓ |
| HTML |  |  |  |  |  |
| RTF |  |  |  |  |  |
| TXT |  |  |  |  |  |
| XLS |  |  |  |  |  |
| XLSX |  |  |  |  |  |
| ODS |  |  |  |  |  |
| PPT |  |  |  |  |  |
| PPTX |  |  |  |  |  |
| ODP |  |  |  |  |  |
| [INDD](managing-image-presets.md#indesign-indd-file-format) | ✓ |  |  |  |  |
| PS |  |  |  |  |  |
| QXP |  |  |  |  |  |
| EPUB |  |  |  |  |  |

Utöver ovanstående funktioner bör du tänka på följande:

* Information om hur du använder Dynamic Media för att generera dynamiska återgivningar för PDF-filer finns i [Adobe Illustrator (AI), PostScript (EPS) och PDF-filformat.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Information om hur du använder Dynamic Media för att förhandsgranska och generera dynamiska renderingar för AI-filer finns i [Adobe Illustrator (AI), PostScript (EPS) och PDF-filformat.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Information om hur du använder Dynamic Media för att generera dynamiska återgivningar för INDD-filer finns i [InDesign-filformat](../assets/managing-image-presets.md#indesign-indd-file-format)(INDD).

## Multimediaformat {#supported-multimedia-formats}

| Format | Lagring | Metadatahantering | Extrahering av metadata | Generering av miniatyrbilder | FFMPEG-omkodning |
|:---|:---:|:---:|:---:|:---:|:---:|
| AAC | ✓ | ✓ |  | − | * |
| MIDI | ✓ | ✓ |  | − | * |
| 3GP | ✓ | ✓ |  | − | * |
| MP3 | ✓ | ✓ | ✓ | − | * |
| MPG | ✓ | ✓ |  | − | * |
| OGA | ✓ | ✓ |  | − | * |
| OGG | ✓ | ✓ |  | − | * |
| RA | ✓ | ✓ |  | − | * |
| WAV | ✓ | ✓ |  | − | * |
| WMA | ✓ | ✓ |  | − | * |
| DVI | ✓ | ✓ |  | * | * |
| FLV | ✓ | ✓ |  | * | * |
| M4V | ✓ | ✓ |  | * | * |
| MPEG | ✓ | ✓ |  | * | * |
| OGV | ✓ | ✓ |  | * | * |
| MOV | ✓ | ✓ |  | * | * |
| WMV | ✓ | ✓ |  | * | * |
| SWF | ✓ | ✓ |  |  |  |

## Indatavideoformat för Dynamic Media Transcoding {#supported-input-video-formats-for-dynamic-media-transcoding}

| Videofiltillägg | Behållare | Rekommenderade videokodekar | Videokodekar som inte stöds |
|---|---|---|---|
| MP4 | MPEG-4 | H264/AVC (alla profiler) |  |
| MOV, QT | Apple QuickTime | H264/AVC, Apple ProRes422 &amp; HQ, Sony XDCAM, Sony DVCAM, HDV, Panasonic DVCPro, Apple DV (DV25), Apple PhotoJPEG, Sorenson, Avid DNxHD, Avid AVR | Apple Intermediate, Apple Animation |
| FLV, F4V | Adobe Flash | H264/AVC, Flix VP6, H263, Sorenson | SWF (vektoranimeringsfiler) |
| WMV | Windows Media 9 | WMV3 (v9), WMV2 (v8), WMV1 (v7), GoToMeeting (G2M2, G2M3, G2M4) | Microsoft-skärm (MSS2), Microsoft Photo Story (WVP2) |
| MPG, VOB, M2V, MP2 | MPEG-2 | MPEG-2 |  |
| M4V | Apple iTunes | H264/AVC |  |
| AVI | A/V-sammanflätning | XVID, DIVX, HDV, MiniDV (DV25), Techsmith Camtasia, Huffyuv, Fraps, Panasonic DVCPro | Indeo3 (IV30), MJPEG, Microsoft Video 1 (MS-CRAM) |
| WebM | WebM | Google VP8 |  |
| OGV, OGG | Ogg | Theora, VP3, Dirac |  |
| MXF | MXF | Sony XDCAM, MPEG-2, MPEG-4, Panasonic DVCPro |  |
| MTS | AVCHD | H264/AVC |  |
| MKV | Matroska | H264/AVC |  |
| R3D, RM | Red Raw-video | MJPEG 2000 |  |
| RAM, RM | RealVideo | Stöds inte | Real G2 (RV20), Real 8 (RV30), Real 10 (RV40) |
| FLAC | Inbyggd Flash | Kostnadsfri förlustfri ljudkodek |  |
| MJ2 | Motion JPEG 2000 | Motion JPEG 2000-kodek |  |

## Arkivformat {#supported-archive-formats}

De arkivformat som stöds och tillämpligheten för de vanliga DAM-arbetsflödena beskrivs i följande tabell.

| Format | Lagring | Versionshantering | Arbetsflöde | Publicering | Åtkomstkontroll | Dynamic Media Delivery |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| TGZ | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| JAR | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| RAR | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| TAR | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| ZIP **†** | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |

**†** Den sammanfogade bilden extraheras från PSD-filen. Det är en bild som genereras av Adobe Photoshop och inkluderas i PSD-filen. Beroende på inställningarna kan den sammanfogade bilden vara den faktiska bilden eller inte. ZIP-arkiven som skapats med `Deflate64` algoritmen har begränsat stöd i AEM. Arkiv- och arkiveringsåtgärder stöds inte. Åtgärder som att överföra, bläddra och hämta stöds emellertid.

## Andra format som stöds {#other-supported-formats}

Hur vanliga DAM-arbetsflöden kan användas för ett par andra filformat beskrivs i tabellen nedan.

| Format | Lagring | Versionshantering | Arbetsflöde | Publicering | Åtkomstkontroll | Dynamic Media Delivery |
|---|:---:|:---:|:---:|:---:|:---:|:---:|
| **#** | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| SVG | ✓ | ✓ | ✓ | ✓ | ✓ |  |
| CSS | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| VTT | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| XML | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| JavaScript (när konfigureras med egen leveransdomän) |  |  |  |  |  | ✓ |

**#** De andra formaten stöds i DAM för lagring, versionshantering, ACL, arbetsflöde, publicering och metadatahantering.

## MIME-typer som stöds {#supported-mime-types}

Som standard identifierar AEM filtypen med hjälp av filtillägget. AEM kan identifiera det från innehållet i filerna. För den senare väljer du [!UICONTROL Detect MIME from content] ett alternativ [!UICONTROL Day CQ DAM Mime Type Service] i AEM Web Console.

En lista över MIME-typer som stöds finns i CRXDE Lite på `/conf/global/settings/cloudconfigs/dmscene7/jcr:content/mimeTypes`.

| Filtillägg | MIME-typ/ Internetmedietyp | Standardvärde för jobParam | Tillåtet jobParam-värde |
|---|---|---|---|
| Bild | bild/s7resurs | `usmAmount=1.75&usmRadius=0.2`<br>`&usmThreshold=2&usmMonochrome=0&` | Standardvärdet jobParam gäller för alla bildresurser av MIME-typ.<ul><li>[knockoutBackgroundOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-knockout-background-options.html)</li><li>[manualCropOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-manual-crop-options.html)</li><li>[autoColorCropOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-auto-color-crop-options.html)</li><li>[autoTransparentCropOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-auto-transparent-crop-options.html)</li><li>[colorManagementOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-color-management-options.html)</li><li>[autoSetCreationOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-auto-set-creation-options.html)</li><li>[emailSetting](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/sting-constants/r-email-settings.html)</li><li>[xmpKeywords](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-xmp-keywords.html)</li><li>[unsharpMaskOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-unsharp-mask-options.html)</li></ul> |
| 3G2 | video/3gpp2 |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| 3GP | video/3gpp |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| AAC | audio/x-aac |  |  |
| AFM | application/x-font-type1 |  |  |
| AI | application/postscript | `aiprocess=Rasterize&airesolution=150`<br>`&aicolorspace=Auto&aialpha=false` | <ul><li>[postScriptOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-post-script-options.html)</li><li> [illustratorOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-illustrator-options.html)</li></ul> |
| AIFF | audio/x-aiff |  |  |
| AVI | video/x-msvideo |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| BMP | image/bmp |  |  |
| CSS | text/css |  |  |
| DOC | application/msword |  |  |
| EPS | <ul><li>application/postscript</li><li>program/steg</li><li>application/x-eps</li><li>bild/steg</li><li>image/x-eps</li> |  |  |
| F4V | video/x-f4v |  | ExcludeMasterVideoFromAVS |
| FLA | application/x-shockwave-flash |  |  |
| FLV | video/x-flv |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| FPX | image/vnd.fpx |  |  |
| GIF | image/gif |  |  |
| ICC | application/vnd.iccprofile |  |  |
| ICM | application/vnd.iccprofile |  |  |
| INDD | application/x-indesign |  |  |
| JPEG | image/jpeg |  |  |
| JPG | image/jpeg |  |  |
| M2V | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| M4V | video/x-m4v |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MOV | video/quicktime |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MP3 | audio/mpeg |  |  |
| MP4 | video/mp4 |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MPEG | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MPG | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MTS | model/vnd.mts |  |  |
| OGV | video/ogg |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| OTF | application/x-font-otf |  |  |
| PDF | application/pdf | `pdfprocess=Rasterize&resolution=150`<br>`&colorspace=Auto&pdfbrochure=false`<br>`&keywords=false&links=false` | [pdfOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-options.html) |
| PFB | application/x-font-type1 |  |  |
| PFM | application/x-font-type1 |  |  |
| PICT | image/x-pict |  |  |
| PNG | bild/png |  |  |
| PPT | application/vnd.ms |  |  |
| PS | application/postscript | `psprocess=Rasterize&psresolution=150`<br>`&pscolorspace=Auto&psalpha=false`<br>`&psextractsearchwords=false`<br>`&aiprocess=Rasterize&airesolution=150`<br>`&aicolorspace=Auto&aialpha=false` | <ul><li>[postScriptOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-post-script-options.html)</li><li>[illustratorOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-illustrator-options.html)</li></ul> |
| PSD | image/vnd.adobe.photoshop | `process=None&layerNaming=Layername`<br>`&anchor=Center&createTemplate=false`<br>`&extractText=false&extendLayers=false` | <ul><li>[photoshopOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-options.html)</li><li>[photoshopLayerOptions](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-layer-options.html)</li></ul> |
| RTF | application/rtf |  |  |
| SVG | image/svg+xml |  |  |
| SWF | application/x-shockwave-flash |  |  |
| TAR | application/x-tar |  |  |
| TIF/TIFF | bild/tiff |  |  |
| TTC | application/x-font-ttf |  |  |
| TTF | application/x-font-ttf |  |  |
| VOB | video/dvd |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| VTT | text/vtt |  |  |
| WAV | audio/x-wav |  |  |
| WEBM | video/webm |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| WMA | audio/x-ms-wma |  |  |
| WMV | video/x-ms-wmv |  | [ExcludeMasterVideoFromAVS](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| XLS | application/vnd.ms |  |  |
| ZIP | application/zip |  |  |

>[!MORELIKETHIS]
>
>* [Aktivera stöd](/help/sites-administering/scene7.md#enabling-mime-type-based-assets-scene-upload-job-parameter-support)för MIME-typbaserade resurser/Scene7-överföringsjobbparametrar.
>* [Konfigurera MIME-typbaserad för stöd](config-dynamic.md)för överföringsjobbparametrar.

