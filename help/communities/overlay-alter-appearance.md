---
title: Ändra utseendet
seo-title: Ändra utseendet
description: Ändra skriptet
seo-description: Ändra skriptet
uuid: 6930381b-74c1-4e63-9621-621dbedbc25e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: da3891d3-fa07-4c88-b4ac-077926b3a674
translation-type: tm+mt
source-git-commit: 1ae2d7f99286e0b958d343778159e2d35095510e
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 2%

---


# Ändra utseende {#alter-the-appearance}

## Ändra skriptet {#modify-the-script}

Skriptet comment.hbs ansvarar för att skapa den övergripande HTML-koden för varje kommentar.

Så här visar du inte avataren bredvid varje publicerad kommentar:

1. Kopiera `comment.hbs`från `libs`till `apps`
   1. Välj `/libs/social/commons/components/hbs/comments/comment/comment.hbs`
   1. Välj **[!UICONTROL Copy]**
   1. Välj `/apps/social/commons/components/hbs/comments/comment`
   1. Välj **[!UICONTROL Paste]**
1. Öppna det överliggande `comment.hbs`
   * Dubbelklicka på noden `comment.hbs`i `/apps/social/commons/components/hbs/comments/comment folder`
1. Hitta följande rader och ta bort eller kommentera dem:

   ```xml
   <aside class="scf-comment-author">
           <img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
   ```

Radera linjerna eller omge dem med &quot;&lt;!—&#39; och &#39;—>&#39; för att kommentera dem. Dessutom läggs tecknen &#39;xxx&#39; till som en visuell indikator på var avataren skulle ha varit.

```xml
<!-- do not display avatar with comment
    <aside class="scf-comment-author">
        <img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
```

## Replikera övertäckningen {#replicate-the-overlay}

Överlagrade kommentarer skickas till publiceringsinstansen med replikeringsverktyget.

>[!NOTE]
>
>En robustare form av replikering skulle vara att skapa ett paket i Package Manager och [aktivera](../../help/sites-administering/package-manager.md#replicating-packages) det. Ett paket kan exporteras och arkiveras.

I den globala navigeringen väljer du **[!UICONTROL Tools > Deployment > Replication]** och sedan **[!UICONTROL Activate Tree]**.

Ange `/apps/social/commons` som startsökväg och välj **[!UICONTROL Activate]**.

![chlimage_1-42](assets/chlimage_1-42.png)

## Visa resultat {#view-results}

Om du loggar in på publiceringsinstansen som administratör, t.ex. http://localhost:4503/crx/de som administratör/administratör, kan du verifiera att de överliggande komponenterna finns där.

Om du loggar ut och loggar in igen som `aaron.mcdonald@mailinator.com/password` och uppdaterar sidan, kommer du att märka att den publicerade kommentaren inte längre visas med en avatar, i stället visas en enkel &#39;xxx&#39;.

![chlimage_1-43](assets/chlimage_1-43.png)

