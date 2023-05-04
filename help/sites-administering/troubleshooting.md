---
title: Arbeta med loggar
seo-title: Working with Logs
description: Lär dig hur du felsöker AEM genom att arbeta med loggar.
seo-description: Learn how to troubleshoot AEM by working with logs.
uuid: b64e0b25-5228-4c2f-9cc1-dde524134026
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: b4c1cb82-865b-48dd-b5c0-946e6610ce8e
exl-id: 201e2b57-17c0-4454-9b0e-026e2c95ac63
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 2%

---

# Arbeta med loggar{#working-with-logs}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

I det här avsnittet finns detaljerad information om loggar som du kan använda för att felsöka.

CRX registrerar detaljerade loggar. När du har packat upp och startat Quickstart finns loggarna på följande platser:

* crx-quickstart/launchpad/logs
* crx-quickstart/server/logs
* crx-quickstart/logs

## Aktivera felsökningsloggnivån {#activating-the-debug-log-level}

Standardloggnivån är INFO, d.v.s. DEBUG-meddelanden loggas inte.

Om du vill aktivera DEBUG-loggnivån använder du CRX-utforskaren för att ange

```xml
/libs/sling/config/org.apache.sling.commons.log.LogManager/org.apache.sling.commons.log.level
```

egenskap som ska felsökas. Lämna inte loggen på DEBUG-loggnivån längre än nödvändigt eftersom den genererar många loggar.

En rad i felsökningsfilen börjar oftast med DEBUG och anger sedan loggnivån, installationsåtgärden och loggmeddelandet. Till exempel:

```xml
DEBUG 3 WebApp Panel: WebApp successfully deployed
```

Loggnivåerna är följande:

| 0 | Allvarligt fel | Åtgärden misslyckades och installationsprogrammet kan inte fortsätta. |
|---|---|---|
| 1 | Fel | Åtgärden misslyckades. Installationen fortsätter, men en del av CRX installerades inte korrekt och kommer inte att fungera. |
| 2 | Varning | Åtgärden har slutförts men problem uppstod. CRX fungerar eventuellt inte korrekt. |
| 3 | Information | Åtgärden har slutförts. |

## Detaljerat alternativ som används för felsökning {#verbose-option-used-for-troubleshooting}

När du startar CRX kan du lägga till alternativet -v (utförligt) på kommandoraden som i: &quot;

` java -jar crx-<*version*>-<*edition*>.jar -v`

Använd det utförliga alternativet för felsökning eftersom det här alternativet visar några av snabbstartsloggens utdata på konsolen.
