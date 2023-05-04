---
title: Komponent för överläggskommentarer
seo-title: Overlay Comments Component
description: Översikt över komponenten Overlay Comments
seo-description: Overlay Comments component overview
uuid: 634240e2-99bb-4107-89f5-c66d53e2515d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 4849da13-518c-40c8-b80e-1b2264d7f8f5
exl-id: 31528814-02bc-4978-87fa-5c8074b454ed
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '197'
ht-degree: 0%

---

# Komponent för överläggskommentarer {#overlay-comments-component}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Avsikten med [överläggning](client-customize.md#overlays) en standardkomponent är att ändra utseendet eller beteendet för en komponent globalt, för alla relativa referenser till komponenten. Det är beroende av vilken typ av sling som du kan lösa till mappen /apps innan du söker i mappen /libs. Sökvägen till komponenten är alltså identisk med sökvägen till standardkomponenten, förutom att den finns i mappen /apps och inte i mappen /libs.

## Exempel {#example}

Anta att du vill ändra kommentarsfunktionen så att den matchar webbplatsens design genom att ändra kommentarsrubriken så att avataren inte längre visas för kommentarer. Lösningarna för att dölja avataren använder antingen CSS eller, som beskrivs här, åsidosätter header.jsp i programmappen så att HTML som innehåller avataren aldrig skickas till klienten.

Om du vill lägga över kommentarer måste du:

1. [Kommentarsida](overlay-create-comments-page.md)
1. [Skapa noder](overlay-create-nodes.md)
1. [Ändra utseendet](overlay-alter-appearance.md)
