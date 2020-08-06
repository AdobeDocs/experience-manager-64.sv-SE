---
title: Anpassa och utöka resurser
description: Lär dig hur du kan anpassa och utöka Resursresurs- och Resursredigeraren, som ger användarna ett särskilt skräddarsytt gränssnitt och en uppsättning funktioner.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---


# Anpassa och utöka resurser {#customizing-and-extending-assets}

Resursredigeraren är den primära åtkomstpunkten som användare på en Adobe Enterprise Manager-webbplats (AEM) använder för att hitta, visa och ändra digitala resurser i din databas.

Som AEM kan du anpassa och utöka resursredigeraren på flera olika sätt och ge användarna ett särskilt skräddarsytt gränssnitt och en uppsättning funktioner.

Följande funktionalitetsaspekter kan anpassas eller förbättras:

* [Utöka resursredigeraren](asseteditorx.md)
* [Utöka resurssökning](searchx.md)
* [Bearbeta resurser med mediehanterare och arbetsflöden](media-handlers.md)
* [Integrera resurser med aktivitetsström](extending-activity-stream.md)
* [Resursproxyutveckling](proxy.md)
* [Bästa metoder för att konfigurera ImageMagick](best-practices-for-imagemagick.md)

## Anpassa utseende och känsla {#customizing-the-look-and-feel}

Följande aspekter av utseendet och känslan i resursredigeraren kan anpassas:

* Logotyp: Du kan lägga till din egen organisations logotyp i gränssnittet.
* Färger och teckensnitt: Du kan ändra de färger och teckensnitt som används i gränssnittet.
* HTML-kod: Om du vill göra en mer detaljerad anpassning kan du ändra den underliggande HTML-koden som definierar gränssnitten.

## Anpassa återgivningar {#customizing-renditions}

I AEM Assets-terminologi är en återgivning den form i vilken en resurs presenteras. I allmänhet kan en viss resurs ha flera renderingar. Fullfärgsbilder kan till exempel ha en återgivning i sin ursprungliga storlek, en annan i en nedskalad storlek och en annan som både är nedskalad och konverterad till gråskala.

De återgivningar som en viss resurs är tillgänglig i kan anpassas och nya återgivningar skapas.
