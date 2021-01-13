---
title: Konfigurera komponenten Video
seo-title: Konfigurera komponenten Video
description: Lär dig hur du konfigurerar videokomponenten.
seo-description: Lär dig hur du konfigurerar videokomponenten.
uuid: f4755a13-08ea-4096-a951-46a590f8d766
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: a1efef3c-0e4b-4a17-bcad-e3cc17adbbf7
translation-type: tm+mt
source-git-commit: 201ddb888e6f1797bf2b84c5719625ebf87ddc82
workflow-type: tm+mt
source-wordcount: '427'
ht-degree: 0%

---


# Konfigurera videokomponenten {#configure-the-video-component}

Med [videokomponenten](/help/sites-authoring/default-components-foundation.md#video) kan du placera ett fördefinierat OTB-videoelement (körklar) på sidan.

För att korrekt omkodning ska ske måste administratören [installera MPEG och konfigurera AEM](#install-ffmpeg) separat. De kan även [konfigurera dina videoprofiler](#configure-video-profiles) för användning med HTML5-element.

>[!CAUTION]
>
>Den här komponenten förväntas inte längre fungera utan omfattande anpassning på projektnivå.

## Konfigurera videoprofiler {#configure-video-profiles}

Du kanske vill definiera videoprofiler som ska användas för HTML5-element. De som väljs här används i ordning. Använd [Designläge](/help/sites-authoring/default-components-designmode.md) (endast Classic UI) och välj fliken **[!UICONTROL Profiles]** för att få åtkomst:

![chlimage_1-317](assets/chlimage_1-317.png)

Du kan också konfigurera designen för videokomponenterna och -parametrarna för [!UICONTROL Playback], [!UICONTROL Flash] och [!UICONTROL Advanced].

## Installera MPEG och konfigurera AEM {#install-ffmpeg}

Video Component (videokomponenten) använder öppen källkod-produkten från tredje part för korrekt omkodning av videoklipp som kan hämtas från [https://ffmpeg.org/](https://ffmpeg.org/). När du har installerat mpeg måste du konfigurera AEM att använda en viss ljudkodek och specifika körningsalternativ.

**Så här installerar du FFmpeg för din plattform**:

* **I Windows:**

   1. Hämta den kompilerade binärfilen som `ffmpeg.zip`
   1. Zippa upp i en mapp.
   1. Ange systemmiljövariabeln `PATH` till `<*your-ffmpeg-locatio*n>\bin`
   1. Starta om AEM.

* **I Mac OS X:**

   1. Installera Xcode ([https://developer.apple.com/technologies/tools/xcode.html](https://developer.apple.com/technologies/tools/xcode.html))
   1. Installera XQuartz/X11.
   1. Installera MacPorts ([https://www.macports.org/](https://www.macports.org/))
   1. Kör följande kommando i konsolen och följ instruktionerna:

      `sudo port install ffmpeg`

      `FFmpeg` måste vara i  `PATH` så att AEM kan hämta det via kommandoraden.

* **Använda den förkompilerade versionen för OS X 10.6:**

   1. Ladda ned den förkompilerade versionen.
   1. Extrahera den till katalogen `/usr/local`.
   1. Kör från terminal:

      `sudo ln -s /usr/local/Cellar/ffmpeg/0.6/bin/ffmpeg /usr/bin/ffmpeg`

**Så här konfigurerar du AEM**:

1. Öppna [!UICONTROL CRXDE Lite] i webbläsaren. ([http://localhost:4502/crx/de](http://localhost:4502/crx/de))
1. Markera noden `/libs/settings/dam/video/format_aac/jcr:content` och kontrollera att nodegenskaperna är följande:

   * audioCodec:

      ```
       aac
      ```

   * customArgs:

      ```
       -flags +loop -me_method umh -g 250 -qcomp 0.6 -qmin 10 -qmax 51 -qdiff 4 -bf 16 -b_strategy 1 -i_qfactor 0.71 -cmp chroma -subq 8 -me_range 16 -coder 1 -sc_threshold 40 -b-pyramid normal -wpredp 2 -mixed-refs 1 -8x8dct 1 -fast-pskip 1 -keyint_min 25 -refs 4 -trellis 1 -direct-pred 3 -partitions i8x8,i4x4,p8x8,b8x8
      ```

1. Om du vill anpassa konfigurationen skapar du en övertäckning i noden `/apps/settings/` och flyttar samma struktur under noden `/conf/global/settings/`. Det kan inte redigeras i noden `/libs`. Om du till exempel vill täcka över sökvägen `/libs/settings/dam/video/fullhd-bp` skapar du den på `/conf/global/settings/dam/video/fullhd-bp`.

   >[!NOTE]
   >
   >Lägg över och redigera hela profilnoden och inte bara den egenskap som behöver ändras. Sådana resurser löses inte via SlingResourceMerger.

1. Om du har ändrat någon av egenskaperna klickar du på **[!UICONTROL Save All]**.

>[!NOTE]
>
>Arbetsflödesmodeller från OTB bevaras inte när du uppgraderar AEM. Adobe rekommenderar att du kopierar OOTB-arbetsflödesmodeller innan du redigerar dem. Kopiera till exempel OTB DAM Update Asset-modellen innan du redigerar omkodningssteget för MPEG i DAM Update Asset-modellen för att välja videoprofilnamn som fanns före uppgraderingen. Sedan kan du täcka över noden `/apps` så att AEM kan hämta anpassade ändringar i OTB-modellen.

