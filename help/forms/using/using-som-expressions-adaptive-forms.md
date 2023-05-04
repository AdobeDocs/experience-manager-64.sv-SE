---
title: Använda SOM-uttryck i adaptiva former
seo-title: Using SOM expressions in adaptive forms
description: Lär dig hur du extraherar SOM-uttryck för en panel i ett adaptivt formulär.
seo-description: Learn how to extract SOM expressions of a panel of an adaptive form.
uuid: 4bc80e2a-3563-48a3-996d-021b701bc2ee
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 7dff7ef2-80d1-434a-b9b0-ac6654736602
feature: Adaptive Forms
exl-id: e4680ede-6a02-4b8b-8a6f-9599a05da8e7
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 0%

---

# Använda SOM-uttryck i adaptiva former {#using-som-expressions-in-adaptive-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Anpassade formulär modelleras som AEM sida, som representeras som JCR-innehållsstruktur i AEM. Nyckelelementet i innehållsstrukturen är noden guideContainer. Under guideContainer finns det rootPanel som kan innehålla kapslade paneler och fält.

Du kan använda en skriptobjektmodell (SOM) för att referera till värden, egenskaper och metoder i en viss dokumentobjektmodell (DOM). En DOM organiserar minnesobjekt och egenskaper i en trädhierarki. A SOM expression references Fields/Draw elements and panels.

Följande bild visar en nodstruktur som ett adaptivt formulär översätter till när du lägger till komponenter i ett formulär. Du kan till exempel lägga till en panel i rotpanelen och en alternativknapp i panelen som omvandlas till DOM vid körning. SOM-uttrycket för alternativknappsfältet i adaptiv form anges som `guide[0].guide1[0].guideRootPanel[0].panel1[0].radiobutton[0]`.

![DOM-träd](assets/hierarchy-1.png)

A SOM expression for any element in an adaptive form is prefix by `guide[0].guide1[0]`. Positionen för en komponent i nodstrukturhierarkin används för att härleda dess SOM-uttryck.

![DOM-träd med två alternativknappar](assets/hierarchy_radio_button.png)

SOM-uttrycket ändras när du ändrar positionen för alternativknapparna i det adaptiva formuläret. I redigeringsläget kan du visa SOM-uttrycket för ett fält eller element i AEM Forms med alternativet Visa SOM-uttryck. Alternativet visas på panelen och när du högerklickar på fältet eller elementet.

![Extrahera SOM-uttryck i en adaptiv form](assets/som-expressions.png)

I paneler kan du komma åt funktionen från panelens verktygsfält. Funktionen underlättar skriptning för formulärförfattare som vill anpassa formulär.

![Extrahera SOM-uttryck med panelens verktygsfält](assets/som-expression.png)

Vissa API:er listas i [GuideBridge](https://helpx.adobe.com/aem-forms/6/javascript-api/GuideBridge.md) använder SOM-uttrycket för ett element. Om du till exempel vill ge fokus till ett visst fält i en adaptiv form skickar du motsvarande SOM-uttryck till `getFocus`API in `guideBridge`.
