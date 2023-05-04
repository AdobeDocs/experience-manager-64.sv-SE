---
title: Konfigurera komponenten Video
seo-title: Configure the Video component
description: Lär dig hur du konfigurerar videokomponenten.
seo-description: Learn how to configure the Video Component.
uuid: f4755a13-08ea-4096-a951-46a590f8d766
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: a1efef3c-0e4b-4a17-bcad-e3cc17adbbf7
exl-id: 46d0765d-fb77-4332-8fbb-5bd2abcd6806
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '452'
ht-degree: 0%

---

# Konfigurera komponenten Video {#configure-the-video-component}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

The [Videokomponent](/help/sites-authoring/default-components-foundation.md#video) Med kan du placera ett fördefinierat OOTB-videoelement (som inte finns i kartongen) på sidan.

Administratören måste [Installera och konfigurera AEM](#install-ffmpeg) separat. De kan också [Konfigurera videoprofiler](#configure-video-profiles) för användning med HTML5-element.

>[!CAUTION]
>
>Den här komponenten förväntas inte längre fungera utan omfattande anpassning på projektnivå.

## Konfigurera videoprofiler {#configure-video-profiles}

Du kanske vill definiera videoprofiler som ska användas för HTML5-element. De som väljs här används i ordning. Använd [Designläge](/help/sites-authoring/default-components-designmode.md) (Endast Classic UI) och välj **[!UICONTROL Profiles]** tab:

![chlimage_1-317](assets/chlimage_1-317.png)

Du kan också konfigurera designen av videokomponenterna och -parametrarna för [!UICONTROL Playback], [!UICONTROL Flash]och [!UICONTROL Advanced].

## Installera och konfigurera AEM {#install-ffmpeg}

Video Component (videokomponenten) använder öppen källkod-produkten från tredje part för korrekt omkodning av videoklipp som kan hämtas från [https://ffmpeg.org/](https://ffmpeg.org/). När du har installerat mpeg måste du konfigurera AEM att använda en viss ljudkodek och specifika körningsalternativ.

**Så här installerar du FFmpeg för din plattform**:

* **I Windows:**

   1. Hämta den kompilerade binärfilen som `ffmpeg.zip`
   1. Zippa upp i en mapp.
   1. Ange systemmiljövariabeln `PATH` till `<*your-ffmpeg-locatio*n>\bin`
   1. Starta om AEM.

* **På Mac OS X:**

   1. Installera Xcode ([https://developer.apple.com/technologies/tools/xcode.html](https://developer.apple.com/technologies/tools/xcode.html))
   1. Installera XQuartz/X11.
   1. Installera MacPorts ([https://www.macports.org/](https://www.macports.org/))
   1. Kör följande kommando i konsolen och följ instruktionerna:

      `sudo port install ffmpeg`

      `FFmpeg` måste vara i `PATH` så AEM kan hämta det via kommandoraden.

* **Använda den förkompilerade versionen för OS X 10.6:**

   1. Ladda ned den förkompilerade versionen.
   1. Extrahera den till `/usr/local` katalog.
   1. Kör från terminal:

      `sudo ln -s /usr/local/Cellar/ffmpeg/0.6/bin/ffmpeg /usr/bin/ffmpeg`

**Konfigurera AEM**:

1. Öppna [!UICONTROL CRXDE Lite] i webbläsaren. ([http://localhost:4502/crx/de](http://localhost:4502/crx/de))
1. Välj `/libs/settings/dam/video/format_aac/jcr:content` nod och kontrollera att nodegenskaperna är följande:

   * audioCodec:

      ```
       aac
      ```

   * customArgs:

      ```
       -flags +loop -me_method umh -g 250 -qcomp 0.6 -qmin 10 -qmax 51 -qdiff 4 -bf 16 -b_strategy 1 -i_qfactor 0.71 -cmp chroma -subq 8 -me_range 16 -coder 1 -sc_threshold 40 -b-pyramid normal -wpredp 2 -mixed-refs 1 -8x8dct 1 -fast-pskip 1 -keyint_min 25 -refs 4 -trellis 1 -direct-pred 3 -partitions i8x8,i4x4,p8x8,b8x8
      ```

1. Om du vill anpassa konfigurationen skapar du en övertäckning i `/apps/settings/` nod och flytta samma struktur under `/conf/global/settings/` nod. Det kan inte redigeras i `/libs` nod. Till exempel för att täcka över bana `/libs/settings/dam/video/fullhd-bp`, skapa på `/conf/global/settings/dam/video/fullhd-bp`.

   >[!NOTE]
   >
   >Lägg över och redigera hela profilnoden och inte bara den egenskap som behöver ändras. Sådana resurser löses inte via SlingResourceMerger.

1. Om du har ändrat någon av egenskaperna klickar du på **[!UICONTROL Save All]**.

>[!NOTE]
>
>Arbetsflödesmodeller från OTB bevaras inte när du uppgraderar AEM. Adobe rekommenderar att du kopierar OOTB-arbetsflödesmodeller innan du redigerar dem. Kopiera till exempel OTB DAM Update Asset-modellen innan du redigerar omkodningssteget för MPEG i DAM Update Asset-modellen för att välja videoprofilnamn som fanns före uppgraderingen. Sedan kan du täcka över `/apps` nod som AEM kan hämta anpassade ändringar i OTB-modellen.
