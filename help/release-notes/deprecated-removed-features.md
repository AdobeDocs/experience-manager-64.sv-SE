---
title: Föråldrade och borttagna funktioner
description: Versionsinformation om borttagna funktioner i Adobe Experience Manager 6.4.
translation-type: tm+mt
source-git-commit: 543f66c760d7b25681a79d5df3d8ab6e8c0b2f47
workflow-type: tm+mt
source-wordcount: '1234'
ht-degree: 3%

---


# Föråldrade och borttagna funktioner {#deprecated-and-removed-features}

Adobe utvärderar ständigt produktfunktioner för att så småningom förnya eller ersätta äldre funktioner med modernare alternativ för att förbättra det totala kundvärdet, alltid med noggrant övervägande av bakåtkompatibilitet.

Följande regler gäller för att informera om den förestående borttagningen/ersättningen av AEM:

1. Föråldringsanmälan kommer först. Funktioner är fortfarande tillgängliga, men de kommer inte att förbättras ytterligare.
1. Borttagning av föråldrade funktioner kommer att ske tidigast i följande större version. Faktiskt måldatum för borttagning tillkännages.

Den här processen ger kunderna minst en releasecykel för att anpassa implementeringen till en ny version eller en efterföljare till en borttagningsfunktion, innan den faktiska borttagningen.

## Borttagna funktioner {#deprecated-features}

Tabellen nedan visar funktioner som har markerats som borttagna i AEM 6.4. I allmänhet är funktioner som ska tas bort i en framtida version först inaktuella, med ett alternativ.

Kunderna rekommenderas att granska om de använder funktionen/funktionen i den aktuella distributionen och planera för att ändra implementeringen så att den använder det alternativ som finns.

<!-- TBD: This MD table is a replacement of the HTML table below. However, it generates validation error hence commenting and replacing with inline text. Restore if required. -->

| Yta | Funktion | Ersättning |
|---|---|---|
| UI | Adobe planerar inte att göra fler förbättringar av det klassiska användargränssnittet. AEM 6.4 har det klassiska användargränssnittet och kunder som uppgraderar från tidigare versioner kan fortsätta använda det som det är. Observera att Classic-användargränssnittet fortfarande stöds fullt ut när det är inaktuellt. <ul> <li>`/libs/cq/core/content/welcome.html` </li> <li> `/siteadmin` </li> <li> `/damadmin` </li> <li> `/mcmadmin` </li> <li> `/inbox` </li> <li> `/tagging` </li> <li> `/cf#` (Page Editor) </li><li> `/libs/launches/content/admin.html` </li> <li> `/libs/cq/workflow/content/console.html` </li> </ul> | Kunder rekommenderas att byta till det nya AEM. |
| Komponenter | Adobe planerar inte att göra ytterligare förbättringar av de grundkomponenter som anges nedan. AEM 6.4 innehåller Foundation Components, och kunder som uppgraderar från tidigare versioner kan fortsätta använda dem som de är. Observera att Foundation Components fortfarande stöds fullt ut medan de föråldras. <ul> <li> foundation/components/account/account/account_name </li> <li> grund/komponenter/konto/åtgärder </li> <li> foundation/components/account/passwordreset </li> <li> grund/komponenter/konto/begärandebekräftelse </li> <li> foundation/components/adaptiveimage </li> <li> foundation/components/assetsharingPage </li> <li> foundation/components/breadcrumb </li> <li> grund/komponenter/form/kreditkort </li> <li> grund/komponenter/listchildren </li> <li> grund/komponenter/inloggning </li> <li> grund/komponenter/logotyp </li> <li> foundation/components/mobilefooter </li> <li> foundation/components/mobileimage </li> <li> foundation/components/mobilelist </li> <li> grund/komponenter/mobilelogo </li> <li> foundation/components/mobilereference </li> <li> grund/komponenter/mobiletextimage </li> <li> foundation/components/mobiletopnav </li> <li> grund/komponenter/sökning </li> <li> grund/komponenter/platskarta </li> <li> grund/komponenter/tabell </li> <li> grund/komponenter/verktygsfält </li> <li> grund/komponenter/topnav </li> <li> foundation/components/userinfo </li> </ul> | Kunderna rekommenderas att använda kärnkomponenterna för framtida projekt. Befintliga webbplatser behöver inte ändras. |
| Komponenter | Adobe planerar inte att göra ytterligare förbättringar av de grundkomponenter som anges nedan. AEM 6.4 innehåller Foundation Components, och kunder som uppgraderar från tidigare versioner kan fortsätta använda dem som de är. Observera att Foundation Components fortfarande stöds fullt ut medan de föråldras. <ul><li>grund/komponenter/timing</li></ul> | Adobe planerar inte att tillhandahålla någon ersättning. |
| Portal Director | Portal Director är en uppsättning funktioner som gör det möjligt att lägga AEM innehåll via Portlet i tredjepartsservrar. Adobe planerar inte att göra ytterligare förbättringar av portalfunktionen Director på den plats som anges nedan. AEM 6.4 har portalen Director och kunder som uppgraderar från tidigare versioner kan fortsätta använda den som den är. Observera att Portal Direct fortfarande stöds fullt ut när det är föråldrat. <ul><li>/libs/portal/director</li></ul> | Adobe planerar inte att tillhandahålla någon ersättning. |
| Portlet-komponent | Portlet Components under /foundation/components/portlet gör att JSR Portlets i AEM kan användas som komponenter. Adobe planerar inte att göra fler förbättringar av funktionen Portlet Component. AEM 6.4 har Portlet Component inkluderat och kunder som uppgraderar från tidigare versioner kan fortsätta använda det som det är. Observera att Portlet Component fortfarande har fullt stöd medan det är föråldrat. | Adobe planerar inte att tillhandahålla någon ersättning. |
| Forms | Stödet för tjänsten Adobe Central Migration Bridge har tagits bort eftersom Adobe Central inte längre stöds. | Ingen ersättning |
| Forms | Användning av JSONObject i Query och OperationOptions har tagits bort. Följande API:er är inaktuella: <ul><li>`setArguments(JSONObject arguments)`</li><li> `JSONObject getArguments()`</li><li>`OperationOptions(String operationId, JSONObject arguments)`</li><li>`JSONObject getArguments()`</li><li> `void setArguments(JSONObject arguments)`</li></ul> | Använda `IValueMap` API |
| Forms | Tjänsten Central Migration Bridge är inaktuell. | Ingen ersättning erbjuds. |
| Assets | Avlastning av resurser har tagits bort från och med AEM 6.4. |  |

<!-- Original HTML table that came from helpx during migration.

<table> 
 <tbody>
  <tr>
   <td>Area</td> 
   <td>Feature</td> 
   <td>Replacement</td> 
  </tr>
  <tr>
   <td>UI</td> 
   <td><p>Adobe does not plan to make further enhancements to the Classic UI. AEM 6.4 has the Classic UI included, and customers upgrading from earlier releases can keep using it as is. Note that Classic UI remains fully supported while being deprecated. </p> 
    <ul> 
     <li>/libs/cq/core/content/welcome.html</li> 
     <li>/siteadmin</li> 
     <li>/damadmin</li> 
     <li>/mcmadmin</li> 
     <li>/inbox</li> 
     <li>/tagging</li> 
     <li>/cf# (Page Editor)</li> 
     <li>/libs/launches/content/admin.html</li> 
     <li>/libs/cq/workflow/content/console.html</li> 
    </ul> </td> 
   <td><p>Customers are advised to switch to use the new AEM UI.</p> <p> </p> </td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td><p>Adobe does not plan to make further enhancements to the Foundation Components listed below. AEM 6.4 has the Foundation Components included, and customers upgrading from earlier releases can keep using them as is. Note that Foundation Components remain fully supported while being deprecated. </p> 
    <ul> 
     <li>foundation/components/account/accountname</li> 
     <li>foundation/components/account/actions</li> 
     <li>foundation/components/account/passwordreset</li> 
     <li>foundation/components/account/requestconfirmation</li> 
     <li>foundation/components/adaptiveimage</li> 
     <li>foundation/components/assetsharepage</li> 
     <li>foundation/components/breadcrumb</li> 
     <li>foundation/components/form/creditcard</li> 
     <li>foundation/components/listchildren</li> 
     <li>foundation/components/login</li> 
     <li>foundation/components/logo</li> 
     <li>foundation/components/mobilefooter</li> 
     <li>foundation/components/mobileimage</li> 
     <li>foundation/components/mobilelist</li> 
     <li>foundation/components/mobilelogo</li> 
     <li>foundation/components/mobilereference</li> 
     <li>foundation/components/mobiletextimage</li> 
     <li>foundation/components/mobiletopnav</li> 
     <li>foundation/components/search</li> 
     <li>foundation/components/sitemap</li> 
     <li>foundation/components/table</li> 
     <li>foundation/components/toolbar</li> 
     <li>foundation/components/topnav</li> 
     <li>foundation/components/userinfo</li> 
    </ul> </td> 
   <td>Customers are advised to use the Core Components for future projects. Existing sites do not need to be changed.</td> 
  </tr>
  <tr>
   <td>Components</td> 
   <td><p>Adobe does not plan to make further enhancements to the Foundation Components listed below. AEM 6.4 has the Foundation Components included, and customers upgrading from earlier releases can keep using them as is. Note that Foundation Components remain fully supported while being deprecated.</p> 
    <ul> 
     <li>foundation/components/timing</li> 
    </ul> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Portal Director</td> 
   <td><p>The Portal Director is a set of features, that enables the hosting of AEM content via Portlet in 3rd party servers.</p> <p>Adobe does not plan to make further enhancements to the Portal Director feature under the location listed below. AEM 6.4 has the Portal Director included, and customers upgrading from earlier releases can keep using it as is. Note that Portal Direct remains fully supported while being deprecated.</p> 
    <ul> 
     <li>/libs/portal/director</li> 
    </ul> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Portlet Component</td> 
   <td><p>Portlet Components under /foundation/components/portlet enables the hosting of JSR Portlets in AEM as components.</p> <p>Adobe does not plan to make further enhancements to the Portlet Component feature. AEM 6.4 has the Portlet Component included, and customers upgrading from earlier releases can keep using it as is. Note that Portlet Component remains fully supported while being deprecated.</p> </td> 
   <td>At the point of writing, it's not planned to provide a replacement.</td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td><p>Support for Adobe Central Migration Bridge service has been deprecated as Adobe Central product is no longer supported.</p> </td> 
   <td>No replacement </td> 
  </tr>
    <tr>
   <td>Forms</td> 
   <td><p>Deprecated use of JSONObject in Query and OperationOptions. The following APIs are deprecated:
   <ul><li>setArguments(JSONObject arguments)</li><li>JSONObject getArguments()</li><li>OperationOptions(String operationId, JSONObject arguments</li><li>JSONObject getArguments()</li><li>void setArguments(JSONObject arguments)</li></ul>
   </p> </td> 
   <td>Use the IValueMap API </td> 
  </tr>
  <tr>
   <td>Forms</td> 
   <td><p>Deprecated Central Migration Bridge service</p> </td> 
   <td> No replacement </td> 
  </tr>
  <tr>
   <td>Assets</td> 
   <td><p>Assets Offloading has been deprecated starting with AEM 6.4</p> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>
-->

## Borttagna funktioner {#removed-features}

Tabellen nedan visar funktioner som har tagits bort från AEM 6.4. Tidigare versioner hade dessa funktioner markerats som föråldrade.

| Yta | Funktion | Ersättning |
|---|---|---|
| Analytics Activity Map | Den version av Activity Map som ingår i AEM. | På grund av säkerhetsändringar i Adobe Analytics API är det inte längre möjligt att använda den version av Activity Map som ingår i AEM. Plugin-programmet [ActivityMap från Adobe Analytics](https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html) bör nu användas. |
| Components-Forms | Form Captcha (foundation/components/form/captcha) | Använd komponenten ReCaptcha från Google i stället |
| Komponenter | Bildspel (grund/komponenter/bildspel) | Ingen ersättning |
| Komponenter | Flash (grund/komponenter/flash) | Ingen ersättning |
| Komponenter | Stöd för uppspelning av SWF-filer i videokomponenten har tagits bort (grund/komponenter/video) | Använd inget-flash-baserade videoformat. |
| Komponenter | Produkttabell (commerce/components/product_table) | Ingen ersättning |
| Aktivitetshantering | Klassisk UI-aktivitetshantering (/libs/cq/taskmanagement/content/taskmanager.html) | Borttagen sedan 6.0. Använd den nya uppgiftshanteringen som kombineras med arbetsflödets användargränssnitt. |
| Arbetsflöde | Meddelandegränssnitt som används mellan 5.6 och 6.2 (/libs/cq/workflow/content/notifications.html) | Inkorg för arbetsflöde/aem/inbox |
| Forms | Export PDF till PDF/E-1-format med PDF Generator har tagits bort. | PDF Generator har fortsatt stöd för export av PDF till formaten PDF/A-1a/b, PDF/A-2a/b och PDF/A-3a/b. |
| Forms | Stöd för bilder i dokumentfragment har tagits bort. | Interaktiv kommunikation gör det möjligt att använda bilder i tryck- och webbkanaler direkt. |
| Forms | Uppgradering utanför kontoret | Det finns inget stöd för att utföra uppgraderingen utanför platsen |
| Forms | Sidegrade för TjärMK till DocumentMK-migreringar | Du kan exportera data från ett äldre system och sedan importera dem i ett uppdateringssystem. Mer information finns i AEM Forms om JEE-uppgraderingsdokumentation |
| Forms | AEM Forms på JEE 32-bitars installationsprogram är inte tillgängligt. | Adobe har slutat leverera AEM Forms på JEE 32-bitars installationsprogram. Du kan fortsätta använda 64-bitars installationsprogram för att installera AEM Forms på JEE. |
| Forms | Tog bort stöd för att använda DAM-bilder i Document Fragment Component. | Du kan använda komponenterna Bild och Diagram i den interaktiva kommunikationens tryckkanal. Om du använder adaptiv dokuments dokumentfragmentkomponent i adaptiva formulär slutar den att fungera efter uppgradering till AEM 6.4 Forms. |
| Forms | Funktionen Adaptiva dokument har tagits bort | Du kan använda funktionen för interaktiv kommunikation för att skapa tryckt och webbaserad kommunikation. Om du använder adaptiva dokument måste du installera kompatibilitetspaketet för att kunna fortsätta använda befintliga adaptiva dokument |
| Forms | AEM Forms på JEE-specifik landningssida togs bort. | AEM Forms på JEE-landningssidan ska ersättas med AEM landningssida (/aem/start.html) |
| Forms | Stöd för standard-Captcha har tagits bort | Använd tjänsten reCAPTCHA från Google. |
| Forms | Stöd för flash-fält i AEM Designer har tagits bort. AEM Designer tillåter inte redigering av Flash-fält som används i ett formulär. | Du kan använda AEM Designer som släppts för en tidigare version för att redigera sådana formulär. |
| Communities | Stöd för Captcha-verifiering har tagits bort. | Använd anpassad Captcha-integrering (till exempel reCAPTCHA från Google) för verifiering. |

## Förhandsmeddelande för nästa release {#pre-announcement-for-next-release}

Tabellen nedan innehåller en lista över ändringar för framtida releaser som inte är inaktuella, men som kan påverka kunderna. Dessa tillhandahålls för planeringsändamål.

| Yta | Funktion | Meddelande |
|---|---|---|
| Webbläsarstöd | Microsoft Internet Explorer | AEM 6.4 är den senaste versionen som har stöd för Microsoft Internet Explorer 11. |
| Foundation | UI Framework | Adobe tar bort Coral UI 2-komponenterna under 2019. AEM 6.4 baseras helt på Coral UI 3 (introducerades med AEM 6.2). Adobe rekommenderar sina kunder och partners som har byggt anpassade gränssnitt med Coral 2 att ändra dessa till Coral 3. Adobe har ett verktyg för att konvertera dialogrutor från Coral 2 till Coral 3 - [Läs mer](/help/sites-developing/dialog-conversion.md). |
