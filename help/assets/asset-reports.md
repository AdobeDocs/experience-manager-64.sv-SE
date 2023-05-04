---
title: Rapporter om användning och delning av digitala resurser.
description: Rapporter om dina resurser i [!DNL Adobe Experience Manager Assets] som hjälper er att förstå användningen, aktiviteten och delningen av era digitala resurser.
contentOwner: AG
feature: Asset Reports,Asset Management
role: User,Admin
exl-id: 6f03ee04-d2e2-47e6-892b-50fad3043a28
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 9%

---

# Materialrapporter {#asset-reports}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med tillgångsrapportering kan du bedöma hur användbar din [!DNL Adobe Experience Manager Assets] distribution. Med [!DNL Assets]kan du generera olika rapporter för dina digitala resurser. Rapporterna innehåller användbar information om hur ditt system används, hur användarna interagerar med resurser och vilka resurser som hämtas och delas.

Använd informationen i rapporterna för att ta fram nyckeltal för att mäta antagandet av [!DNL Assets] inom företaget och av kunderna.

The [!DNL Assets] rapporteringsramverk använder [!DNL Sling] jobb för att asynkront bearbeta rapportbegäranden på ett ordnat sätt. Den kan skalas för stora databaser. Asynkron rapportbearbetning ökar effektiviteten och hastigheten med vilken rapporter genereras.

Rapporthanteringsgränssnittet är intuitivt och innehåller detaljerade alternativ och kontroller för att komma åt arkiverade rapporter och visa rapportkörningsstatus (lyckad, misslyckad och köad).

När en rapport skapas meddelas du via ett e-postmeddelande (valfritt) och ett inkorgsmeddelande. Du kan visa, hämta eller ta bort en rapport från rapportlistsidan, där alla tidigare genererade rapporter visas.

## Förutsättning {#prerequisite-for-reporting}

Om du vill generera rapporter måste du se till att:

* Aktivera [!UICONTROL Day CQ DAM Event Recorder] tjänst från **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
* Välj de aktiviteter eller händelser som du vill rapportera om. Om du till exempel vill generera en rapport om hämtade resurser väljer du [!UICONTROL Asset downloaded (DOWNLOADED)].

![Aktivera tillgångsrapportering i webbkonsolen](assets/reports-config-day-cq-dam-event-recorder.png)

## Generera rapporter {#generate-reports}

[!DNL Experience Manager Assets] genererar följande standardrapporter:

* Överför
* Hämta
* Förfaller
* Ändring
* Publicera
* [!DNL Brand Portal] publicera
* Diskanvändning
* Filer
* Länkdelning

[!DNL Adobe Experience Manager] administratörer kan enkelt generera och anpassa dessa rapporter för din implementering. Administratören kan följa de här stegen för att skapa en rapport:

1. I [!DNL Experience Manager] gränssnitt, klicka **[!UICONTROL Tools]** > **[!UICONTROL Assets]** > **[!UICONTROL Reports]**.

   ![Verktygssida för att navigera bland resurser - rapport](assets/navigation.png)

1. På [!UICONTROL Asset Reports] sida, klicka **[!UICONTROL Create]** i verktygsfältet.
1. Från **[!UICONTROL Create Report page]** väljer du den rapport du vill skapa och klickar på **[!UICONTROL Next]**.

   ![Välj rapporttyp](assets/choose_report.png)

   >[!NOTE]
   >
   >Som standard inkluderas innehållsfragment och länkdelningar i resursen [!UICONTROL Downloaded report]. Välj lämpligt alternativ för att skapa en rapport över länkdelningar eller för att exkludera innehållsfragment från hämtningsrapporten.

   >[!NOTE]
   >
   >The [!UICONTROL Download] rapporten visar endast information om de resurser som har valts individuellt och som har hämtats eller hämtats med Snabbåtgärd. Den innehåller dock inte information om resurserna som fanns i en hämtad mapp.

1. Konfigurera rapportinformation som titel, beskrivning, miniatyrbild och mappsökväg i CRX-databasen där rapporten lagras. Som standard är mappsökvägen `/content/dam`. Du kan ange en annan sökväg.

   ![Sida för att lägga till rapportinformation](assets/report_configuration.png)

   Välj datumintervall för rapporten.

   Du kan välja att generera rapporten nu eller vid ett framtida datum och tid.

   >[!NOTE]
   >
   >Om du väljer att schemalägga rapporten senare måste du ange datum och tid i fälten Datum och Tid. Om du inte anger något värde behandlas det som en rapport som ska genereras omedelbart.

   Konfigurationsfälten kan variera beroende på vilken typ av rapport du skapar. Till exempel **[!UICONTROL Disk Usage]** rapporten innehåller alternativ för att inkludera resursåtergivningar när du beräknar det diskutrymme som används av resurserna. Du kan välja att inkludera eller exkludera resurser i undermappar för beräkning av diskanvändning.

   >[!NOTE]
   >
   >Rapporten **[!UICONTROL Disk Usage]** innehåller inga fält för datumintervall eftersom den endast visar hur mycket diskutrymme som används.

   ![Sidan Information om rapporten Diskanvändning](assets/disk_usage_configuration.png)

   När du skapar **[!UICONTROL Files]** kan du inkludera/exkludera undermappar. Du kan dock inte inkludera resursåtergivningar för den här rapporten.

   ![Detaljsida för rapporten Filer](assets/files_report.png)

   I rapporten **[!UICONTROL Link Share]** visas URL:er till resurser som delas med externa användare inifrån [!DNL Assets]. Den innehåller e-post-ID:n för den användare som delat resurserna, e-post-ID:n för de användare som resurserna delas med, delningsdatum och utgångsdatum för länken. Det går inte att anpassa kolumnerna.

   The **[!UICONTROL Link Share]** , innehåller inga alternativ för undermappar och återgivningar eftersom den bara publicerar de delade URL:er som visas under `/var/dam/share`.

   ![Detaljsida för länkdelningsrapport](assets/link_share.png)

1. Klicka på **[!UICONTROL Next]** i verktygsfältet.

1. I **[!UICONTROL Configure Columns]** på sidan är vissa kolumner markerade för att visas i rapporten som standard. Du kan markera fler kolumner. Avmarkera en markerad kolumn om du vill utesluta den i rapporten.

   ![Markera eller avmarkera rapportkolumner](assets/configure_columns.png)

   Om du vill visa ett anpassat kolumnnamn eller en egenskapssökväg konfigurerar du egenskaperna för resursens binärfil under `jcr:content` nod i CRX. Du kan också lägga till den via egenskapssökvägsväljaren.

   ![Markera eller avmarkera rapportkolumner](assets/custom_columns.png)

1. Klicka på **[!UICONTROL Create]** i verktygsfältet. Ett meddelande meddelar att rapportgenereringen har initierats.
1. På [!UICONTROL Asset Reports] sidan, baseras rapportgenereringsstatusen på rapportjobbets aktuella tillstånd, till exempel [!UICONTROL Success], [!UICONTROL Failed], [!UICONTROL Queued], eller [!UICONTROL Scheduled]. Samma status visas i inkorgen för meddelanden.Om du vill visa rapportsidan klickar du på rapportlänken. Du kan också markera rapporten och klicka på **[!UICONTROL View]** i verktygsfältet.

   ![En genererad rapport](assets/report_page.png)

   Klicka **[!UICONTROL Download]** i verktygsfältet för att hämta rapporten i CSV-format.

## Lägg till anpassade kolumner {#add-custom-columns}

Du kan lägga till anpassade kolumner i följande rapporter om du vill visa mer data för dina anpassade krav:

* Överför
* Hämta
* Förfaller
* Ändring
* Publicera
* [!DNL Brand Portal] publicera
* Filer

Följ de här stegen för att lägga till anpassade kolumner i de här rapporterna:

1. I [!DNL Manager interface], klicka **[!UICONTROL Tools]** > **[!UICONTROL Assets]** > **[!UICONTROL Reports]**.
1. På [!UICONTROL Asset Reports] sida, klicka **[!UICONTROL Create]** i verktygsfältet.

1. Från **[!UICONTROL Create Report]** väljer du den rapport du vill skapa och klickar på **[!UICONTROL Next]**.
1. Konfigurera rapportinformation som titel, beskrivning, miniatyrbild, mappsökväg och datumintervall.

1. Om du vill visa en anpassad kolumn anger du namnet på kolumnen under **[!UICONTROL Custom Columns]**.

   ![Ange namn för anpassad rapportkolumn](assets/custom_columns-1.png)

1. Lägg till egenskapssökvägen under `jcr:content` nod i CRXDE med egenskapssökvägsväljaren. Du kan också skriva sökvägen i fältet för egenskapssökväg.

   ![Mappa egenskapssökvägen från banor i jcr:content](assets/property_picker.png)

   Du kan också skriva sökvägen i fältet för egenskapssökväg.

   ![property_path](assets/property_path.png)

   Om du vill lägga till fler anpassade kolumner klickar du på **[!UICONTROL Add]** och upprepa steg 5 och 6.

1. Klicka på **[!UICONTROL Create]** i verktygsfältet. Ett meddelande meddelar att rapportgenereringen har initierats.

## Konfigurera rensningstjänst {#configure-purging-service}

Om du vill ta bort rapporter som du inte längre behöver konfigurerar du tjänsten DAM Report Renge från webbkonsolen så att befintliga rapporter rensas baserat på antal och ålder.

1. Gå till webbkonsolen (konfigurationshanteraren) från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL DAM Report Purge Service]** konfiguration.
1. Ange frekvens (tidsintervall) för rensningstjänsten i `scheduler.expression.name` fält. Du kan också konfigurera åldern och tröskelvärdet för antal rapporter.
1. Spara ändringarna.
