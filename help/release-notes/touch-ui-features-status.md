---
title: Funktionsstatus för Touch UI
seo-title: Funktionsstatus för Touch UI
description: Versionsinformation om användargränssnittet i Adobe Experience Manager 6.3 Touch.
seo-description: Versionsinformation om användargränssnittet i Adobe Experience Manager 6.3 Touch.
uuid: dc335334-6c50-4cee-8a2e-183958742686
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 482b5eb0-1b15-4f10-a9d8-3b72dd74acf8
translation-type: tm+mt
source-git-commit: db26dd05f6c0997eeda462f27971cbcfa6737527
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 1%

---


# Touch UI Feature Status {#touch-ui-feature-status}

>[!CAUTION]
>
>I version 6.4 av AEM är det klassiska användargränssnittet [föråldrat](/help/release-notes/deprecated-removed-features.md). Adobe planerar inte att göra ytterligare förbättringar av det klassiska användargränssnittet och användare uppmuntras att utnyttja de kraftfulla nya funktionerna som finns i det pekaktiverade användargränssnittet.

Från och med version 6.0 har AEM introducerat ett nytt användargränssnitt som kallas &quot;pekaktiverat användargränssnitt&quot; (kallas även&quot;pekgränssnitt&quot;) som är anpassat till Adobe Marketing Cloud och till de övergripande riktlinjerna för användargränssnittet i Adobe. Med nästan alla funktionspartitioner har detta blivit standardgränssnittet i AEM med det äldre skrivbordsorienterade gränssnittet som kallas &quot;klassiskt gränssnitt&quot;.

De flesta funktioner finns i det beröringskänsliga användargränssnittet, men det finns funktioner som ännu inte är fullständiga och som kommer att läggas till i framtida versioner.

Följande lista visar aktuell status för funktionerna som implementerats i AEM 6.4.

Rekommendationer för kunder som uppgraderar till AEM 6.4 finns i [användargränssnittet Recommendations för kunder](/help/sites-deploying/ui-recommendations.md).

>[!NOTE]
>
>Observera att den här sidan endast omfattar funktionsparitet med klassiskt användargränssnitt.
>
>Funktioner som lagts till och är unika för det beröringsaktiverade användargränssnittet och som inte finns i det klassiska användargränssnittet visas inte.

>[!NOTE]
>
>Denna förteckning skall vara fullständig, men skall inte anses uttömmande.

## Förklaring {#legend}

* **Fullständigt**: Funktionen är helt tillgänglig i det beröringskänsliga användargränssnittet
* **Mest**: Funktionen är oftast tillgänglig i det beröringskänsliga användargränssnittet.
* **Saknas**: Funktionen finns inte i det beröringsaktiverade användargränssnittet, det klassiska användargränssnittet måste användas för att utföra den här åtgärden.
* **Ersatt**: Funktionen har ersatts med en ny implementering som fungerar annorlunda.
* **Borttagen**: Funktionen finns inte längre i det beröringskänsliga användargränssnittet och kommer inte att ersättas.

## Funktionsstatus: Webbplatsadministratör {#feature-status-sites-admin}

Det här är en lista över funktioner som den klassiska gränssnittsadministratören ( `/siteadmin`) har och status i det beröringskänsliga användargränssnittet ( `/sites.html`).

<table> 
 <tbody>
  <tr>
   <td><strong>Funktion<br /> </strong></td> 
   <td><strong>Status<br /> </strong></td> 
   <td><strong>Kommentar</strong></td> 
  </tr>
  <tr>
   <td>Navigera i webbplatshierarkin</td> 
   <td>Fullständig<br /> </td> 
   <td>AEM 6.4 introducerade en <a href="/help/sites-authoring/basic-handling.md#content-tree">innehållsträdsvy</a>.</td> 
  </tr>
  <tr>
   <td>Starta arbetsflöde</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Skapa ny sida</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Skapa ny plats</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Skapa ny start</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Skapa ny livecopy <br /> </td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Skapa mapp</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Visa publiceringsstatus</td> 
   <td>Mest</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Sökning</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Kopiera/klistra in sida (duplicera)</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Flytta sida/sidor</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publicera sidor</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publicera sidor utan replikeringsrättigheter</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publicera senare</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publiceringsträd</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Avpublicera sidor</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Avpublicera sidor utan replikeringsrättigheter</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Avpublicera senare</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Ta bort</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Lås/lås upp</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Visa/redigera egenskaper</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Ange behörigheter på sidor</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Versionshistorik</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Återställ version</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Återställ träd och återställa borttagna sidor</td> 
   <td>Saknas</td> 
   <td>Använd klassiskt gränssnitt.</td> 
  </tr>
  <tr>
   <td>Visa skillnad mellan gammal och aktuell version<br /> </td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Livecopy-åtgärder (utrullning)</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Se språkkopior</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Sök och ersätt</td> 
   <td>Saknas<br /> </td> 
   <td>Använd klassiskt gränssnitt.</td> 
  </tr>
  <tr>
   <td>Inkorgen för meddelanden (JCR-händelser)</td> 
   <td>Saknas</td> 
   <td>Använd klassiskt gränssnitt. Ersätts med annan implementering.</td> 
  </tr>
  <tr>
   <td>Referenser</td> 
   <td>Mest</td> 
   <td>Visning av inkommande sidlänkar kommer att läggas till i 2019-versionen av AEM.</td> 
  </tr>
 </tbody>
</table>

## Funktionsstatus: Sidredigeraren {#feature-status-page-editor}

Det här är en lista över funktioner som den klassiska sidredigeraren i användargränssnittet ( `/cf#`) har och status för den beröringsaktiverade ( `/editor.html`).

<table> 
 <tbody>
  <tr>
   <td><strong>Funktion</strong></td> 
   <td><strong>Status</strong></td> 
   <td><strong>Kommentar</strong></td> 
  </tr>
  <tr>
   <td>Redigera webbsidor</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Redigera mobilwebbsidor<br /> </td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Redigera innehåll som importerats via designimporteraren<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Redigera e-post</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Redigera mobilappar</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Redigera Forms</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Redigera erbjudanden</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Redigera arbetsflödesmodeller<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>kod: Redigera och förhandsgranska</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Responsiv förhandsgranskning<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Läge: Redigera design</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Läge: Ställning</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Läge: Live Copy-status<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Lägg till anteckningar</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Redigera egenskaper<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Rullande sida</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Starta och visa arbetsflöde</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Hantering av arbetsflödespaket</td> 
   <td>Mest</td> 
   <td>Helt åtkomligt i användargränssnittet med pekfunktion. Flera arbetsflödesnyttolaster visas fortfarande i det klassiska användargränssnittet.<br /> </td> 
  </tr>
  <tr>
   <td>Lås/lås upp sida</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Publicera sidan <br /> </td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Avpublicera sida</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Kopiera sida</td> 
   <td>Borttagen<br /> </td> 
   <td>Använd Webbplatsadministratör för att <a href="/help/sites-authoring/managing-pages.md#copying-and-pasting-a-page">kopiera sidor</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Flytta sida</td> 
   <td>Borttagen</td> 
   <td>Använd Webbplatsadministratör för att <a href="/help/sites-authoring/managing-pages.md#moving-or-renaming-a-page">flytta sidor</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Ta bort sida</td> 
   <td>Borttagen</td> 
   <td>Använd Webbplatsadministratör för att <a href="/help/sites-authoring/managing-pages.md#deleting-a-page">ta bort sidor</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Visa referenser</td> 
   <td>Borttagen</td> 
   <td>Använd Webbplatsadministratör för att <a href="/help/sites-authoring/author-environment-tools.md#references">se den detaljerade referenslistan</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Granskningslogg</td> 
   <td>Borttagen</td> 
   <td>Använd Webbplatsadministratör och <a href="/help/sites-authoring/author-environment-tools.md#events-timeline">öppna aktivitetsfält</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Skapa version</td> 
   <td>Borttagen</td> 
   <td>Använd Webbplatsadministratör för att <a href="/help/sites-authoring/working-with-page-versions.md#creating-a-new-version">skapa nya versioner</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Återställ version</td> 
   <td>Borttagen</td> 
   <td>Använd Webbplatsadministratör för att <a href="/help/sites-authoring/working-with-page-versions.md#reverting-to-a-page-version">återställa versioner</a>.</td> 
  </tr>
  <tr>
   <td>Växla startprogram</td> 
   <td>Borttagen</td> 
   <td>Använd Webbplatsadministratör för att <a href="/help/sites-authoring/launches-promoting.md">växla mellan starter</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Översätt sida</td> 
   <td>Borttagen</td> 
   <td>Använd Webbplatsadministratör för att <a href="/help/sites-administering/tc-manage.md">lägga till sida i översättningsprojekt</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Timewarp (välj datum/tid och bläddra på webbplatsen som den såg ut)<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Ange behörigheter</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Klientkontextgränssnitt<br /> </td> 
   <td>Ersatt</td> 
   <td>Använd gränssnittet <a href="/help/sites-authoring/ch-previewing.md">ContextHub</a> som fortsätter framåt.</td> 
  </tr>
  <tr>
   <td>Innehållssökning för de olika medietyperna<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Komponentlista</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Kopiera och klistra in komponenter<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Lista över komponenter i Urklipp</td> 
   <td>Saknas</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Ångra/Gör om</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Dra och släpp innehåll i komponentplatshållaren</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Dra och släpp innehåll direkt i en parsys platshållare med automatisk komponentgenerering<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

## Funktionsstatus: Text-, tabell- och bildredigerare {#feature-status-text-table-and-image-editors}

Det här är en lista över funktioner som det klassiska användargränssnittet för text, tabell och bildredigering har och status i det beröringskänsliga användargränssnittet.

<table> 
 <tbody>
  <tr>
   <td><strong>Funktion</strong></td> 
   <td><strong>Status </strong></td> 
   <td><strong>Kommentar<br /> </strong></td> 
  </tr>
  <tr>
   <td>RTF-redigerare</td> 
   <td>Slutförd</td> 
   <td>Kan användas på plats, i dialogrutor och i helskärmsläge.</td> 
  </tr>
  <tr>
   <td>Aktivera/inaktivera RTE-plugin-program</td> 
   <td>Fullständig<br /> </td> 
   <td>Kan göras med <a href="/help/sites-authoring/templates.md">mallredigeraren</a>.</td> 
  </tr>
  <tr>
   <td>Använd RTE för oformaterad text</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Länkar och ankarpunkt</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Teckenuppsättning</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Kopiera/klistra in</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Klistra in från Microsoft Word<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Sök och ersätt</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Textformat (fet, ...)</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Under och upphöjd text</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Justera</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Listor (punkt / nummer)</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Styckeformat</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Textformat</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Källredigerare (Redigera HTML)<br /> </td> 
   <td>Fullständig<br /> </td> 
   <td>Endast tillgängligt i dialogruta och helskärm.<br /> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Stavningskontroll</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Tabell (inbäddad tabellredigerare)</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Ångra/Gör om<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>RTE-plugin: Tillåt textbundna bilder</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Tabellredigerare</td> 
   <td>Slutförd</td> 
   <td>Kan användas på plats, i dialogruta och i helskärmsläge.<br /> </td> 
  </tr>
  <tr>
   <td>Dra och släpp bild i tabellcell<br /> </td> 
   <td>Slutförd</td> 
   <td>Användbart online</td> 
  </tr>
  <tr>
   <td>Bildredigerare<br /> </td> 
   <td>Slutförd</td> 
   <td>Kan användas på plats, i dialogruta och i helskärmsläge.<br /> </td> 
  </tr>
  <tr>
   <td>Aktivera/inaktivera IPE-plugin-program</td> 
   <td>Slutförd</td> 
   <td>Det finns nu ett användargränssnitt i <a href="/help/sites-authoring/templates.md">mallredigeraren</a>.</td> 
  </tr>
  <tr>
   <td>IPE-plugin: Beskär</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plugin: Vänd</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plugin: Ångra/Gör om</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plugin: Bildschema</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plugin: Rotera</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>IPE-plugin: Zooma</td> 
   <td>Fullständig<br /> </td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

## Funktionsstatus: Verktyg {#feature-status-tools}

Det här är en lista över olika verktyg som det klassiska användargränssnittet har och status i det beröringsaktiverade användargränssnittet.

<table> 
 <tbody>
  <tr>
   <td><strong>Funktion<br /> </strong></td> 
   <td><strong>Status<br /> </strong></td> 
   <td><strong>Kommentar</strong></td> 
  </tr>
  <tr>
   <td>Aktivitetshantering</td> 
   <td>Ersatt</td> 
   <td>6.0 introducerade <a href="/help/sites-authoring/projects.md">Projekt och uppgifter</a>.<br /> </td> 
  </tr>
  <tr>
   <td>Inkorgen för arbetsflöde<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Konfiguration av arbetsflöde till sidmall (<code>/etc/workflow/wcm/templates.html</code>)</td> 
   <td>Saknas<br /> </td> 
   <td>Använd klassiskt gränssnitt.</td> 
  </tr>
  <tr>
   <td>Taggning av administratörsgränssnitt<br /> </td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>MSM/Blueprint Control Center</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Gränssnitt för BluPrint Manager</td> 
   <td>Slutförd</td> 
   <td> </td> 
  </tr>
  <tr>
   <td>Gränssnitt för konfiguration av utrullning</td> 
   <td>Saknas</td> 
   <td>Använd klassiskt gränssnitt.</td> 
  </tr>
  <tr>
   <td>Användare, grupper och behörigheter, användargränssnitt<br /> </td> 
   <td>Mest komplett<br /> </td> 
   <td>Använd Classic UI för redigering av avancerade behörigheter.<br /> </td> 
  </tr>
  <tr>
   <td>Rensa versioner (<code>/etc/versioning/purge.html</code>)</td> 
   <td>Saknas</td> 
   <td>Använd klassiskt gränssnitt.</td> 
  </tr>
  <tr>
   <td>Extern länkkontroll (<code>/etc/linkchecker.html</code>)</td> 
   <td>Saknas</td> 
   <td>Använd klassiskt gränssnitt.<br /> </td> 
  </tr>
  <tr>
   <td>Massredigerare (<code>/etc/importers/bulkeditor.html</code>)</td> 
   <td>Saknas<br /> </td> 
   <td>Använd klassiskt gränssnitt.</td> 
  </tr>
 </tbody>
</table>

