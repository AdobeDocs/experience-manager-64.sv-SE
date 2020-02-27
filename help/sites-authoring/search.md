---
title: Sökning
seo-title: Sökning
description: Hitta materialet snabbare med omfattande sökfunktioner
seo-description: Hitta materialet snabbare med omfattande sökfunktioner
uuid: 1e80cf85-653f-4dde-930a-de05415b994f
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: cd87e1e8-5329-4e60-ac9d-2705f54d0da6
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Sökning{#search-features}

I författarmiljön i AEM finns olika sätt att söka efter innehåll, beroende på resurstypen.

>[!NOTE]
>
>Utanför redigeringsmiljön finns det även andra sökfunktioner, som [Query Builder](/help/sites-developing/querybuilder-api.md) och [CRXDE Lite](/help/sites-developing/developing-with-crxde-lite.md).

## Grunderna i sökning {#search-basics}

Sökfunktionen finns i det övre verktygsfältet:

![](do-not-localize/chlimage_1-17.png)

Med sökfältet kan du:

* Sök efter ett specifikt nyckelord, en viss sökväg eller en viss tagg.
* Filtrera enligt resursspecifika kriterier som ändrade datum, sidstatus, filstorlek osv.
* Definiera och använd en [sparad sökning](#saved-searches) baserat på ovanstående villkor.

>[!NOTE]
>
>Sökfunktionen kan också anropas med snabbtangenten `/` (snedstreck) när sökfältet visas.

## Sök och filtrera {#search-and-filter}

Så här söker och filtrerar du resurser:

1. Öppna **Sök** (med förstoringsglaset i verktygsfältet) och ange söktermen. Förslag kommer att göras och kan väljas:

   ![screen_shot_2018-03-23at101404](assets/screen_shot_2018-03-23at101404.png)

   Som standard begränsas sökresultaten till din aktuella plats (dvs. konsol och relaterad resurstyp):

   ![screen_shot_2018-03-23at101445](assets/screen_shot_2018-03-23at101445.png)

1. Om det behövs kan du ta bort platsfiltret (markera **X** på filtret som du vill ta bort) för att söka i alla konsoler/resurstyper.
1. Resultaten visas, grupperade efter konsol och relaterad resurstyp.

   Du kan antingen välja en specifik resurs (för ytterligare åtgärder) eller gå nedåt genom att välja önskad resurstyp; till exempel **Visa alla platser**:

   ![screen_shot_2018-03-23at101523](assets/screen_shot_2018-03-23at101523.png)

1. Om du vill gå vidare väljer du Rail-symbolen (längst upp till vänster) för att öppna sidopanelens **filter och alternativ**.

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
   >* Din instans som [sökformulär](/help/sites-administering/search-forms.md) kan anpassas (lämplig för platsen i AEM).


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

1. Definiera sökvillkoren och välj **Spara**.

   ![screen_shot_2018-03-23at101710-1](assets/screen_shot_2018-03-23at101710-1.png)

1. Tilldela ett namn och använd sedan **Spara** för att bekräfta:

   ![screen_shot_2018-03-23at101852](assets/screen_shot_2018-03-23at101852.png)

1. Din sparade sökning är tillgänglig från väljaren nästa gång du öppnar sökpanelen:

   ![screen_shot_2018-03-23at102128](assets/screen_shot_2018-03-23at102128.png)

1. När du har sparat kan du:

   * Använd **x** (mot namnet på den sparade sökningen) för att starta en ny fråga (den sparade sökningen tas inte bort).
   * **Redigera sparad sökning**, ändra sökvillkoren och **spara** igen.

Du kan ändra sparade sökningar genom att markera den sparade sökningen och klicka på **Redigera sparad sökning** längst ned på sökpanelen.

![screen_shot_2018-03-23at102213](assets/screen_shot_2018-03-23at102213.png)

