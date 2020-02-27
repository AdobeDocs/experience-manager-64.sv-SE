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

---


# Funktionen Aktivitetsströmmar {#activity-streams-feature}

## Introduktion {#introduction}

En inloggad community-medlems aktiviteter, till exempel publicering på ett forum eller i en blogg, samlas i en ström som kan filtreras och visas på olika sätt genom att `Activity Streams` komponenten konfigureras.

Möjligheten att följa ger en annan bild av aktiviteter när communitymedlemmar följer inlägg av intresse eller följer aktiviteter som andra communitymedlemmar utför.

Detta avsnitt i dokumentationen beskriver

* Lägga till komponenten Activity Streams på en AEM-webbplats
* Konfigurationsinställningar för komponenten för aktivitetsströmmar

## Lägga till aktivitetsströmmar till en sida {#adding-activity-streams-to-a-page}

Om du vill lägga till en `Activity Streams` komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att hitta

* `Communities / Activity Streams`

och dra den till rätt plats på en sida där aktivitetsströmmar ska visas.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](essentials-activities.md#essentials-for-client-side) inkluderas visas `Activity Streams` komponenten så här:

![chlimage_1-195](assets/chlimage_1-195.png)

## Konfigurera aktivitetsströmmar {#configuring-activity-streams}

Markera den monterade `Activity Streams` komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![chlimage_1-196](assets/chlimage_1-196.png)

Ange vilka aktiviteter som ska visas på fliken **[!UICONTROL Användaraktiviteter]** :

![chlimage_1-197](assets/chlimage_1-197.png)

* **[!UICONTROL Maximalt antal aktiviteter]** Antalet aktiviteter som ska visas
* **[!UICONTROL Sökväg till]** direktuppspelningsresurs Lämna tomt om du vill använda community-webbplatsen eller community-gruppen som standard. Direktuppspelningsresursens sökväg identifierar aktivitetskällan. Standardvärdet är tomt.
* **[!UICONTROL Visa vyn]** Användaraktiviteter, om den är markerad, innehåller aktivitetssidan en flik som filtrerar aktiviteter baserat på aktiviteter som genererats i communityn av den aktuella medlemmen. Standard är markerat.
* **[!UICONTROL Visa vyn]** Alla aktiviteter Om det här alternativet är markerat innehåller sidan Aktiviteter en flik som innehåller alla aktiviteter som har skapats i den community som den aktuella medlemmen har åtkomst till. Standard är markerat.
* **[!UICONTROL Visa följande vy]** Om det här alternativet är markerat innehåller aktivitetssidan en flik som filtrerar aktiviteter baserat på de som den aktuella medlemmen följer. Standard är markerat.

## Följande vy {#following-view}

Komponenter måste konfigureras för att aktivera följande. Funktioner som tillåter följande är [blogg](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [kalender](calendar.md), [filbibliotek](file-library.md)[](comments.md)och¥comments.

![chlimage_1-198](assets/chlimage_1-198.png)

Med knappen **Följ** kan du följa inmatningar som aktiviteter, [meddelanden](notifications.md)och/eller [prenumerationer](subscriptions.md). Varje gång knappen **Följ** är markerad går det att aktivera eller inaktivera en markering. Markeringen visas bara när den är konfigurerad. `Email Subscriptions`

Om någon av följande metoder är markerad ändras texten för knappen till **Följ**. Du kan välja `Unfollow All` att inaktivera alla metoder.

Knappen **Följ** visas:

* När en annan medlems profil visas
* På en huvudfunktionssida, till exempel forum, QnA och bloggar
   * Följer alla aktiviteter för den allmänna funktionen

* För ett visst inlägg, t.ex. ett forumämne, en QnA-fråga eller en bloggartikel
   * Följer all aktivitet för den specifika posten

## Additional Information {#additional-information}

Mer information finns på sidan [Activity Streams Essentials](essentials-activities.md) för utvecklare.
