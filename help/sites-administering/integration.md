---
title: Lösningsintegrering
seo-title: Solutions Integration
description: Läs mer om integrering av lösningar i AEM.
seo-description: Learn more about Solutions Integration in AEM.
uuid: 3bf56b1b-284d-4f14-8974-0a595ece5028
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: b5ff918d-08ab-4307-a807-693468fc083b
exl-id: 1ee7ccbd-8654-4d03-8a67-2c41863ae951
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 0%

---

# Lösningsintegrering{#solutions-integration}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

* [Integrera med Adobe Marketing Cloud](/help/sites-administering/marketing-cloud.md)
* [Integrera med tredjepartstjänster](/help/sites-administering/third-party-services.md)
* [Analyser med externa leverantörer](/help/sites-administering/external-providers.md)
* [Katalogproducent](/help/sites-administering/catalog-producer.md)
* [SharePoint Connector](/help/sites-administering/sharepoint-connector.md)

Följande information finns om hur du integrerar AEM med andra Adobe- eller tredjepartstjänster:

>[!NOTE]
>
>Om du använder en anpassad proxykonfiguration tillsammans med integreringen måste du konfigurera båda HTTP-klientproxykonfigurationerna eftersom vissa funktioner i AEM använder 3.x-API:erna och andra 4.x-API:er:
>
>* 3.x har konfigurerats med [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient)
>* 4.x har konfigurerats med [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator)
>

