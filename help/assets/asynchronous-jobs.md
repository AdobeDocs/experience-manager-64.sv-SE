---
title: Konfigurera asynkrona åtgärder i [!DNL Adobe Experience Manager].
description: Slutför asynkront vissa resurskrävande uppgifter för att optimera prestandan i [!DNL Experience Manager Assets].
contentOwner: AG
feature: Asset Management
role: User
exl-id: 0abdfe87-d932-41dd-b1e6-9f5fa5b924fe
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 20%

---

# Asynkrona åtgärder {#asynchronous-operations}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

För att minska negativ påverkan på prestandan [!DNL Adobe Experience Manger Assets] bearbetar vissa långvariga och resurskrävande resursoperationer asynkront. Asynkron bearbetning innebär att du måste placera flera uppgifter i kö och sedan utföra dem på ett seriellt sätt beroende på om det finns systemresurser tillgängliga. Dessa åtgärder omfattar:

* Att ta bort många resurser..
* Flytta många resurser eller resurser med många referenser.
* Exportera och importera resursmetadata i grupp.

Du kan visa status för asynkrona uppgifter från **[!UICONTROL Async Job Status]** sida.

>[!NOTE]
>
>Som standard är [!DNL Assets] uppgifter utförs parallellt. If `N` är antalet processorkärnor, `N/2` uppgifter kan köras parallellt som standard. Om du vill använda anpassade inställningar för uppgiftskön ändrar du **[!UICONTROL Async Operation Default Queue]** från [!UICONTROL Web Console]. Mer information finns i [konfigurationer av kön](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#queue-configurations).

## Övervaka status för asynkrona åtgärder {#monitoring-the-status-of-asynchronous-operations}

När [!DNL Assets] bearbetar en åtgärd asynkront får du ett meddelande i [!DNL Experience Manager] [Inkorg](/help/sites-authoring/inbox.md) och via ett mejl. Gå till sidan **[!UICONTROL Async Job Status]** för att se detaljerad status gällande asynkrona åtgärder.

1. I [!DNL Experience Manager] klicka **[!UICONTROL Operations]** > **[!UICONTROL Jobs]**.

1. Granska informationen om åtgärderna på sidan **[!UICONTROL Async Job Status]**.

   ![Status och information om asynkrona åtgärder](assets/job_status.png)

   Information om hur du kontrollerar förloppet för en åtgärd finns i **[!UICONTROL Status]** kolumn. Beroende på förloppet visas ett av följande statusvärden:

   * **[!UICONTROL Active]**: åtgärden bearbetas.
   * **[!UICONTROL Success]**: åtgärden har slutförts.
   * **[!UICONTROL Fail]** eller **[!UICONTROL Error]**: det gick inte att bearbeta åtgärden.
   * **[!UICONTROL Scheduled]**: åtgärden är schemalagd för bearbetning vid ett senare tillfälle.

1. Om du vill avbryta en aktiv åtgärd markerar du den i listan och klickar på **[!UICONTROL Stop]** ![stoppikon](assets/do-not-localize/stop_icon.svg) i verktygsfältet.

1. Om du vill visa extra information, till exempel beskrivning och loggar, markerar du åtgärden och klickar på **[!UICONTROL Open]** ![open_icon](assets/do-not-localize/edit_icon.svg) i verktygsfältet. Sidan med aktivitetsinformation visas.

   ![Information om en metadataimportaktivitet](assets/job_details.png)

1. Välj **[!UICONTROL Delete]** i verktygsfältet för att ta bort åtgärden från listan. Klicka på **[!UICONTROL Download]** för att ladda ned informationen i en CSV-fil.

   >[!NOTE]
   >
   >Du kan inte ta bort en uppgift om dess status är aktiv eller köad.

## Töm slutförda uppgifter {#purge-completed-tasks}

[!DNL Experience Manager Assets] kör en rensningsåtgärd varje dag i 010 timmar för att ta bort slutförda asynkrona uppgifter som är mer än en dag gamla.

<!-- TBD: Find out from the engineering team and mention the time zone of this 1:00 am task.
-->

Du kan ändra schemat för rensningsaktiviteten och hur länge information om slutförda uppgifter sparas innan de tas bort. Du kan också konfigurera det maximala antalet slutförda uppgifter för vilka information sparas när som helst.

1. I [!DNL Experience Manager] klicka **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Öppna **[!UICONTROL Adobe CQ DAM Async Jobs Purge Scheduled]** uppgift.
1. Ange tröskelvärdet för antal dagar efter vilka slutförda uppgifter tas bort och det högsta antalet uppgifter som detaljerna sparas för i historiken. Spara ändringarna.

   ![Konfiguration som schemalägger rensning av asynkrona uppgifter](assets/purge_job.png)

## Konfigurera tröskelvärde för asynkrona borttagningsåtgärder {#configure-thresholds-for-asynchronous-delete-operations}

Om antalet resurser eller mappar som ska tas bort överstiger det angivna tröskelvärdet, utförs borttagningsåtgärden asynkront.

1. I [!DNL Experience Manager] klicka **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Från [!UICONTROL Web Console]öppnar du **[!UICONTROL Async Delete Operation Job Processing]** konfiguration.
1. I **[!UICONTROL Threshold number of assets]** anger du tröskelvärden för att ta bort resurser, mappar eller referenser asynkront. Spara ändringarna.

   ![Ange tröskelgräns för när resurser ska tas bort för aktiviteten](assets/delete_threshold.png)

## Konfigurera tröskelvärde för asynkrona flyttåtgärder {#configure-thresholds-for-asynchronous-move-operations}

Om antalet resurser, mappar eller referenser som ska flyttas överstiger det angivna tröskelvärdet, utförs flyttåtgärden asynkront.

1. I [!DNL Experience Manager] gränssnitt, klicka **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Från [!UICONTROL Web Console]öppnar du **[!UICONTROL Async Move Operation Job Processing]** konfiguration.
1. I **[!UICONTROL Threshold number of assets/references]** anger du tröskelvärden för att flytta resurser, mappar eller referenser asynkront. Spara ändringarna.

   ![Ange tröskelgräns för när resurser ska flyttas för aktiviteten](assets/move_threshold.png)

>[!MORELIKETHIS]
>
>* [Konfigurera e-post i Experience Manager](/help/sites-administering/notification.md).
>* [Importera och exportera resursers metadata gruppvis](/help/assets/metadata-import-export.md).

