---
title: Grundläggande om identifiering
seo-title: Ideation Essentials
description: Översikt över funktionen Idéer
seo-description: Ideation feature overview
uuid: abaf03ee-8bf4-4241-96c3-474c95a30a88
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: a9e4f2f0-d1ff-40c0-abcf-645e40586a84
exl-id: 7fb68293-c6e3-4793-b433-205bcfc23e20
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '142'
ht-degree: 0%

---

# Grundläggande om identifiering {#ideation-essentials}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Den här sidan innehåller viktig information för att arbeta med idéfunktionen, som liknar ett forum, men med möjlighet att spara som ett utkast och få en bättre samarbetskänsla.

## Grundläggande för klientsidan {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/ideation/components/hbs/ideation</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>oklanderlig</strong></a></td> 
   <td>Nej</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md"><strong>klientlibs</strong></a></td> 
   <td>cq.social.hbs.röstning<br /> cq.social.hbs.like<br /> cq.social.hbs.ideation</td> 
  </tr>
  <tr>
   <td> <strong>mallar</strong></td> 
   <td> /libs/social/ideation/components/hbs/ideation/ideation.hbs<br /> /libs/social/ideation/components/hbs/ideation/ideationlists.hbs<br /> /libs/social/ideation/components/hbs/ideation/composer.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/ideation/components/hbs/ideation/clientlibs/ideation.css</td> 
  </tr>
  <tr>
   <td><strong> egenskaper</strong></td> 
   <td>Se <a href="ideation-feature.md">Idéfunktion</a></td> 
  </tr>
 </tbody>
</table>

* [Anpassningar på klientsidan](client-customize.md)

### Ideationsfunktion {#ideation-function}

En community-webbplatsstruktur som innehåller [Ideationsfunktion](functions.md#ideation-function), innehåller en konfigurerad `ideation` -komponenten.
