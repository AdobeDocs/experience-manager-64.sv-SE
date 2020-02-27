---
title: Lägg till kommentar på exempelsida
seo-title: Lägg till kommentar på exempelsida
description: Lägga till anpassade kommentarer på en sida
seo-description: Lägga till anpassade kommentarer på en sida
uuid: 7dbaff4f-9986-435d-9379-7add676ea254
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 7185fb13-46a2-4fa3-aa21-a51e63cdb9be
translation-type: tm+mt
source-git-commit: 44c56ec5de6e9a832aaa52ab4a6c4978af7a9865

---


# Lägg till kommentar på exempelsida {#add-comment-to-sample-page}

Nu när komponenterna för det anpassade kommentarsystemet finns på plats i programkatalogen (/apps) är det möjligt att använda den utökade komponenten. Instansen av kommentarsystemet på en webbplats som ska påverkas måste ange att dess resourceType ska vara det anpassade kommentarsystemet och innehålla alla nödvändiga klientbibliotek.

## Identifiera nödvändiga klienter {#identify-required-clientlibs}

Klientbiblioteken som är nödvändiga för att standardkommentarerna ska fungera är också nödvändiga för utökade kommentarer.

I [Community Components Guide](components-guide.md) identifieras nödvändiga klientbibliotek. Bläddra till komponentguiden och visa komponenten Kommentarer, till exempel:

[http://localhost:4502/content/community-components/en/comments.html](http://localhost:4502/content/community-components/en/comments.html)

Observera de tre klientbiblioteken som krävs för att kommentarerna ska kunna återges och fungera korrekt. Dessa måste inkluderas där de utökade kommentarerna refereras, liksom de [utökade kommentarernas klientbibliotek](extend-create-components.md#create-a-client-library-folder) ( `apps.custom.comments`).

![chlimage_1-47](assets/chlimage_1-47.png)

## Lägga till anpassade kommentarer på en sida {#add-custom-comments-to-a-page}

Eftersom det bara kan finnas ett kommentarsystem per sida är det enklare att skapa en exempelsida enligt beskrivningen i den korta [självstudiekursen Skapa en exempelsida](create-sample-page.md) .

Öppna designläget och gör komponentgruppen Egen tillgänglig så att `Alt Comments` komponenten kan läggas till på sidan.

För att kommentaren ska visas och fungera på rätt sätt måste klientbiblioteken för kommentarer läggas till i klientlistorlistan för sidan (se [Klientlibs for Communities Components](clientlibs.md)).

### Kommentarsklipp på exempelsida {#comments-clientlibs-on-sample-page}

![Kommentarsklipp på exempelsida](assets/chlimage_1-48.png)

### Författare: Alt-kommentar på exempelsida {#author-alt-comment-on-sample-page}

![Alt-kommentar på exempelsida](assets/chlimage_1-49.png)

### Författare: Exempelnod för sidkommentarer {#author-sample-page-comments-node}

Du kan verifiera resourceType i CRXDE genom att visa egenskaperna för kommentarnoden för exempelsidan på `/content/sites/sample/en/jcr:content/content/primary/comments`.

![chlimage_1-50](assets/chlimage_1-50.png)

### Publicera exempelsida {#publish-sample-page}

När den anpassade komponenten har lagts till på sidan är det också nödvändigt att (återpublicera) [sidan](sites-console.md#publishing-the-site).

### Publicera: Alt-kommentar på exempelsida {#publish-alt-comment-on-sample-page}

När du har publicerat både det anpassade programmet och exempelsidan bör det vara möjligt att ange en kommentar. När du är inloggad, antingen med en [demoanvändare](tutorials.md#demo-users) eller administratör, bör du kunna publicera en kommentar.

Här är aaron.mcdonald@mailinator.com som publicerar en kommentar:

![chlimage_1-51](assets/chlimage_1-51.png) ![chlimage_1-52](assets/chlimage_1-52.png)

Nu när den utökade komponenten ser ut som den ska med standardutseendet är det dags att ändra utseendet.

