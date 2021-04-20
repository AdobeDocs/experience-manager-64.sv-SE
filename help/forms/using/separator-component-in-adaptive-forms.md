---
title: Avgränsningskomponent i adaptiva formulär
seo-title: Avgränsningskomponent i adaptiva formulär
description: Du kan använda avgränsningskomponenten för att segmentera ett formulär visuellt.
seo-description: Du kan använda avgränsningskomponenten för att segmentera ett formulär visuellt.
uuid: d51c3797-8227-41ed-88cd-c56cc129eb86
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: ba674a2d-7c78-430e-8e17-1a18619e71cb
feature: Adaptive Forms
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '300'
ht-degree: 0%

---


# Avgränsningskomponent i adaptiva former {#separator-component-in-adaptive-forms}

Du kan använda avgränsarkomponenten för att dela upp paneler i ett formulär visuellt. Du kan definiera det övergripande utseendet och formatet för en avgränsningskomponent genom att ange följande egenskaper för avgränsningskomponenten:

* **Elementnamn:** Anger komponentens namn. SOM-uttrycken adresserar komponenten med ett värde som anges i fältet Elementnamn.
* **Tjocklek:** Anger tjockleken på avgränsarkomponenten i pixlar.
* **Kolumnutvidgning:** Anger antalet kolumner som en avgränsningskomponent sträcker sig till.
* **CSS-klass:** Anger den anpassade CSS-klassen för avgränsarkomponenten
* **Textbundna format:** Med AEM Forms kan du nu använda infogade CSS-format på enskilda adaptiva formulärkomponenter och förhandsgranska ändringarna i realtid.

Så här anger du egenskaper för en avgränsningskomponent:

1. Markera en avgränsningskomponent och tryck på ![cmpr](assets/cmppr.png). Egenskaperna öppnas i sidofältet.
1. Klicka på en flik i avsnittet Infogade CSS-egenskaper för att ange CSS-egenskaper. Till exempel: a. Klicka på **Lägg till objekt** på fliken Fält. En rad med två fält läggs till.
1. I det första fältet från vänster anger du den CSS3-egenskap som du vill använda. Till exempel **border**. Du kan också välja en egenskap genom att klicka på nedpilsknappen. Listrutan är inte fullständig och du kan ange ett CSS3-egenskapsnamn som stöds i det här fältet.
1. Ange ett giltigt värde för den angivna CSS3-egenskapen i det intilliggande fältet. Exempel: **3px solid black**.
1. Klicka på **Lägg till objekt** om du vill ange en annan egenskap och dess värde.
1. Klicka på **Förhandsgranska** om du vill förhandsgranska ändringarna i formuläret.
1. Klicka på **OK** för att bekräfta ändringarna eller **Avbryt **för att stänga dialogrutan utan ändringar.

