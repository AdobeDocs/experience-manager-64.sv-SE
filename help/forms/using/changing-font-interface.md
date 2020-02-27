---
title: Ändra teckensnitt i gränssnittet
seo-title: Ändra teckensnitt i gränssnittet
description: Så här ändrar du teckensnitt i användargränssnittet selektivt.
seo-description: Så här ändrar du teckensnitt i användargränssnittet selektivt.
uuid: d079f656-76f8-4908-9989-dde79e215eb2
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 487e3966-443a-408e-b5af-899fcba6fca6
translation-type: tm+mt
source-git-commit: 8cbfa421443e62c0483756e9d5812bc987a9f91d

---


# Ändra teckensnitt i gränssnittet {#changing-the-font-on-the-interface}

Du kan ändra teckensnittet som visas på arbetsytan i AEM Forms. Teckensnitt som används i ett visst avsnitt i användargränssnittet definieras i motsvarande avsnitt i formatmallen. Du kan ändra teckensnitten i användargränssnittet selektivt.

Följ de [allmänna stegen för anpassning](/help/forms/using/generic-steps-html-workspace-customization.md) av arbetsytan i AEM Forms och följ stegen för anpassning av CSS, HTML eller båda, beroende på dina behov.

1. Ändra eller lägg till teckensnittsfamiljen i en befintlig stil.
1. Ändra eller lägg till infogad teckensnittsfamilj för HTML-elementet.
1. Lägg till ett format och använd det för HTML-elementet.

Om du till exempel vill ändra teckensnittet för den översta navigeringsfältets ankartext till Courier New följer du de här stegen:

1. Logga in på CRXDE Lite med åtkomst `https://[server]:[port]/lc/crx/de/index.jsp`.
1. Gör något av följande:

   1. Om du vill ändra font-family i en befintlig stil lägger du till följande i filen newStyle.css på /apps/ws/css.

      ```css
      #topnav a {
         font-family: "Courier New";
      }
      ```

   1. Om du vill lägga till teckensnittsfamiljen för HTML-elementet kopierar du filen till `/libs/ws/js/runtime/templates/appnavigation.html` `/apps/ws/js/runtime/templates/appnavigation.html`.

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

      Lägg till följande i filen appnavigation.html på /apps/ws/js/runtime/templates om du vill lägga till teckensnittsfamiljen för HTML-elementet.

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

![](assets/change_font_before.png) change_font_before **** Figure: Övre *navigeringsfältet före teckensnittsanpassning*

![](assets/change_font_after.png) change_font_after **** Figure: Övre *navigeringsfältet efter teckensnittsanpassning för den första fliken*

[Kontakta supporten](https://www.adobe.com/account/sign-in.supportportal.html)
