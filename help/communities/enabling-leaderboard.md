---
title: Funktion för resultatavla
seo-title: Leaderboard Feature
description: Lägga till en Leaderboard-komponent på en sida
seo-description: Adding a Leaderboard component to a page
uuid: 2a766b63-3ab4-44cd-8a26-629a71b837ea
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 1e96d388-8517-4a84-bb0a-d49567eb4bdf
exl-id: 1ebe0cbb-33be-4101-92e3-64253a7f7f31
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Funktion för resultatavla {#leaderboard-feature}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

The `Leaderboard` -komponenten ger möjlighet att få en uppfattning om hur medlemmarna interagerar inom communityn genom att rangordna medlemmar enligt poäng (grundläggande poängsättning) eller deras sakkunskap (avancerad poängsättning).

Innan du tar med huvudpanelskomponenten på en sida måste du konfigurera [Communities Scoring and Badges](implementing-scoring.md).

Detta avsnitt i dokumentationen beskriver

* Lägga till `Leaderboard` till en [communitywebbplats](overview.md#community-sites)

* Konfigurationsinställningar för `Leaderboard` komponent

## Lägga till en huvudpanel på en sida {#adding-a-leaderboard-to-a-page}

Lägga till en `Leaderboard` till en sida i redigeringsläge, leta reda på komponenten

* `Communities / Leaderboard`

och dra den till rätt plats på en sida.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När komponenten placeras på en sida i en community-webbplats är det så här den visas:

![chlimage_1-8](assets/chlimage_1-8.png)

## Konfigurerar huvudpanel {#configuring-leaderboard}

Markera den monterade `Leaderboard` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-9](assets/chlimage_1-9.png) ![chlimage_1-10](assets/chlimage_1-10.png)

### Fliken Inställningar {#settings-tab}

Under **[!UICONTROL Settings]** anger du vilken information om medlemmen som visas:

* **[!UICONTROL Display Name]**
Ett beskrivande namn som ska visas för styrelsen, som återspeglar reglerna som valts för att visa märken och poäng.

   Standard är `Leaderboard`, om inget anges.

* **[!UICONTROL Badge]**
Om du markerar det här alternativet inkluderas en kolumn för ikoner för emblem i rankningspanelen.

   Standard är avmarkerat.

* **[!UICONTROL Badge Name]**
Om du markerar det här alternativet inkluderas en kolumn för märkordsnamnet i resultatlistan.

   Standard är avmarkerat.

* **[!UICONTROL Use Avatar]**
Om det här alternativet är markerat inkluderas medlemmens avatarbild i ledningsgruppen bredvid namnlänken till medlemsprofilen.

   Standard är avmarkerat.

### Fliken Regler {#rules-tab}

Under **[!UICONTROL Rules]** -fliken, communitywebbplatsen och dess regler för poäng och badning

* **[!UICONTROL Rule Location]**
(obligatoriskt) Plats där poängsättningsregeln/badging-regeln är konfigurerad.

* **[!UICONTROL Scoring Rule]**
(obligatoriskt) Specifik regel som genererar poängen som ska visas.

* **[!UICONTROL Badging Rule]**
(obligatoriskt) Specifik regel som genererar märket som ska visas.

* **[!UICONTROL Display Limit]**
Antal medlemmar som ska visas per sida.

   Standardvärdet är 10.

## Exempel: Deltagare i ledningsgruppen {#example-participants-leaderboard}

Den här resultatöversikten är en följd av att grundläggande poängregler har tillämpats.

Konfiguration av huvudpanelskomponent:

* **[!UICONTROL Settings]** tab:

   * Visningsnamn = `Participation Board`
   * `checked`:

      * Badge
      * Märkesnamn
      * Använd avatar

* **[!UICONTROL Rules]** tab:

   * Regelplats = `/content/sites/communities/jcr:content`
   * Poängregel = `/etc/community/scoring/rules/forums-scoring`
   * Badningsregel = `/etc/community/badging/rules/reference-badging`
   * Visningsgräns = `10`

![chlimage_1-11](assets/chlimage_1-11.png)

## Exempel: Experter Leaderboard {#example-experts-leaderboard}

Den här resultatöversikten är en följd av att avancerade poängregler har tillämpats.

Konfiguration av huvudpanelskomponent:

* **[!UICONTROL Settings]** tab:

   * Visningsnamn = `Expertise Board`
   * `checked`:

      * Badge
      * Använd avatar

* **[!UICONTROL Rules]** tab:

   * Regelplats = `/content/sites/communities/jcr:content`
   * Poängregel = `/etc/community/scoring/rules/adv-forums-scoring`
   * Badningsregel = `/etc/community/badging/rules/adv-forums-badging`
   * Visningsgräns = `10`

![chlimage_1-12](assets/chlimage_1-12.png)

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande om Ledningsbord](leaderboard.md) för utvecklare.

Instruktioner för hur du skapar regler finns i [Communities Scoring and Badges](implementing-scoring.md) för administratörer.
