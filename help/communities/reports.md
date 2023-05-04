---
title: Rapportkonsol
seo-title: Reports Console
description: Lär dig hur du får åtkomst till rapporter
seo-description: Learn how to access reports
uuid: 580f5eb8-24b2-4404-90d4-81f7108d1ee6
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 0042893e-3d2c-469e-8759-404be16e7436
role: Admin
exl-id: 766711ea-f3d3-49ab-8346-4e4477c261bd
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 1%

---

# Rapportkonsol {#reports-console}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

För AEM Communities finns det olika rapporter som du kan få åtkomst till på flera sätt från författarmiljön.

De olika rapporterna är i allmänhet följande:

* [Uppdragsrapport](#assignments-report) - för [användargrupper](overview.md#enablement-community), ger en översikt över hur eleverna arbetar med sina uppdrag, inklusive ett poängresultat om SCORM-standarden implementeras
* [Vyrapport](#views-report) - ger en översikt över vad communitymedlemmar och besökare på webbplatser av olika slag
* [Inläggsrapport](#posts-report) - ger en översikt över olika typer av inlägg från communitymedlemmar på alla communitysajter

När [Adobe Analytics är aktiverat](sites-console.md#analytics), rapporter innehåller antalet visningar, uppspelningar, kommentarer och omdömen för varje aktiveringsresurs över tiden

Tabellrapporter kan exporteras i CSV-format för efterföljande bearbetning.

## Rapporteringskonsoler {#reporting-consoles}

### Rapporter om communitysajter {#reports-for-community-sites}

* Från global navigering: **[!UICONTROL Navigation > Communities > Reports]**
* Välj från
   * **[!UICONTROL Assignments Report]**
      * Generera en rapport för den valda communityplatsen, användaren eller gruppen samt tilldelningen
   * **[!UICONTROL Posts Report]**
      * Generera en rapport för den valda communityplatsen, innehållstypen och tidsperioden
   * **[!UICONTROL Views Report]**
      * Generera en rapport för den valda communityplatsen, innehållstypen och tidsperioden
         ![chlimage_1-156](assets/chlimage_1-156.png)

### Rapporter om aktiveringsresurser och utbildningsvägar {#reports-for-enablement-resources-and-learning-paths}

* Från global navigering: **[!UICONTROL Navigation > Communities > Resources]**
* Välj en befintlig webbplats för aktiveringscommunityn
   * Välj **[!UICONTROL Report]** för att generera rapporter som täcker alla aktiveringsresurser
   * Välj en utbildningsväg för aktivering
   * Välj **[!UICONTROL Report]** ikon för att generera rapporter för
      * De medföljande aktiveringsresurserna
      * De studerande som är tilldelade inlärningsbanan
* Rapporterna innehåller följande:
   * Tabelldata, kan hämtas som CSV
      * Identifiera studerande
      * Deras status
      * Om du har tilldelats eller fått åtkomst via katalog
      * Antal kommentarer
      * Stjärngradering

Mer information finns i [Avsnittet Rapporter](resources.md#report) i Resurskonsolen.

## Uppdragsrapport {#assignments-report}

På uppdragskonsolen kan rapporter filtreras efter aktiveringscommunityplats, användare eller grupper samt tilldelning.

Rapporten innehåller information om hur de fortskrider samt eventuella kommentarer eller betyg som lämnats.

![chlimage_1-157](assets/chlimage_1-157.png)

Välj villkor för rapporten:

* **[!UICONTROL Site]**
Välj en community-webbplats för aktivering
* **[!UICONTROL User or Group]**
   * Välj Användare om du vill generera en rapport för en elev
   * Välj Grupp om du vill generera en rapport för en grupp deltagare Tunneltjänsten får åtkomst till medlemmar och medlemsgrupper från publiceringsmiljön
* **[!UICONTROL Assignment]**
Välj bland de aktiveringsresurser som tilldelats de valda eleverna

Välj **[!UICONTROL Generate]** för att skapa rapporten:

![chlimage_1-158](assets/chlimage_1-158.png)

## Vyrapport {#views-report}

Med hjälp av vykonsolen kan rapporter genereras på sidvisningar av communityfunktioner under en viss tidsperiod.

![chlimage_1-159](assets/chlimage_1-159.png)

Välj villkor för rapporten:

* **[!UICONTROL Site]**
Välj en community-webbplats
* **[!UICONTROL Content Type]**
Välj allt innehåll eller någon av funktionerna på webbplatsen
* Tidsram Välj något av:
   * De senaste 7 dagarna
   * De senaste 30 dagarna
   * De senaste 90 dagarna
   * Förra året

Välj **[!UICONTROL Generate]** för att skapa rapporten:

![chlimage_1-160](assets/chlimage_1-160.png)

## Inläggsrapport {#posts-report}

Med publiceringskonsolen kan rapporter genereras om antalet inlägg till communityfunktioner under en viss tidsperiod.

![chlimage_1-161](assets/chlimage_1-161.png)

Välj villkor för rapporten:

* **[!UICONTROL Site]**
Välj en community-webbplats
* **[!UICONTROL Content Type]**
Välj allt innehåll eller någon av funktionerna på webbplatsen
* Tidsram Välj något av:
   * De senaste 7 dagarna
   * De senaste 30 dagarna
   * De senaste 90 dagarna
   * Förra året

Välj **[!UICONTROL Generate]** för att skapa rapporten:

![chlimage_1-162](assets/chlimage_1-162.png)

## Felsökning {#troubleshooting}

### Inga communitywebbplatser har angetts {#no-community-sites-listed}

Om det inte finns några communitysajter i listan kontrollerar du att Adobe Analytics har aktiverats för en webbplats. Om du väljer rapporter om tilldelningar måste du se till att tilldelningsfunktionen finns i communityplatsens struktur.
