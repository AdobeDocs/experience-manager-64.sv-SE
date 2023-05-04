---
title: Ändra utseendet (HBS)
seo-title: Alter the Appearance
description: Ändra HBS-skript
seo-description: Modify the HBS scripts
uuid: 6e1030af-f170-4a60-9d3f-439afd05de57
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 70be208d-185b-4b27-8e01-74e62f656344
exl-id: 358b70b8-8122-4eda-baa7-d9a58d6901f9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# Ändra utseendet (HBS) {#alter-the-appearance-hbs}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Nu när komponenterna för det anpassade kommentarsystemet i programkatalogen (/apps) finns på plats, med en resourceSuperType som refererar till standardkommentarsystemet och den anpassade modellen/vyn registrerad, är det möjligt att ändra implementeringen.

För en enkel demonstration, en visuell funktion, tas den avatar som visas för den inloggade användaren som skickar en kommentar bort.

>[!NOTE]
>
>Om du vill använda tillägget måste instansen av kommentarsystemet på en webbplats som ska påverkas (/content) ange att dess resourceType ska vara det anpassade kommentarsystemet.

## Ändra HBS-skript {#modify-the-hbs-scripts}

Använda [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Öppna [/apps/custom/components/comments/comment/comment.hbs](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comment/comment.hbs)

   * Kommentera taggen som innehåller avataren för ett kommentarinlägg (~ line 21):

      ```
      <!--
       <<img class="scf-comment-avatar {{#if topLevel}}withTopLevel{{/if}}" src="{{author.avatarUrl}}"></img>
       -->
      ```

* Öppna [/apps/custom/components/comments/comments.hbs](http://localhost:4502/crx/de/index.jsp#/apps/custom/components/comments/comments.hbs)

   * Kommentera taggen som innehåller avataren för nästa kommentarspost (~ line 44):

      ```
      <!--
       <img class="scf-composer-avatar" src="{{loggedInUser.avatarUrl}}"></img>
       -->
      ```

* Välj **Spara alla**

## Replikera anpassad app {#replicate-custom-app}

När programmet har ändrats måste den anpassade komponenten replikeras om.

Ett sätt att göra detta är att

* Från huvudmenyn

   * Välj **[!UICONTROL Tools > Operations > Replication]**
   * Välj `Activate Tree`
   * Ange `Start Path`: till `/apps/custom`
   * Avmarkera `Only Modified`
   * Välj `Activate` knapp

## Visa ändrad kommentar på publicerad exempelsida {#view-modified-comment-on-published-sample-page}

[Fortsätta upplevelsen](extend-sample-page.md#publish-sample-page) i publiceringsinstansen, som fortfarande är inloggad som samma användare, är det nu möjligt att uppdatera sidan i publiceringsmiljön för att visa ändringen för att ta bort avataren:

![chlimage_1-81](assets/chlimage_1-81.png)

## Exempel på kommentartillägg {#sample-comment-extension-package}

Bifogat är ett paket med det anpassade kommentarprogrammet som skapas i den här självstudiekursen.

[Hämta fil](assets/sample-comment-extension-6-1-fp3.zip)
