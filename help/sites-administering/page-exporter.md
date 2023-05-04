---
title: Sidexporteraren
seo-title: The Page Exporter
description: Lär dig hur du använder AEM sidexporteraren.
seo-description: Learn how to use the AEM Page Exporter.
uuid: 2ca2b8f1-c723-4e6b-8c3d-f5886cd0d3f1
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 6ab07b5b-ee37-4029-95da-be2031779107
exl-id: a5cb3b7b-d40f-4d86-8473-fb584f1d486c
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1044'
ht-degree: 0%

---

# Sidexporteraren{#the-page-exporter}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med AEM kan du exportera en sida som en fullständig webbsida, inklusive bilder, .js- och .css-filer.

När exporten är konfigurerad begär du bara en sida i webbläsaren genom att ersätta den `html` med `export.zip` i URL:en och du får en ZIP-filnedladdning som innehåller den återgivna sidan i html-format och de refererade resurserna. Alla sökvägar på sidan, t.ex. sökvägar till bilder, skrivs om så att de pekar antingen på filerna som finns i zip-filen eller på resurserna på servern.

## Exportera en sida {#exporting-a-page}

I följande steg beskrivs hur du exporterar en sida och förutsätter att det finns en exportkonfigurationsmall för platsen. En konfigurationsmall definierar hur en sida exporteras och är specifik för din plats. Om du vill skapa en konfigurationsmall går du till [Skapa en sidexportkonfiguration för platsen](#creating-a-page-exporter-configuration-for-your-site) -avsnitt.

Så här exporterar du en sida:

1. Öppna sidan i webbläsaren. Till exempel:
1. `http://localhost:4502/content/geometrixx/en/products/triangle.html`
1. Öppna dialogrutan för sidegenskaper och välj **Avancerat** och utöka **Exportera** fältuppsättning.

1. Klicka på förstoringsikonen och välj en konfigurationsmall. Välj **geometrixx** -mall, som den är standardmall för Geometrixx. Klicka **OK**.

1. Klicka **OK** för att stänga dialogrutan för sidegenskaper.
1. Begär sidan genom att ersätta `html` med `export.zip` i webbadressen.

1. Ladda ned `<page-name>.export.zip` till filsystemet.

1. Zippa upp filen i filsystemet:

   * HTML-sidfil ( `<page-name>.html`) finns nedan `<unzip-dir>/<page-path>`
   * andra resurser (.js-filer, .css-filer, bilder, ...) finns enligt inställningarna i exportmallen. I det här exemplet visas några resurser nedan `<unzip-dir>/etc`, lite nedan `<unzip-dir>/<page-path>`.

1. Öppna HTML-filen för sidan ( `<unzip-dir>/<page-path>.html`) i webbläsaren för att kontrollera återgivningen.

## Skapa en sidexportkonfiguration för platsen {#creating-a-page-exporter-configuration-for-your-site}

Sidexporteraren baseras på ramverket för innehållssynkronisering. De konfigurationer som är tillgängliga i dialogrutan för sidegenskaper är konfigurationsmallar. De definierar alla nödvändiga beroenden för en sida. När en sidexport aktiveras används konfigurationsmallen och både sidsökvägen och designsökvägen tillämpas dynamiskt på konfigurationen. ZIP-filen skapas sedan med standardfunktionen för innehållssynkronisering.

AEM bäddar in några mallar, bland annat:

* Ett standardvärde vid `/etc/contentsync/templates/default`. Den här mallen:

   * Är reservmallen när ingen konfigurationsmall hittas i databasen.
   * Kan fungera som bas för en ny konfigurationsmall.

* En som är dedikerad till **Geometrixx** webbplats, på `/etc/contentsync/templates/geometrixx`. Den här mallen kan användas som exempel för att skapa en ny mall.

Så här skapar du en konfigurationsmall för sidexporterare:

1. I **CRXDE Lite**, skapa en nod nedan `/etc/contentsync/templates`:

   * Namn: t.ex. `mysite`. Namnet visas i dialogrutan för sidegenskaper när du väljer sidexportmall.
   * Typ: `nt:unstructured`

1. Under mallnoden som anropas här `mysite`skapar du en nodstruktur med hjälp av konfigurationsnoderna som beskrivs nedan.

### Konfigurationsnoder för sidexport {#page-exporter-configuration-nodes}

Konfigurationsmallen består av en nodstruktur. Varje nod har en `type` -egenskap som definierar en viss åtgärd när zip-filen skapas. Mer information om type-egenskapen finns i avsnittet Översikt över konfigurationstyper på ramverkssidan för innehållssynkronisering.

Följande noder kan användas för att skapa en exportkonfigurationsmall:

**sidnod** Sidnoden används för att kopiera sidans HTML-kod till zip-filen. Den har följande egenskaper:

* Är en obligatorisk nod.
* Finns nedan `/etc/contentsync/templates/<sitename>`.
* Namnet är `page`.
* Dess nodtyp är `nt:unstructured`

The `page` noden har följande egenskaper:

* A `type` egenskap som anges med värdet `pages`.

* Den har ingen `path` egenskapen när den aktuella sidsökvägen kopieras dynamiskt till konfigurationen.

* De andra egenskaperna beskrivs i avsnittet Översikt över konfigurationstyper i ramverket för innehållssynkronisering.

**skriv om nod** Noden rewrite definierar hur länkarna skrivs om på den exporterade sidan. De omskrivna länkarna kan antingen peka på filerna som finns i ZIP-filen eller på resurserna på servern.

På sidan Innehållssynkronisering finns en fullständig beskrivning av `rewrite` nod.

**designnod** Designnoden används för att kopiera designen som används för den exporterade sidan. Den har följande egenskaper:

* Är valfritt.
* Finns nedan `/etc/contentsync/templates/<sitename>`.
* Namnet är `design`.
* Dess nodtyp är `nt:unstructured`.

The `design` noden har följande egenskaper:

* A `type` egenskapen inställd på värdet `copy`.

* Den har ingen `path` egenskapen när den aktuella sidsökvägen kopieras dynamiskt till konfigurationen.

**generisk nod** En allmän nod används för att kopiera resurser som .js- eller .css-filer med klienten till zip-filen. Den har följande egenskaper:

* Är valfritt.
* Finns nedan `/etc/contentsync/templates/<sitename>`.
* Har inget specifikt namn.
* Dess nodtyp är `nt:unstructured`.
* Har en `type` egenskap och alla `type` relaterade egenskaper enligt definitionen i avsnittet Översikt över konfigurationstyper i ramverket för innehållssynkronisering.

Följande konfigurationsnod kopierar till exempel geometrixx clientlibs .js-filer till zip-filen:

```xml
"geometrixx.clientlibs.js": {
    "extension": "js",
    "type": "clientlib",
    "path": "/etc/designs/geometrixx/clientlibs",
    "jcr:primaryType": "nt:unstructured"
}
```

The **Geometrixx** konfigurationsmallen för sidexport visar hur en sidexport kan konfigureras. Om du vill visa nodstrukturen för mallen i webbläsaren som json-format begär du följande URL:

`http://localhost:4502/etc/contentsync/templates/geometrixx.-1.json`

**Implementera en anpassad konfiguration**

Som du kanske har märkt i nodstrukturen är **Geometrixx** konfigurationsmallen för sidexport har en `logo` nod med en `type` egenskap inställd på `image`. Detta är en speciell konfigurationstyp som har skapats för att kopiera bildlogotypen till zip-filen. För att uppfylla vissa specifika krav kan du behöva implementera en anpassad `type` egenskap: Mer information finns i avsnittet Implementera en anpassad uppdateringshanterare på sidan Innehållssynkronisering.

## Programmatisk export av en sida {#programmatically-exporting-a-page}

Om du vill exportera en sida programmatiskt kan du använda [PageExporter](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/index.html?com/day/cq/wcm/contentsync/PageExporter.html) OSGI-tjänster. Med den här tjänsten kan du:

* Exportera en sida och skriv till HTTP-serverns svar.
* Exportera en sida och spara zip-filen på en viss plats.

Servern som är bunden till `export` väljaren och `zip` i används tjänsten PageExporter.

## Felsökning {#troubleshooting}

Om du får problem med nedladdningen av ZIP-filen kan du ta bort `/var/contentsync` i databasen och skicka exportbegäran igen.
