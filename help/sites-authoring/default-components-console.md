---
title: Komponentkonsol
seo-title: Komponentkonsol
description: 'null'
seo-description: 'null'
uuid: 308b7fa1-9525-43f3-8c15-1076485b3f8c
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 8774c38a-abd2-4dc2-868e-d6760c96f3f6
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Komponentkonsol{#components-console}

Med komponentkonsolen kan du bläddra igenom alla komponenter som definierats för instansen och visa nyckelinformation för varje komponent.

Den kan nås via **Verktyg** -> **Allmänt** -> **Komponenter**. I konsolen är kort- och listvyn tillgängliga. Eftersom det inte finns någon trädstruktur för komponenter är kolumnvyn inte tillgänglig.

![chlimage_1-301](assets/chlimage_1-301.png)

>[!NOTE]
>
>Komponentkonsolen visar alla komponenter i systemet. I [komponentwebbläsaren](/help/sites-authoring/author-environment-tools.md#components-browser) visas komponenter som är tillgängliga för författare och alla komponentgrupper som börjar med en punkt ( `.`) döljs.

## Sökning {#search-features}

Med ikonen Endast **** innehåll (överst till vänster) kan du öppna **sökpanelen** och söka efter och/eller filtrera komponenterna:

![chlimage_1-302](assets/chlimage_1-302.png)

## Komponentinformation {#component-details}

Om du vill visa information om en viss komponent trycker/klickar du på den nödvändiga resursen. Tre flikar innehåller:

* **Egenskaper**

   ![screen_shot_2018-03-27at165847](assets/screen_shot_2018-03-27at165847.png)

   På fliken Egenskaper kan du:

   * Visa komponentens allmänna egenskaper.
   * Visa hur [ikonen eller förkortningen har definierats](/help/sites-developing/components-basics.md#component-icon-in-touch-ui) för komponenten.

      * Om du klickar på ikonens källa kommer du till den komponenten.
   * Visa komponentens **resurstyp** och **resurssupertyp** (om den är definierad).

      * Om du klickar på Resurssupertypen kommer du till den komponenten.
   >[!NOTE]
   >
   >Eftersom `/apps` inte kan redigeras under körning är komponentkonsolen skrivskyddad.

* **Profiler**

   ![chlimage_1-303](assets/chlimage_1-303.png)

* **Live-användning**

   ![chlimage_1-304](assets/chlimage_1-304.png)

   >[!CAUTION]
   >
   >På grund av den typ av information som samlas in för den här vyn kan det ta en stund att sortera/visa informationen.

* **Dokumentation**

   Om utvecklaren har tillhandahållit [dokumentation för komponenten](/help/sites-developing/developing-components.md#documenting-your-component)visas den på fliken **Dokumentation** . Om det inte finns någon tillgänglig dokumentation visas inte fliken **Dokumentation** .

   ![chlimage_1-305](assets/chlimage_1-305.png)

