---
title: Ändra teckensnitt i gränssnittet
seo-title: Changing the font on the interface
description: Så här ändrar du teckensnitt i användargränssnittet selektivt.
seo-description: How to change the fonts on the user interface selectively.
uuid: d079f656-76f8-4908-9989-dde79e215eb2
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 487e3966-443a-408e-b5af-899fcba6fca6
exl-id: bd7ec9d6-b1d2-4f01-8cef-05e5e1eceda1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# Ändra teckensnitt i gränssnittet {#changing-the-font-on-the-interface}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan ändra vilket teckensnitt som visas på arbetsytan i AEM Forms. Teckensnitt som används i ett visst avsnitt i användargränssnittet definieras i motsvarande avsnitt i formatmallen. Du kan ändra teckensnitten i användargränssnittet selektivt.

Följ [Allmänna steg för anpassning av AEM Forms arbetsyta](/help/forms/using/generic-steps-html-workspace-customization.md) och beroende på dina behov följer du stegen för att anpassa CSS, HTML eller båda.

1. Ändra eller lägg till teckensnittsfamiljen i en befintlig stil.
1. Ändra eller lägg till teckensnittsfamiljen för elementet HTML.
1. Lägg till ett format och använd det för elementet HTML.

Om du till exempel vill ändra teckensnittet för den översta navigeringsfältets ankartext till Courier New följer du de här stegen:

1. Logga in på CRXDE Lite med åtkomst `https://[server]:[port]/lc/crx/de/index.jsp`.
1. Gör något av följande:

   1. Om du vill ändra font-family i en befintlig stil lägger du till följande i filen newStyle.css på /apps/ws/css.

      ```css
      #topnav a {
         font-family: "Courier New";
      }
      ```

   1. Om du vill lägga till teckensnittsfamiljen för elementet HTML kopierar du `/libs/ws/js/runtime/templates/appnavigation.html` fil till `/apps/ws/js/runtime/templates/appnavigation.html`.

      Uppdatera /apps/ws/js/runtime/templates/appnavigation.html så här:

      ```
      <li class="process"><a href="#" title="<%= $.t('index.header.topnav.startprocess.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.startprocess.name')%></a></li>
      <li class="todo"><a href="#/todo" title="<%= $.t('index.header.topnav.todo.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.todo.name')%></a></li>
      <li class="track"><a href="#/tracking" title="<%= $.t('index.header.topnav.tracking.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.tracking.name')%></a></li>
      <li class="preference"><a href="#/preferences" title="<%= $.t('index.header.topnav.preferences.detail')%>" style="font-family:Courier New;" ><%= $.t('index.header.topnav.preferences.name')%></a></li>
      ```

      Öppna /apps/ws/js/registry.js för redigering och ersättning `text!/lc/libs/ws/js/runtime/templates/appnavigation.html` med `text!/lc/apps/ws/js/runtime/templates/appnavigation.html`.

   1. Om du vill lägga till en stil som definierar teckensnittsfamiljen lägger du till följande i filen newStyle.css på /apps/ws/css.

      ```css
      .myNewFontStyle a {
         font-family: "Courier New";
      }
      ```

      Lägg till följande i filen appnavigation.html på /apps/ws/js/runtime/templates om du vill lägga till teckensnittsfamiljen för elementet HTML.

      ```css
      <div id="topnav" class="myNewFontStyle">
          <ul>
              <li class="process"><a href="#" title="<%= $.t('index.header.topnav.startprocess.detail')%>" ><%= $.t('index.header.topnav.startprocess.name')%></a></li>
              <li class="todo"><a href="#/todo" title="<%= $.t('index.header.topnav.todo.detail')%>"><%= $.t('index.header.topnav.todo.name')%></a></li>
              <li class="track"><a href="#/tracking" title="<%= $.t('index.header.topnav.tracking.detail')%>" ><%= $.t('index.header.topnav.tracking.name')%></a></li>
              <li class="preference"><a href="#/preferences" title="<%= $.t('index.header.topnav.preferences.detail')%>" ><%= $.t('index.header.topnav.preferences.name')%></a></li>
          </ul>
      </div>
      ```

1. Starta om arbetsytan och rensa webbläsarcachen så att ändringarna syns.

![change_font_before](assets/change_font_before.png)
**Bild:** *Övre navigeringsfält före teckensnittsanpassning*

![change_font_after](assets/change_font_after.png)
**Bild:** *Det övre navigeringsfältet efter teckensnittsanpassning på den första fliken*
