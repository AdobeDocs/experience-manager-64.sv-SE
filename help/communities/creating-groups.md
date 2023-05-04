---
title: Community-grupper
seo-title: Community Groups
description: Skapa communitygrupper
seo-description: Creating community groups
uuid: 05429b23-9083-498c-9eb3-d49b049d9446
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 868a3d5d-d505-4ce5-8776-5bbe68a30ccb
exl-id: 4b663228-9cb6-45c0-99dd-8dd7fc2aa4a6
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '542'
ht-degree: 1%

---

# Community-grupper {#community-groups}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Funktionen för communitygrupper är möjligheten för en undercommunity att skapas dynamiskt på en community-webbplats av behöriga användare (community-medlemmar och författare) från publicerings- och författarmiljöerna.

Den här möjligheten finns när [gruppfunktion](functions.md#groups-function) finns i [communitywebbplats](sites-console.md) struktur.

A [community-gruppmall](tools-groups.md) innehåller designen för communitygruppssidan när en community-grupp skapas dynamiskt.

En eller flera gruppmallar väljs för gruppfunktionen när funktionen läggs till i en community-webbplatsstruktur eller i en community-webbplatsmall. Den här listan över gruppmallar visas för den medlem eller författare som dynamiskt skapar en ny grupp på communitywebbplatsen.

## Skapa en ny grupp {#creating-a-new-group}

Möjligheten att skapa en ny community-grupp bygger på att det finns en community-webbplats som innehåller gruppfunktioner, till exempel en som skapats från ` [Reference Site Template](sites.md)`.

Exemplen som följer använder den communitywebbplats som skapats från `Reference Site Template` enligt beskrivningen i [Komma igång med AEM Communities](getting-started.md) självstudiekurs.

Det här är sidan som läses in vid publicering när **[!UICONTROL Groups]** menyalternativet är markerat:

![chlimage_1-236](assets/chlimage_1-236.png)

När du väljer **[!UICONTROL New Group]** visas en redigeringsdialogruta.

Under **[!UICONTROL Settings]** tillhandahåller du grundläggande funktioner för gruppen:

![chlimage_1-237](assets/chlimage_1-237.png)

* **[!UICONTROL Group Name]**
Namnet på gruppen som ska visas på communitywebbplatsen.

* **[!UICONTROL Description]**
En beskrivning av gruppen som ska visas på communitywebbplatsen.

* **[!UICONTROL Invite]**
En lista med medlemmar som ska bjudas in för att gå med i gruppen. I typsnittssökningen ges förslag på communitymedlemmar som ska bjudas in.

* **[!UICONTROL Group URL Name]**
Namnet på gruppsidan som blir en del av URL:en.

* **[!UICONTROL Open Group]**
Markera 
`Open Group` visar att en anonym besökare kan visa innehållet och kommer att avmarkera `Member Only Group`.

* **[!UICONTROL Member Only Group]**
Markera 
`Member Only Group` visar att endast medlemmar i gruppen kan visa innehållet och avmarkerar `Open Group`.

Under **[!UICONTROL Template]** -fliken är möjligheten att välja från listan med communitygruppsmallar som angavs när gruppfunktionen inkluderades i communityplatsens struktur eller i en community-platsmall.

![chlimage_1-238](assets/chlimage_1-238.png)

Under **[!UICONTROL Image]** är möjligheten att överföra en bild som ska visas för gruppen på gruppwebbplatsens gruppsida. Standardformatmallen ändrar bildens storlek till 170 x 90 pixlar.

![chlimage_1-239](assets/chlimage_1-239.png)

Genom att välja **[!UICONTROL Create Group]** -knappen skapas sidorna för gruppen baserat på den valda mallen, och en användargrupp skapas för medlemskap och sidan Grupper uppdateras för att visa den nya undergruppen.

Sidan Grupper med en ny undercommunity med namnet&quot;Focus Group&quot;, som en miniatyrbild överfördes för, ser ut så här (fortfarande inloggad som administratör för en community-grupp):

![chlimage_1-240](assets/chlimage_1-240.png)

Markera `Focus Group` kommer att öppna sidan Fokusgrupp i webbläsaren, som har ett ursprungligt utseende baserat på den valda mallen, och som innehåller en undermeny under den huvudsakliga communitywebbplatsens meny:

![chlimage_1-241](assets/chlimage_1-241.png)

## Medlemslistkomponent för community {#community-group-member-list-component}

The `Community Group Member List` -komponenten är avsedd för utvecklare av gruppmallar.

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande om communitygrupper](essentials-groups.md) för utvecklare.

Mer information om communitygrupper finns på [Hantera användare och användargrupper](users.md).
