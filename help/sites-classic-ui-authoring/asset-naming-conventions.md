---
title: Namnkonventioner för tillgångstestning
seo-title: Naming conventions for assets
description: Noderna i databasen omfattas av namnkonventioner i Java Content Repository. Adobe Experience Manager inför dock ytterligare konventioner för resursnodernas namn.
seo-description: Nodes in the repository are subject to naming conventions of the Java Content Repository. However, Adobe Experience Manager imposes further conventions for the name of asset nodes.
uuid: 6b622a60-90e8-461e-9b67-42c11c7038f9
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 55e66c66-0120-4ed4-94c5-d65a434bb59b
exl-id: 3dc38c37-f2a0-44f5-90f6-fee8c6f84ff4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 0%

---

# Namnkonventioner för tillgångstestning{#naming-conventions-for-assets-testing}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Noderna i databasen omfattas av namnkonventioner i [Java Content Repository](/help/sites-developing/the-basics.md#java-content-repository). Adobe Experience Manager inför dock ytterligare konventioner för resursnodernas namn.

## Klassiskt användargränssnitt {#classic-ui}

Det klassiska användargränssnittet har tätare begränsningar:

* Validerar resursnamnet när ett explicit nodnamn är:

   * en resurstitel tillhandahålls för konvertering till nodnamnet
   * ett explicit nodnamn anges

* Giltiga tecken (endast dessa tecken är giltiga när en resurs skapas i det klassiska användargränssnittet):

   * &#39;a&#39; till &#39;z&#39;
   * &#39;A&#39; till &#39;Z&#39;
   * 0 till 9
   * _ (understreck)
   * `-` (tankstreck/minustecken)
