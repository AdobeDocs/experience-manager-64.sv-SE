---
title: Lägga till Dynamic Media Classic-funktioner på sidan
seo-title: Lägga till Dynamic Media Classic-funktioner på sidan
description: Adobe Dynamic Media Classic är en värdbaserad lösning för att hantera, förbättra, publicera och leverera mediefiler till webben, mobiler, e-post och internetanslutna skärmar och för tryck.
seo-description: Adobe Dynamic Media Classic är en värdbaserad lösning för att hantera, förbättra, publicera och leverera mediefiler till webben, mobiler, e-post och internetanslutna skärmar och för tryck.
uuid: 66b9c150-c482-4a41-9772-fa39c135802c
contentOwner: Alva Ware-Bevacqui
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 9ba95dce-a801-4a36-8798-45d295371b1b
translation-type: tm+mt
source-git-commit: a3a160a0281c1ea2ca050c2c747d6a5ec1d952b3
workflow-type: tm+mt
source-wordcount: '3243'
ht-degree: 1%

---


# Lägga till Dynamic Media Classic-funktioner på sidan{#adding-scene-features-to-your-page}

[Adobe Dynamic Media Classic](https://help.adobe.com/en_US/scene7/using/WS26AB0D9A-F51C-464e-88C8-580A5A82F810.html) är en värdbaserad lösning för att hantera, förbättra, publicera och distribuera multimediematerial för webben, mobiler, e-post och internetanslutna skärmar och för tryck.

Du kan visa AEM-resurser som publicerats i Dynamic Media Classic i olika visningsprogram:

* Zoomning
* Utfällbar
* Video
* Bildmall
* Bild

Du kan publicera digitala resurser direkt från AEM till Dynamic Media Classic och du kan publicera digitala resurser från Dynamic Media Classic till AEM.

I det här avsnittet beskrivs hur du publicerar digitala resurser från AEM till Dynamic Media Classic och vice versa. Visningsprogrammen beskrivs också i detalj. Mer information om hur du konfigurerar AEM för Dynamic Media Classic finns i [Integrera Dynamic Media Classic med AEM](/help/sites-administering/scene7.md).

Se även [Lägga till bildscheman](/help/assets/image-maps.md).

Mer information om hur du använder videokomponenter med AEM finns i:

* [Video](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md)

>[!NOTE]
>
>Om resurserna i Dynamic Media Classic inte visas som de ska kontrollerar du att Dynamic Media är [inaktiverat](/help/assets/config-dynamic.md#disabling-dynamic-media) och uppdaterar sedan sidan.

## Publicera manuellt till Dynamic Media Classic från Assets {#manually-publishing-to-scene-from-assets}

Du kan publicera digitala resurser till Dynamic Media Classic antingen från Resurskonsolen i det klassiska användargränssnittet eller direkt från resursen.

>[!NOTE]
>
>AEM publicerar till Dynamic Media Classic asynkront. När du har klickat **[!UICONTROL Publish]** kan det ta flera sekunder innan resursen publiceras till Dynamic Media Classic.


### Publicera från Resurskonsolen {#publishing-from-the-assets-console}

Så här publicerar du till Dynamic Media Classic från Resurskonsolen om resurserna finns i en målmapp i Dynamic Media Classic:

1. I det klassiska användargränssnittet för AEM klickar du **[!UICONTROL Digital Assets]** för att öppna den digitala resurshanteraren.

1. Markera resursen (eller resurserna) eller mappen i målmappen som du vill publicera till Dynamic Media Classic, högerklicka och välj **[!UICONTROL Publish to Dynamic Media Classic]**. Du kan också välja **[!UICONTROL Publish to Dynamic Media Classic]** på menyn **[!UICONTROL Tools] .

   ![chlimage_1-76](assets/chlimage_1-76.png)

1. Gå till Dynamic Media Classic och bekräfta att resurserna är tillgängliga.

   >[!NOTE]
   >
   >Om resurserna inte finns i en synkroniserad Dynamic Media Classic-mapp visas **[!UICONTROL Publish to Dynamic Media Classic]** de på båda menyerna, men de är inaktiverade.

### Publicera från en resurs {#publishing-from-an-asset}

Du kan publicera en resurs manuellt så länge som resursen finns inuti den synkroniserade Dynamic Media Classic-mappen.

>[!NOTE]
>
>Om resursen inte finns i den synkroniserade mappen för Dynamic Media Classic är länken till **[!UICONTROL Publish to Dynamic Media Classic]** inte tillgänglig.

**Så här publicerar du till Dynamic Media Classic direkt från en digital resurs**:

1. I AEM klickar du **[!UICONTROL Digital Assets]** för att öppna resurshanteraren.

1. Dubbelklicka för att öppna en resurs.

1. Markera i rutan Resursinformation **[!UICONTROL Publish to Dynamic Media Classic]**.

   ![screen_shot_2012-02-22at34828pm](assets/screen_shot_2012-02-22at34828pm.png)

1. Länken ändras till **[!UICONTROL Publishing ...]** och sedan **[!UICONTROL Published]**. Gå till Dynamic Media Classic och bekräfta att resursen är tillgänglig.

   >[!NOTE]
   >
   >Om resursen inte publiceras korrekt i Dynamic Media Classic ändras länken till **[!UICONTROL Publishing Failed]**. Om resursen redan har publicerats i Dynamic Media Classic läses länken **[!UICONTROL Re-Publish to Dynamic Media Classic]**. Med ompublicering kan du göra ändringar i en mediefil i AEM och publicera om dem.

### Publicera resurser utanför CQ-målmappen {#publishing-assets-from-outside-the-cq-target-folder}

Du bör publicera resurser till Dynamic Media Classic endast från resurser i målmappen för Dynamic Media Classic. Men om du behöver överföra resurser från en mapp utanför målmappen kan du ändå göra det genom att överföra dem till en *ad hoc* -mapp i Dynamic Media Classic.

Det gör du genom att konfigurera molnkonfigurationen för sidan där resursen ska visas. Sedan lägger du till en Dynamic Media Classic-komponent på sidan och drar och släpper en resurs på komponenten. När sidegenskaperna har angetts för den sidan visas en länk som utlöser en överföring till Dynamic Media Classic när du har valt det här alternativet. **[!UICONTROL Publish to Dynamic Media Classic]**

>[!NOTE]
>
>Resurser som finns i ad hoc-mappen visas inte i Dynamic Media Classic-innehållsläsaren.

**Så här publicerar du resurser som finns utanför CQ-målmappen**:

1. I AEM i det klassiska användargränssnittet klickar du på **[!UICONTROL Websites]** och navigerar till den webbsida där du vill lägga till en digital resurs som ännu inte har publicerats i Dynamic Media Classic. (Normala sidarvsregler gäller.)

1. Klicka på **[!UICONTROL Page]** ikonen i sidosparken och klicka sedan på **[!UICONTROL Page Properties]**.

1. Klicka på **[!UICONTROL-Cloud Service > Lägg till tjänster > Dynamic Media Classic (Scene7)**.
1. Markera önskad konfiguration i listrutan Adobe Dynamic Media Classic och klicka sedan på **[!UICONTROL OK]**.

   ![chlimage_1-77](assets/chlimage_1-77.png)

1. På webbsidan lägger du till en Dynamic Media Classic-komponent (Scene7) till önskad plats på sidan.
1. Dra en digital resurs från innehållssökaren till komponenten. Du ser en länk till **[!UICONTROL Check Dynamic Media Classic Publication Status]**.

   >[!NOTE]
   >
   >Om den digitala resursen finns i CQ-målmappen **[!UICONTROL Check Dynamic Media Classic Publication Status]** visas ingen länk. Resurserna placeras bara i komponenten.

   ![chlimage_1-78](assets/chlimage_1-78.png)

1. Klicka på **[!UICONTROL Check Dynamic Media Classic Publication Status]**. Om resursen inte publiceras publicerar AEM resursen till Dynamic Media Classic. När resursen har överförts finns den i ad hoc-mappen. Som standard finns ad hoc-mappen i `name_of_the_company/CQ5_adhoc`. Du kan [konfigurera detta vid behov](#configuringtheadhocfolder).

   >[!NOTE]
   >
   >Om resursen inte finns i en synkroniserad Dynamic Media Classic-mapp och det inte finns någon Dynamic Media Classic-molnkonfiguration kopplad till den aktuella sidan, kommer överföringen att misslyckas.

## Dynamic Media Classic-komponenter (Scene7) {#scene-components}

Följande Dynamic Media Classic-komponenter är tillgängliga i AEM:

* Zoomning
* Utfällbar (zoom)
* Bildmall
* Bild
* Video

>[!NOTE]
>
>De här komponenterna är inte tillgängliga som standard och måste markeras i **[!UICONTROL Design]** läget innan du använder.

När de har gjorts tillgängliga i **[!UICONTROL Design]** läge kan du lägga till komponenterna på sidan precis som andra AEM-komponenter. Resurser som ännu inte har publicerats i Dynamic Media Classic publiceras i Dynamic Media Classic om de ligger i en synkroniserad mapp, på en sida eller med en Dynamic Media Classic-molnkonfiguration.

### Flash viewers end-of-life notice {#flash-viewers-end-of-life-notice}

Från och med den 31 januari 2017 upphör stödet för Flash-visningsprogramplattformen officiellt i Adobe Dynamic Media Classic.

Mer information om den här viktiga förändringen finns i Vanliga frågor och svar om [uttjänta versioner av Flash](https://docs.adobe.com/content/docs/en/aem/6-1/administer/integration/marketing-cloud/scene7/flash-eol.html)Viewer.

### Lägga till en Dynamic Media Classic-komponent på en sida {#adding-a-scene-component-to-a-page}

Att lägga till en Dynamic Media Classic-komponent på en sida är detsamma som att lägga till en komponent på en sida. Dynamic Media Classic-komponenter beskrivs i detalj i följande avsnitt.

**Så här lägger du till en Dynamic Media Classic-komponent/ett visningsprogram på en sida i det klassiska användargränssnittet**:

1. Öppna den sida där du vill lägga till Dynamic Media Classic-komponenten i AEM.

1. Om det inte finns några tillgängliga Dynamic Media Classic-komponenter klickar du på linjalen i sidosparken för att gå till **[!UICONTROL Design]** läget, klickar på **[!UICONTROL Edit]** parsys och väljer alla **[!UICONTROL Dynamic Media Classic]** komponenter som ska vara tillgängliga.

1. Gå tillbaka till **[!UICONTROL Edit]** läget genom att klicka på pennan i sidsparken.

1. Dra en komponent från **[!UICONTROL Dynamic Media Classic]** gruppen i sidsparken till sidan på önskad plats.

1. Klicka **[!UICONTROL Edit]** för att öppna komponenten.

1. Redigera komponenten efter behov och klicka på **[!UICONTROL OK]** för att spara ändringarna.

### Lägga till interaktiva tittarupplevelser på en responsiv webbplats {#adding-interactive-viewing-experiences-to-a-responsive-website}

Responsiv design för dina resurser innebär att dina resurser anpassas beroende på var de visas. Med responsiv design visas samma material effektivt på flera enheter.

**Så här lägger du till en interaktiv visningsupplevelse på en responsiv webbplats i det klassiska användargränssnittet**:

1. Logga in på AEM och kontrollera att du har [konfigurerat Adobe Dynamic Media Classic-Cloud Service](/help/sites-administering/scene7.md#configuring-scene-integration) och att Dynamic Media Classic-komponenter är tillgängliga.

   >[!NOTE]
   >
   >Om Dynamic Media Classic WCM-komponenter inte är tillgängliga måste du aktivera dem i **[!UICONTROL Design] -läget.

1. På en webbplats där komponenterna i Dynamic Media Classic är aktiverade drar du ett **[!UICONTROL Image]** visningsprogram till sidan.
1. Redigera komponenten och justera brytpunkterna på **[!UICONTROL Dynamic Media Classic Settings]** fliken.

   ![chlimage_1-79](assets/chlimage_1-79.png)

1. Bekräfta att tittarna ändrar storlek rejält och att alla interaktioner är optimerade för datorer, surfplattor och mobiler.

### Gemensamma inställningar för alla Dynamic Media Classic-komponenter {#settings-common-to-all-scene-components}

Även om konfigurationsalternativen varierar är följande vanligt för alla Dynamic Media Classic-komponenter:

* **[!UICONTROL File Reference]** - Bläddra till en fil som du vill referera till. Filreferensen visar resurs-URL:en och inte nödvändigtvis den fullständiga Dynamic Media Classic-URL:en, inklusive URL-kommandona och -parametrarna. Du kan inte lägga till Dynamic Media Classic URL-kommandon och -parametrar i det här fältet. De måste läggas till med motsvarande funktioner i komponenten.
* **[!UICONTROL Width]** - Ange bredden.
* **[!UICONTROL Height]** - Här kan du ange höjden.

Du anger dessa konfigurationsalternativ genom att dubbelklicka på en Dynamic Media Classic-komponent, till exempel när du öppnar en **[!UICONTROL Zoom]** komponent:

![chlimage_1-80](assets/chlimage_1-80.png)

### Zoomning {#zoom}

HTML5 Zoom-komponenten visar en större bild när du trycker på +-knappen.

Resursen har zoomverktyg längst ned. Klicka **[!UICONTROL +]** för att förstora. Klicka **[!UICONTROL -]** för att minska. Om du klickar **[!UICONTROL x]** eller återställer zoompilen återställs bilden till den ursprungliga storlek den importerades som. Klicka på de diagonala pilarna för att göra helskärmspilen. Klicka **[!UICONTROL Edit]** för att konfigurera komponenten. Med den här komponenten kan du konfigurera [inställningar som är gemensamma för alla Dynamic Media Classic-komponenter](#settings-common-to-all-scene-components).

![](do-not-localize/chlimage_1-5.png)

### Utfällbar {#flyout}

I den utfällbara HTML5-komponenten visas resursen som en delad skärm. lämnade tillgången i den angivna storleken, till höger visas zoomdelen. Klicka **[!UICONTROL Edit]** för att konfigurera komponenten. Med den här komponenten kan du konfigurera [inställningar som är gemensamma för alla Dynamic Media Classic-komponenter](/help/sites-administering/scene7.md#settingscommontoalldynamicmediaclassiccomponents).

>[!NOTE]
>
>Om den utfällbara komponenten använder en anpassad storlek, används den anpassade storleken och responsiv konfiguration av komponenten inaktiveras.
>
>Om den utfällbara komponenten använder standardstorleken, enligt inställningen i [!UICONTROL Design] vyn, används standardstorleken och komponenten sträcks ut för att passa sidlayoutstorleken med responsiv inställning för komponenten aktiverad. Tänk dock på att det finns en begränsning för responsiv konfiguration av komponenten. När du använder den utfällbara komponenten med responsiv konfiguration bör du inte använda den med full sidsträckning. I annat fall kan den utfällbara menyn sträcka sig utanför sidans högra kant.

![chlimage_1-81](assets/chlimage_1-81.png)

### Bild {#image}

Med Dynamic Media Classic Image-komponenten kan du lägga till Dynamic Media Classic-funktioner i dina bilder, t.ex. Dynamic Media Classic-modifierare, bild- eller visningsförinställningar samt skärpa. Dynamic Media Classic-bildkomponenten liknar andra bildkomponenter i AEM med speciella Dynamic Media Classic-funktioner. I det här exemplet används Dynamic Media Classic URL-modifieraren `&op_invert=1` .

![](do-not-localize/chlimage_1-6.png)

**[!UICONTROL Title, Alt Text]** - Lägg till en titel på bilden och alternativ text på fliken [!UICONTROL Advanced] för användare som har bilder inaktiverade.

**[!UICONTROL URL, Open in]** - Du kan ställa in en resurs från för att öppna en länk. Ange **[!UICONTROL URL]** och **[!UICONTROL Open in]** ange om du vill att den ska öppnas i samma fönster eller i ett nytt fönster.

![chlimage_1-82](assets/chlimage_1-82.png)

**[!UICONTROL Viewer preset]** - Välj en befintlig visningsförinställning i listrutan. Om den visningsförinställning som du söker efter inte visas kan du behöva göra den synlig. Se [Hantera visningsförinställningar](/help/assets/managing-viewer-presets.md). Du kan inte välja en visningsförinställning om du använder en bildförinställning och vice versa.

**[!UICONTROL Dynamic Media Classic Configuration]** - Välj den Dynamic Media Classic-konfiguration som du vill använda för att hämta aktiva bildförinställningar från Scene7 Publishing System.

**[!UICONTROL Image preset]** - Välj en befintlig bildförinställning i listrutan. Om den bildförinställning du söker inte syns kan du behöva göra den synlig. Se [Hantera bildförinställningar](/help/assets/managing-image-presets.md). Du kan inte välja en visningsförinställning om du använder en bildförinställning och vice versa.

**[!UICONTROL Output Format]** - Välj bildens utdataformat, till exempel jpeg. Beroende på vilket utdataformat du väljer kan det finnas ytterligare konfigurationsalternativ. Se [Hantera bildförinställningar](/help/assets/managing-image-presets.md).

**[!UICONTROL Sharpening]** - Välj hur du vill öka skärpan i bilden. Skärpeinställningen förklaras i detalj i [*Adobe Dynamic Media Classic Image Quality and Sharpening Best Practices *](/help/assets/assets/s7_sharpening_images.pdf).

**[!UICONTROL URL Modifiers]** - Du kan ändra bildeffekter genom att ange ytterligare bildkommandon i Dynamic Media Classic. Dessa beskrivs i [Hantera bildförinställningar](/help/assets/managing-image-presets.md) och i [Kommandoreferensen](https://docs.adobe.com/content/help/en/dynamic-media-developer-resources/image-serving-api/image-serving-api/http-protocol-reference/command-reference/c-command-reference.html).

**[!UICONTROL Breakpoints]** - Om webbplatsen är responsiv vill du justera brytpunkterna. Brytpunkter måste avgränsas med kommatecken `,`.

### Bildmall {#image-template}

[Dynamic Media Classic-bildmallar](https://help.adobe.com/en_US/scene7/using/WS60B68844-9054-4099-BF69-3DC998A04D3C.html) är lageruppbyggt Photoshop-innehåll som importerats till Dynamic Media Classic, där innehåll och egenskaper parametriserats för variabilitet. Med **[!UICONTROL Image template]** komponenten kan du importera bilder och ändra texten dynamiskt i AEM. Dessutom kan du konfigurera **[!UICONTROL Image template]** komponenten så att värden från klientkontexten används, så att varje användare upplever bilden på ett personligt sätt.

Klicka **[!UICONTROL Edit]** för att konfigurera komponenten. Du kan konfigurera [inställningar som är gemensamma för alla Dynamic Media Classic-komponenter](/help/sites-administering/scene7.md#settingscommontoalldynamicmediaclassicscomponents) samt andra inställningar som beskrivs i det här avsnittet.

![chlimage_1-83](assets/chlimage_1-83.png)

**[!UICONTROL File Reference, Width, Height]** - Se de inställningar som är gemensamma för alla komponenter i Dynamic Media Classic.

>[!NOTE]
>
>Det går inte att lägga till Dynamic Media Classic-URL-kommandon och -parametrar direkt i filreferenswebbadressen. De kan bara definieras i komponentgränssnittet på **[!UICONTROL Parameter]** panelen.

**[!UICONTROL Title, Alt Text]** Lägg till en titel på bilden och alternativ text på fliken [!UICONTROL Dynamic Media Classic Image Template] för användare som har bilder inaktiverade.

**[!UICONTROL URL, Open in]** Du kan ställa in en resurs från för att öppna en länk. Ange **[!UICONTROL URL]** och i **[!UICONTROL Open in]** anger om du vill att den ska öppnas i samma fönster eller i ett nytt fönster.

![chlimage_1-84](assets/chlimage_1-84.png)

**[!UICONTROL Parameter Panel]** När du importerar en bild fylls parametrarna i automatiskt med information från bilden. Om det inte finns något innehåll som kan ändras dynamiskt är det här fönstret tomt.

![chlimage_1-85](assets/chlimage_1-85.png)

#### Ändra text dynamiskt {#changing-text-dynamically}

Om du vill ändra texten dynamiskt anger du ny text i fälten och klickar på **[!UICONTROL OK]**. I det här exemplet **[!UICONTROL Price]** är nu 50 dollar och frakten 99 cent.

![chlimage_1-86](assets/chlimage_1-86.png)

Texten i bilden ändras. Du kan återställa texten till det ursprungliga värdet genom att klicka **[!UICONTROL Reset]** bredvid fältet.

![chlimage_1-87](assets/chlimage_1-87.png)

#### Ändra text så att värdet för en klientkontext återspeglas {#changing-text-to-reflect-the-value-of-a-client-context-value}

Om du vill länka ett fält till ett klientkontextvärde klickar du på **[!UICONTROL Select]** för att öppna klientsnabbmenyn, markerar klientkontexten och klickar på **[!UICONTROL OK]**. I det här exemplet ändras namnet baserat på att namnet länkas till det formaterade namnet i profilen.

![chlimage_1-88](assets/chlimage_1-88.png)

Texten återspeglar namnet på den inloggade användaren. Du kan återställa texten till det ursprungliga värdet genom att klicka **[!UICONTROL Reset]** bredvid fältet.

![chlimage_1-89](assets/chlimage_1-89.png)

#### Göra Dynamic Media Classic-bildmallen till en länk {#making-the-scene-image-template-a-link}

**Så här skapar du en länk** till bildmallen i Dynamic Media Classic:

1. På sidan med bildmallskomponenten Dynamic Media Classic klickar du på **[!UICONTROL Edit]**.
1. I **[!UICONTROL URL]** fältet anger du den URL som användarna ska gå till när de klickar på bilden. I **[!UICONTROL Open in]** fältet väljer du om du vill att målet ska öppnas (ett nytt fönster eller samma fönster).

   ![chlimage_1-90](assets/chlimage_1-90.png)

1. Klicka på **[!UICONTROL OK]**.

### Videokomponent {#video-component}

I Dynamic Media Classic- **[!UICONTROL Video]** komponenten (som finns i Dynamic Media Classic-avsnittet i sidosparken) används enhets- och bandbreddsidentifiering för att visa rätt video för varje skärm. Den här komponenten är en HTML5-videospelare; det är ett enda visningsprogram som kan användas över flera kanaler.

Den kan användas för adaptiva videouppsättningar, en enda MP4-video eller en enda F4V-video.

Mer information om hur videofilmer fungerar med integrering med Dynamic Media Classic finns i [Video](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md) . Jämför videokomponenten [i **Dynamic Media Classic** med **videokomponenten** som utgör grunden](/help/sites-classic-ui-authoring/manage-assets-classic-s7-video.md).

![chlimage_1-91](assets/chlimage_1-91.png)

### Kända begränsningar för videokomponenten {#known-limitations-for-the-video-component}

Adobe DAM och WCM visar om en mastervideo har överförts. De visar inte följande proxyresurser:

* Dynamic Media Classic-kodade återgivningar
* Dynamic Media Classic adaptiva videouppsättningar

När du använder en adaptiv videouppsättning med videokomponenten i Dynamic Media Classic måste du ändra storlek på komponenten så att den passar videofilens mått.

## Dynamic Media Classic-innehållsläsare {#scene-content-browser}

I Dynamic Media Classic kan du visa innehåll från Dynamic Media Classic direkt i AEM. Om du vill få åtkomst till innehållsläsaren väljer du **[!UICONTROL Dynamic Media Classic]** i det pekoptimerade användargränssnittet eller **[!UICONTROL S7]** ikonen i det klassiska användargränssnittet. Funktionen är identisk mellan båda användargränssnitten.

Om du har flera konfigurationer visar AEM som standard [standardkonfigurationen](/help/sites-administering/scene7.md#configuring-a-default-configuration). Du kan välja olika konfigurationer direkt i webbläsaren för Dynamic Media Classic-innehåll i listrutan.

>[!NOTE]
>
>* Resurser som finns i ad hoc-mappen visas inte i Dynamic Media Classic-innehållsläsaren.
>* När [Säker förhandsvisning är aktiverat](/help/sites-administering/scene7.md#configuring-the-state-published-unpublished-of-assets-pushed-to-scene)visas både publicerade och opublicerade resurser i Dynamic Media Classic i innehållsläsaren i Dynamic Media Classic.
>* Om du inte ser **[!UICONTROL Dynamic Media Classic]** eller **[!UICONTROL S7]** ikonen som ett alternativ i webbläsaren måste du [konfigurera Dynamic Media Classic så att det fungerar med AEM](/help/sites-administering/scene7.md).
   >
   >
* För video har Dynamic Media Classic-innehållsläsaren stöd för:
   >
   >
* Adaptiva videouppsättningar: behållare för alla videoåtergivningar som behövs för sömlös uppspelning på flera skärmar
>* Enkel MP4-video
>* En F4V-video


### Bläddra bland innehåll i det klassiska användargränssnittet {#browsing-content-in-the-classic-ui}

Bläddra bland innehåll i Dynamic Media Classic genom att klicka på **[!UICONTROL S7]** fliken.

Du kan ändra konfigurationen som du använder genom att välja konfigurationen. Mapparna ändras beroende på vilken konfiguration du väljer.

![chlimage_1-92](assets/chlimage_1-92.png)

Precis som med Innehållssökaren för Resurser kan du söka efter resurser och filtrera resultat. Till skillnad från Assets Finder **[!UICONTROL S7]** börjar emellertid filnamnet när du anger ett nyckelord på *-fliken med* strängen som du angav, i stället för *att innehålla* nyckelordet i filnamnet.

Som standard visas resurser efter filnamn. Du kan också filtrera resultat efter resurstyp.

>[!NOTE]
>
>För video har Dynamic Media Classic-webbläsaren i WCM stöd för:
>
>* Adaptiva videouppsättningar: behållare för alla videoåtergivningar som behövs för sömlös uppspelning på flera skärmar
>* Enkel MP4-video
>* En F4V-video
>



### Söka efter Dynamic Media Classic-resurser med innehållsläsaren {#searching-for-scene-assets-with-the-content-browser}

Att söka efter Dynamic Media Classic-resurser liknar att söka efter AEM-resurser, förutom att när du söker ser du en fjärrvy av resurserna i Dynamic Media Classic-systemet i stället för att importera dem direkt till AEM.

Du kan använda det klassiska användargränssnittet eller det pekoptimerade användargränssnittet för att både visa och söka efter resurser. Beroende på gränssnittet är sökningen något annorlunda.

När du söker i något av användargränssnitten kan du filtrera efter följande villkor (visas här i det pekoptimerade användargränssnittet):

**[!UICONTROL Enter keywords]** - Du kan söka efter resurser efter namn. När du söker efter nyckelord som du anger är det filnamnet börjar med. Om du till exempel skriver ordet &quot;simning&quot; söker du efter alla resursfilnamn som börjar med de bokstäverna i den ordningen. Var noga med att klicka på Ange när du har skrivit in termen för att hitta resursen.

![chlimage_1-93](assets/chlimage_1-93.png)

**[!UICONTROL Folder/path]** - Namnet på mappen som visas baseras på den konfiguration du har valt. Du kan gå ned till lägre nivåer genom att klicka på mappikonen och välja en undermapp. Markera sedan kryssrutan för att markera den.

Om du anger ett nyckelord och väljer en mapp söker AEM igenom den mappen och eventuella undermappar. Om du inte anger några nyckelord när du söker efter, kommer endast resurserna i den mappen att visas om du väljer mappen. Inga undermappar kommer att visas.

Som standard söker AEM igenom den markerade mappen och alla undermappar.

![chlimage_1-94](assets/chlimage_1-94.png)

**[!UICONTROL Type of Asset]** Välj Dynamic Media Classic om du vill bläddra i Dynamic Media Classic-innehåll. Det här alternativet är bara tillgängligt om du redan har konfigurerat Dynamic Media Classic.

![chlimage_1-95](assets/chlimage_1-95.png)

**[!UICONTROL Configuration]** Om du har definierat fler än en Dynamic Media Classic-konfiguration i [!UICONTROL Cloud Services]kan du markera den här. Därför ändras mappen baserat på den konfiguration du har valt.

![chlimage_1-96](assets/chlimage_1-96.png)

**[!UICONTROL Asset type]** I Dynamic Media Classic-webbläsaren kan du filtrera resultat så att de innehåller något av följande: bilder, mallar, videor och anpassningsbara videouppsättningar. Om du inte väljer någon resurstyp söker AEM som standard igenom alla resurstyper.

![chlimage_1-97](assets/chlimage_1-97.png)

>[!NOTE]
>
>* När du söker efter video söker du efter en enskild återgivning. Resultatet returnerar den ursprungliga återgivningen (endast &amp;ast;.mp4) och den kodade återgivningen.
>* När du söker i en adaptiv videouppsättning söker du i mappen och i alla undermappar, men bara om du har lagt till ett nyckelord i sökningen. Om du inte har lagt till något nyckelord söker AEM inte igenom undermapparna.
>



**[!UICONTROL Publish Status]** Du kan filtrera efter resurser baserat på publiceringsstatus: [!UICONTROL Published] eller [!UICONTROL Unpublished]. Om du inte väljer något [!UICONTROL Publish status]söker AEM som standard igenom alla publiceringsstatusar.

![chlimage_1-98](assets/chlimage_1-98.png)

