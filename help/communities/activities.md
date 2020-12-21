---
title: Funktionen Aktivitetsströmmar
seo-title: Funktionen Aktivitetsströmmar
description: En inloggad community-medlems verksamhet
seo-description: En inloggad community-medlems verksamhet
uuid: 8a05a5ed-0edf-4528-a145-f9dc37d10247
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: ccaebb4c-cc1c-4ee7-b080-99667f348427
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 1%

---


# Aktivitetsströmmar, funktion {#activity-streams-feature}

## Introduktion {#introduction}

Aktiviteter som tillhör en signerad medlem i communityn, till exempel publicering på ett forum eller en blogg, samlas i en ström som kan filtreras och visas på olika sätt genom konfiguration av `Activity Streams`-komponenten.

Möjligheten att följa ger en annan bild av aktiviteter när communitymedlemmar följer inlägg av intresse eller följer aktiviteter som andra communitymedlemmar utför.

Detta avsnitt i dokumentationen beskriver

* Lägga till komponenten Activity Streams på en AEM
* Konfigurationsinställningar för komponenten för aktivitetsströmmar

## Lägga till aktivitetsströmmar på en sida {#adding-activity-streams-to-a-page}

Om du vill lägga till en `Activity Streams`-komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på

* `Communities / Activity Streams`

och dra den till rätt plats på en sida där aktivitetsströmmar ska visas.

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](essentials-activities.md#essentials-for-client-side) inkluderas visas `Activity Streams`-komponenten så här:

![chlimage_1-195](assets/chlimage_1-195.png)

## Konfigurerar aktivitetsströmmar {#configuring-activity-streams}

Markera den monterade `Activity Streams`-komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-196](assets/chlimage_1-196.png)

Under fliken **[!UICONTROL User Activities]** anger du vilka aktiviteter som ska visas:

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

Komponenter måste konfigureras för att aktivera följande. Följande funktioner tillåter [blogg](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [kalender](calendar.md), [filelibrary](file-library.md) och [kommentarer](comments.md).

![chlimage_1-198](assets/chlimage_1-198.png)

Med knappen **Följ** kan du följa poster som aktiviteter, [meddelanden](notifications.md) och/eller [prenumerationer](subscriptions.md). Varje gång knappen **Följ** är markerad går det att aktivera eller inaktivera en markering. Markeringen `Email Subscriptions` finns bara när den är konfigurerad.

Om någon av följande metoder är markerad ändras knappens text till **Följande**. Du kan av praktiska skäl välja `Unfollow All` för att inaktivera alla metoder.

Knappen **Följ** visas:

* När en annan medlems profil visas
* På en huvudfunktionssida, till exempel forum, QnA och bloggar
   * Följer alla aktiviteter för den allmänna funktionen

* För ett visst inlägg, t.ex. ett forumämne, en QnA-fråga eller en bloggartikel
   * Följer all aktivitet för den specifika posten

## Ytterligare information {#additional-information}

Mer information finns på sidan [Activity Streams Essentials](essentials-activities.md) för utvecklare.
