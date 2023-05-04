---
title: Länka URL:er till ditt webbprogram
seo-title: Linking URLs to your Web Application
description: Länka URL:er till webbprogrammet i dynamiska medier
seo-description: How to link URLs to your web application in dynamic media
uuid: cf599e66-b1f9-40c0-b572-cea19f2e6793
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: d12e6ea3-aaf4-4672-9679-3c16c76d7d5b
exl-id: e076349d-8b1a-487f-b982-9440d7de13b9
feature: Configuration
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1244'
ht-degree: 8%

---

# Länka URL:er till ditt webbprogram {#linking-urls-to-your-web-application}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Dina webbplatser och tillämpningar har åtkomst till Dynamic Media tjänster via URL-samtal. När du har publicerat en resurs aktiverar Dynamic Media en URL-sträng som refererar till resursen. Du kan klistra in dessa URL:er i en webbläsare för testning.

Du länkar bara till URL-adresser om du är *not* med AEM som WCM. Länkning/inbäddning används när du vill leverera en videospelare som ett popup-fönster eller modalt fönster. Om du använder AEM som WCM, [du lägger till resurserna direkt på sidan.](adding-dynamic-media-assets-to-pages.md)

Om du vill placera dessa URL-strängar på dina webbsidor och i dina program kopierar du dem från Dynamic Media.

>[!NOTE]
>
>URL-strängar är bara tillgängliga för dynamiska återgivningar av resurser. De är för närvarande inte tillgängliga för statiska resurser som finns i DAM och inte för den dynamiska medieservern. URL-knappen visas inte för återgivningar som är statiska.

Se även [Bädda in video- eller bildvisningsprogrammet på en webbsida.](embed-code.md)

Se även [Länka YouTube URL:er till ditt webbprogram.](video.md)

Se även [Leverera optimerade bilder för en responsiv webbplats.](responsive-site.md)

Se även [Överför resurser.](managing-assets-touch-ui.md#uploading-assets)

## Hämta en URL för en resurs {#obtaining-a-url-for-an-asset}

Du kan hämta en URL-sträng som genereras av en bildförinställning eller en visningsförinställning. När du har kopierat URL:en markeras den i Urklipp så att du kan klistra in den på sidorna på webbplatsen eller i programmet.

>[!NOTE]
>
>URL:en är inte tillgänglig för kopiering förrän du har publicerat den valda resursen. Dessutom måste du även publicera visningsförinställningen eller bildförinställningen.
>
>Se [Publicera resurser](publishing-dynamicmedia-assets.md).
>
>Se [Förinställningar för publiceringsvisningsprogram](managing-viewer-presets.md#publishing-viewer-presets).
>
>Se [Förinställningar för publicering](managing-image-presets.md#publishing-image-presets).

Du kan hämta en URL-sträng på flera olika sätt. Stegen nedan visar dock bara en metod som du kan använda.

**Så här hämtar du en URL för en resurs**:

1. Navigera till *publicerad* resurs vars förinställda URL eller URL för visningsförinställning som du vill kopiera och tryck på resursen för att öppna den.

   Kom ihåg att URL:er endast går att kopiera *efter* att du har *publicerat* resurserna. Dessutom måste visningsförinställningen eller bildförinställningen också publiceras.

   Se [Publicera resurser.](publishing-dynamicmedia-assets.md)

   Se [Förinställningar för publiceringsvisningsprogram](managing-viewer-presets.md#publishing-viewer-presets).

   Se [Förinställningar för publicering](managing-image-presets.md#publishing-image-presets).

1. Gör något av följande beroende på vilken resurs du valt:

   * Om du har valt en bild trycker du på **[!UICONTROL Renditions]**.

      Under **[!UICONTROL Dynamic]** om du vill visa återgivningen i den högra bildrutan trycker du på ett förinställningsnamn. Du kan behöva rulla i listan Återgivningar för att se den dynamiska rubriken.

      Längst ned i den vänstra listen trycker du på **[!UICONTROL URL]**.

      ![chlimage_1-270](assets/chlimage_1-270.png)

   * Om du har valt en snurruppsättning, en bilduppsättning, en Carousel-uppsättning eller en video trycker du på **[!UICONTROL Viewers]**.

      Tryck på ett namn på en visningsförinställning i den vänstra listen. En förhandsgranskning av uppsättningen eller videon öppnas på en separat sida.

      Tryck på längst ned i den vänstra listen **[!UICONTROL URL]**.

      ![chlimage_1-271](assets/chlimage_1-271.png)

1. Markera och kopiera texten till webbläsaren för att förhandsgranska resursen eller lägga till den på webbinnehållssidan.

   Tryck på knappen **[!UICONTROL X]** eller trycka **[!UICONTROL Close]**.

## Hämta en URL för en statisk resurs {#obtaining-a-url-for-a-static-asset}

Dynamic Media stöder leverans av statiskt material, som är ytterligare material utöver bara bilder och video. Statiska medieformat som stöds för leverans är bland annat följande:

* Animerad GIF
* Ljudfiler
* CSS
* JavaScript (när ditt företag är konfigurerat med sin egen domän)
* PDF
* SVG
* XML
* ZIP

**Hämta en URL för en statisk resurs**:

1. Navigera till den *publicerade *statiska resurs vars URL du vill kopiera och öppna den genom att trycka på resursen.

   Kom ihåg att URL-adresser endast är tillgängliga för kopiering *efter* du har först *publicerad* den statiska resursen.

   Se [Publicera resurser.](publishing-dynamicmedia-assets.md)

1. Använd någon av följande metoder för att hämta URL:en för den publicerade statiska resursen:

   * `The URL of the published static is the following:`

      * `https://*<server_name>*/is/content/*<company_name>*/*<static_asset_filename>*.*<extension>*`

         Till exempel, `https://aem.com/is/content/adobe/image.gif`.
   * klicka **[!UICONTROL Asset > Dynamic Renditions]**, tryck sedan på en dynamisk återgivning av den statiska resursen och kopiera URL:en.

      Ändra den kopierade URL-adressen som ska användas `is/content` i banan i stället för `is/image/`.


## Hämta en video-URL för en publicerad videoåtergivning {#obtaining-a-video-url-for-a-published-video-rendition}

1. I AEM navigerar du till **[!UICONTROL Tools > Deployment > Cloud > Cloud Services]**.
1. På sidan **[!UICONTROL Cloud Services]** bläddrar du nedåt till rubriken **[!UICONTROL Dynamic Media Cloud Services]** och trycker sedan på **[!UICONTROL Show Configurations]**.
1. Under **[!UICONTROL Available Configurations]** trycker du på namnet på den konfiguration du vill använda.

1. På **[!UICONTROL Dynamic Media Cloud Settings]** sida, under **[!UICONTROL Video Service URL]**, kopierar hela URL-sökvägen. Du behöver den kopierade URL-sökvägen senare i stegen.

   URL-sökvägen kan till exempel se ut ungefär så här:

   `https://s7athens.macromedia.com:9090/DMGateway/`

   (Banan ovan är endast avsedd som illustration. det är inte den faktiska sökvägen som du kopierar.)

1. Under **[!UICONTROL Registration ID]** kopierar du det kundnamn som finns i den sista delen av ID:t.

   Om registrerings-ID till exempel var `87654321|MyCompany`, blir kundens namn `MyCompany`.

1. Knacka i det övre vänstra hörnet av sidan **[!UICONTROL Cloud Service]s** och sedan trycka på ikonen AEM och navigera till **[!UICONTROL General > CRXDE Lite]**.
1. Kopiera ned hela videouppdateringssökvägen från JCR-filen (Java Content Repository).

   Videons återgivningssökväg kan till exempel se ut ungefär så här:

   `/_renditions_/0bd/0bd28743-a616-4fe6-92aa-6eae7c2112f/avs/Momentum_1080-0x720-2600k.mp4`

   (Banan ovan är endast avsedd som illustration. det är inte den faktiska sökvägen som du kopierar.)

1. Ordna den kopierade informationen i följande ordning för att skapa en fullständig URL-sökväg:

   `<Video_Service_URL>/public/<Customer_name_from_Registration_ID>/<Video_rendition_path>`

   Om du till exempel använder exempelsökvägarna och exempelkundnamnet från stegen ovan, visas den fullständiga sökvägen enligt följande:

   `https://s7athens.macromedia.com:9090/DMGateway/public/MyCompany/_renditions_/0bd/0bd28743-a616-4fe6-92aa-6eae7c2112ff/avs/Momentum_1080-0x720-2600k.mp4`

   Det här är den fullständiga video-URL:en för en publicerad videoåtergivning.

## Hämta en video-URL för adaptiv direktuppspelning (HLS) {#obtaining-a-video-url-for-adaptive-streaming-hls}

1. I AEM navigerar du till **[!UICONTROL Tools > Deployment > Cloud > Cloud Services]**.
1. På sidan **[!UICONTROL Cloud Services]** bläddrar du nedåt till rubriken **[!UICONTROL Dynamic Media Cloud Services]** och trycker sedan på **[!UICONTROL Show Configurations]**.
1. Under **[!UICONTROL Available Configurations]** trycker du på namnet på den konfiguration du vill använda.
1. På **[!UICONTROL Dynamic Media Cloud Services Settings]** gör du följande på sidan:

   * Under **[!UICONTROL Video Service URL]**, kopierar hela URL-sökvägen. Du behöver den kopierade URL-sökvägen senare i dessa steg. URL-sökvägen kan till exempel se ut ungefär så här:

   `https://gateway-na.assetsadobe.com/DMGateway/`

   (Banan ovan är endast avsedd som illustration. det är inte den faktiska sökvägen som du kopierar.)

   * Under **[!UICONTROL Registration ID]** kopierar du det kundnamn som finns i den sista delen av ID:t. Du behöver det kopierade kundnamnet längre fram i de här stegen.

      Om registrerings-ID till exempel var `87654321|demoCo`, det kundnamn du kopierar är `demoCo`.


1. Kopiera respektive protokollväljare baserat på vilket videoleveransprotokoll du använder. Du behöver den kopierade protokollväljaren senare i dessa steg.

   | Videoleveransprotokoll som du använder | Protokollväljare som ska användas |
   |---|---|
   | HTTP <br> Om du använder HTTP (osäker videoleverans) måste du ändra https till http i URL-värdet för videotjänsten som du kopierade tidigare. | `public/` |
   | HTTPS | `public-ssl/` |

1. Kopiera den fullständiga sökvägen till videomaterialet i AEM, som bearbetats av Dynamic Media. Du behöver den här kopierade sökvägen för videoresurser senare i dessa steg.

   Till exempel:

   `/content/dam/marketing/MyVideo.mp4`

1. Kombinera alla delar du kopierat tidigare och skapa en sträng i följande ordning:

   &lt; `video service URL`>&lt; `protocol selector`>&lt; `customer name`>&lt; `video asset path`>

   Om du till exempel använder den kopierade informationen från exemplen i de här stegen ser strängen ut så här:

   `https://gateway-na.assetsadobe.com/DMGateway/public-ssl/demoCo/content/dam/marketing/MyVideo.mp4`

1. Fyll i URL:en genom att lägga till `.m3u8` till strängens slut. Lägg till exempel `.m3u8` till strängen från det föregående steget visas den fullständiga URL-sökvägen enligt följande:

   `https://gateway-na.assetsadobe.com/DMGateway/public-ssl/demoCo/content/dam/marketing/MyVideo.mp4.m3u8`

## Använd HTTP/2 för att leverera Dynamic Media-material {#using-http-to-deliver-your-dynamic-media-assets}

HTTP/2 är det nya, uppdaterade webbprotokollet som förbättrar kommunikationen mellan webbläsare och servrar. Det ger snabbare överföring av information och minskar mängden processorkraft som behövs. Dynamic Media-material kan nu levereras via HTTP/2 vilket ger bättre respons och laddningstider.

Se [HTTP2-leverans av innehåll](http2.md) om du vill ha fullständig information om hur du kommer igång med HTTP/2 med ditt Dynamic Media-konto.
