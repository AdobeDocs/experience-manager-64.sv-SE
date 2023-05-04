---
title: Konfigurera resursinsikter
description: Lär dig konfigurera resursinsikter i [!DNL Experience Manager] Resurser.
contentOwner: AG
feature: Asset Insights,Asset Reports
role: User,Admin
exl-id: b0d62dd3-1868-4d73-95f7-3d6c3ff474d9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 2%

---

# Konfigurera resursinsikter {#configuring-asset-insights}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets hämtar användningsdata runt [!DNL Experience Manager] resurser som används av tredjepartswebbplatser från Adobe Analytics. Om du vill att Assets Insights ska kunna hämta data och generera insikter måste du först konfigurera funktionen så att den integreras med Adobe Analytics.

>[!NOTE]
>
>Insikter stöds endast och tillhandahålls för bilder.

1. I AEM klickar du på **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-210](assets/chlimage_1-210.png)

1. Klicka på **[!UICONTROL Insights Configuration]** kort.
1. Välj ett datacenter i guiden och ange dina autentiseringsuppgifter, inklusive namnet på organisationen, användarnamnet och lösenordet.

   ![chlimage_1-211](assets/insights_config2.png)

1. Klicka/tryck på **[!UICONTROL Authenticate]**.
1. Efter [!DNL Experience Manager] autentiserar dina inloggningsuppgifter från **[!UICONTROL Report Suite]** väljer du en Adobe Analytics-rapportsserie där du vill att Assets Insights ska hämta data. Klicka på **[!UICONTROL Add]**.
1. Efter [!DNL Experience Manager] ställer in din rapportsvit, klicka/peka **[!UICONTROL Done]**.

## Sidspårare {#page-tracker}

När du har konfigurerat ditt Analytics-konto genereras sidspårningskoden åt dig. Aktivera resursinsikter för att spåra [!DNL Experience Manager] resurser som används på tredjepartswebbplatser, inkluderar sidspårningskoden i webbplatskoden. Använda verktyget Sidspårare i [!DNL Experience Manager] Resurser för att generera sidspårningskod. Mer information om hur du inkluderar Page Tracker-koden på webbsidor från tredje part finns i [Använda sidspåraren och bädda in kod på webbsidor](touch-ui-using-page-tracker.md).

1. I AEM klickar du på **[!UICONTROL Tools > Assets]**.

   ![chlimage_1-214](assets/chlimage_1-214.png)

1. Från **[!UICONTROL Navigation]** klickar du på **[!UICONTROL Insights Page Tracker]** kort.
1. Klicka på **[!UICONTROL Download]** om du vill hämta sidspårningskod.
