---
title: Lägga till Dynamic Media-resurser på sidor
seo-title: Lägga till Dynamic Media-resurser på sidor
description: Lägga till Dynamic Media-komponenter på en sida i AEM
seo-description: Lägga till Dynamic Media-komponenter på en sida i AEM
uuid: 77abcb87-2df7-449b-be52-540d749890b6
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: d1f45751-1761-4d6b-b17d-110b2f1117ea
exl-id: bb97b649-a50d-49c8-97aa-18c32f18d527
feature: Komponenter
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '2709'
ht-degree: 4%

---

# Lägga till Dynamic Media-resurser på sidor {#adding-dynamic-media-assets-to-pages}

Om du vill lägga till funktionen för dynamiska medier i resurser som du använder på dina webbplatser kan du lägga till komponenten **Dynamic Media** eller **Interactive Media** direkt på sidan. Det gör du genom att öppna layoutläget och aktivera de dynamiska mediekomponenterna. Sedan kan du lägga till komponenterna på sidan och lägga till resurser i komponenterna. Komponenterna för dynamiska media och interaktiva media är smarta - de vet om du lägger till en bild eller en video och de tillgängliga alternativen ändras i enlighet med detta.

Du lägger till dynamiska medieresurser direkt på sidan om du använder AEM som WCM-fil. Om ni använder en annan leverantör för innehållshanteringssystemet kan ni antingen [länka](linking-urls-to-yourwebapplication.md) eller [bädda in](embed-code.md) resurserna. Om du har en responsiv webbplats hos en extern leverantör läser du [Leverera optimerade bilder till en responsiv webbplats](responsive-site.md).

>[!NOTE]
>
>Du måste publicera resurser innan du lägger till dem på sidor i AEM. Se [Publicera Dynamic Media Assets](publishing-dynamicmedia-assets.md).

## Lägga till en Dynamic Media-komponent på en sida {#adding-a-dynamic-media-component-to-a-page}

Att lägga till en Dynamic Media-komponent på en sida är detsamma som att lägga till en komponent på en sida. Dynamic Media-komponenterna beskrivs i detalj i följande avsnitt.

>[!NOTE]
>
>Om det finns en Dynamic Media-komponent på en webbsida som en användare med skrivskyddad behörighet kommer åt, bryts sidan och komponenterna återges inte korrekt. Orsaken är att sidan har rekonstruerats för att komponenterna ska bli bra och att alla refererade resurser och konfigurationer är tillgängliga. Sidan återges sedan igen så att komponenterna bryts. respektive komponentkod på sidan kan inte återges på nytt på grund av användarens skrivskyddade åtkomst.
>  
>För att undvika det här problemet måste AEM Sites-användare ha de behörigheter som krävs för att få åtkomst till resurserna.

1. Öppna AEM sidan där du vill lägga till Dynamic Media-komponenten.
1. Klicka på ikonen **[!UICONTROL Components]** i panelen till vänster på sidan (du kan behöva växla visningen av sidopanelen).
1. Under rubriken **[!UICONTROL Components]** väljer du **[!UICONTROL Dynamic Media]** i listrutan. Om det inte finns någon lista över Dynamic Media-komponenter behöver du troligen aktivera de Dynamic Media-komponenter som du vill använda. Se [Aktivera Dynamic Media-komponenter](#enabling-dynamic-media-components).

   ![chlimage_1-537](assets/chlimage_1-537.png)

1. Dra en Dynamic Media-komponent som du vill använda till önskad plats på sidan.
1. Håll muspekaren direkt på komponenten. När komponenten är omgiven av en blå ruta trycker du en gång för att visa komponentens verktygsfält. Tryck på ikonen **[!UICONTROL Configuration]** (skiftnyckel).
1. [Redigera ](#dynamic-media-components) komponenterna efter behov och klicka på bockmarkeringen för att spara ändringarna.

### Aktivera Dynamic Media-komponenter {#enabling-dynamic-media-components}

Om det inte finns några Dynamic Media-komponenter att lägga till på en sida betyder det troligtvis att du först måste aktivera de komponenter som du vill använda.

1. Öppna AEM sidan där du vill lägga till Dynamic Media-komponenten.
1. Tryck på ikonen Sidinformation till vänster i verktygsfältet längst upp på sidan och tryck sedan på **[!UICONTROL Edit Template]** i listrutan.

   ![edit-template](/help/assets/assets-dm/edit-template.png)

1. Tryck på **[!UICONTROL Structure]** i listrutan till höger om verktygsfältet uppe på sidan.

   ![Policy](/help/assets/assets-dm/structure-mode.png)

1. Långt ned på sidan trycker du på **[!UICONTROL Layout Container]** för att öppna verktygsfältet och sedan på ikonen Policy.
1. Kontrollera att fliken **[!UICONTROL Allowed Components]** är markerad under rubriken **[!UICONTROL Properties]** på sidan **[!UICONTROL Layout Container]**.

   ![Tillåtna komponenter](/help/assets/assets-dm/allowed-components.png)

1. Rulla tills du ser **[!UICONTROL Dynamic Media]**.
1. Tryck på ikonen > till vänster om **[!UICONTROL Dynamic Media]** för att utöka listan och markera de Dynamic Media-komponenter som du vill aktivera.

   ![Lista över komponenter i Dynamic Media](/help/assets/assets-dm/dm-components-select.png)

1. I närheten av det övre högra hörnet på sidan **[!UICONTROL Layout Container]** trycker du på ikonen Klar (bock).

1. Till höger om verktygsfältet uppe på sidan trycker du på **[!UICONTROL Initial Content]** i listrutan och sedan [lägger du till en Dynamic Media-komponent på en sida](#adding-a-dynamic-media-component-to-a-page) som vanligt.

## Lokalisera Dynamic Media-komponenter {#localizing-dynamic-media-components}

Du kan lokalisera Dynamic Media-komponenter på ett av två sätt:

* Från en webbsida i Sites öppnar du **[!UICONTROL Properties]** och väljer fliken **[!UICONTROL Advanced]**. Välj språk för lokalisering.

   ![chlimage_1-538](assets/chlimage_1-538.png)

* Välj önskad sida eller sidgrupp i platsväljaren. Tryck på **[!UICONTROL Properties]** och välj fliken **[!UICONTROL Advanced]**. Välj språk för lokalisering.

   >[!NOTE]
   >
   >Observera att inte alla språk som är tillgängliga på **[!UICONTROL Language]**-menyn har tokens tilldelade.

## Dynamic Media-komponenter {#dynamic-media-components}

Dynamic Media och Interactive Media finns på fliken [!UICONTROL Dynamic Media] i [!UICONTROL Components]. Du använder komponenten [!UICONTROL Interactive Media] för alla interaktiva resurser, som interaktiv video, interaktiva bilder eller karuselluppsättningar. Använd Dynamic Media-komponenten för alla andra dynamiska mediekomponenter.

>[!NOTE]
>
>De här komponenterna är inte tillgängliga som standard och måste göras tillgängliga via mallredigeraren innan du använder dem. [När de har gjorts ](/help/sites-authoring/templates.md#editing-templates-template-authors) tillgängliga i mallredigeraren kan du lägga till komponenterna på sidan på samma sätt som andra AEM.

![chlimage_1-539](assets/chlimage_1-539.png)

### Dynamic Media-komponent {#dynamic-media-component}

Dynamic Media-komponenten är smart - beroende på om du lägger till en bild eller en video finns det olika alternativ. Komponenten har stöd för bildförinställningar, bildbaserade visningsprogram som bilduppsättningar, snurra, blandade medieuppsättningar och video. Dessutom är visningsprogrammet responsivt. Skärmstorleken ändras alltså automatiskt baserat på skärmstorleken. Alla visningsprogram är HTML5-visningsprogram.

>[!NOTE]
>
>Om det finns en Dynamic Media-komponent, en Interactive Media-komponent eller båda på en webbsida som en användare med skrivskyddad behörighet har åtkomst till, bryts sidan och komponenterna återges inte korrekt. Orsaken är att sidan har rekonstruerats för att komponenterna ska bli bra och att alla refererade resurser och konfigurationer är tillgängliga. Sidan återges sedan igen så att komponenterna bryts. respektive komponentkod på sidan kan inte återges på nytt på grund av användarens skrivskyddade åtkomst.
>  
>För att undvika det här problemet måste AEM Sites-användare ha de behörigheter som krävs för att få åtkomst till resurserna.

>[!NOTE]
>
>När du lägger till Dynamic Media-komponenten och **[!UICONTROL Dynamic Media Settings]** är tom eller du inte kan lägga till en resurs korrekt bör du kontrollera följande:
>
>* Du har [aktiverat Dynamic Media](config-dynamic.md). Dynamic Media är inaktiverat som standard.
>* Bilden har en pyramidformad fil. Bilder som importerats innan dynamiska medier har aktiverats har ingen pyramiddiff-fil.

>



#### När du arbetar med bilder {#when-working-with-images}

Med Dynamic Media-komponenten kan du lägga till dynamiska bilder, inklusive bilduppsättningar, snurremsor och blandade medieuppsättningar. Du kan zooma in, zooma ut och, om tillämpligt, vrida en bild i en snurra eller välja en bild från en annan typ av uppsättning.

Du kan också konfigurera visningsförinställningen, bildförinställningen eller bildformatet direkt i komponenten. Om du vill göra en bild responsiv kan du antingen ange brytpunkter eller använda en responsiv bildförinställning.

Du måste redigera följande Dynamic Media-inställningar genom att klicka på ikonen **[!UICONTROL Edit]** i komponenten och sedan på **[!UICONTROL Dynamic Media Settings]**.

![dm-settings-image-preset](assets/dm-settings-image-preset.png)

>[!NOTE]
>
>Som standard är Dynamic Media-bildkomponenten adaptiv. Om du vill göra den till en fast storlek anger du den i komponenten på fliken **[!UICONTROL Advanced]** med inställningarna **[!UICONTROL Width]** och **[!UICONTROL Height]**.

* **[!UICONTROL Viewer preset]**
Välj en befintlig visningsförinställning i listrutan. Om den visningsförinställning som du söker efter inte visas kanske du måste göra den synlig. Se Hantera förinställningar för visningsprogram. Du kan inte välja en visningsförinställning om du använder en bildförinställning och vice versa.
Det här är det enda tillgängliga alternativet om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar. De visningsförinställningar som visas är också smarta - endast relevanta visningsprogramförinställningar visas.

* **[!UICONTROL Viewer modifiers]**
Visningsmodifierare har formen av namn=värde-par med en &amp;-avgränsare och du kan ändra visningsprogram enligt riktlinjerna i referenshandboken för visningsprogram. Ett exempel på en visningsmodifierare är posterimage=img.jpg&amp;caption=text.vtt,1 som anger en annan bild för videominiatyrbilden och associerar en undertextfil med videon.

* **[!UICONTROL Image preset]**
Välj en befintlig bildförinställning i listrutan. Om den bildförinställning du söker inte syns kan du behöva göra den synlig. Se Hantera bildförinställningar. Du kan inte välja en visningsförinställning om du använder en bildförinställning och vice versa.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL Image Modifiers]**
Du kan använda bildeffekter genom att ange ytterligare bildkommandon. Dessa beskrivs i Bildförinställningar och i Referens för bildserverkommando.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL Breakpoints]**
Om du använder resursen på en responsiv webbplats måste du lägga till bildbrytpunkterna. Bildbrytpunkter måste avgränsas med kommatecken (,). Det här alternativet fungerar när ingen höjd eller bredd har definierats i en bildförinställning.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.
Du kan redigera följande avancerade inställningar genom att klicka på **[!UICONTROL Edit]** i komponenten.

* **[!UICONTROL Title]**
Ändra bildens titel.

* **[!UICONTROL Alt Text]**
Lägg till en titel i bilden för de användare som har inaktiverat grafik.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL URL, Open in]**
Du kan ställa in en resurs för att öppna en länk. Ange URL:en och Öppna i anger om du vill att den ska öppnas i samma fönster eller i ett nytt fönster.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL Width]** och  **[!UICONTROL Height]**
ange värdet i pixlar om du vill att bilden ska ha en fast storlek. Om du lämnar dessa värden tomma anpassas resursen.

#### När du arbetar med video {#when-working-with-video}

Använd Dynamic Media-komponenten för att lägga till dynamisk video på dina webbsidor. När du redigerar komponenten kan du välja att använda en fördefinierad videovisningsförinställning för att spela upp videon på sidan.

![chlimage_1-540](assets/chlimage_1-540.png)

Du måste redigera följande Dynamic Media-inställningar genom att klicka på **[!UICONTROL Edit]** i komponenten.

>[!NOTE]
>
>Som standard är videokomponenten i Dynamic Media adaptiv. Om du vill göra den till en fast storlek anger du den i komponenten med **[!UICONTROL Width]** och **[!UICONTROL Height]** på fliken [!UICONTROL Advanced].

* **[!UICONTROL Viewer preset]**
Välj en befintlig förinställning för visningsprogrammet för video i listrutan. Om den visningsförinställning som du söker efter inte visas kanske du måste göra den synlig. Se Hantera förinställningar för visningsprogram.

* **[!UICONTROL Viewer modifiers]**
Visningsmodifierare har formen av namn=värde-par med en &amp;-avgränsare och du kan ändra visningsprogram enligt riktlinjerna i referenshandboken för Adobe-visningsprogram. Ett exempel på en visningsmodifierare är posterimage=img.jpg&amp;caption=text.vtt,1

   Med visningsmodifierare kan du till exempel göra följande:

   * Associera en bildtextfil med en videobeskrivning [.](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/video/command-reference-url-video/r-html5-video-viewer-url-caption.html)
   * Associera en navigeringsfil med en video [navigering.](https://experienceleague.adobe.com/docs/dynamic-media-developer-resources/library/viewers-aem-assets-dmc/video/command-reference-url-video/r-html5-video-viewer-url-navigation.html)

Du kan redigera följande [!UICONTROL Advanced Settings] genom att klicka på **[!UICONTROL Edit]** i komponenten.

* **[!UICONTROL Title]**
Ändra videons titel.

* **[!UICONTROL Width]** och  **[!UICONTROL Height]**
ange värdet i pixlar om du vill att videon ska ha en fast storlek. Om du lämnar dessa värden tomma blir de anpassningsbara.

#### När du arbetar med smart beskärning {#when-working-with-smart-crop}

Använd Dynamic Media-komponenten för att lägga till bildresurser för Smart beskärning på dina webbsidor. När du redigerar komponenten kan du välja att använda en fördefinierad videovisningsförinställning för att spela upp videon på sidan.

Se även [Bildprofiler](image-profiles.md).

![dm-settings-smart-crop](assets/dm-settings-smart-crop.png)

Du kan redigera följande [!UICONTROL Dynamic Media Settings] genom att klicka på **[!UICONTROL Edit]** i komponenten.

>[!NOTE]
>
>Som standard är Dynamic Media-bildkomponenten adaptiv. Om du vill att den ska ha en fast storlek anger du det i komponenten på fliken [!UICONTROL Advanced] med **[!UICONTROL Width]** och **[!UICONTROL Height]**.

* **[!UICONTROL Image Modifiers]**
Du kan använda bildeffekter genom att ange ytterligare bildkommandon. Dessa beskrivs i Bildförinställningar och i Referens för bildserverkommando.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

Du kan redigera följande **[!UICONTROL Advanced]**-inställningar genom att klicka på **[!UICONTROL Edit]** i komponenten.

* **[!UICONTROL Title]**
Ändra titeln på bilden för smart beskärning.

* **[!UICONTROL Alt Text]**
Lägg till en titel i den smarta beskärningsbilden för de användare som har inaktiverat grafik.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL URL, Open in]**
Du kan ställa in en resurs för att öppna en länk. Ange URL:en och Öppna i anger om du vill att den ska öppnas i samma fönster eller i ett nytt fönster.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL Height]** och  **[!UICONTROL Width]**
ange värdet i pixlar om du vill att den smarta beskärningsbilden ska ha en fast storlek. Om du lämnar dessa värden tomma blir de anpassningsbara.

### Interaktiv mediekomponent {#interactive-media-component}

Komponenten Interactive Media är till för de resurser som har interaktivitet i dem, till exempel hotspot-områden eller bildscheman. Om du har en interaktiv bild, interaktiv video eller karusellbanderoll använder du komponenten Interactive Media.

Komponenten Interactive Media är smart - beroende på om du lägger till en bild eller en video finns det olika alternativ. Dessutom är visningsprogrammet responsivt - skärmstorleken ändras automatiskt baserat på skärmstorleken. Alla visningsprogram är HTML5-visningsprogram.

>[!NOTE]
>
>Om det finns en Dynamic Media-komponent, en Interactive Media-komponent eller båda på en webbsida som en användare med skrivskyddad behörighet har åtkomst till, bryts sidan och komponenterna återges inte korrekt. Orsaken är att sidan har rekonstruerats för att komponenterna ska bli bra och att alla refererade resurser och konfigurationer är tillgängliga. Sidan återges sedan igen så att komponenterna bryts. respektive komponentkod på sidan kan inte återges på nytt på grund av användarens skrivskyddade åtkomst.
> 
>För att undvika det här problemet måste AEM Sites-användare ha de behörigheter som krävs för att få åtkomst till resurserna.

![chlimage_1-541](assets/chlimage_1-541.png)

Du kan redigera följande **[!UICONTROL General]**-inställningar genom att klicka på **[!UICONTROL Edit]** i komponenten.

* **[!UICONTROL Viewer preset]**
Välj en befintlig visningsförinställning i listrutan. Om den visningsförinställning som du söker efter inte visas kanske du måste göra den synlig. Förinställningar för visningsprogram måste publiceras innan de kan användas. Se Hantera förinställningar för visningsprogram.

* **[!UICONTROL Title]**
Ändra videons titel.

* **[!UICONTROL Width]** och  **[!UICONTROL Height]**
ange värdet i pixlar om du vill att videon ska ha en fast storlek. Om du lämnar dessa värden tomma blir de anpassningsbara.

Du kan redigera följande **[!UICONTROL Add To Cart]**-inställningar genom att klicka på **[!UICONTROL Edit]** i komponenten.

* **[!UICONTROL Show Product Asset]**
Som standard är det här värdet markerat. Produktresursen visar en bild av produkten enligt definitionen i modulen Handel. Avmarkera kryssrutan om du inte vill visa produktresursen.

* **[!UICONTROL Show Product Price]**
Som standard är det här värdet markerat. Produktpriset visar priset för artikeln enligt definitionen i modulen Handel. Avmarkera kryssrutan om du inte vill visa produktpriset.

* **[!UICONTROL Show Product Form]**
Som standard är det här värdet inte markerat. Produktformuläret innehåller alla produktvarianter som storlek och färg. Avmarkera kryssrutan om du inte vill visa produktvarianterna.

### Panoramamediekomponent {#panoramic-media-component}

Komponenten för panoramamedia är avsedd för resurser som är sfäriska panoramabilder. Sådana bilder ger en 360-gradig visningsupplevelse av ett rum, en egenskap, en plats eller ett landskap. För att en bild ska kvalificeras som ett sfäriskt panorama måste den ha antingen ett ELLER båda av följande:

* Proportionerna 2:1.
* Taggad med nyckelorden &quot;ekvirektangulär&quot; eller (&quot;sfärisk&quot; + &quot;panorama&quot;) eller (&quot;sfärisk&quot; + &quot;panoramabild&quot;). Se [Använda taggar](/help/sites-authoring/tags.md).

Både proportioner och nyckelordskriterier gäller för panoramaresurser för sidan med resursinformation och WCM-komponenten &quot;Panoramic Media&quot;.

![panoramabild-media-viewer-preset](assets/panoramic-media-viewer-preset.png)

Du kan redigera följande inställning genom att trycka på **[!UICONTROL Configure]** i komponenten.

* **[!UICONTROL Viewer Preset]**
Välj ett befintligt visningsprogram på den nedrullningsbara menyn Visningsförinställning.

Om den visningsförinställning du söker efter inte visas kontrollerar du att den är publicerad. Du måste publicera förinställningarna för visningsprogrammet innan du kan använda dem. Se [Hantera visningsförinställningar](managing-viewer-presets.md).

### Använda HTTP/2 för att leverera Dynamic Media-resurser {#using-http-to-delivery-dynamic-media-assets}

HTTP/2 är det nya, uppdaterade webbprotokollet som förbättrar kommunikationen mellan webbläsare och servrar. Det ger snabbare överföring av information och minskar mängden processorkraft som behövs. Dynamic Media-material kan nu levereras via HTTP/2 vilket ger bättre respons och laddningstider.

Se [HTTP2 Delivery of Content](http2.md) för fullständig information om hur du kommer igång med HTTP/2 med ditt Dynamic Media-konto.

>[!MORELIKETHIS]
>
>* [Färghantering med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-color-management-technical-video-setup.html)
>* [Använda anpassade videominiatyrbilder med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-video-thumbnails-feature-video-use.html)
>* [Om resursvisningsprogrammet med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-viewer-feature-video-understand.html)
>* [Använda interaktiv video med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-interactive-video-feature-video-use.html)
>* [Använda videospelaren i AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-video-player-feature-video-use.html)
>* [Använda bildskärpa med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/6-4/assets/using/best-practices-for-optimizing-the-quality-of-your-images.html)

