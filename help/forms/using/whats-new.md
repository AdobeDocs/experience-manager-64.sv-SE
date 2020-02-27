---
title: Sammanfattning av nya funktioner| AEM 6.4-formulär
seo-title: Sammanfattning av nya funktioner| AEM 6.4-formulär
description: Sammanfattning av nya funktioner och förbättringar i AEM 6.4-formulär.
seo-description: Sammanfattning av nya funktioner och förbättringar i AEM 6.4-formulär.
uuid: 152068ec-47a8-43f4-b9c8-3a17d1f085fe
contentOwner: vishgupt
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: introduction
discoiquuid: 436aa424-d05e-4f3d-90ac-5ff3b05ddba8
translation-type: tm+mt
source-git-commit: 715cff841252d79504d702817f91db92df919bfc

---


# Sammanfattning av nya funktioner| AEM 6.4-formulär {#new-features-summary-aem-forms}

Sammanfattning av nya funktioner och förbättringar i AEM 6.4-formulär.

AEM Forms innehåller flera nya funktioner och förbättringar som ytterligare effektiviserar skapande, hantering och användarupplevelser med adaptiva formulär och interaktiv kommunikation.

Läs vidare för att få en snabb introduktion till nya funktioner och förbättringar. Mer information finns i dokumentationen. Se även [versionsinformation](/help/release-notes/forms.md)för AEM 6.4-formulär. Fullständig dokumentation för AEM 6.4-formulär finns i [AEM 6.4 Forms User Guide](/help/forms/home.md).

## Interaktiv kommunikation {#interactive-communications}

![korrespondenshantering](assets/correspondence-management.png)

Interactive Communications centraliserar och hanterar framtagning, sammanställning och leverans av säkra, personaliserade och interaktiva korrespondenser som affärskorrespondens, brev, dokument, kontoutdrag, förmånsmeddelanden, förmögenhetsförvaltningsprospekt, marknadsföringsmejl, räkningar och välkomstpaket.

Interactive Communications använder samma underliggande teknik, processer och komponenter som i adaptiva formulär för att skapa responsiv kommunikation i flera kanaler, ungefär som responsiva adaptiva formulär.

Interaktiv kommunikation har stora fördelar:

* Ger OOTB-integrering med Form Data Model för enkel och smidig åtkomst till backend-databaser och andra CRM-system som MS Dynamics
* Har ett integrerat gränssnitt för tryck- och webbkanaler
* Innehåller dra-och-släpp-baserat redigeringsgränssnitt, som liknar redigering av adaptiva formulär, för både tryck- och webbkanaler.

Interaktiv kommunikation är standardmetoden och rekommenderas för att skapa kundkommunikation. Om du vill fortsätta använda bokstäverna i AEM 6.3-formulär och AEM 6.2-formulär måste du installera ett kompatibilitetspaket.

### Framtagning av interaktiv kommunikation i flera kanaler {#multi-channel-interactive-communication-authoring}

Med hjälp av interaktiv kommunikation kan du skapa och redigera både utskrifts- och webbdokument från en enda dokumentredigerare. Genom att använda samma dokumentfragment för att skapa återgivningar av båda kanalerna kan du slippa dubbelarbete.
![printweb_2](assets/printweb_2.png)

Mer information finns i Översikt över [interaktiv kommunikation](/help/forms/using/interactive-communications-overview.md).

### WYSIWYG-dokumentredigerare {#wysiwyg-document-editor}

WYSIWYG-redigeraren för dra-och-släpp-dokument är enkel att använda. Det intuitiva gränssnittet, dra-och-släpp-funktionen, standardkomponenter, datamodeller och det integrerade arkivet för resurser gör det enkelt att snabbt skapa interaktiv kommunikation.

Om du vill skapa en interaktiv kommunikation eller redigera en befintlig, kan företagsanvändare använda följande byggblock: Kanaler, innehåll, egenskaper, resurser, komponenter och datakällor.

![drag-n-drop-lf](assets/drag-n-drop-lf.png)

Mer information finns i Introduktion [till utveckling av interaktiv kommunikation](/help/forms/using/introduction-interactive-communication-authoring.md).

### Generera webbversion automatiskt från tryckt innehåll i interaktiv kommunikation {#auto-generate-web-version-from-print-content-in-interactive-communication}

Man kan automatiskt generera webbdokumentinnehåll från utskrift av dokument till författare, förhandsgranskning och redigering av både utskrifts- och webbdokument i samma redigerare. De som skapar interaktiv kommunikation kan skapa en gång och publicera i alla kanaler. Den som skapar interaktiv kommunikation kan använda samma dokumentfragment i tryck- och webbkanalen för att undvika dubbelarbete.

Mer information finns i [Skriva ut kanal och webbkanal](/help/forms/using/web-channel-print-channel.md).

### Använd teman för att utforma webbkanaler för interaktiv kommunikation {#use-themes-to-style-web-channel-of-interactive-communication}

Interaktiv kommunikation stöder teman. Du kan skapa teman och använda dem i din interaktiva kommunikation. Ett tema innehåller formatinformation för komponenter och paneler. Du kan återanvända ett tema i olika interaktiva dokument för att ge dem ett vanligt och konsekvent utseende och varumärke.

AEM Forms innehåller ett tema för interaktiv kommunikation. Med hjälp av ett tema kan du även anpassa hur en interaktiv kommunikation ser ut på en enhet.

Mer information finns i [Teman i AEM-formulär](/help/forms/using/themes.md).

### Förbättrat agentgränssnitt {#enhanced-agent-interface}

Användargränssnittet Agent har nu stöd för förhandsgranskning av interaktiv kommunikation i tryck och på webben. I samma agentanvändargränssnitt kan du välja att redigera utskriftskanalen och förhandsgranska webbkanalen i din interaktiva kommunikation i flera kanaler. Fält, variabler, FDM-element och dokumentfragment i utskriftskanalen kan konfigureras så att de ändras av agenten i agentens användargränssnitt. Med stöd för formulärdatamodell kan du generera förhandsgranskningar med förfyllda exempeldata.

Mer information finns i [Förbereda och skicka interaktiv kommunikation med agentens användargränssnitt](/help/forms/using/prepare-send-interactive-communication.md).

### Visa information i diagram {#present-information-in-charts}

Interaktiv kommunikation stöder diagram på webben och i tryckkanaler för bättre kommunikation. Med diagram som paj, munk, bar och spalt kan du komprimera och visuellt presentera stora mängder information för enkel tolkning och analys.

![diagram-2](assets/chart-2.png) - ![diagram](assets/chart.png)

Mer information finns i [Använda diagram i interaktiv kommunikation](/help/forms/using/chart-component-interactive-communications.md).

### Körklara dataanslutningar för förifyllda dokument {#out-of-the-box-data-connectors-to-prefill-documents}

Interaktiv kommunikation ger dataintegrering med affärsverktyg för att kunna koppla samman med flera affärssystem, inklusive CRM-system, och personalisera data i dokument.

![fdm_ad](assets/fdm_ad.png)

Mer information finns i [Använda formulärdatamodell](/help/forms/using/using-form-data-model.md).

### Förbättrad dokumentfragmentredigerare {#enhanced-document-fragment-editor}

Nu kan du använda FDM-element och -regler i dokumentfragment för interaktiv kommunikation.

* Stöd för element i formulärdatamodell
* Visa eller dölj en resurs/ett textfragment med hjälp av regler
* Validera värdet för ett element/en variabel
* Utför funktioner för att beräkna värdet för ett matematiskt uttryck

Mer information finns i:

* [Texter i interaktiv kommunikation](/help/forms/using/texts-interactive-communications.md)
* [Villkor i interaktiv kommunikation](/help/forms/using/conditions-interactive-communications.md)

### Kompatibilitetspaket för befintliga resurser {#compatibility-package-for-existing-assets}

Som standard stöds inte bokstavsresurser från tidigare versioner av AEM Forms i den här versionen. Om du tänker fortsätta använda bokstäverna från AEM 6.3-formulär och AEM 6.2-formulär måste du installera kompatibilitetspaketet.

## Dataintegrering {#data-integration}

![](do-not-localize/data-integeration-1.png)

[Med dataintegrering](/help/forms/using/data-integration.md) i AEM Forms kan du konfigurera olika datakällor; såsom databaser, RESTful- eller SOAP-baserade webbtjänster och OData-tjänster, för att skapa en formulärdatamodell som du kan använda för att binda data, förifylla och anropa tjänster i anpassningsbara formulär och dokument.

Det finns flera nya funktioner och förbättringar i dataintegreringen i den här versionen.

### Skapa formulärdatamodell utan datakälla {#create-form-data-model-without-data-source}

Affärsanvändare och formulärförfattare kan nu skapa en formulärdatamodell, med entiteter och egenskaper, utan att konfigurera en datakälla, och kan användas för att skapa adaptiva formulär och dokument. Du kan binda formulärdatamodellen till datakällor senare. Det eliminerar beroendet av datakällor för att skapa formulär och dokument med hjälp av formulärdatamodell.

På samma sätt kan du skapa entiteter och underordnade egenskaper i en befintlig formulärdatamodell och binda dem till motsvarande entiteter och egenskaper i en datakälla senare.

Mer information finns i [Skapa formulärdatamodell](/help/forms/using/create-form-data-models.md).

### Skapa beräknade egenskaper {#create-computed-properties}

Formulärförfattare och utvecklare kan skapa beräknade egenskaper i formulärdatamodellen. De gör att du kan beräkna ett värde för egenskapen genom att skapa regler eller logik för data som är tillgängliga i konfigurerade datakällor. En regel är ett uttryck som utvärderas när data läses in i formulärdatamodellen eller när värdena för egenskaperna i uttrycket ändras. En beräknad fastighet som heter Avbetalningar beräknar t.ex. månadsbeloppet som ska betalas för ett lån baserat på den räntesats som anges i datakällan och det lånebelopp och den löptid som anges av användaren i formuläret.

En beräknad egenskap finns lokalt i en formulärdatamodell och finns inte i en datakälla. Du kan använda beräknade egenskaper i adaptiva formulär och interaktiv kommunikation.

Mer information finns i [Arbeta med formulärdatamodell](/help/forms/using/work-with-form-data-model.md).

### Förgranska formulär och dokument med exempeldata {#preview-forms-and-documents-with-sample-data}

Med formulärdatamodellen kan du generera exempeldata för egenskaper för alla enheter i en formulärdatamodell. De genererade data motsvarar de datatyper som har konfigurerats för egenskaperna. När du förhandsgranskar ett anpassat formulär eller dokument som är kopplat till formulärdatamodellen återges det med förfyllda exempeldata.

Exempeldata är en uppsättning slumpmässiga värden som ändras varje gång du genererar dem. Du kan dock redigera och spara de exempeldata som finns kvar även om du genererar om dem. Om du till exempel redigerar och sparar exempeldata för egenskaperna Förnamn och Efternamn och senare lägger till en annan egenskap eller enhet i formulärdatamodellen och genererar om exempeldata, kommer egenskaperna Förnamn och Efternamn att visa de sparade värdena medan värdena för andra egenskaper genereras om.

Mer information finns i [Använda formulärdatamodell](/help/forms/using/using-form-data-model.md).

### Uppdatera definitioner för datakällor {#refresh-data-source-definitions}

Uppdateringar i datakällenheter eller egenskaper återspeglas inte automatiskt i tillhörande formulärdatamodeller. Formulärdatamodellens redigerare innehåller nu ![refresh_forms_di](assets/refresh_forms_di.png) (Update Data Source Definitions) som gör servercachen ogiltig och hämtar uppdaterat schema från datakällan så att det omedelbart återspeglas i formulärdatamodellen.

### Konfigurera datakällor med Touch-användargränssnittet {#configure-data-sources-using-touch-user-interface}

I den här versionen är molntjänstkonfigurationen för datakällor tillgänglig i Touch-användargränssnittet. Dessutom har platsen för att konfigurera molntjänster ändrats till **[!UICONTROL Verktyg > Molntjänster > Datakällor]**. See [Configure data sources](/help/forms/using/configure-data-sources.md).

## Adaptiva former {#adaptive-forms}

![simplified-of-authoring-forms-and-documents_hero-image_2](assets/simplification-of-authoring-forms-and-documents_hero-image_2.png)

### Förbättra prestanda för anpassningsbara formulär med förbättrad lazy loading {#improve-performance-of-adaptive-forms-with-enhanced-lazy-loading}

Den lata inläsningsfunktionen i adaptiva formulär förenklar initieringen av formulärfragment tills de behövs. Det förbättrar prestanda för stora formulär genom att minimera den tid som krävs för att återge ett formulär, vilket ger en bättre användarupplevelse.

Det finns flera förbättringar av funktionen för lazy loading i den här versionen:

* Komponenter för bifogade filer och villkor stöds i formulärfragment där lazy loading är aktiverat.
* Anpassningsbara formulärfragment med lazy loading aktiverat stöds i repeterbara paneler.
* Anpassningsbara formulär med lazy loading-aktiverade fragment stöds i appen AEM Forms.

## Formulärbaserade AEM-arbetsflöden {#forms-centric-aem-workflows}

![aem-forms-workflow-on-osgi-](assets/aem-forms-workflow-on-osgi-.png)

Med funktioner för formulärcentrerade AEM-arbetsflöden kan du snabbt skapa och distribuera arbetsflöden för olika uppgifter i OSGi-stacken. Du behöver inte längre installera processhanteringsfunktionen som finns i JEE-stacken, vilket förenklar driftsättningen och eliminerar kostnaderna för programservrar och infrastruktur. Mer information finns i [Formulärbaserade arbetsflöden i OSGi](/help/forms/using/aem-forms-workflow.md).

Nedan följer förbättringarna i formulärcentrerade AEM-arbetsflöden: ・

* Arbetsflödesmodellredigeraren är tillgänglig i Touch-användargränssnittet. Det hjälper er att minska den tid som krävs för att skapa formulärbaserade AEM-arbetsflöden.
* Arbetsflödessteg för att skicka e-post. Du kan till exempel använda e-poststeget för att skicka ett postdokument när ett arbetsflöde har slutförts.
* Arbetsflödessteg för att använda formulärdatamodelltjänster i en arbetsflödesmodell. I det här steget kan du anropa dataintegreringstjänster utan att skriva någon anpassad kod. Du kan till exempel anropa en GET-tjänst för att få information om anställda från ett databasarkiv utan att behöva skriva någon egen kod.

## AEM Forms App {#aem-forms-app}

![aem-forms-app](assets/aem-forms-app.png)

Med appen AEM Forms kan fältarbetare synkronisera sina mobila enheter med en AEM Forms-server och arbeta med sina formulär. Programmet fungerar sömlöst när enheten är offline genom att spara data lokalt på enheten och synkronisera data med servern när enheten är online igen. Mer information finns i [AEM Forms-appen](/help/forms/using/aem-forms-app.md).

Nedan följer förbättringarna i appen AEM Forms:

* Anpassningsbara formulär med lazy loading-aktiverade fragment stöds i appen AEM Forms.
* Anpassningsbara formulär med formulärdatamodell stöds i appen AEM Forms.

## Dokumentsäkerhet {#document-security}

![aem-forms-document-security-aem](assets/aem-forms-document-security-.png)

Med dokumentsäkerhet kan du distribuera all information som du har sparat i ett format som stöds. Dokumentsäkerheten säkerställer att bara behöriga användare kan använda dina dokument. Nedan följer de största förändringarna inom dokumentsäkerhet:

* Dokumentsäkerhet tillhandahåller ett [PPL-bibliotek (Portable Protection Library)](/help/forms/using/document-security-offerings.md) som skyddar ett dokument lokalt utan att skicka dokumentet till AEM Forms-servern. Det är bara säkerhetsuppgifter och principinformation som överförs via nätverket till AEM Forms-servern. AEM 6.4 Forms har infört PPL (Portable Protection Library) i ett OSGi-paketformat. Nu kan du direkt installera PPL-biblioteket på en AEM Forms-server och använda funktionerna i AEM och PPL tillsammans.
* Dokumentsäkerhet C++ SDK och C++ PPL-bibliotek kan kompileras med Microsoft Visual Studio 2013. Den tidigare versionen som stöds var Microsoft Visual Studio 2010.

## Plattformar som stöds {#supported-platforms}

AEM Forms kan konfigureras med valfri kombination av operativsystem, programservrar, databaser, databasdrivrutiner, JDK, LDAP-servrar och e-postservrar som stöds. Nedan följer de största förändringarna för plattformar som stöds:

<table> 
 <tbody> 
  <tr> 
   <td>Komponent</td> 
   <td>Support tillagd</td> 
   <td>Stöd borttaget</td> 
  </tr> 
  <tr> 
   <td>Operativsystem</td> 
   <td> 
    <ul> 
     <li>Microsoft Windows Server 2016</li> 
     <li>Oracle Linux 7 Update 3</li> 
    </ul> </td> 
   <td> 
    <ul> 
     <li>IBM AIX 7.2 <sup>[1]</sup><br /> </li> 
     <li>Solaris 11 <sup>[1]</sup></li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Programservrar<br /> </td> 
   <td> 
    <ul> 
     <li>Red Hat JBoss EAP 7</li> 
    </ul> </td> 
   <td> 
    <ul> 
     <li>IBM Weblogic 12.1.3</li> 
     <li>IBM WebSphere 8.5.5</li> 
     <li>Red Hat JBoss EAP 6</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Databaser</td> 
   <td> 
    <ul> 
     <li>Microsoft SQL Server 2016</li> 
     <li>MySQL 5.7.19 och senare</li> 
     <li>IBM DB2 11.1</li> 
     <li>Oracle Multitenant-arkitektur</li> 
    </ul> </td> 
   <td> 
    <ul> 
     <li>Microsoft SQL Server 2012<br /> </li> 
     <li>Microsoft SQL Server 2014</li> 
     <li>MySQL 5.5</li> 
     <li>IBM DB2 10.5<br /> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>LDAP-servrar</td> 
   <td> 
    <ul> 
     <li>Microsoft Active Directory 2016</li> 
     <li>IBM Tivoli Directory Server 6.4</li> 
    </ul> </td> 
   <td> 
    <ul> 
     <li>Microsoft Active Directory 2008</li> 
     <li>IBM Tivoli Directory Server 6.3</li> 
     <li>Oracle Directory Server Enterprise Edition 7.0</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>E-postservrar</td> 
   <td> 
    <ul> 
     <li>Microsoft Office 365</li> 
    </ul> </td> 
   <td> 
    <ul> 
     <li>Novell Group 7</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Anslutningar</td> 
   <td> 
    <ul> 
     <li>Koppling för Microsoft Sharepoint 2016</li> 
     <li>Connector for EMC Documentum 7.3</li> 
    </ul> </td> 
   <td> 
    <ul> 
     <li>Koppling för Microsoft Sharepoint 2007</li> 
     <li>Koppling för Microsoft SharePoint 2010</li> 
     <li>Koppling till IBM Filenet 5.0</li> 
     <li>Connector for EMC Documentum 6.7</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Webbläsare</td> 
   <td> 
    <ul> 
     <li>Apple Safari 11.x i macOS</li> 
     <li>Apple Safari 11.x på iOS</li> 
    </ul> </td> 
   <td> 
    <ul> 
     <li>Blackberry-webbläsare för Blackberry Z30- och Q10-enheter</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Appen AEM Forms<br /> </td> 
   <td> 
    <ul> 
     <li>Android 4.4 eller senare</li> 
     <li>Apple iOS 10 eller senare</li> 
    </ul> </td> 
   <td> </td> 
  </tr> 
 </tbody> 
</table>

1. Operativsystemen AIX och Solaris finns endast för uppgraderingskunder.
