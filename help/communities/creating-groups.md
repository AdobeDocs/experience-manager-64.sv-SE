---
title: Community-grupper
seo-title: Community-grupper
description: Skapa communitygrupper
seo-description: Skapa communitygrupper
uuid: 05429b23-9083-498c-9eb3-d49b049d9446
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 868a3d5d-d505-4ce5-8776-5bbe68a30ccb
translation-type: tm+mt
source-git-commit: 8c66f2b0053882bd1c998d8e01dbb0573881bc87

---


# Community-grupper {#community-groups}

Funktionen för communitygrupper är möjligheten för en undercommunity att skapas dynamiskt på en community-webbplats av behöriga användare (community-medlemmar och författare) från publicerings- och författarmiljöerna.

Den här möjligheten finns när [gruppfunktionen](functions.md#groups-function) finns i [communitywebbplatsens](sites-console.md) struktur.

En mall [för en](tools-groups.md) community-grupp ger designen för communitygruppssidan när en community-grupp skapas dynamiskt.

En eller flera gruppmallar väljs för gruppfunktionen när funktionen läggs till i en community-webbplatsstruktur eller i en community-webbplatsmall. Den här listan över gruppmallar visas för den medlem eller författare som dynamiskt skapar en ny grupp på communitywebbplatsen.

## Skapa en ny grupp {#creating-a-new-group}

Möjligheten att skapa en ny community-grupp bygger på att det finns en community-webbplats som innehåller gruppfunktionen, till exempel en som skapats från ` [Reference Site Template](sites.md)`.

Exemplen som följer använder den communitywebbplats som skapats från `Reference Site Template` enligt beskrivningen i självstudiekursen [Komma igång med AEM Communities](getting-started.md) .

Det här är sidan som läses in vid publicering när menyalternativet **[!UICONTROL Grupper]** är markerat:

![chlimage_1-236](assets/chlimage_1-236.png)

När du väljer ikonen **[!UICONTROL Ny grupp]** öppnas en redigeringsdialogruta.

Under fliken **[!UICONTROL Inställningar]** kan du ange gruppens grundläggande funktioner:

![chlimage_1-237](assets/chlimage_1-237.png)

* **[!UICONTROL Gruppnamn]** Namnet på gruppen som ska visas på communitywebbplatsen.

* **[!UICONTROL Beskrivning]** En beskrivning av gruppen som ska visas på communitywebbplatsen.

* **[!UICONTROL Bjud in]** en lista med medlemmar som ska bjudas in till gruppen. I typsnittssökningen ges förslag på communitymedlemmar som ska bjudas in.

* **[!UICONTROL Grupp-URL-namn]** Namnet på gruppsidan som blir en del av URL-adressen.

* **[!UICONTROL Open Group]** Selecting `Open Group` (Öppna gruppmarkering) anger att en anonym besökare kan visa innehållet och avmarkerar `Member Only Group`.

* **[!UICONTROL Gruppmarkering endast för medlemmar]** anger `Member Only Group` att endast medlemmar i gruppen kan visa innehållet och kommer att avmarkera `Open Group`.

Under fliken **[!UICONTROL Mall]** kan du välja från listan med gruppmallar som angavs när gruppfunktionen inkluderades i communityplatsens struktur eller i en mall för communitywebbplatser.

![chlimage_1-238](assets/chlimage_1-238.png)

Under fliken **[!UICONTROL Bild]** finns möjligheten att överföra en bild som ska visas för gruppen på gruppwebbplatsens gruppsida. Standardformatmallen ändrar bildens storlek till 170 x 90 pixlar.

![chlimage_1-239](assets/chlimage_1-239.png)

Genom att klicka på knappen **[!UICONTROL Skapa grupp]** skapas sidorna för gruppen baserat på den valda mallen, och en användargrupp skapas för medlemskap och sidan Grupper uppdateras för att visa den nya undergruppen.

Sidan Grupper med en ny undercommunity med namnet&quot;Focus Group&quot;, som en miniatyrbild överfördes för, ser ut så här (fortfarande inloggad som administratör för en community-grupp):

![chlimage_1-240](assets/chlimage_1-240.png)

Om du väljer `Focus Group` länken öppnas sidan Fokusgrupp i webbläsaren, som har ett ursprungligt utseende baserat på den valda mallen, och som innehåller en undermeny under den huvudsakliga communitywebbplatsens meny:

![chlimage_1-241](assets/chlimage_1-241.png)

## Medlemslistkomponent för community {#community-group-member-list-component}

Komponenten är avsedd att användas av utvecklare av gruppmallar. `Community Group Member List`

## Additional Information {#additional-information}

Mer information finns på sidan [Community Group Essentials](essentials-groups.md) för utvecklare.

Mer information om communitygrupper finns på [Hantera användare och användargrupper](users.md).
