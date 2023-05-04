---
title: PUBLICERA INTE Skapa ditt första adaptiva dokument
seo-title: DO NOT PUBLISH Create your first adaptive document
description: PUBLICERA INTE
seo-description: DO NOT PUBLISH
page-status-flag: de-activated
uuid: 2cb2bf82-130f-4d6b-a711-df0b97cb0504
discoiquuid: f3ca177f-7c0d-4b8b-ab4b-bf04668d634c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---


# PUBLICERA INTE Skapa ditt första adaptiva dokument {#do-not-publish-create-your-first-adaptive-document}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Användningsfall {#use-case}

Vi på finansområdet är en ledande organisation inom finanssektorn som erbjuder omfattande och personaliserade finansiella lösningar för att passa behoven hos olika kundprofiler.

En av kundernas bilförsäkring upphör att gälla och de skickar en påminnelse till henne, som är interaktiv och innehåller en PDF, med förnyelseofferten. Meddelandet innehåller även annan information, t.ex. om lojalitetsprogram och rabatterbjudanden.

Portalen går på Adobe AEM. Webben och utskriften av välkomstkanaler skapas med de flerkanalsfunktioner som finns i det adaptiva dokumentet.

Du kommer att ha ett adaptivt dokument som liknar följande i slutet av självstudiekursen:
[ ![ad-1](assets/ad-1.png)](https://blogs.adobe.com/contentcorner/files/2017/07/PAF_Mobile.pdf)    [ ![ad-2](assets/ad-2.png)](https://blogs.adobe.com/contentcorner/files/2017/07/PAF_Desktop.pdf)Den första självstudiekursen om adaptiva dokument är indelad i steg. Varje steg är en komplett artikel i sig.

<table> 
 <tbody>
  <tr>
   <th>Du kommer att lära dig</th> 
   <th>
    <ul> 
     <li>Skapa ett adaptivt dokument och en formulärdatamodell.</li> 
     <li>Skapa mallar och teman för adaptiva dokument.</li> 
     <li>Använda regelredigeraren för att skapa affärsregler.<br /> </li> 
     <li>Publicera ett adaptivt dokument. <br /> </li> 
    </ul> </th> 
  </tr>
  <tr>
   <td>Förutsättning</td> 
   <td>
    <ul> 
     <li>AEM författarinstans. </li> 
     <li>Installera AEM Forms-tillägg. Mer information finns i <a href="/help/forms/using/installing-configuring-aem-forms-osgi.md" target="_blank">Installera och konfigurera AEM Forms</a>.</li> 
     <li>Hämta JDBC-databasdrivrutin (JAR-fil) från databasprovidern. Exemplen i självstudien är baserade på MySQL-databasen och använder Oraclets MySQL JDBC-databasdrivrutin. </li> 
     <li>Konfigurera en databas som innehåller kunddata. En databas är nödvändig för att skapa ett adaptivt dokument. I den här självstudien används en databas för att visa formulärdatamodell och beständighetsfunktioner i AEM Forms. </li> 
     <li>Skapa/importera och aktivera <a href="/help/forms/using/web-channel-print-channel.md">Mallar för tryck och webbkanal</a>.</li> 
     <li>Se till att du har <a href="/help/forms/using/document-fragments.md">Dokumentfragment baserade på FDM</a>.</li> 
    </ul> </td> 
  </tr>
 </tbody>
</table>

## Steg 1: Skapa formulärdatamodell {#step-create-form-data-model}

En formulärdatamodell gör det möjligt att koppla ett adaptivt dokument till olika datakällor. Till exempel AEM användarprofil, RESTful-webbtjänster, SOAP-baserade webbtjänster, OData-tjänster och relationsdatabaser. En formulärdatamodell är ett enhetligt datarepresentationsschema för affärsenheter och tjänster som är tillgängliga i anslutna datakällor. Du kan använda formulärdatamodellen med ett adaptivt dokument för att hämta data från anslutna datakällor. Mer information om formulärdatamodell finns i [AEM Forms dataintegrering](/help/forms/using/data-integration.md).

Mål:

* Konfigurera databasinstansen (Microsoft Dynamics) som en datakälla
* Skapa formulärdatamodellen med Microsoft Dynamics som datakälla
* Lägga till datamodellobjekt i formulärdatamodellen
* Konfigurera läs- och skrivtjänster för formulärdatamodellen
* Testa formulärdatamodell och konfigurerade tjänster med testdata

## Steg 2: Skapa ett adaptivt dokument {#step-create-an-adaptive-document}

Customer Communications centraliserar och hanterar framtagning, sammanställning och leverans av säkra, personaliserade och interaktiva korrespondenser som affärskorrespondens, brev, dokument, kontoutdrag, förmånsmeddelanden, förmögenhetsförvaltningsprospekt, marknadsföringsmejl, räkningar och välkomstpaket.

Med adaptiva dokument kan ni skapa kundkommunikation som är engagerande, responsiv, dynamisk och anpassningsbar till sin natur. AEM Forms har en WYSIWYG-redigerare som du kan dra och släppa för att skapa anpassningsbara dokument.

<!--`For more information about adaptive documents, see [Introduction to authoring adaptive documents](/forms/using/introduction-ad-authoring.md).`-->

Mål:

* Skapa tryck- och webbutdata i ett adaptivt dokument baserat på formulärdatamodell.
* Layoutfält i ett anpassat formulär som visar information för kunden
* Skapa regler för att hämta och visa information från formulärdatamodellen till anpassningsbara dokument.

<!--![see-the-guide-sm](assets/see-the-guide-sm.png)-->

## Steg 3: Tillämpa regler på anpassningsbara dokumentfält (endast webbkanalen) {#step-apply-rules-to-adaptive-document-fields-web-channel-only}

Med adaptiva dokument kan du redigera regler för adaptiva dokumentobjekt. Dessa regler definierar åtgärder som ska utlösas för dokumentobjekt baserat på förinställda villkor och användaråtgärder för dokumentet. Det gör att det går snabbare och exaktare att använda i webbversionen av det adaptiva dokumentet. Mer information om anpassningsbara dokumentregler och regelredigerare finns i [regelredigerare](/help/forms/using/rule-editor.md).

Mål:

* Skapa och tillämpa regler för anpassningsbara dokumentets webbkanalsfält
* Använd regler för att aktivera dokumentdatamodelltjänster i webbkanalen

## Steg 4: Formatera det adaptiva dokumentet (endast webbkanalen) {#step-style-the-adaptive-document-web-channel-only}

Med adaptiva dokument kan du skapa teman för adaptiva dokument och infogad formatering. Ett tema innehåller formatinformation för komponenter och paneler, och du kan återanvända ett tema i webbkanaler för olika dokument. Format innehåller egenskaper som bakgrundsfärger, lägesfärger, genomskinlighet, justering och storlek. När du använder temat i dokumentet återspeglas det angivna formatet i motsvarande komponenter i dokumentet. Mer information finns i [Teman](/help/forms/using/themes.md).

Mål:

* Skapa tema för webbkanalen för adaptiva dokument
* Använd tema i webbkanalen för adaptiva dokument
* Validera utseendet på den adaptiva dokumentwebbkanalen på mobila enheter och datorer

## Steg 5: Publicera det adaptiva dokumentet {#step-publish-the-adaptive-document}

När du är klar med att skapa ditt adaptiva dokument måste du publicera det för att det ska vara tillgängligt på din publiceringsinstans där agenterna kan använda det adaptiva dokumentet för att skapa kommunikationsinstanser baserade på det.

För att kunna publicera det adaptiva dokumentet måste dokumentförfattarna ha de behörigheter som krävs.
