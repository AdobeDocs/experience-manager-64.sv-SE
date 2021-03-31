---
title: Sök efter resurser i AEM
description: Lär dig hur du söker efter nödvändiga resurser i AEM genom att använda panelen Filter och hur du använder de resurser som visas i sökningen.
contentOwner: AG
feature: Sök,Metadata
role: Yrkesverksamma inom affärsverksamhet
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '554'
ht-degree: 1%

---


# Sök efter resurser i AEM {#search-assets-in-aem}

Lär dig hur du söker efter nödvändiga resurser i AEM genom att använda panelen Filter och hur du använder de resurser som visas i sökningen.

Använd panelen Filter för att söka efter resurser, mappar, taggar och metadata. Du kan söka efter delar av en sträng med hjälp av asterisk med jokertecken.

På panelen Filter finns olika alternativ för att söka efter resurser och mappar på flera sätt i stället för i en allmän taxonisk ordning.

Du kan söka baserat på följande alternativ (prediktiv):

* Filtyp
* Filstorlek
* Fältnamn
* Senast ändrad
* Status
* Orientering
* Format
* Insikter

<!-- TBD keystroke 65 article and port applicable changes here. This content goes. -->

Du kan anpassa panelen Filter och lägga till/ta bort sökpredikatorn med [sökfaktorer](search-facets.md). Så här visar du panelen Filter:

1. Tryck/klicka på ![search_icon](assets/search_icon.png) i verktygsfältet i Assets-användargränssnittet för att visa rutan Omnissearch.
1. Ange söktermen och tryck på Retur. Du kan också trycka på Retur utan att ange något sökord. Ange inga inledande blanksteg, annars fungerar inte sökningen.

1. Tryck/klicka på ikonen GlobalNav. Panelen Filter visas.

   ![filters_panel-1](assets/filters_panel-1.png)

   Beroende på vilken typ av objekt du söker efter visas antalet träffar högst upp i sökresultatet.

   ![antal_sökningar](assets/number_of_searches.png)

## Sök efter filtyper {#search-for-file-types}

Med panelen Filter kan du göra sökningen mer detaljerad och sökfunktionen mer flexibel. Du kan enkelt gå ned till önskad detaljnivå.

Om du till exempel söker efter en bild använder du predikatet **[!UICONTROL File Type]** för att välja om du vill ha en bitmappsbild eller en vektorbild.

![image_type](assets/image_type.png)

Du kan begränsa sökningen ytterligare genom att ange bildens MIME-typ.

![mime_type](assets/mime_type.png)

På samma sätt kan du ange formatet när du söker efter dokument, till exempel PDF eller MS Word.

![dokument](assets/documents.png)

## Sök baserat på filstorlek {#search-based-on-file-size}

Använd predikatet **Filstorlek** för att söka efter resurser baserat på deras storlek. Du kan ange de nedre och övre gränserna för storleksintervallet för att begränsa sökningen. Du kan också ange måttenhet, till exempel kB, megabyte och så vidare.

![måttenhet](assets/unit_of_measure.png)

## Sökning baserad på när resurser senast ändrades {#search-based-on-when-assets-are-last-modified}

Om du hanterar resurser som är under arbete eller övervakar ett granskningsarbetsflöde kan du söka efter när en resurs senast ändrades baserat på korrekta tidsstämplar. Ange till exempel datum före eller efter vilka resurser ändrades.

![last_modified_dates](assets/last_modified_dates.png)

Du kan också använda följande alternativ för att få en högre detaljnivå i sökningen:

![tidsstämpel](assets/timestamp.png)

## Sök baserat på status {#search-based-on-status}

Använd predikatet **Status** för att söka efter resurser baserat på olika typer av status, till exempel Publicera, Godkännande, Utcheckning och Förfallotid.

![status](assets/status.png)

När du övervakar publicering av resurser kan du till exempel använda lämpligt alternativ för att söka efter vilka resurser som publiceras.

![publicera](assets/publish.png)

När du övervakar granskningsstatusen för resurser ska du använda lämpligt alternativ för att hitta vilka resurser som är godkända eller vilka resurser som väntar på godkännande.

![godkännande](assets/approval.png)

## Sök baserat på Insights-data {#search-based-on-insights-data}

Använd **Insights**-predikatet för att söka efter resurser baserat på användningsstatistik från olika Creative-program. Användningsdata grupperas under följande kategorier:

* Användningspoäng
* Impressions
* Klickningar
* Mediekanaler där resurserna visas

![insikter](assets/insights.png)
