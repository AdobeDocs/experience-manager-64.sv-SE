---
title: Åtgärder och funktioner i formulärcentrerade AEM arbetsflöden i OSGi- och AEM Forms JEE-arbetsflöden
seo-title: Actions and capabilities of Form-centric AEM Workflows on OSGi and AEM Forms JEE workflows
description: Läs mer om skillnaderna i åtgärder som stöds av AEM Inbox och HTML Workspace, skillnaderna i funktioner som stöds av formulärbaserade AEM Workflows i arbetsflöden för OSGi och AEM Forms JEE samt skillnaderna mellan funktionerna AEM Inbox och AEM Forms App.
seo-description: Learn more about the differences in actions supported by AEM Inbox and HTML Workspace, differences in capabilities supported by Form-centric AEM Workflows on OSGi and AEM Forms JEE Workflows, and differences between AEM Inbox and AEM Forms app features.
uuid: ce2a05fe-ba45-42ed-880e-fb1d6efc1d26
contentOwner: khsingh
topic-tags: publish
discoiquuid: 4c7ba430-25b2-4ba2-a5eb-4edaed0d599a
exl-id: 6172d936-9348-4f3f-a437-6465dd156f3b
source-git-commit: f8b19b6723d333e76fed111b9fde376b3bb13a1d
workflow-type: tm+mt
source-wordcount: '878'
ht-degree: 17%

---

# Åtgärder och funktioner i formulärcentrerade AEM arbetsflöden i OSGi- och AEM Forms JEE-arbetsflöden  {#actions-and-capabilities-of-form-centric-aem-workflows-on-osgi-and-aem-forms-jee-workflows}

## Arbetsytan AEM Inkorgen och HTML {#aem-inbox-and-html-workspace}

AEM Inbox används för att köra och övervaka Forms-centrerade AEM Workflows on OSGi. Med arbetsytan i HTML kan du köra och övervaka AEM Forms JEE-arbetsflöden. I följande tabell visas viktiga åtgärder som är tillgängliga i AEM Inbox för Forms-centrerade AEM Workflows on OSGi and HTML Workspace for AEM Forms JEE Workflows.

<table> 
 <tbody>
  <tr>
   <td>Åtgärder</td> 
   <td>AEM</td> 
   <td>HTML arbetsyta</td> 
  </tr>
  <tr>
   <td>Starta en process, en uppgift eller ett formulärprogram<br /> </td> 
   <td>Stöds<br /> </td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Skicka uppgifter</td> 
   <td>Stöds<br /> </td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Tilldela en uppgift till en grupp</td> 
   <td>Stöds<br /> </td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Skicka till flera rutter</td> 
   <td>Stöds<br /> </td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Spåra aktivitetshistorik och uppgiftssammanfattning</td> 
   <td>Stöds<br /> </td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>E-postaviseringar</td> 
   <td>Stöds<br /> </td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Tilldela uppgifter igen</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Bifogade filer på fältnivå för anpassade formulär</td> 
   <td>Stöds</td> 
   <td>Stöds ej</td> 
  </tr>
  <tr>
   <td>Kalendervy</td> 
   <td>Stöds</td> 
   <td>Stöds ej</td> 
  </tr>
  <tr>
   <td>Kommentarer på aktivitetsnivå</td> 
   <td>Stöds</td> 
   <td>Stöds ej</td> 
  </tr>
  <tr>
   <td>Köer (delad personlig kö, göra anspråk på uppgifter från kö)</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Underrättelse utanför kontoret</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Tilldela en uppgift till flera användare</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
 </tbody>
</table>

## Formulärbaserade AEM arbetsflöden för OSGi- och AEM Forms JEE-arbetsflöden {#form-centric-aem-workflows-on-osgi-and-aem-forms-jee-workflows}

Formulärbaserade AEM arbetsflöden för OSGi- och AEM Forms JEE-arbetsflöden (AEM Forms on JEE Process Management) har en annan uppsättning funktioner. I följande tabell visas viktiga funktioner och stöd som är tillgängliga för funktionerna i formulärbaserade AEM arbetsflöden i OSGi och AEM Forms i JEE-arbetsflöden:

<table> 
 <tbody>
  <tr>
   <td>Funktioner</td> 
   <td>Formulärbaserade AEM arbetsflöden i OSGi<br /> </td> 
   <td>AEM Forms JEE Workflows</td> 
  </tr>
  <tr>
   <td>Adaptiv Forms</td> 
   <td>Stöds</td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Integrering med andra AEM</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Klottersignatur</td> 
   <td>Stöds</td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Egna e-postmallar</td> 
   <td>Stöds</td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Definiera uppgiftsprioritet</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Timeout för en aktivitet efter förfallodatum</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Slingor i arbetsflödet</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Välja en tilldelad dynamiskt </td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Använda anpassade metadata</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>E-signatur (Acrobat Sign)</td> 
   <td>Stöds <sup>[1]</sup></td> 
   <td>Stöds <sup>[5]</sup></td> 
  </tr>
  <tr>
   <td>Hantera uppgifter och formulärprogram</td> 
   <td>Stöds <sup>[2]</sup><br /> </td> 
   <td>Stöds <sup>[2]</sup></td> 
  </tr>
  <tr>
   <td>Dokumenttjänster</td> 
   <td>Stöds <sup>[3]</sup></td> 
   <td>Stöds <sup>[3]</sup></td> 
  </tr>
  <tr>
   <td>Rendera den slutförda aktiviteten som ett anpassat formulär eller PDF-dokument</td> 
   <td>Stöds</td> 
   <td>Stöds [4]</td> 
  </tr>
  <tr>
   <td>Integrering med Correspondence Management</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Knappen Återställ</td> 
   <td>Stöds</td> 
   <td>Stöds ej</td> 
  </tr>
  <tr>
   <td>Arbetsflödesfaser</td> 
   <td>Stöds</td> 
   <td>Stöds ej</td> 
  </tr>
  <tr>
   <td>Skrivskyddade anpassningsbara formulär</td> 
   <td>Stöds</td> 
   <td>Stöds ej</td> 
  </tr>
  <tr>
   <td>Dölja standardknappen för att spara</td> 
   <td>Stöds</td> 
   <td>Stöds ej</td> 
  </tr>
  <tr>
   <td>Detaljerad kontroll över avsnittet med arbetsflödesinformation</td> 
   <td>Stöds</td> 
   <td>Stöds ej</td> 
  </tr>
  <tr>
   <td>HTML5 Forms, Interactive PDF forms, Form Set<br /> </td> 
   <td>Stöds ej<br /> </td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Processrapportering</td> 
   <td>Stöds ej<br /> </td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Digital signatur</td> 
   <td>Stöds<br /> </td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Startpunktskategorier</td> 
   <td>Stöds ej </td> 
   <td>Stöds </td> 
  </tr>
  <tr>
   <td>Godkännande av gruppuppgift </td> 
   <td>Stöds ej </td> 
   <td>Stöds </td> 
  </tr>
  <tr>
   <td>Spara utkast med ett eget namn</td> 
   <td>Stöds ej </td> 
   <td>Stöds </td> 
  </tr>
  <tr>
   <td>Initiera en process med befintliga processdata<br /> </td> 
   <td>Stöds ej</td> 
   <td>Stöds </td> 
  </tr>
  <tr>
   <td>Spara en startpunkt som ett utkast</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>User avatar</td> 
   <td>Stöds</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Hanterarvy</td> 
   <td>Stöds ej</td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Sökmallar</td> 
   <td>Stöds ej</td> 
   <td>Stöds<br /> </td> 
  </tr>
  <tr>
   <td>Integrering med tredjepartsprogram</td> 
   <td>Stöds <sup>[6]</sup></td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Bifogade filer på aktivitetsnivå för arbetsflödesprogram eller startpunkt</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Påminnelse - e-post</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Ändra titel på timeout för uppgift</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>E-post om uppgiftsdelegering och aktivitetskrav</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Skicka ett e-postmeddelande i slutet av arbetsflödet</td> 
   <td>Stöds <sup>[7]</sup></td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Delegera mellan osammanhängande grupper</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Anropa en webbtjänst från ett arbetsflöde</td> 
   <td>Stöds <sup>[6]</sup></td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>XSLT-omvandling</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Gateways, INGA VÄNTNINGAR</td> 
   <td>Stöds </td> 
   <td>Stöds </td> 
  </tr>
  <tr>
   <td>ELLER, OCH dela</td> 
   <td>Stöds ej</td> 
   <td>Stöds</td> 
  </tr>
  <tr>
   <td>Prioritet för dynamisk aktivitet</td> 
   <td>Stöds ej</td> 
   <td>Stöds ej</td> 
  </tr>
 </tbody>
</table>

1. Du kan använda formulärbaserade AEM arbetsflöden i OSGi för att signera ett redan ifyllt anpassat formulär. Formulärbaserade AEM i OSGi-arbetsflöden stöder inte formulärsignering. The [signering i formulär](/help/forms/using/working-with-adobe-sign.md#create-in-form-signing-experience) upplevelsen stöds inte.

1. Du måste ha tillgång till AEM Inbox för att kunna köra och övervaka AEM Forms OSGi AEM Workflows och HTML Workspace för att kunna köra och övervaka AEM Forms JEE Workflows.
1. AEM Forms Document Services finns för både formulärbaserade AEM arbetsflöden i OSGi och AEM Forms i JEE-arbetsflöden. AEM Workflow använder inbyggda dokumenttjänster för formulärbaserade AEM arbetsflöden i OSGi- och AEM Forms JEE-arbetsflöden (Process Management).
1. AEM Forms JEE-arbetsflöden kan bara återge ett anpassat formulär. Det går inte att återge ett anpassat formulär som ett PDF-dokument.
1. AEM formulär JEE-arbetsflöden har inget separat steg för Acrobat Sign. Du behöver ett anpassningsbart formulär som kan aktiveras av Acrobat Sign för AEM formulär i JEE-arbetsflöden. Mer information finns i [Acrobat Sign-dokumentation](/help/forms/using/working-with-adobe-sign.md#add-and-configure-the-signature-step-component).
1. Du kan använda [Anropa datamodelltjänst för formulär](/help/forms/using/aem-forms-workflow-step-reference.md#p-invoke-form-data-model-service-step-p) steg för att anropa en webbtjänst och publicera eller hämta data från ett tredjepartsprogram.
1. Du kan använda [Skicka e-post](/help/forms/using/aem-forms-workflow-step-reference.md#send-email-step) steg för att skicka e-post.

## Skillnader mellan funktionerna AEM Inkorgen och AEM Forms app {#differences-between-aem-inbox-and-aem-forms-app-features}

Två av de framträdande sätten att starta ett Forms-centrerat arbetsflöde använder [AEM](/help/forms/using/manage-applications-inbox.md) och AEM Forms. Funktionerna i AEM Inbox och AEM Forms App skiljer sig dock åt. AEM Inkorgen fungerar bara med [Forms-centrerade arbetsflöden](/help/forms/using/aem-forms-workflow.md) medan AEM Forms-programmet fungerar med både Forms-centrerade arbetsflöden och processhantering.

I följande tabell visas funktionerna i AEM Inbox och AEM Forms app:

<table> 
 <tbody>
  <tr>
   <td><p><strong>Åtgärder</strong></p> </td> 
   <td><p><strong>AEM</strong></p> </td> 
   <td><p><strong>AEM Forms App</strong></p> </td> 
  </tr>
  <tr>
   <td><p>Starta ett formulärprogram</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds</p> </td> 
  </tr>
  <tr>
   <td><p>Skicka uppgifter</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds</p> </td> 
  </tr>
  <tr>
   <td><p>Delegera uppgifter</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds ej</p> </td> 
  </tr>
  <tr>
   <td><p>Spåra aktivitetshistorik och uppgiftssammanfattning</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds ej</p> </td> 
  </tr>
  <tr>
   <td><p>Lägga till bilagor på aktivitetsnivå</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds</p> </td> 
  </tr>
  <tr>
   <td><p>Visa bilagor på aktivitetsnivå</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds</p> </td> 
  </tr>
  <tr>
   <td><p>Lägga till bilagor på fältnivå</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds</p> </td> 
  </tr>
  <tr>
   <td><p>Visa kalendervyn</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds ej</p> </td> 
  </tr>
  <tr>
   <td><p>Infogning av kommentarer.</p> </td> 
   <td><p>Stöds</p> </td> 
   <td><p>Stöds</p> </td> 
  </tr>
 </tbody>
</table>
