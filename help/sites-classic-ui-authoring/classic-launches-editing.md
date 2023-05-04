---
title: Redigera Launches
seo-title: Editing Launches
description: När en startsida har skapats för en sida (eller en uppsättning sidor) kan du redigera innehållet i startkopian av sidorna.
seo-description: When a launch has been created for a page (or set of pages) you can edit the content in the launch copy of the page(s).
uuid: 3a310eeb-553d-4d2b-98b5-c5bc523b2aca
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 666b967a-e94b-4f94-a676-00adf150580f
legacypath: /content/docs/en/aem/6-0/author/site-page-features/launches
exl-id: 98bccd13-431a-4cba-bb93-75cdcc98830a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 1%

---

# Redigera Launches{#editing-launches}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Redigera startsidor {#editing-launch-pages}

När en startsida har skapats för en sida (eller en uppsättning sidor) kan du redigera innehållet i startkopian av sidorna.

1. Öppna sidan för redigering.
1. I Sidekick väljer du **Versionshantering** och sedan expandera **Startar** grupp. Titeln på den programstart som redigeras använder ett fet teckensnitt.

   ![chlimage_1-13](assets/chlimage_1-13.jpeg)

1. Välj den start du vill arbeta med och klicka sedan på **Byt**.
1. Börja redigera.

   >[!NOTE]
   >
   >Du kan använda **Sida** flik för att utföra åtgärder som **Skapa underordnad sida**, bland annat.

## Redigera en startkonfiguration {#editing-a-launch-configuration}

När du har skapat en programstart kan du ändra startnamnet och startdatumet. Du kan också ange en bild som ska associeras med starten.

1. Öppna administrationssidan för starter ([http://localhost:4502/libs/launches/content/admin.html](http://localhost:4502/libs/launches/content/admin.html)).

1. Välj önskad start och klicka på **Redigera** för att öppna dialogrutan:

   * I **Allmänt** kan du redigera:

      * **Titel**
      * **Live-datum**: detta motsvarar startdatumet
      * **Produktionsklar**

      Se [Startar - ordningen för händelser](/help/sites-authoring/launches.md#launches-the-order-of-events) för information om syftet med och interaktionen med dessa fält.

   * I **Bild** kan du överföra en bildfil.


1. Klicka **Spara**.

## Identifiera startstatus för en sida {#discovering-the-launch-status-of-a-page}

När du redigerar en startsida visas information om startsidan längst ned i **Versionshantering** fliken Sidekick:

* Startnamnet.
* Tiden sedan den senaste ändringen.
* Den användare som utförde den senaste ändringen.
* Status för **Produktionsklar** flagga (orange=inte inställd; green=set).

![chlimage_1-186](assets/chlimage_1-186.png)
