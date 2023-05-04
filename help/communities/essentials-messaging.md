---
title: Viktiga meddelanden
seo-title: Messaging Essentials
description: Översikt över meddelandekomponenten
seo-description: Messaging component overview
uuid: 53711f4d-6bbc-4be9-aefe-4e75a81cd67f
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: eb8fd2b3-0a31-425e-b0f1-38f09e1106df
exl-id: c6ad3c2b-8776-4ec4-99da-ab73ecc61153
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 1%

---

# Viktiga meddelanden {#messaging-essentials}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

På den här sidan visas information om hur du arbetar med att använda meddelandekomponenten för att inkludera en meddelandefunktion på en webbplats.

## Grundläggande för klientsidan {#essentials-for-client-side}

**Skriv meddelande**

<table> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td><p>social/messaging/components/hbs/composemage</p> </td> 
  </tr> 
  <tr> 
   <td> <a href="client-customize.md#clientlibs-for-scf"><strong>klientlibs</strong></a></td> 
   <td><p>cq.social.hbs.messaging</p> </td> 
  </tr> 
  <tr> 
   <td> <strong>mallar</strong></td> 
   <td>/libs/social/messaging/components/hbs/composemessage/composemessage.hbs</td> 
  </tr> 
  <tr> 
   <td><strong>css</strong></td> 
   <td>/libs/social/messaging/components/hbs/composemessage/clientlibs/composemessage.css</td> 
  </tr> 
  <tr> 
   <td><strong>egenskaper</strong></td> 
   <td>se <a href="configure-messaging.md">Konfigurerar meddelanden</a></td> 
  </tr> 
  <tr> 
   <td><strong>administratörskonfiguration</strong></td> 
   <td><a href="messaging.md">Konfigurerar meddelanden</a></td> 
  </tr> 
 </tbody> 
</table>

**Meddelandelista** (för Inkorgen, Skickat och Papperskorgen)

<table> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td><p>social/messaging/components/hbs/messagebox</p> </td> 
  </tr> 
  <tr> 
   <td> <a href="client-customize.md#clientlibs-for-scf"><strong>klientlibs</strong></a></td> 
   <td><p>cq.social.hbs.messaging</p> </td> 
  </tr> 
  <tr> 
   <td> <strong>mallar</strong></td> 
   <td>/libs/social/messaging/components/hbs/messagebox/messagebox.hbs</td> 
  </tr> 
  <tr> 
   <td><strong>css</strong></td> 
   <td>/libs/social/messaging/components/hbs/messagebox/clientlibs/messagebox.css</td> 
  </tr> 
  <tr> 
   <td><strong>egenskaper</strong></td> 
   <td>Se <a href="configure-messaging.md">Konfigurerar meddelanden</a></td> 
  </tr> 
  <tr> 
   <td><strong>administratörskonfiguration</strong></td> 
   <td><a href="messaging.md">Konfigurerar meddelanden</a></td> 
  </tr> 
 </tbody> 
</table>

Se även [Anpassningar på klientsidan](client-customize.md)

## Grundläggande för serversidan {#essentials-for-server-side}

* [Konfigurerar meddelanden](configure-messaging.md)

* [Meddelandeklient-API:er](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/client/api/package-summary.html) för SCF-komponenter

* [MeddelandeAPI:er](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/api/package-summary.html) för tjänsten

* [Meddelandeslutpunkter](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/messaging/client/endpoints/package-summary.html)

* [Anpassningar på serversidan](server-customize.md)

>[!CAUTION]
>
>String-parametern får inte *innehålla ett avslutande snedstreck (/) för följande MessageBuilder-metoder:
>
>* `setInboxPath`()
>* `setSentItemsPath`()
>
>Till exempel:
>
>
```
>valid: mb.setInboxPath( "/mail/inbox" );
> not valid: mb.setInboxPath( "/mail/inbox/" );
>```

### Community-webbplats {#community-site}

En community-webbplatsstruktur som skapats med guiden innehåller meddelandefunktionen när den väljs. Se `User Management` inställningar för [Konsolen Community Sites](sites-console.md#user-management).

### Exempelkod: Meddelande mottaget {#sample-code-message-received-notification}

Funktionen för sociala meddelanden genererar händelser för åtgärder, till exempel `send`, `marking read`, `marking delete`. Dessa händelser kan fångas upp och åtgärder vidtas utifrån data i händelsen.

Följande exempel är en händelsehanterare som lyssnar efter `message sent` -händelsen och skickar ett e-postmeddelande till alla meddelandemottagare som använder `Day CQ Mail Service`.

Om du vill testa exempelskriptet på serversidan behöver du en utvecklingsmiljö och möjlighet att skapa ett OSGi-paket.

1. Logga in som administratör för att ` [CRXDE|Lite](http://localhost:4502/crx/de)`
1. Skapa en `bundle node`in `/apps/engage/install` med godtyckliga namn, som

   * **[!UICONTROL Symbolic Name]**: com.engage.media.social.messaging.MessagingNotification
   * **[!UICONTROL Name]**: Komma igång - meddelande om självstudiekurser
   * **[!UICONTROL Description]**: en exempeltjänst för att skicka ett e-postmeddelande till användare när de får ett meddelande
   * **[!UICONTROL Package]**: `com.engage.media.social.messaging.notification`

1. Navigera till `/apps/engage/install/com.engage.media.social.messaging.MessagingNotification/src/main/java/com/engage/media/social/messaging/notification`

   1. Ta bort `Activator.java` klass skapas automatiskt
   1. Skapa klass `MessageEventHandler.java`
   1. Kopiera/klistra in koden nedan i `MessageEventHandler.java`

1. Klicka på **[!UICONTROL Save All]**
1. Navigera till `/apps/engage/install/com.engage.media.social.messaging.MessagingNotification/com.engage.media.social.messaging.MessagingNotification.bnd` och lägga till alla import-satser som de är skrivna i `MessageEventHandler.java` kod.
1. Bygg paketet
1. Säkerställ `Day CQ Mail Service`OSGi-tjänsten är konfigurerad
1. Logga in som en demoanvändare och skicka e-post till en annan
1. Mottagaren bör få ett e-postmeddelande om ett nytt meddelande

#### MessageEventHandler.java {#messageeventhandler-java}

```java
package com.engage.media.social.messaging.notification;

import org.apache.felix.scr.annotations.Component;
import org.apache.felix.scr.annotations.Properties;
import org.apache.felix.scr.annotations.Property;
import org.apache.felix.scr.annotations.Service;
import org.apache.felix.scr.annotations.Reference;
import org.apache.sling.api.resource.ResourceResolver;
import org.apache.sling.api.resource.ResourceResolverFactory;
import org.apache.sling.api.resource.Resource;
import org.apache.commons.mail.Email;
import org.apache.commons.mail.EmailException;
import org.apache.commons.mail.SimpleEmail;
import org.apache.commons.mail.HtmlEmail;
import java.util.List;
import org.osgi.service.event.Event;
import org.osgi.service.event.EventHandler;
import org.slf4j.Logger;
import org.slf4j.LoggerFactory;
import com.adobe.cq.social.messaging.api.Message;
import com.adobe.cq.social.messaging.api.MessagingEvent;
import com.day.cq.mailer.MessageGatewayService;
import com.day.cq.mailer.MessageGateway;

@Component(immediate=true)
@Service(EventHandler.class)
@Properties({
        @Property(name = "event.topics", value = "com/adobe/cq/social/message")
})
public class MessagingEventHandler implements EventHandler {
    private Logger logger = LoggerFactory.getLogger(MessagingEventHandler.class);

    @Reference
    ResourceResolverFactory resourceResolverFactory;

    @Reference
    private MessageGatewayService messageGatewayService;

    ResourceResolver resourceResolver=null;
    MessageGateway messageGateway=null;

    public void sendMail(String from, String to,String subject, String content){
        Email email = new SimpleEmail();
        messageGateway = messageGatewayService.getGateway(SimpleEmail.class);
        try {
         email.addTo(to);
            email.addReplyTo(from);
            email.setFrom(from);
            email.setMsg(content);
            email.setSubject(subject);
         messageGateway.send(email);
        } catch(EmailException ex) {
            logger.error("MessageNotificaiton : Error sending email : "+ex.getMessage());
        }
        logger.info("**** MessageNotification **** Mail sent to " + to);
    }

    public void handleEvent(Event event) {
        //Get Message Path and originator User's ID from event
        String messagePath = (String) event.getProperty("path");
        String senderId = (String) event.getProperty("userId");
        MessagingEvent.MessagingActions action = (MessagingEvent.MessagingActions) event.getProperty("action");
        try{
            if(MessagingEvent.MessagingActions.MessageSent.equals(action)){
                resourceResolver = resourceResolverFactory.getAdministrativeResourceResolver(null);

                //Read message
                Resource resource = resourceResolver.getResource(messagePath);
                Message msg = resource.adaptTo(Message.class);

                //Get list of recipient Ids from message
                //For Getting Started Tutorial, Id is same as email. If that is not the case in your site, 
                //an additional step is needed to retrieve the email for the Id
                List<String> reclist = msg.getRecipientIdList();
                for(int i=0;i<reclist.size();i++){
                    //Send Email using Mailing Service
                    sendMail("admin@cqadmin.qqq",reclist.get(i),"New message on Getting Started Tutorial", "Hi\nYou have received a new message from  " +  senderId + ". To read it, sign in to Getting Started Tutorial.\n\n-Engage Admin");
                }
            }
        } catch(Exception ex){
            logger.error("Error getting message info : " + ex.getMessage());
        } finally {
            resourceResolver.close();
        }

    }
}
```
