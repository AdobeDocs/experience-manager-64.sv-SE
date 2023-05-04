---
title: Grundläggande om aktivitetsström
seo-title: Activity Stream Essentials
description: Lista över senaste aktiviteter som utförts av en medlem eller en lista över senaste aktiviteter för en enskild tråd med innehåll
seo-description: List of recent activites performed by a member or a list of recent activities on a single thread of content
uuid: 6e4734bb-52a8-4670-b665-e640108b036e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 8cc04993-4021-4cb7-b973-5afc4da1ed11
exl-id: 74dcbefa-e670-419b-af9b-b3d3c593ebaa
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Grundläggande om aktivitetsström {#activity-stream-essentials}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

En inloggad community-medlems aktiviteter, till exempel publicering på ett forum eller en blogg, samlas i en ström som kan filtreras och visas på olika sätt genom konfiguration av aktivitetsströmkomponenten.

Möjligheten att följa efter lägger till ytterligare en uppsättning aktiviteter när communitymedlemmar följer inlägg av intresse eller andra communitymedlemmar.

Alla [communitysajter](overview.md#communitiessites) innehåller en användarprofilsida för den inloggade medlemmen som visar medlemsaktiviteter på samma sätt.

## Concepts {#concepts}

An *aktivitetsström* är en lista med de senaste aktiviteterna som utförts av en medlem eller en lista med de senaste aktiviteterna för en enskild tråd med innehåll, t.ex. ett forumämne eller en blogg.

En medlem kan följa en aktivitetsström antingen efter en annan person eller ett annat innehåll.

A *nyhetsfeed* är en sammanslagning av de aktivitetsströmmar som följs av en medlem till en enda ström.

A [socialt diagram](essentials-socialgraph.md) hämtar följande relationer mellan en medlem och en annan medlem.

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
   <td> <strong>mallar</strong></td> 
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

En community-webbplatsstruktur som innehåller [Funktionen Aktivitetsström](functions.md#activity-stream-function), innehåller en konfigurerad `activity streams` -komponenten.
