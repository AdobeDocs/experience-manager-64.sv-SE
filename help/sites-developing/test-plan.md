---
title: Kompilera testplanen
seo-title: Compiling your Test Plan
description: De enskilda testfallen samlas i din testplan
seo-description: The individual test cases are amalgamated into your Test Plan
uuid: 99822b02-7b75-422d-ae21-16c4af742567
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 3a8302e8-bc61-402c-a9f2-5db3dfa6dd6d
exl-id: 913e1fee-b071-4152-94c3-dd7b8900e5ed
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# Kompilera testplanen{#compiling-your-test-plan}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

De enskilda testfallen sammanförs sedan i din testplan, som också kommer att definiera:

## Prioriteringar

Vissa tester kommer att ha större betydelse än andra, så det är tillrådligt att ange deras prioritet.

Vissa tester kan t.ex. påverka ett Go-/No-Go-beslut och måste därför bekräftas vid varje testad interimsrelease.

## Iterationer

Om ditt projekt använder någon form av utvecklingsiteration (med flera releaser tillgängliga) kan du behöva eller vill ha en indikation på resultatet för varje iteration. Detta kan användas för att ange:

* vilka tester som ska omfattas av upprepningen.
* resultaten av tester som upprepas i olika iterationer.
* att prioritetstester och tester av grundläggande funktioner upprepas med regelbundna mellanrum.

## Tester

Vid något tillfälle kan du antingen utse rätt testgrupp eller en specifik testperson (eventuellt beroende på tillgänglighet och/eller erfarenhet).

## Sammanfattning eller översikt

För rapportering vill du ge en översikt över testresultaten:

* Procentandel av tester som redan omfattas.
* Procent lyckade/misslyckade.
* Specifika siffror för de prioriterade testerna.
