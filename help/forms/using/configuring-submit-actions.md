---
title: Konfigurera åtgärden Skicka
seo-title: Konfigurera åtgärden Skicka
description: Med AEM Forms kan du konfigurera en skicka-åtgärd för att definiera hur ett anpassat formulär ska bearbetas när det har skickats in. Du kan använda inbyggda skicka-åtgärder eller skriva egna från grunden.
seo-description: Med AEM Forms kan du konfigurera en skicka-åtgärd för att definiera hur ett anpassat formulär ska bearbetas när det har skickats in. Du kan använda inbyggda skicka-åtgärder eller skriva egna från grunden.
uuid: aa261e65-a1ec-402b-80de-0ba8a294e315
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: fea76f90-22d5-4836-9901-a35229401eb0
feature: Adaptiv Forms
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '1505'
ht-degree: 0%

---


# Konfigurera åtgärden Skicka {#configuring-the-submit-action}

## Introduktion till att skicka åtgärder {#introduction-to-submit-actions}

En sändningsåtgärd utlöses när en användare klickar på knappen Skicka i ett anpassat formulär. Du kan konfigurera åtgärden skicka i anpassningsbara formulär. Med adaptiva formulär kan du skicka in ett antal åtgärder direkt. Du kan kopiera och utöka standardåtgärderna för att skicka och skapa en egen sändningsåtgärd. Baserat på dina krav kan du dock skriva och registrera en egen skicka-åtgärd för att bearbeta data i det skickade formuläret.

När ett formulär är förifyllt eller skickat slussas inskickade data via AEM för datamassning till mellanliggande format. Data sparas inte på en AEM, förutom när det adaptiva formuläret använder Adobe Sign, verifiera, formulärportalutkast eller skicka-AEM

Du kan konfigurera en skicka-åtgärd i avsnittet **[!UICONTROL Submission]** i egenskaperna för den adaptiva formulärbehållaren i sidofältet.

![Konfigurera ](assets/thank-you-setting.png)
**åtgärden Skicka:** *Konfigurera åtgärden Skicka*

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
>Kontrollera att [AEM_Installation_Directory]\crx-quickstart\temp\datamanager\ASM folder exists. Katalogen krävs för att temporärt lagra bilagor. Om katalogen inte finns skapar du den.

>[!CAUTION]
>
>Om du [förifyller](/help/forms/using/prepopulate-adaptive-form-fields.md) en formulärmall, formulärdatamodell eller schemabaserad adaptiv form med XML- eller JSON-data, till ett schema (XML-schema, JSON-schema, formulärmall eller formulärdatamodell) som är data innehåller inte &lt;afData>-, &lt;afBoundData>- och &lt;/afUnboundData>-taggar, innehåller data för obundet obegränsade fältet (unbundet) Begränsade fält är adaptiva formulärfält utan [bindref](/help/forms/using/prepopulate-adaptive-form-fields.md)-egenskap) för det adaptiva formuläret går förlorade.

Du kan skriva en anpassad skicka-åtgärd för anpassade formulär för att uppfylla ditt användningssätt. Mer information finns i [Skriva anpassad Skicka-åtgärd för adaptiva formulär](/help/forms/using/custom-submit-action-form.md).

## Skicka till REST-slutpunkt {#submit-to-rest-endpoint}

Med alternativet **[!UICONTROL Submit to REST endpoint]** skickas data som fyllts i formuläret till en konfigurerad bekräftelsesida som en del av HTTP GET-begäran. Du kan lägga till namnet på fälten som ska begäras. Begäran har följande format:

`{fieldName}={request parameter name}`

Som visas i bilden nedan skickas `param1` och `param2` som parametrar med värden som kopierats från fälten **[!UICONTROL textbox]** och **[!UICONTROL numericbox]** för nästa åtgärd.

Du kan också **[!UICONTROL Enable POST request]** och ange en URL för att skicka begäran. Om du vill skicka data till den AEM servern som är värd för formuläret använder du en relativ sökväg som motsvarar rotsökvägen för AEM. Exempel: /content/forms/af/SampleForm.html. Om du vill skicka data till en annan server använder du den absoluta sökvägen.

![Konfigurerar åtgärden Skicka för resterande slutpunkt](assets/action-config.png)

Konfigurerar åtgärden Skicka för resterande slutpunkt

>[!NOTE]
Om du vill skicka fälten som parametrar i en REST-URL måste alla fält ha olika elementnamn, även om fälten placeras på olika paneler.

### Bokför skickade data till en resurs eller extern slutpunkt för vila  {#post-submitted-data-to-a-resource-or-external-rest-end-point-nbsp}

Använd åtgärden **[!UICONTROL Submit to REST Endpoint]** för att skicka skickade data till en rest-URL. URL:en kan vara en intern (servern som formuläret återges på) eller en extern server.

Om du vill skicka data till en intern server anger du sökvägen till resursen. Data bokförs som resurssökväg. Till exempel /content/restEndPoint. För sådana efterfrågningar används autentiseringsinformationen i förfrågan.

Ange en URL om du vill skicka data till en extern server. URL-adressen har formatet https:// host:port/path_to_rest_end_point. Se till att du konfigurerar sökvägen så att den hanterar POSTENS begäran anonymt.

![Mappning för fältvärden skickas som Tack-sidan-parametrar](assets/post-enabled-actionconfig.png)

I exemplet ovan fångas användarinformationen i `textbox` med parametern `param1`. Syntax för att bokföra data som har hämtats med `param1` är:

`String data=request.getParameter("param1");`

På samma sätt är de parametrar som du använder för att skicka XML-data och bifogade filer `dataXml` och `attachments`.

Du kan till exempel använda de här två parametrarna i skriptet för att tolka data till en slutpunkt. Du använder följande syntax för att lagra och analysera data:

`String data=request.getParameter("dataXml");`\
`String att=request.getParameter("attachments");`

I det här exemplet lagrar `data` XML-data och `att` bilagedata.

## Skicka e-post {#send-email}

**[!UICONTROL Send Email]**-sändningsåtgärden skickar ett e-postmeddelande till en eller flera mottagare när formuläret har skickats. E-postmeddelandet som genereras kan innehålla formulärdata i ett fördefinierat format.

>[!NOTE]
Alla formulärfält måste ha olika elementnamn, även om de finns på olika paneler), för att kunna inkludera formulärdata i ett e-postmeddelande.

## Skicka PDF via e-post {#send-pdf-via-email}

Med åtgärden **[!UICONTROL Send PDF via Email]** skickar du ett e-postmeddelande med en PDF-fil som innehåller formulärdata till en eller flera mottagare när formuläret har skickats.

**Obs!** *Den här överföringsåtgärden är tillgänglig för XFA-baserade adaptiva formulär och XSD-baserade adaptionsformulär som har dokumentmallen.*

## Anropa ett formulärarbetsflöde {#invoke-a-forms-workflow}

Alternativet **[!UICONTROL Submit to Forms workflow]** för att skicka data-xml och eventuella bifogade filer till en befintlig JEE-process i Adobe eller AEM Forms.

Mer information om hur du konfigurerar Skicka till formulär-arbetsflödet finns i [Skicka och bearbeta formulärdata med formulärarbetsflöden](/help/forms/using/submit-form-data-livecycle-process.md).

## Skicka med formulärdatamodell {#submit-using-form-data-model}

Överföringsåtgärden **[!UICONTROL Submit using Form Data Model]** skriver skickade adaptiva formulärdata för det angivna datamodellsobjektet i en formulärdatamodell till sin datakälla. När du konfigurerar skicka-åtgärden kan du välja ett datamodellsobjekt vars skickade data du vill skriva tillbaka till dess datakälla.

Dessutom kan du skicka en bifogad fil med hjälp av en formulärdatamodell och en DoR-fil (Document of Record) till datakällan.

Mer information om formulärdatamodell finns i [AEM Forms Data Integration](/help/forms/using/data-integration.md).

## Forms Portal Submit Action {#forms-portal-submit-action}

Alternativet **[!UICONTROL Forms Portal Submit Action]** gör formulärdata tillgängliga via en AEM Forms-portal.

Mer information om Forms Portal och skicka-åtgärden finns i [Komponenten för utkast och inskickning](/help/forms/using/draft-submission-component.md).

## Anropa ett AEM arbetsflöde {#invoke-an-aem-workflow}

Överföringsåtgärden **[!UICONTROL Invoke an AEM Workflow]** associerar ett anpassat formulär med ett AEM arbetsflöde. När ett formulär skickas startar det associerade arbetsflödet automatiskt på bearbetningsnoden. Dessutom placeras datafilen, bilagorna och, om tillämpligt, arkivdokumentet vid arbetsflödets nyttolastplats.

Innan du använder åtgärden **[!UICONTROL Invoke an AEM Workflow]** ska du [konfigurera AEM DS-inställningar](/help/forms/using/configuring-the-processing-server-url-.md). Mer information om hur du skapar ett AEM arbetsflöde finns i [Formulärbaserade arbetsflöden i OSGi](/help/forms/using/aem-forms-workflow.md).

## Serversidesåtervalidering i adaptiv form {#server-side-revalidation-in-adaptive-form}

I alla onlinesystem för datainhämtning lägger utvecklare vanligtvis till JavaScript-valideringar på klientsidan för att tillämpa några få affärsregler. Men i moderna webbläsare kan slutanvändarna kringgå valideringarna och skicka in dokument manuellt med hjälp av olika tekniker, till exempel DevTools Console för webbläsare. Sådana tekniker gäller även för adaptiva former. En formulärutvecklare kan skapa olika valideringslogik, men tekniskt sett kan slutanvändarna kringgå dessa valideringslogik och skicka ogiltiga data till servern. Ogiltiga data skulle bryta mot de affärsregler som en formulärförfattare har infört.

Med funktionen för omvalidering på serversidan kan du även köra de valideringar som en författare av adaptiva formulär har tillhandahållit när de utformar ett adaptivt formulär på servern. Det förhindrar att inskickade data äventyras och affärsregelöverträdelser som representeras i form av formulärvalidering.

### Vad ska valideras på servern? {#what-to-validate-on-server-br}

Alla valideringar av ett anpassningsbart formulär som körs på servern är:

* Krävs
* Valideringsbildsats
* Valideringsuttryck

### Aktivera validering på serversidan {#enabling-server-side-validation-br}

Använd **Verifiera på servern** under Adaptiv formulärbehållare i sidlisten för att aktivera eller inaktivera validering på serversidan för det aktuella formuläret.

![Aktivera ](assets/revalidate-on-server.png)
**validering på serversidan:** *aktivera validering på serversidan*

Om slutanvändaren åsidosätter dessa valideringar och skickar formulären utför servern valideringen igen. Om valideringen misslyckas vid serverslutet stoppas skicka-transaktionen. Slutanvändaren får det ursprungliga formuläret igen. Insamlade data och skickade data visas för användaren som ett fel.

### Stöd för anpassade funktioner i valideringsuttryck {#supporting-custom-functions-in-validation-expressions-br}

När det gäller **komplexa valideringsregler** finns ibland det exakta valideringsskriptet i anpassade funktioner och författaren anropar dessa anpassade funktioner från fältvalideringsuttryck. För att göra det här anpassade funktionsbiblioteket tillgängligt när du utför validering på serversidan kan formulärförfattaren konfigurera namnet på AEM klientbibliotek på fliken **[!UICONTROL Basic]** i egenskaper för adaptiv formulärbehållare enligt nedan.

![Stöd för anpassade funktioner i ](assets/clientlib-cat.png)
**valideringsuttryckBild:** *Stöd för anpassade funktioner i valideringsuttryck*

Författaren kan konfigurera ett anpassat javascript-bibliotek per anpassat formulär. I biblioteket behåller du bara återanvändbara funktioner som är beroende av jQuery och underscore.js från tredje part.

## Felhantering vid sändning av åtgärd {#error-handling-on-submit-action}

Som en del av AEM riktlinjer för säkerhet och skärpa konfigurerar du anpassade felsidor som 404.jsp och 500.jsp. Dessa hanterare anropas när ett formulär 404- eller 500-fel skickas. Hanterarna anropas också när dessa felkoder aktiveras på noden Publicera.

Mer information finns i [Anpassa sidor som visas av felhanteraren](/help/sites-developing/customizing-errorhandler-pages.md).
