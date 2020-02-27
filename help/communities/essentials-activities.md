---
title: Grundläggande om aktivitetsström
seo-title: Grundläggande om aktivitetsström
description: Lista över senaste aktiviteter som utförts av en medlem eller en lista över senaste aktiviteter för en enskild tråd med innehåll
seo-description: Lista över senaste aktiviteter som utförts av en medlem eller en lista över senaste aktiviteter för en enskild tråd med innehåll
uuid: 6e4734bb-52a8-4670-b665-e640108b036e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 8cc04993-4021-4cb7-b973-5afc4da1ed11
translation-type: tm+mt
source-git-commit: 4d64494dff34108d32e060a96209df697b2ce11f

---


# Grundläggande om aktivitetsström {#activity-stream-essentials}

En inloggad community-medlems aktiviteter, till exempel publicering på ett forum eller en blogg, samlas i en ström som kan filtreras och visas på olika sätt genom konfiguration av aktivitetsströmkomponenten.

Möjligheten att följa efter lägger till ytterligare en uppsättning aktiviteter när communitymedlemmar följer inlägg av intresse eller andra communitymedlemmar.

Alla [communitywebbplatser](overview.md#communitiessites) innehåller en användarprofilsida för den inloggade medlemmen som visar medlemsaktiviteter på samma sätt.

## Concepts {#concepts}

En *aktivitetsström* är en lista med de senaste aktiviteterna som utförts av en medlem eller en lista med de senaste aktiviteterna för en enskild tråd med innehåll, till exempel ett forumämne eller en blogg.

En medlem kan följa en aktivitetsström antingen efter en annan person eller ett annat innehåll.

Ett *nyhetsflöde* är en sammanslagning av de aktivitetsströmmar som följs av en medlem till en enda ström.

Ett [socialt diagram](essentials-socialgraph.md) fångar följande relationer mellan en medlem och en annan.

## Grundläggande för klientsidan {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>sociala/aktiva strömmar/komponenter/hbs/aktivitetsströmmar</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>oklanderlig</strong></a></td> 
   <td>Nej</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md"><strong>klientlibs</strong></a></td> 
   <td>cq.social.hbs.activitystreams</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/activitystreams/components/hbs/activitystreams/activitystreams.hbs<br /> /libs/social/activitystreams/components/hbs/activitystreams/activity/activity-title.hbs<br /> /libs/social/activitystreams/components/hbs/activitystreams/activity/activity.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/activitystreams/components/hbs/activitystreams/clientlibs/activitystreams.css</td> 
  </tr>
  <tr>
   <td><strong> egenskaper</strong></td> 
   <td>Se <a href="activities.md">Funktionen Aktivitetsströmmar</a></td> 
  </tr>
 </tbody>
</table>

* [Anpassningar på klientsidan](client-customize.md)

## Grundläggande för serversidan {#essentials-for-server-side}

* [API för aktivitetsströmmar](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/activitystreams/api/package-frame.html)

* [API för lyssnare för aktivitetsströmmar](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/activitystreams/listener/api/package-frame.html)

* [Anpassningar på serversidan](server-customize.md)

### Funktion för aktivitetsström {#activity-stream-function}

En community-platsstruktur som innehåller funktionen [för](functions.md#activity-stream-function)aktivitetsström innehåller en konfigurerad `activity streams` komponent.
