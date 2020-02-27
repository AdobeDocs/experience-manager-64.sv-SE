---
title: Adobe Analytics-integrering med AEM-skärmar
seo-title: Adobe Analytics-integrering med AEM-skärmar
description: Följ den här sidan om du vill veta mer om hur AEM Screens kan integreras med Adobe Analytics och få ett spelbevis.
seo-description: Följ den här sidan om du vill veta mer om hur AEM Screens kan integreras med Adobe Analytics och få ett spelbevis.
uuid: f4f71c85-ab6b-4e4d-94d3-5ba55ec0a246
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: administering
discoiquuid: 2784b590-3402-492f-94a6-36fe16633e89
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Adobe Analytics-integrering med AEM-skärmar{#adobe-analytics-integration-with-aem-screens}

>[!CAUTION]
>
>Den här AEM-skärmfunktionen är bara tillgänglig om du har installerat AEM 6.4.2 Feature Pack 2 och AEM 6.3.3 Feature Pack 4.

>Om du vill få tillgång till något av dessa funktionspaket måste du kontakta Adobes support och begära åtkomst. När du har behörighet kan du hämta den från paketresursen.
>
Detta avsnitt behandlar följande ämnen:

* **Översikt**
* **Arkitekturinformation**
* **Konfigurera egenskaperna**

## Översikt {#overview}

***AEM Screens*** använder Adobe Analytics och med det kan ni uppnå något unikt på marknaden - flerkanalsanalyser som hjälper er att korrelera innehåll som visas på plats med andra datakällor.

Med AEM Screens får du en färdig integrering med Adobe Analytics och ett spelbevis.

I det här avsnittet beskrivs följande funktioner som används för att ansluta ett AEM Screens-projekt till Adobe Analytics:

* Tillåter att uppspelningsrapportering kan styrkas per enhet
* Tillåter granskning av uppspelningsrapportering efter tillgång
* Ser till att alla spelarhändelser hämtas och tidsstämplas
* Ser till att alla spelarhändelser lagras lokalt om uppspelningen inte är ansluten till ett nätverk

Adobe Analytics-integrering med AEM Screens har därför följande *mål*:

* Aktivera ROI från implementering av digitala signaturer
* Integrera Analytics som grund för att i framtiden kunna samla in och analysera användningsinformation

## Arkitekturinformation {#architectural-details}

I följande arkitekturdiagram förklaras Adobe Analytics-integreringen med AEM-skärmar:

![screen_shot_2018-09-12at85611am](assets/screen_shot_2018-09-12at85611am.png)

## Aktivera Adobe Analytics i AEM-skärmar {#enabling-adobe-analytics-in-aem-screens}

Adobe Analytics-inställningarna kan konfigureras från OSGi-konsolen.

Navigera till **Adobe Experience Manager Web Console Configuration** och konfigurera Adobe Analytics för AEM-skärmar enligt bilden nedan:

![screen_shot_2018-09-04at25550pm](assets/screen_shot_2018-09-04at25550pm.png)

### Konfigurera egenskaperna {#configuring-the-properties}

>[!CAUTION]
Innan du konfigurerar egenskaperna bör du kontakta din Adobe Relationship Manager och skapa en biljett för att få ett **API-nyckel** och **analysprojekt** för AEM-skärmar.

I följande tabell visas egenskaperna med en beskrivning av hur du konfigurerar Adobe Analytics för AEM-skärmar:

<table> 
 <tbody>
  <tr>
   <td><strong>Egenskap</strong></td> 
   <td><strong>Beskrivning</strong></td> 
  </tr>
  <tr>
   <td><strong>Analytics URL</strong></td> 
   <td>URL för att publicera analysdata från spelaren<br /> </td> 
  </tr>
  <tr>
   <td><strong>API-nyckel för analyser</strong></td> 
   <td>API-nyckel för autentisering till Adobe Analytics-servern (tillhandahålls av kontohanteraren)</td> 
  </tr>
  <tr>
   <td><strong>Analysprojekt</strong></td> 
   <td>AEM Screens-projektet som konfigurerats på din analys för att ta emot data (tillhandahålls av kontohanteraren)</td> 
  </tr>
  <tr>
   <td><strong>Miljö</strong></td> 
   <td><p>Scen- eller produktionsmiljö.</p> <p><em>För utveckling/scen</em> - https://cc-api-data-stage.adobe.io/ingest/<br /> <em>för produktion</em> - https://cc-api-data.adobe.io/ingest/</p> </td> 
  </tr>
  <tr>
   <td><strong>Sändningsfrekvens för analyser</strong></td> 
   <td>Frekvens i minuter för att skicka analysdata från spelarna. Som standard är den inställd på 15 minuter.</td> 
  </tr>
 </tbody>
</table>

>[!NOTE]
Som standard är **Analytics-sändningsfrekvensen **15 minuter.

#### Använda Adobe Analytics Service i AEM-skärmar {#using-adobe-analytics-service-in-aem-screens}

Detta scenario anropar Analytics API via REST-anrop från en analystjänst i komponenterna firmware och instrumentskärmar för att explicit skapa och skicka händelser som är specifika för ett visst användningsfall, samtidigt som det tillåter utökningsmöjligheter där anpassade meddelanden kan skickas till Analytics från en anpassad utvecklad kanal.

Analyshändelser lagras offline i indexedDB och sedan i chunked-läge och skickas till molnet.

>[!NOTE]
Mer information om ***sekvensering*** och ***standarddatamodell för händelser*** finns i [Konfigurera Adobe Analytics för AEM-skärmar](configuring-adobe-analytics-aem-screens.md) i Developer&#39;s section of AEM Screens.

