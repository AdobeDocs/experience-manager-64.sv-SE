---
title: 'Platshållartext i AEM Forms '
seo-title: 'Platshållartext i AEM Forms '
description: Platshållartext är avsedd att hjälpa användaren med datainmatning när kontrollen inte har något värde. Det kan vara ett exempelvärde eller en kort beskrivning av det förväntade formatet.
seo-description: Platshållartext är avsedd att hjälpa användaren med datainmatning när kontrollen inte har något värde. Det kan vara ett exempelvärde eller en kort beskrivning av det förväntade formatet.
uuid: 553ed988-ad2c-4bdb-bf1e-332e48cf7dfa
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 2d7367fa-6cb8-40a1-8566-1fd0d46fdfde
feature: Adaptiv Forms
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 0%

---


# Platshållartext i AEM Forms {#placeholder-text-in-aem-forms}

Platshållartexten representerar ett ord eller en kort fras. Avsikten är att hjälpa användaren att ange data när kontrollen inte har något värde. En platshållartext kan vara ett exempelvärde eller en kort beskrivning av det förväntade formatet. Platshållartexten visas innan användaren anger ett värde, den tas bort när användaren anger eller väljer ett värde.

>[!NOTE]
>
>Om platshållartexten har angetts måste den ha ett värde som inte innehåller några nya radtecken.

![Datumkomponent med och utan platshållartext](assets/dat-picker-place-holder-text.png)

**A.** Date-komponent med platshållartext  **B.** Date-komponent utan platshållartext

AEM Forms stöder platshållartext för lösenordsrutor, datumväljare, numeriska rutor och textrutefält.\
Platshållartexter stöds inte för den inbyggda HTML5-datumwidgeten. Så här anger du en platshållartext:

1. Högerklicka på en komponent som stöder platshållartext och klicka på **Redigera**. Dialogrutan Redigera komponent visas.

1. Öppna fliken **Titel och text**.
1. Ange ett ord eller en kort fras i textrutan **Platshållare**. Klicka på **OK**.

>[!NOTE]
>
>Platshållartext stöds inte i Microsoft Internet Explorer 9.

