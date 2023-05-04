---
title: Lägga till teckensnitt för grafikåtergivning
seo-title: Adding Fonts for Graphic-Rendering
description: Med AEM kan du skapa grafik som innehåller text dynamiskt från ditt innehåll
seo-description: AEM allows you to generate graphics incorporating text dynamically taken from your content
uuid: 67d9b10f-e986-4d29-bde2-10e08075fe17
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 6af48ef5-75e6-4b66-bc0d-ecf254b1c4ef
exl-id: f29868e3-d05c-4898-94d1-0c77ab6b72eb
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---

# Lägga till teckensnitt för grafikåtergivning{#adding-fonts-for-graphic-rendering}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med AEM kan du skapa grafik som innehåller text dynamiskt från ditt innehåll.

Om du vill göra det kan du även läsa in och använda dina egna teckensnitt.

För närvarande stöder alla implementeringar av Java Platform [TrueType](https://en.wikipedia.org/wiki/Truetype) teckensnitt.

1. Öppna CRXDE Lite och navigera till projektprogrammappen:

   `/apps/<your-project>/`

1. Under `/apps/<your-project>/` skapa en ny nod:

   * **Namn**: `fonts`
   * **Typ**: `sling:Folder`

   Spara alla ändringar.

1. Kopiera teckensnittsfilerna till denna mapp; till exempel med WebDAV.

   >[!NOTE]
   >
   >Teckensnittsfiler i databasen måste ha suffixet `*.ttf` eller `*.TTF`.

1. Uppdatera [OSGi-konfiguration](/help/sites-deploying/configuring-osgi.md) av [Day Commons GFX Font Helper](/help/sites-deploying/osgi-configuration-settings.md). Lägg till sökvägen till teckensnittsmappen; dvs. `/apps/<your-project>/fonts`.

1. Återvänd till CRXDE Lite. Nu bör du se en `.fontlist` i mappen som innehåller namnet på de importerade teckensnitten.

   Dessa teckensnitt kan nu användas i Java API.

Mer information om hur du använder teckensnitten med Java API finns i [dokumentation för klassen Font i Java API](https://download.oracle.com/javase/6/docs/api/java/awt/Font.html).
