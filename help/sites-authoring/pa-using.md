---
title: Visa sidanalysdata
seo-title: Seeing Page Analytics Data
description: Använd data från sidanalys för att mäta hur effektivt deras sidinnehåll är
seo-description: Use page analytics data to gauge the effectiveness of their page content
uuid: 8dda89be-13e3-4a13-9a44-0213ca66ed9c
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 42d2195a-1327-45c0-a14c-1cf5ca196cfc
exl-id: 6509c0ce-fc3a-4248-8dc7-db10602c30d6
source-git-commit: 0f4f8c2640629f751337e8611a2c8f32f21bcb6d
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 0%

---

# Visa sidanalysdata{#seeing-page-analytics-data}

Använd sidanalysdata för att mäta hur effektivt sidinnehållet är.

## Analyser visas från konsolen {#analytics-visible-from-the-console}

![aa-10](assets/aa-10.png)

Sidanalysdata visas i [Listvy](/help/sites-authoring/basic-handling.md#list-view) i Sites-konsolen. När sidorna visas i listformat är följande kolumner tillgängliga som standard:

* Sidvyer
* Unika besökare
* Tid på sidan

Varje kolumn visar ett värde för den aktuella rapporteringsperioden och anger också om värdet har ökat eller minskat sedan den föregående rapporteringsperioden. De data du ser uppdateras var tolfte timme.

>[!NOTE]
>
>Om du vill ändra uppdateringsperioden [konfigurera importintervallet](/help/sites-administering/adobeanalytics-connect.md#configuring-the-import-interval).

1. Öppna **Webbplatser** konsol, till exempel [http://localhost:4502/sites.html/content](http://localhost:4502/sites.html/content)
1. Klicka eller tryck på ikonen längst till höger i verktygsfältet (övre högra hörnet) för att välja **Listvy** (ikonen som visas beror på [aktuell vy](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources)).

1. Återigen, längst till höger i verktygsfältet (övre högra hörnet), klicka eller tryck på ikonen och välj sedan **Visa inställningar**. The **Konfigurera kolumner** öppnas. Gör de ändringar som behövs och bekräfta med **Uppdatera**.

   ![aa-04](assets/aa-04.png)

### Välja rapporteringsperiod {#selecting-the-reporting-period}

Välj den rapporteringsperiod för vilken analysdata visas på webbplatskonsolen:

* Data för de senaste 30 dagarna
* Data för de senaste 90 dagarna
* Årets data

Den aktuella rapportperioden visas i verktygsfältet i webbplatskonsolen (till höger i det övre verktygsfältet). Använd listrutan för att välja önskad rapporteringsperiod.\
![aa-05](assets/aa-05.png)

### Konfigurera tillgängliga datakolumner {#configuring-available-data-columns}

Medlemmar i användargruppen analytics-administrators kan konfigurera konsolen Sites så att författare kan se extra analyskolumner.

>[!NOTE]
>
>När ett sidträd innehåller underordnade objekt som är kopplade till olika Adobe Analytics molnkonfigurationer, kan du inte konfigurera tillgängliga datakolumner för sidorna.

1. I listvyn använder du vyväljarna (höger i verktygsfältet) och väljer **Visa inställningar** och sedan A **Lägg till anpassade analysdata**.

   ![aa-15](assets/aa-15.png)

1. Markera de mätvärden som du vill visa för författare i webbplatskonsolen och klicka sedan på **Lägg till**.

   Kolumnerna som visas hämtas från Adobe Analytics.

   ![aa-16](assets/aa-16.png)

### Öppna innehållsinsikter från webbplatser {#opening-content-insights-from-sites}

Öppna [Content Insight](/help/sites-authoring/content-insights.md) från Sites Console för att ytterligare undersöka hur sidan fungerar.

1. I webbplatskonsolen väljer du den sida som du vill se innehållsinsikter för.
1. Klicka på ikonen Analytics (Analyser) och Recommendations () i verktygsfältet.

   ![](do-not-localize/chlimage_1-16.png)

## Synliga analyser från sidredigeraren (Activity Map) {#analytics-visible-from-the-page-editor-activity-map}

>[!CAUTION]
>
>På grund av säkerhetsändringar i Adobe Analytics API är det inte längre möjligt att använda den version av Activity Map som ingår i AEM.
>
>The [ActivityMap-plugin från Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html) bör nu användas.
