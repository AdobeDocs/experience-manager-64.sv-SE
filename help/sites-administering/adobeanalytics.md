---
title: Integrera med Adobe Analytics
seo-title: Integrera med Adobe Analytics
description: Lär dig hur du integrerar AEM med Adobe Analytics.
seo-description: Lär dig hur du integrerar AEM med Adobe Analytics.
uuid: 8329d891-1897-46f6-80ee-40244b079c0e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 0089394f-0107-49eb-ad73-52e9cabe71b1
translation-type: tm+mt
source-git-commit: 98fae2d51d73bda946f3c398e9276fe4d5a8a0fe
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 20%

---


# Integrera med Adobe Analytics{#integrating-with-adobe-analytics}

Genom att integrera Adobe Analytics och AEM kan du följa upp din webbsidesaktivitet:

* Med en Analytics-konfiguration kan AEM autentisera med Adobe Analytics.
* Ett ramverk identifierar de data som skickas till din Adobe Analytics-rapportsvit.

Informationen innehåller sid- och användardata. till exempel:

* data som AEM-komponenter samlar in
* länkklick
* videoanvändningsinformation
* antalet sidbesök från Adobe Analytics

Följande sidor hjälper dig att konfigurera integreringen:

* [Ansluta till Adobe Analytics och skapa ramverk](/help/sites-administering/adobeanalytics-connect.md)
* [Konfigurera länkspårning för Adobe Analytics](/help/sites-administering/adobeanalytics-link.md)
* [Mappa komponentdata med Adobe Analytics-egenskaper](/help/sites-administering/adobeanalytics-mapping.md)
* [Konfigurera videospårning för Adobe Analytics](/help/sites-administering/adobeanalytics-video.md)

Du kan också använda guiden [](/help/sites-administering/opt-in.md) Anmäl dig för att enkelt utföra integreringen.

>[!NOTE]
>
>Se även artikeln med instruktioner: [Integrera AEM med Adobe Target och Adobe Analytics med DTM](https://helpx.adobe.com/experience-manager/using/integrate-digital-marketing-solutions.html).

## Ytterligare information {#further-information}

Se:

* [Utöka Adobe Analytics Integration](/help/sites-developing/extending-analytics.md) med information om hur man utvecklar komponenter för insamling av användardata och anpassning av Adobe Analytics-ramverket.
* Kunskapsbasartikeln om integrering med [Adobe Analytics - felsökning av problem](https://helpx.adobe.com/experience-manager/kb/sitecatalystintegrationtroubleshooting.html)- innehåller information om hur du felsöker integreringen med Adobe Analytics.

>[!NOTE]
>
>Om du använder Adobe Analytics med en anpassad proxykonfiguration måste du [konfigurera två OSGi-paket](/help/sites-deploying/configuring-osgi.md) (till exempel med webbkonsolen) som krävs för proxykonfigurationerna i **Apaches HTTP-klient**. Båda är obligatoriska eftersom vissa funktioner i AEM använder 3.x-API:erna, medan andra använder 4.x-API:erna. Konfigurera:
>
>* **Day Commons HTTP Client 3.1** för att konfigurera 3.x API;\
   >  till exempel [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient)
   >
   >
* **Proxykonfiguration** för Apache HTTP Components för att konfigurera 4.x API;
>
>  
till exempel [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator)

