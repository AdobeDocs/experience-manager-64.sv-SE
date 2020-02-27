---
title: Kickstart Guide
seo-title: Kickstart Guide
description: Följ den här sidan för att skapa ett demonstrationsprojekt för AEM-skärmar. Det hjälper dig att skapa en digital signeringsupplevelse från installation och konfigurera ett nytt projekt för att visa ditt innehåll i AEM Screens Player.
seo-description: Följ den här sidan för att skapa ett demonstrationsprojekt för AEM-skärmar. Det hjälper dig att skapa en digital signeringsupplevelse från installation och konfigurera ett nytt projekt för att visa ditt innehåll i AEM Screens Player.
uuid: 73fff2f2-c926-4435-8ab2-891771c843aa
contentOwner: Jyotika syal
content-type: reference
topic-tags: introduction
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
discoiquuid: 9e03f35e-284b-43d8-b095-c94800e2e9b3
translation-type: tm+mt
source-git-commit: 5f613cbae9dccbc277287e5e58c8f0648c4f3bed

---


# Kickstart Guide{#kickstart-guide}

I det här avsnittet kommer vi snabbt igång med AEM Screens och visar hur du kan utföra grundläggande åtgärder. Här får du hjälp med att skapa en grundläggande digital signeringsupplevelse med innehåll/resurser och publicera till en skärmspelare. Mer information om alla komponenter för skärmutveckling finns i resurserna i slutet av sidan.

## Skapa en upplevelse av en digital skylt på 5 minuter {#creating-a-digital-signage-experience-in-minutes}

Med följande steg kan du skapa ett exempelprojekt för skärmar och publicera innehåll för skärmspelaren.

1. Om du vill hämta **AEM Screens Player** klickar du [här](https://download.macromedia.com/screens/).

   AEM Screens finns också i **Google Play**.

   Mer information om hur du implementerar Chrome OS Player finns i [Chrome Management Console](implementing-chrome-os-player.md) .

   Mer information finns i [Installera och konfigurera skärmar](configuring-screens-introduction.md) .

   >[!NOTE]
   >
   >**OSGI-inställningar**
   >
   >Du måste aktivera den tomma referenten för att enheten ska kunna skicka data till servern. Om t.ex. den tomma refereraregenskapen är inaktiverad, kan enheten inte publicera en skärmdump. Vissa av dessa funktioner är för närvarande bara tillgängliga om Apache Sling Referrer-filtret Tillåt tomt är aktiverat i OSGI-konfigurationen. Kontrollpanelen kan visa en varning om att skyddsinställningarna kan förhindra vissa av dessa funktioner från att fungera.
   >
   >Följ stegen nedan för att aktivera filtret ***Apache Sling Referrer Tillåt tomt***:
   >
   >1. Gå till [Adobe Experience Manager Web Console Configuration](http://localhost:4502/system/console/configMgr/org.apache.sling.security.impl.ReferrerFilter).
   >1. Markera alternativet **allow.empty** .
   >1. Click **Save**.
   >    
   >Mer information om de föregående stegen finns i avsnittet ***Krav*** i [Konfigurera och distribuera AEM-skärmar](configuring-screens-introduction.md).

1. **Skapa ett nytt projekt**

   1. Markera Adobe Experience Manager-länken (överst till vänster) och sedan **Skärmar**. Du kan också gå direkt till: [http://localhost:4502/screens.html/content/screens](http://localhost:4502/screens.html/content/screens).
   1. Klicka på **Skapa** för att skapa ett nytt skärmsprojekt (se bilden nedan).
   1. Välj **Skärmar** i guiden **Skapa skärmar projekt** och klicka på **Nästa**.
   1. Ange titeln som **Test_Project** och klicka på **Create**.
   ![chlimage_1-64](assets/chlimage_1-64.png)

   När projektet har skapats visas det igen i skärmprojektskonsolen. Nu kan du välja ditt projekt. I ett projekt finns det fem typer av mappar: **Scheman**, **Platser**, **Program**, **Enheter** och **Kanaler**, vilket visas i bilden nedan.

   >[!NOTE]
   >
   >Scheman är bara tillgängliga om du har installerat AEM 6.3 Sites Feature Pack 1. Om du vill få tillgång till det här funktionspaketet måste du kontakta Adobes support och begära åtkomst. När du har behörighet kan du hämta den från paketresursen.

   ![screen_shot_2019-03-04at85952am](assets/screen_shot_2019-03-04at85952am.png)

   Mer information finns i [Skapa och hantera skärmsprojekt](creating-a-screens-project.md) .

1. **Skapa en ny kanal**

   När projektet är på plats måste du skapa en ny kanal där du hanterar innehållet.

   Följ stegen nedan för att skapa en ny kanal för ditt projekt:

   1. Navigera till **Test_Project** som du skapade och markera mappen **Kanaler** .
   1. Klicka på **Skapa** i åtgärdsfältet (se bilden nedan). En guide öppnas.
   1. Välj **sekvenskanal** och klicka på **Nästa**.
   1. Ange **Namn** och **Titel** som **TestChannel** och klicka på **Skapa**.
   ![screen_shot_2019-03-04at90236am](assets/screen_shot_2019-03-04at90236am.png)

   TestChannel ** skapas och läggs till i kanalmappen, vilket visas i bilden nedan.

   ![screen_shot_2019-03-04at90346am](assets/screen_shot_2019-03-04at90346am.png)

   Mer information om hur du skapar och hanterar kanaler finns i [Kanalhantering](managing-channels.md) .

1. **Lägga till innehåll i en kanal**

   När du väl har skapat kanalen måste du lägga till innehåll i kanalen som ska visas i AEM Screens Player.

   Följ stegen nedan för att lägga till innehåll i kanalen (*TestChannel*) i ditt projekt:

   1. Navigera till *Test_Project* som du skapade och markera mappen **Kanaler** .
   1. Klicka på **Redigera** i åtgärdsfältet (se bilden nedan). Redigeraren för *TestChannel* öppnas.
   1. Klicka på ikonen som växlar sidopanelen till vänster i åtgärdsfältet för att öppna resurserna och komponenterna.
   1. Dra och släpp de komponenter du vill lägga till i kanalen.
   ![screen_shot_2019-03-04at90507am](assets/screen_shot_2019-03-04at90507am.png)

   I det här exemplet visar redigeraren en bild som lagts till i kanalen.

   ![screen_shot_2019-03-04at90558am](assets/screen_shot_2019-03-04at90558am.png)

1. **Skapa en ny plats**

   När du väl har skapat din kanal måste du skapa en plats.

   ***Platserna*** är olika för olika digitala signeringsupplevelser och innehåller de konfigurationer som visas beroende på var de olika skärmarna finns.

   Följ stegen nedan för att skapa en ny plats för ditt projekt:

   1. Navigera till *Test_Project* som du skapade och markera mappen **Platser** .
   1. Klicka på **Skapa** bredvid plusikonen i åtgärdsfältet (se bilden nedan). En guide öppnas.
   1. Välj **Plats** i guiden och klicka på **Nästa**.
   1. Ange **namn** och **titel** för platsen (ange titeln som *TestLocation*) och klicka på **Skapa**.
   ![screen_shot_2019-03-04at91021am](assets/screen_shot_2019-03-04at91021am.png)

   TestLocation ** skapas och läggs till i mappen **Locations** .

   ![screen_shot_2019-03-04at91117am](assets/screen_shot_2019-03-04at91117am.png)

1. **Skapa en ny visning för *TestLocation ***

   När du har skapat en plats måste du skapa en ny skärm för platsen.

   ***Skärmar*** representerar den digitala upplevelse som körs på en eller flera skärmar.

   1. Navigera till den plats där du vill skapa visningen (*Test_* Project —> **Locations** —> *TestLocation)* som visas i bilden ovan och välj *TestLocation*.
   1. Klicka på** Skapa **i åtgärdsfältet.
   1. Välj **Visning** i guiden **Skapa** och klicka på **Nästa**.
   1. Ange **titel** för din visningsplats (ange titeln som *TestDisplay*).
   1. Klicka på **Skapa**.
   En ny skärm *TestDisplay* läggs till på platsen *TestLocation*, vilket visas i bilden nedan.

   ![screen_shot_2019-03-04at91341am](assets/screen_shot_2019-03-04at91341am.png)

1. **Lägga till ett schema**

   *Med scheman* i AEM-skärmar kan du ordna kanaler i återanvändbara grupper så att du inte behöver upprepa deras uppdrag separat för varje skärm som du vill visa ditt innehåll på.

   >[!NOTE]
   >
   >Den här skärmfunktionen är bara tillgänglig om du har installerat AEM 6.3 Sites Feature Pack 1 eller senare. Om du vill få tillgång till det här funktionspaketet måste du kontakta Adobes support och begära åtkomst. När du har behörighet kan du hämta den från paketresursen.

   1. Navigera till mappen **Scheman** från Test_Project —> **Scheman**.
   1. Klicka på** Skapa **i åtgärdsfältet. En guide öppnas.
   1. Välj **Schemalägg** på sidan **Skapa** guide.
   1. Ange **Titel** som *morgonschema* på egenskapssidan.
   1. Klicka på **Skapa** och schemat läggs till i mappen **Scheman** , enligt bilden nedan.
   ![screen_shot_2019-03-04at91836am](assets/screen_shot_2019-03-04at91836am.png)

   Dessutom väljer du schemat (*morgonschema*) och klickar på **Kontrollpanelen** i åtgärdsfältet för att visa kontrollpanelen för scheman. Du kan visa/ändra schemats egenskaper, tilldela kanaler och visa tilldelade visningar med kontrollpanelen.

   ![chlimage_1-65](assets/chlimage_1-65.png)

   Mer information om scheman finns i [Skapa och hantera scheman](managing-schedules.md) .

1. **Tilldela en kanal**

   1. Navigera till visningen från *Test_Project* —> **Locations** —> *TestLocation* —> *TestDisplay*.
   1. Välj *TestDisplay* och tryck/klicka på **Tilldela kanal **i åtgärdsfältet, *eller*,
   1. Klicka på **Kontrollpanelen** och välj **+Tilldela kanal** längst upp till höger på panelen **TILLDELADE KANALER &amp; SCHEMALER** , som visas i bilden nedan. **Dialogrutan Kanaltilldelning** öppnas.
   1. Välj **Referenskanal** efter **sökväg**.
   1. Markera **kanalsökvägen** (*Test_Project* —> *Kanaler* —> *TestChannel* ) i **kanalen**. Kanalrollen **** fylls automatiskt i med kanalnamnet.
   1. Välj **Prioritet** för den här kanalen som *1*.
   1. Välj **Händelser** som stöds som **Inledande inläsning** och **Inaktiv skärm**.
   1. Ange **Schedule** och välj de datum som är **aktiva från** och **aktiva till**. *(Du behöver bara fylla i dessa fält om du vill att kanalen ska visas under ett visst tidsintervall.)*
   1. Click **Save**.
   Kanalen tilldelas och läggs till på panelen.

   ![screen_shot_2019-03-04at92423am](assets/screen_shot_2019-03-04at92423am.png)

   Mer information om dialogrutan **Kanaltilldelning** och de egenskaper som är associerade med den finns i [Kanaltilldelning.](channel-assignment.md)

1. **Lägga till schema i en kanal**

   1. Navigera till visningen från *Test_Project* —> **Locations** —> *TestLocation* —> *TestDisplay*.
   1. Klicka på **Kontrollpanelen** och välj **+Tilldela schema** överst till höger från panelen **TILLDELADE KANALER &amp; SCHEMALER** , vilket visas i bilden ovan. **Dialogrutan Schemalägg** tilldelning öppnas.
   1. Välj den sökväg där du skapade schemat (här, *Test_Project* —> **Scheman** —> *Morgonschema*).
   1. Klicka på **Spara** för att lägga till schemat i kanalen.
   ![screen_shot_2019-03-04at93309am](assets/screen_shot_2019-03-04at93309am.png)

1. **Registrera en enhet**

   Du måste registrera din enhet med AEM-kontrollpanelen.

   >[!NOTE]
   >
   >Du kan öppna skärmspelaren med den AEM-skärmar-app som du hämtade eller med webbläsaren.

   Så här visar du den väntande enheten:

   1. Starta ett separat webbläsarfönster.
   1. Gå till Skärmspelaren med [webbläsaren](http://localhost:4502/content/mobileapps/cq-screens-player/firmware.html) eller starta appen AEM Screens. När du öppnar enheten visas enhetens status som ej registrerad.
   1. Navigera från AEM-kontrollpanelen till *Test_Project* —> **Devices**
   1. Klicka på **Enhetshanteraren** i åtgärdsfältet.
   1. Klicka på **Enhetsregistrering** så visas de väntande enheterna enligt bilden nedan.
   >[!NOTE]
   >
   >Om du använder AEM Screens Player som ett ChromeOS-tillägg kan du läsa frågan under ***Installera ChromeOS-spelare som Chrome Browser Plugin*** på sidan Vanliga frågor om [AEM-skärmar](aem-screens-faqs.md) .

   ![screen_shot_2019-03-04at94604am](assets/screen_shot_2019-03-04at94604am.png)

   Välj den enhet som du vill registrera och klicka på **Registrera enhet**.

   ![screen_shot_2019-03-04at94641am](assets/screen_shot_2019-03-04at94641am.png)

   Du måste validera koden genom att verifiera den från webbläsaren eller AEM Screens Player.

   Klicka på **Validera** för att gå till skärmen **Device Registration** .

   ![screen_shot_2019-03-04at94738am](assets/screen_shot_2019-03-04at94738am.png)

   Ange **Titel** och klicka på **** Register så registreras enheten.

   Klicka på **Slutför** för att slutföra enhetsregistreringssteget.

   ![screen_shot_2019-03-04at94901am](assets/screen_shot_2019-03-04at94901am.png)

   När du klickar på **Slutför** återgår du till enhetssidan som visar otilldelade och tilldelade enheter.

   ![screen_shot_2019-03-04at94943am](assets/screen_shot_2019-03-04at94943am.png)

   >[!NOTE]
   >
   >Enheten som du lade till visas som **Inte tilldelad** under **Tilldelad** status.

1. **Tilldela enheten som ska visas**

   När du har registrerat enheten måste du tilldela enheten till en skärm.

   Följ stegen nedan för att tilldela en enhet:

   1. Välj den enhet som du vill tilldela.
   1. Klicka på **Tilldela enhet** i åtgärdsfältet.
   1. Välj visningssökväg för kanalen som */content/screens/Test_Project/***Locations***/TestLocation/TestDisplay.*
   1. Klicka på **Tilldela**.
   1. Klicka på **Slutför** för att slutföra processen, och nu tilldelas enheten.
   ![screen_shot_2019-03-04at95026am](assets/screen_shot_2019-03-04at95026am.png)

   Kontrollpanelen för visning öppnas och du ser all information om tilldelade kanaler och scheman tillsammans med information om enhetskonfigurationen.

   ![screen_shot_2019-03-04at95124am](assets/screen_shot_2019-03-04at95124am.png)

### Visa innehållet i Skärmspelaren {#viewing-the-content-in-screens-player}

När du har lagt till ovanstående konfigurationer bör spelaren automatiskt visa standardkanalen för visningen på enheten, till exempel en bild (i det här fallet en sekvenskanal och innehållet visas i Skärmspelaren för webbläsare).

![screen_shot_2019-03-04at95334am](assets/screen_shot_2019-03-04at95334am.png)

Mer information om AEM Screens Player finns i [AEM Screens Player](working-with-screens-player.md).

### Additional Resources {#additional-resources}

Mer information om alla moduler för skärmar finns i resurserna nedan:

1. [Installera och konfigurera skärmar](configuring-screens-introduction.md)
1. [Skapa och hantera skärmsprojekt](creating-a-screens-project.md)
1. [Tilldela enheter](managing-devices.md)
1. [Skapa och hantera kanaler](managing-channels.md)
1. [Skapa och hantera platser](managing-locations.md)
1. [Skapa och hantera bildskärmar](managing-displays.md)
1. [Tilldela kanaler](channel-assignment.md)
1. [Hantera enheter](managing-devices.md)
1. [Skapa och hantera scheman](managing-schedules.md)
1. [AEM Screens Player](working-with-screens-player.md)
1. [Felsöka Device Control Center](monitoring-screens.md)

