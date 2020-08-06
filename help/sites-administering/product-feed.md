---
title: Produktfeed
seo-title: Produktfeed
description: Läs mer om AEM produktfeed.
seo-description: Läs mer om AEM produktfeed.
uuid: 99eb9bdc-2717-45d4-9203-6394b7d7ddc6
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 1f920892-c52e-42ca-900c-2c7ab3c503b3
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '527'
ht-degree: 1%

---


# Produktfeed{#product-feed}

AEM kan integreras med [Search &amp; Promote](https://www.adobe.com/solutions/testing-targeting/searchandpromote.html) och

* använda eCommerce API, oberoende av den underliggande databasstrukturen och handelsplattformen.
* utnyttja funktionen Index Connector i Search &amp; Promote för att ge en produktfeed i XML-format.
* utnyttja funktionen Fjärrstyrning i Search &amp; Promote för att utföra on-demand- eller schemalagda begäranden i produktflödet
* feed-generering för olika Search &amp; Promote, konfigurerad som molntjänster.

Du måste ha ett giltigt konto och [konfigurera anslutningen till Search &amp; Promote](/help/sites-administering/search-and-promote.md#configuring-the-connection-to-search-promote). Du måste också verifiera att du använder rätt [datacenter](/help/sites-administering/search-and-promote.md#configuring-the-data-center) och kontrollera att URI:n för **fjärrserver **är konfigurerad.

## Ställ in produktfeed {#set-up-the-product-feed}

Du måste först ange en webbplatsrot och ett identifierarattribut. Så här gör du:

1. Navigera till din Search &amp; Promote-konfiguration.
1. Klicka på **[!UICONTROL Edit]**.
1. Click the **[!UICONTROL Index Connector Feed Configuration]** tab.
1. Ange **[!UICONTROL Web site root]** och **[!UICONTROL Identifier attribute]**.

   >[!NOTE]
   >
   >Det **[!UICONTROL Web site root]** är roten till din e-handelswebbplats, till exempel `/content/geometrixx-outdoors/en`.
   >
   >Egenskapen **[!UICONTROL Identifier attribute]** är en JCR-egenskap som unikt identifierar produkten: `identifier`.

1. Klicka på **[!UICONTROL OK]**.

Sedan måste du redigera två konfigurationer i webbkonsolen innan du kan generera produktflöden.

### Configuring the Day CQ Search &amp; Promote Crawler Implementation for Geometrixx {#configuring-the-day-cq-search-promote-products-crawler-implementation-for-geometrixx}

1. Gå till [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Klicka på **[!UICONTROL Day CQ Search&Promote products crawler implementation for Geometrixx]**.
1. Ange Search &amp; Promote kontonummer som crawlern är länkad till. Den kommer att användas för att leta upp den molntjänstkonfiguration som används av denna crawler.
1. Klicka på **[!UICONTROL Save]**.

### Configuring the Day CQ Search &amp; Promote Feed Generator for Geometrixx {#configuring-the-day-cq-search-promote-products-feed-generator-for-geometrixx}

1. Gå till [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr).
1. Klicka på **[!UICONTROL Day CQ Search&Promote products feed generator for Geometrixx]**.
1. Ange Search &amp; Promote kontonummer som generatorn är länkad till. Den kommer att användas för att leta upp den molntjänstkonfiguration som används av den här generatorn.
1. Klicka på **[!UICONTROL Save]**.

## Schemalägg produktfeed {#schedule-the-product-feed}

Om du vill aktivera schemalagd feed-generering måste du konfigurera en schemaläggare för den.\
En schemaläggare är konfigurerad som en underordnad konfiguration till din specifika konfiguration för molntjänster i Search &amp; Promote.

1. Navigera till din Search &amp; Promote-konfiguration.
1. Click **[!UICONTROL +]** next to **[!UICONTROL Scheduler configuration]**.
1. Ange en **[!UICONTROL Title]** som är identifierbar för sidförfattare och en unik **[!UICONTROL Name]**.
1. Klicka på **[!UICONTROL Create]**. En dialogruta öppnas.

   ![chlimage_1-108](assets/chlimage_1-108.png)

1. Ange **[!UICONTROL Remote Control Password]**. Det är lösenordet som du konfigurerade i ditt Search&amp;Pronote-konto.

   >[!NOTE]
   >
   >Det här är inte lösenordet till ditt Search &amp; Promote-konto. Du kan hitta och ändra det här lösenordet genom att logga in på ditt Search &amp; Promote-konto och gå till **[!UICONTROL Index]** och sedan till **[!UICONTROL Remote control]**.

1. Check **[!UICONTROL Enable schedule]** box.
1. Välj en **[!UICONTROL Schedule]**. Det är det faktiska schemat för matningsgenerering.
1. Aktivera **[!UICONTROL On-demand indexing]** eller inte. Den här funktionen används för att manuellt anropa Search &amp; Promote index. Om **[!UICONTROL Request full products feed]** alternativet är markerat begär Search &amp; Promote en fullständig produktfeed. I annat fall begärs inkrementell produktfeed.

   >[!NOTE]
   >
   >Indexeringsfunktionen on-demand använder funktionen Fjärrstyrning i Search &amp; Promote. När en fjärrindexering anropas startar inte indexeringen omedelbart, men en indexeringsbegäran kommer att skickas till Search &amp; Promote med hjälp av fjärrkontrollsfunktionen.

1. Klicka på **[!UICONTROL OK]**.

Nu när du har konfigurerat allt kan du se en XML-sida som innehåller alla produkter i den konfigurerade webbplatsens rot: [http://localhost:4502/etc/commerce/searchpromote/feed/full](http://localhost:4502/etc/commerce/searchpromote/feed/full).
