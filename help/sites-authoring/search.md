---
title: Sökning
seo-title: Search
description: Hitta materialet snabbare med omfattande sökfunktioner
seo-description: Find your content faster with comprehensive search
uuid: 1e80cf85-653f-4dde-930a-de05415b994f
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: cd87e1e8-5329-4e60-ac9d-2705f54d0da6
exl-id: 9e93b28b-627d-4676-82a6-d719de4d152a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '548'
ht-degree: 5%

---

# Sökning{#search-features}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

I författarmiljön i AEM finns olika sätt att söka efter innehåll, beroende på resurstypen.

>[!NOTE]
>
>Utanför redigeringsmiljön finns det även andra sökfunktioner, till exempel [Query Builder](/help/sites-developing/querybuilder-api.md) och [CRXDE Lite](/help/sites-developing/developing-with-crxde-lite.md).

## Grunderna i sökning {#search-basics}

Sökfunktionen finns i det övre verktygsfältet:

![](do-not-localize/chlimage_1-17.png)

Med sökfältet kan du:

* Sök efter ett specifikt nyckelord, en viss sökväg eller en viss tagg.
* Filtrera enligt resursspecifika kriterier som ändrade datum, sidstatus, filstorlek osv.
* Definiera och använda en [sparad sökning](#saved-searches) - baserat på ovanstående kriterier.

>[!NOTE]
>
>Sökningen kan även anropas med snabbtangenten `/` (snedstreck) när sökfältet visas.

## Sök och filtrera {#search-and-filter}

Så här söker och filtrerar du resurser:

1. Öppna **Sök** (med förstoringsglaset i verktygsfältet) och ange söktermen. Förslag kommer att göras och kan väljas:

   ![screen_shot_2018-03-23at101404](assets/screen_shot_2018-03-23at101404.png)

   Som standard begränsas sökresultaten till din aktuella plats (dvs. konsol och relaterad resurstyp):

   ![screen_shot_2018-03-23at101445](assets/screen_shot_2018-03-23at101445.png)

1. Om det behövs kan du ta bort platsfiltret (välj **X** på det filter som du vill ta bort) för att söka i alla konsoler/resurstyper.
1. Resultaten visas, grupperade efter konsol och relaterad resurstyp.

   Du kan antingen välja en specifik resurs (för ytterligare åtgärder) eller gå nedåt genom att välja önskad resurstyp; till exempel **Visa alla platser**:

   ![screen_shot_2018-03-23at101523](assets/screen_shot_2018-03-23at101523.png)

1. Om du vill gå längre ned väljer du skensymbolen (längst upp till vänster) för att öppna sidopanelen **Filter och alternativ**.

   ![](do-not-localize/screen_shot_2018-03-23at101542.png)

   I enlighet med resurstypen Sök visas ett fördefinierat urval av söknings-/filtervillkor.

   På sidopanelen kan du välja:

   * Sparade sökningar
   * Sökkatalog
   * Taggar
   * Sökvillkor; till exempel Ändrade datum, Publiceringsstatus, LiveCopy-status.

   >[!NOTE]
   >
   >Sökvillkoren kan variera:
   >
   >* Beroende på vilken resurstyp du har valt; Exempelvis är kriterierna Assets och Communities begripligt specialiserade.
   >* Din instans som [Sök i Forms](/help/sites-administering/search-forms.md) kan anpassas (lämpligt för platsen i AEM).


   ![screen_shot_2018-03-23at101619](assets/screen_shot_2018-03-23at101619.png)

1. Du kan även lägga till ytterligare söktermer:

   ![screen_shot_2018-03-23at101710](assets/screen_shot_2018-03-23at101710.png)

1. Stäng **sökningen** med **X** (överst till höger).

>[!NOTE]
>
>Sökvillkoren sparas när du väljer ett objekt i sökresultatet.
>
>När du markerar ett objekt på sökresultatsidan och återgår till söksidan efter att du har använt knappen för att återställa webbläsaren, kvarstår sökvillkoren.

## Sparade sökningar {#saved-searches}

Förutom att söka efter en mängd olika aspekter kan du även spara en viss sökkonfiguration för hämtning och användning i ett senare skede:

1. Definiera sökvillkor och välj **Spara**.

   ![screen_shot_2018-03-23at101710-1](assets/screen_shot_2018-03-23at101710-1.png)

1. Tilldela ett namn och använd sedan **Spara** för att bekräfta:

   ![screen_shot_2018-03-23at101852](assets/screen_shot_2018-03-23at101852.png)

1. Din sparade sökning är tillgänglig från väljaren nästa gång du öppnar sökpanelen:

   ![screen_shot_2018-03-23at102128](assets/screen_shot_2018-03-23at102128.png)

1. När du har sparat kan du:

   * Använd **x** (mot namnet på den sparade sökningen) för att starta en ny fråga (den sparade sökningen tas inte bort).
   * **Redigera sparad sökning**, ändra sökvillkoren och sedan **Spara** igen.

Du kan ändra sparade sökningar genom att markera den sparade sökningen och klicka på **Redigera sparad sökning** längst ned på sökpanelen.

![screen_shot_2018-03-23at102213](assets/screen_shot_2018-03-23at102213.png)
