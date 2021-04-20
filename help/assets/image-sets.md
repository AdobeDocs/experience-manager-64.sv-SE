---
title: Bilduppsättningar
seo-title: Bilduppsättningar
description: Lär dig hur du arbetar med bilduppsättningar i dynamiska medier
seo-description: Lär dig hur du arbetar med bilduppsättningar i dynamiska medier
uuid: 16008278-f59f-4fa8-90e9-19c78f132439
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: e00e7cc9-b777-4f9e-906d-824bcb2bbd41
exl-id: af3f95aa-a162-4212-a20a-68b5a0e72d6d
feature: Image Sets
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '1984'
ht-degree: 11%

---

# Bilduppsättningar {#image-sets}

Bilduppsättningar ger användarna en integrerad visningsupplevelse, där användarna kan se olika vyer av ett objekt genom att klicka på en miniatyrbild. Med bilduppsättningar kan du visa alternativa vyer av ett objekt och visningsprogrammet har zoomverktyg som gör att du kan granska bilder noggrant.

Bilduppsättningar definieras av en banderoll med ordet **[!UICONTROL IMAGESET]**. Om bilduppsättningen publiceras visas dessutom det publiceringsdatum som anges av ikonen **[!UICONTROL World]** på banderollen tillsammans med det senaste ändringsdatumet, som anges av ikonen **[!UICONTROL Pencil]**.

![chlimage_1-339](assets/chlimage_1-339.png)

I bilduppsättningen kan du även skapa färgrutor genom att skapa en bilduppsättning och lägga till miniatyrbilder.

Det här programmet är särskilt användbart när du vill visa ett objekt i en annan färg, ett annat mönster eller en annan avslutning. Om du vill skapa en bilduppsättning med färgrutor behöver du en bild för varje färg, mönster eller slut som du vill presentera för användarna. Du behöver också en färg-, mönster- eller slutfärgruta för varje färg, mönster eller slut.

Anta till exempel att du vill visa bilder med olika färgskalor; räkningarna är röda, gröna och blå. I så fall behöver du tre bilder med samma lock. Du behöver en bild med rött, en med grönt och en med blå räkning. Du behöver också en röd, grön och blå färgruta. Färgrutorna fungerar som miniatyrbilder som användare klickar på i visningsprogrammet för färgrutor för att visa den röda, gröna eller blå hatten.

>[!NOTE]
>
>Mer information om användargränssnittet Resurser finns i [Hantera resurser med Touch-gränssnittet](managing-assets-touch-ui.md).

## Snabbstart: Bilduppsättningar {#quick-start-image-sets}

Så här kommer du igång snabbt:

1. [Överför dina primära bilder för flera vyer.](#uploading-assets-in-image-sets)

   Börja med att ladda upp bilderna för dina bilduppsättningar. Eftersom användare kan zooma in på bilder i bilduppsättningsvisningsprogrammet bör du ta hänsyn till zoomning när du väljer bilder. Se till att bilderna har minst 2 000 pixlar i den största dimensionen för optimal zoomdetaljrikedom. Dynamic Media kan återge bilder på upp till 25 megapixlar vardera. Du kan till exempel använda en 5 000 × 5 000 megapixelbild eller någon annan storlekskombination på upp till 25 megapixlar.

   AEM Assets har stöd för många bildfilsformat, men förlustfria TIFF-, PNG- och EPS-bilder rekommenderas.

1. [Skapa bilduppsättningar.](#creating-image-sets)

   I Bilduppsättningar klickar användare på miniatyrbilder i Bilduppsättningsvisningsprogrammet.

   Om du vill skapa en bilduppsättning i Assets trycker du på **[!UICONTROL Create > Image Sets]**. Lägg sedan till bilder och tryck på **[!UICONTROL Save]**.

   Du kan också skapa bilduppsättningar automatiskt med [gruppuppsättningsförinställningar](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

   **Viktigt**  - Batchuppsättningar skapas av IPS (Image Production System) som en del av tillgångsintag och är endast tillgängliga i Dynamic Media - Scene7.

   Se [Förbereda bilduppsättningsresurser för överföring och överföring av filer](#uploading-assets-in-image-sets).

   Se [Arbeta med väljare.](working-with-selectors.md)

1. Lägg till [Image Set Viewer-förinställningar](managing-viewer-presets.md) efter behov.

   Administratörer kan skapa eller ändra bild **[!UICONTROL Set Viewer Presets]**. Om du vill visa bilduppsättningen med en visningsförinställning markerar du bilduppsättningen och väljer **[!UICONTROL Viewers]** i listrutan till vänster.

   Se **[!UICONTROL Tools > Assets > Viewer Presets]** om du vill skapa eller redigera visningsprogramförinställningar.

1. (Valfritt) [Visa bilduppsättningar](image-sets.md#viewing-image-sets) som har skapats med gruppuppsättningsförinställningar.
1. [Förhandsgranska bilduppsättningar.](previewing-assets.md)

   Markera bilduppsättningen och du kan förhandsgranska den. Tryck på miniatyrbildikonerna för att undersöka bilduppsättningen i det valda visningsprogrammet. Du kan välja olika visningsprogram på menyn **[!UICONTROL Viewers]**, som finns i den vänstra listrutan.

1. [Publicera bilduppsättningar.](publishing-dynamicmedia-assets.md)

   När du publicerar en bilduppsättning aktiveras URL-adressen och strängen Embed. Dessutom måste du [publicera alla anpassade visningsförinställningar](managing-viewer-presets.md) som du har skapat. Visningsförinställningarna som är färdiga för leverans har redan publicerats.

1. [Länka URL:er till webbprogrammet ](linking-urls-to-yourwebapplication.md) eller  [bädda in video- eller bildvisningsprogrammet](embed-code.md).

   AEM Assets skapar URL-anrop för bilduppsättningar och aktiverar dem när du har publicerat bilduppsättningarna. Du kan kopiera dessa URL:er när du förhandsgranskar resurser. Du kan även bädda in dem på din webbplats.

   Markera bilduppsättningen och välj sedan **[!UICONTROL Viewers]** i listrutan till vänster.

   Läs mer i [Länka en bilduppsättning till en webbsida](linking-urls-to-yourwebapplication.md) och [Bädda in video- eller bildvisningsprogrammet](embed-code.md).

Mer information om hur du redigerar bilduppsättningar finns i [Redigera bilduppsättningar.](#editing-image-sets) Dessutom kan du visa och redigera  [bilduppsättningsegenskaper](managing-assets-touch-ui.md#editing-properties).

Om du har problem med att skapa uppsättningar kan du läsa Bilder och uppsättningar i [Felsöka Dynamic Media - Scene7-läge](troubleshoot-dms7.md#images-and-sets).

## Överför resurser i bilduppsättningar {#uploading-assets-in-image-sets}

Börja med att ladda upp bilderna för dina bilduppsättningar. Eftersom användare kan zooma in på bilder i bilduppsättningsvisningsprogrammet bör du ta hänsyn till zoomning när du väljer bilder. Se till att bilderna har minst 2 000 pixlar i den största dimensionen. Bilduppsättningar har stöd för många bildfilsformat, men förlustfria TIFF-, PNG- och EPS-bilder rekommenderas.

Du kan överföra bilder för bilduppsättningar på samma sätt som du [överför andra resurser i Resurser](managing-assets-touch-ui.md#uploading-assets).

### Förbereder bilduppsättningsresurser för överföring {#preparing-image-set-assets-for-upload}

Innan du skapar bilduppsättningar bör du kontrollera att bilderna har rätt storlek och format.

Om du vill skapa en bilduppsättning med flera vyer behöver du bilder som visar ett objekt från olika vypunkter eller visar olika aspekter av samma objekt. Målet är att framhäva de viktiga funktionerna i ett objekt så att läsarna får en fullständig bild av hur det ser ut eller gör.

Eftersom användare kan zooma bilder i bilduppsättningar bör du se till att bilderna har minst 2 000 pixlar i den största dimensionen. Resurser har stöd för många bildfilformat, men förlustfria TIFF-, PNG- och EPS-bilder rekommenderas.

>[!NOTE]
>
>Om du använder miniatyrbilder för att ange färgrutor för produkten måste du dessutom göra följande:
>
>Du behöver vinjetter eller olika bilder av samma bild som visar den i olika färger, mönster eller färger. Du behöver också miniatyrbilder som motsvarar de olika färgerna, mönstren eller ytorna. Om du till exempel vill visa miniatyrbilder med en bilduppsättning med samma jacka i svart, brunt och grönt behöver du:
>
>* En svart, brun och grön tagning av samma jacka.
>* En svart, brun och grön färgminiatyrbild.

>



## Skapar bilduppsättningar {#creating-image-sets}

Du kan skapa bilduppsättningar via användargränssnittet eller via API:t. I det här avsnittet beskrivs hur du skapar bilduppsättningar i användargränssnittet.

>[!NOTE]
>
>Du kan också skapa bilduppsättningar automatiskt med [gruppuppsättningsförinställningar](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

**Viktigt:** Gruppuppsättningar skapas av IPS (Image Production System) som en del av tillgångsanvändningen och är endast tillgängliga i Dynamic Media - Scene7-läge.

När du lägger till resurser i uppsättningen läggs de automatiskt till i alfanumerisk ordning. Du kan ändra ordning på eller sortera resurser manuellt när de har lagts till.

>[!NOTE]
>
>Bilduppsättningar stöds inte för resurser med `,` (komma) i filnamnet.

**Så här skapar du en bilduppsättning**:

1. I **Resurser** navigerar du till den plats där du vill skapa en bilduppsättning, trycker på **[!UICONTROL Create]** och väljer **[!UICONTROL Image Set]**. Du kan också skapa uppsättningen inifrån en mapp som innehåller resurserna.

   ![chlimage_1-340](assets/chlimage_1-340.png)

1. Ange ett namn för bilduppsättningen i fältet **[!UICONTROL Title]** på sidan Bilduppsättningsredigerare. Namnet visas i banderollen över bilduppsättningen. Du kan också ange en beskrivning.

   ![chlimage_1-341](assets/chlimage_1-341.png)

   >[!NOTE]
   >
   >När du skapar bilduppsättningen kan du ändra miniatyrbilden för bilduppsättningen eller tillåta att AEM väljer miniatyrbild automatiskt baserat på resurserna i bilduppsättningen. Om du vill välja en miniatyrbild trycker du på **[!UICONTROL Change thumbnail]** och väljer en bild (du kan navigera till andra mappar för att hitta bilder också). Om du har valt en miniatyrbild och sedan bestämmer dig för att du vill att AEM ska generera en från bilduppsättningen väljer du **[!UICONTROL Switch to Automatic thumbnail]**.

1. Gör något av följande:

   * I det övre vänstra hörnet av sidan **[!UICONTROL Image Set Editor]** trycker du på **[!UICONTROL Add Asset]**.
   * I mitten av sidan **[!UICONTROL Image Set Editor]** trycker du på **[!UICONTROL Tap to open Asset Selector]**.

   Tryck för att välja resurser som du vill inkludera i din bilduppsättning. De markerade resurserna visas med en bock. När du är klar trycker du **[!UICONTROL Select]** i det övre högra hörnet på sidan.

   Med resursväljaren kan du söka efter resurser genom att skriva ett nyckelord och trycka på **[!UICONTROL Return]**. Du kan också använda filter för att förfina sökresultatet. Du kan filtrera efter sökväg, samling, filtyp och tagg. Markera filtret och tryck sedan på ikonen **[!UICONTROL Filter]** i verktygsfältet. Ändra vyn genom att trycka på ikonen **[!UICONTROL View]** och välja **[!UICONTROL Column View]**, **[!UICONTROL Card View]** eller **[!UICONTROL List View]**.

   Se [Arbeta med väljare.](working-with-selectors.md)

   ![chlimage_1-342](assets/chlimage_1-342.png)

1. När du lägger till resurser i uppsättningen läggs de automatiskt till i alfanumerisk ordning. Du kan sortera om eller sortera resurser manuellt när du har lagt till dem.

   Om det behövs kan du dra ikonen **[!UICONTROL Reorder]** för en resurs till höger om resursens filnamn för att ordna om bilderna uppåt eller nedåt i uppsättningslistan.

   ![spin_set_assets](assets/spin_set_assets.png)

   Om du vill ändra en miniatyrbild eller färgruta trycker du på ikonen **[!UICONTROL Thumbnail]** bredvid bilden och navigerar till miniatyrbilden eller färgrutan som du vill använda. När du är klar trycker du **[!UICONTROL Save]** på alla bilder.

1. (Valfritt) Gör något av följande:

   * Om du vill ta bort en bild markerar du bilden och trycker sedan på **[!UICONTROL Delete Asset]**.
   * Om du vill använda en förinställning trycker du på **[!UICONTROL Preset]** längst upp till höger på sidan och väljer sedan en förinställning som ska användas på alla resurser samtidigt.

1. Tryck på **[!UICONTROL Save]**. Den nya bilduppsättningen visas i den mapp du skapade den i.

## Visa bilduppsättningar {#viewing-image-sets}

Du kan skapa bilduppsättningar antingen i användargränssnittet eller automatiskt med [gruppuppsättningsförinställningar](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

**Viktigt**  - Batchuppsättningar skapas av IPS  [Image Production System ] som en del av tillgångsintag och är endast tillgängliga i Dynamic Media - Scene7-läge.)

Uppsättningar som skapats med gruppuppsättningsförinställningar visas *inte* i användargränssnittet. Du kan visa uppsättningarna på tre olika sätt. (Dessa metoder är tillgängliga även om du har skapat bilduppsättningarna i användargränssnittet).

* När egenskaperna för en enskild resurs öppnas. Egenskaperna anger vad som ställer in den valda resursen som medlem av (under **[!UICONTROL Member of Sets]**). Tryck på uppsättningens namn för att visa hela uppsättningen.

   ![chlimage_1-343](assets/chlimage_1-343.png)

* Från en medlemsbild i en uppsättning. Välj menyn **[!UICONTROL Sets]** om du vill visa de uppsättningar som resursen är medlem i.

   ![chlimage_1-344](assets/chlimage_1-344.png)

* I sökningen kan du välja **[!UICONTROL Filters]**, sedan expandera **[!UICONTROL Dynamic Media]** och välja **[!UICONTROL Sets]**.

   Sökningen returnerar matchande uppsättningar som skapats manuellt i användargränssnittet eller automatiskt skapats med gruppuppsättningsförinställningar. För automatiserade uppsättningar utförs sökfrågan med sökvillkoren &quot;Börjar med&quot;, som skiljer sig från AEM sökning som baseras på sökvillkoren &quot;Innehåller&quot;. Det enda sättet att söka efter automatiska uppsättningar är att ställa in filtret på **[!UICONTROL Sets]**.

   ![chlimage_1-345](assets/chlimage_1-345.png)

>[!NOTE]
>
>Du kan visa uppsättningar via användargränssnittet enligt beskrivningen i [Redigera bilduppsättningar](#editing-image-sets).

## Redigera bilduppsättningar {#editing-image-sets}

Du kan utföra en mängd redigeringsåtgärder på bilduppsättningar, till exempel:

* Lägg till bilder i bilduppsättningen.
* Ändra ordning på bilderna i bilduppsättningen.
* Ta bort resurser i bilduppsättningen.
* Använd förinställningar för visningsprogram.
* Ta bort bilduppsättningen.

**Så här redigerar du bilduppsättningar**:

1. Gör något av följande:

   * Håll pekaren över en bilduppsättningsresurs och tryck sedan på **[!UICONTROL Edit]** (pennikon).
   * Håll pekaren över en bilduppsättningsresurs, tryck på **[!UICONTROL Select]** (bockmarkeringsikon) och tryck sedan på **[!UICONTROL Edit]** i verktygsfältet.
   * Tryck på en bilduppsättningsresurs och tryck sedan på **[!UICONTROL Edit]** (pennikon) i verktygsfältet.

1. Gör något av följande om du vill redigera bilderna i bilduppsättningen:

   * Om du vill ändra ordning på resurser drar du en bild till en ny plats (markera sorteringsikonen för att flytta objekt).
   * Om du vill sortera objekt i stigande eller fallande ordning trycker du på kolumnrubriken.
   * Om du vill lägga till en resurs eller uppdatera en befintlig resurs trycker du på **[!UICONTROL Add Asset]**. Navigera till en resurs, markera den och tryck sedan på **[!UICONTROL Select]** nära det övre högra hörnet på sidan.

   >[!NOTE]
   >Om du tar bort den bild som AEM använder som miniatyrbild genom att ersätta den med en annan bild, visas fortfarande originalresursen.

   * Om du vill ta bort en resurs markerar du den och trycker sedan på **[!UICONTROL Delete Asset]**.
   * Om du vill använda en förinställning trycker du på **[!UICONTROL Preset]** längst upp till höger på sidan och väljer sedan en visningsförinställning.
   * Om du vill lägga till eller ändra en miniatyrbild markerar du miniatyrbildikonen bredvid resursens högra sida. Navigera till den nya miniatyrbilden eller färgruteresursen, markera den och tryck sedan på **[!UICONTROL Select]**.
   * Om du vill ta bort en hel bilduppsättning går du till bilduppsättningen, markerar den och trycker på **[!UICONTROL Delete]**.

   >[!NOTE]
   >
   >Du kan redigera bilderna i en bilduppsättning genom att navigera till uppsättningen, trycka på **[!UICONTROL Set Members]** i den vänstra listen och sedan på ikonen **[!UICONTROL Pencil]** för en enskild resurs för att öppna redigeringsfönstret.

1. Tryck på **[!UICONTROL Save]** när du är klar med redigeringen.

## Förhandsvisa bilduppsättningar {#previewing-image-sets}

Se [Förhandsgranska resurser](previewing-assets.md).

## Publicerar bilduppsättningar {#publishing-image-sets}

Se [Publicera resurser](publishing-dynamicmedia-assets.md).
