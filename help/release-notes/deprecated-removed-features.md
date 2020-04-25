---
title: Föråldrade och borttagna funktioner
seo-title: Föråldrade och borttagna funktioner
description: Versionsinformation om borttagna och borttagna funktioner i Adobe Experience Manager 6.4.
seo-description: Versionsinformation om borttagna och borttagna funktioner i Adobe Experience Manager 6.4.
uuid: 2619039b-72b4-4c6c-a813-90eed622b423
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 15819d42-4897-40fa-a013-e019d1580fa2
translation-type: tm+mt
source-git-commit: 45849a1a22f99d149369cd91781de4de0260c8e3

---


# Föråldrade och borttagna funktioner {#deprecated-and-removed-features}

Adobe utvärderar ständigt produktfunktioner för att så småningom förnya eller ersätta äldre funktioner med modernare alternativ för att förbättra det totala kundvärdet, alltid med noggrant övervägande av bakåtkompatibilitet.

Följande regler gäller för att informera om kommande borttagning/ersättning av AEM-funktioner:

1. Föråldringsanmälan kommer först. Funktioner är fortfarande tillgängliga, men de kommer inte att förbättras ytterligare.
1. Borttagning av föråldrade funktioner kommer att ske tidigast i följande större version. Faktiskt måldatum för borttagning tillkännages.

Den här processen ger kunderna minst en releasecykel för att anpassa implementeringen till en ny version eller en efterföljare till en borttagningsfunktion, innan den faktiska borttagningen.

## Föråldrade funktioner {#deprecated-features}

Tabellen nedan visar funktioner som har markerats som borttagna i AEM 6.4. I allmänhet är funktioner som ska tas bort i en framtida version först inaktuella, med ett alternativ.

Kunderna rekommenderas att granska om de använder funktionen/funktionen i den aktuella distributionen och planera för att ändra implementeringen så att den använder det alternativ som finns.

<table> 
 <tbody>
  <tr>
   <td>Yta</td> 
   <td>Funktion</td> 
   <td>Ersättning</td> 
  </tr>
  <tr>
   <td>UI</td> 
   <td><p>Adobe planerar inte att göra fler förbättringar av det klassiska användargränssnittet. AEM 6.4 har det klassiska användargränssnittet och kunder som uppgraderar från tidigare versioner kan fortsätta använda det som det är. Observera att Classic-användargränssnittet fortfarande stöds fullt ut när det är inaktuellt. </p> 
    <ul> 
     <li>/libs/cq/core/content/welcome.html</li> 
     <li>/siteadmin</li> 
     <li>/damadmin</li> 
     <li>/mcmadmin</li> 
     <li>/inbox</li> 
     <li>/tagging</li> 
     <li>/cf# (sidredigeraren)</li> 
     <li>/libs/launches/content/admin.html</li> 
     <li>/libs/cq/workflow/content/console.html</li> 
    </ul> </td> 
   <td><p>Kunder rekommenderas att byta till det nya AEM-gränssnittet.</p> <p> </p> </td> 
  </tr>
  <tr>
   <td>Komponenter</td> 
   <td><p>Adobe planerar inte att göra fler förbättringar av de Foundation Components som listas nedan. AEM 6.4 innehåller grundkomponenterna, och kunder som uppgraderar från tidigare versioner kan fortsätta använda dem som de är. Observera att Foundation Components fortfarande stöds fullt ut medan de föråldras. </p> 
    <ul> 
     <li>foundation/components/account/account/account_name</li> 
     <li>grund/komponenter/konto/åtgärder</li> 
     <li>foundation/components/account/passwordreset</li> 
     <li>grund/komponenter/konto/begärandebekräftelse</li> 
     <li>foundation/components/adaptiveimage</li> 
     <li>foundation/components/assetsharingPage</li> 
     <li>foundation/components/breadcrumb</li> 
     <li>grund/komponenter/form/kreditkort</li> 
     <li>grund/komponenter/listchildren</li> 
     <li>grund/komponenter/inloggning</li> 
     <li>grund/komponenter/logotyp</li> 
     <li>foundation/components/mobilefooter</li> 
     <li>foundation/components/mobileimage</li> 
     <li>foundation/components/mobilelist</li> 
     <li>grund/komponenter/mobilelogo</li> 
     <li>foundation/components/mobilereference</li> 
     <li>grund/komponenter/mobiletextimage</li> 
     <li>foundation/components/mobiletopnav</li> 
     <li>grund/komponenter/sökning</li> 
     <li>grund/komponenter/platskarta</li> 
     <li>grund/komponenter/tabell</li> 
     <li>grund/komponenter/verktygsfält</li> 
     <li>grund/komponenter/topnav</li> 
     <li>foundation/components/userinfo</li> 
    </ul> </td> 
   <td>Kunderna rekommenderas att använda kärnkomponenterna för framtida projekt. Befintliga webbplatser behöver inte ändras.</td> 
  </tr>
  <tr>
   <td>Komponenter</td> 
   <td><p>Adobe planerar inte att göra fler förbättringar av de Foundation Components som listas nedan. AEM 6.4 innehåller grundkomponenterna, och kunder som uppgraderar från tidigare versioner kan fortsätta använda dem som de är. Observera att Foundation Components fortfarande stöds fullt ut medan de föråldras.</p> 
    <ul> 
     <li>grund/komponenter/timing</li> 
    </ul> </td> 
   <td>Just nu är det inte tänkt att ersätta något.</td> 
  </tr>
  <tr>
   <td>Portaldirektör</td> 
   <td><p>Portal Director är en uppsättning funktioner som gör det möjligt att lägga upp AEM-innehåll via Portlet i tredjepartsservrar.</p> <p>Adobe planerar inte att göra fler förbättringar av funktionen Portal Director på den plats som listas nedan. AEM 6.4 har Portal Director inkluderat och kunder som uppgraderar från tidigare versioner kan fortsätta använda det som det är. Observera att Portal Direct fortfarande stöds fullt ut när det är föråldrat.</p> 
    <ul> 
     <li>/libs/portal/director</li> 
    </ul> </td> 
   <td>Just nu är det inte tänkt att ersätta något.</td> 
  </tr>
  <tr>
   <td>Portlet-komponent</td> 
   <td><p>Portlet Components under /foundation/components/portlet gör att JSR Portlets i AEM kan användas som komponenter.</p> <p>Adobe planerar inte att göra fler förbättringar av funktionen Portlet Component. Portlet Component ingår i AEM 6.4, och kunder som uppgraderar från tidigare versioner kan fortsätta använda det som det är. Observera att Portlet Component fortfarande har fullt stöd medan det är föråldrat.</p> </td> 
   <td>Just nu är det inte tänkt att ersätta något.</td> 
  </tr>
  <tr>
   <td>Formulär</td> 
   <td><p>Stödet för tjänsten Adobe Central Migration Bridge har tagits bort eftersom Adobe Central-produkten inte längre stöds.</p> </td> 
   <td>Ingen ersättning </td> 
  </tr>
    <tr>
   <td>Formulär</td> 
   <td><p>Användning av JSONObject i Query och OperationOptions har tagits bort. Följande API:er är inaktuella:
   <ul><li>setArguments(JSONObject arguments)</li><li>JSONObject getArguments()</li><li>OperationOptions(String operationId, JSONObject-argument</li><li>JSONObject getArguments()</li><li>void setArguments(JSONObject arguments)</li></ul>
   </p> </td> 
   <td>Använda API:t för IValueMap </td> 
  </tr>
  <tr>
   <td>Formulär</td> 
   <td><p>Tjänsten Central Migration Bridge är inaktuell</p> </td> 
   <td> Ingen ersättning </td> 
  </tr>
  <tr>
   <td>Assets</td> 
   <td><p>Avlastning av resurser har tagits bort från och med AEM 6.4</p> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

## Borttagna funktioner {#removed-features}

Tabellen nedan visar funktioner som har tagits bort från AEM 6.4. Tidigare versioner hade dessa funktioner markerats som föråldrade.

<table> 
 <tbody>
  <tr>
   <td><strong>Yta</strong></td> 
   <td><strong>Funktion</strong></td> 
   <td><strong>Ersättning</strong></td> 
  </tr>
  <tr>
   <td>Aktivitetskarta för analyser</td> 
   <td>Den version av aktivitetskartan som ingår i AEM.</td> 
   <td>På grund av säkerhetsändringar i Adobe Analytics-API:t är det inte längre möjligt att använda den version av Activity Map som ingår i AEM.<br><br>Plugin-programmet <a href="https://docs.adobe.com/content/help/en/analytics/analyze/activity-map/getting-started/get-started-users/activitymap-install.html">ActivityMap från Adobe Analytics</a> bör nu användas.</td> 
  </tr>
  <tr>
   <td>Komponenter-formulär</td> 
   <td>Form Captcha<br /> (foundation/components/form/captcha)</td> 
   <td>Använd komponenten ReCaptcha från Google i stället</td> 
  </tr>
  <tr>
   <td>Komponenter</td> 
   <td>Bildspel<br /> (grund/komponenter/bildspel)</td> 
   <td>Ingen ersättning</td> 
  </tr>
  <tr>
   <td>Komponenter</td> 
   <td>Flash<br /> (grund/komponenter/flash)</td> 
   <td>Ingen ersättning</td> 
  </tr>
  <tr>
   <td>Komponenter</td> 
   <td>Stöd för uppspelning av SWF-filer i videokomponenten<br /> har tagits bort (grund/komponenter/video)</td> 
   <td>Använd inget-flash-baserade videoformat.</td> 
  </tr>
  <tr>
   <td>Komponenter</td> 
   <td>Produkttabell<br /> (commerce/components/product_table)</td> 
   <td>Ingen ersättning</td> 
  </tr>
  <tr>
   <td>Aktivitetshantering</td> 
   <td>Aktivitetshantering<br /> för klassiskt användargränssnitt (/libs/cq/taskmanagement/content/taskmanager.html)</td> 
   <td>Borttagen sedan 6.0. Använd den nya uppgiftshanteringen som kombineras med arbetsflödets användargränssnitt.</td> 
  </tr>
  <tr>
   <td>Arbetsflöde</td> 
   <td>Meddelandegränssnitt som används mellan 5.6 och 6.2<br /> (/libs/cq/workflow/content/notifications.html)</td> 
   <td>Inkorg för arbetsflöde/aem/inbox</td> 
  </tr>
  <tr>
   <td>Formulär</td> 
   <td>Exportera PDF till PDF/E-1-format med PDF Generator har tagits bort.</td> 
   <td>PDF Generator har fortsatt stöd för export av PDF till formaten PDF/A-1a/b, PDF/A-2a/b och PDF/A-3a/b.</td> 
  </tr>
  <tr>
   <td>Formulär</td> 
   <td>Stöd för bilder i dokumentfragment har tagits bort. </td> 
   <td>Interaktiv kommunikation gör det möjligt att använda bilder i tryck- och webbkanaler direkt.<br /> </td> 
  </tr>
    <tr>
   <td>Formulär</td> 
   <td> Uppgradering utanför kontoret </td> 
   <td>Det finns inget stöd för att utföra uppgraderingen utanför platsen <br/> </td> 
  </tr>
  <tr>
   <td>Formulär</td> 
   <td> Sidegrade för TjärMK till DocumentMK-migreringar </td> 
   <td> Du kan exportera data från ett äldre system och sedan importera dem i ett uppdateringssystem. Detaljerade instruktioner finns i AEM Forms om JEE-uppgraderingsdokumentation <br/> </td> 
  </tr>
    <tr>
   <td>Formulär</td> 
 <td>AEM Forms på JEE 32-bitars installationsprogram är inte tillgängligt.</td> 
   <td>Adobe har slutat leverera AEM Forms på JEE 32-bitars installationsprogram. Du kan fortsätta använda 64-bitars installationsprogram för att installera AEM Forms på JEE. </td>  
  </tr>
    <tr>
    <td>Formulär</td> 
    <td>Tog bort stöd för att använda DAM-bilder i Document Fragment Component.</td> 
    <td> Du kan använda komponenterna Bild och Diagram i den interaktiva kommunikationens tryckkanal. Om du använder ett adaptivt dokuments dokumentfragmentkomponent i adaptiva formulär slutar det fungera efter uppgradering till AEM 6.4-formulär. </td>  
  </tr>
  <tr>
   <td>Formulär</td> 
   <td> Funktionen Adaptiva dokument har tagits bort</td> 
   <td> Du kan använda funktionen för interaktiv kommunikation för att skapa tryckt och webbaserad kommunikation. Om du använder adaptiva dokument måste du installera kompatibilitetspaketet för att kunna fortsätta använda befintliga adaptiva dokument<br/> </td> 
  </tr>
    <tr>
    <td>Formulär</td> 
    <td>AEM Forms på JEE-specifik landningssida har tagits bort.</td> 
    <td>AEM Forms på JEE-landningssida ersätts med AEM-landningssida (/aem/start.html) </td>  
  </tr>
   <tr>
   <td>Formulär</td> 
   <td>Stöd för standard-Captcha har tagits bort</td> 
   <td>Använd tjänsten reCAPTCHA från Google.</td> 
  </tr>
  <tr>
   <td>Formulär</td> 
   <td>Stöd för flash-fält i AEM Designer har tagits bort. AEM Designer tillåter inte redigering av Flash-fält som används i ett formulär.</td> 
   <td>Du kan använda AEM Designer som släppts för en tidigare version för att redigera sådana formulär.</td> 
  </tr>
  <tr>
   <td>Communities</td> 
   <td>Stöd för Captcha-verifiering har tagits bort.</td> 
   <td>Använd anpassad Captcha-integrering (till exempel reCAPTCHA från Google) för verifiering.</td> 
  </tr>
 </tbody>
</table>

## Förhandsmeddelande för nästa release {#pre-announcement-for-next-release}


Tabellen nedan innehåller en lista över ändringar för framtida releaser som inte är inaktuella, men som kan påverka kunderna. Dessa tillhandahålls för planeringsändamål.

<table> 
 <tbody>
  <tr>
   <td>Area<br /> </td> 
   <td>Funktion<br /> </td> 
   <td>Meddelande</td> 
  </tr>
  <tr>
   <td>Webbläsarstöd</td> 
   <td>Microsoft Internet Explorer</td> 
   <td>AEM 6.4 är den senaste versionen som stöder Microsoft Internet Explorer 11.</td> 
  </tr>
  <tr>
   <td>Foundation</td> 
   <td>UI Framework</td> 
   <td>Adobe har ersatt komponenterna i användargränssnittet för Coral 2 under 2019. AEM 6.4 bygger helt på Coral UI 3 (introducerades med AEM 6.2). Adobe rekommenderar sina kunder och partners som har byggt anpassade gränssnitt med Coral 2 att ändra dessa till Coral 3. Adobe erbjuder ett verktyg för att konvertera dialogrutor från Coral 2 till Coral 3 - <a href="/help/sites-developing/dialog-conversion.md">Läs mer</a>.</td> 
  </tr>
 </tbody>
</table>
