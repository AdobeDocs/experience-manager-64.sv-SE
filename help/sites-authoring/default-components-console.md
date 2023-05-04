---
title: Komponentkonsol
seo-title: Components Console
description: Komponentkonsol
seo-description: null
uuid: 308b7fa1-9525-43f3-8c15-1076485b3f8c
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 8774c38a-abd2-4dc2-868e-d6760c96f3f6
exl-id: fa583a06-e75c-41de-a977-7e459ab8bca9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 18%

---

# Komponentkonsol{#components-console}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med komponentkonsolen kan du bläddra igenom alla komponenter som definierats för instansen och visa nyckelinformation för varje komponent.

Den kan nås från **verktyg** -> **Allmänt** -> **Komponenter**. I konsolen finns kortvyn och listvyn. Eftersom det inte finns någon trädstruktur för komponenter är kolumnvyn inte tillgänglig.

![chlimage_1-301](assets/chlimage_1-301.png)

>[!NOTE]
>
>Komponentkonsolen visar alla komponenter i systemet. The [Komponentbläddraren](/help/sites-authoring/author-environment-tools.md#components-browser) visar komponenter som är tillgängliga för författare och döljer komponentgrupper som börjar med en punkt ( `.`).

## Sökning {#search-features}

Med ikonen **Endast innehåll** (överst till vänster) kan du öppna **sökpanelen** och söka efter och/eller filtrera komponenterna:

![chlimage_1-302](assets/chlimage_1-302.png)

## Komponentinformation {#component-details}

Om du vill visa information om en viss komponent trycker/klickar du på den nödvändiga resursen. Tre flikar innehåller:

* **Egenskaper**

   ![screen_shot_2018-03-27at165847](assets/screen_shot_2018-03-27at165847.png)

   På fliken Egenskaper kan du:

   * Visa komponentens allmänna egenskaper.
   * Visa hur [ikon eller förkortning har definierats](/help/sites-developing/components-basics.md#component-icon-in-touch-ui) för komponenten.

      * Om du klickar på ikonens källa kommer du till den komponenten.
   * Visa **Resurstyp** och **Resurssupertyp** (om det är definierat) för komponenten.

      * Om du klickar på Resurssupertypen kommer du till den komponenten.
   >[!NOTE]
   >
   >För `/apps` går inte att redigera vid körning, komponentkonsolen är skrivskyddad.

* **Profiler**

   ![chlimage_1-303](assets/chlimage_1-303.png)

* **Live-användning**

   ![chlimage_1-304](assets/chlimage_1-304.png)

   >[!CAUTION]
   >
   >På grund av den typ av information som samlas in för den här vyn kan det ta en stund att sortera/visa informationen.

* **Dokumentation**

   Om utvecklaren har tillhandahållit [dokumentation för komponenten](/help/sites-developing/developing-components.md#documenting-your-component)visas den på **Dokumentation** -fliken. Om det inte finns någon tillgänglig dokumentation kan du **Dokumentation** kommer inte att visas.

   ![chlimage_1-305](assets/chlimage_1-305.png)
