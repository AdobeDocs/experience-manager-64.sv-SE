---
title: Använda socialt diagram
seo-title: Using Social Graph
description: Lägga till en följande komponent på en sida
seo-description: Adding a Following component to a page
uuid: 8be6334b-e6c9-40bc-90a8-750b98419470
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 0ce57ab1-e4c6-4c38-963d-556eef8757f2
exl-id: ab829d28-278d-4139-af16-edcc24b3d56b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '223'
ht-degree: 0%

---

# Använda socialt diagram {#using-social-graph}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

Möjlighet för en community-medlem att följa [verksamhet](activities.md) och som ska följas fastställs genom två komponenter: `Follow`och `Following`.

The `Follow`måste vara associerad med en annan resurs, och den här associationen har redan upprättats för communitymedlemmar och funktioner.

The `Following`listar bara de medlemmar som antingen följer den aktuella medlemmen eller som följs av den aktuella medlemmen. Det här sociala diagrammet över relationerna mellan medlemmar ingår i den användarprofil som upprättats för en [communitywebbplats](overview.md#communitiessites).

## Lägga till följande på en sida {#adding-following-to-a-page}

Om du vill lägga till en `Following`till en sida i redigeringsläge, leta reda på komponenten `Communities / Following` och dra den till rätt plats på en sida där det sociala diagrammet ska visas.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](essentials-socialgraph.md#essentials-for-client-side) ingår så här `Following` visas:

![chlimage_1-447](assets/chlimage_1-447.png)

## Konfigurera följande {#configuring-following}

För närvarande är det nödvändigt att ställa in egenskapen för att avgöra om komponenten visar `follows`relation, eller `following`relation.

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande om sociala diagram](essentials-socialgraph.md) för utvecklare.
