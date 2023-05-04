---
title: Allmänna steg för anpassning av AEM Forms arbetsyta
seo-title: Generic steps for AEM Forms workspace customization
description: Hur man kommer igång med att anpassa användargränssnittet i AEM Forms arbetsyta.
seo-description: How to get started customizing AEM Forms workspace user interface.
uuid: 555b5039-cd68-4090-8a8f-30b654474f55
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 54326a05-3fb0-4111-a6ec-230b6473052e
exl-id: 2c0dab68-d77e-46fb-832d-90edea510750
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 3%

---

# Allmänna steg för anpassning av AEM Forms arbetsyta {#generic-steps-for-aem-forms-workspace-customization}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

De allmänna stegen för att utföra anpassningar är:

1. Logga in på CRXDE Lite med åtkomst `https://[server]:[port]/lc/crx/de/index.jsp`.
1. Skapa en mapp med namnet `ws`på `/apps`, om den inte finns. Klicka på **[!UICONTROL Save All]**.
1. Bläddra till `/apps/ws`och navigera till **[!UICONTROL Access Control]** -fliken.
1. I **[!UICONTROL Access Control]** lista, klicka på **[!UICONTROL +]** för att lägga till en ny post. Klicka **[!UICONTROL +]** igen.
1. Sök och välj **[!UICONTROL PERM_WORKSPACE_USER]** Huvudman.

   ![Välj PERM_WORKSPACE_USER som en del av de allmänna stegen för att anpassa arbetsytan i HTML](assets/perm_workspace_user.png)

1. Ge `jcr:read` Privilegium till rektorn.
1. Klicka på **[!UICONTROL Save All]**.
1. Kopiera `GET.jsp` och `html.jsp`filer från `/libs/ws`mapp till `/apps/ws` mapp.
1. Kopiera `/libs/ws/locales` i `/apps/ws` mapp. Klicka på **[!UICONTROL Save All]**.
1. Uppdatera referenserna och de relativa sökvägarna i `GET.jsp` som visas nedan och klicka på **[!UICONTROL Save all]**.

   ```
   <meta http-equiv="refresh" content="0;URL='/lc/apps/ws/index.html'" />
   ```

1. Gör följande för CSS-anpassningar:

   1. Navigera till `/apps/ws` och skapa en ny mapp med namnet `css`.
   1. I `css`mapp, skapa en ny fil med namnet `newStyle.css`.
   1. Öppna `/apps/ws/html`.jsp och ändra från

   ```css
   <link lang="en" rel="stylesheet" type="text/css" href="css/style.css" />
   <link lang="en" rel="stylesheet" type="text/css" href="css/jquery-ui.css"/>
   ```

   till

   ```css
   <link lang="en" rel="stylesheet" type="text/css" href="../../libs/ws/css/style.css" />
   <link lang="en" rel="stylesheet" type="text/css" href="css/newStyle.css" />
   <link lang="en" rel="stylesheet" type="text/css" href="../../libs/ws/css/jquery-ui.css"/>
   ```

   >[!NOTE]
   >
   >Placera den användardefinierade CSS-filen efter posten newStyle.css, som visas ovan.

1. I /apps/ws/html.jsp

   ```css
   <script data-main="js/main" src="js/libs/require/require.js"></script>
   ```

   till

   ```css
   <script data-main="js/main" src="../../libs/ws/js/libs/require/require.js"></script>
   ```

1. Gör följande:

   1. Skapa en mapp med namnet `js`på `/apps/ws`. Klicka på **[!UICONTROL Save All]**.
   1. Skapa en mapp med namnet `libs`på `/apps/ws/js`. Klicka på **[!UICONTROL Save All]**.
   1. Skapa en mapp med namnet `jqueryui`på `/apps/ws/js/libs`. Klicka på **[!UICONTROL Save All]**.
   1. Kopiera `/libs/ws/js/libs/jqueryui/jquery.ui.datepicker-ja.js` till `/apps/ws/js/libs/jqueryui`. Klicka på **[!UICONTROL Save All]**.

1. Gör följande för anpassning av HTML:

   1. Under `/apps/ws/js`, skapa en mapp med namnet `runtime`. Klicka på **[!UICONTROL Save All]**.
   1. Under `/apps/ws/js/runtime`, skapa en mapp med namnet `templates`. Klicka på **[!UICONTROL Save All]**.
   1. Kopiera `/libs/ws/js/main.js` till `/apps/ws/js/main.js`.
   1. Kopiera /libs/ws/js/registry.js till `/apps/ws/js/registry.js`.

1. Klicka **[!UICONTROL Save All]**, rensa cacheminne och uppdatera AEM Forms arbetsyta.

   Öppna URL:en `https://[server]:[port]/lc/ws` och logga in med inloggningsuppgifter för administratör/lösenord. Webbläsaren omdirigeras till `https://[server]:[port]/lc/apps/ws/index.html`.
