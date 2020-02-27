---
title: Blandade medieuppsättningar
seo-title: Blandade medieuppsättningar
description: Lär dig hur du arbetar med blandade medieuppsättningar i dynamiska medier
seo-description: Lär dig hur du arbetar med blandade medieuppsättningar i dynamiska medier
uuid: e37fa648-74e2-42e3-8611-8509c92ec00d
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 599c316e-b6a7-4a28-bc4b-75d48409bde0
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# Blandade medieuppsättningar {#mixed-media-sets}

Med blandade medieuppsättningar kan du kombinera bilder, bilduppsättningar, snurruppsättningar och videoklipp i en presentation.

Blandade medieuppsättningar definieras av en banderoll med ordet **[!UICONTROL MixedMediaSet]**. Om den blandade medieuppsättningen dessutom publiceras visas det publiceringsdatum som anges av **[!UICONTROL World]** -ikonen på banderollen tillsammans med det senaste ändringsdatumet, vilket anges av **[!UICONTROL pennikonen]** .

![chlimage_1-348](assets/chlimage_1-348.png)

>[!NOTE]
>
>Mer information om användargränssnittet Resurser finns i [Hantera resurser med Touch-gränssnittet](managing-assets-touch-ui.md).

## Snabbstart: Blandade medieuppsättningar {#quick-start-mixed-media-sets}

Följ de här stegen för att komma igång snabbt med blandade medieuppsättningar:

1. [Överför dina resurser](#uploading-assets).

   Börja med att ladda upp bilder och videoklipp för dina blandade medieuppsättningar. Om det behövs kan du skapa [bilduppsättningar](image-sets.md) och [snurruppsättningar](spin-sets.md). Eftersom användare kan zooma in bilder i visningsprogrammet för den blandade medieuppsättningen bör du ta hänsyn till zoomningen när du väljer bilder. Se till att bilderna har minst 2 000 pixlar i den största dimensionen.

1. [Skapa blandade medieuppsättningar.](#creating-mixed-media-sets)

   Om du vill skapa en blandad medieuppsättning går du till sidan **[!UICONTROL Resurser]** och trycker på **[!UICONTROL Skapa > Blandad medieuppsättning]** och ger uppsättningen ett namn. Välj resurserna och välj den ordning som bilderna ska visas i.

   See [Working with Selectors.](working-with-selectors.md)

1. Ställ in förinställningar [för](managing-viewer-presets.md)blandad Media Viewer efter behov.

   Administratörer kan skapa eller ändra visningsförinställningar för blandad medieuppsättning. Om du vill visa de blandade medierna med en visningsförinställning väljer du den blandade medieuppsättningen och väljer **[!UICONTROL Visare]** i den vänstra listrutan.

   Se **[!UICONTROL Verktyg > Resurser > Visningsförinställningar]** för att skapa eller redigera visningsprogramförinställningar.

   Se [Lägga till och redigera visningsförinställningar.](managing-viewer-presets.md)

1. [Förhandsgranska blandade medieuppsättningar.](#previewing-mixed-media-sets)

   Markera den blandade medieuppsättningen och du kan förhandsgranska den. Klicka på miniatyrbildikonerna för att undersöka den blandade medieuppsättningen i det valda visningsprogrammet. Du kan välja olika visningsprogram på menyn **[!UICONTROL Visare]** , som finns i listrutan till vänster.

1. [Publicera blandade medieuppsättningar.](#publishing-mixed-media-sets)

   När du publicerar en blandad medieuppsättning aktiveras URL-adressen och strängen Embed. Dessutom måste du [publicera visningsförinställningen](managing-viewer-presets.md#publishing-viewer-presets).

1. [Länka URL:er till webbprogrammet](linking-urls-to-yourwebapplication.md) eller [bädda in video- eller bildvisningsprogrammet](embed-code.md).

   AEM Resurser skapar URL-anrop för blandade medieuppsättningar och aktiverar dem när du har publicerat de blandade medieuppsättningarna. Du kan kopiera dessa URL:er när du förhandsgranskar resurser. Du kan även bädda in dem på din webbplats.

   Välj den blandade medieuppsättningen och välj sedan **[!UICONTROL Visare]** i den vänstra listrutan.

   Se [Länka en uppsättning med blandade media till en webbsida](linking-urls-to-yourwebapplication.md) och [Bädda in video- eller bildvisningsprogrammet](embed-code.md).

Om du behöver kan du redigera [blandade medieuppsättningar](#editing-mixed-media-sets). Dessutom kan du visa och ändra egenskaperna [för](managing-assets-touch-ui.md#editing-properties)den blandade medieuppsättningen.

>[!NOTE]
>
>Om du har problem med att skapa uppsättningar kan du läsa [Felsökning av dynamiska media - Scene7-läge](troubleshoot-dms7.md).

## Överför resurser {#uploading-assets}

Börja med att ladda upp bilder och videoklipp för dina blandade medieuppsättningar. Eftersom användare kan zooma in bilder i visningsprogrammet för den blandade medieuppsättningen måste du ta hänsyn till zoomningen när du väljer bilder. Se till att bilderna har minst 2 000 pixlar i den största dimensionen.

Om du dessutom vill lägga till snurrsuppsättningar eller bilduppsättningar i den blandade medieuppsättningen skapar du även dem.

## Skapa blandade medieuppsättningar {#creating-mixed-media-sets}

Du kan lägga till bilder, bilduppsättningar, snurruppsättningar och videoklipp i din uppsättning med blandade media. Se till att dina filer, bilduppsättningar och snurruppsättningar är klara att publiceras innan du lägger till dem i den blandade medieuppsättningen.

När du lägger till resurser i uppsättningen läggs de automatiskt till i alfanumerisk ordning. Du kan ändra ordning på eller sortera resurser manuellt när de har lagts till.

**Så här skapar du en blandad medieuppsättning**:

1. Navigera till den plats där du vill skapa en blandad medieuppsättning i Resurser, klicka på **Skapa** och välj **[!UICONTROL Blandad medieuppsättning]**. Du kan också skapa uppsättningen inifrån en mapp som innehåller dina resurser.

   ![chlimage_1-349](assets/chlimage_1-349.png)

1. På sidan **[!UICONTROL Redigerare]** för blandad medieuppsättning anger du ett namn för den blandade medieuppsättningen under **[!UICONTROL Titel]**. Namnet visas i banderollen över den blandade medieuppsättningen. Du kan också ange en beskrivning.

   ![chlimage_1-350](assets/chlimage_1-350.png)

   >[!NOTE]
   >
   >När du skapar den blandade medieuppsättningen kan du ändra miniatyrbilden för den blandade medieuppsättningen eller tillåta att AEM väljer miniatyrbilden automatiskt baserat på resurserna i den blandade medieuppsättningen. Om du vill välja en miniatyrbild klickar du på **[!UICONTROL Ändra miniatyrbild]** och väljer en bild (du kan navigera till andra mappar för att söka efter bilder också). Om du har valt en miniatyrbild och sedan vill att AEM ska generera en från den blandade medieuppsättningen väljer du **[!UICONTROL Växla till automatisk miniatyrbild]**.

1. Tryck på **[!UICONTROL resursväljaren]** för att välja resurser som du vill inkludera i din uppsättning med blandade media. Markera dem och tryck på **[!UICONTROL Välj]**.

   Med **[!UICONTROL resursväljaren]** kan du söka efter resurser genom att skriva ett nyckelord och trycka på **[!UICONTROL Retur]**. Du kan också använda filter för att förfina sökresultaten. Du kan filtrera efter sökväg, samling, filtyp och tagg. Markera filtret och tryck sedan på **[!UICONTROL Filtrera]** -ikonen i verktygsfältet. Ändra vyn genom att markera ikonen Visa och välja **[!UICONTROL Visa]**, **[!UICONTROL Kolumn]** eller **[!UICONTROL Kortvy]** .

   See [Working with Selectors](working-with-selectors.md).

   ![chlimage_1-351](assets/chlimage_1-351.png)

1. Sortera om resurserna genom att dra dem uppåt eller nedåt i listan (måste markera ikonen för att ordna om), om det behövs.

   ![chlimage_1-352](assets/chlimage_1-352.png)

   Om du vill lägga till miniatyrbilder klickar du på **[!UICONTROL +]** -ikonen bredvid bilden och navigerar till miniatyrbilden som du vill använda. När du är klar med att välja alla miniatyrbilder trycker du på **[!UICONTROL Spara]**.

   >[!NOTE]
   >
   >Om du vill lägga till resurser trycker du på **[!UICONTROL Lägg till resurs]**.

1. Om du vill ta bort en resurs markerar du motsvarande kryssruta och trycker på **[!UICONTROL Ta bort resurs]**.
1. Om du vill använda en förinställning trycker du på **[!UICONTROL Förinställning]** i det övre högra hörnet och väljer en förinställning som ska användas för resurserna.
1. Click **[!UICONTROL Save]**. Den nya blandade medieuppsättningen visas i den mapp du skapade den i.

## Redigera blandade medieuppsättningar {#editing-mixed-media-sets}

Du kan utföra en mängd redigeringsåtgärder för resurser i blandade medieuppsättningar direkt i användargränssnittet, [precis som för andra resurser i Resurser](managing-assets-touch-ui.md). Du kan även utföra följande åtgärder i Blandade medieuppsättningar:

* Lägg till resurser i den blandade medieuppsättningen.
* Ändra ordning på resurser i den blandade medieuppsättningen.
* Ta bort resurser i den blandade medieuppsättningen.
* Använd förinställningar för visningsprogram.
* Ändra standardminiatyrbilden.

**Så här redigerar du blandade medieuppsättningar**:

1. Gör något av följande:

   * Håll pekaren över en resurs i en blandad medieuppsättning och tryck sedan på **[!UICONTROL Redigera]** (pennikon).
   * Håll muspekaren över en resurs i en blandad medieuppsättning, tryck på **[!UICONTROL Markera]** (bockmarkeringsikon) och sedan på **[!UICONTROL Redigera]** i verktygsfältet.
   * Tryck på en resurs i en blandad medieuppsättning och tryck sedan på **[!UICONTROL Redigera]** (pennikon) i verktygsfältet.

1. Gör något av följande i redigeraren för den blandade medieuppsättningen:

   * Om du vill ordna om resurser trycker du på **[!UICONTROL Resurser]** (bildikon) i den vänstra panelen och drar en resurs till en ny plats.
   * Om du vill lägga till resurser trycker du på **[!UICONTROL Lägg till resurs]** i verktygsfältet. Navigera till resurserna. För varje resurs som du vill lägga till håller du pekaren över resursens bild (inte resursens namn) och trycker sedan på bockmarkeringsikonen. Tryck på **[!UICONTROL Välj]** i det övre högra hörnet.
   * Om du vill ta bort en resurs trycker du på **[!UICONTROL Resurser]** (bildikon) i den vänstra panelen och markerar sedan resursen. Tryck på **[!UICONTROL Ta bort resurs]** i verktygsfältet.
   * Om du vill sortera resurser efter namn i stigande eller fallande ordning trycker du på **[!UICONTROL Resurser]** (bildikon) i den vänstra panelen. Till höger om rubriken **[!UICONTROL Resurser]** : tryck på cirkonerna uppåt eller nedåt.
   >[!NOTE]
   >
   >* Om du vill ta bort en hel uppsättning med blandade media går du till **[!UICONTROL kortvyn]** eller **[!UICONTROL kolumnvyn]** i valfritt visningsläge. Håll pekaren över resursen och tryck på bockmarkeringsikonen för att markera den. Tryck på **[!UICONTROL Backsteg]** på tangentbordet eller tryck på **[!UICONTROL Mer]** (tre punkter) i verktygsfältet och tryck sedan på **[!UICONTROL Delete]**.
   >* Du kan redigera resurserna i en blandad medieuppsättning genom att gå till uppsättningen, trycka på **[!UICONTROL Ange medlemmar]** i den vänstra listen och sedan trycka på ikonen **[!UICONTROL Penna]** på en enskild resurs för att öppna redigeringsfönstret.


1. Tryck på **[!UICONTROL Save** när du är klar med redigeringen.

   >[!NOTE]
   >
   >* Om du vill redigera resurserna i en uppsättning med blandade media navigerar du till den blandade medieuppsättningen. Tryck på (markera inte) uppsättningen för att öppna den på sidan AEM **[!UICONTROL Set Preview]** . Tryck på nedåtpilen i den vänstra listen för att öppna listrutan och tryck sedan på **[!UICONTROL Ange medlemmar]**. Håll markören över en resurs på sidan **[!UICONTROL Ange medlemmar]** och tryck sedan på **[!UICONTROL Redigera]** (pennikonen) för att öppna redigeringssidan.
   >* Om du vill ta bort en hel uppsättning med blandade media - Från valfritt visningsläge (till exempel **[!UICONTROL kortvyn]** eller **[!UICONTROL kolumnvyn]** ) går du till den blandade medieuppsättningen. Håll muspekaren över uppsättningen och tryck sedan på **[!UICONTROL Välj]** (bockmarkeringsikon). Tryck på **[!UICONTROL Backsteg]** på tangentbordet eller tryck på **[!UICONTROL Mer]** (rad om tre punkter) och sedan på **[!UICONTROL Delete]**.


## Förhandsgranska blandade medieuppsättningar {#previewing-mixed-media-sets}

Mer information om hur du förhandsgranskar blandade medieuppsättningar finns i [Förhandsgranska resurser](previewing-assets.md) .

## Publicera blandade medieuppsättningar {#publishing-mixed-media-sets}

Mer information om hur du publicerar blandade medieuppsättningar finns i [Publicera resurser](publishing-dynamicmedia-assets.md) .

>[!NOTE]
>
>Om det blandade mediet inte hamnar helt i leveranstjänsten första gången du publicerar den, kan du behöva publicera den blandade medieuppsättningen en andra gång.

