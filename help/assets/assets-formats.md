---
title: Filformat som stöds i [!DNL Experience Manager] Resurser
description: Lista över filformat och MIME-typer som stöds av Assets och de funktioner som stöds för varje format.
contentOwner: AG
feature: Asset Management,Renditions
role: User,Admin
exl-id: ee25fe8f-36fb-42b3-9f90-0ea77bc02e2f
source-git-commit: cc47644419f7b7f4f1f00bb848050aa4a98efa09
workflow-type: tm+mt
source-wordcount: '1635'
ht-degree: 2%

---

# Filformat som stöds i [!DNL Adobe Experience Manager Assets] {#assets-supported-formats}

[!DNL Experience Manager Assets] har stöd för ett stort antal filformat och alla funktioner har olika stöd för olika MIME-typer.

Integrera [!DNL Assets] använder Adobe Extensible Metadata Platform (XMP) tillsammans med andra standardkompatibla DAM-lösningar och datorprogram.

Använd teckenförklaringen för att förstå supportnivån.

| Supportnivå | Beskrivning |
|:---:|---|
| ✓ | Stöds |
| &#42; | Stöds med tilläggsfunktioner |
| - | Ej relevant |

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

**‡** Den sammanfogade bilden extraheras från filen PSD. Det är en bild som genereras av Adobe Photoshop och inkluderas i filen PSD. Beroende på inställningarna kan den sammanfogade bilden vara den faktiska bilden eller inte.

Följande rasterbildformat stöds för Dynamic Media-funktioner:

| Format | Överför<br> (Indataformat) | Skapa<br> image<br> förinställning<br> (Utdataformat) | Förhandsgranska<br> dynamisk<br> rendering | Leverera<br> dynamisk<br> rendering | Hämta<br> dynamisk<br> rendering |
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

**‡** Den sammanfogade bilden extraheras från filen PSD. Det är en bild som genereras av Adobe Photoshop och inkluderas i filen PSD. Beroende på inställningarna kan den sammanfogade bilden vara den faktiska bilden eller inte.

Utöver informationen ovan bör du tänka på följande:

* Stödet för EPS-filer gäller endast för rasterbilder. Generering av miniatyrbilder för EPS-vektorbilder stöds till exempel inte som standard. Om du vill lägga till stöd [konfigurera ImageMagick](best-practices-for-imagemagick.md). Information om hur du integrerar tredjepartsverktyg för att aktivera ytterligare funktioner finns i [Kommandoradsbaserad mediehanterare](media-handlers.md#command-line-based-media-handler).

* Metadatatillbakaskrivning fungerar för PSB-filformatet när det läggs till i `NComm` hanterare.

* Information om hur du använder Dynamic Media för att förhandsgranska och generera dynamiska återgivningar för EPS-filer finns i [Filformaten Adobe Illustrator (AI), Postscript (EPS) och PDF.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* För EPS-filer stöds tillbakaskrivning av metadata i PostScript Document Structuring Convention (PS-Adobe) version 3.0 eller senare.

## Rasterbildformat som inte stöds i Dynamic Media {#unsupported-image-formats-dynamic-media}

I följande lista beskrivs de undertyper av rasterbildfilformat som *not* stöds i Dynamic Media.

Se även [Identifiera filformat som inte stöds för Dynamic Media](https://helpx.adobe.com/experience-manager/kb/detect-unsupported-assets-for-dynamic-media.html).

* PNG-filer som har en IDAT-segmentstorlek som är större än 100 MB.
* PSB-filer.
* PSD-filer med en annan färgmodell än CMYK, RGB, Gråskala eller Bitmapp stöds inte. Färgrymderna DuoTone, Lab och Indexed stöds inte.
* PSD-filer med ett bitdjup som är större än 16.
* TIFF-filer med flyttalsdata.
* TIFF-filer med Lab-färgrymd.

## PDF Rasterizer-bibliotek {#supported-pdf-rasterizer-library}

Adobe PDF Rasterizer-biblioteket genererar högkvalitativa miniatyrbilder och förhandsvisningar för stora och innehållsintensiva Adobe Illustrator- och PDF-filer. Adobe rekommenderar att du använder PDF rastrerarbiblioteket för följande:

* Innehållsintensiva AI/PDF-filer som är resurskrävande att bearbeta.
* AI/PDF-filer, för vilka miniatyrbilder inte genereras som standard.
* AI-filer med Pantone Matching System-färger (PMS).

Se [Använda PDF Rasterizer](aem-pdf-rasterizer.md).

## Bildomkodningsbibliotek {#supported-image-transcoding-library}

Adobe Imaging Transcoding Library är en bildbehandlingslösning som utför viktiga bildhanteringsfunktioner, som kodning, omkodning, omsampling och storleksändring.

Bildkonverteringsbiblioteket har stöd för JPG/JPEG, PNG (8-bitars och 16-bitars), GIF, BMP, TIFF/komprimerat TIFF (förutom 32-bitars TIFF och PTIFF-filer), ICO och ICN MIME.

Se [Konverteringsbibliotek för bildbehandling](imaging-transcoding-library.md).

## Camera Raw {#supported-camera-raw}

Adobe Camera Raw-biblioteket aktiverar [!DNL Assets] för att importera råbilder. Se [Camera Raw support](camera-raw.md).

## Dokumentformat {#supported-document-formats}

Dokumentformat som stöds för filhanteringsfunktioner är följande:

| Format | Lagring | Metadata<br> hantering | Fulltext<br> extrahering | Metadata<br> extrahering | Miniatyrbild<br> generering | Undertillgång<br> extrahering | Metadata<br> tillbakaskrivning |
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
| ePub | ✓ | ✓ |  | ✓ | ✓ |  |  |

Dokumentformat som stöds för Dynamic Media-funktioner är följande:

| Format | Överför<br> (Indataformat) | Skapa<br> image<br> förinställning<br> (Utdataformat) | Förhandsgranska<br> dynamisk<br> rendering | Leverera<br> dynamisk<br> rendering | Hämta<br> dynamisk<br> rendering |
|---|:---:|:---:|:---:|:---:|:---:|
| [AI](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) | ✓ |  |  |  |  |
| DOC |  |  |  |  |  |
| DOCX |  |  |  |  |  |
| ODT |  |  |  |  |  |
| [PDF](managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats) (Se anmärkningen nedan) | ✓ | ✓ | ✓ | ✓ | ✓ |
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
| ePub |  |  |  |  |  |

>[!NOTE]
>
>För säker PDF stöds bara överföring.

Utöver ovanstående funktioner bör du tänka på följande:

* Information om hur du använder Dynamic Media för att generera dynamiska renderingar för PDF-filer finns i [Filformaten Adobe Illustrator (AI), Postscript (EPS) och PDF.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Information om hur du använder Dynamic Media för att förhandsgranska och generera dynamiska återgivningar för AI-filer finns i [Filformaten Adobe Illustrator (AI), Postscript (EPS) och PDF.](../assets/managing-image-presets.md#adobe-illustrator-ai-postscript-eps-and-pdf-file-formats)

* Information om hur du använder Dynamic Media för att generera dynamiska renderingar för INDD-filer finns i [InDesign (INDD), filformat](../assets/managing-image-presets.md#indesign-indd-file-format).

## Multimediaformat {#supported-multimedia-formats}

| Format | Lagring | Metadatahantering | Extrahering av metadata | Generering av miniatyrbilder | FFMPEG-omkodning |
|:---|:---:|:---:|:---:|:---:|:---:|
| AAC | ✓ | ✓ |  | - | &#42; |
| MIDI | ✓ | ✓ |  | - | &#42; |
| 3GP | ✓ | ✓ |  | - | &#42; |
| MP3 | ✓ | ✓ | ✓ | - | &#42; |
| MPG | ✓ | ✓ |  | - | &#42; |
| OGA | ✓ | ✓ |  | - | &#42; |
| OGG | ✓ | ✓ |  | - | &#42; |
| RA | ✓ | ✓ |  | - | &#42; |
| WAV | ✓ | ✓ |  | - | &#42; |
| WMA | ✓ | ✓ |  | - | &#42; |
| DVI | ✓ | ✓ |  | &#42; | &#42; |
| FLV | ✓ | ✓ |  | &#42; | &#42; |
| M4V | ✓ | ✓ |  | &#42; | &#42; |
| MPEG | ✓ | ✓ |  | &#42; | &#42; |
| OGV | ✓ | ✓ |  | &#42; | &#42; |
| MOV | ✓ | ✓ |  | &#42; | &#42; |
| WMV | ✓ | ✓ |  | &#42; | &#42; |
| SWF | ✓ | ✓ |  |  |  |

## Indatavideoformat för Dynamic Media Transcoding {#supported-input-video-formats-for-dynamic-media-transcoding}

| Videofiltillägg | Behållare | Rekommenderade videokodekar | Videokodekar som inte stöds |
|---|---|---|---|
| MP4 | MPEG-4 | H264/AVC (alla profiler) |  |
| MOV, QT | Apple QuickTime | H264/AVC, Apple ProRes422 &amp; HQ, Sony XDCAM, Sony DVCAM, HDV, Panasonic DVCPro, Apple DV (DV25), Apple PhotoJPEG, Sorenson, Avid DNxHD, Avid AVR | Apple Intermediate, Apple Animation |
| FLV, F4V | Adobe Flash | H264/AVC, Flix VP6, H263, Sorenson | SWF (vektoranimeringsfiler) |
| WMV | Windows Media 9 | WMV3 (v9), WMV2 (v8), WMV1 (v7), GoToMeeting (G2M2, G2M3, G2M4) | Microsoft Screen (MSS2), Microsoft Photo Story (WVP2) |
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

**†** Den sammanfogade bilden extraheras från filen PSD. Det är en bild som genereras av Adobe Photoshop och inkluderas i filen PSD. Beroende på inställningarna kan den sammanfogade bilden vara den faktiska bilden eller inte. ZIP-arkiv som skapats med `Deflate64` algoritmen har begränsat stöd i AEM. Arkiv- och arkiveringsåtgärder stöds inte. Åtgärder som att överföra, bläddra och hämta stöds emellertid.

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

Som standard [!DNL Experience Manager] identifierar filtypen med hjälp av filtillägget. [!DNL Experience Manager] kan identifiera det från innehållet i filerna. För den senare väljer du [!UICONTROL Detect MIME from content] alternativ i [!UICONTROL Day CQ DAM Mime Type Service] i [!DNL Experience Manager] Webbkonsol.

En lista över MIME-typer som stöds finns i CRXDE Lite på `/conf/global/settings/cloudconfigs/dmscene7/jcr:content/mimeTypes`.

| Filtillägg | MIME-typ/ Internetmedietyp | Standardvärde för jobParam | Tillåtet jobParam-värde |
|---|---|---|---|
| Bild | bild/s7resurs | `usmAmount=1.75&usmRadius=0.2`<br>`&usmThreshold=2&usmMonochrome=0&` | Standardvärdet jobParam gäller för alla bildresurser av MIME-typ.<ul><li>[knockoutBackgroundOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-knockout-background-options.html)</li><li>[manualCropOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-manual-crop-options.html)</li><li>[autoColorCropOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-auto-color-crop-options.html)</li><li>[autoTransparentCropOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-auto-transparent-crop-options.html)</li><li>[colorManagementOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-color-management-options.html)</li><li>[autoSetCreationOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-auto-set-creation-options.html)</li><li>[emailSetting](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/sting-constants/r-email-settings.html)</li><li>[xmpKeywords](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-xmp-keywords.html)</li><li>[unsharpMaskOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-unsharp-mask-options.html)</li></ul> |
| 3G2 | video/3gpp2 |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| 3GP | video/3gpp |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| AAC | audio/x-aac |  |  |
| AFM | application/x-font-type1 |  |  |
| AI | application/postscript | `aiprocess=Rasterize&airesolution=150`<br>`&aicolorspace=Auto&aialpha=false` | <ul><li>[postScriptOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-post-script-options.html)</li><li> [illustratorOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-illustrator-options.html)</li></ul> |
| AIFF | audio/x-aiff |  |  |
| AVI | video/x-msvideo |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| BMP | image/bmp |  |  |
| CSS | text/css |  |  |
| DOC | application/msword |  |  |
| EPS | <ul><li>application/postscript</li><li>program/steg</li><li>application/x-eps</li><li>bild/steg</li><li>image/x-eps</li> |  |  |
| F4V | video/x-f4v |  | ExcludeMasterVideoFromAVS |
| FLA | application/x-shockwave-flash |  |  |
| FLV | video/x-flv |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| FPX | image/vnd.fpx |  |  |
| GIF | image/gif |  |  |
| ICC | application/vnd.iccprofile |  |  |
| ICM | application/vnd.iccprofile |  |  |
| INDD | application/x-indesign |  |  |
| JPEG | image/jpeg |  |  |
| JPG | image/jpeg |  |  |
| M2V | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| M4V | video/x-m4v |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MOV | video/quicktime |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MP3 | audio/mpeg |  |  |
| MP4 | video/mp4 |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MPEG | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MPG | video/mpeg |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| MTS | model/vnd.mts |  |  |
| OGV | video/ogg |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| OTF | application/x-font-otf |  |  |
| PDF | application/pdf | `pdfprocess=Rasterize&resolution=150`<br>`&colorspace=Auto&pdfbrochure=false`<br>`&keywords=false&links=false` | [pdfOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-options.html) |
| PFB | application/x-font-type1 |  |  |
| PFM | application/x-font-type1 |  |  |
| PICT | image/x-pict |  |  |
| PNG | bild/png |  |  |
| PPT | application/vnd.ms |  |  |
| PS | application/postscript | `psprocess=Rasterize&psresolution=150`<br>`&pscolorspace=Auto&psalpha=false`<br>`&psextractsearchwords=false`<br>`&aiprocess=Rasterize&airesolution=150`<br>`&aicolorspace=Auto&aialpha=false` | <ul><li>[postScriptOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-post-script-options.html)</li><li>[illustratorOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-illustrator-options.html)</li></ul> |
| PSD | image/vnd.adobe.photoshop | `process=None&layerNaming=Layername`<br>`&anchor=Center&createTemplate=false`<br>`&extractText=false&extendLayers=false` | <ul><li>[photoshopOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-options.html)</li><li>[photoshopLayerOptions](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-photoshop-layer-options.html)</li></ul> |
| RTF | application/rtf |  |  |
| SVG | image/svg+xml |  |  |
| SWF | application/x-shockwave-flash |  |  |
| TAR | application/x-tar |  |  |
| TIF/TIFF | bild/tiff |  |  |
| TTC | application/x-font-ttf |  |  |
| TTF | application/x-font-ttf |  |  |
| VOB | video/dvd |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| VTT | text/vtt |  |  |
| WAV | audio/x-wav |  |  |
| WEBM | video/webm |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| WMA | audio/x-ms-wma |  |  |
| WMV | video/x-ms-wmv |  | [ExcludeMasterVideoFromAVS](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/image-production-api/data-types/r-exclude-master-video-from-avs.html) |
| XLS | application/vnd.ms |  |  |
| ZIP | application/zip |  |  |

>[!MORELIKETHIS]
>
>* [Aktivera stöd för MIME-typbaserade resurser/Dynamic Media Classic överföringsjobbparametrar](/help/sites-administering/scene7.md#enabling-mime-type-based-assets-scene-upload-job-parameter-support).
>* [Konfigurera MIME-typbaserad för stöd av överföringsjobbparametrar](config-dynamic.md).

