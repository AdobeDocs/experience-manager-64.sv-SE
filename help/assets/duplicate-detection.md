---
title: Aktivera dubblettidentifiering
description: Lär dig hur du aktiverar identifiering av duplicerade resurser i AEM.
contentOwner: AG
feature: Asset Management,Asset Reports
role: User,Admin
exl-id: 138cf649-9e21-415e-9861-b07caacc85db
source-git-commit: 8948bca63f1f5ec9d94ede2fb845ed01b4e23333
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 0%

---

# Aktivera dubblettidentifiering {#enabling-duplicate-detection}

Om du försöker överföra en resurs som finns i Adobe Experience Manager Assets identifieras den som duplicerad av dubblettidentifieringsfunktionen. Dubblettidentifiering är inaktiverat som standard. Så här aktiverar du funktionen:

1. Öppna sidan **[!UICONTROL Adobe Experience Manager Web Console Configuration]** på `https://[server]:[port]/system/console/configMgr`.
1. Redigera konfigurationen för servleten **[!UICONTROL Day CQ DAM Create Asset]**.
1. Välj alternativet **[!UICONTROL detect duplicate]** och klicka/tryck på **[!UICONTROL Save]**.

   ![Välj alternativet Identifiera dubblett i serverleten](assets/chlimage_1-377.png)

Funktionen för att identifiera dubbletter är nu aktiverad i [!DNL Experience Manager]-resurser. När en användare försöker överföra en resurs som finns i AEM, söker systemet efter en konflikt och anger den. Resurserna identifieras med SHA-1-hash som lagras på `jcr:content/metadata/dam:sha1`, vilket innebär att duplicerade resurser identifieras oavsett filnamn.

>[!MORELIKETHIS]
>
>* [Duplicera resurser i befintlig databas (en självstudiekurs från en community-medlem)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)

