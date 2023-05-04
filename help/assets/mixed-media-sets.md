---
title: Blandade medieuppsättningar
description: Lär dig hur du arbetar med blandade medieuppsättningar (bilder, bilduppsättningar, snurreuppsättningar och videofilmer) i Dynamic Media.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: 252c1a50-17ac-4412-88d6-49bb6850658d
feature: Mixed Media Sets
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1424'
ht-degree: 17%

---

# Blandade medieuppsättningar {#mixed-media-sets}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med blandade medieuppsättningar kan du kombinera bilder, bilduppsättningar, snurruppsättningar och videoklipp i en presentation.

Blandade medieuppsättningar definieras av en banderoll med ordet **[!UICONTROL MixedMediaSet]**. Om uppsättningen med blandade medier publiceras visas dessutom det publiceringsdatum som anges av ikonen **[!UICONTROL World]** på banderollen tillsammans med det senaste ändringsdatumet, som anges av ikonen **[!UICONTROL Pencil]**.

![chlimage_1-348](assets/chlimage_1-348.png)

>[!NOTE]
>
>Mer information om gränssnittet Resurser finns i [Hantera resurser med Touch-gränssnittet](managing-assets-touch-ui.md).

## Snabbstart: Blandade medieuppsättningar {#quick-start-mixed-media-sets}

Följ de här stegen för att komma igång snabbt med blandade medieuppsättningar:

1. [Överför dina resurser](#uploading-assets).

   Börja med att ladda upp bilder och videoklipp för uppsättningarna med blandade medier. Om det behövs kan du skapa [bilduppsättningar](image-sets.md) och [rotationsuppsättningar](spin-sets.md). Eftersom användare kan zooma in bilder i visningsprogrammet för uppsättningen med blandade medier bör du ta hänsyn till zoomningen när du väljer bilder. Se till att bilderna har minst 2 000 pixlar i den största dimensionen.

1. [Skapa blandade medieuppsättningar.](#creating-mixed-media-sets)

   Om du vill skapa en blandad medieuppsättning går du till **[!UICONTROL Assets]** sida, tryck **[!UICONTROL Create > Mixed Media Set]** och namnge sedan uppsättningen. Välj resurserna och välj den ordning som bilderna ska visas i.

   Se [Arbeta med väljare.](working-with-selectors.md)

1. Konfigurera [Förinställningar för blandad Media Viewer](managing-viewer-presets.md), efter behov.

   Administratörer kan skapa eller ändra visningsförinställningar för blandade medieuppsättningar. Om du vill visa de blandade medierna med en visningsförinställning väljer du uppsättningen med blandade medier och väljer sedan **[!UICONTROL Viewers]** i listrutan till vänster.

   Se **[!UICONTROL Tools > Assets > Viewer Presets]** om du vill skapa eller redigera förinställningar för visningsprogram.

   Se [Lägga till och redigera visningsförinställningar.](managing-viewer-presets.md)

1. [Förhandsgranska blandade medieuppsättningar.](#previewing-mixed-media-sets)

   Markera den blandade medieuppsättningen och du kan förhandsgranska den. Klicka på miniatyrbildikonerna för att undersöka den blandade medieuppsättningen i det valda visningsprogrammet. Du kan välja olika visningsprogram från **[!UICONTROL Viewers]** som finns på den vänstra menyn.

1. [Publicera blandade medieuppsättningar.](#publishing-mixed-media-sets)

   När du publicerar en blandad medieuppsättning aktiveras URL-adressen och strängen Embed. Dessutom måste du [publicera visningsförinställningen](managing-viewer-presets.md#publishing-viewer-presets).

1. [Länka URL:er till ditt webbprogram](linking-urls-to-yourwebapplication.md) eller [Bädda in video- eller bildvisningsprogrammet](embed-code.md).

   AEM Assets skapar URL-anrop för blandade medieuppsättningar och aktiverar dem när du har publicerat de blandade medieuppsättningarna. Du kan kopiera dessa URL:er när du förhandsgranskar resurser. Du kan även bädda in dem på din webbplats.

   Välj den blandade medieuppsättningen och välj sedan i listrutan till vänster **[!UICONTROL Viewers]**.

   Se [Länka en uppsättning med blandade medier till en webbsida](linking-urls-to-yourwebapplication.md) och [Bädda in video- eller bildvisningsprogrammet](embed-code.md).

Om du behöver kan du redigera [Blandade medieuppsättningar](#editing-mixed-media-sets). Dessutom kan du visa och ändra [Egenskaper för uppsättning med blandade media](managing-assets-touch-ui.md#editing-properties).

>[!NOTE]
>
>Om du har problem med att skapa uppsättningar finns mer information i [Felsökning av Dynamic Media - Scene7-läge](troubleshoot-dms7.md).

## Överför resurser {#uploading-assets}

Börja med att ladda upp bilder och videoklipp för uppsättningarna med blandade medier. Eftersom användare kan zooma in bilder i visningsprogrammet för den blandade medieuppsättningen måste du ta hänsyn till zoomningen när du väljer bilder. Se till att bilderna har minst 2 000 pixlar i den största dimensionen.

Om du dessutom vill lägga till snurrsuppsättningar eller bilduppsättningar i den blandade medieuppsättningen skapar du även dem.

## Skapa blandade medieuppsättningar {#creating-mixed-media-sets}

Du kan lägga till bilder, bilduppsättningar, snurruppsättningar och videoklipp i din uppsättning med blandade media. Se till att dina filer, bilduppsättningar och snurruppsättningar är klara att publiceras innan du lägger till dem i den blandade medieuppsättningen.

När du lägger till resurser i uppsättningen läggs de automatiskt till i alfanumerisk ordning. Du kan ändra ordning på eller sortera resurser manuellt när de har lagts till.

**Skapa en blandad medieuppsättning**:

1. Navigera till den plats där du vill skapa en blandad medieuppsättning i Resurser och klicka på **Skapa** och markera **[!UICONTROL Mixed Media Set]**. Du kan också skapa uppsättningen inifrån en mapp som innehåller resurserna.

   ![chlimage_1-349](assets/chlimage_1-349.png)

1. I **[!UICONTROL Mixed Media Set Editor]** sida, in **[!UICONTROL Title]** anger du ett namn för den blandade medieuppsättningen. Namnet visas i banderollen över den blandade medieuppsättningen. Du kan också ange en beskrivning.

   ![chlimage_1-350](assets/chlimage_1-350.png)

   >[!NOTE]
   >
   >När du skapar den blandade medieuppsättningen kan du ändra miniatyrbilden för den blandade medieuppsättningen eller låta AEM välja miniatyrbilden automatiskt baserat på resurserna i den blandade medieuppsättningen. Om du vill välja en miniatyrbild klickar du på **[!UICONTROL Change thumbnail]** och markera en bild (du kan navigera till andra mappar för att hitta bilder också). Om du har valt en miniatyrbild och sedan vill AEM att du ska generera en från den blandade medieuppsättningen väljer du **[!UICONTROL Switch to Automatic thumbnail]**.

1. Tryck på **[!UICONTROL Asset Selector]** för att välja resurser som du vill inkludera i din uppsättning med blandade media. Markera dem och tryck **[!UICONTROL Select]**.

   Med **[!UICONTROL Asset Selector]** kan du söka efter resurser genom att skriva ett nyckelord och trycka på **[!UICONTROL Return]**. Du kan också använda filter för att förfina sökresultatet. Du kan filtrera efter sökväg, samling, filtyp och tagg. Markera filtret och tryck sedan på ikonen **[!UICONTROL Filter]** i verktygsfältet. Ändra vyn genom att markera ikonen Visa och välja **[!UICONTROL List]**, **[!UICONTROL Column]**, eller **[!UICONTROL Card]** vy.

   Se [Arbeta med väljare](working-with-selectors.md).

   ![chlimage_1-351](assets/chlimage_1-351.png)

1. Sortera om resurserna genom att dra dem uppåt eller nedåt i listan (måste markera ikonen för att ordna om), om det behövs.

   ![chlimage_1-352](assets/chlimage_1-352.png)

   Om du vill lägga till miniatyrbilder klickar du på **[!UICONTROL +]** -ikonen bredvid bilden och navigera till miniatyrbilden som du vill använda. När du är klar med markeringen av alla miniatyrbilder trycker du **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Om du vill lägga till resurser trycker du på **[!UICONTROL Add Asset]**.

1. Om du vill ta bort en resurs markerar du motsvarande kryssruta och trycker på **[!UICONTROL Delete Asset]**.
1. Om du vill använda en förinställning trycker du **[!UICONTROL Preset]** i det övre högra hörnet och välj en förinställning som ska användas för resurserna.
1. Klicka på **[!UICONTROL Save]**. Den nya blandade medieuppsättningen visas i den mapp du skapade den i.

## Redigera blandade medieuppsättningar {#editing-mixed-media-sets}

Du kan utföra en mängd redigeringsåtgärder för resurser i blandade medieuppsättningar direkt i användargränssnittet [som alla resurser i Assets](managing-assets-touch-ui.md). Du kan även utföra följande åtgärder i Blandade medieuppsättningar:

* Lägg till resurser i den blandade medieuppsättningen.
* Ändra ordning på resurser i den blandade medieuppsättningen.
* Ta bort resurser i den blandade medieuppsättningen.
* Använd förinställningar för visningsprogram.
* Ändra standardminiatyrbilden.

**Redigera blandade medieuppsättningar**:

1. Gör något av följande:

   * Håll muspekaren över en resurs i en blandad medieuppsättning och tryck sedan **[!UICONTROL Edit]** (pennikon).
   * Hovra över en resurs i en blandad medieuppsättning, tryck **[!UICONTROL Select]** (bockmarkeringsikon) och sedan trycka **[!UICONTROL Edit]** i verktygsfältet.
   * Tryck på en resurs för en blandad medieuppsättning och tryck sedan på **[!UICONTROL Edit]** (pennikon) i verktygsfältet.

1. Gör något av följande i redigeraren för den blandade medieuppsättningen:

   * Sortera om resurser - Tryck på i den vänstra panelen **[!UICONTROL Assets]** (bildikon) drar du en resurs till en ny plats.
   * Om du vill lägga till resurser trycker du på **[!UICONTROL Add Asset]**. Navigera till resurserna. För varje resurs som du vill lägga till håller du pekaren över resursens bild (inte resursens namn) och trycker sedan på bockmarkeringsikonen. Tryck på i det övre högra hörnet **[!UICONTROL Select]**.
   * Ta bort en resurs genom att trycka på **[!UICONTROL Assets]** (bildikon) och välj sedan resursen. Tryck på i verktygsfältet **[!UICONTROL Delete Asset]**.
   * Om du vill sortera resurser efter namn i stigande eller fallande ordning trycker du på **[!UICONTROL Assets]** (bildikon). Till höger om **[!UICONTROL Assets]** om du vill trycka på ikonerna för cirkumflex uppåt eller nedåt.

   >[!NOTE]
   >
   >* Om du vill ta bort en hel uppsättning med blandade media från valfritt visningsläge (till exempel **[!UICONTROL Card]** visa eller **[!UICONTROL Column]** vy) navigera till den blandade medieuppsättningen. Håll pekaren över resursen och tryck på bocken för att markera den. Tryck **[!UICONTROL Backspace]** på tangentbordet, eller tryck **[!UICONTROL More]** (tre punkter) i verktygsfältet och tryck sedan på **[!UICONTROL Delete]**.
   >* Du kan redigera resurserna i en uppsättning med blandade media genom att gå till uppsättningen och trycka på **[!UICONTROL Set Members]** i den vänstra listen och sedan trycka på **[!UICONTROL Pencil]** på en enskild resurs för att öppna redigeringsfönstret.


1. Tryck **[!UICONTROL Save]** när du är klar med redigeringen.

   >[!NOTE]
   >
   >* Om du vill redigera resurserna i en uppsättning med blandade medier navigerar du till den blandade medieuppsättningen. Tryck (markera inte) på uppsättningen för att öppna den i AEM **[!UICONTROL Set Preview]** sida. Tryck på nedåtpilen i den vänstra listen för att öppna listrutan och tryck sedan på **[!UICONTROL Set Members]**. I **[!UICONTROL Set Members]** sida, hovra över en resurs och sedan trycka **[!UICONTROL Edit]** (pennikon) för att öppna redigeringssidan.
   >* Så här tar du bort en hel uppsättning med blandade media - från valfritt visningsläge (t.ex. **[!UICONTROL Card]** visa eller **[!UICONTROL Column]** navigera till den blandade medieuppsättningen. Hovra på scenen och tryck sedan **[!UICONTROL Select]** (bockmarkeringsikon). Tryck **[!UICONTROL Backspace]** på tangentbordet, eller tryck **[!UICONTROL More]** (rad om tre punkter), och tryck sedan **[!UICONTROL Delete]**.


## Förhandsgranska blandade medieuppsättningar {#previewing-mixed-media-sets}

Se [Förhandsgranska resurser](previewing-assets.md) om du vill ha mer information om hur du förhandsvisar blandade medieuppsättningar.

## Publicera blandade medieuppsättningar {#publishing-mixed-media-sets}

Se [Publicera resurser](publishing-dynamicmedia-assets.md) om du vill ha mer information om hur du publicerar blandade medieuppsättningar.

>[!NOTE]
>
>Om det blandade mediet inte hamnar helt i leveranstjänsten första gången du publicerar den, kan du behöva publicera den blandade medieuppsättningen en andra gång.
