---
title: Aktivera dubblettidentifiering
description: Lär dig hur du aktiverar identifiering av dubblettresurser i AEM.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 26e860cd513d70d748f872e2ce445a042d075bc6

---


# Aktivera dubblettidentifiering {#enabling-duplicate-detection}

Om du försöker överföra en resurs som finns i Adobe Experience Manager-resurser (AEM) identifieras den som duplicerad av dubblettidentifieringsfunktionen. Dubblettidentifiering är inaktiverat som standard. Så här aktiverar du funktionen:

1. Öppna konfigurationssidan för **[!UICONTROL Adobe Experience Manager Web Console]** på `https://[server]:[port]/system/console/configMgr`.
1. Redigera konfigurationen för serverns CQ DAM **[!UICONTROL Create Asset]**.
1. Välj alternativet **[!UICONTROL Identifiera dubbletter]** och klicka/tryck på **[!UICONTROL Spara]**.

   ![Välj alternativet Identifiera dubblett i serverleten](assets/chlimage_1-377.png)

Funktionen för att identifiera dubbletter är nu aktiverad i AEM Resurser. När en användare försöker överföra en resurs som finns i AEM söker systemet efter en konflikt och anger den. Resurserna identifieras med SHA-1-hash som lagras på `jcr:content/metadata/dam:sha1`, vilket innebär att duplicerade resurser identifieras oavsett filnamn.

>[!MORELIKETHIS]
>
>* [Duplicera resurser i befintlig databas (en självstudiekurs från en community-medlem)](https://experience-aem.blogspot.com/2019/06/aem-65-find-duplicate-assets-binaries-in-existing-repository.html)

