---
title: Allmänna steg för anpassning av arbetsytan i AEM Forms
seo-title: Allmänna steg för anpassning av arbetsytan i AEM Forms
description: Hur man kommer igång med att anpassa gränssnittet för arbetsytan i AEM Forms.
seo-description: Hur man kommer igång med att anpassa gränssnittet för arbetsytan i AEM Forms.
uuid: 555b5039-cd68-4090-8a8f-30b654474f55
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 54326a05-3fb0-4111-a6ec-230b6473052e
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f

---


# Allmänna steg för anpassning av arbetsytan i AEM Forms {#generic-steps-for-aem-forms-workspace-customization}

De allmänna stegen för att utföra anpassningar är:

1. Logga in på CRXDE Lite med åtkomst `https://[server]:[port]/lc/crx/de/index.jsp`.
1. Skapa en mapp med namnet `ws`at `/apps`om den inte finns. Klicka på **[!UICONTROL Spara alla]**.
1. Bläddra till `/apps/ws`och navigera till fliken **[!UICONTROL Åtkomstkontroll]** .
1. Klicka **[!UICONTROL +]** i listan **[!UICONTROL Åtkomstkontroll]** för att lägga till en ny post. Klicka **[!UICONTROL +]** igen.
1. Sök efter och markera **[!UICONTROL PERM_WORKSPACE_USER]** Principal.

   ![Välj PERM_WORKSPACE_USER som en del av de allmänna stegen för att anpassa HTML-arbetsytan](assets/perm_workspace_user.png)

1. Ge huvudmannen `jcr:read` privilegium.
1. Klicka på **[!UICONTROL Spara alla]**.
1. Kopiera `GET.jsp` och `html.jsp`filer från `/libs/ws`mappen till `/apps/ws` mappen.
1. Kopiera `/libs/ws/locales` mappen i `/apps/ws` mappen. Klicka på **[!UICONTROL Spara alla]**.
1. Uppdatera referenserna och de relativa sökvägarna i `GET.jsp` filen, så som visas nedan, och klicka på **[!UICONTROL Spara alla]**.

   ```
   <meta http-equiv="refresh" content="0;URL='/lc/apps/ws/index.html'" />
   ```

1. Gör följande för CSS-anpassningar:

   1. Navigera till `/apps/ws` mappen och skapa en ny mapp med namnet `css`.
   1. Skapa en ny fil med namnet `css`i `newStyle.css`mappen.
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

   1. Skapa en mapp med namnet `js`at `/apps/ws`. Klicka på **[!UICONTROL Spara alla]**.
   1. Skapa en mapp med namnet `libs`at `/apps/ws/js`. Klicka på **[!UICONTROL Spara alla]**.
   1. Skapa en mapp med namnet `jqueryui`at `/apps/ws/js/libs`. Klicka på **[!UICONTROL Spara alla]**.
   1. Kopiera `/libs/ws/js/libs/jqueryui/jquery.ui.datepicker-ja.js` till `/apps/ws/js/libs/jqueryui`. Klicka på **[!UICONTROL Spara alla]**.

1. Gör följande för HTML-anpassningar:

   1. Under `/apps/ws/js`skapar du en mapp med namnet `runtime`. Klicka på **[!UICONTROL Spara alla]**.
   1. Under `/apps/ws/js/runtime`skapar du en mapp med namnet `templates`. Klicka på **[!UICONTROL Spara alla]**.
   1. Kopiera `/libs/ws/js/main.js` till `/apps/ws/js/main.js`.
   1. Kopiera /libs/ws/js/registry.js till `/apps/ws/js/registry.js`.

1. Klicka på **[!UICONTROL Spara alla]**, rensa cache och uppdatera arbetsytan i AEM Forms.

   Gå till URL:en `https://[server]:[port]/lc/ws` och logga in med administratörs-/lösenordsinformation. Webbläsaren dirigeras om till `https://[server]:[port]/lc/apps/ws/index.html`.

