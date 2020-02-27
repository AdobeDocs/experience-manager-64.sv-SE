---
title: Komponent för överläggskommentarer
seo-title: Komponent för överläggskommentarer
description: Översikt över komponenten Overlay Comments
seo-description: Översikt över komponenten Overlay Comments
uuid: 634240e2-99bb-4107-89f5-c66d53e2515d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 4849da13-518c-40c8-b80e-1b2264d7f8f5
translation-type: tm+mt
source-git-commit: 8f169bb9b015ae94b9160d3ebbbd1abf85610465

---


# Komponent för överläggskommentarer {#overlay-comments-component}

Avsikten med att [täcka över](client-customize.md#overlays) en standardkomponent är att ändra utseendet eller beteendet för en komponent globalt, för alla relativa referenser till komponenten. Det är beroende av vilken typ av sling som du kan lösa till mappen /apps innan du söker i mappen /libs. Sökvägen till komponenten är alltså identisk med sökvägen till standardkomponenten, förutom att den finns i mappen /apps och inte i mappen /libs.

## Exempel {#example}

Anta att du vill ändra kommentarsfunktionen så att den matchar webbplatsens design genom att ändra kommentarsrubriken så att avataren inte längre visas för kommentarer. Lösningarna för att dölja avataren använder antingen CSS eller, som beskrivs här, åsidosätter header.jsp i programmappen så att HTML-koden som innehåller avataren aldrig skickas till klienten.

Om du vill lägga över kommentarer måste du:

1. [Kommentarsida](overlay-create-comments-page.md)
1. [Skapa noder](overlay-create-nodes.md)
1. [Ändra utseendet](overlay-alter-appearance.md)

