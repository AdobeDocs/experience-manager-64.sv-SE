---
title: Avgränsningskomponent i adaptiva formulär
seo-title: Separator component in adaptive forms
description: Du kan använda avgränsningskomponenten för att segmentera ett formulär visuellt.
seo-description: You can use the separator component to visually segregate sections of a form.
uuid: d51c3797-8227-41ed-88cd-c56cc129eb86
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: ba674a2d-7c78-430e-8e17-1a18619e71cb
feature: Adaptive Forms
exl-id: 7e37401a-8c63-4711-8a33-61e6bd4b419f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---

# Avgränsningskomponent i adaptiva formulär {#separator-component-in-adaptive-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan använda avgränsarkomponenten för att dela upp paneler i ett formulär visuellt. Du kan definiera det övergripande utseendet och formatet för en avgränsningskomponent genom att ange följande egenskaper för avgränsningskomponenten:

* **Elementnamn:** Anger komponentens namn. SOM-uttrycken adresserar komponenten med ett värde som anges i fältet Elementnamn.
* **Tjocklek:** Anger tjockleken på avgränsarkomponenten i pixlar.
* **Kolumnutvidgning:** Anger antalet kolumner som en avgränsningskomponent sträcker sig till.
* **CSS-klass:** Anger den anpassade CSS-klassen för avgränsarkomponenten
* **Textbundna format:** Med AEM Forms kan du nu använda infogade CSS-format på enskilda adaptiva formulärkomponenter och förhandsgranska ändringarna i realtid.

Så här anger du egenskaper för en avgränsningskomponent:

1. Markera en separationskomponent och tryck på ![cmppr](assets/cmppr.png). Egenskaperna öppnas i sidofältet.
1. Klicka på en flik i avsnittet Infogade CSS-egenskaper för att ange CSS-egenskaper. Till exempel: a. Klicka på fliken Fält **Lägg till objekt**. En rad med två fält läggs till.
1. I det första fältet från vänster anger du den CSS3-egenskap som du vill använda. Till exempel: **border**. Du kan också välja en egenskap genom att klicka på nedpilsknappen. Listrutan är inte fullständig och du kan ange ett CSS3-egenskapsnamn som stöds i det här fältet.
1. Ange ett giltigt värde för den angivna CSS3-egenskapen i det intilliggande fältet. Till exempel: **3px solid svart**.
1. Klicka **Lägg till objekt** för att ange en annan egenskap och dess värde.
1. Klicka **Förhandsgranska** om du vill förhandsgranska ändringarna i formuläret.
1. Klicka **OK** för att bekräfta ändringarna eller **Avbryt **för att stänga dialogrutan utan ändringar.
