---
title: Importera och exportera massmetadata
description: I den här artikeln beskrivs hur du importerar och exporterar flera metadata samtidigt.
contentOwner: AG
feature: Metadata
role: Business Practitioner,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 8%

---


# Importera och exportera massvis med metadata{#bulk-metadata-import-and-export}

Med AEM Assets kan du importera resursmetadata i grupp med hjälp av en CSV-fil. Du kan göra satsvisa uppdateringar för de nyligen överförda resurserna eller för befintliga resurser genom att importera en CSV-fil. Du kan också importera resursmetadata i grupp från tredjepartssystem i CSV-format.

## Importera metadata {#import-metadata}

Import av metadata är asynkron och påverkar inte systemets prestanda. Samtidig uppdatering av metadata för flera resurser kan vara resurskrävande på grund av XMP återskrivningsaktivitet om arbetsflödesflaggan är markerad. Planera en sådan import under begränsad serveranvändning för att förhindra prestandapåverkan för andra användare.

>[!NOTE]
>
>Om du vill importera metadata för anpassade namnutrymmen måste du först registrera namnutrymmena.

Så här importerar du flera metadata samtidigt:

1. Navigera till användargränssnittet Resurser och tryck/klicka på **[!UICONTROL Create]** i verktygsfältet.
1. Välj **[!UICONTROL Metadata]** i menyn.
1. Tryck/klicka på **[!UICONTROL Select File]** på sidan **[!UICONTROL Metadata Import]**.  Markera CSV-filen med metadata.
1. Kontrollera att CSV-filen innehåller följande parametrar:

   | Parametrar för metadataimport | Beskrivning |
   |:---|:---|
   | [!UICONTROL Batch Size] | Antal resurser i en grupp som metadata ska importeras för. Standardvärdet är 50. Maxvärdet är 100. |
   | [!UICONTROL Field Separator] | Standardvärdet är `,` - ett komma. Du kan ange andra tecken. |
   | [!UICONTROL Multi Value Delimiter] | Avgränsare för metadatavärden. Standardvärdet är `|` - en pipe. |
   | [!UICONTROL Launch Workflows] | Falskt som standard. När värdet är true används standardinställningarna för startprogrammet för `DAM Metadata WriteBack Workflow` (som skriver metadata till binära XMP). Om du aktiverar startarbetsflöden påverkas systemets prestanda. |
   | [!UICONTROL Asset Path Column Name] | Definierar kolumnnamnet för CSV-filen med resurser. |

1. Tryck/klicka på **[!UICONTROL Import]** i verktygsfältet. När metadata har importerats skickas ett meddelande till din meddelandeinkorg. Navigera till egenskapssidan för resurser och kontrollera om metadatavärdena har importerats korrekt för resurser.

Om du vill lägga till datum och tidsstämpel när du importerar metadata använder du formatet `YYYY-MM-DDThh:mm:ss.fff-00:00` för datum och tid. Datum och tid avgränsas med `T`, `hh` är timmar i 24-timmarsformat, `fff` är nanosekunder och `-00:00` är tidszonsförskjutning. Till exempel är `2020-03-26T11:26:00.000-07:00` den 26 mars 2020 kl. 11:26:00.000 PST-tid.

>[!CAUTION]
>
>Om datumformatet inte matchar `YYYY-MM-DDThh:mm:ss.fff-00:00`, ställs datumvärdena inte in. Datumformaten för den exporterade CSV-metadatafilen har formatet `YYYY-MM-DDThh:mm:ss-00:00`. Om du vill importera den konverterar du den till ett godkänt format genom att lägga till värdet för nanosekunder som anges med `fff`.

## Exportera metadata {#export-metadata}

Några exempel på användningsområden för att exportera flera metadata samtidigt är:

* Importera metadata i ett tredjepartssystem när du migrerar resurser.
* Dela metadata med ett större projektteam.
* Testa eller granska metadata för att se om de är kompatibla.
* Gör metadata externt för separat lokalisering.

Du kan exportera metadata för flera resurser i ett CSV-format. Metadata exporteras asynkront och påverkar inte systemets prestanda. Om du vill exportera metadata går AEM igenom egenskaperna för objektnoden `jcr:content/metadata` och dess underordnade noder och exporterar metadataegenskaperna i en CSV-fil.

Så här exporterar du metadata för flera resurser samtidigt:

1. Välj den resursmapp som innehåller resurser som du vill exportera metadata för. Välj **[!UICONTROL Export metadata]** i verktygsfältet.

1. Ange ett namn för CSV-filen i dialogrutan [!UICONTROL Metadata Export]. Om du vill exportera metadata för resurser i undermappar väljer du **[!UICONTROL Include assets in sub-folders]**.

   ![export_metadata_page](assets/export_metadata_page.png)

1. Välj önskade alternativ. Ange ett filnamn och vid behov ett datum.
1. I **[!UICONTROL Properties to be exported]** anger du om du vill exportera alla eller specifika egenskaper. Om du väljer **[!UICONTROL Selective]**-egenskaper som ska exporteras lägger du till de önskade egenskaperna.

1. Tryck/klicka på **[!UICONTROL Export]** i verktygsfältet. Ett meddelande bekräftar att metadata exporteras. Stäng meddelandet.

1. Öppna inkorgsmeddelandet för exportjobbet. Markera jobbet och klicka på **[!UICONTROL Open]** i verktygsfältet. Om du vill hämta CSV-filen med metadata trycker/klickar du på **[!UICONTROL CSV Download]** i verktygsfältet. Klicka på **[!UICONTROL Close]**.

   ![csv_download](assets/csv_download.png)
