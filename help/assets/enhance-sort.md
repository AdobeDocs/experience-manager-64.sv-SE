---
title: Förbättrad sortering av material i AEM
description: Lär dig mer [!DNL Experience Manager] Resurser distribuerar sortering på serversidan för att sortera mappresurser eller en sökfråga samtidigt i stället för att sortera dem i grupper på klientsidan.
contentOwner: AG
feature: Search
role: User
exl-id: aa24ca68-d94e-4bd4-a5cc-113906650a2e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '465'
ht-degree: 1%

---

# Förbättrad sortering av resurser i [!DNL Experience Manager] {#enhanced-sorting-of-assets-in-aem}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Lär dig mer [!DNL Experience Manager] Resurser distribuerar sortering på serversidan för att sortera mappresurser eller en sökfråga samtidigt i stället för att sortera dem i grupper på klientsidan.

Sökfunktionen i Adobe Experience Manager Assets har förbättrats så att du effektivt kan sortera ett stort antal resurser i mapplistvyn och på sökresultatsidorna. Du kan också sortera tidslinjeposter.

[!DNL Experience Manager] Resurser använder sortering på serversidan för att sortera hela uppsättningen resurser (oavsett var de är stora) i en mapp eller en sökfråga på en gång i stället för att sortera dem i grupper på klientsidan. På så sätt kan förhämtade resultat snabbt visas i användargränssnittet, vilket gör sorteringsåtgärden mer responsiv och snabb.

## Sortera resurser i listvyn {#sorting-assets-in-list-view}

[!DNL Experience Manager] Med resurser kan du sortera mappresurser baserat på följande fält:

* Språk
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
>Sortera värdena i `Name` eller `Title`kolumner, övertäckning `/libs/dam/gui/content/commons/availablecolumns` och ändra värdet för `sortable` till `True`.

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

[!DNL Assets] Med kan du sortera tidslinjeposter kronologiskt, t.ex. anteckningar, versioner, arbetsflöden och aktiviteter.

1. I resursgränssnittet väljer du en resurs som du vill visa tidslinjen för.
1. Klicka/tryck på ikonen GlobalNav och välj **[!UICONTROL Timeline]**.

   ![chlimage_1-399](assets/chlimage_1-399.png)

1. Välj en post i listan på tidslinjen. Välj till exempel **[!UICONTROL Comments]** om du vill visa en lista med anteckningar som är associerade med resursen.

   ![chlimage_1-400](assets/chlimage_1-400.png)

1. Klicka/tryck på **[!UICONTROL Sort]** -ikonen bredvid **[!UICONTROL Date]** label. Beroende på vad du väljer listas anteckningarna i den kronologiska/omvända kronologiska ordning som de lades till i resursen.

   ![chlimage_1-401](assets/chlimage_1-401.png)
