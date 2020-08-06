---
title: Förbättrad sortering av material i AEM
description: Lär dig hur AEM Assets använder sortering på serversidan för att sortera mappresurser eller en sökfråga samtidigt i stället för att sortera dem gruppvis på klientsidan.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '437'
ht-degree: 3%

---


# Förbättrad sortering av material i AEM {#enhanced-sorting-of-assets-in-aem}

Lär dig hur AEM Assets använder sortering på serversidan för att sortera mappresurser eller en sökfråga samtidigt i stället för att sortera dem gruppvis på klientsidan.

Sökfunktionen i Adobe Experience Manager (AEM) Assets har förbättrats så att du effektivt kan sortera ett stort antal resurser i mapplistvyn och söka efter resultatsidor. Du kan också sortera tidslinjeposter.

AEM Assets använder sortering på serversidan för att sortera hela uppsättningen resurser (oavsett var de är stora) i en mapp eller en sökfråga på en gång i stället för att sortera dem gruppvis på klientsidan. På så sätt kan förhämtade resultat snabbt visas i användargränssnittet, vilket gör sorteringsåtgärden mer responsiv och snabb.

## Sortera resurser i listvyn {#sorting-assets-in-list-view}

I AEM Assets kan du sortera mappresurser baserat på följande fält:

* Nat. inst
* Status
* Typ
* Storlek
* Klassificering
* Ändrat den
* Publiceringsdatum
* Användning
* Klickningar
* Impressions
* Utcheckad

1. Navigera till en mapp som innehåller ett stort antal resurser.
1. Klicka/tryck på layoutikonen och växla till listvyn.

   ![chlimage_1-394](assets/chlimage_1-394.png)

1. Klicka/tryck på ikonen Sortera bredvid en kolumnrubrik i listan med resurser.

   ![chlimage_1-395](assets/chlimage_1-395.png)

   Listan med resurser sorteras baserat på fältvärdena.

   ![chlimage_1-396](assets/chlimage_1-396.png)

>[!NOTE]
>
>Om du vill sortera värdena i `Name` eller i `Title`kolumnerna ska du täcka över `/libs/dam/gui/content/commons/availablecolumns` och ändra värdet för `sortable` till `True`.

## Sortera resurser i sökresultat {#sorting-assets-in-search-results}

Du kan sortera sökresultaten baserat på följande fält:

* Titel
* Status
* Typ
* Storlek
* Ändrat den
* Publiceringsdatum

1. I rutan OmniSearch söker du efter resurser baserat på önskade villkor.

   ![chlimage_1-397](assets/chlimage_1-397.png)

1. Klicka/tryck på layoutikonen och växla till listvyn. Om sökresultaten redan visas i listvyn hoppar du över det här steget.
1. Klicka/tryck på ikonen Sortera bredvid en kolumnrubrik i listan med resurser. Listan med resurser sorteras baserat på fältvärdena.

   ![chlimage_1-398](assets/chlimage_1-398.png)

## Sortera resurser på tidslinjen {#sorting-assets-in-timeline}

Med AEM Assets kan du sortera tidslinjeposter kronologiskt, till exempel anteckningar, versioner, arbetsflöden och aktiviteter.

1. I resursgränssnittet väljer du en resurs som du vill visa tidslinjen för.
1. Klicka på/tryck på ikonen GlobalNav och välj **[!UICONTROL Timeline]**.

   ![chlimage_1-399](assets/chlimage_1-399.png)

1. Välj en post i listan på tidslinjen. Välj **[!UICONTROL Comments]** till exempel om du vill visa en lista med anteckningar som är associerade med resursen.

   ![chlimage_1-400](assets/chlimage_1-400.png)

1. Klicka på/tryck på **[!UICONTROL Sort]** ikonen bredvid **[!UICONTROL Date]** etiketten. Beroende på vad du väljer listas anteckningarna i den kronologiska/omvända kronologiska ordning som de lades till i resursen.

   ![chlimage_1-401](assets/chlimage_1-401.png)

