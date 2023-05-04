---
title: Importera och exportera massmetadata
description: I den här artikeln beskrivs hur du importerar och exporterar flera metadata samtidigt.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: 956cdec4-2ba8-43c9-9122-564d764f4681
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 7%

---

# Importera och exportera massvis med metadata {#bulk-metadata-import-and-export}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

[!DNL Experience Manager] Med resurser kan du importera resursmetadata gruppvis med hjälp av en CSV-fil. Du kan göra satsvisa uppdateringar för de nyligen överförda resurserna eller för befintliga resurser genom att importera en CSV-fil. Du kan också importera resursmetadata i grupp från tredjepartssystem i CSV-format.

## Importera metadata {#import-metadata}

Import av metadata är asynkron och påverkar inte systemets prestanda. Samtidig uppdatering av metadata för flera resurser kan vara resurskrävande på grund av XMP återskrivningsaktivitet om arbetsflödesflaggan är markerad. Planera en sådan import under begränsad serveranvändning för att förhindra prestandapåverkan för andra användare.

>[!NOTE]
>
>Om du vill importera metadata för anpassade namnutrymmen måste du först registrera namnutrymmena.

Så här importerar du flera metadata samtidigt:

1. Navigera till användargränssnittet Resurser och tryck/klicka **[!UICONTROL Create]** i verktygsfältet.
1. Välj **[!UICONTROL Metadata]** i menyn.
1. På **[!UICONTROL Metadata Import]** sida, tryck/klicka på **[!UICONTROL Select File]**.  Markera CSV-filen med metadata.
1. Kontrollera att CSV-filen innehåller följande parametrar:

   | Parametrar för metadataimport | Beskrivning |
   |:---|:---|
   | [!UICONTROL Batch Size] | Antal resurser i en grupp som metadata ska importeras för. Standardvärdet är 50. Maxvärdet är 100. |
   | [!UICONTROL Field Separator] | Standardvärdet är `,` - ett komma. Du kan ange andra tecken. |
   | [!UICONTROL Multi Value Delimiter] | Avgränsare för metadatavärden. Standardvärdet är `|` - ett rör. |
   | [!UICONTROL Launch Workflows] | Falskt som standard. Om värdet är true används standardinställningarna för `DAM Metadata WriteBack Workflow` (som skriver metadata till binära XMP). Om du aktiverar arbetsflödena påverkas systemets prestanda. |
   | [!UICONTROL Asset Path Column Name] | Definierar kolumnnamnet för CSV-filen med resurser. |

1. Tryck/klicka **[!UICONTROL Import]** i verktygsfältet. När metadata har importerats skickas ett meddelande till din meddelandeinkorg. Navigera till egenskapssidan för resurser och kontrollera om metadatavärdena har importerats korrekt för resurser.

Om du vill lägga till datum och tidsstämpel när du importerar metadata använder du `YYYY-MM-DDThh:mm:ss.fff-00:00` format för datum och tid. Datum och tid avgränsas med `T`, `hh` är timmar i 24-timmarsformat, `fff` är nanosekunder, och `-00:00` är tidszonsförskjutning. Till exempel: `2020-03-26T11:26:00.000-07:00` är 26 mars 2020 kl. 11:26:00 000 PST-tid.

>[!CAUTION]
>
>Om datumformatet inte matchar `YYYY-MM-DDThh:mm:ss.fff-00:00`, ställs datumvärdena inte in. Datumformaten för den exporterade CSV-metadatafilen har formatet `YYYY-MM-DDThh:mm:ss-00:00`. Om du vill importera den konverterar du den till ett godkänt format genom att lägga till värdet för nanosekunder som markeras med `fff`.

## Exportera metadata {#export-metadata}

Några exempel på användningsområden för att exportera flera metadata samtidigt är:

* Importera metadata i ett tredjepartssystem när du migrerar resurser.
* Dela metadata med ett större projektteam.
* Testa eller granska metadata för att se om de är kompatibla.
* Gör metadata externt för separat lokalisering.

Du kan exportera metadata för flera resurser i ett CSV-format. Metadata exporteras asynkront och påverkar inte systemets prestanda. Om du vill exportera metadata [!DNL Experience Manager] går igenom objektnodens egenskaper `jcr:content/metadata` och dess underordnade noder och exporterar metadataegenskaperna i en CSV-fil.

Så här exporterar du metadata för flera resurser samtidigt:

1. Välj den resursmapp som innehåller resurser som du vill exportera metadata för. Välj **[!UICONTROL Export metadata]** i verktygsfältet.

1. I [!UICONTROL Metadata Export] anger du ett namn för CSV-filen. Om du vill exportera metadata för resurser i undermappar väljer du **[!UICONTROL Include assets in sub-folders]**.

   ![export_metadata_page](assets/export_metadata_page.png)

1. Välj önskade alternativ. Ange ett filnamn och vid behov ett datum.
1. I **[!UICONTROL Properties to be exported]** anger du om du vill exportera alla eller specifika egenskaper. Om du väljer **[!UICONTROL Selective]** de egenskaper som ska exporteras lägger du till önskade egenskaper.

1. Tryck/klicka i verktygsfältet **[!UICONTROL Export]**. Ett meddelande bekräftar att metadata exporteras. Stäng meddelandet.

1. Öppna inkorgsmeddelandet för exportjobbet. Markera jobbet och klicka på **[!UICONTROL Open]** i verktygsfältet. Om du vill hämta CSV-filen med metadata trycker/klickar du på **[!UICONTROL CSV Download]** i verktygsfältet. Klicka på **[!UICONTROL Close]**.

   ![csv_download](assets/csv_download.png)
