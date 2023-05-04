---
title: Redigerare
seo-title: Editor
description: Lär dig hur du växlar tillbaka till den klassiska gränssnittsredigeraren.
seo-description: Learn how to switch back to the Classic UI Editor.
uuid: 78ba4db0-affa-4081-bf29-a3306720c968
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 5fca5401-502d-483b-bfc1-ef53e2c041b7
exl-id: 04a9c595-9a73-4a8a-99ae-c2292882338f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '138'
ht-degree: 2%

---

# Redigerare{#editor}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Som standard har möjligheten att växla till det klassiska användargränssnittet från redigeraren inaktiverats.

![chlimage_1-9](assets/chlimage_1-9.png)

Aktivera alternativet igen **Öppna i Classic UI** i **Sidinformation** gör du så här.

1. Använd CRXDE Lite för att hitta följande nod:

   `/libs/wcm/core/content/editor/jcr:content/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui`

   Till exempel

   `http://localhost:4502/crx/de/index.jsp#/libs/wcm/core/content/editor/jcr%3Acontent/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui](http://localhost:4502/crx/de/index.jsp#/libs/wcm/core/content/editor/jcr%3Acontent/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui`

1. Skapa en övertäckning med **Överläggsnod** option; till exempel:

   * **Bana**: `/apps/wcm/core/content/editor/jcr:content/content/items/content/header/items/headerbar/items/pageinfopopover/items/list/items/classicui`
   * **Överläggsplats**: `/apps/`
   * **Matcha nodtyper**: aktiv (markera kryssrutan)

1. Lägg till följande text-egenskap med flera värden i den åsidosatta noden:

   `sling:hideProperties = ["granite:hidden"]`

1. The **Öppna i Classic UI** finns igen i **Sidinformation** när du redigerar sidor.

   ![chlimage_1-10](assets/chlimage_1-10.png)
