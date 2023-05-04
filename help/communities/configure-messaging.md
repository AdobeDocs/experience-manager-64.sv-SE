---
title: Meddelandefunktion
seo-title: Messaging Feature
description: Konfigurera meddelandekomponenter
seo-description: Configuring Messaging components
uuid: 29ab63b6-67a1-4eb8-8cf8-c1ff52ff2bac
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 88ee8573-58c4-42cd-8e36-2ea4a0d654e4
exl-id: e03cf05c-2469-4883-ae7b-9d7e6660b71f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 1%

---

# Meddelandefunktion {#messaging-feature}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Förutom de synliga interaktionerna som förekommer i forum och i kommentarer gör meddelandefunktionen i AEM Communities det möjligt för communitymedlemmar att interagera med varandra mer privat.

Den här funktionen kan ingå när en [communitywebbplats](overview.md#communitiessites) skapas.

Med meddelandefunktionerna kan du:

* Skicka ett meddelande till en eller flera community-medlemmar
* Skicka ett meddelande till en community-medlemsgrupp
* Skicka ett meddelande med bilagor
* Vidarebefordra ett meddelande
* Svara på ett meddelande
* Ta bort ett meddelande
* Återställa ett borttaget meddelande

Om du vill aktivera och ändra meddelandefunktionen går du till

* [Konfigurerar meddelanden](messaging.md) för administratörer
* [Viktiga meddelanden](essentials-messaging.md) för utvecklare

>[!NOTE]
>
>Det går inte att lägga till `Compose Message, Message, or Message List` komponenter (finns i `Communities`till en sida i redigeringsläge.

## Konfigurerar meddelandekomponenter {#configuring-messaging-components}

När meddelanden är aktiverat för en community-webbplats är det helt konfigurerat utan någon ytterligare konfiguration. Den här informationen tillhandahålls om du behöver ändra standardkonfigurationen.

### Konfigurera meddelandelista (meddelanderuta) {#configuring-message-list-messagebox}

För att ändra konfigurationen av meddelandelistan för **Inkorg**, **Skickade objekt** och **Papperskorgen** sidor med meddelandefunktionen, öppna webbplatsen i [redigeringsläge för författare](sites-console.md#authoring-site-content).

I `Preview` läge, välj **[!UICONTROL Messages]** för att öppna meddelandesidan. Välj sedan antingen **[!UICONTROL Inbox, Sent Items, or Trash]** för att konfigurera komponenten för den meddelandelistan.

I `Edit` markerar du komponenten på sidan.

Om du vill komma åt konfigurationsdialogrutan måste du avbryta arv genom att välja `link`ikon.

När konfigurationen är klar måste du återställa arvet genom att välja `broken link` ikon.

![chlimage_1-396](assets/chlimage_1-396.png)

När arvet har avbrutits går det att välja `configure` -ikonen för att öppna konfigurationsdialogrutan.

![chlimage_1-397](assets/chlimage_1-397.png)

#### Fliken Grundläggande {#basic-tab}

![chlimage_1-398](assets/chlimage_1-398.png)

* **[!UICONTROL Service selector]**
(*Obligatoriskt*) Ange värdet för egenskapen `serviceSelector.name` från [Tjänsten AEM Communities Messaging Operations](messaging.md#messaging-operations-service).

* **[!UICONTROL Compose Page]**
(*Obligatoriskt*) Den sida som ska öppnas när en medlem klickar på `Reply` -knappen. Målsidan ska innehålla **[!UICONTROL Compose Message]** formulär.

* **[!UICONTROL Reply/View as Resource]**
Om det här alternativet är markerat refererar URL:en för svar och vy till en resurs, annars skickas data som frågeparametrar i URL:en.

* **[!UICONTROL Profile Display Form]**
Det profilformulär som ska användas för att visa avsändarprofilen.

* **[!UICONTROL Trash Folder]**
Om den här meddelandelistekomponenten är markerad visas endast meddelanden som har flaggats som borttagna (papperskorg).

* **[!UICONTROL Folder Paths]**
(*Obligatoriskt*) Referera till de värden som angetts för `inbox.path.name` och `sentitems.path.name` i [Tjänsten AEM Communities Messaging Operations](messaging.md#messaging-operations-service). Vid konfigurering för en `Inbox`, lägger till en post med värdet för `inbox.path.name`. Vid konfigurering för en `Outbox`, lägger till en post med värdet för `sentitems.path.name`. Vid konfigurering för `Trash`lägger du till två poster med båda värdena.

#### Fliken Visa {#display-tab}

![chlimage_1-399](assets/chlimage_1-399.png)

* **[!UICONTROL Mark Read Button]**
Om det här alternativet är markerat visas en 
`Read`så att ett meddelande kan markeras som läst.

* **[!UICONTROL Mark Unread Button]**
Om det här alternativet är markerat visas en 
`Mark Unread` så att ett meddelande kan markeras som läst.

* **[!UICONTROL Delete Button]**
Om det här alternativet är markerat visas en 
`Delete`så att ett meddelande kan markeras som läst. Duplicerar borttagningsfunktionen om **`Message Options`** också markeras.

* **[!UICONTROL Message Options]**
Om det här alternativet är markerat visas 
**`Reply`**, **`Reply All`**, **`Forward`** och **`Delete`** -knappar som gör att ett meddelande kan skickas igen eller tas bort. Duplicerar borttagningsfunktionen om **`Delete Button`** också markeras.

* **[!UICONTROL Messages Per Page]**
Det angivna antalet är det högsta antalet meddelanden som visas per sida i ett sidnumreringsschema. Om inget tal anges (vänster tomt) visas alla meddelanden och ingen sidnumrering visas.

* **[!UICONTROL Timestamp patterns]**
Ange tidsstämpelmönster för ett eller flera språk. Standard är för en, de, fr, it, es, ja, zh_CN, ko_KR.

* **[!UICONTROL Display User]**
Välj antingen 
**`Sender`** eller **`Recipients`** för att avgöra om avsändaren eller mottagarna ska visas.

### Konfigurera Compose Message {#configuring-compose-message}

Om du vill ändra konfigurationen för den sammansatta meddelandesidan öppnar du webbplatsen i [redigeringsläge för författare](sites-console.md#authoring-site-content).

I `Preview`läge, välj **[!UICONTROL Messages]** för att öppna meddelandesidan. Klicka sedan på knappen Nytt meddelande för att öppna dialogrutan `Compose Message` sida..

I `Edit` markerar du huvudkomponenten på sidan som innehåller meddelandetexten.

Om du vill komma åt konfigurationsdialogrutan måste du avbryta arv genom att välja `link`ikon.

När konfigurationen är klar måste du återställa arvet genom att välja `broken link` ikon.

![chlimage_1-400](assets/chlimage_1-400.png)

När arvet har avbrutits går det att välja `configure` -ikonen för att öppna konfigurationsdialogrutan.

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
(*Obligatoriskt*) Ange värdet för egenskapen **`serviceSelector.name`** från [Tjänsten AEM Communities Messaging Operations](messaging.md#messaging-operations-service).

#### Fliken Visa {#display-tab-1}

![chlimage_1-403](assets/chlimage_1-403.png)

* **[!UICONTROL Show Subject Field]**
Om du markerar det här alternativet visas 
`Subject` och gör det möjligt att lägga till ett ämne i meddelandet. Standard är inte markerat.

* **[!UICONTROL Subject Label]**
Ange den text som ska visas intill 
`Subject` fält. Standard är `Subject`.

* **[!UICONTROL Show Attach File Field]**
Om du markerar det här alternativet visas 
`Attachment` och gör det möjligt att lägga till bifogade filer i meddelandet. Standard är inte markerat.

* **[!UICONTROL Attach File Label]**
Ange den text som ska visas intill 
`Attachment` fält. Standard är **`Attach File`**.

* **[!UICONTROL Show Content Field]**
Om du markerar det här alternativet visas 
`Content` och aktivera tillägg av meddelandetext. Standard är inte markerat.

* **[!UICONTROL Content Label]**
Ange den text som ska visas intill 
`Content` fält. Standard är **`Body`**.

* **[!UICONTROL With Rich Text Editor]**
Om det här alternativet är markerat används en anpassad innehållstextruta med en egen RTF-redigerare. Standard är inte markerat.

* **[!UICONTROL Timestamp patterns]**
Ange tidsstämpelmönster för ett eller flera språk. Standard är för en, de, fr, it, es, ja, zh_CN, ko_KR.
