---
title: Anpassa flikar för en uppgift
seo-title: Customizing tabs for a task
description: Anpassa namnen på flikarna för dina uppgifter på arbetsytan i LiveCycle AEM Forms.
seo-description: How-to customize the names of the tabs for your tasks, in LiveCycle AEM Forms workspace.
uuid: 77eabb63-f8ea-4ec0-8a41-b51c65cdecc0
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: ac0a281f-f589-4a70-9bc7-1a23e054b02f
exl-id: 42671435-e0f0-41db-af83-182b01742954
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 0%

---

# Anpassa flikar för en uppgift {#customizing-tabs-for-a-task}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan anpassa tabbnamn för `Start Process` i `Start Process` Användarvy och `Task Details` i `ToDo` Användarvy.

1. Följ [Allmänna steg för anpassning av AEM Forms arbetsyta](/help/forms/using/generic-steps-html-workspace-customization.md).
1. Ändra värdet för `tabname`i `translation.json` -fil.

   Ändra till exempel `/apps/ws/locales/en-US/translation.json` för engelska till följande:

   * Använd följande utdrag från `"startprocess" : {}` -block.

   ```
   "tabname" : {
               "form" : "Application",
               "details" : "Overview",
               "attachments" : "Attachments",
               "notes" : "Helper Notes"
           }
   ```

   * Använd följande kodutdrag från `"todo" : {}` -block.

   ```
   "tabname" : {
               "summary" : "Bird's-eye view",
               "history" : "Past",
               "form" : "Form",
               "details" : "Overview",
               "attachments" : "Attachments",
               "notes" : "Notes"
   }
   ```

   >[!NOTE]
   >
   >Lägg till motsvarande nyckelvärdepar för alla språk som stöds.
