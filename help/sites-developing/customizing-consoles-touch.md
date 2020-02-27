---
title: Anpassa konsolerna
seo-title: Anpassa konsolerna
description: AEM innehåller olika mekanismer som gör att du kan anpassa konsolerna i din redigeringsinstans
seo-description: AEM innehåller olika mekanismer som gör att du kan anpassa konsolerna i din redigeringsinstans
uuid: f10cea87-ef8a-468e-94ca-89a1017dcf44
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: extending-aem
content-type: reference
discoiquuid: 221ed05b-855d-4dc2-9df6-12fdeabb157a
translation-type: tm+mt
source-git-commit: 1dc15f323dc30d5730e2af6c0e762d623523870d

---


# Anpassa konsolerna{#customizing-the-consoles}

>[!CAUTION]
>
>I det här dokumentet beskrivs hur du anpassar konsoler i det moderna, pekaktiverade användargränssnittet och det gäller inte det klassiska användargränssnittet.

I AEM finns olika mekanismer som gör att du kan anpassa konsolerna (och [sidredigeringsfunktionerna](/help/sites-developing/customizing-page-authoring-touch.md)) i din redigeringsinstans.

* Clientlibs

   Med Clientlibs kan du utöka standardimplementeringen för att få nya funktioner, samtidigt som du återanvänder standardfunktioner, objekt och standardmetoder. När du anpassar kan du skapa ett eget klientbibliotek under `/apps.` Det kan t.ex. innehålla den kod som krävs för den anpassade komponenten.

* Övertäckningar

   Övertäckningar är baserade på noddefinitioner och gör att du kan täcka över standardfunktionerna (i `/libs`) med dina egna anpassade funktioner (i `/apps`). När du skapar en övertäckning krävs inte en 1:1-kopia av originalet, eftersom sammanslagningen av försäljningsresurser tillåter arv.

Dessa kan användas på många sätt för att utöka dina AEM-konsoler. En liten markering beskrivs nedan (på en hög nivå).

>[!NOTE]
>
>Mer information finns i:
>
>* Använda och skapa [klientlibs](/help/sites-developing/clientlibs.md).
>* Använda och skapa [övertäckningar](/help/sites-developing/overlays.md).
>* [Granit](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/index.html)
>
>
Det här avsnittet behandlas också i [AEM Gems](https://docs.adobe.com/content/ddc/en/gems.html) -sessionen - [Anpassa användargränssnittet för AEM 6.0](https://docs.adobe.com/content/ddc/en/gems/user-interface-customization-for-aem-6.html).

>[!CAUTION]
>
>Du ***får*** inte ändra något i `/libs` banan.
>
>Detta beror på att innehållet i `/libs` skrivs över nästa gång du uppgraderar din instans (och kan mycket väl skrivas över när du använder en snabbkorrigering eller ett funktionspaket).
>
>Den rekommenderade metoden för konfiguration och andra ändringar är:
>
>1. Återskapa önskat objekt (t.ex. som det finns i `/libs`) under `/apps`
   >
   >
1. Gör ändringar i `/apps`
>



Följande platser i `/libs` strukturen kan till exempel överlappas:

* Konsoler (alla konsoler baserade på GRA-sidor). till exempel:

   * `/libs/wcm/core/content`

<!-- Needs a review by Engineering -->
<!--
* secondary (inner) rails; for example:

    * `/libs/wcm/core/content/search`

* toolbar(s) (dependent on console; for example sites):

    * default 

      `/libs/wcm/core/content/sites/jcr:content/body/content/header/items/default`

    * selection mode

      `/libs/wcm/core/content/sites/jcr:content/body/content/header/items/selection`

* help menu options (dependent on console; for example sites):

    * `/libs/wcm/core/content/sites/jcr:content/body/help`

* information shown on the card view (dependent on console; for example sites):

    * `/libs/wcm/core/content/sites/jcr:content/body/content/content/items/childpages`

-->
>[!NOTE]
>
>Mer information finns i artikeln [Troubleshooting AEM TouchUI issues](https://helpx.adobe.com/experience-manager/kb/troubleshooting-aem-touchui-issues.html)i kunskapsbasen.

<!-- Needs a review by Engineering -->
<!--
## Code Samples {#code-samples}

Various packages have been made available on Github. These provide code samples related to the tasks covered on this page.

### aem-admin-extension-new-console {#aem-admin-extension-new-console}

`aem-admin-extension-new-console` is a sample package showing how to [create a new AEM 6 console](#create-a-custom-console). This package provides a UI for managing [Launches](/help/sites-authoring/launches.md) and adds a link in the navigation:

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-admin-extension-new-console project on GitHub](https://github.com/Adobe-Marketing-Cloud/aem-admin-extension-new-console)
* Download the project as [a ZIP file](https://github.com/Adobe-Marketing-Cloud/aem-admin-extension-new-console/archive/master.zip)

### aem-admin-extension-customize-sites {#aem-admin-extension-customize-sites}

`aem-admin-extension-customize-sites` is a sample package showing how to customize an existing AEM 6 admin console. This package provides updates to Sites administration:

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-admin-extension-customize-sites project on GitHub](https://github.com/Adobe-Marketing-Cloud/aem-admin-extension-customize-sites)
* Download the project as [a ZIP file](https://github.com/Adobe-Marketing-Cloud/aem-admin-extension-customize-sites/archive/master.zip)
-->

<!-- Needs a review by Engineering -->
<!--
## Create a Custom Console {#create-a-custom-console}

1. You can create a custom console with related actions; for example, Launches at the top level (below Sites):

   This involves:

    * creating the root space definition of your new console ``; for example:

        * `/apps/<yourProject>/admin/ext/launches`

    * this can contain (according to requirements):

        * the corresponding [clientlibs](/help/sites-developing/clientlibs.md) for custom actions and `less`/ `css` definitions

            * `/apps/<yourProject>/admin/ext/launches/clientlibs`

        * components that need to be redefined/adjusted; for example, the breadcrumbs, datasource and the launch

            * `/apps/<yourProject>/admin/ext/launches/components`

        * the Granite UI page resource:

            * `/apps/<yourProject>/admin/ext/launches/content/jcr:content`

              property: `sling:resourceType`

        * the page definition of the console

            * `/apps/<yourProject>/admin/ext/launches/content/jcr:content/head`
            * `/apps/<yourProject>/admin/ext/launches/content/jcr:content/body`

   ![chlimage_1-236](assets/chlimage_1-236.png)

   To use the new console (for example in the [rail for navigation](#add-new-navigation-option-to-rail)) an ID is used, so that it can be explicitly referenced. The ID is used to connect the console and its navigation definition. The ID is defined in the `rail` node of the page; for example, for the Sites console:

    * the rail node is: 

      `/libs/wcm/core/content/sites/jcr:content/body/rail`

        * here the `currentId` property is defined: 

          `currentId` = `cq-sites`

   For the Launches console example:

    * the node is:

        * `/apps/<yourProject>/admin/ext/launches/content/jcr:content/body/rail`

    * with the following properties:

        * `currentId` = `cq-launches`
        * `sling:resourceType` = `granite/ui/components/endor/navcolumns`
        * `srcPath` = `cq/core/content/nav`
-->

## Anpassa standardvyn för en konsol {#customizing-the-default-view-for-a-console}

Du kan anpassa standardvyn (kolumn, kort, lista) för en konsol:

1. Du kan ändra ordningen på vyerna genom att ersätta den önskade posten under:

   `/libs/wcm/core/content/sites/jcr:content/views`

   Den första posten blir standard.

   De tillgängliga noderna motsvarar de visningsalternativ som är tillgängliga:

   * `column`
   * `card`
   * `list`

1. I en övertäckning för list:

   `/apps/wcm/core/content/sites/jcr:content/views/list`

   Definiera följande egenskap:

   * **Namn**: `sling:orderBefore`
   * **Typ**: `String`
   * **Värde**: `column`

<!-- Needs a review by Engineering -->
<!--
`aem-admin-extension-customize-sites` is a sample package showing how to customize an existing AEM 6 admin console. This package provides updates to Sites administration:

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-admin-extension-customize-sites project on GitHub](https://github.com/Adobe-Marketing-Cloud/aem-admin-extension-customize-sites)
* Download the project as [a ZIP file](https://github.com/Adobe-Marketing-Cloud/aem-admin-extension-customize-sites/archive/master.zip)
-->

<!-- Needs a review by Engineering -->
<!--
### Add New Navigation Option to Rail {#add-new-navigation-option-to-rail}

1. You can add a navigation entry in the rail (for example, a [custom console](#create-a-custom-console) such as Launches).

   To do this, you create an overlay of:

   `/libs/cq/core/content/nav`

   In the `/apps` overlay:

   `/apps/cq/core/content/nav`

   Create the new nodes and properties:

   ![chlimage_1-237](assets/chlimage_1-237.png)

    * Extend navigation:

        * `/apps/cq/core/content/nav/launches`

    * Specify location in the tree:

        * property: `sling:orderBefore`

    * To create the connection, the `id` property references (i.e. must be the same as) the `currentID` property [for the appropriate console](#create-a-custom-console):

        * property: `id`
        * value: same as for your console (e.g. `cq-launches`) 

          for example: the same value as the `currentId` property on:

          `/apps/<yourProject>/admin/ext/launches/content/jcr:content/body/rail`
-->

## Lägg till ny åtgärd i verktygsfältet {#add-new-action-to-the-toolbar}

1. Du kan skapa egna komponenter och inkludera motsvarande klientbibliotek för anpassade åtgärder. Exempel: en **åtgärd från Befordra till Twitter** på:

   `/apps/wcm/core/clientlibs/sites/js/twitter.js`

   Detta kan sedan anslutas till ett verktygsfältsobjekt på konsolen:

   `/apps/<yourProject>/admin/ext/launches`

   I markeringsläge:

   `content/jcr:content/body/content/header/items/selection/items/twitter`

## Begränsa en verktygsfältåtgärd till en viss grupp {#restrict-a-toolbar-action-to-a-specific-group}

1. Du kan använda ett anpassat återgivningsvillkor om du vill täcka över standardåtgärden och ange särskilda villkor som måste uppfyllas innan den återges.

   Skapa till exempel en komponent som styr återgivningsvillkoren enligt grupp:

   `/apps/myapp/components/renderconditions/group`

1. Så här använder du åtgärden Skapa plats på webbplatskonsolen:

   `/libs/wcm/core/content/sites`

   Skapa övertäckningen:

   `/apps/wcm/core/content/sites`

1. Lägg sedan till återgivningsvillkoret för åtgärden:

   `jcr:content/body/content/header/items/default/items/create/items/createsite/rendercondition`

   Med hjälp av egenskaper på den här noden kan du definiera vilka som `groups` får utföra den specifika åtgärden;
till exempel `administrators`

<!-- Needs a review by Engineering -->
<!--
## Remove Access to Navigation Option on Rail {#remove-access-to-navigation-option-on-rail}

1. You can rename a navigation entry in the rail by overlaying the required entry from under:

   `/libs/cq/core/content/nav`

   The nodes available correlate to the navigation options in the rail:

    * `projects`
    * `sites`
    * `assets`
    * `apps`
    * `forms`
    * `screens`
    * `personalization`
    * `commerce`
    * `tools`
    * `communities`

1. For example, on a overlay at:

   `/apps/cq/core/content/nav/sites`

   Define the following property:

    * **Name**: `sling:hideResource`
    * **Type**: `String` 
    * **Value**: `true`

`aem-admin-extension-customize-sites` is a sample package showing how to customize an existing AEM 6 admin console. This package provides updates to Sites administration:

CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-admin-extension-new-console project on GitHub](https://github.com/Adobe-Marketing-Cloud/aem-admin-extension-new-console)
* Download the project as [a ZIP file](https://github.com/Adobe-Marketing-Cloud/aem-admin-extension-new-console/archive/master.zip)
-->

<!-- Needs a review by Engineering -->
<!--
## Restrict Access to Navigation Option on Rail {#restrict-access-to-navigation-option-on-rail}

You can restrict access to a navigation option using ACLs:

1. Open the [user and/or group management](/help/sites-administering/security.md) and select the user/group you want to restrict access for.

   >[!NOTE]
   >
   >Avoid assigning/restricting permissions on a user-by-user basis. It is [recommended to use groups](/help/sites-administering/security.md#best-practices).

1. Remove access [permissions](/help/sites-administering/security.md#permissions) to the appropriate node(s) under `/libs/cq/core/content/nav/sites`. These correlate to the navigation options in the rail:

    * `projects`
    * `sites`
    * `assets`
    * `apps`
    * `forms`
    * `screens`
    * `personalization`
    * `commerce`
    * `tools`
    * `communities`
-->

## Anpassa kolumner i listvyn {#customizing-columns-in-the-list-view}

>[!NOTE]
>
>Den här funktionen är optimerad för kolumner med textfält; för andra datatyper är det möjligt att täcka över `cq/gui/components/siteadmin/admin/listview/columns/analyticscolumnrenderer` in `/apps`.

<!-- Needs a review by Engineering -->
<!--
CODE ON GITHUB

You can find the code of this page on GitHub

* [Open aem-sites-extension-listview-columns project on GitHub](https://github.com/Adobe-Marketing-Cloud/aem-sites-extension-listview-columns)
* Download the project as [a ZIP file](https://github.com/Adobe-Marketing-Cloud/aem-sites-extension-listview-columns/archive/master.zip)
-->

Så här anpassar du kolumnerna i listvyn:

1. Lägg över listan med tillgängliga kolumner.

   * På noden:

      `/apps/wcm/core/content/common/availablecolumns`

   * Lägg till nya kolumner eller ta bort befintliga.
   Mer information finns i [Använda övertäckningar (och Samla resurser)](/help/sites-developing/overlays.md) .

1. Valfritt:

   * Om du vill lägga till ytterligare data måste du skriva en ` [PageInforProvider](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/wcm/api/PageInfoProvider.html)` med en

      `pageInfoProviderType` -egenskap.
   Se till exempel klassen/paketet som bifogas (från GitHub) nedan.

1. Nu kan du markera kolumnen i listvyns kolumnkonfigurator.

## Filtreringsresurser {#filtering-resources}

När du använder en konsol är ett vanligt användningsfall när användaren måste välja bland resurser (t.ex. sidor, komponenter, resurser osv.). Detta kan vara en lista som författaren till exempel måste välja ett objekt från.

För att hålla listan i en rimlig storlek och även relevant för användningsfallet kan ett filter implementeras i form av ett anpassat predikat. Mer information finns i [den här artikeln](/help/sites-developing/customizing-page-authoring-touch.md#filtering-resources) .
