---
title: Meddelandefunktion
seo-title: Meddelandefunktion
description: Konfigurera meddelandekomponenter
seo-description: Konfigurera meddelandekomponenter
uuid: 29ab63b6-67a1-4eb8-8cf8-c1ff52ff2bac
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 88ee8573-58c4-42cd-8e36-2ea4a0d654e4
translation-type: tm+mt
source-git-commit: 8c66f2b0053882bd1c998d8e01dbb0573881bc87

---


# Meddelandefunktion {#messaging-feature}

Förutom de allmänt synliga interaktioner som förekommer i forum och kommentarer, gör meddelandefunktionen i AEM Communities det möjligt för communitymedlemmar att interagera med varandra mer privat.

Den här funktionen kan finnas när en [communitywebbplats](overview.md#communitiessites) skapas.

Med meddelandefunktionerna kan du:

* Skicka ett meddelande till en eller flera community-medlemmar
* Skicka ett meddelande till en community-medlemsgrupp
* Skicka ett meddelande med bilagor
* Vidarebefordra ett meddelande
* Svara på ett meddelande
* Ta bort ett meddelande
* Återställa ett borttaget meddelande

Om du vill aktivera och ändra meddelandefunktionen går du till

* [Konfigurera meddelanden](messaging.md) för administratörer
* [Meddelandefunktioner](essentials-messaging.md) för utvecklare

>[!NOTE]
>
>Det går inte att lägga till `Compose Message, Message, or Message List` komponenter (finns i `Communities`komponentgruppen) på en sida i redigeringsläge för författare.

## Konfigurerar meddelandekomponenter {#configuring-messaging-components}

När meddelanden är aktiverat för en community-webbplats är det helt konfigurerat utan någon ytterligare konfiguration. Den här informationen tillhandahålls om du behöver ändra standardkonfigurationen.

### Konfigurerar meddelandelista (meddelanderuta) {#configuring-message-list-messagebox}

Om du vill ändra konfigurationen för listan med meddelanden för **sidorna Inkorgen**, **Skickat** och **Papperskorgen** i meddelandefunktionen öppnar du webbplatsen i [redigeringsläge](sites-console.md#authoring-site-content).

I `Preview` läget väljer du länken **[!UICONTROL Meddelanden]** för att öppna huvudmeddelandesidan. Välj sedan antingen **[!UICONTROL Inkorg, Skickat eller Papperskorgen]** för att konfigurera komponenten för den meddelandelistan.

Markera komponenten på sidan i `Edit` läget.

Om du vill komma åt konfigurationsdialogrutan måste du avbryta arvet genom att markera `link`ikonen.

När konfigurationen är klar är det nödvändigt att återställa arvet genom att markera `broken link` -ikonen.

![chlimage_1-396](assets/chlimage_1-396.png)

När arvet har avbrutits går det att välja `configure` ikonen för att öppna konfigurationsdialogrutan.

![chlimage_1-397](assets/chlimage_1-397.png)

#### Fliken Grundläggande {#basic-tab}

![chlimage_1-398](assets/chlimage_1-398.png)

* **[!UICONTROL Tjänstväljare]**(*obligatoriskt*) Ange värdet för egenskapen `serviceSelector.name` från [AEM Communities Messaging Operations Service](messaging.md#messaging-operations-service).

* **[!UICONTROL Disponera sida]**(*obligatoriskt*) Den sida som ska öppnas när en medlem klickar på `Reply` knappen. Målsidan ska innehålla **[!UICONTROL formuläret Dispositionsmeddelande]** .

* **[!UICONTROL Svara/Visa som resurs]** Om det här alternativet är markerat refererar URL:en för svar och vy till en resurs. Annars skickas data som frågeparametrar i URL:en.

* **[!UICONTROL Profilvisningsformulär]** Profilformuläret som ska användas för att visa avsändarprofilen.

* **[!UICONTROL Om alternativet är markerat visas endast meddelanden som har flaggats som borttagna (papperskorg) i den här meddelandelistekomponenten]**.

* **[!UICONTROL Mappsökvägar]**(*obligatoriskt*) som refererar till de värden som angetts för `inbox.path.name` och `sentitems.path.name` i [AEM Communities Messaging Operations Service](messaging.md#messaging-operations-service). När du konfigurerar för en `Inbox`post lägger du till en post med värdet för `inbox.path.name`. När du konfigurerar för en `Outbox`post lägger du till en post med värdet för `sentitems.path.name`. När du konfigurerar för `Trash`lägger du till två poster med båda värdena.

#### Fliken Visa {#display-tab}

![chlimage_1-399](assets/chlimage_1-399.png)

* **[!UICONTROL Markera Läs-knapp]** Om det här alternativet är markerat visas en `Read`knapp som gör att ett meddelande kan markeras som läst.

* **[!UICONTROL Markera oläst knapp]** Om det här alternativet är markerat visas en `Mark Unread` knapp som gör att ett meddelande kan markeras som läst.

* **[!UICONTROL Om alternativet Ta bort knapp]**&#x200B;är markerat visas en `Delete`knapp där ett meddelande kan markeras som läst. Duplicerar borttagningsfunktionen om **`Message Options`** även den är markerad.

* **[!UICONTROL Meddelandealternativ]** Om det här alternativet är markerat visas **`Reply`**-, **`Reply All`****`Forward`** - och **`Delete`** -knappar som gör att ett meddelande kan skickas igen eller tas bort. Duplicerar borttagningsfunktionen om **`Delete Button`** även den är markerad.

* **[!UICONTROL Meddelanden per sida]** Det angivna antalet är det maximala antalet meddelanden som visas per sida i ett sidnumreringsschema. Om inget tal anges (vänster tomt) visas alla meddelanden och ingen sidnumrering visas.

* **[!UICONTROL Tidsstämpelmönster]** Tillhandahåller tidsstämpelmönster för ett eller flera språk. Standard är för en, de, fr, it, es, ja, zh_CN, ko_KR.

* **[!UICONTROL Visa Användare]** Välj antingen **`Sender`** eller **`Recipients`** för att bestämma om avsändaren eller mottagarna ska visas.

### Konfigurera Compose Message {#configuring-compose-message}

Om du vill ändra konfigurationen för den sammansatta meddelandesidan öppnar du webbplatsen i [redigeringsläge](sites-console.md#authoring-site-content).

I `Preview`läget väljer du länken **[!UICONTROL Meddelanden]** för att öppna huvudmeddelandesidan. Klicka sedan på knappen Nytt meddelande för att öppna `Compose Message` sidan.

I `Edit` läget markerar du huvudkomponenten på sidan som innehåller meddelandetexten.

Om du vill komma åt konfigurationsdialogrutan måste du avbryta arvet genom att markera `link`ikonen.

När konfigurationen är klar är det nödvändigt att återställa arvet genom att markera `broken link` -ikonen.

![chlimage_1-400](assets/chlimage_1-400.png)

När arvet har avbrutits går det att välja `configure` ikonen för att öppna konfigurationsdialogrutan.

![chlimage_1-401](assets/chlimage_1-401.png)

#### Fliken Grundläggande {#basic-tab-1}

![chlimage_1-402](assets/chlimage_1-402.png)

* **[!UICONTROL Omdirigerings-URL]** Ange URL-adressen till sidan som visas när meddelandet har skickats. Exempel, `../messaging.html`.

* **[!UICONTROL Avbryt URL]** Ange URL-adressen till sidan som visas om avsändaren avbryter meddelandet. Exempel, `../messaging.html`.

* **[!UICONTROL Maximal längd för meddelandemotiv]** Det maximala antalet tecken som tillåts i ämnesfältet. Till exempel 500. Standard är ingen gräns.

* **[!UICONTROL Maximal längd på meddelandetext]** Det maximala antalet tecken som tillåts i fältet Innehåll. Exempel: 10000. Standard är ingen gräns.

* **[!UICONTROL Tjänstväljare]**(*obligatoriskt*) Ange värdet för egenskapen **`serviceSelector.name`** från [AEM Communities Messaging Operations Service](messaging.md#messaging-operations-service).

#### Fliken Visa {#display-tab-1}

![chlimage_1-403](assets/chlimage_1-403.png)

* **[!UICONTROL Visa ämnesfält]** Om det här alternativet är markerat visar du `Subject` fältet och aktiverar möjligheten att lägga till ett ämne i meddelandet. Standard är inte markerat.

* **[!UICONTROL Ämnesetikett]** Ange texten som ska visas bredvid `Subject` fältet. Standardvärdet är `Subject`.

* **[!UICONTROL Visa Bifoga filfält]** Om det är markerat, visa `Attachment` fältet och aktivera tillägg av bifogade filer i meddelandet. Standard är inte markerat.

* **[!UICONTROL Bifoga filetikett]** Ange den text som ska visas bredvid `Attachment` fältet. Standardvärdet är **`Attach File`**.

* **[!UICONTROL Visa innehållsfält]** Om det är markerat visar du `Content` fältet och aktiverar tillägg av meddelandetext. Standard är inte markerat.

* **[!UICONTROL Innehållsetikett]** Ange den text som ska visas bredvid `Content` fältet. Standardvärdet är **`Body`**.

* **[!UICONTROL Om alternativet är markerat med RTF-redigeraren]** visar det att en anpassad textruta med formaterad text används. Standard är inte markerat.

* **[!UICONTROL Tidsstämpelmönster]** Tillhandahåller tidsstämpelmönster för ett eller flera språk. Standard är för en, de, fr, it, es, ja, zh_CN, ko_KR.

