---
title: Versionsinformation om Livefyre Feature Pack 2.0.6
seo-title: Livefyre Feature Pack 2.0.6 Release Notes
description: Versionsinformation om Livefyre Feature Pack 2.0.6
seo-description: Livefyre Feature Pack 2.0.6 Release Notes
uuid: 81ee0527-72c3-4530-80f1-c802ddbe62d0
products: SG_EXPERIENCEMANAGER/6.4
contentOwner: alba
discoiquuid: d445bcfb-7712-472f-bfb4-a8811c2bc4f1
exl-id: e09d2d59-41f0-4cf2-bcf3-ec3dbc3b8474
source-git-commit: 0f4f8c2640629f751337e8611a2c8f32f21bcb6d
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 1%

---

# Versionsinformation om Livefyre Feature Pack 2.0.6 {#livefyre-feature-pack-release-notes}

## Versionsinformation {#release-information}

| Produkter | Livefyre Feature Pack 2.0.6 |
|--- |--- |
| Version | 2.0.6 |
| Typ | Funktionsrelease |
| Date | 31 augusti 2018 |
| Hämta URL | Kontakta administratören |
| Kompatibilitet (*) | AEM 6.4 SP1, 6.4, 6.3 GA och 6.2 SP1 |
| Beskrivning | Med det här paketet kan du integrera Livefyres branschledande kurationsfunktioner med AEM, så att du kan publicera användaranpassat användargenererat innehåll (UGC) från sociala nätverk till webbplatsen på några minuter. |

## Vad ingår i Livefyre Feature Pack 2.0.6 {#what-is-included-in-livefyre-feature-pack}

Det här paketet integrerar Livefyres branschledande kurationsfunktioner med AEM, så att du kan publicera användargenererat innehåll (UGC) från sociala nätverk till webbplatsen på några minuter. Det här paketet innehåller tre olika komponenter:

**Importera UGC-innehåll till AEM Assets**

* Importera användargenererat Twitter- och Instagram-innehåll (UGC) från Livefyre Studio till AEM Assets med UGC-importeraren.
* Gå till Livefyre Library.
* Sök i realtid på Twitter och Instagram med Livefyre Social Search.
* Hantera rättigheter i användargenererat innehåll.

**Lägg till Livefyre-komponenter i AEM Sites eller Communities**

* Bygg och anpassa dynamiska och engagerande upplevelser direkt med en serie sociala komponenter som kartor, gallerier och Media Walls.
* Publicera UGC i AEM Sites eller Communities.

**Importera produktkataloger till Livefyre med AEM Commerce**

* Integrera smidigt din befintliga produktkatalog i Livefyre för att öka användarengagemanget och konverteringsgraden på era sajter, liksom för att leverera användarvänliga användarupplevelser.
* Redigera eller ta bort artiklar i din AEM Commerce-produktkatalog och uppdatera automatiskt ändringar i Livefyre.

Hjälp med installationen finns i [Integrera med Livefyre](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/livefyre.html).

### Ytterligare versionsinformation {#additional-release-information}

På grund av uppdateringar som påverkar sammanställningen av innehåll från icke-företagskonton från Instagram kan vi inte längre lägga in kommentarer åt dig eller automatiskt söka efter svar från författaren. [Klicka här för mer information](https://developers.facebook.com/blog/post/2018/04/04/facebook-api-platform-product-changes/).

>[!NOTE]
>
>Livefyre Feature Pack 2.0.6 stöder inte AEM Classic UI.

#### Ny funktion eller förbättring {#new-feature-or-improvement}

* Lagt till möjligheten att söka efter UGC innan du ställer in behörigheter för sociala konton i Livefyre. Du måste konfigurera sociala konton för att begära rättigheter, eller åsidosätta rättighetsbegäran om du äger innehållet.
* Instagram och Twitter [Arbetsflöde för begäran om UGC-rättigheter](https://experienceleague.adobe.com/docs/experience-manager-64/administering/integration/livefyre.html) har uppdaterats för att uppfylla de senaste API:erna.
* Rättighetsstatus och lämpliga åtgärder visas nu på skärmen för rättighetsförfrågan.

#### Felkorrigeringar {#bug-fixes}

* Ett problem har korrigerats där ett socialt konto i Livefyre Studio som används för rättighetsbegäran orsakade ett fel när UGC-biblioteket lästes in i AEM.
* Ett problem har korrigerats där inventeringen av tillgångar i Livefyre studio inte matchade inventeringen i AEM UGC-bibliotek.
* Korrigerade ett fel i UGC-biblioteket där filtrerade resultat som visades efter att filteralternativen återställdes.
* Korrigerade ett problem med AEM Commerce där knappar för att ringa till åtgärd dirigerade om användare till fel URL.
* Korrigerade ett problem i AEM Sites där flera komponenter i platshållaren för parsys försvann när du drog och släppte dem.
* Korrigerade ett problem där inaktiverade sociala konton var tillgängliga att välja från när en rättighetsbegäran skickades.
* Ett problem har korrigerats där ett fel uppstod när UGC-innehåll från resurser till platser skulle dras och släppas.
* Ett problem har korrigerats där appen inte skapades när du drog och släppte Chat- och LiveBlogg-komponenter till webbplatser.
* Korrigerade ett problem där kommentarsappen genererade ett fel när användare försökte kommentera.
* Ett problem har korrigerats där en extra nod skapades i Java Content Repository när Livefyre Media Wall App lades till på en webbplats.
* Korrigerade ett problem som orsakade sidbrytningar och konsolfel i Instagram UGC-sökning.
* Ett problem har korrigerats där Instagram användarikoner genererade API-fel i Assets.
* Ett problem har korrigerats där appen Recensioner lades till på en webbplats utan något fördefinierat format.
* Korrigerade ett problem med Touch UI-funktioner och infogad redigering.
* Ett problem som orsakade ett fel vid import av vissa bildresurser från Instagram har korrigerats.
* Ett problem har korrigerats där Livefyre HTTP-klienten i AEM inte hade stöd för proxykonfigurationen.
