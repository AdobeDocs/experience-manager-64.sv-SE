---
title: Deploying Best Practices
seo-title: Deploying Best Practices
description: Deploying and maintaining best practices.
seo-description: Deploying and maintaining best practices.
uuid: 4546ed2c-43d5-40f3-874f-567b324e78c2
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 4b5c0677-c630-4fae-867e-4f4583ac8507
translation-type: tm+mt
source-git-commit: c9591211c80d453de5172c90501d2d2907eba4e6
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---


# Distribuera bästa praxis{#deploying-best-practices}

Deploying best practices describe how to deploy or maintain AEM in the most efficient and most effective way possible. Den här växande listan med ämnen innehåller en mängd olika områden i AEM.

Följande områden har dokumentation om användning och underhåll av bästa metoder och rekommendationer:

* [OAK](#oak)
* [Communities](#communities)
* [UI](#ui)
* [Prestanda](#performance)

For best practices on administering, developing, or authoring, see one of the following:

* [Administrera metodtips](/help/sites-administering/administer-best-practices.md)
* [Utveckla bästa praxis](/help/sites-developing/best-practices.md)
* [Bästa tillvägagångssätt](/help/sites-authoring/best-practices.md)

Specifika dokument beskrivs och länkas till i de tabeller som följer.

## OAK {#oak}

[Oak](/help/sites-deploying/platform.md) is a scalable and performant hierarchical content repository that is the foundation of AEM.

<table> 
 <tbody>
  <tr>
   <td><p>Scalability, Performance and Disaster Recovery</p> </td> 
   <td><a href="/help/sites-deploying/performance.md">Performance &amp; Scalability</a></td> 
   <td>Provides a white paper discussing the technical agility, high performance, and sound disaster recovery features</td> 
  </tr>
  <tr>
   <td>Recommended OAK deployments</td> 
   <td><a href="/help/sites-deploying/recommended-deploys.md">Recommended deployments</a></td> 
   <td>Describes deployment scenarios</td> 
  </tr>
  <tr>
   <td>Mongo topology</td> 
   <td><a href="/help/sites-deploying/recommended-deploys.md">Bästa praxis för Mongo-topologi</a></td> 
   <td>Describes mongo topology - when to use which topology.</td> 
  </tr>
  <tr>
   <td>Alternativ för datalagring</td> 
   <td><a href="/help/sites-deploying/data-store-config.md">Konfigurera nod- och datalager</a></td> 
   <td>This document explains best practices around storing binary data and content nodes. Includes informationon using Amazon S3 data store.</td> 
  </tr>
  <tr>
   <td>Search in OAK</td> 
   <td><a href="/help/sites-deploying/best-practices-for-queries-and-indexing.md">Metodtips för frågor och indexering</a><br /> </td> 
   <td>Describes best practices on how to index content.</td> 
  </tr>
 </tbody>
</table>

## Communities {#communities}

AEM Communities simplifies the creation and management of on-premise Communities. Best practices for AEM Communities are described here:

[Community Content Store](/help/communities/working-with-srp.md) - Discusses the new shared storage feature for user generated content (UGC) and the considerations for choosing the underlying [topology](/help/communities/topologies.md).

[Rekommenderade distributioner för communities](/help/sites-deploying/recommended-deploys.md#considerations-for-aem-communities) - Beskriver de rekommenderade distributionerna för Communities. |

## UI {#ui}

Best practices around the user interface are described here:

[User Interface Recommendations for Customers](/help/sites-deploying/ui-recommendations.md)

AEM currently has two UIs: classic and touch-optimized UI in the same release. Therefore customers have to make a decision about which to use during the project implementation. This document is intended to help with finding the right choice.

## Prestanda {#performance}

Best practices around performance are listed here:

<table> 
 <tbody>
  <tr>
   <td>Best Practices for Quality Assurance</td> 
   <td><a href="/help/sites-deploying/configuring-performance.md#best-practices-for-quality-assurance">Bästa metoder för kvalitetssäkring</a></td> 
   <td>A standardized overview of the issues involved with defining a Test Concept specifically for performance tests on your <em>publish</em> environment. This is primarily of interest to QA engineers, project managers and system administrators.</td> 
  </tr>
  <tr>
   <td>Using Dispatcher with a CDN</td> 
   <td><a href="https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher.html#using-dispatcher-with-a-cdn">Using Dispatcher with a CDN</a></td> 
   <td>A content delivery network (CDN), such as Akamai Edge Delivery or Amazon Cloud Front, deliver content from a location close to the end user.</td> 
  </tr>
  <tr>
   <td>Prestandaoptimering</td> 
   <td><a href="/help/sites-deploying/configuring-performance.md">Prestandaoptimering</a></td> 
   <td>Ett viktigt problem är den tid det tar för er webbplats att svara på besökarnas förfrågningar.</td> 
  </tr>
  <tr>
   <td>Prestandatestning</td> 
   <td><a href="/help/sites-deploying/best-practices-for-performance-testing.md">Bästa metoder för prestandatestning</a></td> 
   <td>Beskriver de bästa sätten att köra prestandatester på en AEM.<br /> </td> 
  </tr>
 </tbody>
</table>

