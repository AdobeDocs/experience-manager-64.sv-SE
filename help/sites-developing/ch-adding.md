---
title: Lägga till ContextHub på Pages och Access Stores
seo-title: Lägga till ContextHub på Pages och Access Stores
description: Lägg till ContextHub på sidorna för att aktivera ContextHub-funktionerna och för att länka till ContextHub Javascript-biblioteken
seo-description: Lägg till ContextHub på sidorna för att aktivera ContextHub-funktionerna och för att länka till ContextHub Javascript-biblioteken
uuid: ade37960-21c4-4d64-a525-68f0d199f955
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: ac8f44df-39fb-44ea-ae17-ead0dbd1f6c0
translation-type: tm+mt
source-git-commit: 39b6af8ee815e8f6fa6e0b4a0a6dc80f29165243

---


# Lägga till ContextHub på Pages och Access Stores {#adding-contexthub-to-pages-and-accessing-stores}

Lägg till ContextHub på sidorna för att aktivera ContextHub-funktionerna och för att länka till ContextHub Javascript-biblioteken

ContextHub Javascript-API:t ger åtkomst till kontextdata som hanteras av ContextHub. Den här sidan beskriver kortfattat huvudfunktionerna i API:t för att komma åt och ändra kontextdata. Följ länkarna till API-referensdokumentationen för att se detaljerad information och kodexempel.

## Lägga till ContextHub i en sidkomponent {#adding-contexthub-to-a-page-component}

Om du vill aktivera ContextHub-funktionerna och länka till ContextHub Javascript-biblioteken inkluderar du kontexthub-komponenten i sidans `head` avsnitt. JSP-koden för sidkomponenten liknar följande exempel:

```xml
<head>
   <sling:include path="contexthub" resourceType="granite/contexthub/components/contexthub" />
</head>
```

Observera att du även måste konfigurera om ContextHub-verktygsfältet ska visas i förhandsgranskningsläget. Se [Visa och dölja ContextHub-gränssnittet](/help/sites-administering/contexthub-config.md#showing-and-hiding-the-contexthub-ui).

## Om ContextHub Stores {#about-contexthub-stores}

Använd ContextHub-arkiv för att behålla kontextdata. ContextHub innehåller följande typer av butiker som utgör grunden för alla butikstyper:

* [PersistedStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedstore)
* [SessionStore](/help/sites-developing/contexthub-api.md#contexthub-store-sessionstore)
* [JSONPStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedjsonpstore)
* [PersistedJSONPStore](/help/sites-developing/contexthub-api.md#contexthub-store-persistedstore)

Alla butikstyper är tillägg till [`ContextHub.Store.Core`](/help/sites-developing/contexthub-api.md#contexthub-store-core) klassen. Mer information om hur du skapar en ny butikstyp finns i [Skapa anpassade butiker](/help/sites-developing/ch-extend.md#creating-custom-store-candidates). Mer information om exempel på lagringstyper finns i [Exempel på ContextHub Store-förslag](/help/sites-developing/ch-samplestores.md).

### Beständiga lägen {#persistence-modes}

Kontextnavlager använder ett av följande beständiga lägen:

* **** Lokal: HTML5 localStorage används för att lagra data. Lokal lagring sparas i webbläsaren i alla sessioner.
* **** Session: Använder HTML5 sessionStorage för att behålla data. Sessionslagringsplatsen sparas under hela webbläsarsessionen och är tillgänglig för alla webbläsarfönster.
* **** Cookie: Använder webbläsarens inbyggda stöd för cookies för datalagring. Cookie-data skickas till och från servern i HTTP-begäranden.
* **** Fönster.namn: Använder egenskapen window.name för att behålla data.
* **** Minne: Använder ett JavaScript-objekt för att bevara data.

Som standard använder Context Hub det lokala beständighetsläget. Om webbläsaren inte stöder eller tillåter lokal lagring i HTML5 används sessionens beständighet. Om webbläsaren inte stöder eller tillåter HTML5 sessionStorage, används Window.name persistence.

### Lagra data {#store-data}

Internt kan du lagra data i en trädstruktur, vilket gör att värden kan läggas till som primära typer eller komplexa objekt. När du lägger till komplexa objekt i butiker skapar objektegenskaperna grenar i dataträdet. Följande komplexa objekt läggs till i ett tomt arkiv med namnet location:

```xml
Object {
   number: 321,
   data: {
      city: "Basel",
      country: "Switzerland",
      details: {
         population: 173330,
         elevation: 260
      }
   }
}
```

Trädstrukturen för butiksdata kan utformas på följande sätt:

```xml
/
|- number
|- data
      |- city
      |- country
      |- details
            |- population
            |- elevation
```

Trädstrukturen definierar dataobjekt i arkivet som nyckel/värde-par. I ovanstående exempel `/number` motsvarar tangenten värdet `321`och tangenten `/data/country` motsvarar värdet `Switzerland`.

### Ändra objekt {#manipulating-objects}

ContextHub innehåller klassen [`ContextHub.Utils.JSON.tree`](/help/sites-developing/contexthub-api.md#contexthub-utils-json-tree) för att hantera JavaScript-objekt. Använd funktionerna i den här klassen för att ändra JavaScript-objekt innan du lägger till dem i en butik eller efter att du har fått dem från en butik.

Klassen innehåller dessutom funktioner för att serialisera objekt till strängar och för att avserialisera strängar till objekt. [`ContextHub.Utils.JSON`](/help/sites-developing/contexthub-api.md#contexthub-utils-json) Använd den här klassen för att hantera JSON-data för webbläsare som inte innehåller de interna funktionerna `JSON.parse` och `JSON.stringify` funktionerna.

## Interagera med ContextHub Stores {#interacting-with-contexthub-stores}

Använd [`ContextHub`](/help/sites-developing/contexthub-api.md#ui-event-constants) Javascript-objektet för att hämta ett arkiv som ett Javascript-objekt. När du har fått lagringsobjektet kan du ändra de data som det innehåller. Använd funktionen [`getAllStores`](/help/sites-developing/contexthub-api.md#getallstores) eller [`getStore`](/help/sites-developing/contexthub-api.md#getstore-name) funktionen för att hämta arkivet.

### Åtkomst till butiksdata {#accessing-store-data}

Klassen [`ContexHub.Store.Core`](/help/sites-developing/contexthub-api.md#contexthub-store-core) Javascript definierar flera funktioner för interaktion med butiksdata. Följande funktioner lagrar och hämtar flera dataobjekt som finns i objekt:

* [addAllItems](/help/sites-developing/contexthub-api.md#addallitems-tree-options)
* [getTree](/help/sites-developing/contexthub-api.md#gettree-includeinternals)

Enskilda dataobjekt lagras som en uppsättning nyckel/värde-par. Om du vill lagra och hämta värden anger du motsvarande nyckel:

* [getItem](/help/sites-developing/contexthub-api.md#getitem-key)
* [setItem](/help/sites-developing/contexthub-api.md#setitem-key-value-options)

Observera att anpassade lagringskandidater kan definiera ytterligare funktioner som ger åtkomst till lagringsdata.

>[!NOTE]
>
>ContextHub är som standard inte medveten om den inloggning som för närvarande används på publiceringsservrar, och sådana användare betraktas som&quot;anonyma&quot; av ContextHub.
>
>Du kan göra ContextHub uppmärksam på inloggade användare genom att läsa in profilarkivet som det implementerats på referensplatsen [](/help/sites-developing/we-retail.md)We.Retail. Se [relevant kod på GitHub här](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/blob/master/ui.apps/src/main/content/jcr_root/apps/weretail/components/structure/header/clientlib/js/utilities.js).

### ContextHub Eventing {#contexthub-eventing}

ContextHub innehåller ett ramverk för händelser som gör att du automatiskt kan reagera på butikshändelser. Varje butiksobjekt innehåller ett [`ContextHub.Utils.Eventing`](/help/sites-developing/contexthub-api.md#contexthub-utils-eventing) objekt som är tillgängligt som butikens [`eventing`](/help/sites-developing/contexthub-api.md#eventing) egenskap. Använd funktionen [`on`](/help/sites-developing/contexthub-api.md#on-name-handler-selector-triggerforpastevents) eller [`once`](/help/sites-developing/contexthub-api.md#once-name-handler-selector-triggerforpastevents) för att binda en JavaScript-funktion till en store-händelse.

## Använda kontextnavet för att hantera cookies {#using-context-hub-to-manipulate-cookies}

Context Hub Javascript API har stöd för olika webbläsare för hantering av webbläsarcookies. I [`ContextHub.Utils.Cookie`](/help/sites-developing/contexthub-api.md#contexthub-utils-cookie) namnutrymmet definieras flera funktioner för att skapa, ändra och ta bort cookies.

## Bestämmer matchade ContextHub-segment {#determining-resolved-contexthub-segments}

Med segmentmotorn för ContextHub kan du avgöra vilket av de registrerade segmenten som matchas i det aktuella sammanhanget. Använd funktionen getResolvedSegments i [`ContextHub.SegmentEngine.SegmentManager`](/help/sites-developing/contexthub-api.md#contexthub-segmentengine-segmentmanager) klassen för att hämta lösta segment. Använd sedan funktionen `getName` eller `getPath` i [`ContextHub.SegmentEngine.Segment`](/help/sites-developing/contexthub-api.md#contexthub-segmentengine-segment) klassen för att testa ett segment.

### Installerade segment {#installed-segments}

ContextHub-segment installeras under `/conf/we-retail/settings/wcm/segments` noden.

* hona
* hona-över-30
* hona-under-30
* man
* hand-över-30
* man-under-30
* order-value-75-to-100
* order-value-over-100
* over-30
* sommar
* Sommarhona
* sommar-hona-över-30
* sommar-hona-under-30
* Sommarman
* sommar-man-over-30
* Sommar-man-under-30
* under-30
* vintertid
* vinterhona
* vinterhona-över-30
* vinterhona-under-30
* vinterhandjur
* vintermanlig-över-30
* vinterhandjur under 20

De regler som används för att lösa dessa segment sammanfattas enligt följande:

* Kvinna eller man bestäms av dataobjektet `gender` i [profilarkivet](/help/sites-developing/ch-samplestores.md#granite-profile-sample-store-candidate) .

* Åldern avgörs av åldersdataobjektet i profilarkivet.
* Säsongen bestäms av latituddataobjektet för [geolocation](/help/sites-developing/ch-samplestores.md#contexthub-geolocation-sample-store-candidate) -arkivet och månadsdataobjektet för surferinfo-arkivet.

>[!WARNING]
>
>De installerade segmenten tillhandahålls som referenskonfigurationer som hjälper dig att skapa en egen dedikerad konfiguration för ditt projekt och bör därför inte användas direkt.

## Felsökningsmeddelanden för loggning för ContextHub {#logging-debug-messages-for-contexthub}

Konfigurera tjänsten Adobe Granite ContextHub OSGi (PID = `com.adobe.granite.contexthub.impl.ContextHubImpl`) för att logga detaljerade felsökningsmeddelanden som är användbara vid utveckling.

Om du vill konfigurera tjänsten kan du antingen använda [webbkonsolen](/help/sites-deploying/configuring-osgi.md#osgi-configuration-with-the-web-console) eller en [JCR-nod i databasen](/help/sites-deploying/configuring-osgi.md#osgi-configuration-in-the-repository):

* Webbkonsol: Om du vill logga felsökningsmeddelanden väljer du egenskapen Felsökning.
* JCR-nod: Om du vill logga felsökningsmeddelanden anger du den booleska `com.adobe.granite.contexthub.debug` egenskapen till `true`.

## Se en översikt över ContextHub Framework {#see-an-overview-of-the-contexthub-framework}

ContextHub tillhandahåller en [diagnostiksida](/help/sites-developing/ch-diagnostics.md) där du kan se en översikt över ContextHub-ramverket.
