---
title: Konfigurera resursinsikter
description: Lär dig hur du konfigurerar tillgångsinsikter i AEM Assets.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---


# Konfigurera resursinsikter {#configuring-asset-insights}

Adobe Experience Manager (AEM) Assets hämtar användningsdata runt AEM resurser som används av tredjepartswebbplatser från Adobe Analytics. Om du vill att tillgångsinsikter ska kunna hämta dessa data och generera insikter måste du först konfigurera funktionen så att den integreras med Adobe Analytics.

>[!NOTE]
>
>Insikter stöds endast och tillhandahålls för bilder.

1. Klicka på AEM **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-210](assets/chlimage_1-210.png)

1. Klicka på **[!UICONTROL Insights Configuration]** kortet.
1. Välj ett datacenter i guiden och ange dina autentiseringsuppgifter, inklusive namnet på organisationen, användarnamnet och lösenordet.

   ![chlimage_1-211](assets/insights_config2.png)

1. Klicka/tryck på **[!UICONTROL Authenticate]**.
1. När AEM har autentiserat dina inloggningsuppgifter väljer du en Adobe Analytics-rapportsvit från den plats där du vill att tillgångsinsikter ska hämta data. **[!UICONTROL Report Suite]** Klicka på **[!UICONTROL Add]**.
1. När AEM har konfigurerat rapportsviten klickar/trycker du **[!UICONTROL Done]**.

## Sidspårare {#page-tracker}

När du har konfigurerat ditt Analytics-konto genereras sidspårningskoden åt dig. Om du vill göra det möjligt för Assets Insights att spåra AEM resurser som används på tredjepartswebbplatser, inkluderar du sidspårningskoden i webbplatskoden. Använd verktyget Sidspårare i AEM Assets för att generera sidspårningskod. Mer information om hur du inkluderar Page Tracker-kod i tredjepartswebbsidor finns i [Använda sidspåraren och bädda in kod på webbsidor](touch-ui-using-page-tracker.md).

1. I AEM klickar du på **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-214](assets/chlimage_1-214.png)

1. På **[!UICONTROL Navigation]** sidan klickar du på **[!UICONTROL Insights Page Tracker]** kortet.
1. Klicka på **[!UICONTROL Download]** ikonen för att hämta sidspårningskod.