---
title: Temaanpassning
seo-title: Theme Customization
description: Så här anpassar du temat i din AEM Forms-app.
seo-description: How to customize the theme of your AEM Forms app.
uuid: 36632e67-1cc6-416d-ae80-d84bbabab4bd
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: c72f608e-052a-4bf9-b7bc-ddf57483af35
exl-id: fb1e0bec-c943-4468-920d-8ef360a01365
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '259'
ht-degree: 0%

---

# Temaanpassning {#theme-customization}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan anpassa HTML-koden och CSS-filen för att ge AEM Forms-appen ett distinkt organisationsspecifikt utseende. Du kan till exempel ändra bakgrundsfärgen och höjden på uppgifter eller startpunkter. I följande exempel finns instruktioner för hur du ändrar:

* visningsanvisningar i stället för beskrivningen
* antal visningsrutter
* bakgrundsövertoningsfärg

## Steg {#steps}

1. Öppna projektet.

   * För iOS, öppna `Capture.xcodeproj` i Xcode
   * För Android öppnar du Android-projektet i Eclipse.
   * För Windows: öppna `MWSWindows.sln` i Visual Studio.

1. Navigera till mappen Mallar.

   * I Xcode navigerar du till **Capture > www > wsmoble > js > runtime > templates** mapp.
   * I Eclipse navigerar du till **assets > www > wsmoble > js > runtime > templates** mapp.
   * I Visual Studio går du till **MWSWindows > www > wsmoble > js > runtime > templates** mapp.

1. Öppna `template.html` fil för redigering.
1. Leta reda på följande sträng:

   ```
   <%if ( (task.description !== "") && (task.description !== null) && (typeof task.description !== null) && (typeof task.description !== 'undefined') ) {%>
                  <div class="description_details">
                    <%= task.description %>
                  </div>
                 <%} else 
   ```

   Ersätt den med `<%`.

1. Leta reda på följande kod i `template.html` fil:

   ```
   <ul id="task_menu_list">
                                   <li class="approve" title="<%= task.availableCommands.directCommands[0]%>" data-routename="<%= task.availableCommands.directCommands[0]%>">
                                       <%= task.availableCommands.directCommands[0]%>
                                   </li>
                                   <li class="reject last" title="<%= task.availableCommands.directCommands[1]%>" data-routename="<%= task.availableCommands.directCommands[1]%>">
                                       <%= task.availableCommands.directCommands[1]%>
                                   </li>
   ```

1. Kommentera följande rad och spara filen.

   ```
   task.availableCommands.directCommands[1]%>">
   <%= task.availableCommands.directCommands[1]%>
   </li>
   ```

1. Navigera till css-mappen.

   * I Xcode navigerar du till **Capture > www > wsmoble > css**.
   * I Eclipse navigerar du till **assets > www > wsmoble > css**.
   * I Visual Studio går du till **MWSWindows > www > wsmoble > css**.

1. Öppna `_style.css` fil för redigering.
1. För bakgrundsbild ändrar du `#323232` till `#fff`.
1. Spara ändringarna och stäng `_style.css` -fil.
1. Öppna appen AEM Forms.

   Nu visas instruktioner i stället för beskrivningar i AEM Forms-appen.
