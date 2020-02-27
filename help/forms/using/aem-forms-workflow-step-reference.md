---
title: Formulärcentrerat arbetsflöde i OSGi - stegreferens
seo-title: Formulärcentrerat arbetsflöde i OSGi - stegreferens
description: Med formulärbaserat arbetsflöde i OSGi-steg kan du snabbt skapa anpassningsbara formulärbaserade arbetsflöden.
seo-description: Med formulärbaserat arbetsflöde i OSGi-steg kan du snabbt skapa anpassningsbara formulärbaserade arbetsflöden.
uuid: 57c872d6-c6ca-4f78-a98c-f9487f1d673c
contentOwner: aheimoz
discoiquuid: f2bd4d96-55a5-4fbd-bede-1747c2ec63c8
translation-type: tm+mt
source-git-commit: 36baba4ee20dd3d7d23bc50bfa91129588f55d32

---


# Formulärcentrerat arbetsflöde i OSGi - stegreferens {#forms-centric-workflow-on-osgi-step-reference}

## Arbetsflödessteg för formulär {#forms-workflow-steps}

Blankettstegen utför AEM Forms-specifika åtgärder i ett AEM-arbetsflöde. Med de här stegen kan du snabbt skapa anpassningsbara formulärbaserade formulärbaserade arbetsflöden i OSGi. Dessa arbetsflöden kan användas för att utveckla enkla arbetsflöden för granskning och godkännande samt interna och brandväggsrelaterade affärsprocesser. Du kan också använda steg i formulärarbetsflödet för att starta dokumenttjänster, integrera med signaturarbetsflödet i Adobe Sign och utföra andra AEM Forms-åtgärder. Du behöver [tillägget](https://www.adobe.com/go/learn_aemforms_documentation_63) AEM Forms för att kunna använda dessa steg i ett arbetsflöde.

## Tilldela aktivitetssteg {#assign-task-step}

Tilldela ett uppgiftssteg skapar en uppgift och tilldelar den till en användare eller grupp. Förutom att tilldela uppgiften anger komponenten även det adaptiva formuläret eller den icke-interaktiva PDF-filen för uppgiften. Det adaptiva formuläret krävs för att kunna ta emot indata från användare och icke-interaktiva PDF-filer eller ett skrivskyddat anpassat formulär används endast för granskning.

Du kan också använda komponenten för att styra aktivitetens beteende. Du kan till exempel skapa ett automatiskt postdokument, tilldela uppgiften till en viss användare eller grupp, ange sökvägen till skickade data, ange sökvägen till data som ska fyllas i i förväg och ange standardåtgärder. Tilldela uppgift-steget har följande egenskaper:

* **** Titel: Uppgiftens namn. Titeln visas i AEM Inbox.
* **** Beskrivning: Förklaring av de åtgärder som utförs i uppgiften. Den här informationen är användbar för andra processutvecklare när du arbetar i en delad utvecklingsmiljö.

* **** Miniatyrbildssökväg: Sökväg till aktivitetsminiatyrbilden. Om ingen sökväg anges visas en standardminiatyrbild för ett anpassat formulär och en standardikon för Postdokument.
* **** Arbetsflödesfas: Ett arbetsflöde kan ha flera steg. Dessa steg visas i AEM Inbox. Du kan definiera de här stegen i modellens egenskaper (Sidspark > Sida > Sidegenskaper > Steg).
* **** Prioritet: Den valda prioriteten visas i AEM Inbox. De tillgängliga alternativen är Hög, Medel och Låg. Standardvärdet är Medel.
* **** Förfallodatum: Ange antalet dagar eller timmar efter vilka aktiviteten har markerats som försenad. Om du väljer **Av** markeras uppgiften aldrig som försenad. Du kan också ange en uttidshanterare för att utföra vissa åtgärder när åtgärden är försenad.

* **** Dagar: Antalet dagar innan uppgiften ska slutföras. Antalet dagar räknas efter att uppgiften har tilldelats en användare. Om en uppgift inte är fullständig och korsar det antal dagar som anges i fältet Dagar, aktiveras en timeout-hanterare efter förfallodatumet, om detta väljs.
* **** Timmar: Antalet timmar innan uppgiften ska slutföras. Antalet timmar räknas efter att uppgiften har tilldelats en användare. Om en uppgift inte är slutförd och korsar det antal timmar som anges i fältet Timmar, aktiveras en timeout-hanterare efter de timmar som ska förfalla.
* **** Tidsgräns efter förfallodatum: Välj det här alternativet om du vill aktivera markeringsfältet för Timeout-hanteraren.
* **** Timeout-hanterare: Välj det skript som ska köras när tilldelningssteget överskrider förfallodatumet. Skript som placeras i CRX-databasen i [apps]/fd/dashboard/scripts/timeoutHandler kan väljas. Den angivna sökvägen finns inte i crx-databasen. En administratör skapar sökvägen innan den används.
* **** Markera åtgärden och kommentera från den senaste aktiviteten i Uppgiftsinformation: Välj det här alternativet om du vill visa den senaste åtgärden som utfördes och kommentaren som togs emot i aktivitetsinformationsavsnittet för en uppgift.
* **** Typ: Välj vilken typ av dokument som ska fyllas när arbetsflödet startas. Du kan välja ett anpassningsbart formulär, ett skrivskyddat anpassat formulär eller ett icke-interaktivt PDF-dokument.
* **** Använd adaptiv form: Ange den metod som ska användas för att hitta indataadaptiva formulär. Du kan använda det adaptiva formulär som finns på en absolut sökväg, som skickas som nyttolast till arbetsflödet eller som finns på en sökväg som beräknas med en variabel. Du kan använda en variabel av typen String för att ange sökvägen.
* **Adaptiv formulärsökväg**: Ange sökvägen för det adaptiva formuläret. Fältet är tillgängligt när du använder ett adaptivt formulär eller ett skrivskyddat adaptivt formulär i fältet Typ tillsammans med alternativet för absolut sökväg i fältet Använd adaptivt formulär.
* **** PDF-sökväg: Ange sökvägen till ett icke-interaktivt PDF-dokument. Fältet är tillgängligt när du väljer ett icke-interaktivt PDF-dokument i fältet Typ. Sökvägen är alltid relativ till nyttolasten. Exempel: [Payload_Directory]/Workflow/PDF/credit-card.pdf. Sökvägen finns inte i crx-databasen. En administratör skapar sökvägen innan den används. Du måste aktivera alternativet Dokument för post eller formulärmallsbaserade adaptiva formulär för att kunna använda alternativet PDF-sökväg.
* **Rendera det anpassningsbara formuläret som**: När en uppgift har markerats som slutförd kan du återge det anpassningsbara formuläret som ett skrivskyddat anpassat formulär eller som ett PDF-dokument. Du måste ha alternativet Dokument i post aktiverat eller formulärmallsbaserade adaptiva formulär för att kunna återge det adaptiva formuläret som Dokument i post.
* **** Information som ska fyllas i i förväg: Följande fält i listan nedan fungerar som indata för uppgiften:

   * **** Sökväg till datafil: Sökväg till indatafil (.json eller .xml). Sökvägen är alltid relativ till nyttolasten. Filen innehåller till exempel de data som skickats för formuläret via ett AEM Inbox-program. En exempelsökväg är [Payload_Directory]/workflow/data.
   * **** Sökväg till bifogad fil: Bifogade filer som är tillgängliga på platsen bifogas till formuläret som är kopplat till uppgiften. Sökvägen är alltid relativ till nyttolasten. En exempelsökväg är [Payload_Directory]/attachments/

* **** Skickade uppgifter: Följande fält i listan nedan fungerar som utdataplatser för uppgiften:

   * **** Sökväg till datafil: Sökväg till datafil (.json eller .xml). Datafilen innehåller information som skickas via det associerade formuläret. Sökvägen är alltid relativ till nyttolasten. Exempel: [Payload_Directory]/Workflow/data, där data är en fil.
   * **** Sökväg till bifogad fil: Sökväg för att spara de bifogade formulären i en uppgift.
   * **** Sökväg till postdokument: Sökväg för att spara en postdokumentfil. Exempel: [Payload_Directory]/DocumentofRecord/credit-card.pdf. Postdokumentet genereras inte om sökvägsfältet lämnas tomt. Sökvägen är alltid relativ till nyttolasten.

* **** Tilldelningsalternativ: Ange vilken metod som ska användas för att tilldela en användare uppgiften. Du kan dynamiskt tilldela uppgiften till en användare eller grupp med skriptet för deltagarväljaren eller tilldela uppgiften till en viss AEM-användare eller grupp.
* **** Väljare: Alternativet är tillgängligt när alternativet **Dynamiskt för en användare eller grupp** är markerat i fältet Tilldela alternativ. Du kan använda ett ECMAScript eller en tjänst för att dynamiskt välja en användare eller grupp. Mer information finns i Tilldela användare [ett arbetsflöde](https://helpx.adobe.com/experience-manager/kb/HowToAssignAWorkflowDynamicallyToParticipants.html) dynamiskt och [Skapa ett anpassat Adobe Experience Manager Dynamic Participant-steg.](https://helpx.adobe.com/experience-manager/using/dynamic-steps.html)

* **** Deltagare: Fältet är tillgängligt när alternativet **[!UICONTROL com.adobe.granite.workflow.core.process.RandomParticipantChooser]** har valts i fältet Deltagarväljare. I fältet kan du välja användare eller grupper för alternativet RandomParticipantChooser.

* **** Argument: Fältet är tillgängligt när ett annat skript än skriptet RandomParticipantChoose har valts i fältet för deltagarväljare. I fältet kan du ange en lista med kommaavgränsade argument för det skript som valts i fältet Deltagare.

* **** Användare eller grupp: Uppgiften tilldelas den valda användaren eller gruppen. Alternativet är tillgängligt när alternativet **** Till en viss användare eller grupp är markerat i fältet Tilldela alternativ. I fältet visas alla användare och grupper i gruppen för arbetsflödesanvändare.

* **** Meddela den tilldelade via e-post: Välj det här alternativet om du vill skicka e-postmeddelanden till den tilldelade personen. Dessa meddelanden skickas när en uppgift tilldelas en användare. Aktivera meddelanden från AEM Web Console innan du använder alternativet. Stegvisa instruktioner finns i [Konfigurera e-postmeddelanden för tilldelningssteget](/help/forms/using/aem-forms-workflow.md)

* **HTML-e-postmall**: Välj e-postmall för e-postmeddelandet. Om du vill redigera en mall ändrar du filen på /libs/fd/dashboard/templates/email/htmlEmailTemplate.txt i crx-databasen.
* **** Tillåt delegering till: I AEM Inbox finns ett alternativ för den inloggade användaren att delegera det tilldelade arbetsflödet till en annan användare. Du får delegera inom samma grupp eller till arbetsflödesanvändaren i en annan grupp. Om uppgiften har tilldelats en enskild användare och alternativet **Tillåt delegering till medlemmar i den tilldelade gruppen** har valts, går det inte att delegera uppgiften till en annan användare eller grupp.

* **** Standardåtgärder: Det finns färdiga funktioner för att skicka, spara och återställa. Som standard är alla standardåtgärder aktiverade.
* **** Flödesvariabel: Namn på flödesvariabeln. Vägvariabeln hämtar anpassade åtgärder som en användare väljer i AEM Inbox.
* **** Vägar: En aktivitet kan förgrena till olika vägar. När det här alternativet har valts i AEM Inbox returnerar flödet ett värde och arbetsflödesgrenarna baserat på den valda vägen.
* **Titel**: Ange ruttens titel. Den visas i AEM Inbox.
* **Korallikon**: Ange HTML-attribut för en korallikon. Adobe CorelUI-biblioteket innehåller en mängd ikoner som sätter fokus först. Du kan välja och använda en ikon för rutten. Den visas tillsammans med titeln i AEM Inbox.
* **Tillåt att den som tilldelats kan lägga till kommentarer**: Välj det här alternativet om du vill aktivera kommentarer för uppgiften. En tilldelad kan lägga till kommentarerna inifrån AEM Inbox när uppgiften skickas.
* **Tillåt att den som tilldelas kan lägga till bilagor till uppgiften**: Välj det här alternativet om du vill aktivera bilagor för uppgiften. En tilldelad kan lägga till de bifogade filerna inifrån AEM Inbox när uppgiften skickas.
* **Utdatasökväg för bifogade** uppgifter: Ange platsen för den bifogade mappen. Platsen är relativ till nyttolasten.
* **** Använd anpassade metadata: Välj det här alternativet om du vill aktivera det anpassade metadatafältet. Anpassade metadata används i e-postmallar.
* **** Anpassade metadata: Välj anpassade metadata för e-postmallarna. Anpassade metadata är tillgängliga i crx-databaser på apparna/fd/dashboard/scripts/metadataScripts. Den angivna sökvägen finns inte i crx-databasen. En administratör skapar sökvägen innan den används. Du kan också använda en tjänst för anpassade metadata. Du kan också utöka `WorkitemUserMetadataService` gränssnittet för att tillhandahålla anpassade metadata.

* **Visa data från föregående steg**: Välj det här alternativet om du vill att tilldelningar ska kunna visa tidigare tilldelningar, åtgärder som redan har vidtagits för uppgiften, kommentarer som har lagts till i uppgiften och dokument med information om den slutförda uppgiften, om tillgängligt.
* **** Visa data från efterföljande steg: Välj det här alternativet om du vill att den som är tilldelad ska kunna visa den åtgärd som har vidtagits och de kommentarer som har lagts till i uppgiften av efterföljande tilldelningar. Den aktuella personen kan även visa ett dokument med uppgifter om den slutförda uppgiften, om det är tillgängligt.
* **** Synlighet för datatyp: Som standard kan en tilldelad visa ett dokument för registrering, tilldelningar, åtgärd och kommentarer som tidigare och efterföljande tilldelningar har lagt till. Använd datatypsalternativet för synlighet för att begränsa vilken typ av data som är synlig för de tilldelade.

## Skicka e-poststeg {#send-email-step}

Använd e-poststeget för att skicka ett e-postmeddelande, till exempel ett e-postmeddelande med ett arkivdokument, en länk till ett anpassat formulär, en länk till en interaktiv kommunikation eller med ett bifogat PDF-dokument. Steget Skicka e-post stöder [HTML-e-post](https://en.wikipedia.org/wiki/HTML_email). HTML-e-post är responsiva och anpassar sig efter mottagarnas e-postklient och skärmstorlek. Du kan använda en HTML-e-postmall för att definiera utseendet, färgschemat och beteendet för e-postmeddelandet.

I e-poststeget används Day CQ Mail Service för att skicka e-post. Kontrollera att [e-posttjänsten](/help/forms/using/aem-forms-workflow.md) är konfigurerad innan du använder e-poststeget. E-poststeget har följande egenskaper:

**** Titel: Stegen är en titel som hjälper dig att identifiera steget i arbetsflödesredigeraren.

**** Beskrivning: Förklaring är användbar för andra processutvecklare när du arbetar i en delad utvecklingsmiljö.

**** Ämne: Ämne kan hämtas från ett arbetsflödes metadata eller anges manuellt. Välj alternativet **Litteralt** om du vill ange ett ämne manuellt eller markera alternativet **Hämta från arbetsflödets metadata** om du vill hämta ämnet från en metadataegenskap.

**HTML-e-postmall**: HTML-mall för e-postmeddelandet. Du kan ange variabler i en e-postmall. E-poststeget extraheras och visar alla variabler som ingår i en mall för indata.

**** Metadata för e-postmall: Värdet för e-postmallvariablerna kan vara ett användarspecificerat värde, sökvägen till en resurs på författaren eller på publiceringsservern, bilden eller en metadataegenskap för arbetsflödet.

* **** Literal: Använd alternativet när du vet exakt vilket värde du ska ange. Till exempel [example@example.com](mailto:example@example.com).

* **** Metadata för arbetsflöde: Använd alternativet när värdet som ska användas sparas i en arbetsflödets metadataegenskap. När du har valt alternativet anger du metadataegenskapens namn i den tomma textrutan under alternativet Metadata för arbetsflöde. Till exempel emailAddress.
* **** Resurs-URL: Använd alternativet för att bädda in en webblänk av en interaktiv kommunikation i e-postmeddelandet. När du har valt alternativet bläddrar du och väljer den interaktiva kommunikation som ska bäddas in. Resursen kan finnas på författaren eller på publiceringsservern.
* **** Bild: Använd alternativet för att bädda in en bild i e-postmeddelandet. När du har valt alternativet bläddrar du och väljer bilden. Bildalternativet är bara tillgängligt för de bildtaggar (&lt;img src=&quot;&amp;ast;&quot;/>) som är tillgängliga i e-postmallen.

**** Avsändarens/mottagarens e-postadress: Välj alternativet **Litteral** om du vill ange en e-postadress manuellt eller markera alternativet **Hämta från arbetsflödets metadata** om du vill hämta e-postadressen från en metadataegenskap. Du kan också ange en lista med egenskapsvektorer för metadata för **alternativet Hämta från arbetsflödesmetadata** .

**** Sökväg till bifogad fil: Den tillgängliga resursen på den angivna platsen är kopplad till e-postmeddelandet. Resursens sökväg kan vara relativ till nyttolasten eller den absoluta sökvägen. En exempelsökväg är [Payload_Directory]/attachments/

**** Filnamn: Namn på e-postbilagefilen. E-poststeget ändrar det ursprungliga filnamnet för den bifogade filen till det angivna filnamnet. Namnet kan anges manuellt eller hämtas från en metadataegenskap för arbetsflöde. Använd alternativet **Literal** när du vet exakt vilket värde du ska ange. Använd alternativet **Hämta från arbetsflödesmetadata** när värdet som ska användas sparas i en metadataegenskap för arbetsflöde.

## Generera dokumentarkivhandlingssteget {#generate-document-of-record-step}

När ett formulär fylls i eller skickas kan du spara en post med formuläret, i utskrift eller i dokumentformat. Detta kallas DOS (Document of Record). Du kan använda steget Skapa dokument för post för att skapa en skrivskyddad eller interaktiv PDF-version av ett anpassat formulär. PDF-versionen innehåller information som är ifylld i formuläret tillsammans med layouten för det adaptiva formuläret.

Dokumentsteget har följande egenskaper:

**Använd adaptiv form**: Ange den metod som ska användas för att hitta indataadaptiva formulär. Du kan använda det adaptiva formulär som finns på en absolut sökväg, som skickas som nyttolast till arbetsflödet eller som finns på en sökväg som beräknas med en variabel. Du kan använda en variabel av typen String för att ange sökvägen.

**Adaptiv formulärsökväg**: Ange sökvägen för det adaptiva formuläret. Fältet är tillgängligt när du använder ett adaptivt formulär eller ett skrivskyddat adaptivt formulär i fältet Typ tillsammans med alternativet för absolut sökväg i fältet Använd adaptivt formulär.

**** Sökväg för indata: Sökväg till indata för det adaptiva formuläret. Du kan behålla data på en plats i förhållande till nyttolasten eller ange en absolut sökväg för data. Indata sammanfogas med det adaptiva formuläret för att skapa ett postdokument.

**** Sökväg till bifogad fil: Sökväg för bifogad fil: Sökväg till de bifogade filerna. De här bifogade filerna ingår i dokumentdokumentet. Du kan behålla de bifogade filerna på en plats i förhållande till nyttolasten eller ange en absolut sökväg för de bifogade filerna.

Om du anger sökvägen till en mapp, till exempel bilagor, bifogas alla filer som är direkt tillgängliga i mappen till Dokument för post. Om det finns filer i de mappar som är direkt tillgängliga i den angivna sökvägen inkluderas filerna i Postdokument som bilagor. Om det finns mappar i direkt tillgängliga mappar hoppas de över.

**** Sökväg till genererat postdokument: Ange platsen där ett dokument med en postfil ska sparas. Du kan välja att skriva över nyttolastmappen eller placera postdokumentet på en plats i nyttolastkatalogen.

**Språk**: Ange språk för postdokumentet.

## Anropa tjänststeg för formulärdatamodell {#invoke-form-data-model-service-step}

Du kan använda [AEM Forms-dataintegrering](/help/forms/using/data-integration.md) för att konfigurera och ansluta till olika datakällor. Dessa datakällor kan vara en databas-, webbtjänst-, REST-tjänst-, OData-tjänst- och CRM-lösning. Med dataintegrering i AEM Forms kan du skapa en formulärdatamodell som omfattar olika tjänster som utför datahämtnings-, additions- och uppdateringsåtgärder för den konfigurerade databasen. Du kan använda steget **** Anropa datamodelltjänst för att välja en formulärdatamodell (FDM) och använda tjänsterna i FDM för att hämta, uppdatera eller lägga till data till olika datakällor.

Följande databastabell och JSON-filen används som exempel för att förklara indata för stegfält:

**Exempel på kundinformationsregister**

<table> 
 <tbody> 
  <tr> 
   <td>Egenskap</td> 
   <td>Värde<br /> </td> 
  </tr> 
  <tr> 
   <td>FirstName<br /> </td> 
   <td>Sarah<br /> </td> 
  </tr> 
  <tr> 
   <td>LastName</td> 
   <td>ros</td> 
  </tr> 
  <tr> 
   <td>Kund-ID</td> 
   <td>1</td> 
  </tr> 
  <tr> 
   <td>E-postadress<br /> </td> 
   <td>srose@we.info</td> 
  </tr> 
 </tbody> 
</table>

**JSON-exempelfil**

```
{ 
  customer: { 
   firstName: "Sarah", 
   lastName:"Rose", 
   customerId: "1", 
   emailAddress:"srose@we.info" 
 }, 
  insurance: {
   customerId: "1", 
  policyType: "Premium,
  policyNumber: "Premium-521499",
  customerDetails: { 
   firstName: "Sarah",
   lastName: "Rose",
   customerId: "1",
   emailAddress: "srose@we.info" 
  }
 }
}
```

I steget Anropa formulärdatamodelltjänst visas följande fält för att underlätta formulärdatamodellåtgärder:

* **** Titel: Stegets namn. Det hjälper till att identifiera steget i arbetsflödesredigeraren.
* **** Beskrivning: Förklaring är användbar för andra processutvecklare när du arbetar i en delad utvecklingsmiljö.

* **Sökväg till** formulärdatamodell: Bläddra och välj en formulärdatamodell som finns på servern.

* **Tjänst**: Lista över tjänster som den valda formulärdatamodellen tillhandahåller.
* **Indata för tjänster > Ange indata med hjälp av litteral, arbetsflödesmetadata och en JSON-fil**: En tjänst kan ha flera argument. Välj alternativet för att hämta värdet för tjänstargumenten från en metadataegenskap för arbetsflöde, ett JSON-objekt eller ange värdet direkt i textrutan:

   * **** Literal: Använd alternativet när du vet exakt vilket värde du ska ange. Exempel: srose@we.info.
   * **** Hämta från arbetsflödesmetadata: Använd alternativet när värdet som ska användas sparas i en arbetsflödets metadataegenskap. Till exempel emailAddress.
   * **** JSON-punktnotation: Använd alternativet när värdet som ska användas finns i en JSON-fil. Till exempel, försäkring.customerDetails.emailAddress.Alternativet JSON-punktnotation är bara tillgängligt om alternativet Mappa indatafält från JSON-indata har valts.
   * **** Mappa indatafält från JSON-indata: Ange sökvägen till en JSON-fil för att hämta indatavärdet för vissa tjänstargument från JSON-filen. JSON-filens sökväg kan vara relativ till nyttolasten eller en absolut sökväg.

* **** Indata för tjänster > Ange indata med hjälp av en JSON-fil: Välj alternativet om du vill hämta värden för alla argument från en JSON-fil.
* **Sökväg till** JSON-indatafil: Sökväg till JSON-filen som innehåller värden för alla tjänstargument. JSON-filens sökväg kan vara **relativ till nyttolasten** eller en **absolut sökväg**.

* **** JSON-punktnotation: Lämna fältet tomt om du vill använda alla objekt i den angivna JSON-filen som indata för tjänstargument. Om du vill läsa ett specifikt JSON-objekt från den angivna JSON-filen som indata för serviceargument anger du punktnotation för JSON-objektet, till exempel, om du har en JSON som liknar den som anges i början av avsnittet, anger du försäkring.customerDetails för att ge all information om en kund som indata till tjänsten.
* **** Utdata från tjänst > Mappa och skriv utdatavärden till metadata: Välj alternativet att spara utdatavärdena som egenskaper för arbetsflödesinstansens metadatanod i crx-databasen. Ange namnet på metadataegenskapen och välj det motsvarande tjänstutdataattribut som ska mappas med metadataegenskapen, till exempel mappa det telefonnummer som returneras av utdatatjänsten med egenskapen phone_number för arbetsflödets metadata.
* **** Utdata från tjänst > Spara utdata som JSON: Välj alternativet att spara utdatavärdena i en JSON-fil.
* **** Sökväg till JSON-utdatafil: Sökväg för att spara JSON-utdatafilen. Sökvägen till JSON-utdatafilen kan vara relativ till nyttolasten eller en absolut sökväg.

## Underteckna dokumentsteg {#sign-document-step}

I steget Signera dokument kan du använda Adobe Sign för att signera dokument. Stegen Signera dokument har följande egenskaper:

* **** Avtalsnamn: Ange avtalets namn. Avtalsnamnet blir en del av ämnet och brödtexten i det e-postmeddelande som skickas till signerarna.
* **** Språk: Ange språk för alternativen för e-post och verifiering.
* **Adobe Sign Cloud-konfiguration**: Välj en Adobe Sign Cloud-konfiguration. Om du inte har konfigurerat Adobe Sign för AEM-formulär läser du [Integrera Adobe Sign med AEM-formulär](/help/forms/using/adobe-sign-integration-adaptive-forms.md).

* **** Dokument som ska signeras: Du kan välja ett dokument från en plats som är relativ till nyttolasten, använda nyttolasten som dokument eller ange en absolut sökväg för dokumentet.
* **** Dagar till deadline: Ett dokument markeras som förfallodatum (passerad deadline) efter det att ingen aktivitet har gjorts i aktiviteten för det antal dagar som anges i fältet **Dagar till deadline** . Antalet dagar räknas efter att den dokumenterade har tilldelats en användare för signering.

* **** E-postfrekvens för påminnelse: Du kan skicka en påminnelse via e-post varje dag eller vecka. Veckan räknas från den dag som den dokumenterade tilldelas en användare för signering.
* **** Underskriftsprocess: Du kan välja att signera ett dokument i en sekventiell eller parallell ordning. I sekventiell ordning tar en signerare emot dokumentet i taget för signering. När den första signeraren har slutfört signeringen av dokumentet skickas dokumentet till den andra signeraren och så vidare. Flera signerare kan signera ett dokument samtidigt i parallell ordning.

* **** URL för omdirigering: Ange en URL för omdirigering. När dokumentet har signerats kan du dirigera om den som tilldelats till en URL. Oftast innehåller denna URL ett tackmeddelande eller ytterligare instruktioner.
* **** Arbetsflödesfas: Ett arbetsflöde kan ha flera steg. Dessa steg visas i AEM Inbox. Du kan definiera de här stegen i modellens egenskaper (Sidspark > Sida > Sidegenskaper > Steg).
* **** Välj signerare: Ange metoden för att välja signerare för dokumentet. Du kan dynamiskt tilldela arbetsflödet till en användare eller en grupp eller manuellt lägga till information om en signerare.
* **** Skript eller tjänst för att välja signerare: Alternativet är bara tillgängligt om alternativet Dynamiskt är markerat i fältet Välj signerare. Du kan ange ett ECMAScript eller en tjänst för att välja signerare och verifieringsalternativ för ett dokument.

* **** Signerarinformation: Alternativet är bara tillgängligt om alternativet Manuellt är markerat i fältet Välj signerare. Ange e-postadress och välj en valfri verifieringsmekanism. Innan du väljer en verifieringsmekanism i två steg ska du kontrollera att motsvarande verifieringsalternativ är aktiverat för det konfigurerade Adobe Sign-kontot.
* **** Statusvariabel: Ett Adobe Sign-aktiverat dokument lagrar dokumentets signeringsstatus i en variabel. Ange namnet på statusvariabeln (adobeSignStatus). En statusvariabel för en instans finns i CRXDE på /etc/workflow/instances/&lt;server>/&lt;datum-tid>/&lt;instans av arbetsflödesmodell>/workItems/&lt;nod>/metaData innehåller status för en variabel.
* **** Sökväg till signerat dokument: Ange platsen där signerade dokument ska sparas. Du kan välja att skriva över nyttolastfilen eller placera det signerade dokumentet på en plats i nyttolastkatalogen.

## Steg för Document Services {#document-services-steps}

AEM Document Services är en uppsättning tjänster för att skapa, sammanställa och skydda PDF-dokument. AEM Forms tillhandahåller ett separat AEM-arbetsflödessteg för varje dokumenttjänst:

### Använd tidsstämpelsteg för dokument {#apply-document-time-stamp-step}

Lägg till tidsstämpel i ett dokument. Du kan ange dokumentinformation, t.ex. indatadokumentsökväg, indatadokumentnamn och plats där exporterade data ska lagras. Du kan välja att skriva över en befintlig nyttolastfil eller välja ett annat filnamn för att lagra data i en annan fil under nyttolastmappen.

### Konvertera till bildsteg {#convert-to-image-step}

 Konverterar ett PDF-dokument till en bildfil. Bildformat som stöds är JPEG, JPEG2000, PNG och TIFF. Följande information gäller för konvertering till TIFF-bilder:

* En TIFF-fil med flera sidor skapas.
* Vissa anteckningar ingår inte i TIFF-bilder. Anteckningar som kräver att Acrobat genererar sitt utseende inkluderas inte.

### Konvertera till PDF/A-steg {#convert-to-pdf-a-step}

Konverterar ett PDF-dokument till PDF/A-format med de angivna alternativen. PDF/A-versionen av PDF (Portable Document Format) är avsedd för arkivering och långtidsarkivering av dokument.

### Konvertera till PS-steg {#convert-to-ps-step}

Konvertera PDF-dokument till PostScript. När du konverterar till PostScript kan du använda konverteringsåtgärden för att ange källdokumentet och om det ska konverteras till PostScript-nivå 2 eller 3. PDF-dokumentet som du konverterar till en PostScript-fil måste vara icke-interaktivt.

### Skapa PDF från angivet textsteg {#create-pdf-from-specified-type-step}

Generera ett PDF-dokument från en indatafil. Indatadokumentet kan vara relativt till nyttolasten, ha en absolut sökväg eller vara nyttolasten.

### Skapa PDF från URL/HTML/ZIP {#create-pdf-from-url-html-zip-step}

Skapar ett PDF-dokument av den angivna URL-, HTML- och ZIP-filen.

### Steget Exportera data {#export-data-step}

Exporterar data från ett PDF-formulär eller en XDP-fil. Du måste ange filsökvägen för Input Document och Export Data Format. Alternativen för Exportera dataformat är Auto, XDP och XmlData.

### Exportera PDF till angivet textsteg {#export-pdf-to-specified-type-step}

Konverterar ett PDF-dokument till ett valt format.

### Generera icke-interaktiv PDF-steg {#generate-non-interactive-pdf-step}

Skapa en icke-interaktiv PDF. Här finns olika anpassningsalternativ.

### Importera datasteg {#import-data-step}

Sammanfogar formulärdata till ett PDF-formulär. Du kan importera formulärdata till ett PDF-formulär.

### Anropa DDX-steg {#invoke-ddx-step}

Kör DDX-filen på den angivna kartan över indatadokument och returnerar de manipulerade PDF-dokumenten.

### Optimera PDF-steget {#optimize-pdf-step}

Optimerar PDF-filer genom att minska deras storlek. Resultatet av konverteringen är PDF-filer som kan vara mindre än originalversionerna. Den här åtgärden konverterar även PDF-dokument till den PDF-version som anges i optimeringsparametrarna.

Optimeringsinställningarna anger hur filerna optimeras. Här följer några exempelinställningar:

* Målversion för PDF
* Ignorera objekt som JavaScript-åtgärder och inbäddade sidminiatyrer
* Ignorera användardata som kommentarer och bifogade filer
* Ignorerar ogiltiga eller oanvända inställningar
* Komprimera okomprimerade data eller använda mer effektiva komprimeringsalgoritmer
* Ta bort inbäddade teckensnitt
* Ange genomskinlighetsvärden

### Återge PDF-formulär, steg {#render-pdf-form-step}

Återger ett formulär som skapats i Form Designer (XDP) till ett PDF-formulär.

### Säkra dokument, steg {#secure-document-step}

Kryptera, signera och certifiera ett dokument. AEM Forms stöder både lösenordsbaserad och certifikatbaserad kryptering. Du kan också välja mellan olika algoritmer för signering av dokument. Exempel: SHA-256 och SH-512. Du kan också använda arbetsflödessteget för att läsa utökade PDF-dokument. Arbetsflödessteget innehåller alternativ för att aktivera streckkodsavkodning, digitala signaturer, import och export av PDF-data och andra alternativ.

### Skicka till skrivare, steg {#send-to-printer-step}

Skicka ett dokument direkt till en skrivare. Det har stöd för följande åtkomstmekanismer för utskrift:

* **Direkttillgänglig skrivare**: En skrivare som är installerad på samma dator kallas för en skrivare med direktåtkomst och datorn kallas för skrivarvärd. Den här typen av skrivare kan vara en lokal skrivare som är ansluten direkt till datorn.
* **Indirekt tillgänglig skrivare**: Skrivaren som är installerad på en utskriftsserver är tillgänglig från andra datorer. Teknik som det gemensamma utskriftssystemet UNIX® (CUPS) och protokollet Line Printer Daemon (LPD) är tillgängliga för anslutning till en nätverksskrivare. Om du vill få åtkomst till en indirekt tillgänglig skrivare anger du utskriftsserverns IP-adress eller värdnamn. Med den här funktionen kan du skicka ett dokument till en LPD-URI när nätverket har ett LPD-program öppet. Med hjälp av den här funktionen kan du dirigera dokumentet till en skrivare som är ansluten till nätverket som har ett LPD-program öppet.

