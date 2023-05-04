---
title: SPA och Adobe Experience Platform Launch Integration
seo-title: SPA and Adobe Experience Platform Launch Integration
description: Adobe Experience Platform Launch rekommenderas för att implementera Analytics, Target och Audience Manager inom SPA.
seo-description: Adobe Experience Platform Launch is the recommended way to implement Analytics, Target, and Audience Manager within SPAs.
uuid: 8535a911-2863-4e3b-a3fb-414a0e7e9a4e
contentOwner: bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: spa
discoiquuid: a458cc95-cd94-4f3f-9e7b-d6a5780ec4d5
exl-id: 1af29921-7c24-49b5-9f4c-60671641d4e4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '236'
ht-degree: 0%

---

# Integrering av SPA och startprogram{#spa-and-launch-integration}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Platform Launch rekommenderas för att implementera Analytics, Target och Audience Manager i Single Page Applications (SPA).

>[!NOTE]
>
>Funktionen SPA (Single-Page Application Editor) kräver AEM 6.4 Service Pack 2 eller senare.
>
>SPA Editor är den rekommenderade lösningen för projekt som kräver SPA ramverksbaserad återgivning på klientsidan (t.ex. Reaktion eller Angular).

## Självstudiekurs {#tutorial}

Om du vill veta mer om hur du integrerar dina SPA med Adobe Experience Platform Launch går du till [den här kunskapsbasartikeln och självstudiekursen](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html), som vägleder dig genom Launch-installationen samt implementerar Experience Cloud som byggts med Angular eller React.

>[!NOTE]
>
>Den refererade KB:en skapades för att möjliggöra Adobe Experience Platform Launch-integrering med SPA som inte utnyttjar AEM SPA. Dessa metoder bör också göra det möjligt för Adobe Experience Platform Launch-integreringen att samexistera med SPA som är byggda för att använda SPA Editor.
>
>Användningen av Redux tillsammans med Javascript-SPA har inte utforskats fullständigt. Stöd för Redux planeras i en framtida version av SPA Editor.
