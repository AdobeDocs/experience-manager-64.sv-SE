---
title: XMP metadata
description: Läs mer om metadatastandarden för XMP (Extensible Metadata Platform) som används av AEM Assets för metadatahantering. XMP har ett standardformat för att skapa, bearbeta och utbyta metadata för en mängd olika program.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '815'
ht-degree: 19%

---


# XMP-metadata {#xmp-metadata}

XMP (Extensible Metadata Platform) är den metadatastandard som används av AEM Assets för all metadatahantering. XMP har ett standardformat för att skapa, bearbeta och utbyta metadata för en mängd olika program.

Förutom universell metadatakodning som kan bäddas in i alla filformat, har XMP en innehållsmodell [som](xmp.md#xmp-core-concepts) stöds av Adobe [](xmp.md#advantages-of-xmp) och andra företag, så att användare av XMP i kombination med AEM Assets har en kraftfull plattform att bygga vidare på.

Specifikationen [för](https://www.adobe.com/devnet/xmp.html) XMP är tillgänglig från Adobe.

## Vad är XMP? {#what-is-xmp}

AEM Assets stöder XMP - Extensible Metadata Platform som leds av Adobe. XMP är en standard för bearbetning och lagring av standardiserade och egna metadata i digitala resurser. XMP är en standard som gör att flera program kan arbeta effektivt med metadata.

Produktionsproffs kan t.ex. använda det inbyggda XMP-stödet i Adobe-program för att skicka information till flera filformat. AEM Assets-databasen extraherar XMP metadata och använder den för att hantera innehållets livscykel och ger möjlighet att skapa automatiserade arbetsflöden.

XMP standardiserar hur metadata definieras, skapas och bearbetas genom att tillhandahålla en datamodell, en lagringsmodell och scheman. Alla dessa begrepp beskrivs i detta avsnitt.

Alla äldre metadata från EXIF, ID3 eller Microsoft Office översätts automatiskt till XMP, som kan utökas för att stödja kundspecifika metadatamatchningar, som produktkataloger.

Metadata i XMP består av en uppsättning egenskaper. Dessa egenskaper är alltid kopplade till en\
En särskild enhet som kallas en resurs. Egenskaperna är alltså&quot;om&quot; resursen. När det gäller XMP är resursen alltid resursen.

### Adobe {#adobe}

Adobe introducerade först XMP som en del av Adobe Acrobat programprodukt. Sedan dess har XMP blivit allmänt förekommande.

### XMP ekosystem {#xmp-ecosystem}

XMP definierar en [metadatamodell](https://sv.wikipedia.org/wiki/Metadata) som kan användas med alla definierade metadataobjekt. XMP definierar också särskilda [scheman](https://en.wikipedia.org/wiki/XML_schema) för grundläggande egenskaper som är användbara för att logga en resurs historik genom olika bearbetningssteg – från fotografering, [skanning](https://sv.wikipedia.org/wiki/Bildl%C3%A4sare) och textredigering via fotoredigeringssteg (som [beskärning](https://sv.wikipedia.org/wiki/Bildbesk%C3%A4rning) eller färgjustering) till den slutliga bilden. Med XMP kan alla program och enheter längs vägen lägga till egen information i en digital resurs, som sedan sparas i den slutliga digitala filen.

XMP serialiseras och lagras oftast med en underuppsättning av [W3C](https://sv.wikipedia.org/wiki/World_Wide_Web_Consortium) [Resource Description Framework](https://sv.wikipedia.org/wiki/Resource_Description_Framework) (RDF), som i sin tur uttrycks i [XML](https://sv.wikipedia.org/wiki/XML).

## Fördelar med XMP {#advantages-of-xmp}

XMP har följande fördelar jämfört med andra kodningsstandarder och -scheman:

* XMP metadata är mycket kraftfulla och detaljerade.
* XMP kan du ha flera värden för en egenskap.
* XMP har standardiserad kodning, vilket gör det enkelt att utbyta metadata.
* XMP kan utökas. Du kan lägga till ytterligare information i dina resurser.

### Utbyggbart {#extensible}

XMP är utformad för att vara utökningsbar, så att du kan lägga till anpassade typer av metadata i XMP. EXIF har däremot inte det, utan en fast lista över egenskaper som inte kan utökas.

>[!NOTE]
>
>XMP tillåter vanligtvis inte att binära datatyper bäddas in. Om du vill ha binära data i XMP, till exempel miniatyrbilder, måste de kodas i ett XML-anpassat format som Base64.

## XMP kärnbegrepp {#xmp-core-concepts}

I följande avsnitt beskrivs de centrala begreppen för XMP, inklusive namnutrymmen och scheman, egenskaper och värden samt språkalternativ.

### Namnutrymmen och scheman {#namespaces-and-schemata}

Ett XMP är en uppsättning egenskapsnamn i ett vanligt XML-namnutrymme som innehåller\
datatypen och beskrivande information. Ett XMP-schema identifieras av dess XML-namnområdes-URI. Om du använder namnutrymmen förhindras konflikter mellan egenskaper i olika scheman som har samma namn men en annan betydelse.

Egenskapen **Creator** i två självständigt utformade scheman kan till exempel avse den person som skapade resursen eller det program som skapade resursen (till exempel Adobe Photoshop).

### Egenskaper och värden {#properties-and-values}

XMP kan innehålla egenskaper från ett eller flera av scheman.

En vanlig delmängd som används av många Adobe-program kan till exempel vara följande:

* Dublin Core-schema: dc:title, dc:creator, dc:subject, dc:format, dc:rights
* XMP grundläggande schema: xmp:CreateDate, xmp:CreatorTool, xmp:ModifyDate, xmp:metadataDate
* XMP Rättighetshanteringsschema: xmpRights:WebStatement, xmpRights:Marked
* XMP för mediahantering: xmpMM:DocumentID

### Språkalternativ {#language-alternatives}

XMP ger dig möjlighet att lägga till en **xml:lang** -egenskap i textegenskaperna för att ange textens språk.
