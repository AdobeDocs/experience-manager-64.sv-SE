---
title: Mappstrukturen
seo-title: Understanding the folder structure
description: Hur du förstår mappstrukturen för källkoden för arbetsytan i AEM Forms så att du kan anpassa den.
seo-description: How to understand the folder structure of AEM Forms workspace source code to customize.
uuid: ee844f89-887e-4f07-9db3-389859baa374
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 7427858d-8eec-423d-a0a9-444140420620
exl-id: 192c436d-a507-4883-bd68-a6863a6664e0
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 0%

---

# Mappstrukturen {#understanding-the-folder-structure}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM Forms arbetsytekomponenter är utformade för MVC-arkitektur med Backbone. Varje komponent har en fil för:

* Modell, som innehåller affärslogik.
* Template, that is an HTML file containing interface controls.
* Visa, som fungerar som en kontrollenhetsklass för Template.

Resurserna för alla komponenter placeras i mappstrukturen som beskrivs nedan. Om du vill komma åt resurserna loggar du in på CRXDE Lite och bläddrar till `/libs/ws/js/runtime/`.

**modeller** Innehåller ryggradsmodeller.

**vyer** Innehåller vyer för ryggraden.

**mallar** Innehåller bara komponenternas HTML-mallar.

**rutter** Innehåller universella vägar. Mappen Mallar inuti vägar innehåller HTML-koden och referenserna till komponenterna.

**tjänster** Innehåller tjänstgränssnitt för att anropa Adobe Experience Manager server-API:er på REST-slutpunkten.

**util** Innehåller allmänna verktyg som kan användas av flera komponenter.
