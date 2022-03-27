---
title: AEM Taggningsramverk
seo-title: AEM Tagging Framework
description: Tagga innehåll och utnyttja infrastrukturen för AEM taggar
seo-description: Tag content and leverage the AEM Tagging infrastructure
uuid: 55ba5977-217b-4b0f-a794-ddb9216ee62b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 4b680d17-383b-4173-a444-0b7bdb24e6c8
feature: Tagging
exl-id: bae592db-dc36-409f-b841-0582c464c3f6
source-git-commit: 381e760d1634dec6c6cdb933fd4da6b4652e6ff7
workflow-type: tm+mt
source-wordcount: '1764'
ht-degree: 0%

---

# AEM Taggningsramverk{#aem-tagging-framework}

Så här taggar du innehåll och använder den AEM taggningsinfrastrukturen:

* Taggen måste finnas som en nod av typen [`cq:Tag`](#tags-cq-tag-node-type) under [taxonomirotnod.](#taxonomy-root-node)
* Taggad innehåll-nodens `NodeType` måste innehålla [`cq:Taggable`](#taggable-content-cq-taggable-mixin) blanda.
* The [TaggID](#tagid) läggs till i innehållsnodens [`cq:tags`](#tagged-content-cq-tags-property) -egenskap och löses till en nod av typen [`cq:Tag`.](#tags-cq-tag-node-type)

## Taggar: cq:Tag Node Type  {#tags-cq-tag-node-type}

Deklarationen för en tagg hämtas i databasen i en nod av typen `cq:Tag.`

En tagg kan vara ett enkelt ord (t.ex. `fruit`) eller representerar en hierarkisk taxonomi (t.ex. `fruit/apple`, vilket innebär både frukt i allmänhet och mer specifikt äpple).

Taggar identifieras av ett unikt TagID.

En tagg har valfri metainformation, t.ex. en titel, lokaliserade titlar och en beskrivning. Titeln ska visas i användargränssnitt i stället för i `TagID`, om det finns.

Med taggningsramverket kan du även begränsa möjligheten för författare och besökare att endast använda specifika, fördefinierade taggar.

### Märkordsegenskaper {#tag-characteristics}

* Nodtypen är `cq:Tag`.
* Nodnamnet är en komponent i [`TagID`.](#tagid)
* The [`TagID`](#tagid) innehåller alltid [namnutrymme.](#tag-namespace)
* Valfritt `jcr:title` egenskap (den titel som ska visas i användargränssnittet)
* Valfritt `jcr:description` property
* När den innehåller underordnade noder kallas den för [behållartagg.](#container-tags)
* Den lagras i databasen under en bassökväg som kallas [taxonomirotnod.](#taxonomy-root-node)

### TaggID {#tagid}

A `TagID` identifierar en sökväg som löses till en taggnod i databasen.

Vanligtvis är `TagID` är en kortskrift som börjar med namnutrymmet eller så kan det vara absolut från [taxonomirotnod](#taxonomy-root-node).

Om innehållet är taggat och inte finns än, [`cq:tags`](#tagged-content-cq-tags-property) -egenskapen läggs till i innehållsnoden och `TagID` läggs till i egenskapens strängmatrisvärde.

The `TagID` består av en [namespace](#tag-namespace) följt av `TagID`. [Behållartaggar](#container-tags) har undertaggar som representerar en hierarkisk ordning i taxonomin. Undertaggar kan användas för att referera till taggar som är samma som alla lokala `TagID`. Exempel: tagga innehåll med `fruit` tillåts, även om det är en behållartagg med undertaggar, som `fruit/apple` och `fruit/banana`.

### Taxonomirotnod {#taxonomy-root-node}

Taxonomirotnoden är grundsökvägen för alla taggar i databasen. Taxonomirotnoden får inte vara en nod av typen `cq:Tag`.

I AEM är bassökvägen `/content/cq:tags` och rotnoden är av typen `cq:Folder`.

### Namnutrymme för tagg {#tag-namespace}

Namnutrymmen tillåter gruppobjekt. Det vanligaste användningsområdet är att ha ett namnutrymme per webbplats (t.ex. public, internal och portal) eller per större program (t.ex. Sites, Assets, Forms), men namnutrymmen kan användas för olika andra behov. Namnutrymmen används i användargränssnittet för att endast visa deluppsättningen taggar (d.v.s. taggar för ett visst namnutrymme) som är tillämpliga för det aktuella innehållet.

Taggens namnutrymme är den första nivån i taxonomiunderträdet, som är noden direkt under [taxonomirotnod](#taxonomy-root-node). Ett namnutrymme är en nod av typen `cq:Tag` vars överordnade inte är en `cq:Tag` nodtyp.

Alla taggar har ett namnutrymme. Om inget namnutrymme anges tilldelas taggen standardnamnutrymmet, som är `TagID` `default` (title is `Standard Tags`) som `/content/cq:tags/default`.

### Behållartaggar {#container-tags}

En behållartagg är en nod av typen `cq:Tag` som innehåller valfritt antal och valfri typ av underordnade noder, vilket gör det möjligt att förbättra taggmodellen med anpassade metadata.

Dessutom fungerar behållartaggar (eller supertaggar) i en taxonomi som delsummering av alla undertaggar. Innehåll som du t.ex. taggat med `fruit/apple` anses vara taggad med `fruit` också. Det innebär att sökning efter innehåll som är taggat med `fruit` söker även efter innehåll som taggats med `fruit/apple`.

### Lösa tagg-ID:n {#resolving-tagids}

Om tagg-ID:t innehåller ett kolon `:`avgränsar kolonet namnutrymmet från taggen eller undertaxonomin, som sedan avgränsas med normala snedstreck `/`. Om tagg-ID:t inte har ett kolon används standardnamnutrymmet.

Standardplatsen och den enda platsen för taggar är under `/content/cq:tags`.

Tagg som refererar till icke-befintliga banor eller banor som inte pekar på en `cq:Tag` noden betraktas som ogiltig och ignoreras.

I följande tabell visas några exempel `TagIDs`, deras element och hur `TagID` tolkas till en absolut sökväg i databasen.

| `TagID` | Namnutrymme | Lokalt ID | Behållartaggar | Lövtagg | Absolut databassökväg |
|---|---|---|---|---|---|
| `dam:fruit/apple/braeburn` | `dam` | `fruit/apple/braeburn` | `fruit`, `apple` | `braeburn` | `/content/cq:tags/dam/fruit/apple/braeburn` |
| `color/red` | `default` | `color/red` | `color` | `red` | `/content/cq:tags/default/color/red` |
| `sky` | `default` | `sky` | Inget | `sky` | `/content/cq:tags/default/sky` |
| `dam:` | `dam` | Inget | Inget | Inget | `/content/cq:tags/dam` |
| `/content/cq:tags/category/car` | `category` | `car` | `car` | `car` | `/content/cq:tags/category/car` |

### Lokalisering av taggtitel {#localization-of-tag-title}

När -taggen innehåller den valfria titelsträngen (`jcr:title`) går det att lokalisera titeln för visning genom att lägga till egenskapen `jcr:title.<locale>`.

Mer information finns i:

* [Taggar på olika språk,](/help/sites-developing/building.md#tags-in-different-languages) som beskriver hur API:erna används.
* [Hantera taggar på olika språk,](/help/sites-administering/tags.md#managing-tags-in-different-languages) som beskriver användningen av taggningskonsolen.

### Åtkomstkontroll {#access-control}

Taggar finns som noder i databasen under [taxonomirotnod.](#taxonomy-root-node) Du kan göra det möjligt för skribenter och besökare att skapa taggar i ett givet namnutrymme genom att ange lämpliga åtkomstkontrollistor i databasen.

Om du dessutom nekar läsbehörighet för vissa taggar eller namnutrymmen kan du styra möjligheten att använda taggar för visst innehåll.

En typisk konfiguration innefattar:

* Tillåta `tag-administrators` skrivåtkomst för grupp/roll till alla namnutrymmen (lägg till/ändra under `/content/cq:tags`).
   * Den här gruppen levereras med AEM.
* Ge användare/författare läsåtkomst till alla namnutrymmen som ska vara läsbara för dem (oftast alla).
* Ger användare/författare skrivåtkomst till de namnutrymmen där taggar ska kunna definieras fritt av användare/författare (`add_node` under `/content/cq:tags/some_namespace`)

## Taggbart innehåll: cq:Taggable Mixin {#taggable-content-cq-taggable-mixin}

För att programutvecklare ska kunna bifoga taggning till en innehållstyp, nodens registrering ([CND](https://jackrabbit.apache.org/node-type-notation.html)) måste innehålla `cq:Taggable` blanda eller `cq:OwnerTaggable` blanda.

The `cq:OwnerTaggable` mixin, som ärver från `cq:Taggable`, är avsedd att indikera att innehållet kan klassificeras av ägaren/författaren. I AEM är det bara ett attribut för `cq:PageContent` nod. The `cq:OwnerTaggable` mixin krävs inte av taggningsramverket.

>[!NOTE]
>
>Du bör bara aktivera taggar på den översta noden i ett aggregerat innehållsobjekt (eller på dess `jcr:content` nod). Exempel:
>
>* Sidor ( `cq:Page`) där `jcr:content`noden är av typen `cq:PageContent` som innehåller `cq:Taggable` blanda.
>* Resurser ( `cq:Asset`) där `jcr:content/metadata` noden har alltid `cq:Taggable` blanda.


### Nodtypsnotation (CND) {#node-type-notation-cnd}

Det finns nodtypsdefinitioner i databasen som CND-filer. CND-notation definieras som en del av JCR-dokumentationen [här](https://jackrabbit.apache.org/node-type-notation.html).

De viktigaste definitionerna för de nodtyper som ingår i AEM är följande:

```text
[cq:Tag] > mix:title, nt:base
    orderable
    - * (undefined) multiple
    - * (undefined)
    + * (nt:base) = cq:Tag version

[cq:Taggable]
    mixin
    - cq:tags (string) multiple

[cq:OwnerTaggable] > cq:Taggable
    mixin
```

## Taggat innehåll: cq:tagg, egenskap {#tagged-content-cq-tags-property}

The `cq:tags` egenskapen är en strängmatris som används för att lagra en eller flera `TagID`när de tillämpas på innehåll av författare eller webbplatsbesökare. Egenskapen har bara betydelse när den läggs till i en nod som definieras med [`cq:Taggable`](#taggable-content-cq-taggable-mixin) blanda.

>[!NOTE]
>
>För att utnyttja AEM taggningsfunktion bör anpassade utvecklade program inte definiera andra taggegenskaper än `cq:tags`.

## Flytta och sammanfoga taggar {#moving-and-merging-tags}

Nedan följer en beskrivning av effekterna i databasen när du flyttar eller sammanfogar taggar med [Taggningskonsol](/help/sites-administering/tags.md):

* När en tagg A flyttas eller sammanfogas till tagg B under `/content/cq:tags`:

   * Tagg A tas inte bort och en `cq:movedTo` -egenskap.
   * Tagg B skapas (vid en flytt) och får ett `cq:backlinks` -egenskap.

* `cq:movedTo` pekar på tagg B.

   * Den här egenskapen innebär att tagg A har flyttats eller sammanfogats till tagg B.
   * Om du flyttar tagg B uppdateras den här egenskapen i enlighet med detta. Tagg A är alltså dold och sparas bara i databasen för att matcha tagg-ID:n i innehållsnoder som pekar på tagg A.
   * Taggskräpinsamlaren tar bort taggar som tagg A en gång och inga fler innehållsnoder pekar på dem.
   * Ett specialvärde för `cq:movedTo` egenskapen är `nirvana`: används när taggen tas bort men inte kan tas bort från databasen eftersom det finns undertaggar med en `cq:movedTo` som måste behållas.

      >[!NOTE]
      >
      >The `cq:movedTo` egenskapen läggs bara till i den flyttade eller sammanfogade taggen om något av dessa villkor uppfylls:
      >
      >1. Taggen används i innehåll (vilket innebär att den har en referens).
      >1. Taggen har underordnade objekt som redan har flyttats.


* `cq:backlinks` behåller referenserna i den andra riktningen, dvs. en lista över alla taggar som har flyttats till eller sammanfogats med tagg B.

   * Detta krävs oftast för att behålla `cq:movedTo`egenskaperna är uppdaterade även när tagg B flyttas/sammanfogas/tas bort eller när tagg B aktiveras, och då måste även alla dess bakåttaggar aktiveras.

>[!NOTE]
>
>The `cq:backlinks` egenskapen läggs bara till i den flyttade eller sammanfogade taggen om något av dessa villkor uppfylls:
>
>1. Taggen används i innehåll (vilket innebär att den har en referens).
>1. Taggen har underordnade objekt som redan har flyttats.


* Läsa en `cq:tags` egenskapen för en innehållsnod omfattar följande matchning:

   1. Om det inte finns någon matchning under `/content/cq:tags`, returneras ingen tagg.
   1. Om taggen har en `cq:movedTo` egenskapsuppsättningen följs det refererade tagg-ID:t.

      * Det här steget upprepas så länge som den efterföljande taggen har en `cq:movedTo` -egenskap.
   1. Om den följande taggen inte har en `cq:movedTo` -egenskapen läses taggen.


* Om du vill publicera ändringen när en tagg har flyttats eller sammanfogats väljer du `cq:Tag` noden och alla dess bakgrunder måste replikeras.
   * Detta görs automatiskt när taggen aktiveras i tagghanteringskonsolen.

* Senare uppdateringar av sidans `cq:tags` -egenskapen rensar automatiskt de &quot;gamla&quot; referenserna.
   * Detta utlöses eftersom en flyttad tagg som löses via API returnerar måltaggen och därmed anger måltaggens ID.

## Migrering av taggar {#tags-migration}

I Adobe Experience Manager 6.4 och senare lagras taggar under `/content/cq:tags`. Om Adobe Experience Manager har uppgraderats från en tidigare version finns dock taggarna kvar på den gamla platsen `/etc/tags`. I uppgraderade system måste taggar migreras till `/content/cq:tags`.

>[!NOTE]
>
>På sidan Sidegenskaper för taggar rekommenderar vi att du använder tagg-ID (till exempel `geometrixx-outdoors:activity/biking`) i stället för att hårdkoda taggbassökvägen (till exempel `/etc/tags/geometrixx-outdoors/activity/biking`).
>
>Om du vill visa taggar `com.day.cq.tagging.servlets.TagListServlet` kan användas.

>[!NOTE]
>
>Vi rekommenderar att du använder tagghanterings-API som resurs.

### Om uppgraderad AEM instans stöder TagManager API**

1. I början av komponenten identifierar TagManager API om det är en uppgraderad AEM. I uppgraderat system lagras taggar under `/etc/tags`.

1. TagManager API körs sedan i bakåtkompatibilitetsläge, vilket innebär att API:t använder `/etc/tags` som grundsökväg. I annat fall används en ny plats `/content/cq:tags`.

1. Uppdatera platsen för taggarna.

1. Kör följande skript när du har migrerat taggar till den nya platsen.

```java
import org.apache.sling.api.resource.*
import javax.jcr.*

ResourceResolverFactory resourceResolverFactory = osgi.getService(ResourceResolverFactory.class);
ResourceResolver resolver = resourceResolverFactory.getAdministrativeResourceResolver(null);
Session session = resolver.adaptTo(Session.class);

def queryManager = session.workspace.queryManager;
def statement = "/jcr:root/content/cq:tags//element(*, cq:Tag)[jcr:contains(@cq:movedTo,\'/etc/tags\') or jcr:contains(@cq:backlinks,\'/etc/tags\')]";
def query = queryManager.createQuery(statement, "xpath");

println "query = ${query.statement}\n";

def tags = query.execute().getNodes();


tags.each { node ->
        def tagPath = node.path;
        println "tag = ${tagPath}";

        if(node.hasProperty("cq:movedTo") && node.getProperty("cq:movedTo").getValue().toString().startsWith("/etc/tags")){

                def movedTo = node.getProperty("cq:movedTo").getValue().toString();

                println "cq:movedTo = ${movedTo} \n";

                movedTo = movedTo.replace("/etc/tags","/content/cq:tags");
                node.setProperty("cq:movedTo",movedTo);
        } else if(node.hasProperty("cq:backlinks")){

               String[] backLinks = node.getProperty("cq:backlinks").getValues();
               int count = 0;

               backLinks.each { value ->
                       if(value.startsWith("/etc/tags")){
                               println "cq:backlinks = ${value}\n";
                               backLinks[count] = value.replace("/etc/tags","/content/cq:tags");
    }
                       count++;
               }

               node.setProperty("cq:backlinks",backLinks);
  }
}
session.save();

println "---------------------------------Success-------------------------------------"
```

Skriptet hämtar alla taggar som har `/etc/tags` i värdet av `cq:movedTo/cq:backLinks` -egenskap. Sedan itereras den genom den hämtade resultatuppsättningen och löser problemet `cq:movedTo` och `cq:backlinks` egenskapsvärden till `/content/cq:tags` banor (i det fall där `/etc/tags` identifieras i värdet).

### Om den uppgraderade AEM instansen körs i det klassiska användargränssnittet**

>[!NOTE]
>
>Klassiskt användargränssnitt är inte noll som är nedtidskompatibelt och stöder inte den nya taggens grundsökväg. Om du vill använda ett klassiskt användargränssnitt än `/etc/tags` måste skapas följt av `cq-tagging` starta om komponenten.

Om de uppgraderade AEM-instanserna stöds av TagManager API och körs i Classic UI:

1. En gång refererar till den gamla taggbassökvägen `/etc/tags` ersätts med tagg-ID eller ny taggplats `/content/cq:tags`kan du migrera taggar till den nya platsen `/content/cq:tags` i CRX DE följt av komponentomstart.

1. Kör skriptet ovan när du har migrerat taggar till den nya platsen.
