---
title: Konfigurera överföringsbegränsningar för resurser
description: Lär dig hur du konfigurerar Adobe Experience Manager Assets för att begränsa vilken typ av resurser (filer) som användare kan överföra.
contentOwner: AG
feature: Upload,Asset Ingestion,Asset Management
role: Admin,Architect
exl-id: 0d817cfa-ae06-442a-ad89-5fe619bb2eff
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 25%

---

# Konfigurera överföringsbegränsningar för resurser {#configuring-asset-upload-restrictions}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan konfigurera Adobe Experience Manager Resurser för att begränsa vilken typ av resurser (filer) som användare kan överföra. Den här funktionen hjälper dig att eliminera möjligheten för användare att överföra resurser i ett oönskat format eller överföra skadliga filer. The `Day CQ DAM Asset Upload Restriction` kan du styra vilken typ av filer som användare kan överföra. Som standard [!DNL Experience Manager] Med resurser kan användare överföra resurser av alla MIME-typer. Du kan dock konfigurera tjänsten så att den begränsar användare till att överföra filer av specifika MIME-typer.

1. Om du vill öppna webbkonsolen för Configuration Manager går du till `https://[AEM_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Day CQ DAM Asset Upload Restriction]** i redigeringsläge. Som standard är **Tillåt alla MIME** är markerat, vilket gör att användare kan överföra filer av alla MIME-typer.

   ![chlimage_1-378](assets/chlimage_1-378.png)

1. Om du vill att användarna bara ska kunna överföra filer av vissa MIME-typer avmarkerar du alternativet **[!UICONTROL llow all MIME]** och anger tillåtna MIME-typer i fälten **[!UICONTROL Allowed Asset MIMEs (regex)]** med reguljära uttryck.

   ![chlimage_1-379](assets/chlimage_1-379.png)

1. Klicka/tryck på **[!UICONTROL Save]** för att spara ändringarna. Om du anger MIME-strängar för tillåtna MIME-typer misslyckas överföringen för alla resurser med en MIME-typ som inte matchar de konfigurerade MIME-strängarna i dessa fält.
