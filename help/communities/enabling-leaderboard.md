---
title: Funktion för resultatavla
seo-title: Funktion för resultatavla
description: Lägga till en Leaderboard-komponent på en sida
seo-description: Lägga till en Leaderboard-komponent på en sida
uuid: 2a766b63-3ab4-44cd-8a26-629a71b837ea
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 1e96d388-8517-4a84-bb0a-d49567eb4bdf
translation-type: tm+mt
source-git-commit: 1bbd917ef20c4a618e93af66ffe8a6cfc8448e78

---


# Funktion för resultatavla {#leaderboard-feature}

## Introduktion {#introduction}

Komponenten `Leaderboard` ger möjlighet att få en uppfattning om hur medlemmarna interagerar inom communityn genom att rangordna medlemmar enligt poäng (grundläggande poängsättning) eller deras sakkunskap (avancerad poängsättning).

Innan du tar med huvudpanelskomponenten på en sida måste du konfigurera [Scoring and Badges](implementing-scoring.md)för Communities.

Detta avsnitt i dokumentationen beskriver

* Lägga till `Leaderboard` komponenten på en [communitywebbplats](overview.md#community-sites)

* Konfigurationsinställningar för `Leaderboard` komponenten

## Lägga till en huvudpanel på en sida {#adding-a-leaderboard-to-a-page}

Om du vill lägga till en `Leaderboard` komponent på en sida i redigeringsläge letar du reda på komponenten

* `Communities / Leaderboard`

och dra den till rätt plats på en sida.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När komponenten placeras på en sida i en community-webbplats är det så här den visas:

![chlimage_1-8](assets/chlimage_1-8.png)

## Konfigurerar huvudpanel {#configuring-leaderboard}

Markera den monterade `Leaderboard` komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![chlimage_1-9](assets/chlimage_1-9.png) ![chlimage_1-10](assets/chlimage_1-10.png)

### Fliken Inställningar {#settings-tab}

Under fliken **[!UICONTROL Inställningar]** anger du vilken information om medlemmen som ska visas:

* **[!UICONTROL Visningsnamn]** Ett beskrivande namn som ska visas för styrelsen och som återspeglar reglerna som valts för att visa märken och bakgrundsmusik.

   Standard är `Leaderboard`, om inget anges.

* **[!UICONTROL Badge]** Om det här alternativet är markerat inkluderas en kolumn för ikoner för emblem i rankningslistan.

   Standard är avmarkerat.

* **[!UICONTROL Om du markerar alternativet]** Badge Name (Märkesnamn) inkluderas en kolumn för märkordsnamnet i resultatlistan.

   Standard är avmarkerat.

* **[!UICONTROL Använd Avatar]** Om du markerar det här alternativet inkluderas medlemmens avatarbild i ledningsgruppen bredvid namnlänken till medlemsprofilen.

   Standard är avmarkerat.

### Fliken Regler {#rules-tab}

Under fliken **[!UICONTROL Regler]** , communitywebbplatsen och dess regler för poäng och badging

* **[!UICONTROL Regelplats]**(obligatoriskt) Plats där regeln Klassificering/badging är konfigurerad.

* **[!UICONTROL Poängregel]**(obligatorisk) Specifik regel som genererar de poäng som ska visas.

* **[!UICONTROL Badging-regel]**(obligatoriskt) Specifik regel som genererar märket som ska visas.

* **[!UICONTROL Visningsgräns]** Antal medlemmar som ska visas per sida.

   Standardvärdet är 10.

## Exempel: Deltagare i ledningsgruppen {#example-participants-leaderboard}

Den här resultatöversikten är en följd av att grundläggande poängregler har tillämpats.

Konfiguration av huvudpanelskomponent:

* **[!UICONTROL Fliken Inställningar]** :

   * Visningsnamn = `Participation Board`
   * `checked`:

      * Badge
      * Märkesnamn
      * Använd avatar

* **[!UICONTROL Fliken Regler]** :

   * Regelplats = `/content/sites/communities/jcr:content`
   * Poängregel = `/etc/community/scoring/rules/forums-scoring`
   * Badningsregel = `/etc/community/badging/rules/reference-badging`
   * Visningsgräns = `10`

![chlimage_1-11](assets/chlimage_1-11.png)

## Exempel: Experter Leaderboard {#example-experts-leaderboard}

Den här resultatöversikten är en följd av att avancerade poängregler har tillämpats.

Konfiguration av huvudpanelskomponent:

* **[!UICONTROL Fliken Inställningar]** :

   * Visningsnamn = `Expertise Board`
   * `checked`:

      * Badge
      * Använd avatar

* **[!UICONTROL Fliken Regler]** :

   * Regelplats = `/content/sites/communities/jcr:content`
   * Poängregel = `/etc/community/scoring/rules/adv-forums-scoring`
   * Badningsregel = `/etc/community/badging/rules/adv-forums-badging`
   * Visningsgräns = `10`

![chlimage_1-12](assets/chlimage_1-12.png)

## Additional Information {#additional-information}

Mer information finns på sidan [Ledarpanel Essentials](leaderboard.md) för utvecklare.

Instruktioner för hur du skapar regler finns på sidan [Värderingslista och badges](implementing-scoring.md) för webbgrupper för administratörer.
