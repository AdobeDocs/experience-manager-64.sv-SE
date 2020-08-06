---
title: e-handel - översikt
seo-title: e-handel - översikt
description: 'AEM generiska e-handelslösningen finns som en del av standardinstallationen och ger dig full funktionalitet i e-handelsramverket.  '
seo-description: 'AEM generiska e-handelslösningen finns som en del av standardinstallationen och ger dig full funktionalitet i e-handelsramverket.  '
uuid: 7be42b1e-f1d6-4891-96f8-0133b3a299a1
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: cb043066-aefc-4b68-b302-2b5dd710a786
translation-type: tm+mt
source-git-commit: 0a7f40dd692985890c0c51c54a153135d39c7bd8
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---


# e-handel - översikt{#ecommerce-overview}

AEM allmänna e-handelslösningen är tillgänglig som en del av en standardinstallation och ger dig full funktionalitet i e-handelsramverket.

Adobe tillhandahåller två versioner av Commerce Integration Framework:

|  | CIF lokal | CIF Cloud |
|-------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| AEM | AEM på plats eller AMS 6.x | AEM AMS 6.4 och 6.5 |
| Back-end | - AEM, Java <br> - Monolitisk integrering, mappning före bygge (mall)<br> - JCR-databas | - Magento <br>- Java och Javascript <br>- Inga handelsdata lagras i JCR-databasen |
| Front-end | AEM återgivna sidor på serversidan | Blandat sidprogram (hybridåtergivning) |
| Produktkatalog | - Produktimport, redigerare, cachelagring i AEM <br>- Vanliga kataloger med AEM- eller proxysidor | - Ingen produktimport <br>- generiska mallar <br>- on demand-data via anslutning |
| Skalbarhet | - Kan hantera upp till ett fåtal miljoner produkter (beroende på användningsfall) <br> - Cachelagring av Dispatcher | - Ingen volymbegränsning <br>- Cachelagring av Dispatcher eller CDN |
| Standardiserad datamodell | Nej | Ja, Magento GraphQL-schema |
| Tillgänglighet | Ja:<br> - SAP Commerce Cloud (tillägget har uppdaterats för att stödja AEM 6.4 och Hybris 5 (standard) och bibehåller kompatibiliteten med Hybris 4 <br>- Salesforce Commerce Cloud (Connector open-sourced för att stödja AEM 6.4) | Ja via öppen källkod via GitHub. <br> Magento Commerce (Stöder Magento 2.3.2 (standard) och är kompatibelt med Magento 2.3.1). |
| När ska användas | Begränsad användning: För scenarier där små, statiska kataloger kan behöva importeras | Rekommenderad lösning i de flesta fall |


## Distribuera andra implementeringar {#deploying-other-implementations}

* [SAP Commerce Cloud](/help/sites-deploying/sap-commerce-cloud.md)
* [Salesforce Commerce Cloud](https://github.com/adobe/commerce-salesforce)
* [Magento](https://www.adobe.io/apis/experiencecloud/commerce-integration-framework/integrations.html#!AdobeDocs/commerce-cif-documentation/master/integrations/02-AEM-Magento.md)

>[!NOTE]
>
>Mer information om koncept och hur du administrerar e-handelsimplementeringar finns i [Administrera e-handel](/help/sites-administering/ecommerce.md).
>
>Mer information om hur du utökar e-handelsfunktionerna finns i [Utveckla e-handel](/help/sites-developing/ecommerce.md).

