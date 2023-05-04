---
title: Versionsinformation för AEM Communities
seo-title: AEM Communities
description: Versionsinformation om Adobe Experience Manager 6.4 Communities.
seo-description: Release notes specific to Adobe Experience Manager 6.4 Communities.
uuid: 2de9f511-2a61-4003-9b2c-d6728bc9d57a
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 55a0b70e-5212-408b-8560-6e758bd8bb10
exl-id: 3a341e72-01c5-4c63-8942-6320e5b08440
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '353'
ht-degree: 0%

---

# Versionsinformation för AEM Communities {#aem-communities-release-notes}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Det här avsnittet innehåller information om förbättringarna av AEM Communities sedan version 6.3. Mer information om de nya funktionerna finns i [Nyheter i AEM 6.4 Communities](/help/communities/whats-new-aem-communities.md).

Om du vill ha den senaste versionen går du till [Distribuera webbgrupper](/help/communities/deploy-communities.md#latest-releases) i dokumentationen.

## Huvudförbättringar {#main-improvements}

Community Sites:

* Community-administratörer kan nu:

   * Ta bort permanent communityplatser
   * Välj en kontextmedveten konfigurationsmapp för communityplatser

Community-grupper:

* Community-administratörer kan nu:

   * Ta bort grupper permanent
   * Skapa communitygrupper på flera språk
   * Lägg till aktiveringskatalog och tilldelningar i communitygrupper

* Aktivitetshanterare kan nu

   * Skapa och tilldela resurser och inlärningsmöjligheter i communitygrupper

Filbibliotek:

* Community-medlemmar har nu flera förbättringar av filbiblioteket, t.ex. sorteringsordning, taggning...

Meddelanden:

* Medlemmar i communityn får nu meddelanden när bidrag som genomgått en modereringsprocess har godkänts

Moderering:

* Automatiserat filter för skräppostidentifiering
* Community-moderatorer har ytterligare modereringsfilter (t.ex. besvarade/obesvarade frågor)
* Community-moderatorer kan skapa bokmärken och länka moderering till fördefinierade filter (t.ex. alla inlägg som väntar på godkännande)

Övergripande kompatibilitet med grundläggande förändringar i AEM 6.4.

Obs! alla dessa funktioner finns även för AEM 6.3. Läs versionsinformationen för AEM Communities om du vill veta mer om [6.3](https://helpx.adobe.com/experience-manager/6-3/release-notes.html).

## Kända fel {#known-issues}

* **Moderering** - Det går inte att ta bort överordnat inlägg som en enda borttagningsåtgärd från gränssnittet för massmoderering (CQ-4236797)
* **Konsol** - Länken Glömt användarnamn eller lösenord dirigeras om till inloggningssidan i stället för motsvarande formulär för lösenordsåterhämtning (CQ-4237682)

## Välj funktioner {#select-features}

Expertbedömning (*Powered by Sensei*) - används för att möjliggöra spel, vilket är ett effektivt sätt att uppmuntra och belöna värdefullt communitybeteende. Det kan också användas för att identifiera experter för rekommendationer eller marknadsföring.

## Demonstrationer {#demonstrations}

Alla dessa funktioner kan visas med [AEM Demo Machine](https://github.com/Adobe-Marketing-Cloud/aem-demo-machine/wiki) som är tillgängliga offentligt på GitHub.com när du använder AEM Communities demoscenario och även inom den nya referensimplementeringen av We.Retail.
