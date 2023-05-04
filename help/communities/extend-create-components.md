---
title: Skapa komponenterna
seo-title: Create the Components
description: Skapa komponenten Kommentarer
seo-description: Create the Comments component
uuid: ea6e00d4-1db7-40ef-ae49-9ec55df58adf
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 83c4f18a-d7d6-4090-88c7-41a9075153b5
exl-id: 48809969-5d14-41bb-bc6d-5857e679ceba
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '619'
ht-degree: 3%

---

# Skapa komponenterna {#create-the-components}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Exemplet med utökade komponenter använder kommentarsystemet, som i själva verket består av två komponenter

* Kommentarer - det övergripande kommentarsystemet, som är den komponent som placeras på en sida
* Kommentar - Komponenten som hämtar en instans av en publicerad kommentar

Båda komponenterna måste installeras, särskilt om du anpassar utseendet på en publicerad kommentar.

>[!NOTE]
>
>Endast ett kommentarssystem per webbplatssida tillåts.
>
>Många webbgruppsfunktioner innehåller redan ett kommentarssystem vars resourceType kan ändras för att referera till det utökade kommentarsystemet.

## Skapa komponenten Kommentarer {#create-the-comments-component}

I de här riktningarna anges **Grupp** annat än `.hidden` så att komponenten kan göras tillgänglig från komponentens webbläsare (sidospark).

Borttagningen av den automatiskt skapade JSP-filen beror på att HBS-standardfilen används i stället.

1. Bläddra till **CRXDE|Lite** ([http://localhost:4502/crx/de/index.jsp](http://localhost:4502/crx/de/index.jsp))

1. Skapa en plats för anpassade program:

   * Välj `/apps` nod

      * **Skapa mapp** namngiven **[!UICONTROL custom]**
   * Välj `/apps/custom` nod

      * **Skapa mapp** namngiven **[!UICONTROL components]**


1. Välj `/apps/custom/components` nod

   * **[!UICONTROL Create > Component...]**

      * **Etikett**: *kommentarer*
      * **Titel**: *Alt-kommentarer*
      * **Beskrivning**: *Format för alternativa kommentarer*
      * **Supertyp**: *social/gemensam/komponent/hbs/comments*
      * **Grupp**: *Egen*
   * Välj **[!UICONTROL Next]**
   * Välj **[!UICONTROL Next]**
   * Välj **[!UICONTROL Next]**
   * Välj **[!UICONTROL OK]**


1. Expandera noden som nyss skapades: `/apps/custom/components/comments`
1. Välj **[!UICONTROL Save All]**
1. Högerklicka `comments.jsp`
1. Välj **[!UICONTROL Delete]**
1. Välj **[!UICONTROL Save All]**

![chlimage_1-70](assets/chlimage_1-70.png)

### Skapa den underordnade kommentarskomponenten {#create-the-child-comment-component}

De här riktningarna har angetts **Grupp** till `.hidden` eftersom endast den överordnade komponenten ska inkluderas på en sida.

Borttagningen av den automatiskt skapade JSP-filen beror på att HBS-standardfilen används i stället.

1. Navigera till `/apps/custom/components/comments` nod
1. Högerklicka på noden

   * Välj **[!UICONTROL Create > Component...]**

      * **Etikett**: *kommentar*
      * **Titel**: *Alt-kommentar*
      * **Beskrivning**: *Alternativ kommentarsstil*
      * **Supertyp**: *social/gemensam/komponent/hbs/comments/comment*
      * **Grupp**: `*.hidden*`
   * Välj **[!UICONTROL Next]**
   * Välj **[!UICONTROL Next]**
   * Välj **[!UICONTROL Next]**
   * Välj **[!UICONTROL OK]**


1. Expandera noden som nyss skapades: `/apps/custom/components/comments/comment`
1. Välj **[!UICONTROL Save All]**
1. Högerklicka `comment.jsp`
1. Välj **[!UICONTROL Delete]**
1. Välj **[!UICONTROL Save All]**

![chlimage_1-71](assets/chlimage_1-71.png) ![chlimage_1-72](assets/chlimage_1-72.png)

### Kopiera och ändra standard-HBS-skript {#copy-and-modify-the-default-hbs-scripts}

Använda [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Kopiera `comments.hbs`

   * Från [/libs/social/Commons/components/hbs/comments](http://localhost:4502/crx/de/index.jsp#/libs/social/commons/components/hbs/comments)
   * Till [/apps/custom/components/comments](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments)

* Redigera `comments.hbs` till:

   * Ändra värdet för `data-scf-component` attribute (~line 20):

      * Från `social/commons/components/hbs/comments`
      * Till `/apps/custom/components/comments`
   * Ändra om du vill ta med den anpassade kommentarkomponenten (~line 75):

      * Ersätt `{{include this resourceType='social/commons/components/hbs/comments/comment'}}`
      * Med `{{include this resourceType='/apps/custom/components/comments/comment'}}`


* Kopiera `comment.hbs`

   * Från [/libs/social/commons/components/hbs/comments/comment](http://localhost:4502/crx/de/index.jsp#/libs/social/commons/components/hbs/comments/comment)
   * Till [/apps/custom/components/comments/comment](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comment)

* Redigera `comment.hbs` till:

   * Ändra värdet på data-scf-component-attributet (~ line 19)

      * Från `social/commons/components/hbs/comments/comment`
      * Till `/apps/custom/components/comments/comment`

* Välj `/apps/custom` nod
* Välj **[!UICONTROL Save All]**

## Skapa en biblioteksmapp för klient {#create-a-client-library-folder}

För att undvika att explicit inkludera det här klientbiblioteket kan kategorivärdet för standardkommentarsystemets klientlib användas ( `cq.social.author.hbs.comments`), men sedan inkluderas klientlib även för alla instanser av standardkomponenten.

Använda [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Välj `/apps/custom/components/comments` nod
* Välj **[!UICONTROL Create Node]**

   * **Namn**: `clientlibs`
   * **Typ**: `cq:ClientLibraryFolder`
   * Lägg till i **[!UICONTROL Properties]** tab:

      * **Namn** `categories` **Typ** `String` **Värde** `cq.social.author.hbs.comments` `Multi`
      * **Namn** `dependencies` **Typ** `String` **Värde** `cq.social.scf` `Multi`

* Välj **[!UICONTROL Save All]**
* Med `/apps/custom/components/comments/clientlib`När noden är markerad skapar du 3 filer:

   * **Namn**: `css.txt`
   * **Namn**: `js.txt`
   * **Namn**: customcommentsystem.js

* Ange &#39;customcommentsystem.js&#39; som innehåll i `js.txt`
* Välj **[!UICONTROL Save All]**

![chlimage_1-73](assets/chlimage_1-73.png)

## Registrera SCF-modellen och vyn {#register-the-scf-model-view}

När du utökar (åsidosätter) en SCF-komponent är resourceType annorlunda (overlay använder den relativa sökfunktionen som söker igenom `/apps` före `/libs` så att resourceType förblir densamma). Därför måste du skriva JavaScript (i klientbiblioteket) för att registrera SCF JS-modellen och visa för den anpassade resourceType.

Ange följande text som innehåll i `customcommentsystem.js`:

### customcommentsystem.js {#customcommentsystem-js}

```xml
(function($CQ, _, Backbone, SCF) {
    "use strict";
 
    var CustomComment = SCF.Components["social/commons/components/hbs/comments/comment"].Model;
    var CustomCommentView = SCF.Components["social/commons/components/hbs/comments/comment"].View;

    var CustomCommentSystem = SCF.Components["social/commons/components/hbs/comments"].Model;
    var CustomCommentSystemView = SCF.Components["social/commons/components/hbs/comments"].View;
 
    SCF.registerComponent('/apps/custom/components/comments/comment', CustomComment, CustomCommentView);
    SCF.registerComponent('/apps/custom/components/comments', CustomCommentSystem, CustomCommentSystemView);

})($CQ, _, Backbone, SCF);
```

* Välj **[!UICONTROL Save All]**

## Publicera appen {#publish-the-app}

För att den utökade komponenten ska fungera i publiceringsmiljön måste den anpassade komponenten replikeras.

Ett sätt att göra detta är att

* Från global navigering

   * Välj **[!UICONTROL Tools > Deployment > Replication]**
   * Välj `Activate Tree`
   * Ange `Start Path`: till `/apps/custom`
   * Avmarkera `Only Modified`
   * Välj `Activate`knapp
