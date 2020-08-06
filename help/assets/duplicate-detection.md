---
title: Aktivera dubblettidentifiering
description: Lär dig hur du aktiverar identifiering av duplicerade resurser i AEM.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 26e860cd513d70d748f872e2ce445a042d075bc6
workflow-type: tm+mt
source-wordcount: '140'
ht-degree: 0%

---


# Aktivera dubblettidentifiering {#enabling-duplicate-detection}

Om du försöker överföra en resurs som finns i Adobe Experience Manager (AEM) Resurser identifieras den som duplicerad av dubblettidentifieringsfunktionen. Dubblettidentifiering är inaktiverat som standard. Så här aktiverar du funktionen:

1. Öppna **[!UICONTROL Adobe Experience Manager Web Console Configuration]** sidan på `https://[server]:[port]/system/console/configMgr`.
1. Redigera konfigurationen för serverutrymmet **[!UICONTROL Day CQ DAM Create Asset]**.
1. Välj **[!UICONTROL detect duplicate]** alternativet och klicka/tryck **[!UICONTROL Save]**.

   ![Välj alternativet Identifiera dubblett i serverleten](assets/chlimage_1-377.png)

Funktionen för att identifiera dubbletter är nu aktiverad i AEM Assets. När en användare försöker överföra en resurs som finns i AEM, söker systemet efter en konflikt och anger den. Resurserna identifieras med SHA-1-hash som lagras på `jcr:content/metadata/dam:sha1`, vilket innebär att duplicerade resurser identifieras oavsett filnamn.

>[!MORELIKETHIS]
>
>* [Duplicera resurser i befintlig databas (en självstudiekurs från en community-medlem)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)

