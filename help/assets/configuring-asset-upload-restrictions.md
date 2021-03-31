---
title: Konfigurera överföringsbegränsningar för resurser
description: Lär dig hur du konfigurerar Adobe Experience Manager (AEM) Resurser för att begränsa vilken typ av resurser (filer) som användare kan överföra.
contentOwner: AG
feature: Developer
role: Administratör,Arkitekt
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '208'
ht-degree: 29%

---


# Konfigurera överföringsbegränsningar för resurser {#configuring-asset-upload-restrictions}

Du kan konfigurera Adobe Experience Manager (AEM) Resurser för att begränsa vilken typ av resurser (filer) som användare kan överföra. Den här funktionen hjälper dig att eliminera möjligheten för användare att överföra resurser i ett oönskat format eller överföra skadliga filer. Med tjänsten `Day CQ DAM Asset Upload Restriction` kan du styra vilken typ av filer som användare kan överföra. Som standard tillåter AEM Assets användare att överföra resurser av alla MIME-typer. Du kan dock konfigurera tjänsten så att den begränsar användare till att överföra filer av specifika MIME-typer.

1. Öppna Configuration Manager-webbkonsolen genom att gå till `https://[AEM_server]:[port]/system/console/configMgr`.
1. Öppna tjänsten **[!UICONTROL Day CQ DAM Asset Upload Restriction]** i redigeringsläge. Som standard är alternativet **Tillåt alla MIME** markerat, vilket gör att användare kan överföra filer av alla MIME-typer.

   ![chlimage_1-378](assets/chlimage_1-378.png)

1. Om du vill att användarna bara ska kunna överföra filer av vissa MIME-typer avmarkerar du alternativet **[!UICONTROL llow all MIME]** och anger tillåtna MIME-typer i fälten **[!UICONTROL Allowed Asset MIMEs (regex)]** med reguljära uttryck.

   ![chlimage_1-379](assets/chlimage_1-379.png)

1. Klicka/tryck på **[!UICONTROL Save]** för att spara ändringarna. Om du anger MIME-strängar för tillåtna MIME-typer misslyckas överföringen för alla resurser med en MIME-typ som inte matchar de konfigurerade MIME-strängarna i dessa fält.
