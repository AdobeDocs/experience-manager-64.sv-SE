---
title: Konfigurera resursinsikter
description: Lär dig hur du konfigurerar Assets Insights i AEM Assets.
contentOwner: AG
feature: Resursinsikter,Resursrapporter
role: User,Admin
exl-id: b0d62dd3-1868-4d73-95f7-3d6c3ff474d9
source-git-commit: 5d96c09ef764b02e08dcdf480da1ee18f4d9a30c
workflow-type: tm+mt
source-wordcount: '225'
ht-degree: 2%

---

# Konfigurera resursinsikter {#configuring-asset-insights}

Adobe Experience Manager (AEM) Assets hämtar användningsdata runt AEM resurser som används av tredjepartswebbplatser från Adobe Analytics. Om du vill att Assets Insights ska kunna hämta data och generera insikter måste du först konfigurera funktionen så att den integreras med Adobe Analytics.

>[!NOTE]
>
>Insikter stöds endast och tillhandahålls för bilder.

1. Klicka på **[!UICONTROL Tools > Assets]** i AEM.

   ![chlimage_1-210](assets/chlimage_1-210.png)

1. Klicka på **[!UICONTROL Insights Configuration]**-kortet.
1. Välj ett datacenter i guiden och ange dina autentiseringsuppgifter, inklusive namnet på organisationen, användarnamnet och lösenordet.

   ![chlimage_1-211](assets/insights_config2.png)

1. Klicka/tryck på **[!UICONTROL Authenticate]**.
1. När AEM har autentiserat dina inloggningsuppgifter väljer du en Adobe Analytics-rapportsserie från **[!UICONTROL Report Suite]**-listan där du vill att Assets Insights ska hämta data. Klicka på **[!UICONTROL Add]**.
1. När AEM har konfigurerat rapportsviten klickar/trycker du på **[!UICONTROL Done]**.

## Sidspårare {#page-tracker}

När du har konfigurerat ditt Analytics-konto genereras sidspårningskoden åt dig. Om du vill göra det möjligt för Assets Insights att spåra AEM resurser som används på tredjepartswebbplatser, inkluderar du sidspårningskoden i webbplatskoden. Använd verktyget Sidspårare i AEM Assets för att generera sidspårningskod. Mer information om hur du inkluderar Page Tracker-koden i tredjepartswebbsidor finns i [Använda Page Tracker och bädda in kod i webbsidor](touch-ui-using-page-tracker.md).

1. Klicka på **[!UICONTROL Tools > Assets]** i AEM.

   ![chlimage_1-214](assets/chlimage_1-214.png)

1. Klicka på **[!UICONTROL Insights Page Tracker]**-kortet på sidan **[!UICONTROL Navigation]**.
1. Klicka på ikonen **[!UICONTROL Download]** för att hämta sidspårningskod.
