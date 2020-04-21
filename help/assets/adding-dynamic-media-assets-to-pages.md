---
title: Lägga till dynamiska medieresurser på sidor
seo-title: Lägga till dynamiska medieresurser på sidor
description: Lägga till komponenter för dynamiska media på en sida i AEM
seo-description: Lägga till komponenter för dynamiska media på en sida i AEM
uuid: 77abcb87-2df7-449b-be52-540d749890b6
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: d1f45751-1761-4d6b-b17d-110b2f1117ea
translation-type: tm+mt
source-git-commit: ef00b3d307e01807f90bad8c8fde278204470bc3

---


# Lägga till Dynamic Media-resurser på sidor {#adding-dynamic-media-assets-to-pages}

To add the dynamic media functionality to assets you use on your websites, you can add the **Dynamic Media** or **Interactive Media** component directly on the page. Det gör du genom att öppna layoutläget och aktivera de dynamiska mediekomponenterna. Sedan kan du lägga till komponenterna på sidan och lägga till resurser i komponenterna. Komponenterna för dynamiska media och interaktiva media är smarta - de vet om du lägger till en bild eller en video och de tillgängliga alternativen ändras i enlighet med detta.

Du lägger till dynamiska medieresurser direkt på sidan om du använder AEM som WCM. Om ni använder en annan leverantör för innehållshanteringssystemet kan ni antingen [länka](linking-urls-to-yourwebapplication.md) eller [bädda in](embed-code.md) resurserna. Om du har en responsiv webbplats hos en extern leverantör läser du [Leverera optimerade bilder till en responsiv webbplats](responsive-site.md).

>[!NOTE]
>
>Du måste publicera resurser innan du lägger till dem på sidor i AEM. See [Publishing Dynamic Media Assets](publishing-dynamicmedia-assets.md).

## Lägga till en Dynamic Media-komponent på en sida {#adding-a-dynamic-media-component-to-a-page}

Att lägga till komponenten Dynamic Media eller Interactive Media på en sida är detsamma som att lägga till en komponent på en sida. Komponenterna Dynamic Media och Interactive Media beskrivs i detalj i följande avsnitt.

>[!NOTE]
>
>Om det finns en Dynamic Media-komponent, en Interactive Media-komponent eller både och på en webbsida som en användare med skrivskyddad behörighet har åtkomst till, bryts sidan och komponenterna återges inte korrekt. Orsaken är att sidan har rekonstruerats för att komponenterna ska bli bra och att alla refererade resurser och konfigurationer är tillgängliga. Sidan återges sedan igen så att komponenterna bryts. respektive komponentkod på sidan kan inte återges på nytt på grund av användarens skrivskyddade åtkomst.
>  
>Undvik problemet genom att se till att AEM Sites-användare har de behörigheter som krävs för att få tillgång till resurserna.

1. I AEM öppnar du sidan där du vill lägga till komponenten Dynamic Media eller Interactive Media.
1. Klicka på ikonen **[!UICONTROL Komponenter]** i den vänstra rutan och filtrera efter **[!UICONTROL Dynamic Media]**. Om ingen Dynamic Media-komponent är tillgänglig måste du aktivera komponenterna för Dynamic Media. Mer information finns i [Redigera sidmallar](/help/sites-authoring/templates.md#editing-templates-template-authors) .

   ![chlimage_1-538](assets/chlimage_1-537.png)

1. Dra **[!UICONTROL komponenten Dynamic Media]** eller **[!UICONTROL Interactive Media]** till sidan på önskad plats.
1. Klicka på den blå rutan runt komponenten och tryck sedan på ikonen **[!UICONTROL Konfiguration]** (skiftnyckel).
1. [Redigera komponenterna](#dynamic-media-components) efter behov och klicka på bockmarkeringen för att spara ändringarna.

## Lokalisera komponenter för dynamiska media {#localizing-dynamic-media-components}

Du kan lokalisera komponenter för dynamiska media på ett av två sätt:

* Within a web page in Sites, open **[!UICONTROL Properties]** and select the **[!UICONTROL Advanced]** tab. Välj språk för lokalisering.

   ![chlimage_1-538](assets/chlimage_1-538.png)

* Välj önskad sida eller sidgrupp i platsväljaren. Tryck på **[!UICONTROL Egenskaper]** och välj fliken **[!UICONTROL Avancerat]** . Välj språk för lokalisering.

   >[!NOTE]
   >
   >Observera att inte alla språk som är tillgängliga på menyn **[!UICONTROL Språk]** har tilldelats tokens.

## Dynamiska mediakomponenter {#dynamic-media-components}

Dynamiska media och interaktiva media är tillgängliga under fliken [!UICONTROL Dynamiska media] i [!UICONTROL Komponenter]. Du använder komponenten Interactive Media] för interaktiva resurser som interaktiv video, interaktiva bilder eller karuselluppsättningar. Använd komponenten Dynamic Media för alla andra dynamiska mediekomponenter.

>[!NOTE]
>
>De här komponenterna är inte tillgängliga som standard och måste göras tillgängliga via mallredigeraren innan du använder dem. [När de har gjorts tillgängliga](/help/sites-authoring/templates.md#editing-templates-template-authors)i mallredigeraren kan du lägga till komponenterna på sidan på samma sätt som andra AEM-komponenter.

![chlimage_1-539](assets/chlimage_1-539.png)

### Dynamic Media-komponent {#dynamic-media-component}

Komponenten Dynamic Media är smart - beroende på om du lägger till en bild eller en video finns det olika alternativ. Komponenten har stöd för bildförinställningar, bildbaserade visningsprogram som bilduppsättningar, snurra, blandade medieuppsättningar och video. Dessutom är visningsprogrammet responsivt. Skärmstorleken ändras alltså automatiskt baserat på skärmstorleken. Alla visningsprogram är HTML5-visningsprogram.

>[!NOTE]
>
>Om det finns en Dynamic Media-komponent, en Interactive Media-komponent eller både och på en webbsida som en användare med skrivskyddad behörighet har åtkomst till, bryts sidan och komponenterna återges inte korrekt. Orsaken är att sidan har rekonstruerats för att komponenterna ska bli bra och att alla refererade resurser och konfigurationer är tillgängliga. Sidan återges sedan igen så att komponenterna bryts. respektive komponentkod på sidan kan inte återges på nytt på grund av användarens skrivskyddade åtkomst.
>  
>Undvik problemet genom att se till att AEM Sites-användare har de behörigheter som krävs för att få tillgång till resurserna.

>[!NOTE]
>
>När du lägger till komponenten Dynamic Media och **[!UICONTROL Dynamiska mediainställningar]** är tomma eller du inte kan lägga till en resurs på rätt sätt ska du kontrollera följande:
>
>* Du har [aktiverat Dynamic Media](config-dynamic.md). Dynamiska media är inaktiverat som standard.
>* Bilden har en pyramidformad fil. Bilder som importerats innan dynamiska medier aktiverats har ingen pyramiddiff-fil.
>



#### När du arbetar med bilder {#when-working-with-images}

Med komponenten Dynamic Media kan du lägga till dynamiska bilder, inklusive bilduppsättningar, snurpuppsättningar och blandade medieuppsättningar. Du kan zooma in, zooma ut och, om tillämpligt, vrida en bild i en snurra eller välja en bild från en annan typ av uppsättning.

Du kan också konfigurera visningsförinställningen, bildförinställningen eller bildformatet direkt i komponenten. Om du vill göra en bild responsiv kan du antingen ange brytpunkter eller använda en responsiv bildförinställning.

Du måste redigera följande dynamiska mediainställningar genom att klicka på **[!UICONTROL redigeringsikonen]** i komponenten och sedan på **[!UICONTROL Dynamiska mediainställningar]**.

![dm-settings-image-preset](assets/dm-settings-image-preset.png)

>[!NOTE]
>
>Som standard är Dynamic Media-bildkomponenten adaptiv. If you want to make it a fixed size, set it in the component in the **[!UICONTROL Advanced]** tab with the **[!UICONTROL Width]** and **[!UICONTROL Height]** settings.

* **[!UICONTROL Förinställning]**för visningsprogram Välj en befintlig förinställning för visningsprogram i listrutan. Om den visningsförinställning som du söker efter inte visas kan du behöva göra den synlig. Se Hantera förinställningar för visningsprogram. Du kan inte välja en visningsförinställning om du använder en bildförinställning och vice versa.
Det här är det enda tillgängliga alternativet om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar. De visningsförinställningar som visas är också smarta - endast relevanta visningsprogramförinställningar visas.

* **[!UICONTROL Visningsprogrammodifierare]** Visningsprogrammodifierare har formen av namn=värde-par med en &amp;-avgränsare och du kan ändra visningsprogram enligt anvisningarna i referenshandboken för visningsprogram. Ett exempel på en visningsmodifierare är posterimage=img.jpg&amp;caption=text.vtt,1 som ställer in en annan bild för videominiatyrbilden och associerar en undertextfil med videon.

* **[!UICONTROL Bildförinställning]**Välj en befintlig bildförinställning i listrutan. Om den bildförinställning du söker inte syns kan du behöva göra den synlig. Se Hantera bildförinställningar. Du kan inte välja en visningsförinställning om du använder en bildförinställning och vice versa.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL Bildmodifierare]**Du kan använda bildeffekter genom att ange ytterligare bildkommandon. Dessa beskrivs i Bildförinställningar och i Referens för bildserverkommando.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL Brytpunkter]**Om du använder den här resursen på en responsiv webbplats måste du lägga till bildbrytpunkter. Bildbrytpunkter måste avgränsas med kommatecken (,). Det här alternativet fungerar när ingen höjd eller bredd har definierats i en bildförinställning.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.
You can edit the following Advanced Settings by clicking **[!UICONTROL Edit]** in the component.

* **[!UICONTROL Titel]**&#x200B;Ändra bildens titel.

* **[!UICONTROL Alt Text]**Lägg till en titel i bilden för användare som har bilder inaktiverade.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL URL, Öppna i]**Du kan ange att en resurs ska öppna en länk. Ange URL:en och Öppna i anger om du vill att den ska öppnas i samma fönster eller i ett nytt fönster.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL Bredd]** och **[!UICONTROL höjd]** Ange ett värde i pixlar om du vill att bilden ska ha en fast storlek. Om du lämnar dessa värden tomma anpassas resursen.

#### När du arbetar med video {#when-working-with-video}

Använd komponenten Dynamic Media för att lägga till dynamisk video på dina webbsidor. När du redigerar komponenten kan du välja att använda en fördefinierad videovisningsförinställning för att spela upp videon på sidan.

![chlimage_1-540](assets/chlimage_1-540.png)

Du måste redigera följande dynamiska mediainställningar genom att klicka på **[!UICONTROL Redigera]** i komponenten.

>[!NOTE]
>
>Som standard är videokomponenten för dynamiska media adaptiv. Om du vill göra den till en fast storlek anger du den i komponenten med **[!UICONTROL Bredd]** och **[!UICONTROL Höjd]** på fliken [!UICONTROL Avancerat] .

* **[!UICONTROL Förinställning]** för visningsprogram Välj en befintlig förinställning för visningsprogrammet i listrutan. Om den visningsförinställning som du söker efter inte visas kan du behöva göra den synlig. Se Hantera förinställningar för visningsprogram.

* **[!UICONTROL Visningsmodifierare]** Visningsprogrammodifierare har formen av namn=värde-par med en &amp;-avgränsare och du kan ändra visningsprogram enligt riktlinjerna i referenshandboken för Adobe Viewer. Ett exempel på en visningsmodifierare är posterimage=img.jpg&amp;caption=text.vtt,1

   Med visningsmodifierare kan du till exempel göra följande:

   * Associera en bildtextfil med en video [https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/r_html5_video_viewer_url_caption.html](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/r_html5_video_viewer_url_caption.html)
   * Associera en navigeringsfil med en video [https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/r_html5_video_viewer_url_navigation.html](https://marketing.adobe.com/resources/help/en_US/s7/viewers_ref/r_html5_video_viewer_url_navigation.html)

You can edit the following [!UICONTROL Advanced Settings] by clicking **[!UICONTROL Edit]** in the component.

* **[!UICONTROL Titel]**&#x200B;Ändra videons titel.

* **[!UICONTROL Bredd]** och **[!UICONTROL höjd]** Ange värdet i pixlar om du vill att videon ska ha en fast storlek. Om du lämnar dessa värden tomma blir de anpassningsbara.

#### När du arbetar med smart beskärning {#when-working-with-smart-crop}

Använd komponenten Dynamic Media för att lägga till bildresurser för smart beskärning på dina webbsidor. När du redigerar komponenten kan du välja att använda en fördefinierad videovisningsförinställning för att spela upp videon på sidan.

Se även [Bildprofiler](image-profiles.md).

![dm-settings-smart-crop](assets/dm-settings-smart-crop.png)

You can edit the following [!UICONTROL Dynamic Media Settings] by clicking **[!UICONTROL Edit]** in the component.

>[!NOTE]
>
>Som standard är Dynamic Media-bildkomponenten adaptiv. If you want to make it a fixed size, set it in the component in the [!UICONTROL Advanced] tab with the **[!UICONTROL Width]** and **[!UICONTROL Height]**.

* **[!UICONTROL Bildmodifierare]**Du kan använda bildeffekter genom att ange ytterligare bildkommandon. Dessa beskrivs i Bildförinställningar och i Referens för bildserverkommando.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

You can edit the following **[!UICONTROL Advanced]** settings by clicking **[!UICONTROL Edit]** in the component.

* **[!UICONTROL Titel]**&#x200B;Ändra titeln på bilden för smart beskärning.

* **[!UICONTROL Alt Text]**Lägg till en titel i den smarta beskärningsbilden för de användare som har inaktiverat grafik.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL URL, Öppna i]**Du kan ange att en resurs ska öppna en länk. Ange URL:en och Öppna i anger om du vill att den ska öppnas i samma fönster eller i ett nytt fönster.
Det här alternativet är inte tillgängligt om du visar bilduppsättningar, snurruppsättningar eller blandade medieuppsättningar.

* **[!UICONTROL Höjd** och **[!UICONTROL Bredd]** Ange värdet i pixlar om du vill att den smarta beskärningsbilden ska ha en fast storlek. Om du lämnar dessa värden tomma blir de anpassningsbara.

### Interaktiv mediekomponent {#interactive-media-component}

Komponenten Interactive Media är till för de resurser som har interaktivitet i dem, till exempel hotspot-områden eller bildscheman. Om du har en interaktiv bild, interaktiv video eller karusellbanderoll använder du komponenten Interactive Media.

Komponenten Interactive Media är smart - beroende på om du lägger till en bild eller en video finns det olika alternativ. Dessutom är visningsprogrammet responsivt - skärmstorleken ändras automatiskt baserat på skärmstorleken. Alla visningsprogram är HTML5-visningsprogram.

>[!NOTE]
>
>Om det finns en Dynamic Media-komponent, en Interactive Media-komponent eller både och på en webbsida som en användare med skrivskyddad behörighet har åtkomst till, bryts sidan och komponenterna återges inte korrekt. Orsaken är att sidan har rekonstruerats för att komponenterna ska bli bra och att alla refererade resurser och konfigurationer är tillgängliga. Sidan återges sedan igen så att komponenterna bryts. respektive komponentkod på sidan kan inte återges på nytt på grund av användarens skrivskyddade åtkomst.
> 
>Undvik problemet genom att se till att AEM Sites-användare har de behörigheter som krävs för att få tillgång till resurserna.

![chlimage_1-541](assets/chlimage_1-541.png)

You can edit the following **[!UICONTROL General]** settings by clicking **[!UICONTROL Edit]** in the component.

* **[!UICONTROL Förinställning]** för visningsprogram Välj en befintlig förinställning för visningsprogram i listrutan. Om den visningsförinställning som du söker efter inte visas kanske du måste göra den synlig. Förinställningar för visningsprogram måste publiceras innan de kan användas. Se Hantera förinställningar för visningsprogram.

* **[!UICONTROL Titel]**&#x200B;Ändra videons titel.

* **[!UICONTROL Bredd]** och **[!UICONTROL höjd]** Ange värdet i pixlar om du vill att videon ska ha en fast storlek. Om du lämnar dessa värden tomma blir de anpassningsbara.

You can edit the following **[!UICONTROL Add To Cart]** settings by clicking **[!UICONTROL Edit]** in the component.

* **[!UICONTROL Visa produktresurs]** Som standard är det här värdet valt. Produktresursen visar en bild av produkten enligt definitionen i modulen Handel. Avmarkera kryssrutan om du inte vill visa produktresursen.

* **[!UICONTROL Visa produktpris]** Som standard är det här värdet valt. Produktpriset visar priset för artikeln enligt definitionen i modulen Handel. Avmarkera kryssrutan om du inte vill visa produktpriset.

* **[!UICONTROL Visa produktformulär]** Som standard är det här värdet inte valt. Produktformuläret innehåller alla produktvarianter som storlek och färg. Avmarkera kryssrutan om du inte vill visa produktvarianterna.

### Panoramakomponenten Media {#panoramic-media-component}

Komponenten för panoramamedia är avsedd för resurser som är sfäriska panoramabilder. Sådana bilder ger en 360-gradig visningsupplevelse av ett rum, en egenskap, en plats eller ett landskap. För att en bild ska kvalificeras som ett sfäriskt panorama måste den ha antingen ett ELLER båda av följande:

* Proportionerna 2:1.
* Taggad med nyckelorden &quot;ekvirektangulär&quot; eller (&quot;sfärisk&quot; + &quot;panorama&quot;) eller (&quot;sfärisk&quot; + &quot;panoramabild&quot;). Se [Använda taggar](/help/sites-authoring/tags.md).

Både proportioner och nyckelordskriterier gäller för panoramaresurser för sidan med resursinformation och WCM-komponenten &quot;Panoramic Media&quot;.

![panoramabild-media-viewer-preset](assets/panoramic-media-viewer-preset.png)

Du kan redigera följande inställning genom att trycka på **[!UICONTROL Konfigurera]** i komponenten.

* **[!UICONTROL Förinställning]** för visningsprogram Välj ett befintligt visningsprogram i listrutan med förinställningar för visningsprogram.

Om den visningsförinställning du söker efter inte visas kontrollerar du att den är publicerad. Du måste publicera förinställningarna för visningsprogrammet innan du kan använda dem. Se [Hantera visningsförinställningar](managing-viewer-presets.md).

### Använda HTTP/2 för att leverera Dynamic Media-resurser {#using-http-to-delivery-dynamic-media-assets}

HTTP/2 är det nya, uppdaterade webbprotokollet som förbättrar kommunikationen mellan webbläsare och servrar. Det ger snabbare överföring av information och minskar mängden processorkraft som behövs. Dynamic Media-material kan nu levereras via HTTP/2 vilket ger bättre respons och laddningstider.

Se [HTTP2 Delivery of Content](http2.md) för fullständig information om hur du kommer igång med HTTP/2 med ditt Dynamic Media-konto.

>[!MORELIKETHIS]
>
>* [Färghantering med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-color-management-technical-video-setup.html)
>* [Använda anpassade videominiatyrer med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-video-thumbnails-feature-video-use.html)
>* [Så här fungerar resursvisningsprogrammet med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-viewer-feature-video-understand.html)
>* [Använda interaktiv video med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-interactive-video-feature-video-use.html)
>* [Använda videospelaren i AEM Dynamic Media](https://helpx.adobe.com/experience-manager/kt/assets/using/dynamic-media-video-player-feature-video-use.html)
>* [Använda bildskärpa med AEM Dynamic Media](https://helpx.adobe.com/experience-manager/6-4/assets/using/best-practices-for-optimizing-the-quality-of-your-images.html)

