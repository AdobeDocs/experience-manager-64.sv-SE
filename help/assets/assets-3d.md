---
title: Arbeta med 3D-resurser
seo-title: Arbeta med 3D-resurser
description: Lär dig hur du arbetar med 3D-resurser i AEM 3D
seo-description: Lär dig hur du arbetar med 3D-resurser i AEM 3D
uuid: a1c1bb29-9d3d-4025-8142-ed9719434bf9
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: introduction
content-type: reference
discoiquuid: 32143da1-09c8-45ce-b50d-32adf6efe383
translation-type: tm+mt
source-git-commit: 7c850ed0d20dd2ba2626242c67ba190e371f049f

---


# Arbeta med 3D-resurser {#working-with-d-assets}

Med AEM 3D (Adobe Experience Manager 3D) kan du överföra, hantera, visa och återge 3D-innehåll. Stöd för visning och återgivning är optimerat för enskilda objekt.

Se även [AEM 3D versionsinformation](/help/release-notes/aem3d-release-notes.md).

Se även [Installera och konfigurera AEM 3D](install-config-3d.md).

## Om modeller och faser i AEM 3D {#about-models-and-stages-in-aem-d}

Med AEM 3D kan du visa och återge statiska, fristående 3D-modeller av hög kvalitet i fördefinierade miljöer som kallas för scener. Scenen innehåller i princip&quot;ljus&quot; för 3D-scenen och inställningarna för återgivning i ett program som Autodesk® Maya® eller Autodesk 3ds Max®. Dessutom kan scenen även innehålla fördefinierade kameror, bakgrunder och geometri för markplan.

Överförda 3D-filer som innehåller ljus antas vara en scen. Du kan återställa sådana resurser till enkla 3D-objekt genom att öppna resursen på sidan med resursinformation. Tryck på **[!UICONTROL Visa egenskaper]** och sedan på fliken **[!UICONTROL Grundläggande]** . Välj **[!UICONTROL 3D-objekt]** i listrutan Resursklass under rubriken Metadata.

När du skapar 3D-modeller som ska användas i AEM 3D bör du tänka på följande:

* 3D-modellfilerna får endast innehålla ett objekt, utan bakgrunder, markplan, scenbelysning eller kameror.
* Placera modellen ovanför markplanet. Den här placeringen är särskilt viktig när du visar eller återger med faser som utgör ett markplan. En konfigurationsinställning är tillgänglig (och aktiverad som standard) som gör att objektet flyttas ovanför markplanet när du förhandsgranskar eller återger med Snabb förfining. Den här inställningen påverkar inte återgivning med tredjepartsrenderare (t.ex. via Maya), och därför kan objekt som inte finns ovanför markplanet vara delvis dolda.
* Placera modellen så att den centreras i sidled runt koordinatsystemets ursprung (0,0,0). På så sätt får du en bra interaktiv visningsupplevelse.
* Externa filreferenser stöds inte, förutom texturscheman. Därför måste du bädda in allt refererat innehåll i den primära modellfilen innan du överför det till AEM.

   Se [Om överföring och bearbetning av 3D-resurser i AEM](upload-processing-3d-assets.md).

* Scenens allmänna belysning tillhandahålls av scenen. Därför rekommenderar Adobe inte att du inkluderar ljus med 3D-modellfiler. Du kan inkludera ljus i modellen. De måste dock vara specifika endast för modellen. Det kan till exempel vara nödvändigt att inkludera ytterligare ljus för att göra en del av objektet ljusare som är skymt av andra delar. Den skulle därför inte vara tillräckligt synlig med enbart scenbelysningen.

## Filer som stöds i AEM 3D {#supported-files-in-aem-d}

En vanlig 3D-resurs har en primär modellfil och inga eller fler refererade filer. Refererade filer innehåller till exempel texturscheman eller **IBL-bilder (bildbaserad ljussättning)** .

### Om den primära 3D-modellfilen {#about-the-primary-d-model-file}

Den primära 3D-modellfilen innehåller den faktiska 3D-modellgeometrin och definitioner för (standard) material som används på modellytorna. AEM 3D har stöd för följande primära 3D-modellfilformat:

* Wavefront OBJ, filformat (`.obj`)

   OBJ-formatet kräver en eller flera separata, externa MTL-filer (materialmallsbibliotek) (`.mtl`).

* Autodesk FBX (Filmbox), filformat (`.fbx`)

   Autodesk 3D-filutbytesformat; både binära format och ASCII-format.

   När du skapar FBX-filer i tredjepartsprogram rekommenderar Adobe följande konfigurationsinställningar (se tabellen nedan). Dessa inställningar kan hjälpa dig att uppnå bästa resultat för 3D-filer som du tänker använda i AEM. Alternativnamnen hämtas från dialogrutan **[!UICONTROL Autodesk Maya FBX Export Options]** .

<table> 
 <tbody> 
  <tr> 
   <td><strong>Alternativ i Autodesk Maya FBX Export dialog</strong></td> 
   <td><strong>Beskrivning</strong></td> 
  </tr> 
  <tr> 
   <td>Bevara referenser<br /> </td> 
   <td><p>Avmarkera.</p> <p>AEM 3D stöder för närvarande inte externa referenser.</p> </td> 
  </tr> 
  <tr> 
   <td>Jämna nät<br /> </td> 
   <td>Välj.</td> 
  </tr> 
  <tr> 
   <td>Konvertera NURBS-ytor till</td> 
   <td><strong>Mesh för programvaruåtergivning</strong></td> 
  </tr> 
  <tr> 
   <td>Animering</td> 
   <td><p>Markera eller avmarkera.</p> <p>Om du väljer det här alternativet ignorerar AEM 3D animeringsinformationen i filen.</p> </td> 
  </tr> 
  <tr> 
   <td>Kameror</td> 
   <td><p>Välj för <strong>3D-stadier</strong>.</p> <p>Avmarkera för 3D-modeller.</p> </td> 
  </tr> 
  <tr> 
   <td>Ljus</td> 
   <td><p>Välj för <strong>3D-stadier</strong>.</p> <p>Avmarkera för <strong>3D-modeller</strong>.</p> </td> 
  </tr> 
  <tr> 
   <td>Enheter - automatiska</td> 
   <td>Välj. AEM 3D konverteras vid import.</td> 
  </tr> 
  <tr> 
   <td>Axelkonvertering - uppåtaxel</td> 
   <td><p><strong>Y-upp</strong></p> <p>Y-up ger enhetliga resultat när du exporterar från Maya och är det rekommenderade koordinatsystemet för FBX-filer i den här AEM 3D-versionen.</p> </td> 
  </tr> 
  <tr> 
   <td>Bädda in media</td> 
   <td>Båda alternativen stöds. Om inbäddad är markerat extraherar AEM 3D det inbäddade mediet till en intilliggande mapp som har samma namn som modellfilen med <code>.fbm</code> tillägg.</td> 
  </tr> 
  <tr> 
   <td>FBX-filformat - Typ</td> 
   <td>Både <strong>Binary </strong>och <strong>ASCII </strong>stöds.</td> 
  </tr> 
  <tr> 
   <td>FBX-filformat - version</td> 
   <td>FBX 2014/2015 rekommenderas. Andra versioner kan också fungera bra.</td> 
  </tr> 
 </tbody> 
</table>

Följande ytterligare filformat stöds om Autodesk Maya är installerat och konfigurerat på AEM-utvecklingsservrar:

* Autodesk Maya

   Både ASCII- `.ma` och binära `.mb` format.

* `Jupiter Tesselation (ISO 14306-1).jt`.

   Ett standardformat för utbyte av CAD-data, samarbete och produktvisualisering.

### Stöd för texturschemafiler {#support-for-texture-map-files}

Materialdefinitioner i 3D-modellfiler kan innehålla referenser till externa bildfiler som innehåller texturscheman. AEM 3D har stöd för följande typer av texturschemafiler:

* Diffusera färgtexturer
* Speglande färgtexturer
* Omgivande färgtexturer
* Förskjutningspapper (kallas även ojämnhetsscheman)
* Normala kartor
* Opacitetskartor
* Grovhetskartor (kallas även glans-, reflektivitets- eller cosinuskonfigurationer)

Material i den primära 3D-modellfilen kan referera till andra typer av kartor som ignoreras av AEM 3D.

### IBL-bilder (bildbaserad belysning) {#ibl-image-based-lighting-images}

En 3D-modellfil som definierar en scen kan referera till en enda IBL-miljöbild. För närvarande stöder AEM 3D endast 32-bitars TIFF-bilder i latitud-/longitudformat för diffus IBL och för speglingar. För sfärisk scenbakgrund stöds även 8-bitars RGB-bilder.

Se [Arbeta med IBL-stadier](working-with-ibl-stages.md).

>[!NOTE]
>
>Filreferenser - andra än de som beskrivs ovan - som finns i den primära 3D-modellfilen ignoreras för närvarande. AEM 3D stöder inte referenser till sekundära 3D-modellfiler.
Y-upp är det rekommenderade koordinatsystemet för FBX-filer i den här versionen.

## Materialskuggning i en primär 3D-modellfil {#material-shading-in-a-primary-d-model-file}

Den ursprungliga originalmodellfilen kan innehålla materialdefinitioner som används med skuggningar som Blinn, Lambert eller procedurskuggningar. Dessa potentiellt komplexa material stöds bara när du återger med motsvarande inbyggda program (som Autodesk Maya).

För visning eller när du återger med standardåtergivningen av Rapid Refine™ blir allt material antingen förenklat, ersatt eller båda så att det kan användas med en Phone-liknande skuggning. Skuggningen stöder en begränsad uppsättning attribut. Andra attribut i materialdefinitionen ignoreras.

Se [Visa 3D-resurser](viewing-3d-assets.md).

Se [Återge 3D-resurser](rendering-3d-assets.md).

## Namnge material i en primär 3D-modellfil {#naming-materials-in-a-primary-d-model-file}

En *yta* definieras som ytan i en 3D-modell som täcks av samma material. Det här materialet innehåller också ytans namn. Därför rekommenderar Adobe att du namnger materialet i de primära 3D-modellfilerna därefter. Om du t.ex. använder särskilda namn som &quot;Kropp&quot;, &quot;Fönster&quot;, &quot;Däck&quot; eller &quot;Rims&quot; bör du använda vaga namn som &quot;Rött&quot;, &quot;Glas&quot;, &quot;Gummi&quot; eller &quot;Aluminium&quot;.

