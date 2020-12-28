---
title: PUBLICERA INTE, MEN ANPASSA INTE DELETE-datatyper för modeller för innehållsfragment
seo-title: Anpassa datatyper för modeller för innehållsfragment
description: Datatyper som används i Content Fragment Models kan anpassas.
seo-description: Datatyper som används i Content Fragment Models kan anpassas.
page-status-flag: de-activated
uuid: d8215dbf-2dbe-43cb-a5c1-dc1cb412a204
contentOwner: aheimoz
discoiquuid: a8b8155c-852c-4d16-b59b-7e19527c2bd4
noindex: true
translation-type: tm+mt
source-git-commit: 3bdff366a0d455b405c1f9de371ced98d25ae2e2
workflow-type: tm+mt
source-wordcount: '1642'
ht-degree: 0%

---


# PUBLICERA INTE, MEN ANPASSA INTE DELETE-datatyper för modeller för innehållsfragment{#do-not-publish-but-do-not-delete-customizing-data-types-for-content-fragment-models}

[Innehållsfragmentering ](/help/assets/content-fragments.md) baseras på  [innehållsfragmentmodeller](/help/assets/content-fragments-models.md). Dessa modeller är uppbyggda av [element](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) av olika datatyper.

Det finns olika datatyper som är tillgängliga direkt, bland annat enkelradig text, multiradig text, numeriska fält, booleska väljare, alternativ på rullgardinsmenyn, datum och tid med mera. AEM kan välja datatyper baserat på redigeringsmetoden för motsvarande fragment. På så sätt kan du hantera enkla textmodeller till komplexa modeller med olika typer av innehåll och tillhörande fragmentredigeringsupplevelse.

Datatyperna definieras av en [kombination av nodegenskaper](#properties) som finns på [specifika platser i databasen](#locations-in-the-repository). Du kan också skapa egna [datatyper](#creating-your-data-type) och [fieldProperties](#creating-your-own-fieldproperties-property).

<!-- Please uncomment when files are used>
>[!NOTE]
>
>See also [Customizing Content Fragment Models](/help/sites-developing/customizing-content-fragment-models.md).
-->

## Platser i databasen {#locations-in-the-repository}

Alla färdiga datatyper deklareras under:

`/libs/settings`

Du kan lägga till nya datatyper genom att täcka över nodstrukturen enligt följande under `/apps`:

`/apps/settings/dam/cfm/models/formbuilderconfig/datatypes/items`

>[!CAUTION]
>
>Du får inte ändra något i `/libs`-sökvägen.
>
>Allt som kan ändras vid nästa uppgradering, eller vid installation av en tjänst eller ett korrigeringspaket.

## Egenskaper {#properties}

Nodegenskaper används för att definiera datatyperna:

* [Egenskaper för datatyper](#data-type-properties)
* och i dessa [fieldProperties](#fieldproperties)

### Egenskaper för datatyp {#data-type-properties}

Alla datatyper visas i en nodstruktur som under:

`/libs/settings/dam/cfm/models/formbuilderconfig/datatypes/items`

Varje nod under `/items` har egenskaper som definierar hur den datatypen ska representeras inuti modellredigeraren.

Alla följande egenskaper måste finnas för att datatypen ska finnas i modellredigeraren:

* `fieldIcon`

   [CoralUI-](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/coral-ui/coralui3/Coral.Icon.html#availableicons) ikonen representerar datatypen i modellredigeringsgränssnittet.

* ` [fieldProperties](#fieldproperties)`

   En array som representerar konfigurationsegenskaperna för varje datatyp.

* `fieldResourceType`

   Den Sling-resurstyp som används för att återge datatypen i ett innehållsfragment. För datatyper som kan återges på olika sätt (t.ex. som enkel textinmatning och/eller flerradig textinmatning) måste den här egenskapen skapas som en array som innehåller alla resurstyper. Egenskapen `renderasfield` läggs automatiskt till i `fieldProperties` så att användaren kan välja vilken resurstyp som ska läggas till i modellen.

* `fieldPropResourceType`

   Den Sling-resurstyp som används för att återge standardegenskapen för datatypen.

   För datatypen:

   * Enkelradig text, skulle `fieldPropResourceType` vara en `textfield`-komponent
   * Boolean: `fieldPropResourceType` skulle vara en `checkbox`-komponent

* `fieldViewResourceType`

   Den Sling-resurstyp som används för att återge datatypen i förhandsgranskningen, när modellen skapas. När användaren drar datatypen till vänster om modellredigeraren representerar egenskapen `fieldViewResourceType` komponenten som återges där. Detta används för fall där du inte vill återge den fullständiga komponenten, men bara vill återge en ersättning som minimerar overheadkostnaden för modellredigeraren.

* `fieldTitle`

   Egenskap som definierar titeln för den här datatypen. Exempel: **Enkelradig text** för en `textfield`-komponent, **Flerradig text** för en flerfältskomponent.

* `valueType`

   Detta är den typ av värde som datatypen returnerar när den lagras internt. Se [Mappningar](#mappings).

* `renderType`

   Detta är en intern representation av datatypen. Den ansluter `valueType` till en UI-komponent. Se [Mappningar](#mappings).

* `listOrder`

   Varje datatyp behöver ett värde som representerar dess ordning i listan. Detta används för att säkerställa att de olika fälten ordnas korrekt (läggs till/flyttas genom att användaren drar och släpper) när modellredigeraren sparas. Värdet måste vara ett heltal och du bör tilldela talet i stigande ordning. När du skapar en ny datatyp är det bäst att tilldela värdet baserat på den senaste datatypen i listan (det högsta värdet på `listOrder`-värdet som finns i datatyperna).

#### Mappningar {#mappings}

<table> 
 <tbody> 
  <tr> 
   <td>Datatyp<br /> </td> 
   <td>Värdetyp<br /> </td> 
   <td>Återgivningstyp</td> 
  </tr> 
  <tr> 
   <td>Enkelradig text</td> 
   <td>string</td> 
   <td>text-single</td> 
  </tr> 
  <tr> 
   <td>Flerradstext</td> 
   <td>sträng, med innehållstyp<br /> </td> 
   <td>text-multi</td> 
  </tr> 
  <tr> 
   <td>Tal (heltal/lång)<br /> </td> 
   <td>long</td> 
   <td>tal</td> 
  </tr> 
  <tr> 
   <td>Number (double/float)</td> 
   <td>double</td> 
   <td>tal</td> 
  </tr> 
  <tr> 
   <td>Boolesk</td> 
   <td>boolean</td> 
   <td>boolesk</td> 
  </tr> 
  <tr> 
   <td>Datum och tid</td> 
   <td>kalender</td> 
   <td>time</td> 
  </tr> 
  <tr> 
   <td>Uppräkning</td> 
   <td>string/long</td> 
   <td>uppräkning</td> 
  </tr> 
  <tr> 
   <td>Taggar</td> 
   <td>string</td> 
   <td>taggar</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Vissa typer (till exempel `string`, `long`) kan vara flervärden. I det här fallet kapslas komponenten som används för återgivning och redigering vanligtvis in av en flerfältskomponent ( `granite/ui/components/coral/foundation/form/multifield`). Undantaget är taggar, där redigeringskomponenten ansvarar för att återge den korrekt.

### fieldProperties {#fieldproperties}

Konfigurationsegenskaperna för varje datatyp. Värden för `fieldProperties`:

* `base`

   Detta är grunden för alla `fieldProperties`-komponenter. Definitionen finns under `/libs/dam/cfm/models/editor/components/datatypeproperties/base`.

   Den innehåller variabeln `fieldRoot`, som efterföljande `fieldProperties` kan använda när indata skapas för att hämta rätt sökväg.

   Exempel: för att få rätt sökväg för en **fältetikett** behöver du nyckeln för att identifiera den komponent som det här tillhör, ska indata för det här fältet vara `fieldRoot` + `<*fieldLabel*>`

* `checkboxfields`

   Den här komponenten lägger till standardkryssrutan för datatypen `Boolean` samt Sling-parametrarna `checked@Delete` och `checked@TypeHint`.

* `datepickerfields`

   Komponent som lägger till de dolda indata som behövs för att datumväljarkomponenten ska fungera. Innehåller att skapa egenskaperna `defaultDateField`, `displayedFormat`, `emptyText`, `valueFormat`, `minDate` och `maxDate`.

* `datetimepickerfields`

   Detta lägger till ett urvalsfält för datatypen `Date&Time` för att skilja mellan alternativen `Date` och `Date&Time`.

* `datevaluefield`

   Detta lägger till en datumväljare i egenskaperna, så att en användare kan välja en standard för datatypen `Date&Time`.

* `descriptionfield`

   Den här komponenten lägger till ett textfält med flera rader som representerar beskrivningen av den markerade komponenten i flerradsredigeraren. Den läggs automatiskt till av modellredigerarrenderaren i slutet av varje datatypsegenskap.

* `labelfield`

   Komponent som lägger till `textfield`-indata som lägger till fältetiketten för en datatyp som kan ha fältetiketter.

* `maptopropertyfield`

   Den här komponenten lägger till fältet `Name` i egenskaperna och ger en identifierare till den markerade komponenten i en datatyp. Den ska finnas i alla datatyper.

* `maxlengthfield`

   Den används för att lägga till egenskapen `maxLength` för användning med datatyper som accepterar den här egenskapen. Exempel: med **enkelradig text**, **Number** osv.

* `multieditorfield`

   Då läggs alla dolda fält till som behövs för att flerradsredigeraren ska fungera, vilket representeras av datatypen **Flerradig text**.

* `mvfields`

   Komponent som lägger till alla dolda fält som behövs för att en flerfältskomponent ska fungera. För det andra alternativet för datatypen **Single Line Text**. Detta bör läggas till för alla komponenter som återges som ett multifält.

* `numbertypefield`

   Välj ett alternativ för datatypen **Number** som väljer mellan **Integer** eller **Fraction** för datatypen **Number**.

* `numbervaluefield`

   En `numberfield`-standardvärdesväljare för datatypen **Number** `type.options` Detta lägger till alternativindata för datatypen **Enumeration**, som används för att fastställa värdena för markeringsrutekomponenten.

* `placeholderfield`

   Detta är ett textfält som fungerar som indata för en komponents `emptyText`-egenskap. Detta bör användas av alla datatyper som accepterar en platshållare (som inte är särskilt komplicerad). t.ex. **Enkelradig text**, **Tal** osv.).

* `renderasfield`

   Det här är den komponent som återges automatiskt när flera `fieldResourceTypes` finns i datatypsnodens egenskap.

* `requiredfield`

   Det här är en kryssruta som representerar egenskapen `required` för en komponent. Eftersom de flesta komponenter accepterar fältet `required` kan det här fältet användas för de flesta datatyper.

* `tagsfields`

   Komponenter som lägger till de indata som krävs för att en `tagfield`-komponent ska återges, används av datatypen **Taggar**.

* `tagsroot`

   En sökvägsväljare som används av datatypen **Taggar** för att ange rotsökvägen för `tagsfield`-komponenten.

* `textfield`

   Används av datatypen `Boolean` för att ange fältetiketten för kryssrutan som definieras av den här datatypen.

* `textvaluefield`

   Standardvärdeegenskapen för datatypen **Single Line Text**.

## Skapar din datatyp {#creating-your-data-type}

Om du vill skapa en egen datatyp måste du:

* [Skapa nodstrukturen](#creating-the-node-structure)
* [Definiera egenskaperna för din datatyp](#defining-the-properties-for-your-data-type)

Du kan sedan [använda din datatyp](#using-your-data-type).

Du kan också [skapa en egen `fieldProperties`](#creating-your-own-fieldproperties-property).

### Skapa nodstrukturen {#creating-the-node-structure}

Nodstrukturen måste skapas under `/apps` för att datatyperna ska kunna överlappas. Om den inte redan finns måste du skapa:

1. Om den inte redan finns måste du skapa:

   ```
   + apps 
     + settings
       + dam 
         + cfm (cq:Page) 
           + models (nt:folder)
             + formbuilderconfig (sling:folder)
               + datatypes (nt:unstructured)
                 + items (nt:unstructured)
   ```

   >[!NOTE]
   >
   >`/apps/settings/dam` ska redan finnas.
   >
   >`/cfm/models/formbuilderconfig/datatypes/items` kan behöva skapas med de angivna nodtyperna.

1. Under `/items` kan du lägga till nya noder som representerar dina nya datatyper:

   * Nodtyp: `nt:unstructured`
   * &quot;Egenskaper: se [Definiera egenskaper för din datatyp](#defining-the-properties-for-your-data-type)

### Definiera egenskaperna för din datatyp {#defining-the-properties-for-your-data-type}

1. Fastställ värden för följande [datatypsegenskaper](#data-type-properties) som krävs för din datatyp:

   * `fieldResourceType`
   * `fieldPropResourceType`
   * `fieldViewResourceType`

   Dessa definierar hur komponenterna för din datatyp ska återges. De kan vara vilken komponent som helst. inklusive dina egna anpassade komponenter (behöver en matchande uppsättning ` [fieldProperties](#fieldproperties)`).

   Definiera dessa egenskaper med rätt värden på noden för din datatyp.

1. Fastställ ` [fieldProperties](#fieldproperties)` som ska användas. Detta beror på de attribut eller egenskaper som `fieldResourceType` behöver.

   En `granite/ui/components/coral/foundation/form/textfield`måste till exempel ha ett **etikettnamn**, en **maximal längd**, en **platshållartext** och en **standardvärde**-egenskap.

   Du kan välja bland de färdiga [fieldProperties](#fieldproperties) eller [skapa egna egenskaper](#creating-your-own-fieldproperties-property).

   Definiera dessa egenskaper med rätt värden på noden för din datatyp.

1. Fastställ värden för följande [datatypsegenskaper](#data-type-properties):

   * `fieldIcon`
   * `fieldTitle`
   * `renderType`
   * `valueType`
   * `listOrder`

   Definiera dessa egenskaper med rätt värden på noden för din datatyp.

### Använda din datatyp {#using-your-data-type}

När du har sparat den här nodstrukturen, med alla egenskaper tillämpade, kan du öppna en modell med modellredigeraren och se och använda den nya datatypen.

## Skapar en egen fieldProperties-egenskap {#creating-your-own-fieldproperties-property}

Du kan välja bland de färdiga [fieldProperties](#fieldproperties) eller skapa en egen:

1. Skapa en komponent under:

   `/apps/dam/cfm/models/editor/components/datatypeproperties/`

   Om sökvägen inte finns kan du skapa den med `nt:folder`-noder.

   1. För att få åtkomst till variablerna bör den här komponenten utöka:

      `/libs/dam/cfm/models/editor/components/datatypeproperties/base`* *

   1. Komponenten ska kunna inkluderas genom:

      `sling:include`

   1. Den här komponenten bör antingen återge ett fält (om en användare behöver lägga till data) eller en dold inmatning med de egenskaper som behövs för din datatyp. En multifältskomponent kräver till exempel en underordnad nod med den typ av fält som den ska duplicera, och därför bör det finnas en inmatning som kan skapa (med hjälp av sling POST-mekanik) en underordnad nod av en viss typ.

1. Komponentens basnamn bör läggas till i `fieldProperties`.
1. Upprepa för alla egenskaper du behöver.

