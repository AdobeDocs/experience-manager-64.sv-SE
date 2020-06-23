---
title: Konfigurerar meddelanden
seo-title: Konfigurerar meddelanden
description: Communities messaging
seo-description: Communities messaging
uuid: 35d98667-a82e-4ed1-b6a1-1ffbbe1d08b5
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 5cb571ae-eeb5-4943-a6b8-92e346e85be2
translation-type: tm+mt
source-git-commit: 9fa89ca34843d41a5ab5711c1090fcc7a1077760
workflow-type: tm+mt
source-wordcount: '688'
ht-degree: 0%

---


# Konfigurerar meddelanden {#configuring-messaging}

## Översikt {#overview}

Meddelandefunktionen för AEM Communities ger möjlighet för inloggade webbplatsbesökare (medlemmar) att skicka meddelanden till varandra som är tillgängliga när de loggar in på webbplatsen.

Meddelanden aktiveras för en community-webbplats genom att en kryssruta markeras när en [community-webbplats skapas](sites-console.md).

På den här sidan finns information om standardkonfigurationen och eventuella justeringar.

Mer information för utvecklare finns i [Messaging Essentials](essentials-messaging.md).

## Tjänsten Meddelandeåtgärder {#messaging-operations-service}

Tjänsten [](http://localhost:4502/system/console/configMgr/com.adobe.cq.social.messaging.client.endpoints.impl.MessagingOperationsServiceImpl) AEM Communities Messaging Operations identifierar slutpunkten som hanterar meddelanderelaterade begäranden, de mappar som tjänsten ska använda för att lagra meddelanden och, om meddelanden kan innehålla bifogade filer, vilka filtyper som tillåts.

För communitysajter som skapats med konsolen [Webbplatser i](sites-console.md)Communities finns redan en instans av tjänsten med inkorgen inställd på `/mail/community/inbox`.

### Tjänsten Community Messaging Operations {#community-messaging-operations-service}

Så som visas nedan finns det en konfiguration av tjänsten för webbplatser som skapats med guiden [Skapa](sites-console.md)plats. Du kan visa eller redigera konfigurationen genom att välja pennikonen bredvid konfigurationen:

![chlimage_1-63](assets/chlimage_1-63.png)

### Ny konfiguration {#new-configuration}

Om du vill lägga till en ny konfiguration väljer du plusikonen &quot;**+**&quot; bredvid tjänstens namn:

![chlimage_1-64](assets/chlimage_1-64.png)

* **[!UICONTROL Message Fields Allowlist]**
Anger egenskaperna för den Compose Message-komponent som användare kan redigera och behålla. Om nya formulärelement läggs till måste element-ID läggas till om det ska lagras i SRP. Standard är två poster: *ämne* och *innehåll*.

* **[!UICONTROL Message box size limit]**
Maximalt antal byte i varje användares meddelanderuta. Standardvärdet är *1073741824* (1 GB).

* **[!UICONTROL Message count limit]**
Det totala antalet meddelanden som tillåts per användare. Värdet -1 anger att ett obegränsat antal meddelanden tillåts, enligt storleksgränsen för meddelanderutan. Standardvärdet är *1000* (10 kB).

* **[!UICONTROL Notify delivery failure]**
Om du markerar det här alternativet ska du meddela avsändaren om meddelandeleveransen misslyckas för vissa mottagare. Standard är *markerat*.

* **[!UICONTROL Failure delivery sender id]**
Namnet på den avsändare som visas i meddelandet som inte kunde levereras. Standardvärdet är *errorNotifier*.

* **[!UICONTROL Failure message template path]**
Absolut sökväg till leveransmallroten för misslyckade meddelanden. Standard är */etc/notification/messaging/default*.

* **[!UICONTROL maxRetries.name]**
Antal försök att skicka om meddelande som inte kan levereras. Standardvärdet är *3*.

* **[!UICONTROL minWaitBetweenRetries.name]**
Antal sekunder mellan försök att skicka meddelandet igen om det inte går att skicka. Standardvärdet är *100 *(sekunder).

* **[!UICONTROL Count update pool size]**
Antal samtidiga trådar som används för att räkna uppdatering. Standardvärdet är *10*.

* **[!UICONTROL inbox.path.name]**
(*Obligatoriskt*) Sökvägen, i förhållande till användarens nod (/home/users/*username*), som ska användas för **`inbox`** mappen. Sökvägen får INTE avslutas med ett avslutande snedstreck (/). Standard är */e-post/inkorg* .

* **[!UICONTROL sentitems.path.name]**
(*Obligatoriskt*) Sökvägen, i förhållande till användarens nod (/home/users/*username*), som ska användas för **`senditems`** mappen. Sökvägen får INTE avslutas med ett avslutande snedstreck (/). Standardvärdet är */mail/sentists* .

* **[!UICONTROL supportAttachments.name]**
Om det här alternativet är markerat kan användare lägga till bilagor i sina meddelanden. Standard är *markerat*.

* **[!UICONTROL batchSize.name]**
Antal meddelanden som ska grupperas tillsammans för en sändning när den skickas till en stor grupp mottagare. Standardvärdet är *100*.

* **[!UICONTROL maxTotalAttachmentSize.name]**
Om supportAttachments är markerat anger det här värdet den största tillåtna totala storleken (i byte) för alla bilagor. Standardvärdet är *104857600* (100 MB).

* **[!UICONTROL attachmentTypeBlocklist.name]**
En blocklista med filtillägg, prefix med &#39;**.**&#39;, som kommer att refuseras av systemet. Om det inte blockeras tillåts tillägget. Tillägg kan läggas till eller tas bort med ikonerna **+** och **-**. Standard är *STANDARD*.

* **[!UICONTROL allowedAttachmentTypes.name]**
   **(*Åtgärd krävs*)** En lista över filtillägg, motsatsen till blocklistan. Om du vill tillåta alla filtillägg, förutom de som är blocklistade, använder du ikonen &quot;**-**&quot; för att ta bort den tomma posten.

* **[!UICONTROL serviceSelector.name]**
(*Obligatoriskt*) En absolut sökväg (slutpunkt) genom vilken tjänsten anropas (en virtuell resurs). Roten för den valda sökvägen måste vara en som ingår i konfigurationsinställningen för *körningssökvägar* i OSGi-konfigurationen [ `Apache Sling Servlet/Script Resolver and Error Handler`](http://localhost:4502/system/console/configMgr/org.apache.sling.servlets.resolver.SlingServletResolver)som `/bin/`, `/apps/`och `/services/`. Om du vill välja den här konfigurationen för en webbplats meddelandefunktion anges den här slutpunkten som **`Service selector`** värde för `Message List and Compose Message components` (se [Meddelandefunktion](configure-messaging.md)). Standardvärdet är */bin/messaging* .

* **[!UICONTROL fieldAllowlist.name]**
Använd listan Tillåtna **meddelandefält**.

>[!CAUTION]
>
>Varje gång en `Messaging Operations Service` konfiguration öppnas för redigering, om den `allowedAttachmentTypes.name` tagits bort, läggs en tom post till så att egenskapen kan konfigureras. En enda tom post inaktiverar effektivt bifogade filer.
>
>Om du vill tillåta alla filtillägg, förutom de som är blocklistade, använder du ikonen &quot;**-**&quot; för att (en gång till) ta bort den tomma posten innan du klickar **[!UICONTROL Save]**.

## Felsökning {#troubleshooting}

Ett sätt att felsöka problem är att aktivera [felsökningsmeddelanden i loggen.](../../help/sites-administering/troubleshooting.md)

Se även [Loggare and Writers for Individual Services](../../help/sites-deploying/configure-logging.md#loggers-and-writers-for-individual-services).

Paketet som ska övervakas är `com.adobe.cq.social.messaging`.
