---
title: Asynkron inlämning av adaptiva formulär
seo-title: Asynchronous submission of adaptive forms
description: Lär dig att konfigurera asynkron överföring för adaptiva formulär.
seo-description: Learn to configure asynchronous submission for adaptive forms.
uuid: 3b8aeac8-cb38-4a2b-8375-556b2736d58b
contentOwner: vishgupt
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 6e4e3af5-4260-4f38-9b29-0818e92bc182
feature: Adaptive Forms
exl-id: 1ca492e9-9832-4e5d-8020-2690ac4f5505
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '663'
ht-degree: 0%

---

# Asynkron inlämning av adaptiva formulär {#asynchronous-submission-of-adaptive-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Som standard är webbformulär konfigurerade att skicka synkront. När användare skickar ett formulär omdirigeras de till en bekräftelsesida, eller en felsida om överföringen misslyckas. Moderna webbupplevelser som single page-applikationer blir dock allt populärare där webbsidan är statisk medan klient-server-interaktion sker i bakgrunden. Du kan nu ge den här upplevelsen tillgång till adaptiva formulär genom att konfigurera asynkron överföring. I det här fallet fungerar ett anpassat formulär som ett program med en sida eftersom formuläret inte läses in igen eller dess URL inte ändras när de skickade formulärdata valideras på servern.

Läs vidare för mer information om asynkron överföring i adaptiva formulär.

## Konfigurera asynkron överföring {#configure}

Så här konfigurerar du asynkron sändning för ett anpassat formulär:

1. I redigeringsläget för anpassningsbara formulär väljer du objektet Formulärbehållare och trycker på ![cmppr1](assets/cmppr1.png) för att öppna dess egenskaper.
1. I **[!UICONTROL Submission]** egenskapsavsnittet, aktivera **[!UICONTROL Use asynchronous submission]**.
1. I **[!UICONTROL On Submit]** väljer du något av följande alternativ när formuläret har skickats.

   * **[!UICONTROL Redirect to URL]**: Omdirigerar till angiven URL eller sida när formulär skickas. Du kan ange en URL-adress eller bläddra för att välja sökvägen till en sida i dialogrutan **[!UICONTROL Redirect URL/Path]** fält.
   * **[!UICONTROL Show Message]**: Visar ett meddelande om att formulär har skickats. Du kan skriva ett meddelande i textfältet under alternativet Visa meddelande. Textfältet har stöd för RTF-formatering.

1. Tryck ![check-button1](assets/check-button1.png) för att spara egenskaperna.

## Hur asynkron inlämning fungerar {#how-asynchronous-submission-works}

AEM Forms har färdiga funktioner och felhanterare för att skicka in formulär. Hanterare är funktioner på klientsidan som körs baserat på serversvaret. När ett formulär skickas skickas data till servern för validering, som returnerar ett svar till klienten med information om om huruvida överföringen lyckades eller inte. Informationen skickas som parametrar till den relevanta hanteraren för att köra funktionen.

Dessutom kan formulärförfattare och utvecklare skriva regler på formulärnivå för att åsidosätta standardhanterare. Mer information finns i [Åsidosätta standardhanterare med regler](#custom).

Låt oss först granska serversvaret för att se om det har lyckats eller inte.

### Serversvar för lyckad sändning {#server-response-for-submission-success-event}

Strukturen för serversvaret för händelsen att överföringen lyckades är följande:

```
{
  contentType : "<xmlschema or jsonschema>", 
  data : "<dataXML or dataJson>" , 
  thankYouOption : <page/message>, 
  thankYouContent : "<thank you page url/thank you message>"
}
```

Serversvaret vid lyckad formulärsändning innehåller:

* Typ av formulärdataformat: XML eller JSON
* Formulärdata i XML- eller JSON-format
* Markerat alternativ för omdirigering till en sida eller för att visa ett meddelande som konfigurerats i formuläret
* Sidans URL- eller meddelandeinnehåll som konfigurerats i formuläret

Hanteraren för lyckade åtgärder läser serversvaret och dirigerar därför om till den konfigurerade sidans URL eller visar ett meddelande.

### Serversvar för en felhändelse för överföring {#server-response-for-submission-error-event}

Strukturen för serversvaret för en felhändelse vid överföring är följande:

```
{
   errorCausedBy : "<CAPTCHA_VALIDATION or SERVER_SIDE_VALIDATION>",

   errors : [
               { "somExpression" : "<SOM Expression>",
                 "errorMessage"  : "<Error Message>"
               },
               ...
             ]
 }
```

Serversvaret vid fel när formulär skickas innehåller:

* Orsak till felet, misslyckades med CAPTCHA eller validering på serversidan
* Lista över felobjekt, som innehåller SOM-uttrycket för fältet som inte kunde valideras och motsvarande felmeddelande

Felhanteraren läser serversvaret och visar därför felmeddelandet i formuläret.

## Åsidosätta standardhanterare med regler {#custom}

Formulärutvecklare och författare kan skriva regler på formulärnivå i kodredigeraren för att åsidosätta standardhanterare. Serversvaret för lyckade händelser och felhändelser visas på formulärnivå, som utvecklare kan komma åt med `$event.data` i regler.

Utför följande steg för att skriva regler i kodredigeraren för att hantera lyckade händelser och felhändelser.

1. Öppna det adaptiva formuläret i redigeringsläge, markera ett formulärobjekt och tryck på ![edit-rules1](assets/edit-rules1.png) för att öppna regelredigeraren.
1. Välj **[!UICONTROL Form]** i trädet Formulärobjekt och tryck på **[!UICONTROL Create]**.
1. Välj **[!UICONTROL Code Editor]** i listrutan för lägesval.
1. Tryck på i kodredigeraren **[!UICONTROL Edit Code]**. Tryck **[!UICONTROL Edit]** i bekräftelsedialogrutan.
1. Välj **[!UICONTROL Successful Submission]** eller **[!UICONTROL Error in Submission]** från **[!UICONTROL Event]** nedrullningsbar meny.
1. Skriv en regel för den valda händelsen och tryck på **[!UICONTROL Done]** för att spara regeln.
