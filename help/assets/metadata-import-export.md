---
title: Importera och exportera massmetadata
description: I den här artikeln beskrivs hur du importerar och exporterar flera metadata samtidigt.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1

---


# Importera och exportera massmetadata {#bulk-metadata-import-and-export}

Med AEM Resurser kan du importera resursmetadata i grupp med hjälp av en CSV-fil. Du kan göra satsvisa uppdateringar för de nyligen överförda resurserna eller för befintliga resurser genom att importera en CSV-fil. Du kan också importera resursmetadata i grupp från tredjepartssystem i CSV-format.

## Importera metadata {#import-metadata}

Import av metadata är asynkron och påverkar inte systemets prestanda. Samtidig uppdatering av metadata för flera resurser kan vara resurskrävande på grund av XMP-återskrivningsaktivitet om arbetsflödesflaggan är markerad. Planera en sådan import under begränsad serveranvändning så att prestanda för andra användare inte påverkas.

>[!NOTE]
>
>Om du vill importera metadata för anpassade namnutrymmen måste du först registrera namnutrymmena.

1. Navigera till användargränssnittet Resurser och tryck/klicka på **[!UICONTROL Skapa]** i verktygsfältet.
1. Välj **[!UICONTROL Metadata]** på menyn.
1. På sidan **[!UICONTROL Metadataimport]** trycker/klickar du på **[!UICONTROL Välj fil]**.  Markera CSV-filen med metadata.
1. Ange följande parametrar:

   | Parametrar för metadataimport | Beskrivning |
   |:---|:---|
   | [!UICONTROL Batchstorlek] | Antal resurser i en grupp som metadata ska importeras för. Standardvärdet är 50. Maxvärdet är 100. |
   | [!UICONTROL Fältavgränsare] | Standardvärdet är Komma. Du kan ange andra tecken. |
   | [!UICONTROL Flervärdesavgränsare] | Avgränsare för metadatavärden. Standardvärdet är | . |
   | [!UICONTROL Starta arbetsflöden] | Falskt som standard. När värdet är true används standardinställningarna för startprogrammet för arbetsflödet WriteBack för DAM-metadata (som skriver metadata till binära XMP-data). Om du aktiverar startarbetsflöden blir systemet långsammare. |
   | [!UICONTROL Kolumnnamn för resurssökväg] | Definierar kolumnnamnet för CSV-filen med resurser. |

1. Tryck/klicka på **[!UICONTROL Importera]** i verktygsfältet. När metadata har importerats skickas ett meddelande till din meddelandeinkorg. Navigera till egenskapssidan för resurser och kontrollera om metadatavärdena har importerats korrekt för resurser.

<!-- TBD: Format characters in the table using backticks and add UICONTROL after table is converted to MD
-->

## Exportera metadata {#export-metadata}

Du kan exportera metadata för flera resurser i ett CSV-format. Metadata exporteras asynkront och påverkar inte systemets prestanda. Om du vill exportera metadata går AEM igenom egenskaperna för objektnoden `jcr:content/metadata` och dess underordnade noder och exporterar metadataegenskaperna i en CSV-fil.

Några exempel på användningsområden för att exportera flera metadata samtidigt är:

* Importera metadata i ett tredjepartssystem när du migrerar resurser.
* Dela metadata med ett större projektteam.
* Testa eller granska metadata för att se om de är kompatibla.
* Gör metadata externt för separat lokalisering.

1. Välj den resursmapp som innehåller resurser som du vill exportera metadata för. Välj **[!UICONTROL Exportera metadata]** i verktygsfältet.

1. Ange ett namn för CSV-filen i dialogrutan Exportera metadata. Om du vill exportera metadata för resurser i undermappar väljer du **[!UICONTROL Inkludera resurser i undermappar]**.

   ![export_metadata_page](assets/export_metadata_page.png)

1. Välj önskade alternativ. Ange ett filnamn och vid behov ett datum.
1. I **[!UICONTROL Egenskaper som ska exporteras]** anger du om du vill exportera alla eller specifika egenskaper. Om du väljer **[!UICONTROL Selektiva]** egenskaper som ska exporteras lägger du till önskade egenskaper.

1. Tryck/klicka på **[!UICONTROL Exportera]** i verktygsfältet. Ett meddelande bekräftar att metadata exporteras. Stäng meddelandet.

1. Öppna inkorgsmeddelandet för exportjobbet. Markera jobbet och klicka på **[!UICONTROL Öppna]** i verktygsfältet. Om du vill hämta CSV-filen med metadata trycker/klickar du på **[!UICONTROL CSV-hämtning]** i verktygsfältet. Click **[!UICONTROL Close]**.

   ![csv_download](assets/csv_download.png)
