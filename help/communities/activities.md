---
title: Funktionen Aktivitetsströmmar
seo-title: Activity Streams Feature
description: En inloggad community-medlems verksamhet
seo-description: Activities of a signed-in community member
uuid: 8a05a5ed-0edf-4528-a145-f9dc37d10247
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: ccaebb4c-cc1c-4ee7-b080-99667f348427
exl-id: e62b7c0d-5004-4672-9fdc-566ece2785c9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 1%

---

# Funktionen Aktivitetsströmmar {#activity-streams-feature}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

En inloggad community-medlems aktiviteter, till exempel publicering på ett forum eller en blogg, samlas i en ström som kan filtreras och visas på olika sätt genom att konfigurationen av `Activity Streams` -komponenten.

Möjligheten att följa ger en annan bild av aktiviteter när communitymedlemmar följer inlägg av intresse eller följer aktiviteter som andra communitymedlemmar utför.

Detta avsnitt i dokumentationen beskriver

* Lägga till komponenten Activity Streams på en AEM
* Konfigurationsinställningar för komponenten för aktivitetsströmmar

## Lägga till aktivitetsströmmar till en sida {#adding-activity-streams-to-a-page}

Om du vill lägga till en `Activity Streams` -komponent till en sida i redigeringsläge använder du komponentwebbläsaren för att leta upp

* `Communities / Activity Streams`

och dra den till rätt plats på en sida där aktivitetsströmmar ska visas.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](essentials-activities.md#essentials-for-client-side) ingår så här `Activity Streams` visas:

![chlimage_1-195](assets/chlimage_1-195.png)

## Konfigurera aktivitetsströmmar {#configuring-activity-streams}

Markera den monterade `Activity Streams` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-196](assets/chlimage_1-196.png)

Under **[!UICONTROL User Activities]** -flik, ange vilka aktiviteter som ska visas:

![chlimage_1-197](assets/chlimage_1-197.png)

* **[!UICONTROL Max number of activities]**
Antalet aktiviteter som ska visas
* **[!UICONTROL Stream Resource Path]**
Lämna tomt som standard till communitywebbplatsen eller community-gruppen. Direktuppspelningsresursens sökväg identifierar aktivitetskällan. Standardvärdet är tomt.
* **[!UICONTROL Display User Activities View]**
Om det här alternativet är markerat kommer aktivitetssidan att innehålla en flik som filtrerar aktiviteter baserat på aktiviteter som genererats i communityn av den aktuella medlemmen. Standard är markerat.
* **[!UICONTROL Display All Activities View]**
Om det här alternativet är markerat kommer aktivitetssidan att innehålla en flik som innehåller alla aktiviteter som har skapats i den community som den aktuella medlemmen har åtkomst till. Standard är markerat.
* **[!UICONTROL Display Following View]**
Om det här alternativet är markerat innehåller aktivitetssidan en flik som filtrerar aktiviteter baserat på de som den aktuella medlemmen följer. Standard är markerat.

## Följande vy {#following-view}

Komponenter måste konfigureras för att aktivera följande. Funktioner som tillåter följande är [blogg](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [kalender](calendar.md), [filbibliotek](file-library.md)och [kommentarer](comments.md).

![chlimage_1-198](assets/chlimage_1-198.png)

The **Följ** knappen är ett sätt att följa inmatningar som aktiviteter, [meddelanden](notifications.md)och/eller [prenumerationer](subscriptions.md). Varje gång **Följ** är markerad går det att aktivera eller inaktivera en markering. The `Email Subscriptions` markeringen finns bara när den är konfigurerad.

Om någon av följande metoder är markerad ändras texten för knappen till **Följande**. Det går att välja `Unfollow All` för att växla mellan olika metoder.

The **Följ** visas:

* När en annan medlems profil visas
* På en huvudfunktionssida, till exempel forum, QnA och bloggar
   * Följer alla aktiviteter för den allmänna funktionen

* För ett visst inlägg, t.ex. ett forumämne, en QnA-fråga eller en bloggartikel
   * Följer all aktivitet för den specifika posten

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande om aktivitetsströmmar](essentials-activities.md) för utvecklare.
