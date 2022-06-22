---
title: Snurrande uppsättningar
description: Lär dig hur du arbetar med snurruppsättningar i Dynamic Media. Med en snurra uppsättning kan du simulera hur det ser ut i verkligheten när du vrider ett objekt för att undersöka det ur en viss vinkel.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: 47cb6d40-a5c4-4f6a-9794-bd2eddfaa7d0
feature: Spin Sets
role: User
source-git-commit: 5d4d0c86a9d9e3eaaaca1e795260e8e49567ea73
workflow-type: tm+mt
source-wordcount: '1840'
ht-degree: 7%

---

# Snurrande uppsättningar {#spin-sets}

Med en snurra uppsättning kan du simulera hur det ser ut när du vrider ett objekt för att undersöka det. Med snurra uppsättningar kan du visa objekt från vilken vinkel som helst och få fram de viktigaste visuella detaljerna från vilken vinkel som helst.

Med en snurra uppsättning simuleras en 360-graders visningsupplevelse. Dynamic Media erbjuder snurra uppsättningar med en axel där tittarna kan rotera ett objekt. Dessutom kan man zooma och panorera med några enkla musklick. På så sätt kan användare undersöka ett objekt närmare från en viss betraktningsvinkel.

Snurra uppsättningar anges av en banderoll med ordet **[!UICONTROL SPINSET]**. Om rotationsuppsättningen dessutom är publicerad är det publiceringsdatum som anges av **[!UICONTROL World]** ikonen finns på banderollen tillsammans med det senaste ändringsdatumet, vilket anges av **[!UICONTROL Pencil]** visas.

![chlimage_1-380](assets/chlimage_1-380.png)

>[!NOTE]
>
>Mer information om gränssnittet Resurser finns i [Hantera resurser med Touch-gränssnittet](managing-assets-touch-ui.md).

När du skapar en snurrsuppsättning rekommenderar Adobe följande bästa praxis och tillämpar följande gräns:

| Begränsningstyp | Bästa praxis | Implementerad gräns |
| --- | --- | --- |
| Maximalt antal rader/kolumner per 2D-uppsättning | 12-18 bilder per uppsättning | 1000 |

Se även [Dynamic Media begränsningar](/help/assets/limitations.md).

## Snabbstart: Snurra uppsättningar {#quick-start-spin-sets}

Så här kommer du igång snabbt med Spin Sets:

1. [Ladda upp bilderna för flera vyer.](#uploading-assets-for-spin-sets)

   Du behöver minst 8-12 tagningar av ett objekt för en endimensionell snurra och 16-24 för en tvådimensionell snurra uppsättning. Fotografierna måste tas med jämna mellanrum för att ge intryck av att objektet roteras och vändas. Om en endimensionell snurra t.ex. innehåller 12 tagningar roterar du objektet 30 grader (360/12) för varje tagning.

1. [Skapa snurruppsättningar.](#creating-spin-sets)

   Om du vill skapa en snurruppsättning väljer du **[!UICONTROL Create > Spin Set]** och namnge uppsättningen, välj resurserna och sortera sedan bilderna i den ordning de visas.

   Se [Arbeta med väljare](working-with-selectors.md).

   >[!NOTE]
   >
   >Du kan också skapa snurruppsättningar automatiskt genom att [gruppuppsättningsförinställningar](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).
   >
   >*Batchuppsättningar skapas av IPS (Image Production System) som en del av tillgångsintag och är endast tillgängliga i Dynamic Media - Scene7-läge*.

1. Konfigurera [Snurra inställningar för visningsprogram](managing-viewer-presets.md), efter behov.

   Administratörer kan skapa eller ändra förinställningar för Spin Set Viewer. Om du vill visa din snurruppsättning med en visningsförinställning väljer du snurra uppsättning och väljer i den vänstra rullgardinsmenyn **[!UICONTROL Viewers]**.

   Se **[!UICONTROL Tools > Assets > Viewer Presets]** om du vill skapa eller redigera förinställningar för visningsprogram.

   Se [Lägga till och redigera visningsförinställningar.](managing-viewer-presets.md)

1. [Visa snurruppsättningar](#viewing-spin-sets).

   Du kan visa och komma åt uppsättningar som skapats med hjälp av gruppuppsättningsförinställningar på tre olika sätt. (Uppsättningar som skapats med gruppuppsättningsförinställningar, gör *not* visas i användargränssnittet.)

1. [Förhandsgranska snurra uppsättningar.](previewing-assets.md)

   Markera rotationsuppsättningen så kan du förhandsgranska den. Rotera snurrsuppsättningen. Du kan välja olika visningsprogram från **[!UICONTROL Viewers]** som finns på den vänstra menyn.

1. [Publicera snurruppsättningar.](publishing-dynamicmedia-assets.md)

   När du publicerar en snurrsuppsättning aktiveras den ordning i vilken bilderna visas i en snurra. Se till att ordna dem så att snurret blir en jämn 360-gradersvy.**[!UICONTROL URL]** och **[!UICONTROL Embed]** sträng. Dessutom måste du [publicera visningsförinställningen](managing-viewer-presets.md).

1. [Länka URL:er till ditt webbprogram](linking-urls-to-yourwebapplication.md) eller [Bädda in video- eller bildvisningsprogrammet](embed-code.md).

   AEM Assets skapar URL-anrop för Spin Sets och aktiverar dem när du har publicerat Spin Sets. Du kan kopiera dessa URL:er när du förhandsgranskar resurser. Du kan även bädda in dem på din webbplats.

   Markera rotationsuppsättningen och välj sedan **[!UICONTROL Viewers]** i listrutan till vänster.

   Läs [Länka en rotationsuppsättning till en webbsida](linking-urls-to-yourwebapplication.md) och [Bädda in video- eller bildvisningsprogrammet](embed-code.md).

Om du behöver det kan du [redigera snurra uppsättningar](#editing-spin-sets). Dessutom kan du visa och redigera [Snurra uppsättningsegenskaper](managing-assets-touch-ui.md#editing-properties).

## Överför resurser för snurpuppsättningar {#uploading-assets-for-spin-sets}

Du behöver minst 8-12 tagningar av ett objekt för en endimensionell snurra och 16-24 för en tvådimensionell snurra uppsättning. Fotografierna måste tas med jämna mellanrum för att ge intryck av att objektet roteras och vändas. Om en endimensionell snurra t.ex. innehåller 12 tagningar roterar du objektet 30 grader (360/12) för varje tagning.

Du kan överföra bilder för snurra uppsättningar på samma sätt som du gör [ladda upp alla andra resurser i AEM Assets](managing-assets-touch-ui.md).

### Riktlinjer för fotografering av snurra uppsättningsbilder {#guidelines-for-shooting-spin-set-images}

Nedan följer några tips om hur du använder snurra uppsättningsbilder. Ju fler bilder du har i en snurrfunktion, desto bättre blir effekten av att snurra. Om du inkluderar många bilder i uppsättningen ökar dock tiden det tar för bilderna att läsas in. AEM rekommenderar följande riktlinjer för att ta bilder för användning i snurra uppsättningar:

* Använd minst 8-12 bilder i en endimensionell snurra och 16-24 bilder i en tvådimensionell snurra. Minst 8 bilder krävs för att kunna vridas 360 grader. Endimensionella snurruppsättningar är vanligare eftersom tvådimensionella snurvuppsättningar är arbetsintensiva.
* Använd ett förlustfritt format, TIFF och PNG rekommenderas.
* Maskera alla bilder så att objektet visas på en helt vit eller annan bakgrund med hög kontrast. Du kan också lägga till skuggor.
* Se till att produktinformationen är väl belyst och i fokus.
* Ta snurra bilder till modekläder med mannequin eller modell. Ofta är mannequin antingen helt maskerat (med hjälp av en glasmannequin) eller en stiliserad mannequin/form visas i bilden. Du kan skapa en omformningsrotation genom att definiera antalet vinklar. Markera varje vinkel med band på golvet för att vägleda modellen till steg och titta i riktningen för varje tagning.

## Skapa snurruppsättningar {#creating-spin-sets}

Den ordning i vilken bilderna visas i en snurrfunktion. Se till att ordna dem så att snurret blir en jämn 360-gradersvy.

>[!NOTE]
>
>Du kan också skapa rotationsuppsättningar automatiskt med hjälp av [förinställningar för gruppuppsättningar](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).
>
>Batchuppsättningar skapas av IPS (Image Production System) som en del av tillgångsintag och är endast tillgängliga i Dynamic Media-Scene7-läge.
>
>Se&quot;Skapa gruppuppsättningsförinställningar för automatisk generering av bilduppsättningar och snurruppsättningar&quot; i [Konfigurera Dynamic Media - Scene7-läge](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

När du skapar en snurrsuppsättning rekommenderar Adobe följande bästa praxis och tillämpar följande gräns:

| Begränsningstyp | Bästa praxis | Implementerad gräns |
| --- | --- | --- |
| Maximalt antal rader/kolumner per 2D-uppsättning | 12-18 bilder per uppsättning | 1000 |

Se även [Dynamic Media begränsningar](/help/assets/limitations.md).

**Så här skapar du snurruppsättningar:**

1. I Resurser navigerar du till den plats där du vill skapa en snurruppsättning och trycker på **[!UICONTROL Create]** och markera **[!UICONTROL Spin Set]**. Du kan också skapa uppsättningen inifrån en mapp som innehåller resurserna.

   ![chlimage_1-381](assets/chlimage_1-381.png)

1. På **[!UICONTROL Spin Set Editor]** sida, på **[!UICONTROL Title]** anger du ett namn för rotationsrutan. Namnet visas i banderollen över snurruppsättningen. Du kan också ange en beskrivning.

   ![chlimage_1-382](assets/chlimage_1-382.png)

   När du skapar rotationsuppsättningen kan du ändra miniatyrbilden för rotationsuppsättningen eller låta AEM välja miniatyrbilden automatiskt baserat på resurserna i rotationsuppsättningen. Välj en miniatyrbild genom att trycka **[!UICONTROL Change thumbnail]**. Markera en bild (du kan navigera till andra mappar om du även vill söka efter bilder). Om du har markerat en miniatyrbild och sedan vill AEM generera en från rotationsuppsättningen väljer du **[!UICONTROL Switch to Automatic thumbnail]**.

1. Gör något av följande:

   * Nära det övre vänstra hörnet av **[!UICONTROL Spin Set Editor]** sida, tryck **[!UICONTROL Add Asset]**.
   * I mitten av **[!UICONTROL Spin Set Editor]** sida, tryck **[!UICONTROL Tap to open Asset Selector]**.

   Tryck för att välja resurser som du vill inkludera i din snurruppsättning. De markerade resurserna visas med en bock. När du är klar trycker du på **[!UICONTROL Select]**.

   Med resursväljaren kan du söka efter resurser genom att skriva ett nyckelord och trycka på **[!UICONTROL Return]**. Du kan också använda filter för att förfina sökresultatet. Du kan filtrera efter sökväg, samling, filtyp och tagg. Markera filtret och tryck sedan på ikonen **[!UICONTROL Filter]** i verktygsfältet. Om du vill ändra vyn trycker du på längst upp till höger på sidan **[!UICONTROL View]** ikonen och tryck sedan **[!UICONTROL Column View]**, **[!UICONTROL Card View]**, eller **[!UICONTROL List View]**.

   Se [Arbeta med väljare](working-with-selectors.md).

   ![chlimage_1-383](assets/chlimage_1-383.png)

1. När du lägger till resurser i uppsättningen läggs de automatiskt till i alfanumerisk ordning. Du kan sortera om eller sortera resurser manuellt när du har lagt till dem. Om det behövs drar du en resurs **[!UICONTROL Reorder]** till höger om resursens filnamn om du vill ändra ordning på bilderna i uppsättningslistan.

   ![spin_set_assets6-4](assets/spin_set_assets6-4.png)

1. (Valfritt) Gör något av följande:

   * Om du vill ta bort en bild markerar du bilden och trycker sedan **[!UICONTROL Delete Asset]**.
   * Om du vill använda en förinställning i det övre högra hörnet av sidan trycker du på **[!UICONTROL Preset]** väljer du sedan en förinställning som ska användas på alla resurser samtidigt.

1. Tryck på **[!UICONTROL Save]**. Den nyligen skapade rotationsuppsättningen visas i den mapp som du skapade den i.

## Visa snurruppsättningar {#viewing-spin-sets}

Du kan skapa snurruppsättningar antingen i användargränssnittet eller automatiskt med [gruppuppsättningsförinställningar](/help/assets/config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets). Men uppsättningar som skapats med gruppuppsättningsförinställningar gör *not* visas i användargränssnittet. Du kan komma åt uppsättningar som skapats med hjälp av gruppuppsättningsförinställningar på tre olika sätt. (De här metoderna är tillgängliga även om du har skapat snurruppsättningarna i användargränssnittet).

Du kan också visa uppsättningar via användargränssnittet enligt beskrivningen i [Redigera snurruppsättningar](#editing-spin-sets).

**Så här visar du snurruppsättningar:**

1. När egenskaperna för en enskild resurs öppnas. Egenskaperna anger vad som ställer in den valda resursen som medlem av (under **[!UICONTROL Member of Sets]**). Tryck på uppsättningens namn för att visa hela uppsättningen.

   ![chlimage_1-384](assets/chlimage_1-384.png)

1. Från en medlemsbild i en uppsättning. Välj **[!UICONTROL Sets]** för att visa de uppsättningar som resursen är medlem i.

   ![chlimage_1-385](assets/chlimage_1-385.png)

1. Du kan välja **[!UICONTROL Filters]** och sedan expandera **[!UICONTROL Dynamic Media]** och markera **[!UICONTROL Sets]**.

   Sökningen returnerar matchande uppsättningar som skapats manuellt i användargränssnittet eller automatiskt skapats med gruppuppsättningsförinställningar. För automatiska uppsättningar utförs sökfrågan med **[!UICONTROL Starts with]** sökvillkor som skiljer sig från AEM sökning som baseras på **[!UICONTROL Contains]** sökvillkor. Ange att filtret ska **[!UICONTROL Sets]** är det enda sättet att söka i automatiska uppsättningar.

   ![chlimage_1-386](assets/chlimage_1-386.png)

## Redigera snurruppsättningar {#editing-spin-sets}

Du kan utföra en mängd redigeringsåtgärder på snurra uppsättningar, till exempel:

* Lägg till bilder i rotationsrutan.
* Ändra ordning på bilderna i rotationsrutan.
* Ta bort resurser i rotationsuppsättningen.
* Använd förinställningar för visningsprogram.
* Ta bort rotationsrutan.

**Så här redigerar du en snurra:**

1. Gör något av följande:

   * Håll pekaren över en resurs i en snurra uppsättning och tryck sedan **[!UICONTROL Edit]** (pennikon).
   * Håll pekaren över en resurs i en snurra uppsättning, tryck **[!UICONTROL Select]** (bockmarkeringsikon) och sedan trycka **[!UICONTROL Edit]** i verktygsfältet.
   * Tryck på en resurs för att snurra uppsättning och tryck sedan på **[!UICONTROL Edit]** (pennikon) i verktygsfältet.

1. Gör något av följande om du vill redigera rotationsuppsättningen:

   * Om du vill ändra ordning på bilderna drar du en bild till en ny plats (markera ikonen för att ändra ordning för att flytta objekt).
   * Om du vill sortera objekt i stigande eller fallande ordning trycker du på kolumnrubriken.
   * Om du vill lägga till en resurs eller uppdatera en befintlig resurs trycker du **[!UICONTROL Add Asset]**. Navigera till en resurs, markera den och tryck sedan på **[!UICONTROL Select]** nära det övre högra hörnet.
Om du tar bort den bild som AEM använder som miniatyrbild genom att ersätta den med en annan bild, visas fortfarande originalresursen.
   * Om du vill ta bort en resurs markerar du den och trycker på **[!UICONTROL Delete Asset]**.
   * Om du vill använda en förinställning trycker du på **[!UICONTROL Preset]** och välj en förinställning.
   * Om du vill ta bort en hel snurruppsättning går du till snurra-uppsättningen, markerar den och markerar den **[!UICONTROL Delete]**

      >[!NOTE]
      >* Du kan redigera bilderna i en snurruppsättning genom att gå till uppsättningen och trycka på **[!UICONTROL Set Members]** till vänster och tryck sedan på **[!UICONTROL Edit]** (pennikon) på en enskild resurs för att öppna redigeringsfönstret.


1. Klicka **[!UICONTROL Save]** när redigeringen är klar.

## Förhandsgranska snurra uppsättningar {#previewing-spin-sets}

Se [Förhandsgranska resurser](previewing-assets.md).

## Publicera snurruppsättningar {#publishing-spin-sets}

Se [Publicera resurser](publishing-dynamicmedia-assets.md).
