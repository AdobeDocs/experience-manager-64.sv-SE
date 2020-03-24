---
title: Hantera metadata för dina digitala resurser
description: Lär dig mer om metadatatyperna och hur Adobe Experience Manager Assets hjälper dig att hantera metadata för resurser så att det blir enklare att kategorisera och ordna resurser. Med möjligheten att behålla och hantera godtyckliga metadata med era resurser gör Adobe Experience Manager Assets det möjligt att automatiskt ordna och bearbeta resurser baserat på deras metadata.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 5ef4c4e42165819191c6e3810c36183110f3f34a

---


# Hantera metadata för dina digitala resurser {#managing-metadata-for-digital-assets}

Adobe Experience Manager Assets sparar metadata för alla resurser. Detta gör det enklare att kategorisera och ordna resurser och det hjälper personer som letar efter en viss resurs. Tack vare möjligheten att extrahera metadata från filer som överförts till Experience Manager Assets kan metadatahanteringen integreras med det kreativa arbetsflödet. Med Experience Manager kan ni behålla och hantera metadata med era resurser och automatiskt ordna och bearbeta resurser baserat på metadata.

* [XMP-metadata](xmp.md)
* [Redigera eller lägga till metadata](meta-edit.md)
* [Referens för metadatamappningar](meta-ref.md)

## Därför behöver vi metadata {#why-we-need-metadata}

Metadata är data om data. I det här avseendet avser data era digitala resurser, till exempel en bild. Metadata är avgörande för effektiv resurshantering.

Metadata är en samling med alla data som är tillgängliga för en resurs, men som inte nödvändigtvis finns i bilden. Några exempel på metadata är:

* Namnet på resursen.
* Tid och datum för senaste ändring.
* Storlek på resursen när den sparades i databasen.
* Namnet på mappen som den finns i.
* Relaterade resurser eller tillämpade taggar.

Detta är de grundläggande metadataegenskaper som Experience Manager kan hantera för resurser, vilket gör att användare kan se alla resurser, till exempel ordnade efter det senaste ändringsdatumet - användbart när de försöker identifiera vilka resurser som nyligen har lagts till i databasen.

Du kan lägga till mer högnivådata till digitala resurser, till exempel:

* Typ av resurs (är det en bild, en video, ett ljudklipp eller ett dokument?).
* Tillgångens ägare.
* Tillgångens namn.
* Beskrivning av tillgången.
* Taggar som tilldelats en resurs.

Fler metadata hjälper dig att kategorisera resurser ytterligare och är till hjälp när mängden digital information växer. Det går att hantera några hundra filer baserat på bara filnamnen. Den här metoden är dock inte skalbar och blir snabbt kort när antalet inblandade personer och antalet förvaltade resurser ökar.

När metadata läggs till i resurser växer resursens värde eftersom resursen blir

* mer åtkomligt - det är mycket enklare för andra.
* enklare att hantera - du kan hitta resurser med samma uppsättning egenskaper enklare och använda ändringarna på dem.
* mer komplex - ju mer metadata du har lagt till i en resurs, desto viktigare blir det att hantera metadata.

Av dessa skäl ger Experience Manager Assets er det rätta sättet att skapa, hantera och utbyta metadata för era digitala resurser.

## Typer av metadata {#types-of-metadata}

De två grundläggande metadatatyperna är tekniska metadata och beskrivande metadata.

Tekniska metadata är användbara för program som hanterar digitala resurser och bör inte underhållas manuellt. Experience Manager Assets och andra program bestämmer automatiskt tekniska metadata och metadata kan ändras när resursen ändras. Vilka tekniska metadata som är tillgängliga för en mediefil beror till stor del på filtypen för resursen. Några exempel på tekniska metadata är:

* Storlek på en fil
* Bildens mått (höjd och bredd)
* Bithastighet för en ljud- eller videofil
* Bildens upplösning (detaljnivå)

Beskrivande metadata är metadata som rör programdomänen, till exempel det företag som en resurs kommer från. Beskrivande metadata kan inte bestämmas automatiskt. Den skapas manuellt eller halvautomatiskt. En GPS-aktiverad kamera kan till exempel automatiskt spåra latitud och longitud och lägga till geotagga bilden.

På grund av den höga kostnaden för manuell insats som krävs för att skapa beskrivande metadatainformation har standarder upprättats för att underlätta utbyte av metadata mellan olika programsystem och organisationer.

Experience Manager Assets stöder alla relevanta standarder för metadatahantering.

Eftersom metadata är så viktiga och det krävs mycket manuellt arbete för att skapa metadata har standarder fastställts som gör det enklare att utbyta.

## Kodningsstandarder {#encoding-standards}

Det finns olika sätt att bädda in metadata i filer. Ett urval kodningsstandarder stöds:

* XMP: som används av Experience Manager Assets för att lagra extraherade metadata i databasen.
* ID3: för ljud- och videofiler.
* Exif: för bildfiler.
* Annat/äldre: från Microsoft Word, PowerPoint, Excel och så vidare.

### XMP {#xmp}

XMP (Extensible Metadata Platform) är en öppen standard som används av Experience Manager Assets för all metadatahantering. Standarden erbjuder universell metadatakodning som kan bäddas in i alla filformat. Adobe och andra företag stöder XMP-standarden eftersom den erbjuder en innehållsmodell med mycket innehåll. Användare av XMP-standard och Experience Manager Assets har en kraftfull plattform att bygga vidare på. For more information, see [XMP](https://www.adobe.com/products/xmp.html).

### ID3 {#id}

Data som lagras i dessa ID3-taggar visas när du spelar upp en digital ljudfil på datorn eller en bärbar MP3-spelare.

ID3-taggar är utformade för filformatet MP3. Mer information om format:

* ID3-taggar fungerar i MP3- och mp3PRO-filer.
* WAV saknar taggar.
* WMA har egna taggar som inte tillåter implementering med öppen källkod.
* Ogg Vorbis använder Xiph-kommentarer som är inbäddade i Ogg-behållaren.
* AAC använder ett märkordsformat.

### Exif {#exif}

Exchangeable image file format (Exif) är det vanligaste metadataformatet som används för digitalfoto. Det är ett sätt att bädda in en fast ordlista med metadataegenskaper i många filformat, till exempel JPEG, TIFF, RIFF och WAV. Exif lagrar metadata som par av ett metadatanamn och ett metadatavärde. Dessa metadata name-value-pars kallas också taggar, som inte ska blandas ihop med taggarna i Experience Manager. Eftersom Exif automatiskt skapas av moderna digitalkameror och stöds av moderna grafikprogram, kan det ses som den lägsta gemensamma nämnaren för metadatahantering.

En stor begränsning för Exif är att ett fåtal populära bildfilsformat som BMP, GIF och PNG inte har stöd för det.

Metadatafält som vanligtvis definieras av Exif är av teknisk natur och har begränsad användning för beskrivande metadatahantering. Därför erbjuder Experience Manager Assets mappning av Exif-egenskaper till [vanliga metadatamatchningar](metadata-schemas.md) och till [XMP](xmp-writeback.md).

### Andra metadata {#other-metadata}

Andra metadata som kan bäddas in från filer är bland annat Microsoft Word, PowerPoint och Excel.

## Metadata-scheman {#metadata-schemata}

Metadata-scheman är fördefinierade uppsättningar metadataegenskapsdefinitioner som kan användas i olika program. Egenskaper är alltid kopplade till en resurs, vilket innebär att egenskaperna är&quot;about&quot; the resource.

Du kan också utforma egna metadatamatchningar om det inte finns några som passar dina behov. Duplicera inte befintlig information. Inom en organisation gör separerade scheman det enklare att dela metadata. I Experience Manager finns en standardlista med de vanligaste metadatamappningarna. Listan hjälper dig att snabbt komma igång med metadatastrategin och snabbt välja de metadataegenskaper du behöver.

De metadatamappningar som stöds listas nedan.

### Standardmetadata {#standard-metadata}

* dc - Dublin Core - den viktigaste och mest använda uppsättningen metadata.
* DICOM - Digital Imaging and Communications in Medicine.
* Iptc4xmpCore &amp; iptc4xmpExt - International Press Communications Standard - massor av ämnesspecifika metadata.
* rdf - Resource Description Framework - för generiska semantiska webbmetadata.
* xmp - Extensible Metadata Platform.
* xmpBJ - Grundläggande jobbiljetter.

### Programspecifika metadata {#application-specific-metadata}

Programspecifika metadata innehåller tekniska och beskrivande metadata. Om du använder dessa kanske andra program inte kan använda metadata. Om du t.ex. har en resurs med Adobe Photoshop-metadata och ett annat bildåtergivningsprogram försöker få åtkomst till metadata kanske det inte går att få åtkomst till metadata. Om du har mycket programspecifika metadata i dina resurser kan du skapa ett arbetsflödessteg som ändrar en programspecifik egenskap till en standardegenskap.

* cd-see - metadata hanteras av ACDSee-programmet [www.acdsee.com/](https://www.acdsee.com/).
* album - Adobe Photoshop Album.
* cq - används av Experience Manager Assets.
* dam - används av Experience Manager Assets.
* dex - Optima SC Description Explorer.
* crs - Adobe Photoshop Camera Raw.
* lr - Adobe Lightroom.
* mediapro - IView MediaPro.
* Microsoft Photo &amp; MP - Microsoft Photo.
* pdf och pdfx
* photoshop &amp; psAux - Adobe Photoshop

### Metadata för hantering av digitala rättigheter {#digital-rights-management-metadata}

* cc - creative comms
* xmpRights
* plus - Picture Licensing Universal System - https://www.useplus.com/
* prisma - https://www.idealliance.org/prism-metadata Publiceringskrav för branschstandardmetadata
* prl - Prism Rights Language
* pur - Användarrättigheter för prismaanvändning
* xmpPlus - integrering av PLUS med XMP

### Fotografispecifika metadata {#photography-specific-metadata}

* exif - massor av teknisk information från kameran, inklusive GPS-position
* crs - photoshop camera raw
* Iptc4xmpCore och iptc4xmpExt
* TIFF - bildmetadata (inte bara för TIFF-bilder)

### Utskriftsspecifika metadata {#print-specific-metadata}

* pdf och pdfx - Adobe PDF och tredjepartsprogram
* prisma - [www.prismstandard.org](https://www.prismstandard.org) publiceringskrav för branschstandardmetadata
* xmp
* xmpPG - xmp för växlad text

### Multimediaspecifika metadata {#multimedia-specific-metadata}

* xmpDM - Dynamiska media
* xmpMM - Mediehantering

## Metadatastyrda arbetsflöden {#metadata-driven-workflows}

Genom att skapa metadatadrivna arbetsflöden kan du automatisera vissa processer, vilket ökar effektiviteten. I ett metadatadrivet arbetsflöde läser arbetsflödet och utför därför en fördefinierad åtgärd. Du kan till exempel använda metadatadrivna arbetsflöden på olika sätt:

* Arbetsflödet kan kontrollera om en bild har en titel. Om så inte är fallet meddelas användaren om att lägga till en titel.
* Arbetsflödet kan kontrollera om ett copyrightmeddelande för en mediefil tillåter distribution. Om så är fallet skickas resursen till en server. Om så inte är fallet skickas resursen till en annan server.
* Ett arbetsflöde kan söka efter resurser utan fördefinierade, obligatoriska metadata eller med *ogiltiga* metadata.
