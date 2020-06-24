---
title: Hantera förinställningar för visningsprogrammet för Dynamic Media
seo-title: Hantera förinställningar för visningsprogrammet för Dynamic Media
description: Skapa och hantera visningsförinställningar för Dynamic Media
seo-description: Skapa och hantera visningsförinställningar för Dynamic Media
uuid: 31ef7a4e-2053-43b5-ac6c-cdc4b30c3914
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: e78bb08a-a923-4399-b3f7-13aa4b7994d5
legacypath: /content/docs/en/aem/6-0/administer/integration/dynamic-media/viewer-presets
translation-type: tm+mt
source-git-commit: a3a160a0281c1ea2ca050c2c747d6a5ec1d952b3
workflow-type: tm+mt
source-wordcount: '4105'
ht-degree: 9%

---


# Managing Dynamic Media viewer presets {#managing-viewer-presets}

En förinställning för visningsprogrammet för Dynamic Media är en samling inställningar som avgör hur användare visar mediefiler på datorskärmar och mobila enheter. Om du är administratör kan du skapa visningsförinställningar. Inställningarna är tillgängliga för en array med visningskonfigurationsalternativ. Du kan till exempel ändra visningsprogrammets visningsstorlek eller zoombeteende.

Instruktioner om hur du skapar och anpassar egna HTML5-visningsförinställningar finns i *Adobe Scene7 HTML5 Viewer SDK*. SDK är tillgängligt på IS-publiceringsservern som är inbäddad i SDK:n. Varje biblioteksversion har en egen SDK-dokumentation.

Path: `<scene7_domain>/s7sdk/<library_version>/docs/jsdocs/index.html`.\
Exempel: 3.5 SDK: [https://s7d1.scene7.com/s7sdk/3.5/docs/jsdoc/index.html](https://s7d1.scene7.com/s7sdk/3.5/docs/jsdoc/index.html)

Se även [Adobe Viewer Reference Guide](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/library/home.html).

I det här avsnittet beskrivs hur du skapar, redigerar och hanterar visningsprogramförinställningar. Du kan använda en visningsförinställning för en resurs när du vill förhandsgranska den. Se [Använda visningsförinställningar](viewer-presets.md).

>[!NOTE]
>
>Tänk på att redigering av *fördefinierade förinställningar* för visningsprogram som är färdiga att användas inte är ett scenario som stöds. Om du försöker redigera en förinställning för visningsprogrammet som inte är klar visas en uppmaning om att spara visningsförinställningen med ett nytt namn.

## Tangentbordstillgänglighet för tittare {#keyboard-accessibility-for-viewers}

Alla färdiga visningsprogram har stöd för tangentbordstillgänglighet.

Se även [Tangentbordstillgänglighet och -navigering](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/library/c-keyboard-accessibility.html).

## Managing Dynamic Media viewer presets {#managing-presets}

You can add, edit, delete, publish, unpublish, and preview viewer presets in AEM by tapping **[!UICONTROL Tools > Assets > Viewer Presets]**.

![verktyg-resurser](assets/tools-assets.png)

>[!NOTE]
>
>Som standard visas 15 visningsförinställningar när du väljer visningsprogram i detaljvyn för en resurs. Du kan öka den här gränsen. Se [Öka antalet visningsförinställningar som visas](#increasing-the-number-of-viewer-presets-that-display).

## Stöd för visningsprogram för responsiva webbsidor {#viewer-support-for-responsive-designed-web-pages}

Olika webbsidor har olika behov. Ibland kanske du vill ha en webbsida som innehåller en länk som öppnar HTML5 Viewer i ett separat webbläsarfönster. I andra fall kan det vara nödvändigt att bädda in HTML5 Viewer direkt på värdsidan. I det senare fallet kan webbsidan ha en statisk layout. Den kan också vara *responsiv* och visas på olika enheter eller i olika webbläsarfönsterstorlekar. För att tillgodose dessa behov har alla fördefinierade färdiga HTML5-visningsprogram som medföljer Dynamic Media stöd för både statiska webbsidor och responsiva webbsidor.

Mer information om hur du bäddar in responsiva visningsprogram på dina webbsidor finns i [Biblioteket](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-serving-api/image-serving-api/responsive-static-image-library/c-about-responsive-static-image-library.html) för responsiva bilder i hjälpen *för* Image Serving API.

>[!NOTE]
>
>Observera att du måste publicera alla användningsklara visningsprogram innan du använder dem första gången.\
>Se Förinställningar för [publiceringsvisningsprogrammet.](#publishing-viewer-presets)

## Systemkompatibilitet för visningsförinställningar  {#viewer-preset-system-compatibility}

Alla färdiga visningsförinställningar för Dynamic Media är helt kompatibla med följande system:

* Stationära datorer
* Apple iPhone
* Apple iPad
* Android Smartphone
* Android-surfplatta
* För video finns ytterligare stöd för MP4-uppspelning för [Blackberry](https://developer.blackberry.com/devzone/develop/supported_media/bb_media_support_at_a_glance.html#kba1328730952678) och [Windows Phone 8](https://msdn.microsoft.com/library/windows/apps/ff462087%28v=vs.105%29.aspx).

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
|  | Viktigt: Det här visningsprogrammet är bara tillgängligt i Dynamic Media - Scene7-läge. |
| **Snurra uppsättning** | Ger flera vyer av en bild så att användare kan vrida objektet för att undersöka olika sidor och vinklar. |
| **Video** | Spelar upp video med strömning med progressiv eller adaptiv bithastighet. Med adaptiv bithastighetsströmning utförs automatiskt enhets- och bandbreddsidentifiering för att leverera rätt kvalitetsvideo i rätt format. |
| **Lodrät zoomning** | Med Lodrät zoomning kan du maximera visningen av produktbilder och ge användarna bästa möjliga återgivning av en produkt. Den lodräta placeringen av färgrutor gör följande: <ul><li>Ser till att färgrutorna är över vecket. Med vågräta färgrutor var färgrutorna inte synliga förrän användaren rullade nedåt på sidan, beroende på  skärmstorlek. Genom att placera färgrutorna lodrätt i visningsprogrammet ser du till att de visas oavsett användarens skärmstorlek.</li><li>Maximerar storleken på huvudbilden. Med vågräta färgrutor måste du reservera utrymme på sidan för att se till att de är synliga. Den här placeringen minskade storleken på huvudbilden. Om du har en lodrät färgrutelayout behöver du dock inte tilldela det här utrymmet. Därför kan du maximera huvudbildstorleken.</li></ul> |
| **Zoomning** | Låter användarna zooma in i området genom att klicka på det. Användare kan klicka på kontroller för att zooma in, zooma ut och återställa bilden till standardstorleken. |

## Lista med färdiga visningsförinställningar {#list-of-out-of-the-box-viewer-presets}

I följande tabell visas alla fördefinierade, färdiga visningsförinställningar som medföljer Dynamic Media.

Se även <!-- [SAVE THIS REFERENCE Viewers Reference Library Examples](https://marketing.adobe.com/resources/help/en_US/s7/vlist/vlist.html) and --> [Live Demos](https://landing.adobe.com/en/na/dynamic-media/ctir-2755/live-demos.html).

Information om vilka webbläsare och operativsystemversioner som stöds för visningsprogram finns i Viewer Release Notes.

Se Versionsinformation *för* visningsprogram i innehållsförteckningen i [referenshandboken](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/library/home.html)för visningsprogram.

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
| **Tryck på** | Visar utfällbart fönster | Visar eller döljer användargränssnittet | Visar eller döljer användargränssnittet |
| **Dubbelknacka** | Gäller inte | Zoomar in eller återställer | Zoomar in eller återställer |
| **Knipning öppen** | Gäller inte | Zoomar in (endast iOS och Android 3x) | Zoomar in (endast iOS och Android 3x) |
| **Knipning - stäng** | Gäller inte | Zoomar ut (endast iOS och Android 3x) | Zoomar ut (endast iOS och Android 3x) |
| **Svep** | Rullningslist | Rulla bilder | Spins |
| **Snurra** | Rullningslist | Rulla bilder | Spins |

## Öka antalet visningsförinställningar för Dynamic Media {#increasing-the-number-of-viewer-presets-that-display}

AEM visar en mängd olika förinställningar för visningsprogram när du visar resurser från **[!UICONTROL Detail View > Viewers]**. Du kan öka eller minska antalet visningsprogram som visas.

**Så här ökar du antalet visningsförinställningar för Dynamic Media**:

1. Navigera till **[!UICONTROL CRXDE Lite]** ([http://localhost:4502/crx/de](http://localhost:4502/crx/de)).
1. Navigera till noden med visningsförinställningar på `/libs/dam/gui/coral/content/commons/sidepanels/viewerpresets/viewerpresetslist`

   ![chlimage_1-221](assets/chlimage_1-221.png)

1. I egenskapen **[!UICONTROL limit]** ändrar du **[!UICONTROL Value]**, som är inställt på 15 som standard, till önskat tal.
1. Navigera till datakällan för visningsförinställningen på `/libs/dam/gui/coral/content/commons/sidepanels/viewerpresets/viewerpresetslist/datasource`

   ![chlimage_1-222](assets/chlimage_1-222.png)

1. I egenskapen **[!UICONTROL limit]** ändrar du talet till önskat tal, till exempel `{empty requestPathInfo.selectors[1] ? "20" : requestPathInfo.selectors[1]}`
1. Tryck på **[!UICONTROL Save All]**.

## Skapa en ny visningsförinställning för Dynamic Media {#creating-a-new-viewer-preset}

Genom att skapa visningsförinställningar kan du använda olika inställningar för att visa och interagera med resurser. Du behöver dock inte skapa nya förinställningar för visningsprogrammet. Om du vill kan du använda standardförinställningarna för visningsprogram som redan finns i AEM Assets.

Om du väljer att skapa en ny visningsförinställning aktiveras visningsprogrammets läge automatiskt (anges till **På**) på **[!UICONTROL Viewer Presets]** sidan när du har sparat den. Det här läget innebär att det är synligt i **[!UICONTROL Dynamic Media]** komponenten och **[!UICONTROL Interactive Media]** komponenten, och när du förhandsgranskar en bild eller video.

Vissa visningsprogramförinställningar har exklusiva inställningar som kan påverka visningsprogrammets användning och allmänna beteende. Beroende på vilken visningsförinställning du skapar kan det vara bra att tänka på dessa speciella saker.

Se [Specialöverväganden när du skapar en interaktiv visningsprogramförinställning](#special-considerations-for-creating-an-interactive-viewer-preset).

Se [Specialöverväganden när du skapar en förinställning](#special-considerations-for-creating-a-carousel-banner-viewer-preset)för Carousel Banner Viewer.

**Så här skapar du en ny visningsförinställning** för Dynamic Media:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.

   ![visningsförinställningar](assets/viewerpresets.png)

1. Tryck på i verktygsfältet på **[!UICONTROL Viewer Presets]** sidan **[!UICONTROL Create]**.
1. In the **[!UICONTROL New Viewer Preset]** dialog box, in the **[!UICONTROL Preset Name]** field, enter the name of the new preset. Choose a name carefully--they are not editable after you tap **[!UICONTROL Create]**.

   När du sparar förinställningen senare i de här stegen visas namnet på sidan Förinställningar för visningsprogram under kolumnrubriken **[!UICONTROL Preset Title]** .

1. I den **[!UICONTROL Rich Media Type]** nedrullningsbara menyn väljer du vilken typ av visningsförinställning som du vill skapa och trycker sedan på i sidans övre högra hörn **[!UICONTROL Create]**.

   Se [Multimedietyper för visningsförinställningar](#rich-media-types-for-viewer-presets).

1. On the **Edit Viewer Preset** page, tap the **[!UICONTROL Appearance]** tab.
1. Gör något av följande:

   * In the **[!UICONTROL Selected Type]** pull-down menu, select a component whose visual design you want to customize. Du kan också trycka på valfritt visuellt element i visningsprogrammet för att välja det för konfiguration.

      Med den visuella redigeraren kan du se vilken effekt en viss egenskap har på ett format. Du behöver bara ställa in eller justera en egenskap för att omedelbart se vilken effekt den har på visningsprogrammet med exemplet till vänster om redigeraren.

      CSS-formategenskaperna för varje typ av visningsförinställning beskrivs i hjälpavsnittet Anpassa *&lt;viewer_name>* Viewer i [referenshandboken](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/library/home.html)för visningsprogram.

      Om du till exempel skapar en visningsförinställning av den här typen `Mixed_Media`kan du läsa [Anpassa blandad medievisare](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/mixed-media/customing-mixed-media/c-html5-mixedmedia-viewer-customizingviewer.html) för en lista och en beskrivning av varje egenskap.

   * Om du har definierat formatinställningar i en separat CSS-fil kan du överföra CSS-filen till AEM Assets. Tap **[!UICONTROL Import CSS]** below the **[!UICONTROL Selected Type]** pull-down menu (you may need to scroll the visual editor up to see it) to find the uploaded CSS file and associate it with the viewer preset.

      När du importerar en CSS-fil kontrollerar den visuella redigeraren om rätt visningsmarkörer används i CSS. Om du till exempel skapar ett Zoom-visningsprogram måste alla CSS-regler som du importerar definieras med hjälp av visningsprogrammets klassnamn som `.s7mixedmediaviewer` definieras för ett överordnat visningsprogramelement.

      Du kan importera godtycklig, handgjord CSS så länge den definierar CSS-markörerna för ett visst visningsprogram. (CSS-markörer beskrivs i hjälpavsnittet Anpassa *&lt;visningsprogramnamn>* visningsprogram&quot; i [referenshandboken](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/library/home.html)för visningsprogram. Om du till exempel vill läsa om CSS-markörer för Zoomvisningsprogrammet läser du [Anpassa zoomvisningsprogrammet](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/zoom/customizing-zoom/c-html5-20-zoom-viewer-customizingviewer.html).) Det är dock möjligt att den visuella redigeraren kanske inte förstår vissa CSS-värden. I sådana fall försöker den visuella redigeraren åsidosätta felen så att CSS fortfarande fungerar.
   >[!NOTE]
   >
   >If you prefer to edit the CSS directly in its raw form, tap **[!UICONTROL Show/Hide CSS]** below the **[!UICONTROL Selected Type]** pull-down menu (you may need to scroll the visual editor up to see it).
   >
   >Precis som den visuella redigeraren kan du omedelbart se vilken effekt den har på visningsprogramexemplet när du ändrar en egenskap direkt i CSS. Och samma egenskap uppdateras automatiskt samtidigt i den visuella redigeraren. Därför kan du använda CSS-redigeraren raw eller den visuella redigeraren, eller använda båda för båda.

   >[!NOTE]
   >
   >För knappbilder väljer du 2x-bilden och överför högupplösta bilder. När du arbetar med interaktiva bilder och köpbara banners kan du även välja bland en mängd färdiga hotspot-knappar.

1. (Optional) Near the top of the **[!UICONTROL Edit Viewer Preset]** page, tap **[!UICONTROL Desktop]**, **[!UICONTROL Tablet]**, or **[!UICONTROL Phone]** to uniquely define visual styles for different device and screen types.
1. Tryck på fliken **[!UICONTROL Edit Viewer Preset]** Beteende **på** sidan. Du kan också trycka eller klicka på ett visuellt element i visningsprogrammet för att välja det för konfiguration.
1. Välj en komponent vars beteenden du vill ändra i listrutan **[!UICONTROL Selected Type]**.

   Många komponenter i den visuella redigeraren har en detaljerad beskrivning. Dessa beskrivningar visas i blå rutor när du expanderar en komponent för att visa dess associerade parametrar.

   Some Viewer types have components that let you specify Image Serving commands in an **IS Command** text field. En lista med kommandon som du kan använda finns i [API-referenshandboken för bildservrar](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-serving-api/image-serving-api/c-is-home.html).

   >[!NOTE]
   >
   >**Om du använder en pekenhet, till exempel en telefon eller surfplatta...**
   >
   >När du har skrivit ett värde i textfältet trycker du någon annanstans i användargränssnittet för att skicka ändringen och stänga det virtuella tangentbordet. Om du trycker **[!UICONTROL Enter]** utförs ingen åtgärd.

1. Near the upper-right corner of the page, tap **[!UICONTROL Save]**.
1. Publicera din nya visningsförinställning. Du måste publicera förinställningen innan du kan använda den på webbplatsen.

   Se [Publicera förinställningar](#publishing-viewer-presets)för visningsprogram.

## Specialöverväganden när du skapar en interaktiv visningsförinställning {#special-considerations-for-creating-an-interactive-viewer-preset}

**Visningslägen för miniatyrbilder på panelen**

When you create or edit an Interactive Video viewer preset, you have the choice of which **[!UICONTROL Display Mode]** setting to use when you select `InteractiveSwatches` from the **[!UICONTROL Selected Component]** pull-down menu under the **[!UICONTROL Behavior]** tab. Det visningsläge du väljer påverkar hur och när miniatyrbilder visas när videon spelas upp. You can choose either a `segment`display mode (default) or a `continuous`display mode.

| Visningsläge | Beskrivning |
|---|---|
| [!UICONTROL Segment] | [!UICONTROL Segment] är standardvisningsläget för förinställningarna Shoppable_Video_light och Shoppable_Video_dark och alla Interactive Video Viewer-förinställningar som du själv skapar. |
|  | I det här läget, när det finns färre miniatyrbilder tilldelade till ett videosegment än antalet synliga fläckar på visningspanelen, hämtas inte miniatyrbilder från nästa eller föregående undersegment för att fylla tomma fläckar på panelen. Det innebär att det bevarar visningen av färgrutor som har tilldelats ett visst videosegment. |
| [!UICONTROL Continuous] | Om antalet miniatyrbilder i ett segment är mindre än det antal som visas på panelen, visas miniatyrbilderna automatiskt i det [!UICONTROL Continuous] visningsläge som visas i nästa segment, eller i det föregående segmentet, där den sista miniatyrbilden visas. |

**Om automatisk rullning i det interaktiva visningsprogrammet**

Funktionen för automatisk rullning för miniatyrbilder i det interaktiva visningsprogrammet fungerar oberoende av det visningsläge du väljer.

When you create or edit an interactive video viewer preset, you access **[!UICONTROL Auto Scroll]** from the **[!UICONTROL Behavior]** tab. På fliken Beteende i listrutan **[!UICONTROL Selected Components]** trycker du på **[!UICONTROL InteractiveSwatches]**. The **[!UICONTROL Auto Scroll]** check box is listed below the IS Command text field.

Om du inaktiverar **[!UICONTROL Auto Scroll]** (avmarkerar kryssrutan) i visningsförinställningen visas bara den första miniatyrbilden för hela videolängden på panelen när användaren spelar upp videon. Användaren kan dock bläddra bland miniatyrbilderna manuellt med upp- och nedpilarna om så önskas.

När du aktiverar (markerar) **[!UICONTROL Auto Scroll]** i visningsförinställningen rullas miniatyrbilder som tilldelats ett videosegment in i vyn i början av ett segment under videouppspelningen. Det kan hända att vissa miniatyrer i ett segment visas dubbelt så länge som andra miniatyrer före eller efter dem. Det här beteendet beror på att antalet miniatyrbilder i ett segment är större än det antal som visas på panelen och inte är jämnt delbart.

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
| **Ikon för aktiveringspunkt** | Ändra ikonen som används för hotspot | Om du vill ändra hotspot-ikonbilden trycker du på i **[!UICONTROL Appearance]** på **[!UICONTROL Selected Component]** fliken **[!UICONTROL ImageMapEffect]**. Under **[!UICONTROL Icon]** markerar du **[!UICONTROL Background]** och i fältet **[!UICONTROL Image]** navigerar du till den bakgrundsbild du vill ha. |

## Aktivera eller inaktivera förinställningar för Dynamic Media-visningsprogram {#activating-or-deactivating-viewer-presets}

Vilka visningsprogramförinställningar som är tillgängliga i användargränssnittet beror på vilka som är aktiva i redigeringsläget. Som standard är en visningsförinställning *På* när du har skapat den. Om du inaktiverar förinställningen visas den inte i redigeringsläge. Om förinställningen publiceras. den kommer alltid att publiceras oavsett om den är på eller av. Du kanske vill inaktivera visningsförinställningarna om listan blir för oskarp eller om du inte vill att en visningsförinställning ska vara tillgänglig för användning.

**Så här aktiverar eller inaktiverar du visningsförinställningar** för Dynamic Media:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. På **[!UICONTROL Viewer Preset]** sidan, under **[!UICONTROL State]** kolumnrubriken, trycker du på växlingsknappen för att aktivera eller inaktivera en visningsförinställning.

   De visningsprogramförinställningar som är aktiverade visas till höger, i en blå ruta. förinställningar för inaktiverat visningsprogram har växlingsknappen till vänster, i en ljusgrå ruta.

## Publishing Dynamic Media viewer presets {#publishing-viewer-presets}

När du aktiverar (eller aktiverar *)* läget för en visningsförinställning innebär det att den visas i komponenten Dynamic Media, i komponenten Interactive Media och när du visar en resurs.

Om du vill leverera en resurs med en visningsförinställning måste visningsförinställningen också publiceras. All viewer presets must be activated *and* published to obtain URL or embed code for an asset. Du måste aktivera och publicera alla färdiga visningsförinställningar som medföljer Dynamic Media. Anpassade visningsförinställningar som du skapar och lägger till aktiveras automatiskt, men de måste också publiceras.

Se [Aktivera eller inaktivera visningsförinställningar](#activating-or-deactivating-viewer-presets).

Se även [Förhandsgranska resurser](previewing-assets.md).

**Så här publicerar du visningsförinställningar** för Dynamic Media:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. Välj en eller flera visningsförinställningar som du vill publicera.
1. Tryck på **[!UICONTROL Publish]** ikonen i verktygsfältet.

## Sorting Dynamic Media viewer presets {#sorting-viewer-presets}

**Så här sorterar du visningsförinställningar** för Dynamic Media:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **Tools** (hammer icon) **[!UICONTROL > Assets > Viewer Presets]**.
1. Klicka på **[!UICONTROL Preset Title]**, **[!UICONTROL Type]**, **[!UICONTROL Published]** eller **[!UICONTROL State]** för att sortera efter den kolumnrubriken. Du kan till exempel klicka på **[!UICONTROL Type]** för att sortera de olika typerna av visningsförinställningar i alfabetisk eller omvänd alfabetisk ordning.

## Editing Dynamic Media viewer presets {#editing-viewer-presets}

Tänk på att redigering av *fördefinierade förinställningar* för visningsprogram som är färdiga att användas inte är ett scenario som stöds. Om du redigerar en förinställning för ett visningsprogram som inte är installerat uppmanas du att spara den med ett nytt namn.

**Så här redigerar du visningsförinställningar** för Dynamic Media:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. Markera en förinställning genom att markera rutan till vänster om visningsförinställningens titel.
1. Tryck på i verktygsfältet **[!UICONTROL Edit]**.
1. Gör de ändringar du vill av visningsförinställningen på **[!UICONTROL Edit Viewer Preset]** sidan.
1. Gör något av följande:

   * Tryck **[!UICONTROL Save]** för att spara ändringarna och återgå till **[!UICONTROL Viewer Preset]** sidan.
   * Tryck för **[!UICONTROL Cancel]** att ångra ändringar du gjort och återgå till **[!UICONTROL Viewer Preset]** sidan.

## Ta bort anpassade förinställningar för visningsprogrammet för Dynamic Media {#deleting-custom-viewer-presets}

Du kan ta bort visningsförinställningar som du har skapat och lagt till i Dynamic Media.

**Så här tar du bort anpassade visningsförinställningar** för Dynamic Media:

1. In the upper-left corner of AEM, tap the AEM logo, then in the left rail, tap **[!UICONTROL Tools > Assets > Viewer Presets]**.
1. På **[!UICONTROL Viewer Presets]** sidan markerar du en **[!UICONTROL Preset Title]** och trycker sedan på **[!UICONTROL Trash]** -ikonen.
1. Tryck på **[!UICONTROL Delete]**.

## Använda en förinställning för Dynamic Media-visningsprogram på en resurs {#applying-a-viewer-preset-to-an-asset}

Om du redan har publicerat både resursen och det valda visningsprogrammet visas knapparna **[!UICONTROL URL]** och **[!UICONTROL Embed]** när du har valt en visningsförinställning.

**Så här använder du en förinställning för Dynamic Media-visningsprogram på en resurs**:

1. Öppna resursen och i det övre vänstra hörnet av sidan, tryck på listrutan och välj sedan **[!UICONTROL Viewers]**.

   >[!NOTE]
   >
   >Om du redan har publicerat både resursen och det valda visningsprogrammet visas knapparna **[!UICONTROL URL]** och **[!UICONTROL Embed]** när du har valt en visningsförinställning.

1. Välj en visningsförinställning i den vänstra rutan för att använda den på resursen.

   Du kan [kopiera URL-adressen och dela](linking-urls-to-yourwebapplication.md) den med andra användare.

## Leverera resurser med Dynamic Media visningsförinställningar {#delivering-assets-with-viewer-presets}

Mer information om hur du hämtar URL:er för visningsförinställningar finns i [Länka URL:er till webbprogrammet](linking-urls-to-yourwebapplication.md). Se även [Bädda in Video Viewer på en webbsida](embed-code.md).

Om du använder AEM som WCM kan du lägga till resurser med visningsförinställningarna direkt på sidan. See [Adding Dynamic Media Assets to Pages](adding-dynamic-media-assets-to-pages.md).
