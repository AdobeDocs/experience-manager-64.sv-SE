---
title: Hantera förinställningar för Dynamic Media Viewer
seo-title: Hantera förinställningar för Dynamic Media Viewer
description: Skapa och hantera förinställningar för visningsprogrammet för Dynamic Media
seo-description: Skapa och hantera förinställningar för visningsprogrammet för Dynamic Media
uuid: 31ef7a4e-2053-43b5-ac6c-cdc4b30c3914
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: e78bb08a-a923-4399-b3f7-13aa4b7994d5
legacypath: /content/docs/en/aem/6-0/administer/integration/dynamic-media/viewer-presets
translation-type: tm+mt
source-git-commit: 211d6f13eba0000bbab92e0bd014420f5ca88e4d

---


# Managing Dynamic Media viewer presets {#managing-viewer-presets}

En förinställning för Dynamic Media Viewer är en samling inställningar som bestämmer hur användare visar mediefiler på datorskärmar och mobila enheter. Om du är administratör kan du skapa visningsförinställningar. Inställningarna är tillgängliga för en array med visningskonfigurationsalternativ. Du kan till exempel ändra visningsprogrammets visningsstorlek eller zoombeteende.

Instruktioner om hur du skapar och anpassar egna HTML5-visningsförinställningar finns i *Adobe Scene7 HTML5 Viewer SDK*. SDK är tillgängligt på IS-publiceringsservern som är inbäddad i SDK:n. Varje biblioteksversion har en egen SDK-dokumentation.

Path: `<scene7_domain>/s7sdk/<library_version>/docs/jsdocs/index.html`.\
Exempel: 3.5 SDK: [https://s7d1.scene7.com/s7sdk/3.5/docs/jsdoc/index.html](https://s7d1.scene7.com/s7sdk/3.5/docs/jsdoc/index.html)

Se även [Adobe Viewer Reference Guide](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/).

I det här avsnittet beskrivs hur du skapar, redigerar och hanterar visningsprogramförinställningar. Du kan använda en visningsförinställning för en resurs när du vill förhandsgranska den. Se [Använda visningsförinställningar](viewer-presets.md).

>[!NOTE]
>
>Tänk på att redigering av *fördefinierade förinställningar* för visningsprogram som är färdiga att användas inte är ett scenario som stöds. Om du försöker redigera en visningsförinställning som inte är klar uppmanas du att spara visningsförinställningen med ett nytt namn.

## Tangentbordstillgänglighet för tittare {#keyboard-accessibility-for-viewers}

Alla färdiga visningsprogram har stöd för tangentbordstillgänglighet.

Se även [Tangentbordstillgänglighet och -navigering](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_keyboard_accessibility.html).

## Managing Dynamic Media viewer presets {#managing-presets}

Du kan lägga till, redigera, ta bort, publicera, avpublicera och förhandsgranska visningsförinställningar i AEM genom att trycka på **[!UICONTROL Verktyg > Resurser > Visningsförinställningar]**.

![verktyg-resurser](assets/tools-assets.png)

>[!NOTE]
>
>Som standard visas 15 visningsförinställningar när du väljer visningsprogram i detaljvyn för en resurs. Du kan öka den här gränsen. Se [Öka antalet visningsförinställningar som visas](#increasing-the-number-of-viewer-presets-that-display).

## Stöd för visningsprogram för responsiva webbsidor {#viewer-support-for-responsive-designed-web-pages}

Olika webbsidor har olika behov. Ibland kanske du vill ha en webbsida som innehåller en länk som öppnar HTML5 Viewer i ett separat webbläsarfönster. I andra fall kan det vara nödvändigt att bädda in HTML5 Viewer direkt på värdsidan. I det senare fallet kan webbsidan ha en statisk layout. Den kan också vara *responsiv* och visas på olika enheter eller i olika webbläsarfönsterstorlekar. För att tillgodose dessa behov har alla fördefinierade färdiga HTML5-visningsprogram som medföljer Dynamic Media stöd för både statiska webbsidor och responsiva webbsidor.

Mer information om hur du bäddar in responsiva visningsprogram på dina webbsidor finns i [Responsive Image Library](https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/is_api/c_about_responsive_static_image_library.html) i API-hjälpen *för* Scene7 Image Serving.

>[!NOTE]
>
>Observera att du måste publicera alla användningsklara visningsprogram innan du använder dem första gången.\
>Se Förinställningar för [publiceringsvisningsprogrammet.](#publishing-viewer-presets)

## Systemkompatibilitet för visningsförinställningar {#viewer-preset-system-compatibility}

Alla färdiga visningsförinställningar som medföljer Dynamic Media är helt kompatibla med följande system:

* Stationära datorer
* Apple iPhone
* Apple iPad
* Android Smartphone
* Android-surfplatta
* För video finns ytterligare stöd för MP4-uppspelning för [Blackberry](https://developer.blackberry.com/devzone/develop/supported_media/bb_media_support_at_a_glance.html#kba1328730952678) och [Windows Phone](https://msdn.microsoft.com/library/windows/apps/ff462087%28v=vs.105%29.aspx).

### Multimedietyper för visningsförinställningar {#rich-media-types-for-viewer-presets}

Administratörer kan lägga till och anpassa följande typer av multimedia när de skapar nya visningsförinställningar.

| Multimedietyper | Beskrivning |
|:---|:---|
| **Carousel Set** | Aktiveringspunkter, bildscheman eller båda läggs till i en serie med två eller flera bilder. Kunden kan panorera bilderna åt vänster eller höger och sedan klicka på en hotspot på en bild för mer information eller för att köpa direkt från en webbplats kategori, hemsida eller landningssidor. |
| **Utfällbar zoom** | Visar en andra bild av det zoomade området bredvid originalbilden. Det finns inga kontroller att använda - användarna flyttar markeringen över det område de vill visa. |
|  | När du fastställer den fullständiga bandbreddsanvändningen för det här visningsprogrammet bör du tänka på att både huvudbilden och den utfällbara bilden visas i visningsprogrammet. Huvudbildens storlek (scenens bredd och höjd) och zoomfaktorn bestämmer den utfällbara bildens storlek. Om du vill förhindra att den utfällbara filstorleken blir för stor ska du balansera dessa två värden: om du har en stor huvudbildstorlek, sänker du zoomfaktorn. (Utfällbar bredd och Utfällbar höjd bestämmer storleken på det utfällbara fönstret, men inte storleken på den utfällbara bild som visas i visningsprogrammet.) |
|  | Om huvudbildens storlek till exempel är 350 x 350 pixlar, med zoomfaktorn 3, blir den utfällbara bilden 1 050 x 1 050 pixlar. Om huvudbildstorleken är 300 x 300 pixlar, med zoomfaktorn 4, är den utfällbara bilden 1 200 x 1 200 pixlar. Beroende på kvalitetsinställningen för JPEG (rekommenderade inställningar är mellan 80 och 90) kan du minska filstorleken avsevärt. Rekommenderade zoomningsfaktorer är 2,5 till 4, beroende på storleken på huvudbilden. |
| **Textbunden zoom** | Visar en bild av det zoomade området i det ursprungliga visningsprogrammet. Det finns inga kontroller att använda. Användarna flyttar markeringen över det område de vill visa. |
| **Bilduppsättning** | I visningsprogrammet för bilduppsättningen kan användare visa olika vyer eller färgvariationer för ett objekt genom att klicka på en miniatyrbild. Det här visningsprogrammet har även zoomverktyg som gör att du kan granska bilder noggrant. |
| **Interaktiv bild** | Aktiveringspunkter läggs till i delar av en bild som en kund sedan kan klicka på för mer information eller för att köpa direkt från en webbplats kategori, hemsida eller landningssidor. |
| **Interaktiv video** | Miniatyrbilder läggs till i tidslinjesegment i en video som en kund sedan kan klicka på för mer information eller för att köpa direkt från en webbplats kategori, hemsida eller landningssidor. |
| **Blandade media** | Visar olika typer av media i ett och samma visningsprogram. Du kan inkludera snurruppsättningar, bilduppsättningar, bilder och videoklipp. |
| **Panoramabild** | Visningsprogrammen Panoramabild och PanoramicVR återger sfäriska panoramabilder så att användarna kan se dem i ett 360-gradersrum, på en plats eller i ett landskap. |
|  | För att en överförd bild ska kvalificeras som ett sfäriskt panorama måste den ha antingen ett eller båda av följande: <ul><li>Proportionerna 2:1.</li><li>Taggad med nyckelorden ekvirektangulärt, sfäriskt och panorama, eller sfäriskt och panorama. Se [Använda taggar](../sites-authoring/tags.md).</li></ul> |
|  | Både proportioner och nyckelordskriterier gäller för panoramaresurser för sidan med resursinformation och WCM-komponenten &quot;Panoramic Media&quot;. |
|  | Viktigt: Det här visningsprogrammet är bara tillgängligt i läget Dynamic Media - Scene7. |
| **Snurra uppsättning** | Ger flera vyer av en bild så att användare kan vrida objektet för att undersöka olika sidor och vinklar. |
| **Video** | Spelar upp video med strömning med progressiv eller adaptiv bithastighet. Med adaptiv bithastighetsströmning utförs automatiskt enhets- och bandbreddsidentifiering för att leverera rätt kvalitetsvideo i rätt format. |
| **Lodrät zoomning** | Med Lodrät zoomning kan du maximera visningen av produktbilder och ge användarna bästa möjliga återgivning av en produkt. Den lodräta placeringen av färgrutor gör följande: <ul><li>Ser till att färgrutorna är över vecket. Med vågräta färgrutor var färgrutorna inte synliga förrän användaren rullade nedåt på sidan, beroende på  skärmstorlek. Genom att placera färgrutorna lodrätt i visningsprogrammet ser du till att de visas oavsett användarens skärmstorlek.</li><li>Maximerar storleken på huvudbilden.  Med vågräta färgrutor måste du reservera utrymme på sidan för att se till att de är synliga. Den här placeringen minskade storleken på huvudbilden. Om du har en lodrät färgrutelayout behöver du dock inte tilldela det här utrymmet. Därför kan du maximera huvudbildstorleken.</li></ul> |
| **Zoomning** | Låter användarna zooma in i området genom att klicka på det. Användare kan klicka på kontroller för att zooma in, zooma ut och återställa bilden till standardstorleken. |

## Lista med färdiga visningsförinställningar {#list-of-out-of-the-box-viewer-presets}

I följande tabell visas alla fördefinierade, färdiga visningsförinställningar som medföljer Dynamic Media.

Se även Exempel på [visningsprogramreferensbibliotek](https://marketing.adobe.com/resources/help/en_US/s7/vlist/vlist.html) och [livedemonstrationer](https://landing.adobe.com/en/na/dynamic-media/ctir-2755/live-demos.html).

Information om vilka webbläsare och operativsystemversioner som stöds för visningsprogram finns i Viewer Release Notes.

Se Versionsinformation *för* visningsprogram i innehållsförteckningen i [referenshandboken](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/)för visningsprogram.

>[!NOTE]
>
>Alla färdiga visningsförinställningar i Dynamic Media är redan aktiverade (aktiverade), men du måste publicera dem.\
>Se [Publicera förinställningar](#publishing-viewer-presets)för visningsprogram.
>
>Alla nya förinställningar för visningsprogram som du skapar och lägger till måste vara både aktiverade *och* publicerade.\
>Se [Aktivera eller inaktivera visningsförinställningar](#activating-or-deactivating-viewer-presets) och [Publicera visningsförinställningar](#publishing-viewer-presets).

| Förinställningsrubrik för visningsprogram | Typ | CSS-filnamn |
|:---|:---|:---|
| Carousel_Doted_dark | Carousel_Set | html5_carouselviewer_dotted_dark.css |
| Carousel_Doted_light | Carousel_Set | html5_carouselviewer_dotted_light.css |
| Carousel_Numeric_dark | Carousel_Set | html5_carouselviewer_numeric_dark.css |
| Carousel_Numeric_light | Carousel_Set | html5_carouselviewer_numeric_light.css |
| Utfällbar | Flyout_Zoom | html5_flyoutviewer.css |
| ImageSet_dark | Bilduppsättning | html5_zoomviewer_dark.css |
| ImageSet_light | Bilduppsättning | html5_zoomviewer_light.css |
| InlineMixedMedia_dark | Mixed_Media | html5_inlinemixedmediaviewer_dark.css |
| InlineMixedMedia_light | Mixed_Media | html5_inlinemixedmediaviewer_light.css |
| InlineZoom | Flyout_Zoom | html5_inlinezoomviewer.css |
| MixedMedia_dark | Mixed_Media | html5_mixedmediaviewer_dark.css |
| MixedMedia_light | Mixed_Media | html5_mixedmediaviewer_light.css |
| Panoramabild | Panorama_bild | html5_panoramicimage.css |
| PanoramabildVR | Panorama_bild | html5_panoramicimage.css |
| Shoppable_Banner | Interactive_image | html5_interactiveImage.css |
| Shoppable_Video_dark | Interactive_Video | html5_interactive_videoviewer_dark.css |
| Shoppable_Video_light | Interactive_Video | html5_interactive_videovewer_light.css |
| SpinSet_dark | Spin_mängd | html5_spinviewer_dark.css |
| SpinSet_light | Spin_mängd | html5_spinviewer_light.css |
| Video (har stöd för undertexter) | Video | html5_videoviewer.css |
| Video_social (inkluderar stöd för undertexter och sociala medier) | Video | html5_videoviewersocial.css |
| Zoom_dark | Zoomning | html5_basiczoomviewer_dark.css |
| Zoom_light | Zoomning | html5_basiczoomviewer_light.css |
| ZoomVertical_dark | Lodrät_zoom | html5_zoomverticalviewer_dark.css |
| ZoomVertical_light | Lodrät_zoom | html5_zoomverticalviewer_light.css |

### Rörelsematris för mobilvisningsprogram som stöds {#supported-mobile-viewers-gestures-matrix}

Följande tabell visar vilka mobilvisningsgester som stöds på iOS-, Android 2.x- och Android 3.x-enheter.

| Gesture | Utfällbar zoom | Zoomning | Snurra |
|---|---|---|---|
| **Dra** | Panoreringar | Panoreringar | Panoreringar |
| **Tryck** | Visar utfällbart fönster | Visar eller döljer användargränssnittet | Visar eller döljer användargränssnittet |
| **Dubbelknacka** | Gäller inte | Zoomar in eller återställer | Zoomar in eller återställer |
| **Knipning öppen** | Gäller inte | Zoomar in (endast iOS och Android 3x) | Zoomar in (endast iOS och Android 3x) |
| **Knipning - stäng** | Gäller inte | Zoomar ut (endast iOS och Android 3x) | Zoomar ut (endast iOS och Android 3x) |
| **Svep** | Rullningslist | Rulla bilder | Spins |
| **Snurra** | Rullningslist | Rulla bilder | Spins |

## Öka antalet förinställningar för Dynamic Media Viewer som visas {#increasing-the-number-of-viewer-presets-that-display}

AEM visar en mängd olika förinställningar för visningsprogram när du visar resurser från **[!UICONTROL Detaljvy > Visare]**. Du kan öka eller minska antalet visningsprogram som visas.

**Så här ökar du antalet förinställningar för Dynamic Media Viewer som visas**:

1. Navigera till **[!UICONTROL CRXDE Lite]** ([http://localhost:4502/crx/de](http://localhost:4502/crx/de)).
1. Navigera till noden med visningsförinställningar på `/libs/dam/gui/coral/content/commons/sidepanels/viewerpresets/viewerpresetslist`

   ![chlimage_1-221](assets/chlimage_1-221.png)

1. I **[!UICONTROL limit]** -egenskapen ändrar du **[!UICONTROL Value]**, som är inställt på 15 som standard, till önskat tal.
1. Navigera till datakällan för visningsförinställningen på `/libs/dam/gui/coral/content/commons/sidepanels/viewerpresets/viewerpresetslist/datasource`

   ![chlimage_1-222](assets/chlimage_1-222.png)

1. I **[!UICONTROL limit]** -egenskapen ändrar du talet till önskat tal, till exempel `{empty requestPathInfo.selectors[1] ? "20" : requestPathInfo.selectors[1]}`
1. Tryck på **[!UICONTROL Spara alla]**.

## Skapa en ny förinställning för Dynamic Media Viewer {#creating-a-new-viewer-preset}

Genom att skapa visningsförinställningar kan du använda olika inställningar för att visa och interagera med resurser. Du behöver dock inte skapa nya förinställningar för visningsprogrammet. Om du vill kan du använda standardförinställningarna för visningsprogram som redan finns i AEM Assets.

Om du väljer att skapa en ny visningsförinställning aktiveras visningsprogrammets läge automatiskt (anges till **På**) på sidan **[!UICONTROL Visningsförinställningar]** när du har sparat den. Det här läget innebär att det är synligt i komponenten **[!UICONTROL Dynamic Media]** och komponenten **[!UICONTROL Interactive Media]** och när du förhandsgranskar en bild eller video.

Vissa visningsprogramförinställningar har exklusiva inställningar som kan påverka visningsprogrammets användning och allmänna beteende. Beroende på vilken visningsförinställning du skapar kan det vara bra att tänka på dessa speciella saker.

Se [Specialöverväganden när du skapar en interaktiv visningsprogramförinställning](#special-considerations-for-creating-an-interactive-viewer-preset).

Se [Specialöverväganden när du skapar en förinställning](#special-considerations-for-creating-a-carousel-banner-viewer-preset)för Carousel Banner Viewer.

**Så här skapar du en ny förinställning** för Dynamic Media Viewer:

1. I det övre vänstra hörnet av AEM trycker du på AEM-logotypen och sedan på **[!UICONTROL Verktyg > Resurser > Visningsförinställningar]** i den vänstra listen.

   ![visningsförinställningar](assets/viewerpresets.png)

1. På sidan **[!UICONTROL Förinställningar]** för visningsprogram trycker du på **[!UICONTROL Skapa]** i verktygsfältet.
1. I dialogrutan **[!UICONTROL Ny visningsförinställning]** anger du namnet på den nya förinställningen i fältet **[!UICONTROL Förinställningsnamn]** . Välj ett namn noggrant - de kan inte redigeras när du trycker på **[!UICONTROL Skapa]**.

   När du sparar förinställningen senare i de här stegen visas namnet på sidan Förinställningar för visningsprogram under kolumnrubriken **[!UICONTROL Förinställningstitel]** .

1. I listrutan **[!UICONTROL Multimedietyp]** väljer du den typ av visningsförinställning som du vill skapa och sedan trycker du på **[!UICONTROL Skapa]** längst upp till höger på sidan.

   Se [Multimedietyper för visningsförinställningar](#rich-media-types-for-viewer-presets).

1. Tryck på fliken **Utseende** på sidan **[!UICONTROL Redigera visningsförinställning]** .
1. Gör något av följande:

   * I listrutan **[!UICONTROL Markerad text]** väljer du en komponent vars visuella design du vill anpassa. Du kan också trycka på valfritt visuellt element i visningsprogrammet för att välja det för konfiguration.

      Med den visuella redigeraren kan du se vilken effekt en viss egenskap har på ett format. Du behöver bara ställa in eller justera en egenskap för att omedelbart se vilken effekt den har på visningsprogrammet med exemplet till vänster om redigeraren.

      CSS-formategenskaperna för varje typ av visningsförinställningar beskrivs i hjälpavsnittet Anpassa *&lt;viewer_name>* Viewer i [referenshandboken](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/)för visningsprogram.

      Om du till exempel skapar en visningsförinställning av den här typen `Mixed_Media`kan du läsa [Anpassa blandad medievisare](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_html5_mixedmedia_viewer_customizingviewer.html) för en lista och en beskrivning av varje egenskap.

   * Om du har definierat formatinställningar i en separat CSS-fil kan du överföra CSS-filen till AEM Resurser. Tryck på **[!UICONTROL Importera CSS]** under listrutan **[!UICONTROL Vald typ]** (du kan behöva rulla den visuella redigeraren uppåt för att se den) för att hitta den överförda CSS-filen och associera den med visningsförinställningen.

      När du importerar en CSS-fil kontrollerar den visuella redigeraren om rätt visningsmarkörer används i CSS. Om du till exempel skapar ett Zoom-visningsprogram måste alla CSS-regler som du importerar definieras med hjälp av visningsprogrammets klassnamn som `.s7mixedmediaviewer` definieras för ett överordnat visningsprogramelement.

      Du kan importera godtycklig, handgjord CSS så länge den definierar CSS-markörerna för ett visst visningsprogram. (CSS-markörer beskrivs i hjälpavsnittet Anpassa *&lt;visningsprogramnamn>* visningsprogram&quot; i [referenshandboken](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/)för visningsprogram. Om du till exempel vill läsa om CSS-markörer för Zoomvisningsprogrammet läser du [Anpassa zoomvisningsprogrammet](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/c_html5_20_zoom_viewer_customizingviewer.html).) Det är dock möjligt att den visuella redigeraren kanske inte förstår vissa CSS-värden. I sådana fall försöker den visuella redigeraren åsidosätta felen så att CSS fortfarande fungerar.
   >[!NOTE]
   >
   >Om du föredrar att redigera CSS direkt i dess Raw-format trycker du på **[!UICONTROL Visa/dölj CSS]** under listrutan **[!UICONTROL Vald typ]** (du kan behöva rulla den visuella redigeraren uppåt för att se den).
   >
   >Precis som den visuella redigeraren kan du omedelbart se vilken effekt den har på visningsprogramexemplet när du ändrar en egenskap direkt i CSS. Och samma egenskap uppdateras automatiskt samtidigt i den visuella redigeraren. Därför kan du använda CSS-redigeraren raw eller den visuella redigeraren, eller använda båda för båda.

   >[!NOTE]
   >
   >För knappbilder väljer du 2x-bilden och överför högupplösta bilder. När du arbetar med interaktiva bilder och köpbara banners kan du även välja bland en mängd färdiga hotspot-knappar.

1. (Valfritt) I början av sidan **[!UICONTROL Redigera visningsförinställning]** trycker du på **[!UICONTROL Skrivbord]**, **[!UICONTROL Surfplatta]** eller **[!UICONTROL Telefon]** för att unikt definiera visuella format för olika enheter och skärmtyper.
1. Tryck på fliken **[!UICONTROL Beteende]** på sidan **Redigera visningsförinställning** . Du kan också trycka eller klicka på ett visuellt element i visningsprogrammet för att välja det för konfiguration.
1. I listrutan **[!UICONTROL Markerad text]** väljer du en komponent vars beteenden du vill ändra.

   Många komponenter i den visuella redigeraren har en detaljerad beskrivning. Dessa beskrivningar visas i blå rutor när du expanderar en komponent för att visa dess associerade parametrar.

   Vissa visningsprogramtyper har komponenter som gör att du kan ange bildserverkommandon i ett **IS Command** -textfält. En lista med kommandon som du kan använda finns i API-referens för [bildservering](https://marketing.adobe.com/resources/help/en_US/s7/is_ir_api/image_serving_api_ref.html).

   >[!NOTE]
   >
   >**Om du använder en pekenhet, till exempel en telefon eller surfplatta...**
   >
   >När du har skrivit ett värde i textfältet trycker du någon annanstans i användargränssnittet för att skicka ändringen och stänga det virtuella tangentbordet. Om du trycker på **[!UICONTROL Enter]** utförs ingen åtgärd.

1. I det övre högra hörnet av sidan trycker du på **[!UICONTROL Spara]**.
1. Publicera din nya visningsförinställning. Du måste publicera förinställningen innan du kan använda den på webbplatsen.

   Se [Publicera förinställningar](#publishing-viewer-presets)för visningsprogram.

## Specialöverväganden när du skapar en interaktiv visningsförinställning {#special-considerations-for-creating-an-interactive-viewer-preset}

**Visningslägen för miniatyrbilder på panelen**

När du skapar eller redigerar en förinställning för Interactive Video Viewer kan du välja vilken **[!UICONTROL Visningsläge]** som ska användas när du väljer `InteractiveSwatches` i listrutan **[!UICONTROL Vald komponent]** på fliken **[!UICONTROL Beteende]** . Det visningsläge du väljer påverkar hur och när miniatyrbilder visas när videon spelas upp. Du kan välja ett `segment`visningsläge (standard) eller ett `continuous`visningsläge.

| Visningsläge | Beskrivning |
|---|---|
| [!UICONTROL Segment] | [!UICONTROL Segment] är standardvisningsläget för förinställningarna Shoppable_Video_light och Shoppable_Video_dark och alla interaktiva visningsprogramförinställningar som du själv skapar. |
|  | I det här läget, när det finns färre miniatyrbilder tilldelade till ett videosegment än antalet synliga fläckar på visningspanelen, hämtas inte miniatyrbilder från nästa eller föregående undersegment för att fylla tomma fläckar på panelen. Det innebär att det bevarar visningen av färgrutor som har tilldelats ett visst videosegment. |
| [!UICONTROL Kontinuerlig] | Om antalet miniatyrbilder i ett segment är mindre än det antal som visas på panelen i [!UICONTROL kontinuerligt] läge, visas miniatyrbilder automatiskt i nästa segment, eller i föregående segment, om den sista miniatyrbilden visas. |

**Om automatisk rullning i det interaktiva visningsprogrammet**

Funktionen för automatisk rullning för miniatyrbilder i det interaktiva visningsprogrammet fungerar oberoende av det visningsläge du väljer.

När du skapar eller redigerar en förinställning för ett interaktivt visningsprogram öppnar du **[!UICONTROL Automatisk rullning]** på fliken **[!UICONTROL Beteende]** . Tryck på **[!UICONTROL InteractiveSwatches]** på menyn **[!UICONTROL Valda komponenter]** på fliken Beteende. Kryssrutan **[!UICONTROL Autorullning]** visas under textfältet IS Command.

Om du inaktiverar **[!UICONTROL automatisk rullning]** (avmarkerar kryssrutan) i visningsförinställningen visas endast den första miniatyrbilden för hela videolängden på panelen när användaren spelar upp videon. Användaren kan dock bläddra bland miniatyrbilderna manuellt med upp- och nedpilarna om så önskas.

När du aktiverar (väljer) **[!UICONTROL Auto Scroll]** i visningsförinställningen rullas miniatyrbilder som tilldelats ett videosegment in i vyn i början av ett segment under videouppspelningen. Det finns instanser där vissa miniatyrer i ett segment visas dubbelt så länge som andra miniatyrer före eller efter det. Det här beteendet beror på att antalet miniatyrbilder i ett segment är större än det antal som visas på panelen och inte är jämnt delbart.

Anta att du har ett 30-sekunders videosegment. Och det finns totalt nio miniatyrbilder som ska visas under 30 sekunder. Storleken på webbläsaren ändras så att det finns fyra synliga miniatyrpositioner på visningspanelen. Det 30 sekunder långa videotidssegmentet är uppdelat i tre undersegment. I följande tabell visas hur miniatyrbilder visas för ett givet tidsundersegment:

| **Videoundersegment** | **Delsegmenttid i sekunder** | **Miniatyrbilder som visas på panelen** |
|---|---|---|
| 1 | 0-10 | 1, 2, 3, 4 |
| 2 | 10-20 | 4, 5, 6, 7 |
| 3 | 20-30 | 6, 7, 8, 9 |

Video-undersegment 3 sträcker sig inte utanför de miniatyrbilder som är tilldelade till det. Lägg märke till att miniatyrbilderna 4, 6 och 7 visas dubbelt så långt på panelen som de andra miniatyrbilderna.

Följande logik används för hur många miniatyrbilder som visas på panelen baserat på antalet tillgängliga positioner:

* Antal undersegment = rund upp till nästa undersegment (antal miniatyrbilder/antal synliga platser på miniatyrbildspanelen, baserat på webbläsarfönstrets storlek).

   I exemplet i tabellen ovan används 9 miniatyrbilder/4 kortplatser = 2,25; visningsprogrammets logik omger den med upp till tre undersegment.

* Antal miniatyrbilder = avrunda till nästa miniatyrbild (antal miniatyrbilder/antal undersegment till video).

   Med hjälp av exemplet i tabellen ovan är det 9 miniatyrbilder/3 undersegment för video = 3 miniatyrbilder.

* Undersegmentets längd = den totala videons längd/antal undersegment.

   Med hjälp av exemplet i tabellen ovan visas 30 sekunder/3 undersegment för video = 10 sekunder för varje undersegment för video.

### Specialöverväganden när du skapar en visningsförinställning för Carousel Banner {#special-considerations-for-creating-a-carousel-banner-viewer-preset}

När du skapar visningsförinställningar för Carousel Banner kan du ändra format för aktiveringspunkter på följande sätt:

|  | **Beskrivning** | **Åtgärder** |
|---|---|---|
| **Ikon för aktiveringspunkt** | Ändra ikonen som används för hotspot | Om du vill ändra hotspot-ikonbilden trycker du på **[!UICONTROL ImageMapEffect]** på fliken **[!UICONTROL Utseende]** i den valda komponenten ****. Under **[!UICONTROL Ikon]** väljer du **[!UICONTROL Bakgrund]** och i fältet **[!UICONTROL Bild]** navigerar du till den bakgrundsbild du vill ha. |

## Aktivera eller inaktivera förinställningar för Dynamic Media Viewer {#activating-or-deactivating-viewer-presets}

Vilka visningsprogramförinställningar som är tillgängliga i användargränssnittet beror på vilka som är aktiva i redigeringsläget. Som standard är en visningsförinställning *På* när du har skapat den. Om du inaktiverar förinställningen visas den inte i redigeringsläge. Om förinställningen publiceras. den kommer alltid att publiceras oavsett om den är på eller av. Du kanske vill inaktivera visningsförinställningarna om listan blir för oskarp eller om du inte vill att en visningsförinställning ska vara tillgänglig för användning.

**Så här aktiverar eller inaktiverar du förinställningar** för visningsprogrammet för Dynamic Media:

1. I det övre vänstra hörnet av AEM trycker du på AEM-logotypen och sedan på **[!UICONTROL Verktyg > Resurser > Visningsförinställningar]** i den vänstra listen.
1. På sidan **[!UICONTROL Visningsförinställning]** , under kolumnrubriken **[!UICONTROL Läge]** , trycker du på för att aktivera eller inaktivera en visningsförinställning.

   De visningsprogramförinställningar som är aktiverade visas till höger, i en blå ruta. förinställningar för inaktiverat visningsprogram har växlingsknappen till vänster, i en ljusgrå ruta.

## Publishing Dynamic Media viewer presets {#publishing-viewer-presets}

När du aktiverar (eller aktiverar *)* läget för en visningsförinställning innebär det att den visas i komponenten Dynamic Media, i komponenten Interactive Media och när du visar en resurs.

Om du vill leverera en resurs med en visningsförinställning måste visningsförinställningen också publiceras. Alla visningsförinställningar måste aktiveras *och* publiceras för att hämta URL- eller inbäddningskod för en resurs. Du måste aktivera och publicera alla färdiga visningsförinställningar som medföljer Dynamic Media. Anpassade förinställningar för visningsprogram som du skapar och lägger till aktiveras automatiskt, men måste också publiceras.

Se [Aktivera eller inaktivera visningsförinställningar](#activating-or-deactivating-viewer-presets).

Se även [Förhandsgranska resurser](previewing-assets.md).

**Så här publicerar du förinställningar** för Dynamic Media Viewer:

1. I det övre vänstra hörnet av AEM trycker du på AEM-logotypen och sedan på **[!UICONTROL Verktyg > Resurser > Visningsförinställningar]** i den vänstra listen.
1. Välj en eller flera visningsförinställningar som du vill publicera.
1. Tryck på ikonen **[!UICONTROL Publicera]** i verktygsfältet.

## Sorting Dynamic Media viewer presets {#sorting-viewer-presets}

**Så här sorterar du förinställningar** för Dynamic Media Viewer:

1. I det övre vänstra hörnet av AEM trycker du på AEM-logotypen och sedan på **Verktyg** (hamikon) **[!UICONTROL > Resurser > Visningsförinställningar]** i den vänstra listen.
1. Klicka på **[!UICONTROL Förinställningstitel]**, **[!UICONTROL Text]**, **[!UICONTROL Publicerad]** eller **[!UICONTROL Läge]** för att sortera efter den kolumnrubriken. Klicka till exempel på **[!UICONTROL Text]** om du vill sortera visningsprogrammets förinställningstyper i alfabetisk eller omvänd alfabetisk ordning.

## Editing Dynamic Media viewer presets {#editing-viewer-presets}

Tänk på att redigering av *fördefinierade förinställningar* för visningsprogram som är färdiga att användas inte är ett scenario som stöds. Om du redigerar en förinställning för ett visningsprogram som inte är installerat uppmanas du att spara den med ett nytt namn.

**Så här redigerar du förinställningar** för Dynamic Media Viewer:

1. I det övre vänstra hörnet av AEM trycker du på AEM-logotypen och sedan på **[!UICONTROL Verktyg > Resurser > Visningsförinställningar]** i den vänstra listen.
1. Markera en förinställning genom att markera rutan till vänster om visningsförinställningens titel.
1. Tryck på **[!UICONTROL Redigera]** i verktygsfältet.
1. Gör de ändringar du vill av visningsförinställningen på sidan **[!UICONTROL Redigera visningsförinställning]** .
1. Gör något av följande:

   * Tryck på **[!UICONTROL Spara]** för att spara ändringarna och återgå till sidan **[!UICONTROL Visningsförinställning]** .
   * Tryck på **[!UICONTROL Avbryt]** för att ångra ändringar du gjort och återgå till sidan **[!UICONTROL Visningsförinställning]** .

## Ta bort anpassade förinställningar för Dynamic Media Viewer {#deleting-custom-viewer-presets}

Du kan ta bort visningsförinställningar som du har skapat och lagt till i dynamiska media.

**Så här tar du bort anpassade förinställningar** för Dynamic Media Viewer:

1. I det övre vänstra hörnet av AEM trycker du på AEM-logotypen och sedan på **[!UICONTROL Verktyg > Resurser > Visningsförinställningar]** i den vänstra listen.
1. Markera en **[!UICONTROL förinställningsrubrik]** på sidan **[!UICONTROL Förinställningar]** och tryck sedan på **[!UICONTROL papperskorgsikonen]** .
1. Tryck på **[!UICONTROL Ta bort]**.

## Använda en förinställning för Dynamic Media Viewer på en mediefil {#applying-a-viewer-preset-to-an-asset}

Om du redan har publicerat både resursen och det valda visningsprogrammet visas knapparna **[!UICONTROL URL]** och **[!UICONTROL Bädda in]** när du har valt en visningsförinställning.

**Så här använder du en förinställning för Dynamic Media Viewer på en resurs**:

1. Öppna resursen och i det övre vänstra hörnet av sidan, tryck på den nedrullningsbara menyn och välj sedan **[!UICONTROL Visare]**.

   >[!NOTE]
   >
   >Om du redan har publicerat både resursen och det valda visningsprogrammet visas knapparna **[!UICONTROL URL]** och **[!UICONTROL Bädda in]** när du har valt en visningsförinställning.

1. Välj en visningsförinställning i den vänstra rutan för att använda den på resursen.

   Du kan [kopiera URL-adressen och dela](linking-urls-to-yourwebapplication.md) den med andra användare.

## Leverera resurser med förinställningar för Dynamic Media Viewer {#delivering-assets-with-viewer-presets}

Mer information om hur du hämtar URL:er för visningsförinställningar finns i [Länka URL:er till webbprogrammet](linking-urls-to-yourwebapplication.md). Se även [Bädda in Video Viewer på en webbsida](embed-code.md).

Om du använder AEM som WCM kan du lägga till resurser med visningsförinställningarna direkt på sidan. See [Adding Dynamic Media Assets to Pages](adding-dynamic-media-assets-to-pages.md).
