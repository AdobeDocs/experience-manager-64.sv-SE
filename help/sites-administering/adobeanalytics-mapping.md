---
title: Mappa komponentdata med Adobe Analytics-egenskaper
seo-title: Mappa komponentdata med Adobe Analytics-egenskaper
description: Lär dig hur du mappar komponentdata med SiteCatalyst-egenskaper.
seo-description: Lär dig hur du mappar komponentdata med SiteCatalyst-egenskaper.
uuid: accdb0e8-957c-4617-9a8d-eccc24ac436e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 2a9be3b7-b325-4d74-a5bc-8d24db491920
translation-type: tm+mt
source-git-commit: 98fae2d51d73bda946f3c398e9276fe4d5a8a0fe
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 0%

---


# Mappa komponentdata med Adobe Analytics-egenskaper{#mapping-component-data-with-adobe-analytics-properties}

Lägg till komponenter i ramverket som samlar in data som ska skickas till Adobe Analytics. Komponenter som är utformade för att samla in analysdata lagrar data i lämplig **CQ-variabel**. När du lägger till en sådan komponent i ett ramverk visas en lista med CQ-variabler så att du kan använda alla till rätt **Analytics-variabel**.

![aa-11](assets/aa-11.png)

När **AEM** är öppen visas Analytics-variablerna i innehållssökaren.

![aa-12](assets/aa-12.png)

Du kan mappa flera Analytics-variabler med samma **CQ-variabel**.

![chlimage_1-155](assets/chlimage_1-155.png)

Mappade data skickas till Adobe Analytics när sidan läses in och följande villkor uppfylls:

* Sidan är kopplad till ramverket.
* Sidan använder de komponenter som har lagts till i ramverket.

Använd följande procedur för att mappa CQ-komponentvariabler med Adobe Analytics rapportegenskaper.

1. I **AEM vy** drar du en spårningskomponent från sidosparken till ramverket. Dra till exempel komponenten **Sida** från kategorin **Allmänt** .

   ![aa-13](assets/aa-13.png)

   Det finns flera standardkomponentgrupper: **General**, **Commerce**, **Communities**, **Search &amp; Promote** och **Other**. Din AEM kan vara konfigurerad att visa olika grupper och komponenter.

1. Om du vill mappa Adobe Analytics-variabler med variabler som är definierade i komponenten drar du en **Analytics-variabel** från innehållssökaren till ett fält i spårningskomponenten. Dra till exempel `Page Name (pageName)` till `pagedata.title`.

   ![aa-14](assets/aa-14.png)

   >[!NOTE]
   >
   >Det Report Suite-ID (RSID) som har valts för ramverket avgör vilka Adobe Analytics-variabler som visas i innehållssökaren.

1. Upprepa de två föregående stegen för andra komponenter och variabler.

   >[!NOTE]
   >
   >Du kan mappa flera analysvariabler (t.ex. `props`, `eVars`, `events`) till samma CQ-variabel (t.ex. `pagedata.title`)

   >[!CAUTION]
   >
   >Vi rekommenderar starkt följande:
   >
   >* `eVars` och mappas `props` till CQ-variabler som börjar med antingen `pagedata.X` eller `eventdata.X`
   >* Händelser bör mappas till variabler som börjar med `eventdata.events.X`


1. Om du vill göra ramverket tillgängligt på publiceringsinstansen på webbplatsen öppnar du fliken **Page **sidespark och klickar på **Activate Framework.**

## Mappa produktrelaterade variabler {#mapping-product-related-variables}

AEM använder en konvention för att namnge produktrelaterade variabler och händelser som ska mappas till Adobe Analytics produktrelaterade egenskaper:

| CQ-variabel | Analysvariabel | Beskrivning |
|---|---|---|
| `product.category` | `product.categor`y (konverteringsvariabel) | Produktkategorin. |
| `product.sku` | `product.sku` (konverteringsvariabel) | Produktens sku. |
| `product.quantity` | `product.quantity` (konverteringsvariabel) | Antalet produkter som köpts. |
| `product.price` | `product.price` (konverteringsvariabel) | Produktpriset. |
| `product.events.*eventName*` | Vilka lyckade händelser som ska kopplas till produkten i din rapport. | `product.events` är prefixet för händelser med namnet *eventName.* |
| `product.evars.*eVarName*` | Konverteringsvariablerna ( `eVar`) som ska associeras med produkten. | `product.evars` är prefixet för eVar med namnet *eVarName.* |

Several AEM Commerce components use these variable names.

>[!NOTE]
>
>Do not map the Adobe Analytics Products property to a CQ variable. Configuring product-related mappings as described in the table is effectively equivalent to mapping the Products variable.

## Checking reports on Adobe Analytics {#checking-reports-on-adobe-analytics}

1. Login to the Adobe Analytics website using the same credentials provided to AEM.
1. Make sure the RSID selected is the one used in the previous steps.
1. In **Reports** (on the left side of the page) select **Custom Conversion**, then **Custom Conversion 1-10** and select the variable coresponding to `eVar7`

1. Depending on the version of Adobe Analytics that you are using, you need to wait on average 45 minutes for the report to be updated with the search term used; e.g. aubergine in the example

## Using the Content Finder (cf#) with Adobe Analytics frameworks {#using-the-content-finder-cf-with-adobe-analytics-frameworks}

Initially, when you open an Adobe Analytics framework the content finder contains predefined Analytics variables under:

* Traffic

* Konvertering

* Händelser

When an RSID is selected all the variables belonging to that RSID get added to the list.\
The `cf#` is needed in order to map Analytics variables to the CQ variables present on the different tracking components. See Setting Up a Framework for Basic Tracking.

Depending on the view selected for the framework, the content finder will be populated by either Analytics variables (in AEM view) or CQ variables (in Analytics view).

The list can be manipulated in the following ways:

1. When in **AEM view**, the list can be filtered depending on what variable type is selected using the 3 filter buttons:

   * If *no button* is selected, the list shows the full list.
   * If the **Traffic** button is selected, the list will only show the variables belonging to the Traffic section
   * If the **Conversion** button is selected, the list will only show the variables belonging to the Conversion section.
   * Om knappen **Händelser** är markerad visas bara de variabler som tillhör avsnittet Händelser i listan.

   >[!NOTE]
   >
   >Only one filter button can be active at once.

   >[!NOTE]
   >
   >Search&amp;Promote variables belong to the Conversion section as well.

   1. Listan har också en sökfunktion som filtrerar elementen efter den text som anges i sökfältet.
   1. If a filter option is activated while searching for elements in the list, the results displayed will be filtered according to the active button as well.
   1. Listan kan läsas in igen när som helst med hjälp av pilknappen.
   1. If multiple RSIDs are selected on the framework, all variables in the list will be displayed using all labels used within the RSIDs selected.


1. I Adobe Analytics-vyn visar Content Finder alla CQ-variabler som tillhör spårningskomponenterna som dras i CQ-vyn.

   * e.g. in case the **Download component **is the *only one dragged* in CQ view (which has two mappable variables *eventdata.downloadLink* and *eventdata.events.startDownload*), the Content Finder wil look like this when switching to Adobe Analytics view:

   ![aa-22](assets/aa-22.png)

   * Variablerna kan dras &amp;släppas till alla Adobe Analytics-variabler som tillhör någon av de tre variabelavsnitten (**Trafik**, **Konvertering** och **Händelser**).
   * When dragging a new tracking component onto the framework in CQ view, the CQ variables belonging to the component get automatically added to the Content Finder(cf#) in Adobe Analytics view.

   >[!NOTE]
   >
   >Only one CQ variable can be mapped to a Adobe Analytics variable at once

## Använda AEM vy och analysvy {#using-aem-view-and-analytics-view}

At any given time, users have the option to switch between 2 ways of viewing the Adobe Analytics mappings when on a framework page. The 2 views provide a better overview of the mappings within the framework, from 2 distinct perspectives.

### AEM View {#aem-view}

![aa-23](assets/aa-23.png)

Taking the above image as an example, the **AEM view** has the following properties:

1. This is the default view when the framework opens.
1. Left side: the content finder(cf#) is populated by Adobe Analytics variables based on the RSID(s) selected.
1. Flikrubriker (**AEM vy** och **analysvy**): använder du dessa för att växla mellan de två vyerna.

1. **AEM view**:

   1. If the framework has components that are inherited from its parent, they will be listed here, along with the variables mapped to the components.

      1. Inherited components are locked.
      1. To unlock an inherited component, just double-click on the padlock next to the component&#39;s name
      1. In order to revert the inheritance you must delete the unlocked component; after which it will regain its locked status.
   1. **Drag components here to include them in the analytics framework**: Components can be dragged from the Sidekick and dropped here.
   1. You can find all of the components that are currently included in the analytics framework:

      1. Om du vill lägga till en komponent drar du den från sidosparkens komponentflik
      1. To delete a component and all of its mappings, select Delete from the component&#39;s context menu then accept the deletion on the confirmation dialogue.
      1. Tänk på att en komponent bara kan tas bort från ramverket som den skapades i och inte kan tas bort från underordnade ramverk i traditionell mening (de kan bara skrivas över).


### Analysvy {#analytics-view}

![aa-24](assets/aa-24.png)

1. Du kommer åt den här vyn genom att växla till fliken **Analysvy** i ramverket.
1. Left side: Content Finder (cf#) populated by CQ variables based on the components dragged onto the framework in CQ view.
1. Flikrubriker (**AEM vy** och **analysvy**): använder du dessa för att växla mellan de två vyerna.

1. De tre tabellerna (Traffic, Conversion, Event) innehåller alla tillgängliga Adobe Analytics-variabler. som tillhör de markerade RSID:erna. Mappningarna som visas här ska vara desamma som i AEM:

   * **Trafik**:

      * Trafikvariabel ( `prop1`) mappad till en CQ-variabel ( `eventdata.downloadLink`)
      * When the component has a Padlock next to it, this means it is inherited from a parent framework and thus cannot be edited
   * **Conversion**:

      * Conversion variable ( `eVar1`) mapped to a CQ variable ( `pagedata.title`)
      * Conversion variable ( `eVar3`) mapped to a javascript expression added inline by double-clicking on the CQ variable field and entering the code manually
   * **Händelse**:

      * Event variable ( `event1`) mapped to a CQ event ( `eventdata.events.pageView`)



>[!NOTE]
>
>The CQ variable column of any table can be filled inline as well, by double-clicking on the field and adding text to it. These fields accept javascript as an input.
>
>* e.g. next to `prop3` you can add
>* `'`* `Adobe:'+pagedata.title+':'+pagedata.sitesection`\
   >  to send the *title* of a page concatenated with its *sitesection* using *:* (colon) and prefixed with *Adobe* as `prop3`


>[!CAUTION]
>
>Only one CQ variable can be mapped to a Adobe Analytics variable at any given time.

