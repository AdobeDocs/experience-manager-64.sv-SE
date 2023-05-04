---
title: Konsekvenskontroll och genomgående kontroll
seo-title: Consistency and Traversal Checks
description: Lär dig hur du utför konsekventa och stegvisa kontroller.
seo-description: Learn how to perform consistency and traversal checks.
uuid: 0304e378-7c60-4bf5-9052-d01149d2a6df
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
discoiquuid: af9a3e9d-194a-42e5-be28-b238e0c1e55e
feature: Configuring
exl-id: 67dfa0f7-24ac-41ae-83c9-3bb1a8656502
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Konsekvenskontroll och genomgående kontroll{#consistency-and-traversal-checks}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När du uppgraderar kan det uppstå problem på grund av inkonsekvenser i arbetsytan. Du kan antingen köra en testuppgradering för att se om det är ett problem eller köra konsekvenskontrollerna som förebyggande åtgärder.

Om du kör en testuppgradering som misslyckas på grund av inkonsekvenser i arbetsytan ser du liknande poster i crx-quickstart/logs/crx/error.log:

```xml
*ERROR* TarPersistenceManager: No bundle found for uuid 'deadbeef-cafe-babe-cafe-babecafebabe'
 ...
*ERROR* RepositoryImpl: Failed to initialize workspace 'crx.default'
javax.jcr.RepositoryException: Error indexing workspace: Error indexing workspace: Error indexing workspace
...
```

## Utför en konsekvenskontroll {#perform-a-consistency-check}

Navigera till administrationssidan för JMX Mbean**.adobe.granite (Repository)** för att utföra en konsekvenskontroll. Från AEM huvudskärm går du till:

**Verktyg > Webbkonsol > Huvudmeny (på menyraden) > JMX > com.adobe.granite (databas)**

I en standardinstallation finns den här:  **[|Visa mig|](http://localhost:4502/system/console/jmx/com.adobe.granite%3Atype%3DRepository)**

I **Operationer** på sidan hittar du två metoder: **`traversalCheck`** och **`consistencyCheck`**. Om du vill utföra en kontroll klickar du på åtgärden och anger önskade parametrar.

![chlimage_1-117](assets/chlimage_1-117.png)
