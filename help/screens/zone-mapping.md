---
title: Visa layoutredigeraren
seo-title: Visa layoutredigeraren
description: 'null'
seo-description: 'null'
page-status-flag: never-activated
uuid: 6c3b35bc-ea4f-46d4-bfed-2505ae21f764
contentOwner: jsyal
discoiquuid: 679da35f-2b6b-4910-92bd-5dbd4ae3742a
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Visa layoutredigeraren{#display-layout-editor}

***Med zonmappning*** kan du skapa olika zoner och använda olika resurser som videoklipp, bilder och text som kan kombineras på en enda skärm på sammanhangsberoende sätt. Ni kan hämta in bilder, videor och texter och låta allt smälta samman och skapa en intuitiv och interaktiv digital upplevelse. Enligt projektkraven behöver du ibland flera zoner på en skärm.

Till exempel en produktsekvens med en relaterad feed för sociala medier som körs i två separata zoner på en enda skärm.

## Översikt {#overview}

När du skapar en visning för kanalen kan du välja olika mallalternativ för att visa/hantera innehåll i kanalen.

Följande mallar är tillgängliga när du skapar zoner för visning:

* 2x1
* 2x2
* 3x1
* 4x1
* 5x1

Om du använder någon av dessa mallar kan du skapa en intuitiv och interaktiv digital signeringsupplevelse där olika typer av innehåll kan användas på en enda skärm.

>[!NOTE]
>
>Mer information om hur du skapar kanaler och skärmar finns i [Hantera kanaler](managing-channels.md) och [Hantera skärmar](managing-displays.md) i Redigeringsskärmar.

## Använd fallbeskrivning {#use-case-description}

I det här exemplet kan du skapa ett AEM-skärmsprojekt med en kanal som utnyttjar innehåll och visar det på skärmen i flera zoner.

>[!NOTE]
>
>Zoner ändrar inte storlek på innehållet och det måste göras innan innehållet infogas i kanalerna.

### Steg för att skapa ett projekt {#steps-for-creating-a-project}

Följ stegen nedan för att skapa ett AEM Screens-projekt som visar hur du uppnår zonmappning för ditt AEM Screens-projekt:

1. ***Skapa ett nytt skärmsprojekt***

   1. Välj länken Adobe Experience Manager (överst till vänster) och sedan Skärmar. Du kan också gå direkt till: [http://localhost:4502/screens.html/content/screens](http://localhost:4502/screens.html/content/screens).
   1. Klicka på **Skapa** för att skapa ett nytt skärmsprojekt.
   1. Välj **Skärmar** i guiden **Skapa skärmar projekt** och klicka på **Nästa**.
   1. Ange titeln som **demomappningsprojekt** och klicka på **Skapa**.
   ![zm1](assets/zm1.gif)

1. ***Skapa en ny kanalmapp***

   1. Navigera till** Zonmappningsprojekt**.
   1. Klicka på **Skapa** i åtgärdsfältet. En guide öppnas.
   1. Välj **Channel-mappen **och klicka på **Nästa**.
   1. Ange titeln som **Dual Zone **och klicka på **Create**.
   ![zm2](assets/zm2.gif)

1. ***Skapa en ny kanal***

   1. Navigera till det **zonmappningsprojekt** du har skapat och markera mappen Kanaler (**Dual Zone**).
   1. Klicka på **Skapa** i åtgärdsfältet. En guide öppnas.
   1. Välj **Sekvenskanal **och klicka på **Nästa**.
   1. Ange **titeln** som **vänster** och klicka på **Skapa**.
   Du kan också skapa en annan sekvenskanal som **höger** i **zonmappningsprojektet**.

   ![zm3](assets/zm3.gif)

1. ***Lägga till innehåll i kanalerna***

   1. Navigera till **zonmappningsprojektet** som du skapade och markera den **kanal** som du skapade.
   1. Klicka på **Redigera** i åtgärdsfältet.
   1. Redigeraren för **vänster** öppnas. Klicka på ikonen som växlar sidopanelen till vänster i åtgärdsfältet för att öppna resurserna och komponenterna.
   1. Dra och släpp de komponenter du vill lägga till i kanalen.
   Lägg också till innehåll i den **högra** kanalen.

   ![zm4](assets/zm4.gif)

   >[!NOTE]
   >
   >Du kan fylla i innehållet i dina kanaler med olika resurser (bilder, videor) beroende på dina projektbehov.

1. ***Skapa en ny plats***

   1. Navigera till* Zonmappningsprojektet** och markera mappen **Platser** .
   1. Klicka på **Skapa** bredvid plusikonen i åtgärdsfältet. En guide öppnas.
   1. Välj **Plats** i guiden och klicka på **Nästa**.
   1. Ange **titel** för din plats (ange titeln som **San Jose**) och klicka på **Skapa**.
   ![zm5](assets/zm5.gif)

1. ***Skapa en ny visning för San Jose***

   1. Navigera till den plats där du vill skapa din visning (**demomappningsprojekt** —> **Platser** —> **San Jose**) och välj **San Jose**.
   1. Klicka på **Skapa** i åtgärdsfältet. Välj **Visning** i guiden **Skapa** och klicka på **Nästa**.
   1. Ange **titel** för bildskärmsplatsen (ange titeln som **Dual Zone**).
   1. Välj information om layouten på fliken **Visa** . Välj Upplösning som **Full HD**.
   1. Välj **Antal enheter vågrätt** som **2**. Välj **Antal enheter lodrätt** som **1**.
   1. Klicka på **Skapa**.
   ![zm6](assets/zm6.gif)

1. ***Tilldela en kanal***

   1. Navigera till skärmen från **Zonmappningsprojekt** —> **Platser** —> **San Jose** —> **Dubbelzonsvisning**.
   1. Välj **Visning av dubbla zoner **och tryck/klicka på **Tilldela kanal** i åtgärdsfältet, eller
   1. Klicka på **Kontrollpanelen** och välj **+Tilldela kanal** längst upp till höger på panelen **TILLDELADE KANALER &amp; SCHEMALER** , som visas i bilden nedan. **Dialogrutan Kanaltilldelning **öppnas.
   1. Ange **kanalrollen** som **zon**.
   1. Välj Referenskanal efter sökväg. Välj kanalmappssökvägen (**Zonmappningsprojekt **—> **Kanaler** —> **Dubbelzon** ) i kanalen.
   1. Välj **Prioritet** för den här kanalen som **1**. Välj **Händelser** som stöds som **Inledande inläsning** och **Inaktiv skärm**.
   1. Click **Save**.
   ![zm7](assets/zm7.gif)

1. ***Registrera och tilldela enheten***

   1. Starta ett separat webbläsarfönster. Gå till Skärmspelaren med webbläsaren eller starta appen AEM Screens. När du öppnar enheten visas enhetens status som ej registrerad.
   1. Navigera från AEM-kontrollpanelen till **Zonmappningsprojekt** —> **Enheter**.
   1. Klicka på** Enhetshanteraren** i åtgärdsfältet.
   1. Klicka på **Enhetsregistrering** så visas de väntande enheterna.
   1. Välj den enhet som du vill registrera och klicka på **Registrera enhet**.
   1. Du måste validera koden genom att verifiera den från webbläsaren eller AEM Screens Player. Klicka på **Validera** för att gå till skärmen **Device Registration** .
   1. Ange **Titel** som **zonenhet** och klicka på **Registrera** så registreras enheten.
   1. Klicka på **Tilldela skärm** för att gå vidare till nästa steg där du tilldelar enheten till en skärm.
   1. Klicka på **Tilldela enhet** och välj visningssökvägen för kanalen () som */content/screens/Test_Project/Locations/TestLocation/TestDisplay*. Klicka på **Tilldela**.
   1. Klicka på **Slutför** för att slutföra processen, och nu tilldelas enheten.
   ![zm8](assets/zm8.gif)

1. ***Skapa visning av flera zoner***

   1. Navigera till och markera visningen i **Zonmappningsprojekt** —> **Platser** —> **San Jose **—> **Dubbelzonsvisning **och klicka på **Kontrollpanel** i åtgärdsfältet.
   1. Välj ikonen till vänster om **Enhetskonfiguration** för spelaren på panelen **Enheter** och klicka på **egenskaper**.
   1. Navigera till fliken **Enhetskonfiguration** och fyll i fälten **Mappning** och **Mall** . Ange *{&quot;a1&quot;:&quot;${display.channel}/left&quot;, &quot;a2&quot;: &quot;${display.channel}/right&quot;}* i fältet **Mappning** och mallen som *grid-2x1*.
   1. Klicka på **Spara och stäng** och läs in spelaren igen.
   >[!NOTE]
   >
   >***Mappning och mall i enhetskonfiguration:***
   >
   >* identifierarna &quot;a1&quot; och &quot;a2&quot; motsvarar de zoner som definierats i mallen, det vill säga &quot;screens-zone-a1&quot; och &quot;screens-zone-a2&quot;.
   >* ${display.channel}/left&quot; pekar på den kanal som ska bäddas in i zonen, där display.channel pekar på den aktuella kanalsökvägen i visningen. Detta bäddar in kanalens &quot;vänster&quot;- och &quot;höger&quot;-underordnade.


   ![screen_shot_2018-01-22at114708am](assets/screen_shot_2018-01-22at114708am.png)

#### Visa innehåll i AEM Screens Player {#viewing-content-in-aem-screens-player}

Läs in din AEM Screens Player eller använd webbläsaren.

Du ser innehållet i både kanalen (vänster och höger) som visas i skärmspelaren. Innehållet visas som 2x1 visningszon.

![](do-not-localize/screen_shot_2018-01-22at120206pm.png)

### Inledning {#inference}

Zonmappning som använder en av de tillgängliga mallarna när du skapar en kanal i AEM-skärmar gör att du kan förenkla klientsidan. Du kan skapa olika zoner på skärmen och fylla zonerna ytterligare med videoklipp, bilder och andra tillgängliga resurser.
