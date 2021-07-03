---
title: Hantera era digitala resurser med AEM Assets
description: Lär dig mer om olika resurshanterings- och redigeringsuppgifter som du kan utföra med det Touch-optimerade användargränssnittet i AEM Assets
contentOwner: AG
mini-toc-levels: 1
feature: Resurshantering, sökning, renderingar, samarbete
role: User
exl-id: aa1a702b-18dd-496b-a6e0-aa593af6e57c
source-git-commit: cdee53ea75faa2e6d1a1ec6ca7aa8bf8b8840e46
workflow-type: tm+mt
source-wordcount: '9810'
ht-degree: 2%

---

# Hantera era digitala resurser {#managing-assets-with-the-touch-optimized-ui}

Lär dig mer om olika resurshanterings- och redigeringsuppgifter som du kan utföra med det pekoptimerade användargränssnittet i AEM Assets.

I den här artikeln beskrivs hur du hanterar och redigerar resurser med det användargränssnitt som är optimerat för Adobe Experience Manager (AEM) Assets Touch. Mer information om användargränssnittet finns i [Grundläggande hantering av Touch-gränssnittet](/help/sites-authoring/basic-handling.md). Information om hur du hanterar innehållsfragment finns i [Hantera innehållsfragment](content-fragments-managing.md) resurser.

## Skapa mappar {#create-folders}

När du organiserar en samling resurser, till exempel alla `Nature`-bilder, kan du skapa mappar som håller ihop dem. Du kan använda mappar för att kategorisera och ordna dina resurser. AEM Assets kräver inte att du ordnar resurser i mappar för att fungera bättre.

>[!NOTE]
>
>* Delning av en resursmapp av typen `sling:OrderedFolder` stöds inte vid delning till Marketing Cloud. Om du vill dela en mapp ska du inte välja Ordnad när du skapar en mapp.
>* Experience Manager tillåter inte att `subassets`-ordet används som namn på en mapp. Det är ett nyckelord som är reserverat för nod som innehåller delresurser för sammansatta resurser.


1. Navigera till den plats i mappen med digitala resurser där du vill skapa en ny mapp.
1. Klicka på **[!UICONTROL Create]** på menyn. Välj **[!UICONTROL New Folder]**.
1. Ange ett mappnamn i fältet **[!UICONTROL Title]**. Som standard använder DAM den titel som du angav som mappnamn. När mappen har skapats kan du åsidosätta standardmappen och ange ett annat mappnamn.
1. Klicka på **[!UICONTROL Create]**. Mappen visas i mappen med digitala resurser.

Följande (blankstegsavgränsad lista med) tecken stöds inte:

* resursens filnamn får inte innehålla `* / : [ \ \ ] | # % { } ? &`
* resursmappnamnet får inte innehålla `* / : [ \ \ ] | # % { } ? \" . ^ ; + & \t`

## Överför resurser {#uploading-assets}

Du kan överföra olika typer av resurser (inklusive bilder, PDF-filer, RAW-filer och så vidare) från en lokal mapp eller en nätverksenhet till AEM Assets.

>[!NOTE]
>
>I Dynamic Media - Scene7-läge kan du bara överföra resurser vars filstorlek är 2 GB eller mindre.

Du kan välja att överföra resurser till mappar med eller utan en bearbetningsprofil tilldelad dem.

För mappar som har en tilldelad bearbetningsprofil visas profilnamnet på miniatyrbilden i kortvyn. I listvyn visas profilnamnet i kolumnen **[!UICONTROL Processing Profile]**. Se [Bearbeta profiler](processing-profiles.md).

Innan du överför en resurs måste du kontrollera att den har ett [format som stöds](assets-formats.md).

**Så här överför du resurser**:

1. Navigera till den plats där du vill lägga till digitala resurser i webbgränssnittet Resurser.
1. Gör något av följande om du vill överföra resurserna:

   * Tryck på ikonen **[!UICONTROL Create]** i verktygsfältet. Tryck sedan på **[!UICONTROL Files]** på menyn. Du kan byta namn på filen i den dialogruta som visas om det behövs.
   * I en webbläsare som stöder HTML5 drar du resurserna direkt i gränssnittet. Dialogrutan för att byta namn på filen visas inte.

   ![create_menu](assets/create_menu.png)

   Om du vill markera flera filer trycker du på Ctrl/Kommando och väljer resurserna i dialogrutan för filväljaren. Från en iPad kan du bara markera en fil i taget.

   Du kan pausa överföringen av stora resurser (större än 500 MB) och återuppta den senare från samma sida. Tryck på ikonen **[!UICONTROL Pause]** bredvid förloppsindikatorn som visas när överföringen startar.

   ![chlimage_1-5](assets/chlimage_1-5.png)

   Den storlek över vilken en tillgång betraktas som en stor tillgång kan konfigureras. Du kan till exempel konfigurera systemet så att resurser över 1 000 MB (i stället för 500 MB) betraktas som stora resurser. I det här fallet visas knappen **[!UICONTROL Pause]** i förloppsindikatorn när resurser som är större än 1 000 MB överförs.

   Knappen **[!UICONTROL Pause]** visas inte om en fil som är större än 1 000 MB överförs med en fil som är mindre än 1 000 MB. Om du avbryter filöverföringen på mindre än 1 000 MB visas knappen **[!UICONTROL Pause]**.

   Om du vill ändra storleksgränsen konfigurerar du egenskapen `chunkUploadMinFileSize` för noden `fileupload`i CRX-databasen.

   När du klickar på ikonen **[!UICONTROL Pause]** växlar den till en **[!UICONTROL Play]**-ikon. Klicka på ikonen **[!UICONTROL Play]** om du vill återuppta överföringen.

   ![chlimage_1-6](assets/chlimage_1-6.png)

   Om du vill avbryta en pågående överföring klickar du på `X` bredvid förloppsindikatorn. När du avbryter överföringen tar AEM Assets bort den delvis överförda delen av resursen.

   Möjligheten att återuppta överföring är särskilt användbar i scenarier med låg bandbredd och nätverksfel, där det tar lång tid att överföra stora resurser. Du kan pausa överföringen och fortsätta senare när situationen förbättras. När du återupptar startar överföringen från den punkt där du pausade den.

   Under överföringsåtgärden sparar AEM de delar av resursen som överförs som datablock i CRX-databasen. När överföringen är klar konsoliderar AEM dessa segment till ett enda datablock.

   Om du vill konfigurera rensningsaktiviteten för de oavslutade segmentöverföringsjobben går du till `https://[aem_server]:[port]/system/console/configMgr/org.apache.sling.servlets.post.impl.helper.ChunkCleanUpTask`.

   Om du överför en resurs med samma namn som en resurs som redan finns på den plats där du överför resursen visas en varningsdialogruta.

   Du kan välja att ersätta en befintlig resurs, skapa en annan version eller behålla båda genom att byta namn på den nya resursen som överförs. Om du ersätter en befintlig resurs tas metadata för resursen och eventuella tidigare ändringar och historik bort (till exempel anteckningar, beskärningar och så vidare). Om du väljer att behålla båda resurserna får den nya resursen ett nytt namn.

   ![chlimage_1-7](assets/chlimage_1-7.png)

   >[!NOTE]
   >
   >När du väljer **[!UICONTROL Replace]** i dialogrutan **[!UICONTROL Name Conflict]** genereras resurs-ID om för den nya resursen. Detta ID skiljer sig från ID:t för föregående resurs.
   >
   >Om **[!UICONTROL Asset Insights]** är aktiverat för att spåra visningar/klickningar med Adobe Analytics blir det här återskapade resurs-ID:t ogiltigt för de data som hämtats för resursen på Adobe Analytics.

   Om resursen som du överför finns i AEM Assets visas en varning i dialogrutan **[!UICONTROL Duplicates Detected]** om att du försöker överföra en dubblettresurs. Dialogrutan visas bara om kontrollsummevärdet SHA 1 för den befintliga resursens binära värde matchar kontrollsummevärdet för den resurs som du överför. I det här fallet är namnen på tillgångarna oväsentliga. Dialogrutan kan med andra ord även visas för resurser som har olika namn om SHA 1-värdena för deras binärfiler är desamma.

   >[!NOTE]
   >
   >Dialogrutan **[!UICONTROL Duplicates Detected]** visas bara när funktionen **[!UICONTROL Duplicate Detection]** är aktiverad. Mer information om hur du aktiverar funktionen **[!UICONTROL Duplicate Detection]** finns i [Aktivera dubblettidentifiering](duplicate-detection.md).

   ![chlimage_1-8](assets/chlimage_1-8.png)

   Tryck på **[!UICONTROL Keep]** om du vill behålla den duplicerade resursen i AEM Assets. Tryck på **[!UICONTROL Delete]** för att ta bort den duplicerade resursen som du överförde.

   AEM Assets förhindrar att du överför resurser med förbjudna tecken i filnamnen. Om du försöker överföra en resurs som innehåller otillåtna tecken visar AEM Assets ett varningsmeddelande om att det finns otillåtna tecken i filnamnet och stoppar överföringen tills du tar bort dessa tecken eller överför med ett tillåtet namn.

   Om du vill anpassa filnamnsreglerna för din organisation kan du i dialogrutan **[!UICONTROL Upload Assets]** ange långa namn för de filer som du överför.

   ![chlimage_1-9](assets/chlimage_1-9.png)

   Följande (blankstegsavgränsad lista med) tecken stöds emellertid inte:
   * resursens filnamn får inte innehålla `* / : [ \ \ ] | # % { } ? &`
   * resursmappnamnet får inte innehålla `* / : [ \ \ ] | # % { } ? \" . ^ ; + & \t`

   I gränssnittet Resurser visas dessutom den senaste resursen som du överför eller den mapp som du skapade först i alla vyer (**[!UICONTROL Card view]**, **[!UICONTROL List view]** och **[!UICONTROL Column view]**).

   När du överför stora resurser eller flera resurser samtidigt kan du ofta använda visuella indikatorer för att utvärdera förloppet. I dialogrutan **[!UICONTROL Upload Progress]** visas antalet överförda filer och de filer som inte kunde överföras.

   ![chlimage_1-10](assets/chlimage_1-10.png)

   Om du avbryter överföringen innan filerna har överförts, avbryter AEM Assets överföringen av den aktuella filen och uppdaterar innehållet. Filer som redan har överförts tas dock inte bort.

### Serieuppladdningar {#serial-uploads}

Vid överföring av flera resurser i grupp förbrukas betydande systemresurser, vilket kan påverka prestandan i AEM. Möjliga flaskhalsar kan vara din internetanslutning, läs- och skrivåtgärder på disk, webbläsarbegränsningar för antalet begäranden om POST vid samtidig överföring av resurser. En gruppöverföring kan misslyckas eller avslutas i förtid. Med andra ord kan AEM resurser sakna vissa filer när en grupp filer importeras eller inte alls kan importera någon fil.

För att komma till rätta med denna situation importerar AEM Assets en mediefil i taget (seriell överföring) under en gruppöverföring, i stället för att alla mediefiler hämtas samtidigt.

Seriell överföring av resurser är aktiverat som standard. Om du vill inaktivera funktionen och tillåta samtidig överföring ska du täcka över noden `fileupload` i CRXDe och ange värdet `parallelUploads` för egenskapen till `true`.

### Överför resurser med FTP {#uploading-assets-using-ftp}

Dynamic Media möjliggör batchöverföring av resurser via FTP-server. Om du tänker överföra stora resurser (>1 GB) eller överföra hela mappar och undermappar bör du använda FTP. Du kan till och med konfigurera FTP-överföring så att den sker regelbundet.

>[!NOTE]
>
>I Dynamic Media - Scene7-läge kan du bara överföra resurser vars filstorlek är 2 GB eller mindre.

>[!NOTE]
>
>Om du vill överföra resurser via FTP i Dynamic Media - Scene7 mode installerar du funktionspaket (FP) 18912 på AEM. Kontakta Adobe kundtjänst för att få tillgång till FP-18912 och slutföra konfigurationen av ditt FTP-konto. Se [Installera funktionspaket 18912 för migrering av gruppresurser](/help/assets/bulk-ingest-migrate.md).
>
>Om du använder FTP för att överföra resurser ignoreras de överföringsinställningar som anges i AEM. I stället används filbearbetningsregler, enligt definitionen i Dynamic Media Classic,.

**Så här överför du resurser med FTP**

1. Logga in på FTP-servern med det FTP-användarnamn och lösenord som du fick från e-postmeddelandet om etablering. Överför filer eller mappar till FTP-servern i FTP-klienten.
1. Öppna [Dynamic Media Classic-datorprogrammet](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/getting-started/signing-out.html#getting-started) och logga sedan in på ditt konto med hjälp av autentiseringsuppgifter från e-postmeddelandet om etablering.
1. Tryck på **[!UICONTROL Upload]** i det globala navigeringsfältet.
1. På sidan **[!UICONTROL Upload]**, nära det övre vänstra hörnet, trycker du på fliken **[!UICONTROL Via FTP]**.
1. Välj en FTP-mapp att överföra filer från till vänster på sidan. till höger på sidan väljer du en målmapp.
1. I närheten av sidans nedre högra hörn trycker du på **[!UICONTROL Job Options]** och anger sedan önskade alternativ baserat på resurserna i den mapp du valde.

   Se [Alternativ för överföring av jobb](#upload-job-options).

   >[!NOTE]
   >
   >När du överför resurser via FTP får de alternativ för överföringsjobb som du anger i Dynamic Media Classic företräde framför de parametrar för resursbearbetning som angetts i AEM.

1. Tryck på **[!UICONTROL Save]** i det nedre högra hörnet av dialogrutan **[!UICONTROL Upload Job Options]**.
1. Tryck på **[!UICONTROL Submit Upload]** i det nedre högra hörnet på sidan **[!UICONTROL Upload]**.

   Om du vill visa överföringsförloppet trycker du på **[!UICONTROL Jobs]** på det globala navigeringsfältet. Sidan **[!UICONTROL Jobs]** visar överföringsförloppet. Du kan när som helst fortsätta arbeta i AEM och gå tillbaka till jobbsidan i Dynamic Media Classic för att granska ett pågående jobb.

   Om du vill avbryta ett pågående överföringsjobb trycker du på **[!UICONTROL Cancel]** bredvid **[!UICONTROL Duration]**-tiden.

#### Alternativ för överföringsjobb {#upload-job-options}

| Överföringsalternativ | Delalternativ | Beskrivning |
|---|---|---|
| Jobbnamn |  | Standardnamnet som är förifyllt i textfältet innehåller den användardefinierade delen av namnet och datum- och tidsstämpeln. Du kan använda standardnamnet eller ange ett namn på ditt eget skapande för det här överföringsjobbet. <br>Jobbet och andra överförings- och publiceringsjobb registreras på sidan Jobs, där du kan kontrollera jobbens status. |
| Publicera efter överföring |  | Publicerar automatiskt de resurser som du överför. |
| Skriv över i valfri mapp, samma basresursnamn oavsett tillägg |  | Välj det här alternativet om du vill att de filer du överför ska ersätta befintliga filer med samma namn. Namnet på det här alternativet kan vara annorlunda, beroende på inställningarna i **[!UICONTROL Application Setup]** > **[!UICONTROL General Settings]** > **[!UICONTROL Upload to Application]** > **[!UICONTROL Overwrite Images]**. |
| Dekomprimera ZIP- eller TAR-filer vid överföring |  |  |
| Jobbalternativ |  | Tryck/klicka på **[!UICONTROL Job Options]** för att öppna dialogrutan [!UICONTROL Upload Job Options] och välj alternativ som påverkar hela överföringsjobbet. De här alternativen är desamma för alla filtyper.<br>Du kan välja standardalternativ för att överföra filer från sidan Allmänna inställningar i programmet. Om du vill öppna den här sidan väljer du **[!UICONTROL Setup]** > **[!UICONTROL Application Setup]**. Tryck på knappen **[!UICONTROL Default Upload Options]** för att öppna dialogrutan [!UICONTROL Upload Job Options]. |
|  | När | Välj En gång eller Återkommande. Om du vill ställa in ett återkommande jobb väljer du alternativet Upprepa - varje dag, Varje vecka, Varje månad eller Anpassa - för att ange när du vill att FTP-överföringsjobbet ska återkomma. Ange sedan schemaläggningsalternativen efter behov. |
|  | Inkludera undermappar | Överför alla undermappar i mappen som du vill överföra. Namnen på mappen och dess undermappar som du överför anges automatiskt i AEM Assets. |
|  | Beskärningsalternativ | Om du vill beskära manuellt från sidorna av en bild väljer du Beskär-menyn och sedan Manuell. Ange sedan antalet pixlar att beskära från en sida eller från varje sida av bilden. Hur mycket av bilden som beskärs beror på bildfilens ppi-inställning (pixlar per tum). Om bilden till exempel visar 150 ppi och du anger 75 i textrutorna Överkant, Höger, Underkant och Vänster beskärs en halv tum från varje sida.<br> Om du vill beskära pixlar med tomt utrymme automatiskt från en bild öppnar du menyn Beskär, väljer Manuell och anger pixelmått i fälten Överkant, Höger, Underkant och Vänster för att beskära från sidorna. Du kan också välja Trimma på menyn Beskär och välja följande alternativ:<br> **Trimma bort baserat på** <ul><li>**Färg**  - Välj alternativet Färg. Välj sedan menyn Hörn och välj hörnet på bilden med den färg som bäst motsvarar den tomrumsfärg som du vill beskära.</li><li>**Genomskinlighet**  - Välj alternativet Genomskinlighet.<br> **Tolerans**  - Dra i skjutreglaget för att ange en tolerans mellan 0 och 1. För beskärning baserat på färg anger du 0 om pixlarna bara ska beskäras om de exakt matchar den färg som du har markerat i hörnet av bilden. Nummer som ligger närmare 1 ger större färgskillnader.<br>Om du vill trimma baserat på genomskinlighet anger du 0 så att pixlarna bara beskärs om de är genomskinliga. Siffror närmare 1 ger större genomskinlighet.</li></ul><br>Observera att dessa beskärningsalternativ är icke-förstörande. |
|  | Alternativ för färgprofil | Välj en färgkonvertering när du skapar optimerade filer som används för leverans:<ul><li>Standardfärgbevaring: Behåller källbildens färger när bilderna innehåller färgrymdsinformation. det inte finns någon färgkonvertering. Nästan alla bilder idag har rätt färgprofil inbäddad. Om en CMYK-källbild inte innehåller någon inbäddad färgprofil konverteras färgerna till sRGB-färgrymden (standard röd grön). sRGB är den rekommenderade färgrymden för visning av bilder på webbsidor.</li><li>Behåll ursprunglig färgrymd: Bevarar de ursprungliga färgerna utan någon färgkonvertering vid punkten. För bilder utan inbäddad färgprofil görs färgkonverteringen med de standardfärgprofiler som konfigurerats i publiceringsinställningarna. Färgprofilerna kanske inte justeras mot färgen i de filer som skapas med det här alternativet. Därför bör du använda alternativet Standardfärgbevaring.</li><li>Anpassad från > Till<br> Öppnar menyer så att du kan välja färgmodellen Konvertera från och Konvertera till. Det här avancerade alternativet åsidosätter eventuell färginformation som är inbäddad i källfilen. Välj det här alternativet när alla bilder som du skickar in innehåller felaktiga eller saknade färgprofildata.</li></ul> |
|  | Bildredigeringsalternativ | Du kan bevara urklippsmaskerna i bilder och välja en färgprofil.<br> Se  [Ange bildredigeringsalternativ vid överföring](#setting-image-editing-options-at-upload). |
|  | PostScript-alternativ | Du kan rastrera PostScript®, beskära filer, behålla genomskinliga bakgrunder, välja en upplösning och välja en färgrymd.<br> Se  [Ange överföringsalternativ](#setting-postscript-and-illustrator-upload-options) för PostScript och Illustrator. |
|  | Photoshop-alternativ | Du kan skapa mallar från Adobe® Photoshop®-filer, behålla lager, ange hur lager ska namnges, extrahera text och ange hur bilder ska förankras i mallar.<br> Observera att mallar inte stöds i AEM.<br> Se  [Ange överföringsalternativ](#setting-photoshop-upload-options) för Photoshop. |
|  | PDF-alternativ | Du kan rastrera filerna, extrahera sökord och länkar, automatiskt generera en e-katalog, ange upplösningen och välja en färgrymd.<br> Observera att e-kataloger inte stöds i AEM. <br> Se  [Ange överföringsalternativ](#setting-pdf-upload-options) för PDF. |
|  | Illustrator-alternativ | Du kan rastrera Adobe Illustrator®-filer, behålla genomskinliga bakgrunder, välja en upplösning och välja en färgrymd.<br> Se  [Ange överföringsalternativ](#setting-postscript-and-illustrator-upload-options) för PostScript och Illustrator. |
|  | EVideoalternativ | Du kan omkoda en videofil genom att välja en videoförinställning.<br> Se  [Ange alternativ](#setting-evideo-upload-options) för eVideo-överföring. |
|  | Förinställningar för gruppuppsättning | Om du vill skapa en bilduppsättning, eller en snurra uppsättning, från de överförda filerna klickar du på kolumnen Aktiv för den förinställning som du vill använda. Du kan markera flera förinställningar. Du skapar förinställningarna på sidan Programinställningar/Gruppinställningar i Dynamic Media Classic.<br> Mer information om hur du skapar förinställningar för gruppuppsättningar finns i  [Konfigurera förinställningar för gruppuppsättningar för att automatiskt generera ](config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets) bilduppsättningar och snurra uppsättningar.<br> Se  [Ställa in förinställningar för gruppuppsättning vid överföring](#setting-batch-set-presets-at-upload). |

#### Ange bildredigeringsalternativ vid överföring {#setting-image-editing-options-at-upload}

När du överför bildfiler, inklusive AI-, EPS- och PSD-filer, kan du utföra följande redigeringsåtgärder i dialogrutan **[!UICONTROL Upload Job Options]**:

* Beskär tomt utrymme från bildens kant (se beskrivningen i tabellen ovan).
* Beskär manuellt från bildsidorna (se beskrivningen i tabellen ovan).
* Välj en färgprofil (se alternativbeskrivningen i tabellen ovan).
* Skapa en mask från en urklippsbana.
* Öka skärpan i bilder med oskarpa maskningsalternativ
* Blockera bakgrund

| Alternativ | Delalternativ | Beskrivning |
|---|---|---|
| Skapa mask från urklippsbana |  | Skapa en mask för bilden baserat på dess urklippsbaneinformation. Det här alternativet gäller bilder som skapats med bildredigeringsprogram där en urklippsbana har skapats. |
| Oskarp mask |  | Gör att du kan finjustera en skärpefiltereffekt i den slutliga nedsamplade bilden, styra intensiteten i effekten, radien för effekten (mätt i pixlar) och ett kontrasttröskelvärde som ignoreras.<br> Den här effekten använder samma alternativ som Photoshop Oskarp mask-filter. Till skillnad från vad namnet antyder är Oskarp mask ett skärpefilter. Under Oskarp mask anger du önskade alternativ. Inställningsalternativen beskrivs i följande: |
|  | Belopp | Styr mängden kontrast som används på kantpixlar.<br> Tänk på det som intensiteten i effekten. Den största skillnaden mellan mängden oskarp mask i Dynamic Media och mängden värden i Adobe Photoshop är att Photoshop har ett intervall på 1 till 500 %. I Dynamic Media är värdeintervallet 0,0 till 5,0. Värdet 5,0 motsvarar 500 % i Photoshop. värdet 0,9 motsvarar 90 % och så vidare. |
|  | Radie | Styr radien för effekten. Värdeintervallet är 0-250.<br> Effekten körs på alla pixlar i en bild och strålar ut från alla pixlar i alla riktningar. Radien mäts i pixlar. Om du till exempel vill få en liknande skärpeeffekt för en bild på 2 000 x 2 000 pixlar och en bild på 500 x 500 pixlar anger du en radie på två pixlar för bilden på 2 000 x 2 000 pixlar och ett radievärde på en pixel för bilden på 500 x 500 pixlar . Ett större värde används för en bild som har fler pixlar. |
|  | Tröskelvärde | Tröskelvärde är ett kontrastintervall som ignoreras när filtret Oskarp mask används. Det är viktigt så att inget &quot;brus&quot; uppstår i en bild när det här filtret används. Värdeintervallet är 0-255, vilket är antalet intensitetssteg i en gråskalebild. 0=svart, 128=50% grått och 255=vitt.<br> Ett tröskelvärde på 12 ignorerar t.ex. små variationer i hudtonens ljusstyrka för att undvika att lägga till brus, men ändå ger kantkontrast till kontrasterande områden, t.ex. där ögonfransarna möts av hud.<br> Om du t.ex. har ett foto av någons ansikte kommer Oskarp mask att påverka de kontrasterande delarna av bilden, t.ex. där ögonfransar och hud möts för att skapa ett tydligt kontrastområde, samt den utjämnade huden. Även den jämnaste huden uppvisar subtila förändringar i intensitetsvärden. Om du inte använder ett tröskelvärde framhäver filtret dessa subtila ändringar i hudpixlar. I sin tur skapas en högljudd och oönskad effekt medan kontrasten på ögonfransarna ökar, vilket ökar skärpan.<br> För att undvika det här problemet introduceras ett tröskelvärde som instruerar filtret att ignorera pixlar som inte förändrar kontrasten dramatiskt, som mjuk hud.<br> Lägg märke till texturen bredvid dragkedjan i zippargrafiken som visades tidigare. Bildbrus visas eftersom tröskelvärdena var för låga för att undertrycka bruset. |
|  | Monokrom | Markera för att få bildintensiteten oskarp mask (intensitet).<br> Avmarkera alternativet om du vill skapa en oskarp mask för varje färgkomponent separat. |
| Blockera bakgrund |  | Tar automatiskt bort bakgrunden i en bild när du överför den. Den här tekniken är användbar för att dra uppmärksamheten till ett visst objekt och få det att sticka ut från en rörig bakgrund. Välj om du vill aktivera eller aktivera funktionen Blockera bakgrund och följande underalternativ: |
|  | Hörn | Krävs.<br> Hörnet på bilden som används för att definiera bakgrundsfärgen som ska blockeras.<br> Du kan välja mellan  **Övre vänster**,  **Nedre vänster**,  **Övre höger** eller  **Nedre höger**. |
|  | Fyllningsmetod | Krävs.<br> Styr pixelgenomskinlighet från den hörnplats som du anger.<br> Du kan välja bland följande fyllningsmetoder: <ul><li>**Flood Fill**  - gör alla pixlar genomskinliga som matchar det hörn du har angett och som är anslutet till det.</li><li>**Matcha pixlar** - gör alla matchande pixlar genomskinliga, oavsett var de finns i bilden.</li></ul> |
|  | Tolerans | Valfritt.<br> Styr den tillåtna variationen i pixelfärgmatchning baserat på den hörnplats som du anger.<br> Använd värdet 0,0 om du vill matcha pixelfärgerna exakt, eller använd värdet 1,0 om du vill tillåta den största variationen. |

#### Ange överföringsalternativ för PostScript och Illustrator {#setting-postscript-and-illustrator-upload-options}

När du överför bildfiler från PostScript (EPS) eller Illustrator (AI) kan du formatera dem på olika sätt. Du kan rastrera filerna, behålla den genomskinliga bakgrunden, välja en upplösning och välja en färgrymd. Alternativ för formatering av PostScript- och Illustrator-filer finns i dialogrutan Alternativ för överföringsjobb under PostScript-alternativ och Illustrator-alternativ.

| Alternativ | Delalternativ | Beskrivning |
|---|---|---|
| Bearbetar |  | Välj **[!UICONTROL Rasterize]** om du vill konvertera vektorgrafik i filen till bitmappsformat. |
| Bevara genomskinlig bakgrund i återgiven bild |  | Bevara filens genomskinlighet i bakgrunden. |
| Upplösning |  | Anger upplösningsinställningen. Den här inställningen avgör hur många pixlar som visas per tum i filen. |
| Färgrymd |  | Välj menyn Färgrymd och välj bland följande alternativ för färgrymd: |
|  | Identifiera automatiskt | Bevarar filens färgrymd. |
|  | Tvinga som RGB | Konverterar till RGB-färgmodellen. |
|  | Tvinga som CMYK | Konverterar till CMYK-färgmodellen. |
|  | Tvinga som gråskala | Konverterar till gråskalefärgrymden. |

#### Ange överföringsalternativ för Photoshop {#setting-photoshop-upload-options}

PSD-filer (Photoshop Document) används oftast för att skapa bildmallar. När du överför en PSD-fil kan du skapa en bildmall automatiskt från filen (välj alternativet Skapa mall på skärmen Överför).

Dynamic Media skapar flera bilder från en PSD-fil med lager om du använder filen för att skapa en mall. skapas en bild för varje lager.

Använd **[!UICONTROL Crop Options]** och **[!UICONTROL Color Profile Options]**, som beskrivs ovan, med överföringsalternativ för Photoshop.

>[!NOTE]
>
>Mallar stöds inte i AEM.

| Alternativ | Delalternativ | Beskrivning |
|---|---|---|
| Behåll lager |  | Rippar lagren i PSD-filen, om det finns några, till enskilda resurser. Resurslagren förblir kopplade till PSD-filen. Du kan visa dem genom att öppna PSD-filen i detaljvyn och välja lagerpanelen. |
| Skapa mall |  | Skapar en mall från lagren i PSD-filen. |
| Extrahera text |  | Extraherar texten så att användare kan söka efter text i ett visningsprogram. |
| Utöka lager till bakgrundsstorlek |  | Utökar storleken på överlappade bildlager till storleken på bakgrundslagret. |
| Namnge lager |  | Lager i PSD-filen överförs som separata bilder. |
|  | Lagernamn | Namnger bilderna efter deras lagernamn i PSD-filen. Ett lager med namnet Price Tag i den ursprungliga PSD-filen blir till exempel en bild med namnet Price Tag. Om lagernamnen i PSD-filen däremot är Photoshop standardlagernamn (Bakgrund, Lager 1, Lager 2 och så vidare) får bilderna namn efter sina lagernummer i PSD-filen, inte efter deras standardlagernamn. |
|  | Photoshop och lagernummer | Namnger bilderna efter deras lagernummer i PSD-filen och ignorerar de ursprungliga lagernamnen. Bilderna får samma namn som Photoshop-filnamnet och ett nummer i det tillagda lagret. Det andra lagret i en fil som heter Spring Ad.psd får till exempel namnet Spring Ad_2 även om det har ett icke-standardnamn i Photoshop. |
|  | Photoshop- och lagernamn | Namnger bilderna efter PSD-filen följt av lagernamnet eller lagernumret. Lagernumret används om lagernamnen i PSD-filen är Photoshop standardlagernamn. Ett lager med namnet Price Tag i en PSD-fil med namnet SpringAd får till exempel namnet Spring Ad_Price Tag. Ett lager med standardnamnet Lager2 kallas Spring Ad_2. |
| Fästpunkt |  | Ange hur bilder ska förankras i mallar som genereras från lagerkompositionen som skapas från PSD-filen. Som standard är ankarpunkten i mitten. Med en central ankarpunkt kan ersättningsbilder bäst fylla samma område, oavsett ersättningsbildens proportioner. Bilder med en annan aspekt som ersätter den här bilden upptar i själva verket samma utrymme när de refererar till mallen och använder parameterersättning. Ändra till en annan inställning om ditt program kräver att ersättningsbilderna fyller ut det tilldelade utrymmet i mallen. |

#### Ange överföringsalternativ för PDF {#setting-pdf-upload-options}

När du överför en PDF-fil kan du formatera den på olika sätt. Du beskär sidorna, extraherar sökord, anger en pixel per tum-upplösning och väljer en färgrymd. PDF-filer innehåller ofta en ytmarginal, skärmärken, passmärken och andra skrivarmärken. Du kan beskära dessa märken från sidorna när du överför en PDF-fil.

>[!NOTE]
>
>eCatalogs stöds inte i AEM.

Välj bland följande alternativ:

| Alternativ | Delalternativ | Beskrivning |
|---|---|---|
| Bearbetar | Rastrera | (Standard) Rippar ned sidorna i PDF-filen och konverterar vektorgrafik till bitmappsbilder. Välj det här alternativet om du vill skapa en e-katalog. |
| Extract | Sök efter ord | Extraherar ord från PDF-filen så att filen kan genomsökas efter nyckelord i en eCatalog Viewer. |
|  | Länkar | Extraherar länkar från PDF-filerna och konverterar dem till bildscheman som används i en eCatalog Viewer. |
| Generera eCatalog automatiskt från PDF med flera sidor |  | Skapar automatiskt en e-katalog från PDF-filen. eCatalog namnges efter den PDF-fil du överförde. (Det här alternativet är bara tillgängligt om du rastrerar PDF-filen när du överför den.) |
| Upplösning |  | Anger upplösningsinställningen. Den här inställningen avgör hur många pixlar som visas per tum i PDF-filen. Standardvärdet är 150. |
| Färgrymd |  | Välj menyn Färgrymd och välj en färgrymd för PDF-filen. De flesta PDF-filer har både RGB- och CMYK-färgbilder. RGB-färgmodellen är att föredra när du vill visa bilden online. |
|  | Identifiera automatiskt | Behåller PDF-filens färgrymd. |
|  | Tvinga som RGB | Konverterar till RGB-färgmodellen. |
|  | Tvinga som CMYK | Konverterar till CMYK-färgmodellen. |
|  | Tvinga som gråskala | Konverterar till gråskalefärgrymden. |

#### Ange överföringsalternativ för eVideo {#setting-evideo-upload-options}

Du kan omkoda en videofil genom att välja bland en mängd olika förinställningar för video.

| Alternativ | Delalternativ | Beskrivning |
|---|---|---|
| Adaptiv video |  | En enda förinställning för kodning som fungerar med alla proportioner för att skapa videor som ska skickas till mobilen, surfplattan och datorn. Överförda källvideor som är kodade med den här förinställningen har en fast höjd. Bredden skalas dock automatiskt så att videons proportioner bevaras. <br>Det bästa sättet är att använda adaptiv videokodning. |
| Förinställningar för enskild kodning | Sortera kodningsförinställningar | Välj Namn eller Storlek om du vill sortera kodningsförinställningarna under Skrivbord, Mobil och Surfplatta efter namn eller upplösningsstorlek. |
|  | Skrivbord | Skapa en MP4-fil för att leverera en direktuppspelad eller progressiv videoupplevelse till stationära datorer. Välj en eller flera proportioner med önskad upplösningsstorlek och måldatahastighet. |
|  | Mobil | Skapa en MP4-fil för leverans på iPhone- eller Android-mobilenheter. Välj en eller flera proportioner med önskad upplösning och datahastighet. |
|  | Tablet | Skapa en MP4-fil för leverans på iPad- eller Android-surfplattor. Välj en eller flera proportioner med önskad upplösning och datahastighet. |

#### Ange förinställningar för gruppuppsättning vid överföring {#setting-batch-set-presets-at-upload}

Om du automatiskt vill skapa en bilduppsättning eller en snurra uppsättning från överförda bilder klickar du på kolumnen **[!UICONTROL Active]** för den förinställning du vill använda. Du kan markera flera förinställningar.

Mer information om hur du skapar gruppuppsättningsförinställningar finns i [Konfigurera gruppuppsättningsförinställningar för att automatiskt generera bilduppsättningar och snurpuppsättningar](config-dms7.md#creating-batch-set-presets-to-auto-generate-image-sets-and-spin-sets).

### Strömmade överföringar {#streamed-uploads}

Om du överför flera resurser ökar I/O-anropen till AEM drastiskt, vilket minskar överföringseffektiviteten och till och med kan göra att den tar slut. AEM Assets har stöd för direktuppspelad överföring av resurser. Direktuppspelad överföring minskar I/O-disken under överföringen genom att undvika att lagra resurser i en tillfällig mapp på servern innan den kopieras till databasen. I stället överförs data direkt till databasen. På så sätt minskas tiden det tar att överföra stora resurser och möjligheten till timeout. Direktuppspelning är aktiverat som standard i AEM Assets.

Direktuppspelningsöverföring är inaktiverat för AEM som körs på JEE-server med en servlet-api-version som är lägre än 3.1.

### Extrahera ZIP-arkiv som innehåller resurser {#extract-zip-archive-containing-assets}

Du kan överföra ZIP-arkiv precis som andra resurser som stöds. Samma filnamnsregler gäller för ZIP-filer. AEM kan du extrahera ett ZIP-arkiv till en DAM-plats.

Välj ett ZIP-arkiv i taget, klicka på **[!UICONTROL Extract Archive]** och välj en målmapp. Välj ett alternativ för att hantera eventuella konflikter. Om resurserna i ZIP-filen redan finns i målmappen kan du välja något av följande alternativ: hoppa över extrahering, ersätta befintliga filer, behålla båda resurserna genom att byta namn eller skapa en ny version.

När extraheringen är klar meddelar AEM dig i meddelandefältet. Medan AEM extraherar ZIP-filen kan du gå tillbaka till arbetet utan att avbryta extraheringen.

![Meddelande om ZIP-extrahering](assets/zip_extract_notification.png)

Vissa begränsningar för funktionen är:

* Om det finns en mapp med samma namn på målet extraheras resurserna från ZIP-filen i den befintliga mappen.

* Om du avbryter extraheringen tas de redan extraherade resurserna inte bort.

* Du kan inte markera två ZIP-filer samtidigt och extrahera dem. Du kan bara extrahera ett ZIP-arkiv åt gången.

## Förhandsgranska resurser {#previewing-assets}

**Så här förhandsgranskar du resurser**:

1. I resursgränssnittet navigerar du till platsen för resursen som du vill förhandsgranska.
1. Tryck på önskad resurs för att öppna den.

1. I förhandsgranskningsläget är zoomalternativ tillgängliga för [bildtyper som stöds](assets-formats.md#supported-raster-image-formats) (med interaktiv redigering).

   Om du vill zooma in på en resurs trycker du på **[!UICONTROL +]** (eller trycker på förstoringsglaset på resursen). Om du vill zooma ut trycker du på **[!UICONTROL -]**. När du zoomar in kan du titta närmare på alla delar av bilden genom att panorera. Med **[!UICONTROL Reset Zoom]**-pilen återgår du till den ursprungliga vyn.

   ![uploadicon](assets/uploadicon.png)

   Tryck på knappen **[!UICONTROL Reset]** för att återställa vyn till den ursprungliga storleken.

   ![chlimage_1-11](assets/chlimage_1-11.png)

>[!MORELIKETHIS]
>
>* [Förhandsgranska Dynamic Media Assets](/help/assets/previewing-assets.md).
>* [Visa delresurser](managing-linked-subassets.md#viewing-subassets).


## Redigera egenskaper {#editing-properties}

1. Navigera till platsen för resursen vars metadata du vill redigera.

1. Markera resursen och tryck på **[!UICONTROL Properties]** i verktygsfältet för att visa resursegenskaper. Du kan också välja snabbåtgärden **[!UICONTROL Properties]** på resurskortet.

   ![properties_quickaction](assets/properties_quickaction.png)

1. Redigera metadataegenskaperna under olika flikar på sidan **[!UICONTROL Properties]**. Du kan till exempel redigera titeln, beskrivningen och så vidare på fliken **[!UICONTROL Basic]**.

   Layouten för **[!UICONTROL Properties]**-sidan och de metadataegenskaper som är tillgängliga beror på det underliggande metadataschemat. Mer information om hur du ändrar layouten för **[!UICONTROL Properties]**-sidan finns i [Metadata Schemas](metadata-schemas.md).

1. Om du vill schemalägga ett visst datum/tid för att aktivera resursen använder du datumväljaren bredvid fältet **[!UICONTROL On Time]**.

   ![Ställ in På-tid för tillgångar för att göra tillgångar tillgängliga för en fast tidsperiod mellan på- och fråntid](assets/chlimage_1-12.png)

1. Om du vill inaktivera resursen efter en viss tid väljer du datum och tid för inaktiveringen i datumväljaren bredvid fältet **[!UICONTROL Off Time]**.

   Inaktiveringsdatumet ska vara senare än aktiveringsdatumet för en tillgång. Efter [!UICONTROL Off Time] är en resurs och dess återgivningar inte tillgängliga via webbgränssnittet Resurser eller via HTTP API:t.

   ![Inställningstid för när tillgångar ska sluta vara tillgängliga efter en viss tidsperiod](assets/chlimage_1-13.png)

1. Markera en eller flera taggar i fältet **[!UICONTROL Tags]**. Om du vill lägga till en egen tagg skriver du namnet på taggen i rutan och trycker på **[!UICONTROL Enter]**. Den nya taggen sparas i AEM.

   YouTube kräver att taggar publiceras och har en länk till YouTube (om en lämplig länk finns).
Om du vill skapa taggar måste du ha skrivbehörighet för `/content/cq:tags/default` i CRX-databasen.

1. Om du vill ge resursen en gradering trycker du på fliken **[!UICONTROL Advanced]** och sedan på stjärnan vid rätt position för att tilldela den önskade graderingen.

   ![omdömen](assets/ratings.png)

   Värderingspoängen som du tilldelar resursen visas under **[!UICONTROL Your Ratings]**. Det genomsnittliga omdöme som resursen fick från användare som värderade resursen visas under **[!UICONTROL Rating]**. Dessutom visas uppdelningen av de omdömen som bidrar till det genomsnittliga omdömet under **[!UICONTROL Rating Breakdown]**. Du kan söka efter resurser baserat på genomsnittliga poäng.

1. Om du vill visa användningsstatistik för resursen trycker du på fliken **[!UICONTROL Insights]**.

   Användningsstatistik omfattar följande:

   * Antal gånger som resursen visats eller hämtats.
   * Kanaler/enheter som resursen användes genom.
   * Kreativa lösningar där resursen nyligen användes.

   Mer information finns i [Resursinsikter](touch-ui-asset-insights.md).

1. Tryck på **[!UICONTROL Save & Close]**.
1. Navigera till resursgränssnittet. De redigerade metadataegenskaperna, inklusive titel, beskrivning, omdömen och så vidare, visas på tillgångskortet i kortvyn och under relevanta kolumner i listvyn.

## Kopiera resurser {#copying-assets}

När du kopierar en resurs eller en mapp kopieras hela resursen eller mappen tillsammans med dess innehållsstruktur. En kopierad resurs eller en mapp dupliceras på målplatsen. Resursen på källplatsen ändras inte.

Några attribut som är unika för en viss kopia av en tillgång överförs inte. Några exempel är:

* Tillgångs-ID, datum och tid när de skapades samt versioner och versionshistorik. Vissa av dessa egenskaper indikeras av egenskaperna `jcr:uuid`, `jcr:created` och `cq:name`.

* Skapandetid och refererade sökvägar är unika för varje resurs och för varje återgivning.

Övriga egenskaper och metadatainformation behålls. Ingen del av kopian skapas när en resurs kopieras.

1. Välj en eller flera resurser i resursgränssnittet och tryck sedan på ikonen **[!UICONTROL Copy]** i verktygsfältet. Du kan också välja snabbåtgärden **[!UICONTROL Copy]** från resurskortet.

   ![copy_icon](assets/copy_icon.png)

   >[!NOTE]
   >
   >Om du använder snabbåtgärden **[!UICONTROL Copy]** kan du bara kopiera en resurs åt gången.

1. Navigera till den plats där du vill kopiera resurserna.

   >[!NOTE]
   >
   >Om du kopierar en resurs på samma plats, genererar AEM automatiskt en variant av namnet. Om du till exempel kopierar en resurs med namnet Fyrkant, genererar AEM automatiskt titeln för kopian som Fyrkant1.

1. Tryck på resursikonen **[!UICONTROL Paste]** från verktygsfältet:

   ![chlimage_1-14](assets/chlimage_1-14.png)

   Resurserna kopieras till den här platsen.

   >[!NOTE]
   >
   >Ikonen **[!UICONTROL Paste]** är tillgänglig i verktygsfältet tills inklistringen är klar.

## Flytta och byta namn på resurser {#moving-or-renaming-assets}

När du flyttar resurser (eller mappar) till en annan plats dupliceras inte resurserna (eller mapparna) till skillnad från när du kopierar resursen. Resurserna (eller mapparna) placeras på målplatsen och tas bort från källplatsen. Du kan också byta namn på resursen när du flyttar den till den nya platsen. Om du flyttar en publicerad resurs till en annan plats kan du välja att publicera om resursen. Som standard avpubliceras en flyttningsåtgärd för en publicerad resurs automatiskt. Flyttad resurs publiceras om om författaren väljer alternativet [!UICONTROL Republish] när resursen flyttas.

![Du kan publicera om en redan publicerad resurs när du flyttar den](assets/republish-on-move.png)

Så här flyttar du resurser eller mappar:

1. Navigera till platsen för resursen som du vill flytta.

![Du kan publicera om en redan publicerad resurs när du flyttar den](assets/republish-on-move.png)

Så här flyttar du resurser eller mappar:

1. Navigera till platsen för resursen som du vill flytta.

1. Markera resursen och klicka på **[!UICONTROL Move]**-alternativet i verktygsfältet.
   ![Alternativet Flytta i verktygsfältet Resurser](assets/do-not-localize/move_icon.png)

1. Gör något av följande i [!UICONTROL Move Assets]-guiden:

   * Ange namnet på resursen när den har flyttats. Klicka sedan på **[!UICONTROL Next]** för att fortsätta.

   * Klicka på **[!UICONTROL Cancel]** för att stoppa processen.
   >[!NOTE]
   >
   >* Du kan ange samma namn för resursen om det inte finns någon resurs med det namnet på den nya platsen. Du bör emellertid använda ett annat namn om du flyttar resursen till en plats där det finns en resurs med samma namn. Om du använder samma namn genereras automatiskt en variant av namnet. Om resursen till exempel har namnet Fyrkant, genereras namnet Fyrkant1 för kopian.
   >* När namnet ändras tillåts inte tomt utrymme i filnamnet.


1. Gör något av följande i dialogrutan **[!UICONTROL Select Destination]**:

   * Navigera till den nya platsen för resurserna och klicka sedan på **[!UICONTROL Next]** för att fortsätta.

   * Klicka på **[!UICONTROL Back]** för att återgå till skärmen **[!UICONTROL Rename]**.

1. Om de resurser som flyttas har några referenssidor, resurser eller samlingar visas fliken **[!UICONTROL Adjust References]** bredvid fliken **[!UICONTROL Select Destination]**.

   Gör något av följande på skärmen **[!UICONTROL Adjust References]**:

   * Ange vilka referenser som ska justeras baserat på den nya informationen och klicka sedan på **[!UICONTROL Move]** för att fortsätta.

   * Välj/avmarkera referenser till resurserna i kolumnen **[!UICONTROL Adjust]**.
   * Klicka på **[!UICONTROL Back]** för att återgå till skärmen **[!UICONTROL Select Destination]**.

   * Klicka på **[!UICONTROL Cancel]** om du vill avbryta flyttningen.

   Om du inte uppdaterar referenser fortsätter de att peka på resursens tidigare sökväg. Om du justerar referenserna uppdateras de till den nya resurssökvägen.

### Flytta resurser med dra-åtgärden {#move-using-drag}

Du kan flytta resurser (eller mappar) till en mapp på samma nivå genom att dra dem till målplatsen, i stället för att använda alternativet [!UICONTROL Move] i användargränssnittet. Den här åtgärden är dock bara möjlig i listvyn.

När du flyttar resurser genom att dra dem öppnas inte guiden [!UICONTROL Move Asset]. Därför kan du inte ändra namn på resurserna när du flyttar dem. Dessutom publiceras redan publicerade resurser på nytt när de flyttas genom att användaren drar dem, utan att användaren behöver godkänna publiceringen på nytt.

![Flytta resurser till jämställda mappar genom att dra resurser](assets/move-by-drag.gif)

## Hantera återgivningar {#managing-renditions}

1. Du kan lägga till eller ta bort återgivningar för en resurs, förutom originalet. Navigera till platsen för resursen som du vill lägga till eller ta bort återgivningar för.

1. Tryck på resursen för att öppna sidan för resursen.

   ![chlimage_1-15](assets/chlimage_1-15.png)

1. Tryck på ikonen **[!UICONTROL Global Navigation]** och välj **[!UICONTROL Renditions]** i listan.

   ![renditions_menu](assets/renditions_menu.png)

1. I panelen **[!UICONTROL Renditions]** visar du listan över återgivningar som genererats för resursen.

   ![renditions_panel](assets/renditions_panel.png)

   >[!NOTE]
   >
   >Som standard visas inte den ursprungliga återgivningen av resursen i förhandsgranskningsläget i AEM Assets. Om du är administratör kan du använda övertäckningar för att konfigurera AEM Assets så att ursprungliga återgivningar visas i förhandsgranskningsläget.

1. Välj en återgivning om du vill visa eller ta bort återgivningen.

   **Ta bort en återgivning**

   Välj en återgivning på panelen **[!UICONTROL Renditions]** och tryck sedan på ikonen **[!UICONTROL Delete Rendition]** i [verktygsfältet](/help/sites-authoring/basic-handling.md). Det går inte att ta bort återgivningar gruppvis när resursbearbetningen är slutförd. För enskilda resurser kan du ta bort återgivningar manuellt från användargränssnittet. För flera resurser kan du anpassa Experience Manager för att ta bort antingen specifika återgivningar eller ta bort resurserna och överföra de borttagna resurserna igen.

   ![delete_renderingicon](assets/delete_renditionicon.png)

   **Överför en ny återgivning**

   Navigera till sidan med resursinformation för resursen och tryck på ikonen **[!UICONTROL Add Rendition]** i verktygsfältet för att överföra en ny återgivning för resursen.

   ![chlimage_1-16](assets/chlimage_1-16.png)

   >[!NOTE]
   >
   >Om du väljer en återgivning på panelen **[!UICONTROL Renditions]** ändras sammanhanget för verktygsfältet och endast de åtgärder som är relevanta visas. Alternativ som ikonen **[!UICONTROL Upload Rendition]** visas inte. Om du vill visa de här alternativen i verktygsfältet går du till informationssidan för resursen.

   Du kan konfigurera dimensionerna för den återgivning som du vill ska visas på informationssidan för en bild- eller videoresurs. Beroende på de dimensioner du anger visas återgivningen med de exakta eller närmaste måtten i AEM Assets.

   Om du vill konfigurera återgivningsdimensionerna för en bild på resursdetaljnivån ska du täcka över noden **[!UICONTROL renditionpicker]** `libs/dam/gui/content/assets/assetpage/jcr:content/body/content/content/items/assetdetail/items/col1/items/assetview/renditionpicker` och konfigurera värdet för egenskapen width. Konfigurera egenskapen **[!UICONTROL size (Long) in KB]** i stället för bredden för att anpassa återgivningen på resursdetaljsidan utifrån bildstorleken. För storleksbaserad anpassning prioriterar egenskapen **[!UICONTROL preferOriginal]** originalet om storleken på den matchade återgivningen är större än originalet.

   På samma sätt kan du anpassa sidbilden **[!UICONTROL Annotation]** genom att åsidosätta `libs/dam/gui/content/assets/annotate/jcr:content/body/content/content/items/content/renditionpicker`.

   ![chlimage_1-17](assets/chlimage_1-17.png)

   Om du vill konfigurera återgivningsdimensioner för en videoresurs navigerar du till noden **[!UICONTROL videopicker]** i CRX-databasen på platsen `/libs/dam/gui/content/assets/assetpage/jcr:content/body/content/content/items/assetdetail/items/col1/items/assetview/videopicker`, täcker över noden och redigerar sedan lämplig egenskap.

   >[!NOTE]
   >
   >Videoanteckningar stöds bara i webbläsare med HTML5-kompatibla videoformat. Beroende på webbläsaren stöds dessutom olika videoformat.

Mer information om delresurser finns i [hantera delresurser](managing-linked-subassets.md).

## Ta bort resurser {#deleting-assets}

Om du vill lösa eller ta bort inkommande referenser från andra sidor uppdaterar du de relevanta referenserna innan du tar bort en resurs.

Du kan även inaktivera Tvinga borttagningsknappen med hjälp av en övertäckning, så att användare inte kan ta bort refererade resurser och lämna brutna länkar.

Du måste ha behörighet att ta bort en resurs för att den ska kunna tas bort. Om du bara har ändringsbehörighet kan du bara redigera metadata för resursen och lägga till anteckningar till resursen. Du kan dock inte ta bort resursen eller dess metadata.

**Så här tar du bort resurser**:

1. Navigera till platsen för de resurser som du vill ta bort.

1. Markera resursen och tryck på ikonen **[!UICONTROL Delete]** i verktygsfältet.

   ![delete_icon](assets/delete_icon.png)

1. Tryck på följande i bekräftelsedialogrutan:

   * **[!UICONTROL Cancel]** för att stoppa åtgärden
   * **[!UICONTROL Delete]** för att bekräfta åtgärden baserat på följande:

      * Om resursen inte har några referenser tas resursen bort.
      * Om resursen har referenser visas ett felmeddelande om att **[!UICONTROL One or more assets are referenced]**. Du kan välja **[!UICONTROL Force Delete]** eller **[!UICONTROL Cancel]**.

   >[!NOTE]
   >
   >Om du vill lösa eller ta bort inkommande referenser från andra sidor uppdaterar du de relevanta referenserna innan du tar bort en resurs.
   >
   >Inaktivera även knappen **[!UICONTROL Force Delete]** med en övertäckning så att användare inte kan ta bort refererade resurser och lämna brutna länkar.

## Hämta resurser {#downloading-assets}

Se [Hämta resurser från AEM](download-assets-from-aem.md)

## Publicera och avpublicera resurser {#publish-assets}

När du har överfört, bearbetat eller redigerat dina resurser på [!DNL Experience Manager]-författaren publicerar du resursen till publiceringsservern. Publicering gör materialet tillgängligt för allmänheten. Funktionen för avpublicering tog bort resursen från publiceringsservern men inte från redigeringsservern.

Mer information om [!DNL Dynamic Media] finns i [publicera [!DNL Dynamic Media] resurser](publishing-dynamicmedia-assets.md).

1. Navigera till platsen för resursen eller resursmappen som du vill publicera eller som du vill ta bort från publiceringsmiljön (avpublicera).

1. Markera resursen eller mappen som ska avpubliceras och klicka på **[!UICONTROL Manage Publication]** ![alternativet Hantera publikation](assets/do-not-localize/globe-publication.png) i verktygsfältet. Du kan även publicera snabbt genom att välja alternativet **[!UICONTROL Quick Publish]** i verktygsfältet. Om mappen som du vill publicera innehåller en tom mapp publiceras inte den tomma mappen.

1. Välj **[!UICONTROL Publish]** eller **[!UICONTROL Unpublish]** efter behov.

   ![Avpubliceringsåtgärd](assets/unpublish_action.png)
   *Bild: Alternativ för publicering och avpublicering samt schemaläggning.*

1. Välj **[!UICONTROL Now]** om du vill agera på resursen direkt eller välj **[!UICONTROL Later]** om du vill schemalägga åtgärden. Välj ett datum och en tid om du väljer alternativet **[!UICONTROL Later]**. Klicka på **[!UICONTROL Next]**.

1. Om en resurs refererar till andra resurser vid publicering visas dess referenser i guiden. Endast de referenser som inte har publicerats eller ändrats sedan den senaste publiceringen visas. Välj de referenser som du vill publicera.

1. Om en resurs refererar till andra resurser vid avpublicering väljer du de referenser som du vill avpublicera. Klicka på **[!UICONTROL Unpublish]**. Klicka på **[!UICONTROL Cancel]** i bekräftelsedialogrutan för att stoppa åtgärden eller klicka på **[!UICONTROL Unpublish]** för att bekräfta att resurserna ska avpubliceras vid det angivna datumet.

Förstå följande begränsningar och tips för publicering eller avpublicering av resurser och mappar:

* Alternativet [!UICONTROL Manage Publication] är bara tillgängligt för användarkonton som har replikeringsbehörigheter.
* När du avpublicerar en komplex resurs avpublicerar du bara resursen. Undvik att avpublicera referenserna eftersom andra publicerade resurser kan referera till dem.
* Tomma mappar publiceras inte.
* Om du publicerar ett material som bearbetas publiceras bara det ursprungliga innehållet. Återgivningarna saknas. Antingen väntar du på att bearbetningen ska slutföras och publicerar eller publicerar om resursen när bearbetningen är klar.

## Skapa en stängd användargrupp {#closed-user-group}

En CUG (Closed User Group) används för att begränsa åtkomsten till specifika resursmappar som publiceras från AEM. Om du skapar en CUG-fil för en mapp är åtkomsten till mappen (inklusive mappresurser och undermappar) begränsad till endast tilldelade medlemmar eller grupper. För att få åtkomst till mappen måste de logga in med sina inloggningsuppgifter.

CUG är ett extra sätt att begränsa åtkomsten till dina resurser. Du kan också konfigurera en inloggningssida för mappen.

**Så här skapar du en sluten användargrupp**:

1. Välj en mapp i resursgränssnittet och tryck på ikonen **[!UICONTROL Properties]** i verktygsfältet för att visa egenskapssidan.
1. Lägg till medlemmar eller grupper under **[!UICONTROL Closed User Group]** på fliken **[!UICONTROL Permissions]**.

   ![add_user](assets/add_user.png)

1. Om du vill visa en inloggningsskärm när användare öppnar mappen väljer du alternativet **[!UICONTROL Enable]**. Markera sedan sökvägen till en inloggningssida i AEM och spara ändringarna.

   ![login_page](assets/login_page.png)

   Om du inte anger sökvägen till en inloggningssida visas AEM standardinloggningssidan i publiceringsinstansen.

1. Publicera mappen och försök sedan komma åt den från publiceringsinstansen. En inloggningsskärm visas.
1. Om du är CUG-medlem anger du dina säkerhetsuppgifter. Mappen visas när AEM autentiserar dig.

## Söka efter resurser {#searching-assets}

Grundläggande sökning finns i avsnittet [Sök och filtrera](/help/sites-authoring/search.md#search-and-filter). Använd panelen **[!UICONTROL Search]** för att söka efter resurser, taggar och metadata. Du kan söka efter delar av en sträng med hjälp av asterisk med jokertecken. Dessutom kan du anpassa panelen **[!UICONTROL Search]** med [sökfunktioner](search-facets.md).

![filters_panel](assets/filters_panel.png)

För nyligen överförda resurser är deras metadata (inklusive titlar, taggar och så vidare) inte direkt tillgängliga i listan med förslag som visas när du skriver i rutan Sök.

Detta beror på att AEM Assets väntar tills en timeout-period har passerats (1 timme som standard) innan ett bakgrundsjobb körs för att indexera metadata för alla nyligen överförda/uppdaterade resurser och lägga till dem i listan med förslag.

## Använd snabbåtgärder {#quick-actions}

Snabbåtgärdsikoner är tillgängliga för en enskild resurs i taget. Beroende på vilken enhet du använder utför du följande åtgärder för att visa snabbåtgärdsikonerna:

* Pekskärmar: Peka och håll. På en iPad kan du till exempel trycka och hålla ned en resurs så att snabbåtgärderna visas.
* Ej pekskärmar: Hovringspekare. På en stationär enhet visas t.ex. snabbåtgärdsfältet om du håller pekaren över miniatyrbilden för resursen.

### Navigera till och markera resurser {#navigating-and-selecting-assets}

Du kan visa, navigera genom och välja resurser med någon av de tillgängliga vyerna (kort, kolumn, lista) med ikonen **[!UICONTROL Select]**. **[!UICONTROL Select]** visas som en snabbåtgärd i kortvyn.

![select_quick_action](assets/select_quick_action.png)

I listvyn visas **[!UICONTROL Select]** när du håller muspekaren över miniatyrbilden före namnen på resurserna/mappen i listan.

![select_quick_in_listview](assets/select_quick_in_listview.png)

På samma sätt som i listvyn visas **[!UICONTROL Select]** när du håller musikonen över miniatyrbilden före namnen på resurserna eller mappen i kolumnvyn.

![select_quick_in_columnview](assets/select_quick_in_columnview.png)

Mer information finns i [Visa och välja resurser](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).

## Redigera bilder {#editing-images}

Med redigeringsverktygen i AEM Assets gränssnitt kan du utföra små redigeringsjobb på bildresurser. Du kan beskära, rotera, vända och utföra andra redigeringsjobb på bilder. Du kan också lägga till bildscheman till resurser.

Bildredigering stöds för filer som har följande format:

* BMP
* GIF
* PNG
* JPEG

För vissa komponenter finns det ytterligare alternativ i **[!UICONTROL Full Screen]**-läget.

Om du vill redigera en TXT-fil anger du **[!UICONTROL Day CQ Link Externalizer]** i Configuration Manager.

Du kan också lägga till bildscheman med bildredigeraren. Mer information finns i [Lägga till bildscheman](image-maps.md).

**Så här redigerar du bilder**:

1. Gör något av följande om du vill öppna en resurs i redigeringsläge:

   * Markera resursen och klicka sedan på ikonen **[!UICONTROL Edit]** i verktygsfältet.
   * Tryck på **[!UICONTROL Edit]**-alternativet som visas för en resurs i kortvyn.
   * Tryck på ikonen **[!UICONTROL Edit]** i verktygsfältet på resurssidan.

   ![edit_icon](assets/edit_icon.png)

1. Om du vill beskära bilden trycker du på **[!UICONTROL Crop]**.

   ![chlimage_1-22](assets/chlimage_1-22.png)

1. Välj önskat alternativ i listan. Beskärningsområdet visas på bilden baserat på det alternativ du väljer. Med alternativet **[!UICONTROL Free Hand]** kan du beskära bilden utan begränsningar för proportioner.

   ![chlimage_1-23](assets/chlimage_1-23.png)

1. Markera området som ska beskäras och ändra storlek på det eller flytta det på bilden.
1. Använd alternativet **[!UICONTROL Finish]** i det övre högra hörnet för att beskära bilden. Om du trycker på **[!UICONTROL Finish]** aktiveras även omgenereringen av återgivningar.

   ![chlimage_1-24](assets/chlimage_1-24.png)

1. Använd ikonerna **[!UICONTROL Undo]** och **[!UICONTROL Redo]** längst upp till höger för att återgå till den beskurna bilden eller behålla den beskurna bilden.

   ![chlimage_1-25](assets/chlimage_1-25.png)

1. Tryck på motsvarande **[!UICONTROL Rotate]**-ikon för att rotera bilden medsols eller motsols.

   ![chlimage_1-26](assets/chlimage_1-26.png)

1. Tryck på motsvarande **[!UICONTROL Flip]**-ikon för att vända bilden vågrätt eller lodrätt.

   ![chlimage_1-27](assets/chlimage_1-27.png)

1. Tryck på ikonen **[!UICONTROL Finish]** för att spara ändringarna.

   ![chlimage_1-28](assets/chlimage_1-28.png)

## Använda tidslinjen {#timeline}

Med **[!UICONTROL Timeline]** kan du visa olika händelser för ett markerat objekt, till exempel aktiva arbetsflöden för en resurs, kommentarer, anteckningar, aktivitetsloggar och versioner.

I [Samlingskonsolen](managing-collections-touch-ui.md#navigating-the-collections-console) innehåller **[!UICONTROL Show All]**-listan alternativ som du kan använda för att endast visa kommentarer och arbetsflöden. Dessutom visas tidslinjen bara för samlingar på den översta nivån som visas i konsolen. Den visas inte om du navigerar i någon av samlingarna.

**[!UICONTROL Timeline]** innehåller flera  [alternativ som är specifika för innehållsfragment](content-fragments-managing.md#timeline-for-content-fragments), den här funktionen kräver  [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) eller senare.

**Så här använder du tidslinjen**:

1. Öppna resurssidan för en resurs eller markera den i resursgränssnittet.
1. Tryck på ikonen **[!UICONTROL Global Navigation]** och välj **[Tidslinje]** i listan.

   ![tidslinje](assets/timeline.png)

1. I listan som visas använder du listan **[!UICONTROL Show All]** för att filtrera resultaten baserat på kommentarer, versioner, arbetsflöden och aktiviteter.

   ![tidslinje_alternativ](assets/timeline_options.png)

## Lägg till anteckningar {#annotating}

Anteckningar är kommentarer eller förklarande kommentarer som läggs till i bilder eller videoklipp. Anteckningar ger marknadsförarna möjlighet att samarbeta och lämna feedback om resurser.

Videoanteckningar stöds bara i webbläsare med HTML5-kompatibla videoformat. Videoformat som AEM Assets stöder beror på webbläsaren.

För innehållsfragment skapas [anteckningar i redigeraren](content-fragments-variations.md#annotating-a-content-fragment); den här funktionen kräver [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) eller senare.

Du kan lägga till flera anteckningar innan du sparar dem.

Du kan lägga till anteckningar i videoresurser. När du kommenterar videoklipp pausas spelaren så att du kan anteckna i en bildruta. Mer information finns i [hantera videomaterial](managing-video-assets.md).

Du kan också lägga till anteckningar i en samling. Men om en samling innehåller underordnade samlingar kan du bara lägga till anteckningar eller kommentarer i den överordnade samlingen. Alternativet **[!UICONTROL Annotate]** är inte tillgängligt för underordnade samlingar.

**Så här lägger du till anteckningar**:

1. Navigera till platsen för resursen som du vill lägga till anteckningar i.
1. Tryck på ikonen **[!UICONTROL Annotate]** på något av följande sätt:

   * [Snabbåtgärder](managing-assets-touch-ui.md#quick-actions)
   * Från verktygsfältet när du har valt resursen eller navigerat till resurssidan

   ![chlimage_1-29](assets/chlimage_1-29.png)

1. Lägg till en kommentar i rutan **[!UICONTROL Comment]** längst ned på tidslinjen. Du kan också markera ett område i bilden och lägga till en anteckning i dialogrutan **[!UICONTROL Add Annotation]**.

   ![chlimage_1-30](assets/chlimage_1-30.png)

1. Om du vill meddela en användare om en anteckning anger du användarens e-postadress och lägger till kommentaren. Om du till exempel vill meddela Aaron McDonald om en anteckning anger du @aa. Tips för alla matchande användare visas i en lista. Välj Aaron e-postadress i listan för att tagga honom med kommentaren. På samma sätt kan du tagga fler användare var som helst i anteckningen eller före eller efter den.

   >[!NOTE]
   >
   >För användare som inte är administratörer visas endast förslag om användaren har läsbehörighet på `/home` i CRXDE.

   ![chlimage_1-31](assets/chlimage_1-31.png)

1. När du har lagt till anteckningen trycker du på **[!UICONTROL Add]** för att spara den. Ett meddelande om anteckningen skickas till Aaron.

   ![chlimage_1-32](assets/chlimage_1-32.png)

1. Tryck på **[!UICONTROL Close]** för att avsluta **[!UICONTROL Annotation]**-läget.
1. Om du vill visa meddelandet loggar du in på AEM Assets med Aaron MacDonald&#39;s credentials och trycker på ikonen **[!UICONTROL Notifications]** för att visa meddelandet.

1. Om du vill välja en annan färg så att du kan skilja mellan användarna trycker du på ikonen **[!UICONTROL Profile]** och trycker på **[!UICONTROL My Preferences]**.

   ![chlimage_1-33](assets/chlimage_1-33.png)

1. Ange önskad färg i rutan **[!UICONTROL Annotation Color]** och tryck sedan på **[!UICONTROL Accept]**.

   ![chlimage_1-34](assets/chlimage_1-34.png)

### Visa sparade anteckningar {#viewing-saved-annotations}

Du kan bara visa en anteckning åt gången.

>[!NOTE]
>
>Om du markerar flera anteckningar visas den senaste anteckningen i användargränssnittet.
>
>Flerval stöds endast för utskrift av kommenterade resurser som PDF.

1. Om du vill visa sparade anteckningar för en resurs går du till resursens plats och öppnar resurssidan för resursen.

1. Tryck på ikonen **[!UICONTROL Global Navigation]** och tryck på **[!UICONTROL Timeline]** i listan.

   ![chlimage_1-35](assets/chlimage_1-35.png)

1. I listan **[!UICONTROL Show All]** på tidslinjen väljer du **[!UICONTROL Comments]** för att filtrera resultatet baserat på kommentarer.

   ![chlimage_1-36](assets/chlimage_1-36.png)

1. Tryck på en kommentar på panelen **[!UICONTROL Timeline]** för att visa motsvarande anteckning på bilden.

   ![chlimage_1-37](assets/chlimage_1-37.png)

1. Tryck på **[!UICONTROL Delete]** om du vill ta bort en viss kommentar.

### Skriv ut anteckningar {#printing-annotations}

Om en resurs har anteckningar eller har genomgått ett granskningsarbetsflöde kan du skriva ut resursen tillsammans med anteckningar och granskningsstatus som en PDF-fil för offlinegranskning.

Du kan också välja att bara skriva ut anteckningarna eller granskningsstatusen.

>[!NOTE]
>
>Du kan välja flera anteckningar när du skriver ut den kommenterade resursen som PDF.

Långa anteckningar kanske inte återges korrekt i PDF-filen. För optimal återgivning rekommenderar Adobe att du begränsar kommentarerna till 50 ord.

Om du vill skriva ut anteckningarna och granskningsstatusen trycker du på ikonen **[!UICONTROL Print]** och följer instruktionerna i guiden. Ikonen **[!UICONTROL Print]** visas bara i verktygsfältet när resursen har minst en antecknings- eller granskningsstatus tilldelad.

1. Öppna förhandsgranskningssidan för en resurs i resursgränssnittet.
1. Gör något av följande:

   * Om du vill skriva ut alla anteckningar och granskningsstatus går du till steg 4.
   * Om du vill skriva ut specifika anteckningar och granskningsstatus öppnar du tidslinjen [och fortsätter sedan till steg 3.](managing-assets-touch-ui.md#timeline)

1. Om du vill skriva ut särskilda anteckningar väljer du anteckningarna i **[!UICONTROL Timeline]**.

   ![chlimage_1-38](assets/chlimage_1-38.png)

   Om du bara vill skriva ut granskningsstatusen väljer du den i **[!UICONTROL Timeline]**.

   ![chlimage_1-39](assets/chlimage_1-39.png)

1. Tryck på ikonen **[!UICONTROL Print]** i verktygsfältet.

   ![chlimage_1-40](assets/chlimage_1-40.png)

1. I dialogrutan **[!UICONTROL Print]** väljer du den position du vill att anteckningarna eller granskningsstatusen ska visas i PDF-filen. Om du till exempel vill att anteckningarna eller statusen ska skrivas ut längst upp till höger på sidan som innehåller den utskrivna bilden använder du inställningen **[!UICONTROL Top-Left]** (standard).

   ![chlimage_1-41](assets/chlimage_1-41.png)

   Du kan välja andra inställningar beroende på var du vill att anteckningarna eller statusen ska visas i den utskrivna PDF-filen. Om du vill att anteckningarna eller statusen ska visas på en sida som är skild från den utskrivna resursen väljer du **[!UICONTROL Next Page]**.

1. Tryck på **[!UICONTROL Print]**. Beroende på vilket alternativ du väljer i steg 2, visar den genererade PDF-filen anteckningarna eller statusen på den angivna positionen. Om du t.ex. väljer att skriva ut både anteckningar och granskningsstatus med inställningen **[!UICONTROL Top-Left]**, liknar de genererade utdata PDF-filen som återges här.

   ![chlimage_1-42](assets/chlimage_1-42.png)

1. Hämta eller skriv ut PDF-filen med alternativen längst upp till höger.

   ![chlimage_1-43](assets/chlimage_1-43.png)

   >[!NOTE]
   >
   >Om resursen har delresurser kan du skriva ut alla delresurser tillsammans med deras specifika sidvisa anteckningar.

   Om du vill ändra utseendet på den återgivna PDF-filen, till exempel teckensnittsfärg, storlek och format, bakgrundsfärg för kommentarer och statusvärden, öppnar du **[!UICONTROL Annotation PDF configuration]** från **[!UICONTROL Configuration Manager]** och ändrar önskade alternativ. Om du till exempel vill ändra visningsfärgen för den godkända statusen ändrar du färgkoden i motsvarande fält. Mer information om hur du ändrar teckenfärg i anteckningar finns i [Kommentera](managing-assets-touch-ui.md#annotating).

   ![chlimage_1-44](assets/chlimage_1-44.png)

   Återgå till den återgivna PDF-filen och uppdatera den. Den uppdaterade PDF-filen återspeglar de ändringar du har gjort.

**Så här skriver du ut anteckningar på främmande språk**: Om en resurs innehåller anteckningar på främmande språk (särskilt icke-latinska språk) måste du först konfigurera tjänsten CQ-DAM-Handler-Gibson Font Manager på AEM server så att anteckningarna kan skrivas ut. När du konfigurerar Font Manager-tjänsten CQ-DAM-Handler-Gibson anger du sökvägen till teckensnitten för de önskade språken.

1. Öppna konfigurationssidan **[!UICONTROL CQ-DAM-Handler-Gibson Font Manager Service]** från URL:en [https://&lt;server>:&lt;port>/system/console/configMgr/com.day.cq.dam.handler.gibson.fontmanager.impl.FontManagerServiceImpl](http://localhost:4502/system/console/configMgr/com.day.cq.dam.handler.gibson.fontmanager.impl.FontManagerServiceImpl).
1. Gör något av följande om du vill konfigurera **[!UICONTROL CQ-DAM-Handler-Gibson Font Manager Service]**:

   * Ange den fullständiga sökvägen till teckensnittskatalogen på datorn i katalogalternativet **[!UICONTROL System Fonts]**. Om du till exempel är Mac-användare kan du ange sökvägen som `/Library/Fonts` i katalogalternativet **[!UICONTROL System Fonts]**. AEM hämtar teckensnitten från den här katalogen.
   * Skapa en katalog med namnet **fonts** i mappen **[!UICONTROL crx-quickstart]**. **[!UICONTROL CQ-DAM-Handler-Gibson Font Manager Service]** hämtar teckensnitten automatiskt på platsen  `crx-quickstart/fonts`. Du kan åsidosätta den här standardsökvägen inifrån katalogalternativet **[!UICONTROL Adobe Server Fonts]**.
   * Skapa en ny mapp för teckensnitt i datorn och lagra önskade teckensnitt i mappen. Ange sedan den fullständiga sökvägen till den mappen i katalogalternativet **[!UICONTROL Customer Fonts]**.

1. Gå till konfigurationen **[!UICONTROL Annotation PDF]** från URL:en [https://&lt;server>:&lt;port>/system/console/configMgr/com.day.cq.dam.core.impl.annotation.pdf.AnnotationPdfConfig](http://localhost:4502/system/console/configMgr/com.day.cq.dam.core.impl.annotation.pdf.AnnotationPdfConfig).
1. Konfigurera **[!UICONTROL Annotation PDF]** med rätt uppsättning av teckensnittsfamilj enligt följande:

   * Inkludera strängen `<font_family_name_of_custom_font, sans-serif>` i alternativet för teckensnittsfamilj. Om du till exempel vill skriva ut anteckningar i CJK (kinesiska, japanska och koreanska), inkluderar du strängen `Arial Unicode MS, Noto Sans, Noto Sans CJK JP, sans-serif` i alternativet för teckensnittsfamilj. Om du vill skriva ut anteckningar på hindi hämtar du lämpligt teckensnitt och konfigurerar teckensnittsfamiljen som Arial Unicode MS, Noto Sans, Noto Sans CJK JP, Noto Sans Devanagari, sans-serif.

1. Starta om AEM.

Följande är ett exempel på hur du konfigurerar AEM att skriva ut anteckningar i CJK (kinesiska, japanska och koreanska):

1. Hämta Google Noto CJK-teckensnitt från följande länkar och lagra dem i den teckensnittskatalog som konfigurerats i teckensnittshanterartjänsten.

   * Allt i ett Super CJK-teckensnitt: [https://www.google.com/get/noto/help/cjk/](https://www.google.com/get/noto/help/cjk/)
   * Noto Sans (för europeiska språk): [https://www.google.com/get/noto/](https://www.google.com/get/noto/)
   * Teckensnitt för valfritt språk: [https://www.google.com/get/noto/](https://www.google.com/get/noto/)

1. Konfigurera PDF-filen med anteckningen genom att ange parametern font-family till `Arial Unicode MS, Noto Sans, Noto Sans CJK JP, sans-serif`. Den här konfigurationen är tillgänglig som standard och fungerar för alla europeiska språk och CJK-språk.
1. Om det språk du väljer skiljer sig från de språk som nämns i steg 2 lägger du till en lämplig (kommaseparerad) post i standardteckensnittsfamiljen.

## Skapa resursversionshantering {#asset-versioning}

Versionshantering skapar en ögonblicksbild av digitala resurser vid en viss tidpunkt. Versionshantering hjälper till att återställa resurser till ett tidigare läge vid ett senare tillfälle. Om du till exempel vill ångra en ändring som du har gjort i en resurs återställer du den oredigerade versionen av resursen.

Här följer exempel där du skapar versioner:

* Du ändrar en bild i ett annat program och överför den till AEM Assets. En version av bilden skapas så att originalbilden inte skrivs över.
* Du redigerar metadata för en resurs.
* Du använder AEM datorprogram för att checka ut en befintlig resurs och spara ändringarna. En ny version skapas varje gång resursen sparas.

Du kan även aktivera automatisk versionshantering via ett arbetsflöde. När du skapar en version för en resurs sparas metadata och återgivningar tillsammans med versionen. Återgivningar är renderingsalternativ för samma bilder, till exempel en PNG-återgivning av en överförd JPEG-fil.

Versionsfunktionen gör följande:

* Skapa en version av en resurs.
* Visa aktuell revision för en tillgång.
* Återställ resursen till en tidigare version.

**Så här skapar du resursversionshantering**:

1. Navigera till platsen för resursen som du vill skapa en version för och klicka på den för att öppna resurssidan.

1. Klicka på ikonen **[!UICONTROL Global Navigation]** och välj **[!UICONTROL Timeline]** på menyn.

   ![tidslinje-1](assets/timeline-1.png)

1. Klicka på **[!UICONTROL Actions]** längst ned för att visa tillgängliga åtgärder som du kan utföra på resursen.

1. Klicka på **[!UICONTROL Save as Version]** för att skapa en version för resursen.

   ![chlimage_1-46](assets/chlimage_1-46.png)

1. Lägg till en etikett och kommentar och klicka sedan på **[!UICONTROL Create]** för att skapa en version. Du kan också trycka på **[!UICONTROL Cancel]** för att avsluta åtgärden.

   ![chlimage_1-47](assets/chlimage_1-47.png)

1. Om du vill visa den nya versionen öppnar du listan **[!UICONTROL Show All]** på tidslinjen från sidan med resursinformation eller gränssnittet [!DNL Assets] och väljer **[!UICONTROL Versions]**.

   ![versions_option](assets/versions_option.png)

1. Välj en specifik version för resursen om du vill förhandsgranska den eller aktivera den för visning i resursgränssnittet.

   ![select_version](assets/select_version.png)

   >[!NOTE]
   >
   >Du kan också välja resursen i [listvyn](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources) eller [kolumnvyn](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).

1. Lägg till en etikett och kommentar för versionen som ska återställas till den aktuella versionen i resursgränssnittet.

   ![save_version](assets/save_version.png)

1. Om du vill generera en förhandsgranskning för versionen klickar du på **[!UICONTROL Preview Version]**.
1. Om du vill visa den här versionen i resursgränssnittet väljer du **[!UICONTROL Revert to this Version]**.
1. Om du vill jämföra två versioner går du till resursens sida och klickar på den version du vill jämföra med den aktuella versionen.

   ![Välj en tidigare version av resursen som ska jämföras med den aktuella versionen](assets/select_version_tocompare.png)

1. Välj den version du vill jämföra på tidslinjen och dra reglaget åt vänster för att lägga den här versionen ovanpå den aktuella versionen och jämföra.

   ![compare_versions](assets/compare_versions.png)

### Starta ett arbetsflöde för en resurs {#starting-a-workflow-on-an-asset}

Se [tillämpa ett arbetsflöde på en AEM](/help/assets/assets-workflow.md#apply-a-workflow-to-an-aem-asset).

## Om samlingar {#collections}

En samling är en ordnad uppsättning med resurser. Använd samlingar för att dela resurser mellan användare.

* En samling kan innehålla resurser från olika platser eftersom de bara innehåller referenser till dessa resurser. Varje samling bevarar materialens referensintegritet.
* Du kan dela samlingar med flera användare med olika behörighetsnivåer, inklusive redigering, visning och så vidare.

En användare kan ha tillgång till flera samlingar. Samlingar är av följande typer, baserat på det sätt som de samlar resurser på:

* En samling med en **statisk referenslista** med resurser, mappar och andra samlingar.

* En samling som använder ett **sökvillkor** och fyller i resurser dynamiskt baserat på villkoret. Detta kallas **smart samling**.

Mer information om samlingshantering finns i [Hantera samlingar](managing-collections-touch-ui.md).

>[!NOTE]
>
>Du måste ha rätt åtkomsträttigheter för ditt konto för att kunna skapa eller redigera resurser.
