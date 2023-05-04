---
title: Omstrukturering av Dynamic Media-arkiv i AEM 6.4
seo-title: Dynamic Media repository restructuring in AEM 6.4
description: Lär dig hur du gör de ändringar som krävs för att migrera till den nya databasstrukturen i AEM 6.4 för Dynamic Media.
seo-description: Learn how to make the necessary changes in order to migrate to the new repository structure in AEM 6.4 for Dynamic Media.
uuid: e26d61a4-47b6-493a-9ba2-4c58b200ddd9
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: 61cd5751-0dc8-48e0-873e-3a64899489bb
feature: Upgrading
exl-id: 1323ee60-c80c-4eed-b3e5-aa0f0c07e6ee
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Omstrukturering av Dynamic Media-arkiv i AEM 6.4{#dynamic-media-repository-restructuring-in-aem}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Enligt beskrivning på överordnad [Omstrukturering av lager i AEM 6.4](/help/sites-deploying/repository-restructuring.md) ska kunder som uppgraderar till AEM 6.4 använda den här sidan för att bedöma arbetsinsatsen i samband med databasändringar som påverkar Dynamic Media-lösningen. Vissa ändringar kräver arbete under uppgraderingsprocessen för AEM 6.4, medan andra kan skjutas upp till en uppgradering av version 6.5.

**Före 6.5-uppgradering**

* [Anpassade konfigurationer för adaptiv videokodning](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#custom-adaptive-video-encoding-configurations)
* [Dynamic Media (DMS7) Cloud-konfiguration](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#dynamic-media-dms-cloud-configuration)
* [Konfiguration av Dynamic Media (DM Hybrid) Cloud Service](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#cloudserviceconfiguration)
* [Dynamic Media - YouTube Cloud Service Configuration](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#youtubecloudserviceconfiguration)
* [Diverse](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md#misc)

## Före 6.5-uppgradering {#prior-to-upgrade}

### Anpassade adaptiva videokodningskonfigurationer  {#custom-adaptive-video-encoding-configurations}

<table> 
 <tbody>
  <tr>
   <td><strong>Föregående plats</strong></td> 
   <td><code>/etc/dam/video/dynamicmedia</code></td> 
  </tr>
  <tr>
   <td><strong>Ny plats(er)</strong></td> 
   <td><code>/conf/global/settings/dam/dm/presets/video/jcr:content</code></td> 
  </tr>
  <tr>
   <td><strong>Omstruktureringsvägledning</strong></td> 
   <td><p>Du kan köra följande migreringsskript för att migrera till den nya platsen:</p> <p><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> <p>Du kan också redigera konfigurationen i AEM och ändringarna sparas på den nya platsen.</p> </td> 
  </tr>
  <tr>
   <td><strong>Anteckningar</strong></td> 
   <td>Ej tillämpligt<br /> </td> 
  </tr>
 </tbody>
</table>

### Dynamic Media (DMS7) Cloud-konfiguration {#dynamic-media-dms-cloud-configuration}

<table> 
 <tbody>
  <tr>
   <td><strong>Föregående plats</strong></td> 
   <td><code>/etc/cloudservices/dmscene7</code></td> 
  </tr>
  <tr>
   <td><strong>Ny plats(er)</strong></td> 
   <td><code>/conf/global/settings/cloudservices/dmscene7</code></td> 
  </tr>
  <tr>
   <td><strong>Omstruktureringsvägledning</strong></td> 
   <td><p>Kunden kan köra ett migreringsskript på följande plats:<br /> </p> 
    <ul> 
     <li><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></li> 
     <li>Starta om Dynamic Media OSGi-paketet.</li> 
    </ul> </td> 
  </tr>
  <tr>
   <td><strong>Anteckningar</strong></td> 
   <td>Ej tillämpligt</td> 
  </tr>
 </tbody>
</table>

### Dynamic Media (DM Hybrid) Cloud Service configuration {#cloudserviceconfiguration}

<table> 
 <tbody>
  <tr>
   <td><strong>Föregående plats</strong></td> 
   <td><code>/etc/cloudservices/dynamicmediaservices</code></td> 
  </tr>
  <tr>
   <td><strong>Ny plats(er)</strong></td> 
   <td><code>/conf/global/settings/dam/dm/cloudservices/dynamicmediaservices</code></td> 
  </tr>
  <tr>
   <td><strong>Omstruktureringsvägledning</strong></td> 
   <td><p>Du kan köra migreringsskriptet nedan för att anpassa dig till den senaste modellen:</p> <p><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.jso</em></p> </td> 
  </tr>
  <tr>
   <td><strong>Anteckningar</strong></td> 
   <td>Ej tillämpligt<br /> </td> 
  </tr>
 </tbody>
</table>

### Dynamic Media - YouTube Cloud Service configuration  {#youtubecloudserviceconfiguration}

<table> 
 <tbody>
  <tr>
   <td><strong>Föregående plats</strong></td> 
   <td><code>/etc/cloudservices/youtube</code></td> 
  </tr>
  <tr>
   <td><strong>Ny plats(er)</strong></td> 
   <td><code>/libs/settings/dam/dm/youtube</code></td> 
  </tr>
  <tr>
   <td><strong>Omstruktureringsvägledning</strong></td> 
   <td><p>1. Avpublicera alla videofilmer från YouTube<br /> 2. Skapa YouTube-konfigurationen med nya TouchUI (från <code>/conf</code>) inklusive kopiering av alla kanaler från den gamla platsen<br /> 3. Publicera alla videor på YouTube igen.</p> <p>Arbetsflödet ger nya YouTube URL:er. Om du inte avpublicerar innan du skapar en ny TouchUI YouTube-konfiguration, kommer du att ha flera YouTube-URL:er listade under Egenskaper eftersom de återskapade kanalerna kommer att publiceras igen om du får chansen. Det innebär att du har oanvändbara URL:er som listas under Egenskaper.</p> </td> 
  </tr>
  <tr>
   <td><strong>Anteckningar</strong></td> 
   <td>Ej tillämpligt<br /> </td> 
  </tr>
 </tbody>
</table>

### Diverse {#misc}

<table> 
 <tbody>
  <tr>
   <td><strong>Föregående plats</strong></td> 
   <td><code>/etc/dam/imageserver/macros</code></td> 
  </tr>
  <tr>
   <td><strong>Ny plats(er)</strong></td> 
   <td><code>/conf/global/settings/dam/dm/presets/macro</code></td> 
  </tr>
  <tr>
   <td><strong>Omstruktureringsvägledning</strong></td> 
   <td><p>Kunden kan köra migreringsskriptet nedan.</p> <p><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> <p>Du kan också redigera konfigurationen i AEM och ändringarna sparas på den nya platsen.</p> </td> 
  </tr>
  <tr>
   <td><strong>Anteckningar</strong></td> 
   <td>Ej tillämpligt</td> 
  </tr>
 </tbody>
</table>

<table> 
 <tbody>
  <tr>
   <td><strong>Föregående plats</strong></td> 
   <td><code>/etc/dam/presets/analytics</code></td> 
  </tr>
  <tr>
   <td><strong>Ny plats(er)</strong></td> 
   <td><code>/libs/settings/dam/dm/analytics</code></td> 
  </tr>
  <tr>
   <td><strong>Omstruktureringsvägledning</strong></td> 
   <td><p>Kunden kan köra migreringsskriptet nedan.</p> <p><em>https://serveraddress:serverport/libs/settings/dam/dm/presets.migratedmcontent.json</em></p> </td> 
  </tr>
  <tr>
   <td><strong>Anteckningar</strong></td> 
   <td>Ej tillämpligt</td> 
  </tr>
 </tbody>
</table>
