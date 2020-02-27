---
title: Resursmappning
seo-title: Resursmappning
description: Lär dig hur du definierar omdirigeringar, tillfälliga URL:er och virtuella värdar för AEM genom att använda resursmappning.
seo-description: Lär dig hur du definierar omdirigeringar, tillfälliga URL:er och virtuella värdar för AEM genom att använda resursmappning.
uuid: 33de7e92-8144-431b-badd-e6a667cd78e1
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
discoiquuid: ddfacc63-1840-407e-8802-3730009c84f0
translation-type: tm+mt
source-git-commit: c4ac10736c937198aa0c81ecf547dd489ef93366

---


# Resursmappning{#resource-mapping}

Resursmappning används för att definiera omdirigeringar, tillfälliga URL:er och virtuella värdar för AEM.

Du kan till exempel använda dessa mappningar för:

* Använd prefix för alla förfrågningar `/content` så att den interna strukturen döljs för besökarna på webbplatsen.
* Definiera en omdirigering så att alla begäranden till `/content/en/gateway` sidan på webbplatsen omdirigeras till `https://gbiv.com/`.

Ett möjligt HTTP-mappningsprefix [för alla begäranden till localhost:4503 med /content](#configuring-an-internal-redirect-to-content). En sådan här mappning kan användas för att dölja den interna strukturen för besökarna på webbplatsen så som den tillåter:

`localhost:4503/content/geometrixx/en/products.html`

ska nås med:

`localhost:4503/geometrixx/en/products.html`

när mappningen automatiskt lägger till prefixet `/content` i `/geometrixx/en/products.html`.

>[!CAUTION]
>
>Vanity-URL:er stöder inte regex-mönster.

>[!NOTE]
>
>Mer information finns i dokumentationen om Sling och [Mappings for Resource Resolution](https://sling.apache.org/site/resources.html) and [Resources](https://sling.apache.org/site/mappings-for-resource-resolution.html) .

## Visa mappningsdefinitioner {#viewing-mapping-definitions}

Mappningarna består av två listor som JCR-resurslösaren utvärderar (högst upp) för att hitta en matchning.

Dessa listor kan visas (tillsammans med konfigurationsinformation) under **JCR ResourceResolver** -alternativet i Felix-konsolen. till exempel `https://<host>:<port>/system/console/jcrresolver`:

* Konfiguration

   Visar den aktuella konfigurationen (enligt definition för [Resurslösaren](/help/sites-deploying/osgi-configuration-settings.md)för Apache Sling.

* Konfigurationstest

   På så sätt kan du ange en URL eller resurssökväg. Klicka på **Lös** eller **Karta** för att bekräfta hur posten ska omformas.

* **Matcha mappningsposter** Listan över poster som används av metoderna ResourceResolver.resolve för att mappa URL:er till Resources.

* **Mappa mappningsposter** Listan med poster som används av metoderna ResourceResolver.map för att mappa resurssökvägar till URL:er.

De två listorna visar olika poster, inklusive de som definieras som standardvärden av programmen. Dessa syftar ofta till att förenkla URL:er för användaren.

Listorna innehåller ett **mönster**, ett reguljärt uttryck som matchar begäran, med en **ersättning** som definierar den omdirigering som ska skjutas upp.

Till exempel:

**Mönster**`^[^/]+/[^/]+/welcome$`

kommer att aktivera:

**Ersättning** `/libs/cq/core/content/welcome.html`.

omdirigera en begäran:

`http://localhost:4503/welcome`

till:

`http://localhost:4503/libs/cq/core/content/welcome.html`

Nya mappningsdefinitioner skapas i databasen.

>[!NOTE]
>
>Det finns många resurser som kan förklara hur du definierar reguljära uttryck. till exempel [https://www.regular-expressions.info/](https://www.regular-expressions.info/).

## Skapa mappningsdefinitioner i AEM {#creating-mapping-definitions-in-aem}

I en standardinstallation av AEM hittar du mappen:

`/etc/map/http`

Detta är den struktur som används för att definiera mappningar för HTTP-protokollet. Andra mappar ( `sling:Folder`) kan skapas under `/etc/map` för andra protokoll som du vill mappa.

### Konfigurera en intern omdirigering till /content {#configuring-an-internal-redirect-to-content}

Så här skapar du en mappning som prefixar en begäran till http://localhost:4503/ med `/content`:

1. Navigera till med CRXDE `/etc/map/http`.

1. Skapa en ny nod:

   * **Typ**`sling:Mapping`

      Den här nodtypen är avsedd för sådana mappningar, men det är inte obligatoriskt att använda den.

   * **Namn**`localhost_any`

1. Klicka på **Spara alla**.
1. **Lägg till** följande egenskaper i den här noden:

   * **Namn**`sling:match`

      * **Typ**`String`
      * **Värde**`localhost.4503/`
   * **Namn**`sling:internalRedirect`

      * **Typ**`String`
      * **Värde**`/content/`


1. Klicka på **Spara alla**.

Detta kommer att hantera en begäran som:\
`localhost:4503/geometrixx/en/products.html`\
som if:\
`localhost:4503/content/geometrixx/en/products.html`\
hade blivit ombedd.

>[!NOTE]
>
>Mer information om tillgängliga [försäljningsalternativ och hur de kan konfigureras finns i Resurser](https://sling.apache.org/site/mappings-for-resource-resolution.html) i Sling Documentation.

>[!NOTE]
>
>Du kan använda `/etc/map.publish` för att hålla konfigurationerna för publiceringsmiljön. Dessa måste sedan replikeras och den nya platsen ( `/etc/map.publish`) konfigureras för **mappningsplatsen** för [Apache Sling Resource Resolver](/help/sites-deploying/osgi-configuration-settings.md#apacheslingresourceresolver) i publiceringsmiljön.

