---
title: Platshållartext i AEM Forms
seo-title: Placeholder text in AEM Forms
description: Platshållartext är avsedd att hjälpa användaren med datainmatning när kontrollen inte har något värde. Det kan vara ett exempelvärde eller en kort beskrivning av det förväntade formatet.
seo-description: Placeholder text is intended to aid the user with data entry when the control has no value. It could be a sample value or a brief description of the expected format.
uuid: 553ed988-ad2c-4bdb-bf1e-332e48cf7dfa
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 2d7367fa-6cb8-40a1-8566-1fd0d46fdfde
feature: Adaptive Forms
exl-id: 26a1a5f7-b4d4-4f38-81a4-5f2d39702138
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '251'
ht-degree: 0%

---

# Platshållartext i AEM Forms {#placeholder-text-in-aem-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Platshållartexten representerar ett ord eller en kort fras. Avsikten är att hjälpa användaren att ange data när kontrollen inte har något värde. En platshållartext kan vara ett exempelvärde eller en kort beskrivning av det förväntade formatet. Platshållartexten visas innan användaren anger ett värde, den tas bort när användaren anger eller väljer ett värde.

>[!NOTE]
>
>Om platshållartexten har angetts måste den ha ett värde som inte innehåller några nya radtecken.

![Datumkomponent med och utan platshållartext](assets/dat-picker-place-holder-text.png)

**S.** Datumkomponent med platshållartext **B.** Datumkomponent utan platshållartext

AEM Forms stöder platshållartext för lösenordsrutor, datumväljare, numeriska rutor och textrutefält.\
Platshållartexter stöds inte för den inbyggda HTML5-datumwidgeten. Så här anger du en platshållartext:

1. Högerklicka på en komponent som stöder platshållartext och klicka på **Redigera**. Dialogrutan Redigera komponent visas.

1. Öppna **Titel och text** -fliken.
1. Ange ett ord eller en kort fras i **Platshållartextruta**. Klicka **OK**.

>[!NOTE]
>
>Platshållartext stöds inte i Microsoft Internet Explorer 9.
