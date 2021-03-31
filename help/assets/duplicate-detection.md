---
title: Aktivera dubblettidentifiering
description: Lär dig hur du aktiverar identifiering av duplicerade resurser i AEM.
contentOwner: AG
feature: Resurshantering,Resursrapporter
role: Affärsledare,Administratör
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '147'
ht-degree: 0%

---


# Aktiverar dubblettidentifiering {#enabling-duplicate-detection}

Om du försöker överföra en resurs som finns i Adobe Experience Manager (AEM) Resurser identifieras den som duplicerad av dubblettidentifieringsfunktionen. Dubblettidentifiering är inaktiverat som standard. Så här aktiverar du funktionen:

1. Öppna sidan **[!UICONTROL Adobe Experience Manager Web Console Configuration]** på `https://[server]:[port]/system/console/configMgr`.
1. Redigera konfigurationen för servleten **[!UICONTROL Day CQ DAM Create Asset]**.
1. Välj alternativet **[!UICONTROL detect duplicate]** och klicka/tryck på **[!UICONTROL Save]**.

   ![Välj alternativet Identifiera dubblett i serverleten](assets/chlimage_1-377.png)

Funktionen för att identifiera dubbletter är nu aktiverad i AEM Assets. När en användare försöker överföra en resurs som finns i AEM, söker systemet efter en konflikt och anger den. Resurserna identifieras med SHA-1-hash som lagras på `jcr:content/metadata/dam:sha1`, vilket innebär att duplicerade resurser identifieras oavsett filnamn.

>[!MORELIKETHIS]
>
>* [Duplicera resurser i befintlig databas (en självstudiekurs från en community-medlem)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)

