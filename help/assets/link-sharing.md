---
title: Resurslänkdelning
description: Dela resurser, mappar och samlingar inom AEM Assets som en URL till externa parter.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '1137'
ht-degree: 9%

---


# Resurslänkdelning {#asset-link-sharing}

Med Adobe Experience Manager (AEM) Assets kan du dela resurser, mappar och samlingar som en URL till medlemmar i organisationen och externa enheter, inklusive partners och leverantörer. Att dela resurser via en länk är ett bekvämt sätt att göra resurser tillgängliga för externa parter utan att de först behöver logga in på AEM Assets.

>[!NOTE]
>
>Du måste ha behörigheten Redigera åtkomstkontrollista för de mappar och resurser som du vill dela som en länk.

## Dela resurser {#share-assets}

Använd dialogrutan Länkdelning för att generera URL:en för resurser som du vill dela med användare. Användare med administratörsbehörighet eller läsbehörighet på `/var/dam/share` platsen kan visa de länkar som delas med dem.

>[!NOTE]
>
>Innan du delar en länk med användarna måste du se till att den [!UICONTROL Day CQ Mail Service] är konfigurerad. Ett fel uppstår om du försöker dela en länk utan att först [konfigurera Day CQ Mail Service](link-sharing.md#configure-day-cq-mail-service).

1. I Assets-användargränssnittet väljer du den resurs som ska delas som en länk.
1. Klicka/tryck på ikonen **[!UICONTROL Share Link]** för att dela ![](assets/assets_share.png)resurser i verktygsfältet.

   En resurslänk skapas automatiskt i **[!UICONTROL Share Link]** fältet. Kopiera den här länken och dela den med användarna. Länkens standardförfallotid är en dag.

   ![Dialogruta med länkresurs](assets/chlimage_1-542.png)

   Du kan också fortsätta med steg 3-7 i den här proceduren för att lägga till e-postmottagare, konfigurera förfallotiden för länken och skicka den från dialogrutan.

   >[!NOTE]
   >
   >Om du vill dela länkar från din AEM-författare till externa enheter behöver du bara visa följande URL:er som används för länkdelning för GET-begäranden. Blockera andra URL-adresser för att säkerställa att AEM distributionen är säker.
   >
   >* &lt;AEM Server>/linkshare.html
   * &lt;AEM Server>/linksharepreview.html
   * &lt;AEM Server>/linkexpired.html


   >[!NOTE]
   Om en delad resurs flyttas till en annan plats slutar länken att fungera. Återskapa länken och dela den på nytt med användarna.

1. Öppna **[!UICONTROL Day CQ Link Externalizer]**-konfigurationen från webbkonsolen och ändra följande egenskaper i fältet **[!UICONTROL Domains]** till de värden som anges för var och en:

   * lokal
   * author
   * publicera

   För egenskaperna `local` och `author` anger du URL:en för den lokala instansen respektive författarinstansen. Både `local` och `author` egenskaper har samma värde om du kör en enda AEM författarinstans. Ange till `publish`exempel URL:en för publiceringsinstansen.

1. Skriv e-post-ID:t för den användare som du vill dela länken med i rutan för e-postadress i dialogrutan **[!UICONTROL Link Sharing]**. Du kan också dela länken med flera användare.

   Om användaren är medlem i din organisation väljer du användarens e-post-ID bland de föreslagna e-post-ID:n som visas i listan under skrivområdet. För en extern användare anger du det fullständiga e-post-ID:t och väljer det sedan i listan.

   Konfigurera SMTP-serverinformationen i [Day CQ Mail Service](link-sharing.md#configure-day-cq-mail-service)om du vill att e-postmeddelanden ska kunna skickas till användare.

   ![Dela länkar till resurser direkt från dialogrutan Länkdelning](assets/chlimage_1-543.png)

   Dela länkar till resurser direkt från dialogrutan Länkdelning

   >[!NOTE]
   Om du anger ett e-post-ID för en användare som inte är medlem i din organisation, kommer orden&quot;Extern användare&quot; att föregås av användarens e-post-ID.

1. Ange ett ämne för den resurs du vill dela i **[!UICONTROL Subject]** rutan.
1. Ange ett valfritt meddelande i **[!UICONTROL Message]** rutan.
1. I **[!UICONTROL Expiration]** fältet anger du ett förfallodatum och en förfallotid för länken med datumväljaren. Som standard är förfallodatumet inställt för en vecka från det datum du delar länken.

   ![Ange förfallodatum och förfallotid för delad länk](assets/chlimage_1-544.png)

1. Om du vill att användarna ska kunna hämta originalbilden tillsammans med återgivningarna väljer du **[!UICONTROL Allow download of original file]**.

   >[!NOTE]
   Som standard kan användare bara hämta återgivningar av resursen som du delar som en länk.

1. Klicka på **[!UICONTROL Share]**. Ett meddelande bekräftar att länken delas med användarna via ett e-postmeddelande.
1. Om du vill visa den delade resursen klickar/trycker du på länken i det e-postmeddelande som skickas till användaren. Den delade resursen visas på [!UICONTROL Adobe Marketing Cloud] sidan.

   ![Delade resurser är tillgängliga i Adobe Marketing Cloud](assets/chlimage_1-545.png)

   Om du vill växla till listvyn klickar/trycker du på layoutikonen i verktygsfältet.

1. Om du vill generera en förhandsgranskning av resursen klickar/trycker du på den delade resursen. Klicka/tryck **[!UICONTROL Back]** på verktygsfältet för att stänga förhandsgranskningen och återgå till [!UICONTROL Marketing Cloud] sidan. Om du har delat en mapp klickar/trycker du på **[!UICONTROL Parent Folder]** för att gå tillbaka till den överordnade mappen.

   ![chlimage_1-546](assets/chlimage_1-546.png)

   >[!NOTE]
   AEM har stöd för att generera en förhandsgranskning av resurser av dessa MIME-typer: JPG, PNG, GIF, BMP, INDD, PDF och PPT. Du kan bara hämta resurser från andra MIME-typer.

1. Om du vill hämta den delade resursen klickar/trycker du på **[!UICONTROL Select]** -ikonen i verktygsfältet, klickar/trycker på resursen och sedan på/trycker du **[!UICONTROL Download]** i verktygsfältet.

   ![Verktygsfältsalternativ för att hämta den delade resursen](assets/chlimage_1-547.png)

1. Om du vill visa de resurser du har delat som länkar går du till resursgränssnittet och klickar/trycker på **[!UICONTROL GlobalNav]** -ikonen. Välj **[!UICONTROL Navigation]** i listan för att visa navigeringsrutan.
1. I navigeringsrutan väljer du **[!UICONTROL Shared Links]** för att visa en lista med delade resurser.
1. Om du vill ta bort delningen av en resurs markerar du den och trycker/klickar på **[!UICONTROL Unshare]** i verktygsfältet. Ett meddelande bekräftar att du inte har delat resursen. Dessutom tas posten för resursen bort från listan.

## Konfigurera CQ-e-posttjänst för dag {#configure-day-cq-mail-service}

1. Klicka eller tryck på AEM-logotypen och navigera sedan till **[!UICONTROL Tools > Operations > Web Console]**.
1. I listan med tjänster går du till **[!UICONTROL Day CQ Mail Service]**.
1. Click the **[!UICONTROL Edit]** icon beside the service, and configure the following parameters for **[!UICONTROL Day CQ Mail Service]** with the details mentioned against their names:

   * Värdnamn för SMTP-server: värdnamn för e-postserver
   * SMTP-serverport: e-postserverport
   * SMTP-användare: e-postserverns användarnamn
   * SMTP-lösenord: e-postserverlösenord

   ![chlimage_1-548](assets/chlimage_1-548.png)

1. Klicka/tryck på **[!UICONTROL Save]**.

## Konfigurera maximal datastorlek {#configure-maximum-data-size}

När du hämtar resurser från den länk som delas med funktionen Länkdelning komprimerar AEM hela resurshierarkin från databasen och returnerar sedan resursen i en ZIP-fil. I avsaknad av begränsningar för den mängd data som kan komprimeras i en ZIP-fil utsätts stora mängder data för komprimering, vilket leder till minnesfel i JVM. För att skydda systemet från en potentiell denial of service-attack på grund av den här situationen måste du konfigurera maxstorleken med hjälp av parametern **[!UICONTROL Max Content Size (uncompressed)]** för **[!UICONTROL Day CQ DAM Adhoc Asset Share Proxy Servlet]** i Configuration Manager. Om resursens okomprimerade storlek överskrider det konfigurerade värdet, avvisas begäranden om hämtning av resurser. Standardvärdet är 100 MB.

1. Click/Tap the AEM logo and then go to **[!UICONTROL Tools > Operations > Web Console]**.
1. Leta reda på konfigurationen från webbkonsolen **[!UICONTROL Day CQ DAM Adhoc Asset Share Proxy Servlet]** .
1. Öppna **[!UICONTROL Day CQ DAM Adhoc Asset Share Proxy Servlet]** konfigurationen i redigeringsläge och ändra värdet på **[!UICONTROL Max Content Size (uncompressed)]** parametern.

   ![chlimage_1-549](assets/chlimage_1-549.png)

1. Spara ändringarna.

## Bästa praxis och felsökning {#best-practices-and-troubleshooting}

* Resursmappar eller samlingar som innehåller ett tomt utrymme i namnet kanske inte delas.
* Om användarna inte kan hämta de delade resurserna, bör du fråga AEM administratören vilka [hämtningsgränser](#configure-maximum-data-size) som finns.
* Om du inte kan skicka e-post med länkar till delade resurser eller om de andra användarna inte kan ta emot din e-post, bör du kontakta AEM om [e-posttjänsten](#configure-day-cq-mail-service) är konfigurerad eller inte.
* Om du inte kan dela resurser med hjälp av länkdelningsfunktionen måste du se till att du har rätt behörighet. Se [Dela resurser](#share-assets).
