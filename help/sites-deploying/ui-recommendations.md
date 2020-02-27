---
title: Rekommendationer för användargränssnitt för kunder
seo-title: Rekommendationer för användargränssnitt för kunder
description: 'En lista med rekommendationer relaterade till de klassiska och pekoptimerade användargränssnitten. '
seo-description: 'En lista med rekommendationer relaterade till de klassiska och pekoptimerade användargränssnitten. '
uuid: c661fb10-4dbc-4f8b-93be-3e77af1ad095
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 42bf42cb-0c6c-4390-8170-2c540c4d3ed3
translation-type: tm+mt
source-git-commit: b01e95110bffc1ee96e0814e782d716ed949c1b4

---


# Rekommendationer för användargränssnitt för kunder{#user-interface-recommendations-for-customers}

Adobe Experience Manager 6.4 har två användargränssnitt - det enhetliga användargränssnittet i Experience Cloud och det klassiska användargränssnittet.

Det här dokumentet är avsett att vägleda kunderna att välja vilket användargränssnitt som ska användas beroende på deras situation.

Intressevillkor:

* **Användargränssnitt (eller standardgränssnitt)** Modernt användargränssnitt som introducerades i 5.6.0 som en förhandstitt på teknik och utökades i efterföljande versioner. Det baseras på den enhetliga användarupplevelsen för Adobe Experience Cloud, som tidigare kallades användargränssnitt med pekfunktion eller användargränssnitt.

* **Klassiskt användargränssnitt** baserat på ExtJS-teknik som introducerades med CQ 5.1 2008.

* **Webbplatsadministratörer** kan hantera platshierarkin (flytta, aktivera, hantera referenser) och skapa nya sidor.

* **Sidredigering** för att lägga till/redigera innehållet på en sida.

* **DAM/Assets Admin** Capabilities to manage digital assets (including images, video, documents, downloads).

* **ContextHub** Capabilities för att samla information om besökaren och använda den för olika syften. Tillhandahåller ett användargränssnitt för att simulera personer som besöker webbplatsen. Med början från AEM 6.2 ersatte ContextHub den tidigare tekniken, Client Context.

## Allmänt {#general}

Under de senaste åren har Adobe uppdaterat alla Adobe Experience Cloud-lösningar med ett enhetligt användargränssnitt. Användare i hela Experience Cloud-lösningar får en enhetlig upplevelse av vanliga mönster för hur de använder och använder programmen. I varje release har Adobe förfinat användargränssnittet baserat på feedback från kunder som arbetar med de olika lösningarna.

Det ursprungliga användargränssnittet för Adobe Experience Manager (tidigare kallat CQ5), som introducerades 2008 och används av kunder som kör version 5.0-5.6.1, finns i AEM 6.4. Detta garanterar att kunderna kan uppdatera till 6.4 och dra nytta av en uppdaterad plattform med nya funktioner samtidigt som de använder samma användargränssnitt.

Adobe rekommenderar kunder att gå över till det nya användargränssnittet under 2018/2019. Detta kan antingen göras under uppdateringen till 6.4, eller i ett separat projekt efter uppdateringen som innehåller nödvändiga justeringar av anpassningarna och komponentdialogrutorna.

Adobe planerar inte att göra fler förbättringar av det klassiska användargränssnittet med början från AEM 6.4.Observera att Classic-användargränssnittet fortfarande stöds fullt ut när det är inaktuellt.

## Regler och rekommendationer {#rules-and-recommendations}

Nedan följer en lista med rekommendationer från Product Management för Adobe Experience Manager 6.4:

<table> 
 <tbody> 
  <tr> 
   <th>Mitt projekt...</th> 
   <th>Rekommendationer</th> 
  </tr> 
  <tr> 
   <td>Vi börjar precis använda Adobe Experience Manager.</td> 
   <td>Använd standardgränssnittet.</td> 
  </tr> 
  <tr> 
   <td><p>Har använt AEM ett tag.</p> <p>Har använt produktgränssnittet som det är tänkt och utvecklat anpassade komponenter för webbplatserna.<br /> </p> </td> 
   <td> 
    <ol> 
     <li>Uppdatera till 6.4</li> 
     <li>Använd standardgränssnittet för platsadministration, resurser, ... osv.<br /> </li> 
     <li>Konfigurera åtgärden Redigera sida för att öppna den klassiska sidredigeraren i användargränssnittet. Se <a href="#selecting-your-ui">Välja användargränssnitt</a>.</li> 
    </ol> <p>I en andra fas:</p> 
    <ol> 
     <li>Uppdatera komponentdialogrutorna så att de använder Dialogrutan Coral 3. Adobe rekommenderar att du uppdaterar komponenterna med <a href="/help/sites-developing/dialog-conversion.md">Dialog Conversion Tool</a> .</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td>Har skapat en webbplats som använder ClientContext med integreringar.<br /> </td> 
   <td> 
    <ol> 
     <li>Uppdatera till 6.4</li> 
     <li>Använd standardgränssnittet för platsadministration, resurser, ... osv.</li> 
     <li>Konfigurera åtgärden Redigera sida för att öppna den klassiska sidredigeraren i användargränssnittet. Se <a href="#selecting-your-ui">Välja användargränssnitt</a>.</li> 
    </ol> <p>I en andra fas:</p> 
    <ol> 
     <li>Uppdatera komponentdialogrutorna så att de använder Dialogrutan Coral 3. Adobe rekommenderar att du uppdaterar komponenterna med <a href="/help/sites-developing/dialog-conversion.md">Dialog Conversion Tool</a> .</li> 
     <li>Konfigurera ContextHub (ersättning för ClientContext) och uppdatera sidmallarna så att ContextHub används. Observera att ContextHub har ett kompatibilitetsläge som tillåter inläsning av anpassade ClientContext-lager.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><p>Har använt CQ/AEM i många år.</p> <p>Har utökat produktgränssnittet (t.ex. platsadministratör) och byggt komponenter med omfattande redigeringsdialogrutor.</p> </td> 
   <td><p>Uppdatera till 6.4 och konfigurera det klassiska användargränssnittet som standard för sidredigering för alla användare. Se <a href="#selecting-your-ui">Välja användargränssnitt</a>.</p> <p>Starta sedan ett projekt för att anpassa och optimera komponentdialogrutorna i Coral 3-format. Se <a href="#resources-to-help">Resurser att hjälpa</a>.<br /> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vanliga frågor {#faq}

Mer information finns i kunskapsbasartikeln [Touch UI Authoring FAQ](https://helpx.adobe.com/experience-manager/kb/index/touchui_faq.html). inklusive information om det klassiska användargränssnittets borttagningsschema.

## Välja användargränssnitt {#selecting-your-ui}

Se [Välja användargränssnitt](/help/sites-authoring/select-ui.md) för information om hur du konfigurerar systemet efter behov.

## Touchoptimerad gränssnittsstatus {#touch-optimized-ui-status}

Mer information om förbättringarna av det pekoptimerade användargränssnittet i AEM 6.3 finns i [Nyheter](/help/release-notes/release-notes.md#what-s-new) i versionsinformationen.

En fullständig översikt finns på sidan [Funktionsstatus](/help/release-notes/touch-ui-features-status.md) för Touch UI

## Resurser att hjälpa {#resources-to-help}

För bakgrundsinformation om grundläggande hantering:

* [Arbeta med redigeringsmiljön](/help/sites-authoring/home.md).
* [Redigeringssidor](/help/sites-authoring/author-environment-tools.md).

Detaljerad utvecklingsinformation:

* [Touchoptimerad gränssnittsarkitektur](/help/sites-developing/touch-ui-concepts.md).
* Använd verktyget [för](/help/sites-developing/dialog-conversion.md) dialogkonvertering för att konvertera komponentredigeringsdialogrutor från det klassiska användargränssnittet till det pekoptimerade användargränssnittet.

* [Struktur för det pekoptimerade användargränssnittet](/help/sites-developing/touch-ui-structure.md).

* [Anpassa konsolerna i det pekoptimerade användargränssnittet](/help/sites-developing/customizing-consoles-touch.md) (inklusive exempelkod).

* [Anpassa sidredigering i det pekoptimerade användargränssnittet](/help/sites-developing/customizing-page-authoring-touch.md) (inkluderar exempelkod).

* [AEM Gem Session vid pekoptimerad anpassning](https://docs.adobe.com/content/ddc/en/gems/user-interface-customization-for-aem-6.html).
* [Bevilja gränssnittsdokumentation](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/index.html).

