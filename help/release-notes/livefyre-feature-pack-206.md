---
title: Versionsinformation om Livefyre Feature Pack 2.0.6
seo-title: Versionsinformation om Livefyre Feature Pack 2.0.6
description: Versionsinformation om Livefyre Feature Pack 2.0.6
seo-description: Versionsinformation om Livefyre Feature Pack 2.0.6
uuid: 81ee0527-72c3-4530-80f1-c802ddbe62d0
products: SG_EXPERIENCEMANAGER/6.4
contentOwner: alba
discoiquuid: d445bcfb-7712-472f-bfb4-a8811c2bc4f1
translation-type: tm+mt
source-git-commit: f1bf1545689b977a0f5074954df224db58cbd695
workflow-type: tm+mt
source-wordcount: '653'
ht-degree: 1%

---


# Versionsinformation om Livefyre Feature Pack 2.0.6 {#livefyre-feature-pack-release-notes}

## Versionsinformation {#release-information}

<table> 
 <tbody>
  <tr>
   <td>Produkter</td> 
   <td>Livefyre Feature Pack 2.0.6</td> 
  </tr>
  <tr>
   <td>Version</td> 
   <td>2.0.6</td> 
  </tr>
  <tr>
   <td>Typ</td> 
   <td>Funktionsrelease</td> 
  </tr>
  <tr>
   <td>Date</td> 
   <td>31 augusti 2018</td> 
  </tr>
  <tr>
   <td>Hämta URL<br /> </td> 
   <td>Kontakta administratören</td> 
  </tr>
  <tr>
   <td>Kompatibilitet (*)</td> 
   <td>AEM 6.4 SP1, 6.4, 6.3 GA och 6.2 SP1</td> 
  </tr>
  <tr>
   <td>Beskrivning</td> 
   <td>Med det här paketet kan du integrera Livefyres branschledande kurationsfunktioner med din AEM-instans, så att du kan publicera användargenererat innehåll (UGC) från sociala nätverk till din webbplats på några minuter.</td> 
  </tr>
 </tbody>
</table>

## Vad ingår i Livefyre Feature Pack 2.0.6 {#what-is-included-in-livefyre-feature-pack}

Det här paketet integrerar Livefyres branschledande kurationsfunktioner med din AEM-instans så att du kan publicera användargenererat innehåll (UGC) från sociala nätverk till din webbplats på några minuter. Det här paketet innehåller tre olika komponenter:

**Importera UGC-innehåll till AEM Assets**

* Importera Twitter- och Instagram-användargenererat innehåll (UGC) från Livefyre Studio till AEM Assets med UGC-importeraren.
* Gå till Livefyre Library.
* Sök i realtid på Twitter och Instagram med Livefyre Social Search.
* Hantera rättigheter i användargenererat innehåll.

**Lägg till Livefyre-komponenter i AEM Sites eller Communities**

* Bygg och anpassa dynamiska och engagerande upplevelser direkt med en serie sociala komponenter som kartor, gallerier och Media Walls.
* Publicera UGC i AEM Sites eller Communities.

**Importera produktkataloger till Livefyre med AEM Commerce**

* Integrera smidigt din befintliga produktkatalog i Livefyre för att öka användarengagemanget och konverteringsgraden på era sajter, liksom för att leverera användarvänliga användarupplevelser.
* Redigera eller ta bort artiklar i din AEM Commerce-produktkatalog och uppdatera automatiskt ändringar i Livefyre.

Hjälp med installationen finns i [Integrera med Livefyre](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html).

### Ytterligare versionsinformation {#additional-release-information}

På grund av uppdateringar som påverkar sammanställningen av innehåll från användarkonton i Instagram kan vi inte längre publicera kommentarer åt dig eller automatiskt söka efter svar från författaren. [Klicka här om du vill veta mer](https://developers.facebook.com/blog/post/2018/04/04/facebook-api-platform-product-changes/).

>[!NOTE]
>
>Livefyre Feature Pack 2.0.6 stöder inte AEM Classic UI.

#### Ny funktion eller förbättring {#new-feature-or-improvement}

* Lagt till möjligheten att söka efter UGC innan du ställer in behörigheter för sociala konton i Livefyre. Du måste konfigurera sociala konton för att begära rättigheter, eller åsidosätta rättighetsbegäran om du äger innehållet.
* Instagram och Twitter [UGC-rättighetsarbetsflödet](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/livefyre.html) har uppdaterats för att uppfylla de senaste API:erna.
* Rättighetsstatus och lämpliga åtgärder visas nu på skärmen för rättighetsförfrågan.

#### Felkorrigeringar {#bug-fixes}

* Ett problem har korrigerats där ett socialt konto i Livefyre Studio som används för rättighetsbegäran orsakade ett fel när UGC-biblioteket lästes in i AEM.
* Ett problem har korrigerats där inventeringen av tillgångar i Livefyre-studion inte matchade inventeringen i AEM UGC-biblioteket.
* Korrigerade ett fel i UGC-biblioteket där filtrerade resultat som visades efter att filteralternativen återställdes.
* Korrigerade ett problem med AEM Commerce där knappar för att ringa till åtgärd dirigerade om användare till fel URL.
* Ett problem har korrigerats i AEM Sites där flera komponenter försvann när du drog och släppte dem i platshållaren.
* Korrigerade ett problem där inaktiverade sociala konton var tillgängliga att välja från när en rättighetsbegäran skickades.
* Ett problem har korrigerats där ett fel uppstod när UGC-innehåll från resurser till platser skulle dras och släppas.
* Ett problem har korrigerats där appen inte skapades när du drog och släppte Chat- och LiveBlogg-komponenter till webbplatser.
* Korrigerade ett problem där kommentarsappen genererade ett fel när användare försökte kommentera.
* Ett problem har korrigerats där en extra nod skapades i Java Content Repository när Livefyre Media Wall App lades till på en webbplats.
* Korrigerade ett problem som orsakade sidbrytningar och konsolfel i Instagram UGC-sökning.
* Ett problem har korrigerats där användarikoner för Instagram genererade API-fel i Assets.
* Ett problem har korrigerats där appen Recensioner lades till på en webbplats utan något fördefinierat format.
* Korrigerade ett problem med Touch UI-funktioner och infogad redigering.
* Ett problem som orsakade ett fel vid import av vissa Instagram-bildresurser har korrigerats.
* Ett problem har korrigerats där Livefyre HTTP-klienten i AEM inte hade stöd för proxykonfiguration.

