---
title: Konfigurerar meddelanden
seo-title: Configuring Messaging
description: Communities messaging
seo-description: Communities messaging
uuid: 35d98667-a82e-4ed1-b6a1-1ffbbe1d08b5
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 5cb571ae-eeb5-4943-a6b8-92e346e85be2
role: Admin
exl-id: 0e906f67-b908-4c41-b243-e4f90100ce5d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 0%

---

# Konfigurerar meddelanden {#configuring-messaging}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Meddelandefunktionen för AEM Communities gör det möjligt för besökare på den inloggade webbplatsen (medlemmar) att skicka meddelanden till varandra som är tillgängliga när de loggar in på webbplatsen.

Meddelanden är aktiverade för en community-webbplats genom att markera en kryssruta under [communitysajt](sites-console.md).

På den här sidan finns information om standardkonfigurationen och eventuella justeringar.

Mer information för utvecklare finns i [Viktiga meddelanden](essentials-messaging.md).

## Tjänsten Meddelandeåtgärder {#messaging-operations-service}

The [Tjänsten AEM Communities Messaging Operations](http://localhost:4502/system/console/configMgr/com.adobe.cq.social.messaging.client.endpoints.impl.MessagingOperationsServiceImpl) identifierar slutpunkten som hanterar meddelanderelaterade begäranden, de mappar som tjänsten ska använda för att lagra meddelanden och, om meddelanden kan innehålla bifogade filer, vilka filtyper som tillåts.

För communitysajter som skapats med [Konsolen Webbplatser i Communities](sites-console.md), finns det redan en instans av tjänsten med inkorgen inställd på `/mail/community/inbox`.

### Tjänsten Community Messaging Operations {#community-messaging-operations-service}

Så som visas nedan finns det en konfiguration för tjänsten för webbplatser som skapats med [guide för att skapa webbplatser](sites-console.md). Du kan visa eller redigera konfigurationen genom att välja pennikonen bredvid konfigurationen:

![chlimage_1-63](assets/chlimage_1-63.png)

### Ny konfiguration {#new-configuration}

Om du vill lägga till en ny konfiguration väljer du plustecknet (+)**+**&#39; bredvid tjänstens namn:

![chlimage_1-64](assets/chlimage_1-64.png)

* **[!UICONTROL Message Fields Allowlist]**
Anger egenskaperna för den Compose Message-komponent som användare kan redigera och behålla. Om nya formulärelement läggs till måste element-ID läggas till om det ska lagras i SRP. Standard är två poster: 
*ämne* och *innehåll*.

* **[!UICONTROL Message box size limit]**
Maximalt antal byte i varje användares meddelanderuta. Standard är 
*1073741824* (1 GB).

* **[!UICONTROL Message count limit]**
Det totala antalet meddelanden som tillåts per användare. Värdet -1 anger att ett obegränsat antal meddelanden tillåts, enligt storleksgränsen för meddelanderutan. Standard är 
*10000* (10 kB).

* **[!UICONTROL Notify delivery failure]**
Om du markerar det här alternativet ska du meddela avsändaren om meddelandeleveransen misslyckas för vissa mottagare. Standard är 
*checked*.

* **[!UICONTROL Failure delivery sender id]**
Namnet på den avsändare som visas i meddelandet som inte kunde levereras. Standard är 
*errorNotifier*.

* **[!UICONTROL Failure message template path]**
Absolut sökväg till leveransmallroten för misslyckade meddelanden. Standard är 
*/etc/notification/messaging/default*.

* **[!UICONTROL maxRetries.name]**
Antal försök att skicka om meddelande som inte kan levereras. Standard är 
*3*.

* **[!UICONTROL minWaitBetweenRetries.name]**
Antal sekunder mellan försök att skicka meddelandet igen om det inte går att skicka. Standardvärdet är *100 *(sekunder).

* **[!UICONTROL Count update pool size]**
Antal samtidiga trådar som används för att räkna uppdatering. Standard är 
*10*.

* **[!UICONTROL inbox.path.name]**
(
*Obligatoriskt*) Sökvägen i förhållande till användarens nod (/home/users/*användarnamn*), för **`inbox`** mapp. Sökvägen får INTE avslutas med ett avslutande snedstreck (/). Standard är */mail/inbox* .

* **[!UICONTROL sentitems.path.name]**
(
*Obligatoriskt*) Sökvägen i förhållande till användarens nod (/home/users/*användarnamn*), för **`senditems`** mapp. Sökvägen får INTE avslutas med ett avslutande snedstreck (/). Standard är */mail/sentitems* .

* **[!UICONTROL supportAttachments.name]**
Om det här alternativet är markerat kan användare lägga till bilagor i sina meddelanden. Standard är 
*checked*.

* **[!UICONTROL batchSize.name]**
Antal meddelanden som ska grupperas tillsammans för en sändning när den skickas till en stor grupp mottagare. Standard är 
*100*.

* **[!UICONTROL maxTotalAttachmentSize.name]**
Om supportAttachments är markerat anger det här värdet den största tillåtna totala storleken (i byte) för alla bilagor. Standard är 
*104857600* (100 MB).

* **[!UICONTROL attachmentTypeBlocklist.name]**
Ett blockeringslista med filtillägg, med &#39;
**.**&#39;, som kommer att refuseras av systemet. Om tillägget inte blocklist tillåts det. Tillägg kan läggas till eller tas bort med **+** och **-** ikoner. Standard är *STANDARD*.

* **[!UICONTROL allowedAttachmentTypes.name]**

   **(*Åtgärd krävs*)** Ett tillåtelselista med filtillägg, motsatsen till blockeringslista. Om du vill tillåta alla filtillägg, förutom de som blocklist, använder du **-**&#39; om du vill ta bort en enskild tom post.

* **[!UICONTROL serviceSelector.name]**
(*Obligatoriskt*) En absolut sökväg (slutpunkt) genom vilken tjänsten anropas (en virtuell resurs). Roten för den valda sökvägen måste vara en som ingår i *Körningsbanor* konfigurationsinställning för OSGi-konfiguration [ `Apache Sling Servlet/Script Resolver and Error Handler`](http://localhost:4502/system/console/configMgr/org.apache.sling.servlets.resolver.SlingServletResolver), till exempel `/bin/`, `/apps/`och `/services/`. Om du vill välja den här konfigurationen för en webbplats meddelandefunktion anges den här slutpunkten som **`Service selector`** värdet för `Message List and Compose Message components` (se [Meddelandefunktion](configure-messaging.md)). Standardvärdet är */bin/messaging* .

* **[!UICONTROL fieldAllowlist.name]**
Använd 
**Meddelandefält Tillåtslista**.

>[!CAUTION]
>
>Varje gång `Messaging Operations Service` konfigurationen öppnas för redigering, om `allowedAttachmentTypes.name` har tagits bort, läggs en tom post till på nytt så att egenskapen kan konfigureras. En enda tom post inaktiverar effektivt bifogade filer.
>
>Om du vill tillåta alla filtillägg, förutom de som blocklist, använder du **-**&#39; om du vill (igen) ta bort en enskild tom post innan du klickar på **[!UICONTROL Save]**.

## Felsökning {#troubleshooting}

Ett sätt att felsöka problem är att aktivera [felsökningsmeddelanden i loggen.](../../help/sites-administering/troubleshooting.md)

Se även [Loggare och skribenter för enskilda tjänster](../../help/sites-deploying/configure-logging.md#loggers-and-writers-for-individual-services).

Paketet som ska övervakas är `com.adobe.cq.social.messaging`.
