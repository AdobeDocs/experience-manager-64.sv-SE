---
title: Kanallayoutredigeraren
seo-title: Kanallayoutredigeraren
description: 'null'
seo-description: 'null'
page-status-flag: never-activated
uuid: 81490abc-58cf-4daa-93d6-d697f7495232
contentOwner: jsyal
discoiquuid: 10beb13e-d8b2-440e-b2b0-d9fc2dafdc26
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Kanallayoutredigeraren{#channel-layout-editor}

***Med Kanallayoutredigeraren*** kan du skapa innehåll med flera zoner och använda olika resurser som videor, bilder och text som kan kombineras på en enda skärm på sammanhangsberoende sätt. Ni kan hämta in bilder, videor och texter och låta allt smälta samman och skapa en intuitiv och interaktiv digital upplevelse.

Enligt projektkraven behöver du ibland flera zoner i en kanal och kan redigera dem som en enda heltäckande enhet. Till exempel en produktsekvens med en relaterad feed för sociala medier som körs i tre separata zoner på en enda kanal.

## Översikt {#overview}

När du skapar en kanal kan du använda olika mallar för att skapa zoner i kanalen. Du kan lägga till en bild, video eller en inbäddad kanal för att utnyttja innehållet i enlighet med dina projektkrav.

### Använd fallbeskrivning {#use-case-description}

I följande exempel beskrivs hur du skapar flera zoner i en kanal.

1. ***Skapa ett skärmsprojekt***

   1. Markera Adobe Experience Manager-länken (överst till vänster) och sedan **Skärmar**. Du kan också gå direkt till: http://localhost:4502/screens.html/content/screens.
   1. Klicka på **Skapa** för att skapa ett nytt skärmsprojekt.
   1. Välj **Skärmar** i guiden **Skapa skärmar projekt** och klicka på **Nästa**.
   1. Ange titeln som **kanallayoutprojekt** och klicka på **Skapa**.
   ![ch1](assets/ch1.gif)

1. ***Skapa en kanal***

   1. Navigera till **Kanallayoutprojekt**.
   1. Klicka på **Skapa** i åtgärdsfältet. En guide öppnas.
   1. Välj **1x2-kanalen för delad skärm** och klicka på **Nästa**.
   1. Ange **titeln** som **delad vågrät** och klicka på **Skapa**.
   ![kanalskapande](assets/channelcreation.gif)

1. ***Lägga till innehåll i kanalen***

   1. Navigera till det **kanallayoutprojekt** du har skapat och markera kanalen (**Dela kanal**).
   1. Klicka på **Redigera** i åtgärdsfältet så öppnas redigeraren för den **delade kanalen** .
   1. Klicka på ikonen som växlar sidopanelen till vänster i åtgärdsfältet för att öppna resurserna och komponenterna. Dra och släpp de komponenter du vill lägga till i kanalen.
   ![ch4](assets/ch4.gif)

   >[!NOTE]
   >
   >Följande två bilder läggs till i kanalen i redigeraren.

   ![screen_shot_2018-02-08at123635pm](assets/screen_shot_2018-02-08at123635pm.png)

1. ***Skapa en plats***

   1. Navigera till mappen Platser där du vill skapa din visning (**Channel Layout Project**—> **Locations**).
   1. Klicka på **Skapa** i åtgärdsfältet.
   1. Välj **Plats** i guiden **Skapa** och klicka på **Nästa**.
   1. Ange **titel** som **San Jose**.
   1. Klicka på **Skapa**.
   ![ch5](assets/ch5.gif)

1. ***Skapa en ny visning***

   1. Navigera till den plats där du vill skapa din visning (**Acme** —> **Platser** —> **San Jose**) och välj **San Jose**.
   1. Klicka på **Skapa** i åtgärdsfältet. Välj **Visning** i guiden **Skapa** och klicka på **Nästa**.
   1. Ange **titel** för din visningsplats (ange titeln som **Delad visning)**.
   1. Välj information om layouten på fliken **Visa** . Välj **Upplösning** som **Full HD**. Välj **Antal enheter vågrätt** som 1 och **Antal enheter lodrätt** som **1**.
   1. Klicka på **Skapa**.
   ![ch6](assets/ch6.gif)

1. ***Tilldela en kanal***

   1. Navigera till visningen från **Channel Layout Project** —> **Locations** —> **San Jose** —> **Split Display**.
   1. Välj **Delad visning** och tryck/klicka på **Tilldela kanal** i åtgärdsfältet, eller
   1. Klicka på **Kontrollpanelen** och välj **+Tilldela kanal** längst upp till höger på panelen **TILLDELADE KANALER &amp; SCHEMALER** . **Dialogrutan Kanaltilldelning** öppnas.
   1. Ange **kanalrollen** som **Delad**.
   1. Välj **Referenskanal** efter sökväg. Markera kanalmappsökvägen (**Channel Layout Project** —> **Channels** —> **Split horizontal**) i kanalen.
   1. Välj **Prioritet** för den här kanalen som **1**.
   1. Välj **Händelser** som stöds som **Inledande inläsning** och **Inaktiv skärm**.
   1. Click **Save**.
   ![ch7](assets/ch7.gif)

1. ***Registrera och tilldela enheten***

   1. Starta ett separat webbläsarfönster. Gå till Skärmspelaren med webbläsaren eller starta appen AEM Screens.
   1. När du öppnar enheten visas enhetens status som ej registrerad. Navigera från AEM-kontrollpanelen till **Channel Layout Project** —> **Devices**.
   1. Klicka på **Enhetshanteraren** i åtgärdsfältet.
   1. Klicka på **Enhetsregistrering** så visas de väntande enheterna. Välj den enhet som du vill registrera och klicka på **Registrera enhet**.
   1. Du måste validera koden genom att verifiera den från webbläsaren eller AEM Screens Player. Klicka på **Validera** för att gå till skärmen **Device Registration** .
   1. Ange Title as **NewD** och klicka på **Register** så registreras enheten.
   1. Klicka på **Tilldela skärm** för att gå vidare till nästa steg där du tilldelar enheten till en skärm.
   1. Klicka på Tilldela enhet och välj visningssökvägen för kanalen () som /content/screens/Test_Project/Locations/TestLocation/TestDisplay. Klicka på **Tilldela**.
   1. Klicka på **Slutför** för att slutföra processen, och nu tilldelas enheten.
   ![ch8](assets/ch8.gif)

#### Visa innehåll i AEM Screens Player {#viewing-content-in-aem-screens-player}

Läs in din AEM Screens Player eller använd webbläsaren. Du kommer att märka innehållet i kanalen som visas i skärmspelaren. Innehållet visas som en 1x2 delad skärmkanalmall.

![](do-not-localize/screen_shot_2018-02-08at123648pm.png)

### Inledning {#inference}

Genom att använda de tillgängliga mallarna när du skapar en kanal kan du utnyttja och visa innehållet i olika zoner. Exemplet ovan visar hur du använder en 2x2-mall.

I följande bilder visas den layout som kan nås med olika mallar.
