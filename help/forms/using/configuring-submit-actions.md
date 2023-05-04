---
title: Konfigurera åtgärden Skicka
seo-title: Configuring the Submit action
description: Med AEM Forms kan du konfigurera en skicka-åtgärd för att definiera hur ett anpassat formulär ska bearbetas när det har skickats in. Du kan använda inbyggda skicka-åtgärder eller skriva egna från grunden.
seo-description: AEM Forms allows you to configure a submit action to define how an adaptive form is processed after submission. You can use built-in submit actions or write your own from scratch.
uuid: aa261e65-a1ec-402b-80de-0ba8a294e315
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: fea76f90-22d5-4836-9901-a35229401eb0
feature: Adaptive Forms
exl-id: 2a842bdc-6dcf-42cc-9a45-57ac15b79eb7
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1504'
ht-degree: 0%

---

# Konfigurera åtgärden Skicka {#configuring-the-submit-action}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion till att skicka åtgärder {#introduction-to-submit-actions}

En sändningsåtgärd utlöses när en användare klickar på knappen Skicka i ett anpassat formulär. Du kan konfigurera åtgärden skicka i anpassningsbara formulär. Med adaptiva formulär kan du skicka in ett antal åtgärder direkt. Du kan kopiera och utöka standardåtgärderna för att skicka och skapa en egen sändningsåtgärd. Baserat på dina krav kan du dock skriva och registrera en egen skicka-åtgärd för att bearbeta data i det skickade formuläret.

När ett formulär är förifyllt eller skickat slussas inskickade data via AEM för datamassning till mellanliggande format. Data sparas inte på en AEM, förutom när det adaptiva formuläret använder Acrobat Sign, verifiera, formulärportalutkast eller skicka-AEM

Du kan konfigurera en skicka-åtgärd i **[!UICONTROL Submission]** i egenskaperna för den adaptiva formulärbehållaren i sidlisten.

![Konfigurera Skicka-åtgärd](assets/thank-you-setting.png)
**Bild:** *Konfigurera Skicka-åtgärd*

Standardåtgärderna för att skicka in anpassningsbara formulär är:

* Skicka till REST-slutpunkt
* Skicka e-post
* Skicka PDF via e-post
* Anropa en Forms Workflow
* Skicka med formulärdatamodell
* Forms Portal Submit Action
* Anropa ett AEM arbetsflöde

>[!NOTE]
>
>Åtgärden Skicka PDF via e-post gäller endast för adaptiva formulär som använder XFA-mall som formulärmodell.

>[!NOTE]
>
>Se till att [AEM_Installation_Directory]\crx-quickstart\temp\datamanager\ASM folder exists. Katalogen krävs för att temporärt lagra bilagor. Om katalogen inte finns skapar du den.

>[!CAUTION]
>
>Om du [prefill](/help/forms/using/prepopulate-adaptive-form-fields.md) en formulärmall, formulärdatamodell eller schemabaserad adaptiv form med XML- eller JSON-data som klagomål till ett schema (XML-schema, JSON-schema, formulärmall eller formulärdatamodell) som inte innehåller data &lt;afdata>, &lt;afbounddata>och &lt;/afunbounddata> taggar, så är data i oavgränsade fält (oavgränsade fält) adaptiva formulärfält utan [bindref](/help/forms/using/prepopulate-adaptive-form-fields.md) egenskap) för det adaptiva formuläret har gått förlorat.

Du kan skriva en anpassad skicka-åtgärd för anpassade formulär för att uppfylla ditt användningssätt. Mer information finns i [Skriva anpassad skickaåtgärd för anpassningsbara formulär](/help/forms/using/custom-submit-action-form.md).

## Skicka till REST-slutpunkt {#submit-to-rest-endpoint}

The **[!UICONTROL Submit to REST endpoint]** Skicka-alternativet skickar data som fylls i formuläret till en konfigurerad bekräftelsesida som en del av HTTP GET-begäran. Du kan lägga till namnet på fälten som ska begäras. Begäran har följande format:

`{fieldName}={request parameter name}`

Som visas i bilden nedan `param1` och `param2` skickas som parametrar med värden som kopierats från **[!UICONTROL textbox]** och **[!UICONTROL numericbox]** fält för nästa åtgärd.

Du kan också **[!UICONTROL Enable POST request]** och ange en URL för att skicka begäran. Om du vill skicka data till den AEM servern som är värd för formuläret använder du en relativ sökväg som motsvarar rotsökvägen för AEM. Exempel: /content/forms/af/SampleForm.html. Om du vill skicka data till en annan server använder du den absoluta sökvägen.

![Konfigurerar åtgärden Skicka för resterande slutpunkt](assets/action-config.png)

Konfigurerar åtgärden Skicka för resterande slutpunkt

>[!NOTE]
Om du vill skicka fälten som parametrar i en REST-URL måste alla fält ha olika elementnamn, även om fälten placeras på olika paneler.

### Bokför skickade data till en resurs eller extern slutpunkt för vila  {#post-submitted-data-to-a-resource-or-external-rest-end-point-nbsp}

Använd **[!UICONTROL Submit to REST Endpoint]** åtgärd för att skicka skickade data till en rest-URL. URL:en kan vara en intern (servern som formuläret återges på) eller en extern server.

Om du vill skicka data till en intern server anger du sökvägen till resursen. Data bokförs som resurssökväg. Till exempel /content/restEndPoint. För sådana efterfrågningar används autentiseringsinformationen i förfrågan.

Ange en URL om du vill skicka data till en extern server. URL-adressen har formatet https:// host:port/path_to_rest_end_point. Se till att du konfigurerar sökvägen så att den hanterar POSTENS begäran anonymt.

![Mappning för fältvärden skickas som Tack-sidan-parametrar](assets/post-enabled-actionconfig.png)

I exemplet ovan har användaren angett information i `textbox` hämtas med parameter `param1`. Syntax för att bokföra data som samlats in med `param1` är:

`String data=request.getParameter("param1");`

På samma sätt är parametrarna som du använder för att skicka XML-data och bifogade filer `dataXml` och `attachments`.

Du kan till exempel använda de här två parametrarna i skriptet för att tolka data till en slutpunkt. Du använder följande syntax för att lagra och analysera data:

`String data=request.getParameter("dataXml");`\
`String att=request.getParameter("attachments");`

I det här exemplet `data` lagrar XML-data, och `att` lagrar data för bifogade filer.

## Skicka e-post {#send-email}

The **[!UICONTROL Send Email]** skickar en åtgärd ett e-postmeddelande till en eller flera mottagare när formuläret har skickats. E-postmeddelandet som genereras kan innehålla formulärdata i ett fördefinierat format.

>[!NOTE]
Alla formulärfält måste ha olika elementnamn, även om de finns på olika paneler), för att kunna inkludera formulärdata i ett e-postmeddelande.

## Skicka PDF via e-post {#send-pdf-via-email}

The **[!UICONTROL Send PDF via Email]** skicka-åtgärd skickar ett e-postmeddelande med ett PDF som innehåller formulärdata till en eller flera mottagare när formuläret har skickats.

**Obs!** *Den här överföringsåtgärden är tillgänglig för XFA-baserade adaptiva formulär och XSD-baserade adaptionsformulär som har dokumentmallen.*

## Anropa ett formulärarbetsflöde {#invoke-a-forms-workflow}

The **[!UICONTROL Submit to Forms workflow]** Skicka-alternativet skickar en XML-datafil och eventuella bifogade filer till en befintlig JEE-process i Adobe eller AEM Forms.

Mer information om hur du konfigurerar Skicka till formulär-arbetsflödet finns i [Skicka och bearbeta formulärdata med hjälp av formulärarbetsflöden](/help/forms/using/submit-form-data-livecycle-process.md).

## Skicka med formulärdatamodell {#submit-using-form-data-model}

The **[!UICONTROL Submit using Form Data Model]** skicka-åtgärd skriver skickade adaptiva formulärdata för det angivna datamodellsobjektet i en formulärdatamodell till sin datakälla. När du konfigurerar skicka-åtgärden kan du välja ett datamodellsobjekt vars skickade data du vill skriva tillbaka till dess datakälla.

Dessutom kan du skicka en bifogad fil med hjälp av en formulärdatamodell och en DoR-fil (Document of Record) till datakällan.

Mer information om formulärdatamodell finns i [AEM Forms dataintegrering](/help/forms/using/data-integration.md).

## Forms Portal Submit Action {#forms-portal-submit-action}

The **[!UICONTROL Forms Portal Submit Action]** gör formulärdata tillgängliga via en AEM Forms-portal.

Mer information om Forms Portal och skicka-åtgärden finns i [Komponenten Utkast och inskickat material](/help/forms/using/draft-submission-component.md).

## Anropa ett AEM arbetsflöde {#invoke-an-aem-workflow}

The **[!UICONTROL Invoke an AEM Workflow]** skicka-åtgärd associerar ett anpassat formulär med ett AEM arbetsflöde. När ett formulär skickas startar det associerade arbetsflödet automatiskt på bearbetningsnoden. Dessutom placeras datafilen, bilagorna och, om tillämpligt, arkivdokumentet vid arbetsflödets nyttolastplats.

Innan du använder **[!UICONTROL Invoke an AEM Workflow]** skicka-åtgärd, [konfigurera AEM DS-inställningar](/help/forms/using/configuring-the-processing-server-url-.md). Mer information om hur du skapar ett AEM arbetsflöde finns i [Formulärbaserade arbetsflöden i OSGi](/help/forms/using/aem-forms-workflow.md).

## Förtroende på serversidan i adaptiv form {#server-side-revalidation-in-adaptive-form}

I alla onlinesystem för datainhämtning lägger utvecklare vanligtvis till JavaScript-valideringar på klientsidan för att tillämpa några få affärsregler. Men i moderna webbläsare kan slutanvändarna kringgå valideringarna och skicka in dokument manuellt med hjälp av olika tekniker, till exempel DevTools Console för webbläsare. Sådana tekniker gäller även för adaptiva former. En formulärutvecklare kan skapa olika valideringslogik, men tekniskt sett kan slutanvändarna kringgå dessa valideringslogik och skicka ogiltiga data till servern. Ogiltiga data skulle bryta mot de affärsregler som en formulärförfattare har infört.

Med funktionen för omvalidering på serversidan kan du även köra de valideringar som en författare av adaptiva formulär har tillhandahållit när de utformar ett adaptivt formulär på servern. Det förhindrar att inskickade data äventyras och affärsregelöverträdelser som representeras i form av formulärvalidering.

### Vad ska valideras på servern? {#what-to-validate-on-server-br}

Alla valideringar av ett anpassningsbart formulär som körs på servern är:

* Obligatoriskt
* Valideringsbildsats
* Valideringsuttryck

### Aktivera validering på serversidan {#enabling-server-side-validation-br}

Använd **Återvalidera på servern** under Adaptiv formulärbehållare i sidofältet för att aktivera eller inaktivera validering på serversidan för det aktuella formuläret.

![Aktivera validering på serversidan](assets/revalidate-on-server.png)
**Bild:** *Aktivera validering på serversidan*

Om slutanvändaren åsidosätter dessa valideringar och skickar formulären utför servern valideringen igen. Om valideringen misslyckas vid serverslutet stoppas skicka-transaktionen. Slutanvändaren får det ursprungliga formuläret igen. Insamlade data och skickade data visas för användaren som ett fel.

### Stöd för anpassade funktioner i valideringsuttryck {#supporting-custom-functions-in-validation-expressions-br}

Ibland, om **komplexa valideringsregler**, finns det exakta valideringsskriptet i anpassade funktioner och författaren anropar dessa anpassade funktioner från fältvalideringsuttryck. Om du vill att det här anpassade funktionsbiblioteket ska vara känt och tillgängligt vid validering på serversidan kan formulärförfattaren konfigurera namnet på AEM klientbibliotek under **[!UICONTROL Basic]** fliken med egenskaper för adaptiv formulärbehållare enligt nedan.

![Stöd för anpassade funktioner i valideringsuttryck](assets/clientlib-cat.png)
**Bild:** *Stöd för anpassade funktioner i valideringsuttryck*

Författaren kan konfigurera ett anpassat javascript-bibliotek per anpassat formulär. I biblioteket behåller du bara återanvändbara funktioner som är beroende av jQuery och underscore.js från tredje part.

## Felhantering vid sändning {#error-handling-on-submit-action}

Som en del av AEM riktlinjer för säkerhet och skärpa konfigurerar du anpassade felsidor som 404.jsp och 500.jsp. Dessa hanterare anropas när ett formulär 404- eller 500-fel skickas. Hanterarna anropas också när dessa felkoder aktiveras på noden Publicera.

Mer information finns i [Anpassa sidor som visas av felhanteraren](/help/sites-developing/customizing-errorhandler-pages.md).
