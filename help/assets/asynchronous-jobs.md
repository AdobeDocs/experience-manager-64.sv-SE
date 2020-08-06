---
title: Konfigurera asynkrona åtgärder i [!DNL Adobe Experience Manager].
description: Slutför asynkront vissa resurskrävande uppgifter för att optimera prestandan i [!DNL Experience Manager Assets].
contentOwner: AG
translation-type: tm+mt
source-git-commit: f6aa1ab2c7a0ddeda1504e95ce4bd57fe74a65fd
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 21%

---


# Asynchronous operations {#asynchronous-operations}

För att minska den negativa inverkan på prestanda behandlar [!DNL Adobe Experience Manger Assets] vissa långvariga och resurskrävande resursoperationer asynkront. Asynkron bearbetning innebär att du måste placera flera uppgifter i kö och sedan utföra dem på ett seriellt sätt beroende på om det finns systemresurser tillgängliga. Dessa åtgärder omfattar:

* Att ta bort många resurser..
* Flytta många resurser eller resurser med många referenser.
* Exportera och importera resursmetadata i grupp.

Du kan visa status för asynkrona uppgifter från **[!UICONTROL Async Job Status]** sidan.

>[!NOTE]
>
>Som standard körs åtgärderna [!DNL Assets] parallellt. If `N` is the number of CPU cores, `N/2` tasks can execute in parallel, by default. Om du vill använda anpassade inställningar för uppgiftskön ändrar du **[!UICONTROL Async Operation Default Queue]** konfigurationen från [!UICONTROL Web Console]. Mer information finns i [konfigurationer av kön](https://sling.apache.org/documentation/bundles/apache-sling-eventing-and-job-handling.html#queue-configurations).

## Monitor the status of asynchronous operations {#monitoring-the-status-of-asynchronous-operations}

Whenever [!DNL Assets] processes an operation asynchronously, you receive a notification in your [!DNL Experience Manager] [Inbox](/help/sites-authoring/inbox.md) and via an email. Gå till sidan **[!UICONTROL Async Job Status]** för att se detaljerad status gällande asynkrona åtgärder.

1. In the [!DNL Experience Manager] interface click **[!UICONTROL Operations]** > **[!UICONTROL Jobs]**.

1. Granska informationen om åtgärderna på sidan **[!UICONTROL Async Job Status]**.

   ![Status och information om asynkrona åtgärder](assets/job_status.png)

   Information om förloppet för en åtgärd finns i **[!UICONTROL Status]** kolumnen. Beroende på förloppet visas ett av följande statusvärden:

   * **[!UICONTROL Active]**: åtgärden bearbetas.
   * **[!UICONTROL Success]**: åtgärden har slutförts.
   * **[!UICONTROL Fail]** eller **[!UICONTROL Error]**: det gick inte att bearbeta åtgärden.
   * **[!UICONTROL Scheduled]**: åtgärden är schemalagd för bearbetning vid ett senare tillfälle.

1. To stop an active operation, select it from the list and click **[!UICONTROL Stop]** ![stop icon](assets/do-not-localize/stop_icon.svg) from the toolbar.

1. To view extra details, for example description and logs, select the operation and click **[!UICONTROL Open]** ![open_icon](assets/do-not-localize/edit_icon.svg) from the toolbar. Sidan med aktivitetsinformation visas.

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

1. In the [!DNL Experience Manager] interface click **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Öppna **[!UICONTROL Adobe CQ DAM Async Jobs Purge Scheduled]** uppgiften.
1. Ange tröskelvärdet för antal dagar efter vilka slutförda uppgifter tas bort och det högsta antalet uppgifter som detaljerna sparas för i historiken. Spara ändringarna.

   ![Konfiguration som schemalägger rensning av asynkrona uppgifter](assets/purge_job.png)

## Konfigurera tröskelvärde för asynkrona borttagningsåtgärder {#configure-thresholds-for-asynchronous-delete-operations}

Om antalet resurser eller mappar som ska tas bort överstiger det angivna tröskelvärdet, utförs borttagningsåtgärden asynkront.

1. In the [!DNL Experience Manager] interface click **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Öppna [!UICONTROL Web Console]konfigurationen från **[!UICONTROL Async Delete Operation Job Processing]** .
1. I **[!UICONTROL Threshold number of assets]** rutan anger du tröskelvärden för att ta bort resurser, mappar eller referenser asynkront. Spara ändringarna.

   ![Ange tröskelgräns för när resurser ska tas bort för aktiviteten](assets/delete_threshold.png)

## Konfigurera tröskelvärde för asynkrona flyttåtgärder {#configure-thresholds-for-asynchronous-move-operations}

Om antalet resurser, mappar eller referenser som ska flyttas överstiger det angivna tröskelvärdet, utförs flyttåtgärden asynkront.

1. In the [!DNL Experience Manager] interface, click **[!UICONTROL Tools]** > **[!UICONTROL Operations]** > **[!UICONTROL Web Console]**.
1. Öppna [!UICONTROL Web Console]konfigurationen från **[!UICONTROL Async Move Operation Job Processing]** .
1. I **[!UICONTROL Threshold number of assets/references]** rutan anger du tröskelvärden för att flytta resurser, mappar eller referenser asynkront. Spara ändringarna.

   ![Ange tröskelgräns för när resurser ska flyttas för aktiviteten](assets/move_threshold.png)

>[!MORELIKETHIS]
>
>* [Konfigurera e-post i Experience Manager](/help/sites-administering/notification.md).
>* [Importera och exportera resursers metadata gruppvis](/help/assets/metadata-import-export.md).

