---
title: Uppdaterar länken till dokumentationen
seo-title: Updating the link to the documentation
description: Så här uppdaterar du målet för hjälplänken för arbetsytan i AEM Forms så att den pekar på den anpassade dokumentationslänken.
seo-description: How-to update the destination of Workspace Help link in AEM Forms workspace to point to your custom documentation link.
uuid: 64056d10-1451-44ed-8f25-81a21037dc75
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 788c427f-190f-4580-9efd-6a4c4a008837
exl-id: 68fe3f97-ded8-4223-b4b9-02704077e37e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# Uppdaterar länken till dokumentationen {#updating-the-link-to-the-documentation}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kommer åt standardhjälpinnehållet för AEM Forms genom att välja **Hjälp > Hjälp för arbetsytan**. Den hänvisar till onlinedokumentationen på Adobe webbplats. Du kan dock uppdatera den så att den pekar på en annan URL.

Här följer några exempel på hur du kan ändra standardhjälpens URL: n:

* För att få hjälp på valfritt språk.
* Skräddarsy hjälpmaterial för en skräddarsydd arbetsyta.

Följ webbadressen för onlinedokumentationen för att uppdatera webbadressen [Allmänna anpassningssteg](/help/forms/using/generic-steps-html-workspace-customization.md) och därefter följande steg.

1. Kopiera `userinfo.html` fil från `/libs/ws/js/runtime/templates` till `/apps/ws/js/runtime/templates`.
1. Ändra:

   ```
   <ul class="helpmenu">
     <li>            
       <a href="https://www.adobe.com/go/learn_aemforms_documentation_63" title="<%= $.t('index.header.dropdown.WorkspaceHelp')%>" target="_blank"><%= $.t('index.header.dropdown.WorkspaceHelp')%></a>
     </li>
   ```

   till

   ```
   <ul class="helpmenu">
     <li>            
       <a href="<!--place new help url here-->" title="<%= $.t('index.header.dropdown.WorkspaceHelp')%>" target="_blank"><%= $.t('index.header.dropdown.WorkspaceHelp')%></a>
     </li>
   ```

1. Gör följande:

   1. Öppna /apps/ws/js/registry.js för redigering.
   1. Söka och ersätta `text!/lc/libs/ws/js/runtime/templates/userinfo.html` med `text!/lc/apps/ws/js/runtime/templates/userinfo.html`.
