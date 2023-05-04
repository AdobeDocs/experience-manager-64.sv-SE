---
title: Bildredigeraren
seo-title: Image Editor
description: Bildredigeraren är en AEM och kan utnyttjas av komponenter för att underlätta redigering av bilder av innehållsförfattare.
seo-description: The Image Editor is a core piece of AEM and can be leveraged by components to facilitate the manipulation of images by content authors.
uuid: de6ac71b-380a-4b67-b697-ac34a79a9cc4
contentOwner: bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: components
discoiquuid: f6347492-cf48-4835-b8fd-ce9a75a09abe
exl-id: 843c67d6-dda1-448f-a992-19574066e1c3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Bildredigeraren{#image-editor}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Bildredigeraren är en AEM och kan utnyttjas av komponenter för att underlätta redigering av bilder av innehållsförfattare.

>[!CAUTION]
>
>Om du vill använda funktionerna i bildredigeraren som beskrivs i den här artikeln [funktionspaket 24267](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/featurepack/cq-6.4.0-featurepack-24267) måste vara installerat.

## Relativa enheter för bildschema {#relative-units-for-image-map}

Bildredigeraren behåller bildschemaområden som både absoluta och relativa enheter. Relativa enheter är användbara när de anges som dataattribut för att dynamiskt ändra storlek på ett bildschema (i förhållande till bildstorleken) på klientsidan i en responsiv bildkomponent.

### imageMap, egenskap {#imagemap-property}

Koordinaterna för bildschemat bevaras till JCR som en `imageMap` av bildredigeraren. Den har följande format.

Egenskapen lagrar kartområden enligt följande:

`[area1][area2][...]`

Områdesformat:

`[SHAPE(COORDINATES)"HREF"|"TARGET"|"ALT"|(RELATIVE_COORDINATES)]`

Exempel:

`[rect(0,0,10,10)"https://www.adobe.com"|"_self"|"alt"|(0,0,0.8,0.8)]`
`[circle(10,10,10)"https://www.adobe.com"|"_self"|"alt"|(0.8,0.8,0.8)]`

## Stöd för SVG-bilder {#support-for-svg-images}

Skalbar vektorgrafik (SVG) stöds av bildredigeraren.

* Både dra-och-släpp av en SVG-resurs från DAM och överföring av en SVG-filöverföring från ett lokalt filsystem stöds.

## Aktivera plugin-program efter MIME-typ {#enabling-plugins-by-mime-type}

I vissa situationer måste redigeringsåtgärderna begränsas för vissa MIME-typer, eftersom det inte finns stöd för bearbetning på serversidan. Det är till exempel inte tillåtet att redigera bilder i SVG.

Insticksprogram i bildredigeraren kan aktiveras selektivt av MIME-typ genom att en `supportedMimeTypes` på den enskilda plugin-programmets konfigurationsnod.

### Exempel {#example}

Låt oss till exempel säga att beskärning bara ska vara tillåten för bilderna GIF, JPEG, PNG, WEBP och TIFF.

The `supportedMimeTypes` måste sedan anges som en sträng med de tillåtna MIME-typerna på konfigurationsnoden för plugin-programmet på `cq:editConfig` bildkomponentens nod.

`/apps/core/wcm/components/image/v2/image/cq:editConfig`

```xml
 jcr:primaryType="cq:EditConfig">
     <cq:dropTargets jcr:primaryType="nt:unstructured">
         <image ...>
            ...
         </image>
     </cq:dropTargets>
     <cq:inplaceEditing
         jcr:primaryType="cq:InplaceEditingConfig"
         active="{Boolean}true"
         editorType="image">
         <config jcr:primaryType="nt:unstructured">
             <plugins jcr:primaryType="nt:unstructured">
                 <crop
                     jcr:primaryType="nt:unstructured"
                     supportedMimeTypes="[image/gif,image/jpeg,image/png,image/webp,image/tiff]"
                     features="*">
                     <aspectRatios jcr:primaryType="nt:unstructured">
                        ...
                     </aspectRatios>
                 </crop>
                 ...
             </plugins>
             <ui jcr:primaryType="nt:unstructured">
                 ...
             </ui>
         </config>
     </cq:inplaceEditing>
 </jcr:root>
```
