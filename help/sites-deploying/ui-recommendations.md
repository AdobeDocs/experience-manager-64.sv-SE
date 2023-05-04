---
title: Användargränssnitt Recommendations för kunder
seo-title: User Interface Recommendations for Customers
description: En lista med rekommendationer relaterade till de klassiska och pekoptimerade användargränssnitten.
seo-description: A list of recommendations related to the classic and touch-optimized user interfaces.
uuid: c661fb10-4dbc-4f8b-93be-3e77af1ad095
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 42bf42cb-0c6c-4390-8170-2c540c4d3ed3
exl-id: 1e5172d9-47a3-4d73-b749-166e201f4eef
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '813'
ht-degree: 0%

---

# Användargränssnitt Recommendations för kunder{#user-interface-recommendations-for-customers}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager 6.4 har två användargränssnitt - det enhetliga användargränssnittet för Experience Cloud och det klassiska användargränssnittet.

Det här dokumentet är avsett att vägleda kunderna att välja vilket användargränssnitt som ska användas beroende på deras situation.

Intressevillkor:

* **Användargränssnitt (eller standardgränssnitt)**
Modernt användargränssnitt som introducerades i 5.6.0 som en förhandstitt på teknik och utökades i efterföljande versioner. Det bygger på den enhetliga användarupplevelsen för Adobe Experience Cloud, som tidigare kallades användargränssnitt med pekfunktion eller användargränssnitt.

* **Klassiskt användargränssnitt**
Användargränssnitt som bygger på ExtJS-teknik som introducerades med CQ 5.1 2008.

* **Webbplatsadministratör**
Möjlighet att hantera platshierarkin (flytta, aktivera, hantera referenser) och skapa nya sidor.

* **Sidredigering**
Möjlighet att lägga till/redigera innehållet på en sida.

* **DAM-/resursadministratör**
Möjlighet att hantera digitalt material (inklusive bilder, video, dokument, nedladdningar).

* **ContextHub**
Möjlighet att samla information om besökaren och använda den för olika syften. Tillhandahåller ett användargränssnitt för att simulera personer som besöker webbplatsen. Med början AEM 6.2 ersatte ContextHub den tidigare tekniken, Client Context.

## Allmänt {#general}

Under de senaste åren har Adobe uppdaterat alla Adobe Experience Cloud-lösningar med ett enhetligt användargränssnitt. De olika Experience Cloud-lösningarna har en enhetlig upplevelse av de vanligaste mönstren för hur programmen används och används. I varje release har Adobe förfinat sitt användargränssnitt baserat på feedback från kunder som arbetar med de olika lösningarna.

Det ursprungliga användargränssnittet för Adobe Experience Manager (tidigare CQ5), som introducerades 2008 och används av kunder som kör version 5.0-5.6.1, finns i AEM 6.4. Detta garanterar att kunderna kan uppdatera till 6.4 och dra nytta av en uppdaterad plattform med nya funktioner samtidigt som de använder samma användargränssnitt.

Adobe rekommenderar att man planerar att gå över till det nya användargränssnittet under 2018/2019. Detta kan antingen göras under uppdateringen till 6.4, eller i ett separat projekt efter uppdateringen som innehåller nödvändiga justeringar av anpassningarna och komponentdialogrutorna.

Adobe planerar inte att göra fler förbättringar av det klassiska användargränssnittet från och med AEM 6.4. Observera att Classic-användargränssnittet fortfarande stöds fullt ut när det är inaktuellt.

## Regler och Recommendations {#rules-and-recommendations}

Nedan följer en lista med rekommendationer från Product Management för Adobe Experience Manager 6.4:

<table> 
 <tbody> 
  <tr> 
   <th>Mitt projekt...</th> 
   <th>Recommendations</th> 
  </tr> 
  <tr> 
   <td>Börjar bara använda Adobe Experience Manager.</td> 
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
     <li>Uppdatera komponentdialogrutorna så att de använder Dialogrutan Coral 3. Adobe rekommenderar att du använder <a href="/help/sites-developing/modernization-tools.md">AEM</a> för att uppdatera komponenterna.</li> 
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
     <li>Uppdatera komponentdialogrutorna så att de använder Dialogrutan Coral 3. Adobe rekommenderar att du använder <a href="/help/sites-developing/modernization-tools.md">AEM</a> för att uppdatera komponenterna.</li> 
     <li>Konfigurera ContextHub (ersättning för ClientContext) och uppdatera sidmallarna så att ContextHub används. Observera att ContextHub har ett kompatibilitetsläge som tillåter inläsning av anpassade ClientContext-arkiv.</li> 
    </ol> </td> 
  </tr> 
  <tr> 
   <td><p>Har använt CQ/AEM i många år.</p> <p>Har utökat produktgränssnittet (t.ex. platsadministratör) och byggt komponenter med omfattande redigeringsdialogrutor.</p> </td> 
   <td><p>Uppdatera till 6.4 och konfigurera det klassiska användargränssnittet som standard för sidredigering för alla användare. Se <a href="#selecting-your-ui">Välja användargränssnitt</a>.</p> <p>Starta sedan ett projekt för att anpassa och optimera komponentdialogrutorna i Coral 3-format. Se <a href="#resources-to-help">Resurser att hjälpa</a>.<br /> </p> </td> 
  </tr> 
 </tbody> 
</table>

## Vanliga frågor {#faq}

Läs artikeln i kunskapsbasen [Vanliga frågor om redigering av Touch UI](https://helpx.adobe.com/experience-manager/kb/index/touchui_faq.html), för närmare uppgifter, inklusive information om det klassiska användargränssnittets borttagningsschema.

## Välja användargränssnitt {#selecting-your-ui}

Se [Välja användargränssnitt](/help/sites-authoring/select-ui.md) om du vill ha information om hur du konfigurerar systemet.

## Touchoptimerad gränssnittsstatus {#touch-optimized-ui-status}

Mer information om förbättringarna i det pekoptimerade användargränssnittet i AEM 6.3 finns i [Nyheter](/help/release-notes/release-notes.md#what-s-new) i versionsinformationen.

En fullständig översikt finns i [Funktionsstatus för Touch UI](/help/release-notes/touch-ui-features-status.md) page

## Resurser att hjälpa {#resources-to-help}

För bakgrundsinformation om grundläggande hantering:

* [Arbeta med redigeringsmiljön](/help/sites-authoring/home.md).
* [Redigeringssidor](/help/sites-authoring/author-environment-tools.md).

Detaljerad utvecklingsinformation:

* [Touchoptimerad gränssnittsarkitektur](/help/sites-developing/touch-ui-concepts.md).
* Använd [AEM](/help/sites-developing/modernization-tools.md) om du vill konvertera komponentredigeringsdialogrutor från det klassiska användargränssnittet till det pekoptimerade användargränssnittet.

* [Struktur för det pekoptimerade användargränssnittet](/help/sites-developing/touch-ui-structure.md).

* [Anpassa konsolerna i det pekoptimerade användargränssnittet](/help/sites-developing/customizing-consoles-touch.md) (innehåller exempelkod).

* [Anpassa sidutveckling i det pekoptimerade användargränssnittet](/help/sites-developing/customizing-page-authoring-touch.md) (innehåller exempelkod).

* [Granite UI-dokumentation](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/index.html).
