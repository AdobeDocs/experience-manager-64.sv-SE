---
title: Konfigurera komponenter i designläge
seo-title: Configuring Components in Design Mode
description: När AEM är installerad i en körklar version är ett urval av komponenter omedelbart tillgängliga i sidosparken. Förutom dessa finns även andra komponenter tillgängliga. Du kan använda designläget för att aktivera/inaktivera sådana komponenter.
seo-description: When AEM instance is installed out-of-the-box, a selection of components are immediately available in the sidekick. In addition to these, various other components are also available. You can use Design mode to Enable/disable such components.
page-status-flag: de-activated
uuid: 57249965-3a30-49ce-9fb0-864c5daaa262
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 93f98f7b-7ab8-4d9c-b179-dc99b80ffc91
exl-id: af6c383b-f8fd-442c-8fc5-3cdd40657c6a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '536'
ht-degree: 0%

---

# Konfigurera komponenter i designläge{#configuring-components-in-design-mode}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När AEM är installerad i en körklar version är ett urval av komponenter omedelbart tillgängliga i sidosparken.

Förutom dessa finns även andra komponenter tillgängliga. Du kan använda designläget för att [Aktivera/inaktivera sådana komponenter](#enabledisablecomponentsusingdesignmode). När det är aktiverat och finns på sidan kan du sedan använda designläget för att [konfigurera olika aspekter av komponentdesignen](#configuringcomponentsusingdesignmode) genom att redigera attributparametrarna.

>[!NOTE]
>
>Försiktighet måste iakttas vid redigering av dessa komponenter. Designinställningarna är ofta en viktig del av designen för hela webbplatsen, så de bör bara ändras av någon med rätt behörighet (och upplevelse), ofta administratör eller utvecklare. Se [Utveckla komponenter](/help/sites-developing/components.md) för mer information.

Detta innebär att lägga till, eller ta bort, de komponenter som är tillåtna i sidans styckesystem. Styckesystemet ( `parsys`) är en sammansatt komponent som innehåller alla andra styckekomponenter. Med styckesystemet kan författare lägga till komponenter av olika typer på en sida eftersom det innehåller alla andra styckekomponenter. Varje stycketyp representeras som en komponent.

Innehållet på en produktsida kan till exempel innehålla ett styckesystem som innehåller följande:

* En bild av produkten (i form av en bild eller ett textimagestycke)
* Produktbeskrivningen (som ett textstycke)
* En tabell med tekniska uppgifter (som ett tabellstycke)
* En formuläranvändare fyller i (när ett formulär börjar, formulärelement och slutstycke för formulär)

>[!NOTE]
>
>Se [Utveckla komponenter](/help/sites-developing/components.md#paragraphsystem) och [Riktlinjer för användning av mallar och komponenter](/help/sites-developing/dev-guidelines-bestpractices.md#guidelines-for-using-templates-and-components) för mer information om `parsys`.

## Aktivera/inaktivera komponenter {#enable-disable-components}

I designläget minimeras sidosparken och du kan konfigurera komponenter som är tillgängliga för redigering:

1. Öppna en sida för redigering och använd ikonen för att öppna designläget:

   ![](do-not-localize/chlimage_1.png)

1. Klicka **Redigera** på styckesystemet (**Partikeldesign**).

   ![screen_shot_2012-02-08at102726am](assets/screen_shot_2012-02-08at102726am.png)

1. En dialogruta öppnas med en lista över de komponentgrupper som visas i Spark tillsammans med de enskilda komponenterna som de innehåller.

   Välj vad som krävs för att lägga till eller ta bort komponenterna som ska vara tillgängliga i sidosparken.

   ![screen_shot_2012-02-08at103407am](assets/screen_shot_2012-02-08at103407am.png)

1. The Sidekick minimeras i designläge. Genom att klicka på pilen kan du maximera sparken och återgå till redigeringsläget:

   ![](do-not-localize/sidekick-collapsed.png)

## Konfigurera designen för en komponent {#configuring-the-design-of-a-component}

I designläget kan du även konfigurera attribut för de enskilda komponenterna. Varje komponent har sina egna parametrar visas i följande exempel **Bild** komponent:

1. Öppna en sida för redigering och använd ikonen för att öppna designläget:

   ![](do-not-localize/chlimage_1-1.png)

1. Du kan konfigurera komponenternas design.

   Om du till exempel klickar **Redigera** på komponenten Bild (**Design av bild**) kan du konfigurera komponentspecifika parametrar:

   ![chlimage_1-12](assets/chlimage_1-12.png)

1. Klicka **OK** för att spara ändringarna.

1. The Sidekick minimeras i designläge. Genom att klicka på pilen kan du maximera sparken och återgå till redigeringsläget:

   ![](do-not-localize/sidekick-collapsed-1.png)
