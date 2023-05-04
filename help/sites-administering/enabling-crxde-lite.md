---
title: Aktivera CRXDE Lite i AEM
seo-title: Enabling CRXDE Lite in AEM
description: Lär dig hur du aktiverar CRXDE Lite i AEM.
seo-description: Learn how to enable CRXDE Lite in AEM.
uuid: d7a3db67-6384-463b-9aa9-f08ecc6c99c6
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: Security
content-type: reference
discoiquuid: 72df3ece-badf-466b-8f9a-0ec985d87741
exl-id: 3d8dc987-2ff9-4f71-bc07-48018caa3af4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 0%

---

# Aktivera CRXDE Lite i AEM{#enabling-crxde-lite-in-aem}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

För att säkerställa att AEM installationer är så säkra som möjligt rekommenderar checklistan [inaktivera WebDAV](/help/sites-administering/security-checklist.md#disable-webdav) i produktionsmiljöer.

CRXDE Lite är dock beroende av `org.apache.sling.jcr.davex` så att WebDAV-paketet fungerar som det ska, så att även CRXDE Lite inaktiveras om du inaktiverar det.

När det händer går du till `https://serveraddress:4502/crx/de/index.jsp` visar en tom rotnod och alla HTTP-begäranden till CRXDE Lite-resurser misslyckas:

```xml
404 Resource at '/crx/server/crx.default/jcr:root/.1.json' not found: No resource found
```

Den här rekommendationen är avsedd att minska attackytan så mycket som möjligt, men systemadministratörer kan ibland behöva åtkomst till CRXDE Lite för att kunna bläddra bland innehåll eller felsöka problem i produktionsinstanser.

Om du avaktiverar det här alternativet kan du aktivera CRXDE Lite genom att följa nedanstående procedur:

1. Gå till OSGi Components-konsolen på `http://localhost:4502/system/console/components`
1. Sök efter följande komponent:

   * `org.apache.sling.jcr.davex.impl.servlets.SlingDavExServlet`

1. Klicka på skiftnyckelsikonen bredvid den för att visa dess konfigurationsalternativ:

   ![chlimage_1-80](assets/chlimage_1-80.png)

1. Skapa följande konfiguration:

   * **Rotsökväg:** `/crx/server`
   * Fäst lådan under **Använd absoluta URI:er**.

1. När du är klar med CRXDE Lite måste du inaktivera WebDAV igen.

Du kan även aktivera CRXDE Lite via cURL genom att köra det här kommandot:

```shell
curl -u admin:admin -F "jcr:primaryType=sling:OsgiConfig" -F "alias=/crx/server" -F "dav.create-absolute-uri=true" -F "dav.create-absolute-uri@TypeHint=Boolean" http://localhost:4502/apps/system/config/org.apache.sling.jcr.davex.impl.servlets.SlingDavExServlet
```

## Andra resurser {#other-resources}

Mer information om säkerhetsfunktionerna i AEM 6 finns på följande sidor:

* [AEM checklista](/help/sites-administering/security-checklist.md)
* [Köra AEM i produktionsklart läge](/help/sites-administering/production-ready.md)
