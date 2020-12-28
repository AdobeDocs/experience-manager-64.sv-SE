---
title: Sidexporteraren
seo-title: Sidexporteraren
description: Lär dig hur du använder AEM sidexporteraren.
seo-description: Lär dig hur du använder AEM sidexporteraren.
uuid: 2ca2b8f1-c723-4e6b-8c3d-f5886cd0d3f1
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 6ab07b5b-ee37-4029-95da-be2031779107
translation-type: tm+mt
source-git-commit: aac5026a249e1cb09fec66313cc03b58597663f0
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 0%

---


# Sidexporteraren{#the-page-exporter}

Med AEM kan du exportera en sida som en fullständig webbsida, inklusive bilder, .js- och .css-filer.

När exporten är konfigurerad begär du bara en sida i webbläsaren genom att ersätta `html` med `export.zip` i URL:en och få en ZIP-filhämtning som innehåller den återgivna sidan i html-format och de refererade resurserna. Alla sökvägar på sidan, t.ex. sökvägar till bilder, skrivs om så att de pekar antingen på filerna som finns i zip-filen eller på resurserna på servern.

## Exportera en sida {#exporting-a-page}

I följande steg beskrivs hur du exporterar en sida och förutsätter att det finns en exportkonfigurationsmall för platsen. En konfigurationsmall definierar hur en sida exporteras och är specifik för din plats. Om du vill skapa en konfigurationsmall läser du avsnittet [Skapa en sidexportkonfiguration för din plats](#creating-a-page-exporter-configuration-for-your-site).

Så här exporterar du en sida:

1. Öppna sidan i webbläsaren. Till exempel:
1. `http://localhost:4502/content/geometrixx/en/products/triangle.html`
1. Öppna dialogrutan för sidegenskaper, välj fliken **Avancerat** och utöka fältuppsättningen **Exportera**.

1. Klicka på förstoringsikonen och välj en konfigurationsmall. Markera **geometrixx**-mallen eftersom det är standardmallen för Geometrixx. Klicka på **OK**.

1. Klicka på **OK** för att stänga dialogrutan för sidegenskaper.
1. Begär sidan genom att ersätta `html` med `export.zip` i URL:en.

1. Hämta filen `<page-name>.export.zip` till filsystemet.

1. Zippa upp filen i filsystemet:

   * HTML-sidfilen ( `<page-name>.html`) är tillgänglig under `<unzip-dir>/<page-path>`
   * andra resurser (.js-filer, .css-filer, bilder, ...) finns enligt inställningarna i exportmallen. I det här exemplet är vissa resurser under `<unzip-dir>/etc`, andra under `<unzip-dir>/<page-path>`.

1. Öppna HTML-sidfilen ( `<unzip-dir>/<page-path>.html`) i webbläsaren för att kontrollera återgivningen.

## Skapa en sidexportkonfiguration för din plats {#creating-a-page-exporter-configuration-for-your-site}

Sidexporteraren baseras på ramverket för innehållssynkronisering. De konfigurationer som är tillgängliga i dialogrutan för sidegenskaper är konfigurationsmallar. De definierar alla nödvändiga beroenden för en sida. När en sidexport aktiveras används konfigurationsmallen och både sidsökvägen och designsökvägen tillämpas dynamiskt på konfigurationen. ZIP-filen skapas sedan med standardfunktionen för innehållssynkronisering.

AEM bäddar in några mallar, bland annat:

* Ett standardvärde på `/etc/contentsync/templates/default`. Den här mallen:

   * Är reservmallen när ingen konfigurationsmall hittas i databasen.
   * Kan fungera som bas för en ny konfigurationsmall.

* En som är dedikerad till **Geometrixx**-webbplatsen på `/etc/contentsync/templates/geometrixx`. Den här mallen kan användas som exempel för att skapa en ny mall.

Så här skapar du en konfigurationsmall för sidexporterare:

1. I **CRXDE Lite** skapar du en nod under `/etc/contentsync/templates`:

   * Namn: t.ex. `mysite`. Namnet visas i dialogrutan för sidegenskaper när du väljer sidexportmall.
   * Typ: `nt:unstructured`

1. Under mallnoden, som anropas här `mysite`, skapar du en nodstruktur med hjälp av konfigurationsnoderna som beskrivs nedan.

### Konfigurationsnoder för sidexport {#page-exporter-configuration-nodes}

Konfigurationsmallen består av en nodstruktur. Varje nod har en `type`-egenskap som definierar en specifik åtgärd när zip-filen skapas. Mer information om type-egenskapen finns i avsnittet Översikt över konfigurationstyper på ramverkssidan för innehållssynkronisering.

Följande noder kan användas för att skapa en exportkonfigurationsmall:

**page** nodeThe page node is used to copy the page html to the zip file. Den har följande egenskaper:

* Är en obligatorisk nod.
* Finns under `/etc/contentsync/templates/<sitename>`.
* Dess namn är `page`.
* Dess nodtyp är `nt:unstructured`

Noden `page` har följande egenskaper:

* En `type`-egenskap med värdet `pages`.

* Den har ingen `path`-egenskap eftersom den aktuella sidsökvägen kopieras dynamiskt till konfigurationen.

* De andra egenskaperna beskrivs i avsnittet Översikt över konfigurationstyper i ramverket för innehållssynkronisering.

**skriv om** nodNoden rewrite definierar hur länkarna skrivs om på den exporterade sidan. De omskrivna länkarna kan antingen peka på filerna som finns i ZIP-filen eller på resurserna på servern.

En fullständig beskrivning av noden `rewrite` finns på sidan Innehållssynkronisering.

**designnod** Designnoden används för att kopiera designen som används för den exporterade sidan. Den har följande egenskaper:

* Är valfritt.
* Finns under `/etc/contentsync/templates/<sitename>`.
* Dess namn är `design`.
* Dess nodtyp är `nt:unstructured`.

Noden `design` har följande egenskaper:

* En `type`-egenskap inställd på värdet `copy`.

* Den har ingen `path`-egenskap eftersom den aktuella sidsökvägen kopieras dynamiskt till konfigurationen.

**generisk** nodEn generisk nod används för att kopiera resurser som clientlibs .js- eller .css-filer till zip-filen. Den har följande egenskaper:

* Är valfritt.
* Finns under `/etc/contentsync/templates/<sitename>`.
* Har inget specifikt namn.
* Dess nodtyp är `nt:unstructured`.
* Har en `type`-egenskap och alla `type`-relaterade egenskaper som definieras i avsnittet Översikt över konfigurationstyper i ramverket för innehållssynkronisering.

Följande konfigurationsnod kopierar till exempel geometrixx clientlibs .js-filer till zip-filen:

```xml
"geometrixx.clientlibs.js": {
    "extension": "js",
    "type": "clientlib",
    "path": "/etc/designs/geometrixx/clientlibs",
    "jcr:primaryType": "nt:unstructured"
}
```

Konfigurationsmallen för sidexport i **Geometrixx** visar hur en sidexport kan konfigureras. Om du vill visa nodstrukturen för mallen i webbläsaren som json-format begär du följande URL:

`http://localhost:4502/etc/contentsync/templates/geometrixx.-1.json`

**Implementera en anpassad konfiguration**

Som du kanske har märkt i nodstrukturen har konfigurationsmallen **Geometrixx** en `logo`-nod med egenskapen `type` inställd på `image`. Detta är en speciell konfigurationstyp som har skapats för att kopiera bildlogotypen till zip-filen. För att uppfylla vissa specifika krav kan du behöva implementera en anpassad `type`-egenskap: Mer information finns i avsnittet Implementera en anpassad uppdateringshanterare på sidan Innehållssynkronisering.

## Exportera en sida {#programmatically-exporting-a-page} programmatiskt

Om du vill exportera en sida programmatiskt kan du använda OSGI-tjänsten [PageExporter](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/index.html?com/day/cq/wcm/contentsync/PageExporter.html). Med den här tjänsten kan du:

* Exportera en sida och skriv till HTTP-serverns svar.
* Exportera en sida och spara zip-filen på en viss plats.

Servern som är bunden till väljaren `export` och tillägget `zip` använder tjänsten PageExporter.

## Felsökning {#troubleshooting}

Om du får problem med nedladdningen av zip-filen kan du ta bort noden `/var/contentsync` i databasen och skicka exportbegäran igen.

