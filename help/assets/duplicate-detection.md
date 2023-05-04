---
title: Aktivera dubblettidentifiering
description: Lär dig hur du aktiverar identifiering av duplicerade resurser i AEM.
contentOwner: AG
feature: Asset Management,Asset Reports
role: User,Admin
exl-id: 138cf649-9e21-415e-9861-b07caacc85db
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '174'
ht-degree: 0%

---

# Aktivera dubblettidentifiering {#enabling-duplicate-detection}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Om du försöker överföra en resurs som finns i Adobe Experience Manager Assets identifieras den som duplicerad av dubblettidentifieringsfunktionen. Dubblettidentifiering är inaktiverat som standard. Så här aktiverar du funktionen:

1. Öppna **[!UICONTROL Adobe Experience Manager Web Console Configuration]** sida vid `https://[server]:[port]/system/console/configMgr`.
1. Redigera konfigurationen för serverutrymmet **[!UICONTROL Day CQ DAM Create Asset]**.
1. Välj **[!UICONTROL detect duplicate]** och klicka/peka **[!UICONTROL Save]**.

   ![Välj alternativet Identifiera dubblett i serverleten](assets/chlimage_1-377.png)

Funktionen för att identifiera dubbletter är nu aktiverad i [!DNL Experience Manager] Resurser. När en användare försöker överföra en resurs som finns i AEM, söker systemet efter en konflikt och anger den. Resurserna identifieras med SHA-1-hash som lagras på `jcr:content/metadata/dam:sha1`, vilket innebär att duplicerade resurser identifieras oavsett filnamn.

>[!MORELIKETHIS]
>
>* [Duplicera resurser i befintlig databas (en självstudiekurs från en community-medlem)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)

