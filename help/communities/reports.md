---
title: Rapportkonsol
seo-title: Rapportkonsol
description: Lär dig hur du får åtkomst till rapporter
seo-description: Lär dig hur du får åtkomst till rapporter
uuid: 580f5eb8-24b2-4404-90d4-81f7108d1ee6
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 0042893e-3d2c-469e-8759-404be16e7436
translation-type: tm+mt
source-git-commit: 63001012f0d865c2548703ea387c780679128ee7

---


# Rapportkonsol {#reports-console}

## Översikt {#overview}

För AEM Communities finns det olika rapporter som kan nås på flera sätt från författarmiljön.

De olika rapporterna är i allmänhet följande:

* [Uppdragsrapport](#assignments-report) - för en community [för](overview.md#enablement-community)aktivering ger en översikt över elevens framsteg i sina uppdrag, inklusive ett associerat poängvärde om SCORM-standarden implementeras
* [Vyrapport](#views-report) - ger en översikt över vad communitymedlemmar och besökare tycker om communitysajter
* [Inläggsrapport](#posts-report) - innehåller en lista över olika typer av inlägg från communitymedlemmar på valfri communitywebbplats

När [Adobe Analytics är aktiverat](sites-console.md#analytics)innehåller rapporterna antalet visningar, uppspelningar, kommentarer och omdömen för varje aktiveringsresurs över tiden

Tabellrapporter kan exporteras i CSV-format för efterföljande bearbetning.

## Rapporteringskonsoler {#reporting-consoles}

### Rapporter om communitysajter {#reports-for-community-sites}

* Från global navigering: **[!UICONTROL Navigation > Communities > Reports]**
* Välj från
   * **[!UICONTROL Uppdragsrapport]**
      * Generera en rapport för den valda communityplatsen, användaren eller gruppen samt tilldelningen
   * **[!UICONTROL Inläggsrapport]**
      * Generera en rapport för den valda communityplatsen, innehållstypen och tidsperioden
   * **[!UICONTROL Vyrapport]**
      * Generera en rapport för den valda communityplatsen, innehållstypen och tidsperioden
         ![chlimage_1-156](assets/chlimage_1-156.png)

### Rapporter om aktiveringsresurser och utbildningsvägar {#reports-for-enablement-resources-and-learning-paths}

* Från global navigering: **[!UICONTROL Navigering > Communities > Resources]**
* Välj en befintlig webbplats för aktiveringscommunityn
   * Välj **[!UICONTROL rapportikonen]** om du vill generera rapporter som täcker alla aktiveringsresurser
   * Välj en utbildningsväg för aktivering
   * Välj ikonen **[!UICONTROL Rapport]** om du vill generera rapporter för
      * De medföljande aktiveringsresurserna
      * De studerande som är tilldelade inlärningsbanan
* Rapporterna innehåller följande:
   * Tabelldata, kan hämtas som CSV
      * Identifiera studerande
      * Deras status
      * Om du har tilldelats eller fått åtkomst via katalog
      * Antal kommentarer
      * Stjärngradering

Mer information finns i avsnittet [Rapporter](resources.md#report) i resurskonsolen.

## Uppdragsrapport {#assignments-report}

På uppdragskonsolen kan rapporter filtreras efter aktiveringscommunityplats, användare eller grupper samt tilldelning.

Rapporten innehåller information om hur de fortskrider samt eventuella kommentarer eller betyg som lämnats.

![chlimage_1-157](assets/chlimage_1-157.png)

Välj villkor för rapporten:

* **[!UICONTROL Site]** Select an enablement community site
* **[!UICONTROL Användare eller grupp]**
   * Välj Användare om du vill generera en rapport för en elev
   * Välj Grupp om du vill generera en rapport för en grupp deltagareTunneltjänsten kommer åt medlemmar och medlemsgrupper från publiceringsmiljön
* **[!UICONTROL Tilldelning]** Välj bland de aktiveringsresurser som tilldelats de valda eleven/eleven/eleven

Välj **[!UICONTROL Generera]** för att skapa rapporten:

![chlimage_1-158](assets/chlimage_1-158.png)

## Vyrapport {#views-report}

Med hjälp av vykonsolen kan rapporter genereras på sidvisningar av communityfunktioner under en viss tidsperiod.

![chlimage_1-159](assets/chlimage_1-159.png)

Välj villkor för rapporten:

* **[!UICONTROL Site]** Select a community site
* **[!UICONTROL Innehållstypen]** kan välja Allt innehåll eller någon av funktionerna på webbplatsen
* TidsramVälj något av:
   * De senaste 7 dagarna
   * De senaste 30 dagarna
   * De senaste 90 dagarna
   * Förra året

Välj **[!UICONTROL Generera]** för att skapa rapporten:

![chlimage_1-160](assets/chlimage_1-160.png)

## Inläggsrapport {#posts-report}

Med publiceringskonsolen kan rapporter genereras om antalet inlägg till communityfunktioner under en viss tidsperiod.

![chlimage_1-161](assets/chlimage_1-161.png)

Välj villkor för rapporten:

* **[!UICONTROL Site]** Select a community site
* **[!UICONTROL Innehållstypen]** kan välja Allt innehåll eller någon av funktionerna på webbplatsen
* TidsramVälj något av:
   * De senaste 7 dagarna
   * De senaste 30 dagarna
   * De senaste 90 dagarna
   * Förra året

Välj **[!UICONTROL Generera]** för att skapa rapporten:

![chlimage_1-162](assets/chlimage_1-162.png)

## Felsökning {#troubleshooting}

### Inga communitywebbplatser har angetts {#no-community-sites-listed}

Om det inte finns några communitysajter i listan kontrollerar du att Adobe Analytics har aktiverats för en webbplats. Om du väljer rapporter om tilldelningar måste du se till att tilldelningsfunktionen finns i communityplatsens struktur.
