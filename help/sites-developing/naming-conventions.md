---
title: Namnkonventioner
seo-title: Naming Conventions
description: Noderna i databasen omfattas av namnkonventioner i Java Content Repository
seo-description: Nodes in the repository are subject to naming conventions of the Java Content Repository
uuid: 0515c5c5-3e93-4710-983f-c08c146467fc
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 198098c0-432b-4a93-a94e-2552337435dd
exl-id: 741043c7-2ebb-455d-8163-a246b874a7b3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---

# Namnkonventioner{#naming-conventions}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Noderna i databasen omfattas av namnkonventioner i [Java Content Repository](/help/sites-developing/the-basics.md#java-content-repository). AEM lägger dock till ytterligare konventioner för sidnodernas namn.

## Namnkonventioner för sidor {#naming-conventions-for-pages}

Dessa namnkonventioner implementeras på olika nivåer:

* JcrUtil: AEM genomförande av [JCR-verktyg](#jcr-utilities).
* PageManager: den [Page Manager](#page-manager) innehåller metoder för åtgärder på sidnivå.
* Enligt det användargränssnitt som används:

   * [Pekaktiverat användargränssnitt som standard](#standard-ui)
   * [Klassiskt användargränssnitt](#classic-ui)

### JCR-verktyg {#jcr-utilities}

[JcrUtil](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/index.html?com/day/cq/commons/jcr/JcrUtil.html) är den AEM implementeringen av de gemensamma teknikverktygen. Det är särskilt intressant att validera namn om du kontrollerar teckenmappningar och följande valideringar:

* `isValidName`

   * Kontrollerar om namnet inte är tomt och bara innehåller giltiga tecken.
   * Kan användas för att kontrollera om ett föreslaget namn är giltigt.

* `createValidName`

   * Detta skapar en giltig etikett av en godtycklig sträng.
   * Den kan användas för att skapa ett namn från en titel.

### Page Manager {#page-manager}

[PageManager](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageManager.html) innehåller metoder för sidnivååtgärder, baserade på [JCRUtil](#jcr-utilities).

### Standardgränssnitt {#standard-ui}

Standardgränssnittet med pekskärm:

* Validerar namnet enligt de begränsningar som PageManager har när något av följande inträffar:

   * en sidrubrik tillhandahålls för konvertering till nodnamnet
   * ett explicit nodnamn anges

### Klassiskt användargränssnitt {#classic-ui}

Det klassiska användargränssnittet har tätare begränsningar:

* Validerar namnet när ett explicit nodnamn är:

   * en sidrubrik tillhandahålls för konvertering till nodnamnet
   * ett explicit nodnamn anges

* Giltiga tecken (endast dessa tecken är giltiga när en sida skapas i det klassiska användargränssnittet, även om `PageManagerImpl` tillåter ytterligare tecken):

   * &#39;a&#39; till &#39;z&#39;
   * &#39;A&#39; till &#39;Z&#39;
   * 0 till 9
   * _ (understreck)
   * `-` (tankstreck/minustecken)
