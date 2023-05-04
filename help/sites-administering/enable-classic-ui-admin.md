---
title: Admin Console
seo-title: Admin Consoles
description: Lär dig hur du använder Admin Console som finns i AEM.
seo-description: Lear how to use the Admin Consoles available in AEM.
uuid: 701dc57c-f7b4-421e-a847-577ae2585e80
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 98ba3093-1edb-4891-abbe-47cf6e4f1feb
exl-id: f3c03562-aaeb-4d43-aee1-d92d661ee329
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '263'
ht-degree: 0%

---

# Admin Console{#admin-consoles}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Som standard har möjligheten att växla till det klassiska användargränssnittet via administratörskonsolerna inaktiverats. Därför visas inte längre de popup-ikoner som visades när användaren placerade musen över vissa konsolikoner, vilket ger åtkomst till det klassiska gränssnittet.

![screen_shot_2018-03-23at11956](assets/screen_shot_2018-03-23at111956.png)

Alla konsoler som har en klassisk användargränssnittsversion i `/libs/cq/core/content/nav` kan återaktiveras individuellt så att **Klassiskt användargränssnitt** igen visas konsolikonen igen när användaren för musen över den.

I det här exemplet återaktiverar vi det klassiska gränssnittet för webbplatskonsolen.

1. Använd CRXDE Lite för att hitta noden som motsvarar den Admin Console som du vill aktivera Classic-gränssnittet för igen. De finns under:

   `/libs/cq/core/content/nav`

   Till exempel

   [ `http://localhost:4502/crx/de/index.jsp#/libs/cq/core/content/nav`](http://localhost:4502/crx/de/index.jsp#/libs/cq/core/content/nav)

1. Markera noden som motsvarar konsolen som du vill återaktivera det klassiska användargränssnittet för. Vi kommer till exempel att återaktivera det klassiska användargränssnittet för webbplatskonsolen.

   `/libs/cq/core/content/nav/sites`

1. Skapa en övertäckning med **Överläggsnod** option; till exempel:

   * **Bana**: `/apps/cq/core/content/nav/sites`
   * **Överläggsplats**: `/apps/`
   * **Matcha nodtyper**: aktiv (markera kryssrutan)

1. Lägg till följande boolesk egenskap till den överlagrade noden:

   `enableDesktopOnly = {Boolean}true`

1. The **Klassiskt användargränssnitt** Alternativet är igen tillgängligt som ett poseralternativ i Admin Console.

   ![screen_shot_2018-03-23at11924](assets/screen_shot_2018-03-23at111924.png)

Upprepa dessa steg för varje konsol som du vill återaktivera åtkomst till den klassiska användargränssnittsversionen för.
