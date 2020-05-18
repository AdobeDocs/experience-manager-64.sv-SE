---
title: Utöka resurssökning
description: Utöka sökfunktionerna i AEM Resurser utöver färdiga sökningar efter resurser efter strängar.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0560d47dcffbf9b74a36ea00e118f8a176adafcd
workflow-type: tm+mt
source-wordcount: '830'
ht-degree: 11%

---


# Utöka resurssökning {#extending-assets-search}

Du kan utöka sökfunktionerna i Adobe Experience Manager (AEM) Assets. När allt är klart söker AEM Resurser efter resurser efter strängar.

Sökningen görs via gränssnittet i QueryBuilder så att sökningen kan anpassas med flera predikat. Du kan täcka över standarduppsättningen med predikat i följande katalog: `/apps/dam/content/search/searchpanel/facets`.

Du kan även lägga till ytterligare flikar på AEM Resurser-administratörspanelen.

>[!CAUTION]
>
>Från och med AEM 6.4 är det klassiska användargränssnittet föråldrat. Information finns i [Föråldrade och Borttagna funktioner](../release-notes/deprecated-removed-features.md). Du rekommenderas att använda användargränssnittet med pekskärmsfunktioner. Anpassa finns i [Sök efter ansikten](search-facets.md).

## Överläggning {#overlaying}

Om du vill täcka över de förkonfigurerade predikaten kopierar du `facets` noden från `/libs/dam/content/search/searchpanel` till `/apps/dam/content/search/searchpanel/` eller anger en annan `facetURL` egenskap i sökpanelens konfiguration (standardvärdet är `/libs/dam/content/search/searchpanel/facets.overlay.infinity.json`).

![screen_shot_2012-06-05at113619am](assets/screen_shot_2012-06-05at113619am.png)

>[!NOTE]
>
>Som standard finns inte katalogstrukturen under/ `apps` och måste skapas. Kontrollera att nodtyperna matchar dem under / `libs`.


## Lägga till tabbar {#adding-tabs}

Du kan lägga till fler sökflikar genom att konfigurera dem i AEM Resurser Admin. Så här skapar du ytterligare flikar:

1. Skapa mappstrukturen `/apps/wcm/core/content/damadmin/tabs,`om den inte redan finns, och kopiera `tabs` noden från `/libs/wcm/core/content/damadmin` och klistra in den.
1. Skapa och konfigurera den andra fliken efter behov.

   >[!NOTE]
   >
   >När du skapar en andra platshållarsökpanel måste du ange en `id` egenskap för att förhindra formulärkonflikter.

## Skapa anpassade predikat {#creating-custom-predicates}

AEM Resurser innehåller en uppsättning fördefinierade predikat som kan användas för att anpassa en resursdelssida. Att anpassa en resurs på det här sättet beskrivs i [Skapa och konfigurera en resursdelssida](assets-finder-editor.md#creating-and-configuring-an-asset-share-page).

Förutom att använda befintliga predikat kan AEM-utvecklare även skapa egna predikat med [Query Builder API](/help/sites-developing/querybuilder-api.md).

Det krävs grundläggande kunskaper om [widgetramverket](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html)för att kunna skapa anpassade predikat.

Det bästa sättet är att kopiera ett befintligt predikat och justera det. Exempelpredikat finns i `/libs/cq/search/components/predicates`.

### Exempel: Skapa ett enkelt egenskapspredikat {#example-build-a-simple-property-predicate}

Så här skapar du ett egenskapspredikat:

1. Skapa till exempel en komponentmapp i projektkatalogen `/apps/geometrixx/components/titlepredicate`.
1. Lägg till `content.xml`:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
    xmlns:cq="https://www.day.com/jcr/cq/1.0"
    xmlns:jcr="https://www.jcp.org/jcr/1.0"
       jcr:primaryType="cq:Component"
       jcr:title="Title Predicate"
       sling:resourceSuperType="foundation/components/parbase"
       allowedParents="[*/parsys]"
       componentGroup="Search"/>
   ```

1. Lägg till `titlepredicate.jsp`.

   ```xml
   <%--
     Sample title predicate component
   
   --%><%@ page import="java.util.Calendar" %><%
   %><%@include file="/libs/foundation/global.jsp"%><%
   
       // A unique id is necessary in case this predicate is inserted multiple times on the same page
       String elemId = "cq-predicate-" +  Long.toString(Calendar.getInstance().getTimeInMillis());
   
   %><div class="predicatebox">
   
       <div class="title">Title</div>
   
       <%-- The wrapper for the form elements. All items will be append to this wrapper. --%>
       <div id="<%= elemId %>" class="content"></div>
   
   </div><script type="text/javascript">
   
       CQ.Ext.onLoad(function() {
   
           var predicateName = "property";
           var propertyName = "jcr:content/metadata/dc:title";
           var elemId = "<%= elemId %>";
   
           // Get the page wide available QueryBuilder.
           var qb = CQ.search.Util.getQueryBuilder();
   
           // createId adds a counter to the predicate name - useful in case this predicate
           // is inserted multiple times on the same page.
           var id = qb.createId(predicateName);
   
           // Hidden field that defines the property to search for; in our case this
           // is the "dc:title" metadata. The name "property" (or "1_property", "2_property" etc.)
           // indicates the server to use the property predicate
           // (com.day.cq.search.eval.JcrPropertyPredicateEvaluator).
           qb.addField({
               "xtype": "hidden",
               "renderTo": elemId,
               "name": id,
               "value": propertyName
           });
   
           // The visible text field. The name has to be like the one of the hidden field above
           // plus the ".value" suffix.
           qb.addField({
               "xtype": "textfield",
               "renderTo": elemId,
               "name": id + ".value"
           });
   
           // Depending on the predicate additional parameters allow to configure the
           // predicate. Here we add an operation parameter to create a "like" query.
           // Again note the name set to the id and a suffix.
           qb.addField({
               "xtype": "hidden",
               "renderTo": elemId,
               "name": id + ".operation",
               "value": "like"
           });
   
       });
   
   </script>
   ```

1. Om du vill göra komponenten tillgänglig måste du kunna redigera den. To make a component editable, in CRXDE, add a node `cq:editConfig` of primary type `cq:EditConfig`. Du kan ta bort stycken genom att lägga till en egenskap med flera värden `cq:actions` med ett enda värde på **DELETE**.
1. Navigera till webbläsaren och på exempelsidan (till exempel `press.html`) växla till designläge och aktivera den nya komponenten för prediate paragraph system (till exempel **vänster**).

1. I **redigeringsläget** är den nya komponenten nu tillgänglig i sidosparken (finns i **sökgruppen** ). Infoga komponenten i kolumnen **Predikatorer** och skriv ett sökord, till exempel **Diamant** , och klicka på förstoringsglaset för att starta sökningen.

   >[!NOTE]
   >
   >När du söker måste du skriva in ordet exakt, inklusive rätt skiftläge.

### Exempel: Skapa ett enkelt grupppredikat {#example-build-a-simple-group-predicate}

Så här skapar du ett grupppredikat:

1. Skapa till exempel en komponentmapp i projektkatalogen `/apps/geometrixx/components/picspredicate`.
1. Lägg till `content.xml`:

   ```xml
   <?xml version="1.0" encoding="UTF-8"?>
   <jcr:root xmlns:sling="https://sling.apache.org/jcr/sling/1.0"
    xmlns:cq="https://www.day.com/jcr/cq/1.0"
    xmlns:jcr="https://www.jcp.org/jcr/1.0"
       jcr:primaryType="cq:Component"
       jcr:title="Image Formats"
       sling:resourceSuperType="foundation/components/parbase"
       allowedParents="[*/parsys]"
       componentGroup="Search"/>
   ```

1. Lägg till `titlepredicate.jsp`:

   ```java
   <%--
   
     Sample group predicate component
   
   --%><%@ page import="java.util.Calendar" %><%
   %><%@include file="/libs/foundation/global.jsp"%><%
   
       // A unique id is necessary in case this predicate is inserted multiple times on the same page.
       String elemId = "cq-predicate-" +  Long.toString(Calendar.getInstance().getTimeInMillis());
   
   %><div class="predicatebox">
   
       <div class="title">Image Formats</div>
   
       <%-- The wrapper for the form elements. All items will be append to this wrapper. --%>
       <div id="<%= elemId %>" class="content"></div>
   
   </div><script type="text/javascript">
   
       CQ.Ext.onLoad(function() {
   
           var predicateName = "property";
           var propertyName = "jcr:content/metadata/dc:format";
           var elemId = "<%= elemId %>";
   
           // Get the page wide available QueryBuilder.
           var qb = CQ.search.Util.getQueryBuilder();
   
           // Create a unique group ID; will return e.g. "1_group".
           var groupId = qb.createGroupId();
   
           // Hidden field that defines the property to search for  - in our case "dc:format" -
           // and declares the group of predicates. "property" in the name ("1_group.property")
           // indicates to the server to use the "property predicate"
           // (com.day.cq.search.eval.JcrPropertyPredicateEvaluator).
           qb.addField({
               "xtype": "hidden",
               "renderTo": "<%= elemId %>",
               "name": groupId + "." + predicateName, // 1_group.property
               "value": propertyName
           });
   
           // Declare to combine the multiple values using OR.
           qb.add(new CQ.Ext.form.Hidden({
               "name": groupId + ".p.or",  // 1_group.p.or
               "value": "true"
           }));
   
           // The options
           var options = [
               { "label":"JPEG", "value":"image/jpeg"},
               { "label":"PNG",  "value":"image/png" },
               { "label":"GIF",  "value":"image/gif" }
           ];
   
           // Build a checkbox for each option.
           for (var i = 0; i < options.length; i++) {
               qb.addField({
                   "xtype": "checkbox",
                   "renderTo": "<%= elemId %>",
                   // 1_group.property.0_value, 1_group.property.1_value etc.
                   "name": groupId + "." +  predicateName + "." + i + "_value",
                   "inputValue": options[i].value,
                   "boxLabel": options[i].label,
                   "listeners": {
                       "check": function() {
                           // Submit the search form when checking/unchecking a checkbox.
                           qb.submit();
                       }
                   }
               });
           }
   
       });
   ```

1. Om du vill göra komponenten tillgänglig måste du kunna redigera den. To make a component editable, in CRXDE, add a node `cq:editConfig` of primary type `cq:EditConfig`. Du kan ta bort stycken genom att lägga till en egenskap med flera värden `cq:actions` med ett enda värde på `DELETE`.
1. Navigera till webbläsaren och på exempelsidan (till exempel `press.html`) växla till designläge och aktivera den nya komponenten för prediate paragraph system (till exempel **vänster**).
1. I **redigeringsläget** är den nya komponenten nu tillgänglig i sidosparken (finns i **sökgruppen** ). Infoga komponenten i kolumnen **Predicates** .

### Installerade prediktiva widgetar {#installed-predicate-widgets}

Följande predikat är tillgängliga som förkonfigurerade ExtJS-widgetar.

### FulltextPredicate {#fulltextpredicate}

| Egenskap | Typ | Beskrivning |
|---|---|---|
| predikateName | Sträng | Predikatets namn. Defaults to `fulltext` |
| searchCallback |  -funktion | Återanrop för att utlösa sökning vid händelse `keyup`. Defaults to `CQ.wcm.SiteAdmin.doSearch` |

### PropertyPredicate {#propertypredicate}

| Egenskap | Typ | Beskrivning |
|---|---|---|
| predikateName | Sträng | Predikatets namn. Defaults to `property` |
| propertyName | Sträng | Namn på JCR-egenskapen. Defaults to `jcr:title` |
| defaultValue | Sträng | Förfyllt standardvärde. |

### PathPredicate {#pathpredicate}

| Egenskap | Typ | Beskrivning |
|---|---|---|
| predikateName | Sträng | Predikatets namn. Defaults to `path` |
| rootPath | Sträng | Predikatets rotsökväg. Defaults to `/content/dam` |
| pathFieldPredicateName | Sträng | Defaults to `folder` |
| showFlatOption | Boolesk | Flagga som visar kryssrutan `search in subfolders`. Standardvärdet är true. |

### DatePredicate {#datepredicate}

| Egenskap | Typ | Beskrivning |
|---|---|---|
| predikateName | Sträng | Predikatets namn. Defaults to `daterange` |
| egenskapsnamn | Sträng | Namn på JCR-egenskapen. Defaults to `jcr:content/jcr:lastModified` |
| defaultValue | Sträng | Förfyllt standardvärde |

### OptionsPredicate {#optionspredicate}

| Egenskap | Typ | Beskrivning |
|---|---|---|
| title | Sträng | Lägger till ytterligare en rubrik |
| predikateName | Sträng | Predikatets namn. Defaults to `daterange` |
| egenskapsnamn | Sträng | Namn på JCR-egenskapen. Defaults to `jcr:content/metadata/cq:tags` |
| komprimera | Sträng | Komprimera nivå. Defaults to `level1` |
| triggerSearch | Boolesk | Flagga för att utlösa sökning vid kontroll. Standardvärdet är false |
| searchCallback |  -funktion | Återanrop för att utlösa sökning. Defaults to `CQ.wcm.SiteAdmin.doSearch` |
| searchTimeoutTime | Siffra | Timeout innan searchCallback aktiveras. Standardvärdet är 800 ms |

## Anpassa sökresultat {#customizing-search-results}

Presentationen av sökresultaten på en resursdelningssida styrs av det valda objektivet. AEM Assets innehåller en uppsättning fördefinierade objektiv som kan användas för att anpassa en resursdelssida. Att anpassa en resurs på det här sättet beskrivs i [Skapa och konfigurera en resursdelssida](assets-finder-editor.md#creating-and-configuring-an-asset-share-page).

Förutom att använda befintliga linser kan AEM-utvecklare även skapa egna linser.
