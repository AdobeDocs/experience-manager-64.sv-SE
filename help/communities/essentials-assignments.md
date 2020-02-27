---
title: Grundläggande om uppdrag
seo-title: Grundläggande om uppdrag
description: Översikt över uppdragsfunktionen för aktiveringscommunities
seo-description: Översikt över uppdragsfunktionen för aktiveringscommunities
uuid: 8310decf-174d-4e93-8c92-4a9583077b7a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 796781e6-5cab-4ea1-b484-0945bc8febbf
translation-type: tm+mt
source-git-commit: 4d64494dff34108d32e060a96209df697b2ce11f

---


# Grundläggande om uppdrag {#assignments-essentials}

Den här sidan innehåller viktig information om hur du arbetar med tilldelningsfunktionen på webbplatser [för aktiveringscommunityn](overview.md#enablement-community) .

Tilldelningsfunktionen är möjligheten att tilldela aktiveringsresurser och utbildningsvägar till medlemmar i aktiveringscommunityn.

## Grundläggande för klientsidan {#essentials-for-client-side}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/aktivering/components/hbs/myassign</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>oklanderlig</strong></a></td> 
   <td>Nej</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md"><strong>klientlibs</strong></a></td> 
   <td>cq.social.enablement.hbs.breadcrumbs<br /> cq.social.enablement.hbs.mysigned<br /> cq.social.enablement.hbs.resource<br /> cq.social.enablement.hbs.learningpath</td> 
  </tr>
  <tr>
   <td> <strong>templates</strong></td> 
   <td> /libs/social/enablement/components/hbs/myassigned/myassigned.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/enablement/components/hbs/myassigned/clientlibs/myassigned.css</td> 
  </tr>
  <tr>
   <td><strong> egenskaper</strong></td> 
   <td>Se <a href="assignments.md">Uppdragsfunktion</a></td> 
  </tr>
 </tbody>
</table>

### Status för slutförande och slutförande {#completion-and-success-status}

Slutförandestatus och Slutförandestatus används i rapporter och statusbanners för tilldelningar.

Slutförandestatus:

* Inte tilldelad
* Inte startad (ny)
* Pågår
* Slutförd

Status:

* Okänd
* Pass
* Misslyckades

De enda möjliga kombinationerna av slutförande och lyckad status är:

| **Slutförande** | **Lyckades** |
|---|---|
| Har inte startats | Okänd |
| Pågår | Okänd |
| Slutförd | Pass |
| Slutförd | Misslyckades |

## Grundläggande för serversidan {#essentials-for-server-side}

### Tilldelningsfunktion {#assignments-function}

En community-platsstruktur som innehåller [uppdragsfunktionen](functions.md#assignments-function), innehåller en konfigurerad ` [assignments](assignments.md)` komponent.

### Referens-API:er {#reference-apis}

* [API för aktivering](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/enablement/reporting/model/api/package-summary.html)

* [Rapporterings-API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/reporting/dv/api/package-summary.html)

* [API för rapporteringsanalys](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/reporting/analytics/api/package-summary.html)