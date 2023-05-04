---
title: Sökfunktion
seo-title: Search Feature
description: Lägga till och konfigurera sökning på en webbgruppsplats
seo-description: Adding and configuring Search to a Communities site
uuid: ca633456-911f-447f-881e-653533125d5f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 3acac082-efbe-4995-b374-851cb9aaf62d
exl-id: 15d8bd59-397e-4bd3-b0a2-b6893c015798
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '474'
ht-degree: 1%

---

# Sökfunktion {#search-feature}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Sökfunktionen fungerar med olika andra funktioner, till exempel forum, som gör det möjligt att söka efter innehåll.

När du lägger till möjligheten att söka efter inlägg som lagts in av communitymedlemmar, så kallade användargenererat innehåll (UGC), finns det två komponenter: [ `Search`](#search-features) och [ `Search Results`](#search-results).

Sidan som innehåller `Search Results` -komponenten har stöd för både sökning och visning av resultat.

Sidan som innehåller `Search`-komponenten ger dig en plats att starta en sökning med resultat som visas på `Search Results` sida.

Sökfunktionen kan användas med andra funktioner som gör att besökare och medlemmar kan visa innehåll.

## Sökning {#search-features}

### Lägg till sökning på en sida {#add-search-to-a-page}

Lägga till en `Search` -komponent till en sida i redigeringsläge använder du komponentwebbläsaren för att leta upp `Communities / Search` och dra den till rätt plats på en sida. Användning av `Search` kräver en andra sida för `Search Results.`

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När det nödvändiga klientbiblioteket `cq.social.hbs.search`, finns med, det är så här `Search` visas.

![chlimage_1-373](assets/chlimage_1-373.png)

### Konfigurera den tillagda sökningen {#configure-the-added-search}

Markera den monterade `Search` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-374](assets/chlimage_1-374.png)

Under **[!UICONTROL Search Settings]** anger du hur sökvägarna ska sökas igenom när en fråga anges av en besökare.

![chlimage_1-375](assets/chlimage_1-375.png)

* **[!UICONTROL Search Paths]**
Genom att lägga till sökvägar med knappen Lägg till objekt begränsas innehållssökningen. Om du till exempel vill begränsa sökningen till ett specifikt forum väljer du en forumkomponent som placeras på en sida:

   * `/content/community-components/en/forum/jcr:content/content/forum`

* **[!UICONTROL Result Page]**
Resultatet visas på en separat sida som du anger med webbläsaren för att välja en sida som innehåller 
`Search Results` -komponenten.

## Sökresultat {#search-results}

### Lägg till sökresultat på en sida {#add-search-results-to-a-page}

Lägga till en `Search Results` -komponent till en sida i redigeringsläge använder du komponentwebbläsaren för att leta upp

* `Communities / Search Results`

och dra den till rätt plats på en sida. Till skillnad från sökkomponenten behövs ingen andra sida eftersom resultaten visas på samma sida.

Om du använder Sök någon annanstans på webbplatsen är den här sidan med `Search Results` kan konfigureras att vara `Result Page` för alla eller alla förekomster av `Search`.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När det nödvändiga klientbiblioteket `cq.social.hbs.search`, finns med, det är så här `Search Result` visas:

![chlimage_1-376](assets/chlimage_1-376.png)

### Konfigurera det tillagda sökresultatet {#configure-the-added-search-result}

Markera den monterade `Search Results` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-377](assets/chlimage_1-377.png)

Under **[!UICONTROL Search Result Settings]** kan du ange vilka sökvägar som ska ingå i sökningen när en fråga anges av en besökare.

![chlimage_1-378](assets/chlimage_1-378.png)

* **[!UICONTROL Search Results Per Page]**
Definiera antalet ämnen/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Search Paths]**
Genom att lägga till sökvägar med knappen Lägg till objekt begränsas innehållssökningen.

## Ytterligare information {#additional-information}

Mer information finns på [Sök i Grundläggande](search-implementation.md) för utvecklare.
