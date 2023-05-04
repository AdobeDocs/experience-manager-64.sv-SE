---
title: Ändra utseendet
seo-title: Alter the Appearance
description: Ändra skriptet
seo-description: Modify the script
uuid: 6930381b-74c1-4e63-9621-621dbedbc25e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: da3891d3-fa07-4c88-b4ac-077926b3a674
exl-id: 01a20578-56c3-41b3-8a0e-281104af2481
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '241'
ht-degree: 2%

---

# Ändra utseendet {#alter-the-appearance}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Ändra skriptet {#modify-the-script}

Skriptet comment.hbs ansvarar för att skapa det övergripande HTML för varje kommentar.

Så här visar du inte avataren bredvid varje publicerad kommentar:

1. Kopiera `comment.hbs`från `libs`till `apps`
   1. Välj `/libs/social/commons/components/hbs/comments/comment/comment.hbs`
   1. Välj **[!UICONTROL Copy]**
   1. Välj `/apps/social/commons/components/hbs/comments/comment`
   1. Välj **[!UICONTROL Paste]**
1. Öppna överlägg `comment.hbs`
   * Dubbelklicka på noden  `comment.hbs`in `/apps/social/commons/components/hbs/comments/comment folder`
1. Hitta följande rader och ta bort eller kommentera dem:

   ```xml
   <aside class="scf-comment-author">
           <img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
   ```

Radera raderna eller omge dem med &#39;&lt;!>—&#39; och &#39;—>&#39; för att kommentera dem. Dessutom läggs tecknen &#39;xxx&#39; till som en visuell indikator på var avataren skulle ha varit.

```xml
<!-- do not display avatar with comment
    <aside class="scf-comment-author">
        <img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
```

## Replikera övertäckningen {#replicate-the-overlay}

Överlagrade kommentarer skickas till publiceringsinstansen med replikeringsverktyget.

>[!NOTE]
>
>En robustare form av replikering skulle vara att skapa ett paket i Package Manager och [activate](../../help/sites-administering/package-manager.md#replicating-packages) den. Ett paket kan exporteras och arkiveras.

Välj **[!UICONTROL Tools > Deployment > Replication]** och sedan **[!UICONTROL Activate Tree]**.

Ange startsökvägen `/apps/social/commons` och markera **[!UICONTROL Activate]**.

![chlimage_1-42](assets/chlimage_1-42.png)

## Visa resultat {#view-results}

Om du loggar in på publiceringsinstansen som administratör, t.ex. http://localhost:4503/crx/de som administratör/administratör, kan du verifiera att de överliggande komponenterna finns där.

Om du loggar ut och loggar in igen som `aaron.mcdonald@mailinator.com/password` och uppdatera sidan, observera att den publicerade kommentaren inte längre visas med en avatar, i stället visas en enkel &#39;xxx&#39;.

![chlimage_1-43](assets/chlimage_1-43.png)
