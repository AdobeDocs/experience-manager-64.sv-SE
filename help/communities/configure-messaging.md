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
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 1%

---


# Meddelandefunktion {#messaging-feature}

Förutom de synliga interaktionerna som förekommer i forum och i kommentarer gör meddelandefunktionen i AEM Communities det möjligt för communitymedlemmar att interagera med varandra mer privat.

Den här funktionen kan ingå när en [community-webbplats](overview.md#communitiessites) skapas.

Med meddelandefunktionerna kan du:

* Skicka ett meddelande till en eller flera community-medlemmar
* Skicka ett meddelande till en community-medlemsgrupp
* Skicka ett meddelande med bilagor
* Vidarebefordra ett meddelande
* Svara på ett meddelande
* Ta bort ett meddelande
* Återställa ett borttaget meddelande

Om du vill aktivera och ändra meddelandefunktionen går du till

* [Konfigurera ](messaging.md) meddelanden för administratörer
* [Messaging ](essentials-messaging.md) Essentials för utvecklare

>[!NOTE]
>
>Det går inte att lägga till `Compose Message, Message, or Message List`-komponenter (finns i `Communities`komponentgrupp) till en sida i redigeringsläge för författare.

## Konfigurerar meddelandekomponenter {#configuring-messaging-components}

När meddelanden är aktiverat för en community-webbplats är det helt konfigurerat utan någon ytterligare konfiguration. Den här informationen tillhandahålls om du behöver ändra standardkonfigurationen.

### Konfigurerar meddelandelista (meddelanderuta) {#configuring-message-list-messagebox}

Om du vill ändra konfigurationen för listan med meddelanden för **Inkorg**, **Skickade objekt** och **Papperskorgssidor för meddelandefunktionen öppnar du webbplatsen i [redigeringsläge](sites-console.md#authoring-site-content) för författare.**

I `Preview`-läget väljer du länken **[!UICONTROL Messages]** för att öppna huvudmeddelandesidan. Välj sedan antingen **[!UICONTROL Inbox, Sent Items, or Trash]** för att konfigurera komponenten för den meddelandelistan.

Markera komponenten på sidan i `Edit`-läge.

Om du vill komma åt konfigurationsdialogrutan måste du avbryta arvet genom att välja ikonen `link`.

När konfigurationen är klar måste du återställa arvet genom att välja ikonen `broken link`.

![chlimage_1-396](assets/chlimage_1-396.png)

När arvet har avbrutits går det att välja ikonen `configure` för att öppna konfigurationsdialogrutan.

![chlimage_1-397](assets/chlimage_1-397.png)

#### Fliken Grundläggande {#basic-tab}

![chlimage_1-398](assets/chlimage_1-398.png)

* **[!UICONTROL Service selector]**
(*Obligatoriskt*) Ange det här till värdet för egenskapen  `serviceSelector.name` från  [AEM Communities Messaging Operations Service](messaging.md#messaging-operations-service).

* **[!UICONTROL Compose Page]**
(*Obligatoriskt*) Den sida som ska öppnas när en medlem klickar på  `Reply` knappen. Målsidan ska innehålla formuläret **[!UICONTROL Compose Message]**.

* **[!UICONTROL Reply/View as Resource]**
Om det här alternativet är markerat refererar URL:en för svar och vy till en resurs, annars skickas data som frågeparametrar i URL:en.

* **[!UICONTROL Profile Display Form]**
Det profilformulär som ska användas för att visa avsändarprofilen.

* **[!UICONTROL Trash Folder]**
Om den här meddelandelistekomponenten är markerad visas endast meddelanden som har flaggats som borttagna (papperskorg).

* **[!UICONTROL Folder Paths]**
(*Obligatoriskt*) Referera till de värden som angetts för  `inbox.path.name` och  `sentitems.path.name` i  [AEM Communities meddelandetjänst](messaging.md#messaging-operations-service). När du konfigurerar för en `Inbox` lägger du till en post med värdet `inbox.path.name`. När du konfigurerar för en `Outbox` lägger du till en post med värdet `sentitems.path.name`. När du konfigurerar för `Trash` lägger du till två poster med båda värdena.

#### Visningsflik {#display-tab}

![chlimage_1-399](assets/chlimage_1-399.png)

* **[!UICONTROL Mark Read Button]**
Om det här alternativet är markerat visas en 
`Read`så att ett meddelande kan markeras som läst.

* **[!UICONTROL Mark Unread Button]**
Om det här alternativet är markerat visas en 
`Mark Unread` så att ett meddelande kan markeras som läst.

* **[!UICONTROL Delete Button]**
Om det här alternativet är markerat visas en 
`Delete`så att ett meddelande kan markeras som läst. Duplicerar borttagningsfunktionen om **`Message Options`** också är markerat.

* **[!UICONTROL Message Options]**
Om det här alternativet är markerat visas 
**`Reply`**,  **`Reply All`** och  **`Forward`**   **`Delete`** knappar som gör att ett meddelande kan skickas igen eller tas bort. Duplicerar borttagningsfunktionen om **`Delete Button`** också är markerat.

* **[!UICONTROL Messages Per Page]**
Det angivna antalet är det högsta antalet meddelanden som visas per sida i ett sidnumreringsschema. Om inget tal anges (vänster tomt) visas alla meddelanden och ingen sidnumrering visas.

* **[!UICONTROL Timestamp patterns]**
Ange tidsstämpelmönster för ett eller flera språk. Standard är för en, de, fr, it, es, ja, zh_CN, ko_KR.

* **[!UICONTROL Display User]**
Välj antingen 
**`Sender`** eller  **`Recipients`** för att avgöra om avsändaren eller mottagarna ska visas.

### Konfigurera Compose Message {#configuring-compose-message}

Om du vill ändra konfigurationen för den sammansatta meddelandesidan öppnar du webbplatsen i [redigeringsläge](sites-console.md#authoring-site-content).

I `Preview`läge väljer du länken **[!UICONTROL Messages]** för att öppna huvudmeddelandesidan. Klicka sedan på knappen Nytt meddelande för att öppna sidan `Compose Message`.

I `Edit`-läge väljer du huvudkomponenten på sidan som innehåller meddelandetexten.

Om du vill komma åt konfigurationsdialogrutan måste du avbryta arvet genom att välja ikonen `link`.

När konfigurationen är klar måste du återställa arvet genom att välja ikonen `broken link`.

![chlimage_1-400](assets/chlimage_1-400.png)

När arvet har avbrutits går det att välja ikonen `configure` för att öppna konfigurationsdialogrutan.

![chlimage_1-401](assets/chlimage_1-401.png)

#### Fliken Grundläggande {#basic-tab-1}

![chlimage_1-402](assets/chlimage_1-402.png)

* **[!UICONTROL Redirect URL]**
Ange URL-adressen till sidan som visas när meddelandet har skickats. Till exempel, 
`../messaging.html`.

* **[!UICONTROL Cancel URL]**
Ange URL-adressen till sidan som visas om avsändaren avbryter meddelandet. Till exempel, 
`../messaging.html`.

* **[!UICONTROL Maximum length of Message Subject]**
Det maximala antalet tecken som tillåts i fältet Ämne. Till exempel 500. Standard är ingen gräns.

* **[!UICONTROL Maximum length of Message Body]**
Det högsta antalet tecken som tillåts i fältet Innehåll. Exempel: 10000. Standard är ingen gräns.

* **[!UICONTROL Service selector]**
(*Obligatoriskt*) Ange det här till värdet för egenskapen  **`serviceSelector.name`** från  [AEM Communities Messaging Operations Service](messaging.md#messaging-operations-service).

#### Visningsflik {#display-tab-1}

![chlimage_1-403](assets/chlimage_1-403.png)

* **[!UICONTROL Show Subject Field]**
Om du markerar det här alternativet visas 
`Subject` och gör det möjligt att lägga till ett ämne i meddelandet. Standard är inte markerat.

* **[!UICONTROL Subject Label]**
Ange den text som ska visas intill 
`Subject` fält. Standardvärdet är `Subject`.

* **[!UICONTROL Show Attach File Field]**
Om du markerar det här alternativet visas 
`Attachment` och gör det möjligt att lägga till bifogade filer i meddelandet. Standard är inte markerat.

* **[!UICONTROL Attach File Label]**
Ange den text som ska visas intill 
`Attachment` fält. Standardvärdet är **`Attach File`**.

* **[!UICONTROL Show Content Field]**
Om du markerar det här alternativet visas 
`Content` och aktivera tillägg av meddelandetext. Standard är inte markerat.

* **[!UICONTROL Content Label]**
Ange den text som ska visas intill 
`Content` fält. Standardvärdet är **`Body`**.

* **[!UICONTROL With Rich Text Editor]**
Om det här alternativet är markerat används en anpassad innehållstextruta med en egen RTF-redigerare. Standard är inte markerat.

* **[!UICONTROL Timestamp patterns]**
Ange tidsstämpelmönster för ett eller flera språk. Standard är för en, de, fr, it, es, ja, zh_CN, ko_KR.

