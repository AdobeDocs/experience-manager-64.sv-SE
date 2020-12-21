---
title: Sökfunktion
seo-title: Sökfunktion
description: Lägga till och konfigurera sökning på en webbgruppsplats
seo-description: Lägga till och konfigurera sökning på en webbgruppsplats
uuid: ca633456-911f-447f-881e-653533125d5f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 3acac082-efbe-4995-b374-851cb9aaf62d
translation-type: tm+mt
source-git-commit: a6d50dbcbfec85d21072d51a5fa48e3667835f06
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---


# Sökfunktion {#search-feature}

Sökfunktionen fungerar med olika andra funktioner, till exempel forum, som gör det möjligt att söka efter innehåll.

När du lägger till möjligheten att söka efter inlägg som lagts in av communitymedlemmar, så kallade användargenererat innehåll (UGC), finns det två komponenter: [ `Search`](#search-features) och [ `Search Results`](#search-results).

Sidan som innehåller komponenten `Search Results` har stöd för både sökning och visning av resultat.

På sidan som innehåller `Search`komponenten kan du starta en sökning med resultat som visas på `Search Results`-sidan.

Sökfunktionen kan användas med andra funktioner som gör att besökare och medlemmar kan visa innehåll.

## Sökning {#search-features}

### Lägg till sökning på en sida {#add-search-to-a-page}

Om du vill lägga till en `Search`-komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på `Communities / Search` och dra den till rätt plats på en sida. Användning av `Search` kräver en andra sida för `Search Results.`

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När det nödvändiga klientbiblioteket, `cq.social.hbs.search`, inkluderas visas `Search`-komponenten så här.

![chlimage_1-373](assets/chlimage_1-373.png)

### Konfigurera den tillagda sökningen {#configure-the-added-search}

Markera den monterade `Search`-komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-374](assets/chlimage_1-374.png)

Under fliken **[!UICONTROL Search Settings]** anger du hur sökvägarna ska sökas igenom när en fråga anges av en besökare.

![chlimage_1-375](assets/chlimage_1-375.png)

* **[!UICONTROL Search Paths]**
Genom att lägga till sökvägar med knappen Lägg till objekt begränsas innehållssökningen. Om du till exempel vill begränsa sökningen till ett specifikt forum väljer du en forumkomponent som placeras på en sida:

   * `/content/community-components/en/forum/jcr:content/content/forum`

* **[!UICONTROL Result Page]**
Resultatet visas på en separat sida som du anger med webbläsaren för att välja en sida som innehåller 
`Search Results` -komponenten.

## Sökresultat {#search-results}

### Lägg till sökresultat på en sida {#add-search-results-to-a-page}

Om du vill lägga till en `Search Results`-komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på

* `Communities / Search Results`

och dra den till rätt plats på en sida. Till skillnad från sökkomponenten behövs ingen andra sida eftersom resultaten visas på samma sida.

Om du använder Sök någon annanstans på webbplatsen kan den här sidan med `Search Results` konfigureras som `Result Page` för någon eller alla instanser av `Search`.

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När det nödvändiga klientbiblioteket, `cq.social.hbs.search`, inkluderas, visas `Search Result`-komponenten så här:

![chlimage_1-376](assets/chlimage_1-376.png)

### Konfigurera det tillagda sökresultatet {#configure-the-added-search-result}

Markera den monterade `Search Results`-komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-377](assets/chlimage_1-377.png)

På fliken **[!UICONTROL Search Result Settings]** kan du ange vilka sökvägar som ska ingå i sökningen när en fråga anges av en besökare.

![chlimage_1-378](assets/chlimage_1-378.png)

* **[!UICONTROL Search Results Per Page]**
Definiera antalet ämnen/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Search Paths]**
Genom att lägga till sökvägar med knappen Lägg till objekt begränsas innehållssökningen.

## Ytterligare information {#additional-information}

Mer information finns på sidan [Search Essentials](search-implementation.md) för utvecklare.
