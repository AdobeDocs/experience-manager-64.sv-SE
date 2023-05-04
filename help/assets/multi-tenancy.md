---
title: Flera innehavare för samlingar, kodavsnitt och kodfragment
description: Segmentera innehållet i CRX-databasen baserat på kundorganisationen för att förhindra obehörig åtkomst.
contentOwner: AG
feature: Collections
role: Architect,Admin,Leader
exl-id: d00a671a-6707-4941-868d-fa13510b7b60
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '266'
ht-degree: 0%

---

# Flera innehavare för samlingar, kodavsnitt och kodfragment {#multi-tenancy-for-collections-snippets-and-snippet-templates}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med funktionen Multi-tenancy kan du dela upp innehåll i CRX baserat på organisationens prefix och organisations-ID för att skydda innehållet från obehörig åtkomst för användare i andra organisationer.

Adobe Experience Manager (AEM) Assets lagrar data för varje organisation på olika sätt. Varje organisationsspecifik sökväg identifieras av organisationens prefix och organisations-ID.
som ingår i den traditionella platsen där olika typer av resurser lagras i CRX.

Om du till exempel skapar en mapp med namnet `Demo`AEM som standard sparas mappen på `../content/dam/Demo` plats i CRX. När funktionen för flera innehavare är aktiverad kan du lagra data på `../content/dam/<organization prefix>/<organization id>Demo`.

För Adobe Marketing Cloud-användare av AEM Assets (on-demand) som är tilldelade `aodpremium` kan du använda funktionen för flera innehavare för att konfigurera följande sökväg till `../content/dam/mac/aodpremiumDemo`, separera innehållet. I det här exemplet `mac` är organisationsprefixet och `aodpremium` är organisations-ID.

Baserat på användarens organisation och ID visas den här kvalificerade sökvägen i AEM Assets-gränssnittet och i olika guider, inklusive guiderna för att flytta och skapa fragment för att framtvinga en gruppering.

Med funktionen för flera innehavare kan du välja följande typer av resurser och komponenter:

* Samlingar
* Offentliga samlingar
* Kataloger (inklusive guiden Lägg till/välj sida)
* Mallar
* Fragmentmallar
* Ljuslåda
