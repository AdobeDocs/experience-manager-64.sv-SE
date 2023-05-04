---
title: Tagg Essentials
seo-title: Tag Essentials
description: Översikt över taggar
seo-description: Tag overview
uuid: a5d52319-f821-4608-b0ab-abc8a1374343
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: d355a3ee-c8a8-4a07-8d28-d1a99bda315c
exl-id: 863ee5e3-daa7-4f7d-8897-291d367cf29d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# Tagg Essentials {#tag-essentials}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När AEM Communities-komponenter har konfigurerats med taggning aktiverat, kan communitymedlemmar tagga det innehåll de publicerar i publiceringsmiljön.

Den underliggande infrastrukturen för taggar som används i publiceringsmiljön är densamma som för taggar som används på innehåll i redigeringsmiljön, till exempel sidor och resurser:

* Se [Administrera taggar](../../help/sites-administering/tags.md) och [Tagga användargenererat innehåll](tag-ugc.md) (UGC) om du vill ha information om hur du skapar och hanterar taggar.

* Se [Tagga för utvecklare](../../help/sites-developing/tags.md) om du vill ha information om [taggningsramverk](../../help/sites-developing/framework.md) samt inkludera och utöka taggar i [anpassade program](../../help/sites-developing/building.md).

* Se [Använda molnet för sociala taggar](tagcloud.md) för information till författare om hur du lägger till en `social tag cloud` -komponent på en sida för att markera de taggar som används i UGC i publiceringsmiljön.

* Se [Aktiveringsresurser för taggning](tag-resources.md) om du vill ha information om hur du taggar resurser för kataloger.

Taggning av UGC kan vara aktiverat när en [communitywebbplats](sites-console.md#tagging) eller någon av följande funktioner:

* [Blogg](blog-feature.md)
* [Kalender](calendar.md)
* [Filbibliotek](file-library.md)
* [Forum](forum.md)
* [QnA](working-with-qna.md)

## Grundläggande för klientsidan {#essentials-for-client-side}

### Social Tag Cloud {#social-tag-cloud}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/komma/components/hbs/tagcloud</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>oklanderlig</strong></a></td> 
   <td>Nej</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md"><strong>klientlibs</strong></a></td> 
   <td>cq.social.hbs.tagcloud</td> 
  </tr>
  <tr>
   <td> <strong>mallar</strong></td> 
   <td> /libs/social/commons/components/hbs/tagcloud/tagcloud.hbs<br /> </td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/commons/components/hbs/tagcloud/clientlibs/tagcloud.css</td> 
  </tr>
  <tr>
   <td><strong>egenskaper</strong></td> 
   <td>Se <a href="tagcloud.md">Använda molnet för sociala taggar</a></td> 
  </tr>
 </tbody>
</table>

* [Anpassningar på klientsidan](client-customize.md)

## Grundläggande för serversidan {#essentials-for-server-side}

* [API för socialt taggmoln](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/commons/tagcloud/api/package-summary.html)

* [Social Tag Manager](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/commons/tagging/package-summary.html)

* [Anpassningar på serversidan](server-customize.md)

## Taggsökning {#tag-searching}

Från och med [funktionspaket 1](deploy-communities.md#latestfeaturepack) (FP1) utförs taggsökning med [taggtitlar](../../help/sites-developing/framework.md#tag-characteristics).

Före FP1 utfördes sökningen med [tagg-ID](../../help/sites-developing/framework.md#tagid).
