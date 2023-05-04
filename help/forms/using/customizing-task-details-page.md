---
title: Anpassa sidan med uppgiftsinformation
seo-title: Customizing the task details page
description: Anpassa informationssidan i AEM Forms arbetsyta för att ändra standardinformationen som visas för en uppgift.
seo-description: How-to customize the task details page in AEM Forms workspace to modify the default information displayed about a task.
uuid: d85fae55-8e66-4595-8560-5485622b6841
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 16e57cf6-aaa1-406d-a6ad-71ec60b15386
exl-id: de97e6f7-25bf-462b-b67d-0d3fbd86a321
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# Anpassa sidan med uppgiftsinformation {#customizing-the-task-details-page}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Sidan med uppgiftsinformation innehåller information om en uppgift och dess processer. Du kan dock anpassa informationssidan för att lägga till eller ta bort information.

Du kan lägga till följande information på informationssidan:

* Information som är tillgänglig i JSON-objektet för en uppgift (Uppgiftsavsnitt i [JSON-objektbeskrivning för arbetsytan i AEM Forms](/help/forms/using/html-workspace-json-object-description.md))
* Information tillgänglig i JSON-objektet för en processinstans (processinstansavsnitt i [JSON-objektbeskrivning för arbetsytan i AEM Forms](/help/forms/using/html-workspace-json-object-description.md))

Så här anpassar du informationssidan:

1. Följ [Allmänna steg för anpassning av AEM Forms arbetsyta.](/help/forms/using/generic-steps-html-workspace-customization.md)
1. Om du vill visa ytterligare information lägger du till motsvarande nyckelvärdepar i `translation.json` fil på `todo`block > `details`block > `app`block > [ `required`block].

   The [ `required`block] refererar till tillgängliga block, t.ex. uppgiftsblocket för uppgiftsinformation, processblock för processinformation och aktuellt väntande uppgiftsblock för information om väntande uppgifter.

   Om du till exempel vill lägga till information om val av väg krävs på sidan med uppgiftsinformation kan du lägga till följande nyckelvärdepar i åtgärdsblocket:

   ```
   "todo" : {
       .
       .
       .
       "details" : {
           .
           .
           "task" : {
               .
               .
               "RouteSelectionRequired" : "Route Selection Required"
           }
       }
   }
   ```

   >[!NOTE]
   >
   >Lägg till motsvarande nyckelvärdepar för alla språk som stöds.

1. Kopiera `/libs/ws/js/runtime/templates/taskdetails.html` till `/apps/ws/js/runtime/templates/taskdetails.html`.

   Lägg till ny information i `/apps/ws/js/runtime/templates/taskdetails.html`. Till exempel:

   ```css
   <div class="detailsContainer">
       .
       .
       <ul>
           .
           .
           <li>
               <label for="routeSelectionRequired" title="<%= $.t('todo.details.task.RouteSelectionRequired')%>"><%= $.t('todo.details.task.RouteSelectionRequired')%></label>
               <div>
                   <span id="routeSelectionRequired"><%= isRouteSelectionRequired != null ? isRouteSelectionRequired : ''%></span>
               </div>
           </li>
           .
           .
       </ul>
   </div>
   ```

1. Öppna /apps/ws/js/registry.js för redigering.

   Söka och ersätta `text!/lc/libs/ws/js/runtime/templates/taskdetails.html` med `text!/lc/apps/ws/js/runtime/templates/taskdetails.html`.

>[!NOTE]
>
>Om du vill anpassa uppgiftsinformationssidan med uppgifter som har skapats på fliken **Starta process **på arbetsytan i AEM Forms lägger du till den nya informationen i `/apps/ws/js/runtime/templates/startprocess.html`.
>
>Om du vill lägga till nya format för informationen som lagts till på informationssidan ändrar du CSS-filen med hjälp av *Ändringar i användargränssnittet* avsnitt i [Anpassa arbetsytan](/help/forms/using/changing-locale-user-interface.md).
