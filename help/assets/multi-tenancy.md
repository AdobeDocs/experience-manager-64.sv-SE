---
title: Flera innehavare för samlingar, kodavsnitt och kodfragment
description: Segmentera innehållet i CRX-databasen baserat på kundorganisationen för att förhindra obehörig åtkomst.
contentOwner: AG
feature: Collections
role: Architect,Administrator,Leader
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 1%

---


# Multi-tenancy för samlingar, fragment och fragmentmallar {#multi-tenancy-for-collections-snippets-and-snippet-templates}

Med funktionen Multi-tenancy kan du dela upp innehåll i CRX baserat på organisationens prefix och organisations-ID för att skydda innehållet från obehörig åtkomst för användare i andra organisationer.

Adobe Experience Manager (AEM) Assets lagrar data för varje organisation på olika sätt. Varje organisationsspecifik sökväg identifieras av organisationens prefix och organisations-ID.
som ingår i den traditionella platsen där olika typer av resurser lagras i CRX.

Om du till exempel skapar en mapp med namnet `Demo`, lagrar AEM som standard mappen på `../content/dam/Demo`-platsen i CRX. När funktionen för flera innehavare är aktiverad kan du lagra data på `../content/dam/<organization prefix>/<organization id>Demo`.

För Adobe Marketing Cloud-användare av AEM Assets (on-demand) som är tilldelade till `aodpremium`-organisationen kan du till exempel använda funktionen multi-tenancy för att konfigurera följande sökväg till `../content/dam/mac/aodpremiumDemo`, dela upp innehållet. I det här exemplet är `mac` organisationsprefixet och `aodpremium` organisations-ID.

Baserat på användarens organisation och ID visas den här kvalificerade sökvägen i AEM Assets-gränssnittet och i olika guider, inklusive guiderna för att flytta och skapa fragment för att framtvinga en gruppering.

Med funktionen för flera innehavare kan du välja följande typer av resurser och komponenter:

* Samlingar
* Offentliga samlingar
* Kataloger (inklusive guiden Lägg till/välj sida)
* Mallar
* Fragmentmallar
* Ljuslåda
