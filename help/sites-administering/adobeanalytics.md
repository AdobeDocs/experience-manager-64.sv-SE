---
title: Integrera med Adobe Analytics
seo-title: Integrating with Adobe Analytics
description: Lär dig integrera AEM med Adobe Analytics.
seo-description: Learn how to integrate AEM with Adobe Analytics.
uuid: 8329d891-1897-46f6-80ee-40244b079c0e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 0089394f-0107-49eb-ad73-52e9cabe71b1
exl-id: ca11bfcd-06d1-4ca9-9069-afa91d8a6610
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 18%

---

# Integrera med Adobe Analytics{#integrating-with-adobe-analytics}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Genom att integrera Adobe Analytics och AEM kan du spåra webbsidans aktivitet:

* Med en Adobe Analytics-konfiguration kan AEM autentisera med Adobe Analytics.
* Ett ramverk identifierar de data som skickas till din Adobe Analytics-rapportsserie.

Informationen innehåller sid- och användardata. till exempel:

* data som AEM komponenter samla in
* länkklick
* videoanvändningsinformation
* antalet sidbesök från Adobe Analytics

Följande sidor hjälper dig att konfigurera integreringen:

* [Ansluta till Adobe Analytics och skapa ramverk](/help/sites-administering/adobeanalytics-connect.md)
* [Konfigurera länkspårning för Adobe Analytics](/help/sites-administering/adobeanalytics-link.md)
* [Mappa komponentdata med Adobe Analytics-egenskaper](/help/sites-administering/adobeanalytics-mapping.md)
* [Konfigurera videospårning för Adobe Analytics](/help/sites-administering/adobeanalytics-video.md)

Du kan också använda [Guiden Anmäl dig](/help/sites-administering/opt-in.md) för att enkelt kunna genomföra integreringen.

>[!NOTE]
>
>Se även artikeln med instruktioner: [Integrera AEM med Adobe Target och Adobe Analytics med DTM](https://helpx.adobe.com/experience-manager/using/integrate-digital-marketing-solutions.html).

## Ytterligare information {#further-information}

Se:

* [Utöka Adobe Analytics-integreringen](/help/sites-developing/extending-analytics.md) för information om utveckling av komponenter som samlar in användardata och anpassar Adobe Analytics-ramverket.
* Kunskapsbasartikeln [Adobe Analytics-integrering - felsökningsproblem](https://helpx.adobe.com/experience-manager/kb/sitecatalystintegrationtroubleshooting.html), för information om felsökning av Adobe Analytics-integrering.

>[!NOTE]
>
>Om du använder Adobe Analytics med en anpassad proxykonfiguration måste du [konfigurera två OSGi-paket](/help/sites-deploying/configuring-osgi.md) (till exempel med webbkonsolen) som krävs för proxykonfigurationerna i **Apaches HTTP-klient**. Båda är obligatoriska eftersom vissa funktioner i AEM använder 3.x-API:erna, medan andra använder 4.x-API:erna. Konfigurera:
>
>* **Day Commons HTTP Client 3.1** konfigurera 3.x-API:t,\
   >  till exempel [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient)
>
>* **Proxykonfiguration för Apache HTTP-komponenter** konfigurera 4.x-API:t,
>
>  till exempel [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator)
