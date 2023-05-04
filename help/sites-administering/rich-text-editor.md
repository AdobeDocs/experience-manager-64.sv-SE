---
title: Konfigurera RTF-redigeraren
description: Lär dig att konfigurera AEM RTF-redigerare.
contentOwner: AG
exl-id: 2d5e9ada-1567-43dc-ab19-6891e20e1d0b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2695'
ht-degree: 0%

---

# Konfigurera RTF-redigeraren {#configure-the-rich-text-editor}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med textredigeraren får författarna ett stort antal funktioner för redigering av textinnehåll. Ikoner, markeringsrutor, verktygsfält och menyer finns för WYSIWYG-textredigering.

Om du vill veta hur du använder RTE-funktioner för redigering kan du läsa [Använd RTF-redigerare för att skapa](/help/sites-authoring/rich-text-editor.md). RTE kan konfigureras för att aktivera, inaktivera och utöka de funktioner som är tillgängliga i redigeringskomponenterna. Följande arbetsflöde visar den rekommenderade ordningen för att slutföra RTE-konfigurationsuppgifterna i Experience Manager.

![Normalt arbetsflöde för att konfigurera RTF-redigeraren](assets/rte_workflow_v1.png)

*Bild: Normalt arbetsflöde för att konfigurera RTF-redigeraren*

## Förstå användargränssnittet med pekskärmsfunktioner och det klassiska användargränssnittet {#understand-touch-enabled-ui-and-classic-ui}

Det användargränssnitt som har stöd för pekskärm är standardgränssnittet för AEM. Adobe introducerade Touch UI med [responsiv design](/help/sites-authoring/responsive-layout.md) för redigeringsmiljön, i version 5.6. Touchgränssnittet är utformat för enheter med pekskärm och stationära datorer. Gränssnittet skiljer sig avsevärt från det ursprungliga klassiska användargränssnittet.

![Verktygsfältet för textredigeraren i det Touch-aktiverade gränssnittet](assets/chlimage_1-404.png)

*Bild: Verktygsfältet för textredigeraren i det Touch-aktiverade gränssnittet*

![Verktygsfältet RTF-redigerare i det klassiska användargränssnittet](assets/rtedefault.png)

*Bild: Verktygsfältet RTF-redigerare i det klassiska användargränssnittet*

>[!MORELIKETHIS]
>
>* [Gränssnittsrekommendationer](/help/sites-deploying/ui-recommendations.md)
>* Information om hur du ersätter det klassiska användargränssnittet finns i [AEM 6.4 Versionsinformation](/help/release-notes/deprecated-removed-features.md)
>* Skillnaden mellan användargränssnitten finns i [Touch-gränssnittet och det klassiska gränssnittet](https://aemcq5pedia.wordpress.com/2018/01/05/touch-enabled-ui-aem6-3/)
>* Mer information om användargränssnittet med pekfunktioner finns i [AEM Touch UI](/help/sites-developing/touch-ui-concepts.md)


## Olika redigeringslägen {#editingmodes}

Författare kan skapa och redigera textinnehåll i AEM med de olika komponentlägena. Alternativen i verktygsfältet för att skapa och formatera innehåll och användarupplevelsen i komponenter med RTE-funktioner i olika redigeringslägen varierar beroende på RTE-konfigurationer.

| Redigeringsläge | Redigeringsområde | Rekommenderade funktioner som ska aktiveras | Pekgränssnitt | Klassiskt användargränssnitt |
|--- |--- |--- |--- |--- |
| Textbunden | On-place editing for quick, minor edits; Formatera utan att öppna en dialogruta | Minimala RTE-funktioner | Y | Y |
| RTE helskärm | Täcker hela sidan | Alla RTE-funktioner som krävs | Y | N |
| Dialog | Dialogrutan visas ovanpå sidinnehållet men täcker inte hela sidan | Alla nödvändiga RTE-funktioner i Classic UI. aktivera funktioner i Touch-gränssnittet | Y | Y |
| Dialogruta i helskärmsläge | Samma som helskärmsläge. innehåller fält i dialogrutan vid sidan om textredigeringsprojektet | Alla RTE-funktioner som krävs | Y | N |

>[!NOTE]
>
>Funktionen för källredigering är inte tillgänglig i inline-redigeringsläge i det användargränssnitt som har stöd för pekfunktioner. Du kan inte dra bilder i helskärmsläge. Alla andra funktioner fungerar i alla lägen.

### Inline-redigering {#inline-editing}

När innehållet öppnas (med en långsam dubbeltryckning/klick) kan det redigeras på sidan. Ett kompakt verktygsfält med grundläggande alternativ visas.

![Inline-redigering med grundläggande verktygsfält i Touch-aktiverat användargränssnitt](assets/chlimage_1-405.png)

*Bild: Inline-redigering med grundläggande verktygsfält i Touch-aktiverat användargränssnitt*

I det klassiska användargränssnittet kan du med en långsam dubbelklickning på komponenten redigera textbundet och med en orange kontur markeras innehållet. Om Innehållssökning är öppet visas ett verktygsfält med tillgängliga alternativ för RTF-formatering högst upp i fönstret. Om Innehållssökning inte är öppet visas inte formateringsalternativen och du kan bara göra grundläggande textredigeringar.

### Helskärmsredigering {#full-screen-editing}

AEM kan öppnas i helskärmsläge som döljer sidinnehållet och tar upp den tillgängliga skärmen. Överväg att redigera i helskärmsläge som en detaljerad version av den infogade redigeringen eftersom den erbjuder de flesta redigeringsalternativen. Du kan öppna den genom att klicka ![rte_fullscreen](assets/rte_fullscreen.png)från det kompakta verktygsfältet när du använder det infogade redigeringsläget.

I helskärmsläget i dialogrutan finns ett detaljerat verktygsfält för textredigering, samt alternativ och komponenter som är tillgängliga i dialogruteläget. Det gäller endast för en dialogruta som innehåller RTE tillsammans med andra komponenter.

![Det detaljerade verktygsfältet för textredigering när du redigerar i helskärmsläge i det touchaktiverade gränssnittet](assets/chlimage_1-406.png)

*Bild: Det detaljerade verktygsfältet för textredigering när du redigerar i helskärmsläge i det touchaktiverade gränssnittet*

### Dialogruteredigering {#dialog-editing}

När du dubbelklickar på en komponent i det klassiska användargränssnittet öppnas en dialogruta där du kan redigera innehållet. Dialogrutan öppnas ovanpå den befintliga sidan. I vissa specifika scenarier öppnas dialogrutan som ett popup-fönster. Om en textkomponent till exempel är en del av en kolumn i en sidlayout med flera kolumner och området som är tillgängligt för dialogrutan är mindre.

![Dialogruteredigeringsläge i användargränssnittet med pekfunktioner](assets/dialog_editing_modetouchui.png)

*Bild: Dialogruteredigeringsläge i användargränssnittet med pekfunktioner*

![Dialogruta i Classic UI som innehåller ett detaljerat verktygsfält för redigering](assets/chlimage_1-407.png)

*Bild: Dialogruta i Classic UI som innehåller ett detaljerat verktygsfält för redigering*

## Om RTE-plugin-program och associerade funktioner {#aboutplugins}

Funktionerna är tillgängliga via ett antal plugin-program, var och en med:

* A `features` egenskap:

   * Det används för att aktivera, eller inaktivera, grundläggande funktioner för det plugin-programmet.
   * Det kan konfigureras med en standardiserad procedur.

* Fler egenskaper och alternativ som kräver specialkonfigurering.

Grundfunktionerna i textredigeringsprojektet aktiveras, eller inaktiveras, av värdet på `features` på en nod som är specifik för rätt plugin-program.

I följande tabell visas de aktuella plugin-programmen:

* Plugin-ID:n med en länk till API-dokumentationen. ID används som nodnamn när [aktivera ett plugin-program](/help/sites-administering/configure-rich-text-editor-plug-ins.md#activateplugin).
* Tillåtna värden för `features` -egenskap.
* En beskrivning av de funktioner som tillhandahålls av plugin-programmet.

| Plug-in-ID | funktioner | Beskrivning |
|--- |--- |--- |
| redigera | cut copy paste-default paste-plaintext paste-wordhtml | [Klipp ut, kopiera och, de tre inklistringslägena](/help/sites-administering/configure-rich-text-editor-plug-ins.md#text-styles). |
| [findreplace](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.FindReplacePlugin) | sök och ersätt | Sök och ersätt. |
| [format](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.FormatPlugin) | fet kursiv understrykning | [Grundläggande textformatering](/help/sites-administering/configure-rich-text-editor-plug-ins.md#text-styles). |
| [bild](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.ImagePlugin) | bild | Grundläggande bildstöd (dra från innehåll eller Innehållssökning). Beroende på webbläsaren har stödet olika beteenden för författare |
| [tangenter](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.KeyPlugin) |  | Information om hur du definierar det här värdet finns i [tabbstorlek](/help/sites-administering/configure-rich-text-editor-plug-ins.md#tab-size). |
| [justera](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.JustifyPlugin) | justera vänsterjustera centrera högerjustera | Styckejustering. |
| [länkar](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.LinkPlugin) | ändra länkavlänkningsankarpunkt | [Hyperlänkar och ankarpunkter](/help/sites-administering/configure-rich-text-editor-plug-ins.md#link-styles). |
| [listor](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.ListPlugin) | sorterat indrag utan ordning | Detta plugin-program kontrollerar båda [indrag och listor](/help/sites-administering/configure-rich-text-editor-plug-ins.md#indent-margin); inklusive kapslade listor. |
| [felverktyg](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.MiscToolsPlugin) | specialteckenkälla redigera | Med andra verktyg kan författare ange [specialtecken](/help/sites-administering/configure-rich-text-editor-plug-ins.md#special-char) eller redigera HTML-källan. Du kan också lägga till en hel [intervall med specialtecken](/help/sites-administering/configure-rich-text-editor-plug-ins.md#define-range-char) om du vill definiera en egen lista. |
| Paraformat | paraformat | Standardstyckeformaten är Stycke, Rubrik 1, Rubrik 2 och Rubrik 3 (`<p>`, `<h1>`, `<h2>`och `<h3>`). Du kan [lägga till fler styckeformat](/help/sites-administering/configure-rich-text-editor-plug-ins.md#para-formats) eller utöka listan. |
| stavningskontroll | checkText | [Språkmedveten stavningskontroll](/help/sites-administering/configure-rich-text-editor-plug-ins.md#add-dict). |
| stilar | stilar | Stöd för formatering med en CSS-klass. [Lägga till nya textformat](/help/sites-administering/configure-rich-text-editor-plug-ins.md#text-styles) om du vill lägga till (eller utöka) egna format för användning med text. |
| nedsänkt | nedsänkt upphöjd text | Tillägg till de grundläggande formaten, med både sub- och super-script. |
| table | tabell borttagbar infogning ta bort infogkolumn borttagbar kolumn cellprops mergeceller splitcell markervalkolumner | Se [konfigurera tabellformat](/help/sites-administering/configure-rich-text-editor-plug-ins.md#table-styles)om du vill lägga till egna format för hela tabeller eller enskilda celler. |
| ångra | ångra gör om | Historikstorlek för [ångra och göra om](/help/sites-administering/configure-rich-text-editor-plug-ins.md#undo-history) åtgärder. |

>[!NOTE]
>
>Plugin-programmet för helskärm stöds inte i dialogruteläge. Användning av `dialogFullScreen` inställning för att konfigurera verktygsfältet för helskärmsläge.

## Förstå konfigurationssökvägar och -platser {#understand-the-configuration-paths-and-locations}

The [RTE-redigeringsläge (och användargränssnittet)](#editingmodes) som du anger för författarna bestämmer var konfigurationsinformationen ska placeras när du är [aktivera RTE-plugin-program](/help/sites-administering/configure-rich-text-editor-plug-ins.md#activateplugin):

| Redigeringsläge | Plats för Touch UI | Plats för Classic UI |
|---|---|---|
| Textbunden | `cq:editConfig/cq:inplaceEditing` | `cq:editConfig/cq:inplaceEditing` |
| Helskärm | `cq:editConfig/cq:inplaceEditing` | Ej tillämpligt |
| Dialog | `cq:dialog` | `dialog` |
| Dialogrutan Helskärm | `cq:dialog` | Ej tillämpligt |

>[!NOTE]
>
>Namnge inte noden under `cq:inplaceEditing` as `config`. På `cq:inplaceEditing` -nod definierar du följande egenskaper:
>
>* **Namn**: `configPath`
>* **Typ**: `String`
>* **Värde**: sökväg till noden som innehåller den faktiska konfigurationen
>
>Namnge inte RTE-konfigurationsnoden som `config`. I annat fall gäller RTE-konfigurationerna bara för administratörerna och inte för användarna i gruppen `content-author`.

Konfigurera följande egenskaper som gäller i redigeringsläget för dialogrutor endast i Touch-gränssnittet:

* `useFixedInlineToolbar`: Ange den här booleska egenskapen som är definierad på RTE-noden (en med sling:resourceType= `cq/gui/components/authoring/dialog/richtext`) till `True`, om du vill att verktygsfältet RTE ska vara fast i stället för flytande.

   När den här egenskapen är true startas Richtext-redigering som standard på händelsen &quot;foundation-contentloaded&quot;.

   Du kan förhindra detta genom att ange egenskapen `customStart` till `True`och utlöser händelsen&quot;start-start&quot; för att starta redigering av textredigering. När den här egenskapen är true fungerar inte standardbeteendet, som börjar med klickning.

* `customStart`: Ställ in den här booleska egenskapen som definierats på RTE-noden på `True`för att styra när RTE ska startas genom att händelsen utlöses `rte-start`.

* `rte-start`: Utlös den här händelsen på `contenteditable-div` av RTE, när redigering av RTE ska börja. Detta fungerar bara om `customStart` har angetts till true.

När textredigeraren används i den beröringsaktiverade dialogrutan anger du egenskapen `useFixedInlineToolbar` true är obligatoriskt för att undvika problem.

## Anpassa redigering på plats {#customizing-in-place-editing}

Du kan definiera på vilken HTML-väljare textredigeraren ska starta genom att konfigurera följande egenskaper:

* **`editElementQuery`** - Definierad den `cq:InplaceEditingConfig`används den här egenskapen för att ange en väljare för det HTML-element som textbundna redigeringar för textkomponenten ska startas på. Om inget anges startas den infogade redigeringen direkt på HTML i textkomponenten.
* **`textPropertyName`** - Definierad den `cq:InplaceEditingConfig`används den här egenskapen för att ange namnet på egenskapen som ska sparas på noden content där textkomponentens HTML-värde ska bevaras efter infogad redigering.

Motsvarande egenskap för dialogläge är `name`.

## Aktivera RTE-funktioner genom att aktivera plugin-program {#enable-rte-functionalities-by-activating-plug-ins}

RTE-funktioner är tillgängliga via en serie plugin-program, var och en med features-egenskaper. Du kan konfigurera egenskapen features för att aktivera eller inaktivera de olika funktionerna i varje plugin-program.

Detaljerade konfigurationer av RTE-plugin-program finns i [hur du aktiverar och konfigurerar RTE-plugin-program](/help/sites-administering/configure-rich-text-editor-plug-ins.md).

Hämta den här exempelkonfigurationen för att förstå hur du konfigurerar RTE. I det här paketet är alla funktioner aktiverade.

[Hämta fil](/help/assets/assets/rte-sample-all-features-enabled-10.zip)

>[!NOTE]
>
>The [Textkomponent för kärnkomponenter](https://helpx.adobe.com/experience-manager/core-components/using/text.html) I kan mallredigerare konfigurera många RTE-plugin-program i användargränssnittet som innehållsprinciper, vilket eliminerar behovet av teknisk konfiguration. Innehållsprinciper kan fungera med RTE-användargränssnittskonfigurationer enligt beskrivningen. Mer information finns i [Inställningar för RTE-användargränssnitt och innehållsprinciper](/help/sites-administering/rich-text-editor.md#rtecontentpolicies), [Skapa sidmallar](/help/sites-authoring/templates.md)och [Dokumentation för grundkomponentutvecklare](https://helpx.adobe.com/experience-manager/core-components/using/developing.html).

>[!NOTE]
>
>I referenssyfte finns textstandardkomponenterna (levereras som en del av en standardinstallation) på:
>
>* `/libs/wcm/foundation/components/text`
>* `/libs/foundation/components/text`
>
>Om du vill skapa en egen textkomponent kopierar du ovanstående komponent i stället för att redigera de här komponenterna.

## Verktygsfältet Konfigurera RTE {#dialogfullscreen}

I AEM kan du konfigurera gränssnittet för RichText Editor på olika sätt för de olika redigeringslägena. Standardinställningarna anges nedan. Du kan åsidosätta dessa standardinställningar baserat på dina behov.

För bästa redigeringsmiljö:

* I en flytande dialogruta aktiverar du bara de plugin-program som inte har något popup-fönster eftersom den flytande dialogrutan är mindre.
* Aktivera alla plugin-program som behövs, även plugin-program med större popup-fönster, till exempel `Paste` plugin-program. Använd `dialogFullScreen` som beskrivs nedan.

```java
<uiSettings jcr:primaryType="nt:unstructured">
  <cui jcr:primaryType="nt:unstructured">
    <inline
      jcr:primaryType="nt:unstructured"
      toolbar="[format#bold,format#italic,format#underline,#justify,#lists,links#modifylink,links#unlink,#paraformat]">
      <popovers jcr:primaryType="nt:unstructured">
        <justify
          jcr:primaryType="nt:unstructured"
          items="[justify#justifyleft,justify#justifycenter,justify#justifyright]"
          ref="justify"/>
        <lists
          jcr:primaryType="nt:unstructured"
          items="[lists#unordered,lists#ordered,lists#outdent,lists#indent]"
          ref="lists"/>
        <paraformat
          jcr:primaryType="nt:unstructured"
          items="paraformat:getFormats:paraformat-pulldown"
          ref="paraformat"/>
      </popovers>
    </inline>
    <dialogFullScreen
      jcr:primaryType="nt:unstructured"
      toolbar="[format#bold,format#italic,format#underline,justify#justifyleft,justify#justifycenter,justify#justifyright,lists#unordered,lists#ordered,lists#outdent,lists#indent,links#modifylink,links#unlink,table#createoredit,#paraformat,image#imageProps]">
      <popovers jcr:primaryType="nt:unstructured">
        <paraformat
          jcr:primaryType="nt:unstructured"
          items="paraformat:getFormats:paraformat-pulldown"
          ref="paraformat"/>
      </popovers>
    </dialogFullScreen>
    <tableEditOptions
      jcr:primaryType="nt:unstructured"
      toolbar="[table#insertcolumn-before,table#insertcolumn-after,table#removecolumn,-,table#insertrow-before,table#insertrow-after,table#removerow,-,table#mergecells-right,table#mergecells-down,table#mergecells,table#splitcell-horizontal,table#splitcell-vertical,-,table#selectrow,table#selectcolumn,-,table#ensureparagraph,-,table#modifytableandcell,table#removetable,-,undo#undo,undo#redo,-,table#exitTableEditing,-]">
    </tableEditOptions>
  </cui>
</uiSettings>
```

Olika gränssnittsinställningar används för textbundet läge och helskärmsläge. Verktygsfältsegenskapen används för att ange knapparna i verktygsfältet. Om till exempel själva knappen är en funktion (till exempel `Bold`), anges som `PluginName#FeatureName` (t.ex. `links#modifylink`). Om knappen är en pekare (som innehåller vissa funktioner i ett plugin-program) anges den som `#PluginName` (t.ex. `#format`). Avgränsare ( | ) mellan en grupp knappar kan anges med &#39;-&#39;.

Popup-noden under infogat läge eller helskärmsläge innehåller en lista över de poseringar som används. Varje underordnad nod under `popovers` noden namnges efter plugin-programmet (till exempel `format`). Den har en egenskap `items` som innehåller en lista med funktioner i plugin-programmet (till exempel `format#bold`).

## RTE-inställningar (User Interface Settings) och innehållsprinciper {#rtecontentpolicies}

Administratörer kan styra textredigeringsalternativen med hjälp av innehållsprinciper, till exempel i stället för att göra konfigurationen enligt beskrivningen ovan. Innehållsprofiler definierar designegenskaperna för en komponent när de används som en del av en [redigerbar mall](../sites-authoring/templates.md). Om en textkomponent som använder textredigeraren till exempel används med en redigerbar mall kan innehållsprincipen definiera att det feta alternativet är tillgängligt och att några styckeformateringsalternativ är tillgängliga. Innehållsprofilerna kan återanvändas och kan tillämpas på flera mallar.

AEM 6.4 Service Pack 3 och senare flödar de tillgängliga alternativen i RTE nedåt från användargränssnittskonfigurationerna till innehållsprinciperna.

* Konfigurationsinställningarna för användargränssnittet definierar vilka alternativ som är tillgängliga för innehållsprinciperna.
* Om användargränssnittskonfigurationen för RTE har tagits bort eller inte aktiverar ett objekt kan innehållsprincipen inte konfigurera det.
* En författare har bara tillgång till funktioner som är tillgängliga i användargränssnittskonfigurationerna och i innehållsprinciperna.

Du kan till exempel se [Dokumentation för komponenten Text Core](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/components/text.html#the-text-component-and-the-rich-text-editor).

## Anpassa mappningen mellan verktygsfältsikoner och kommandon {#iconstoolbar}

Du kan anpassa mappningen mellan koralikonerna som visas i verktygsfältet för textredigering och de tillgängliga kommandona. Du kan inte använda några andra ikoner förutom kornikoner.

1. Skapa en nod med namnet `icons` under `uiSettings/cui`.

1. Skapa noder för enskilda ikoner under den.
1. På varje enskild ikonnod anger du en korallikon och ett kommando som ska kopplas till ikonen.

Nedan finns ett exempelfragment som kopplar kommandot Fet till koralikonen med namnet `textItalic`.

```java
<text jcr:primaryType="nt:unstructured" sling:resourceType="cq/gui/components/authoring/dialog/richtext" name="./text" useFixedInlineToolbar="{Boolean}true"> 
    <rtePlugins jcr:primaryType="nt:unstructured"> 
        <format jcr:primaryType="nt:unstructured" features="bold,italic"/> 
    </rtePlugins> 
    <uiSettings jcr:primaryType="nt:unstructured"> 
        <cui jcr:primaryType="nt:unstructured"> 
            <inline jcr:primaryType="nt:unstructured" 
                toolbar="[format#bold,format#italic,format#underline,links#modifylink,links#unlink]"> 
            </inline> 
            <icons jcr:primaryType="nt:unstructured"> 
                <bold jcr:primaryType="nt:unstructured" 
                    command="format#bold" 
                    icon="textItalic"/> 
            </icons> 
        </cui> 
    </uiSettings> 
</text>
```

## Växla till CoralUI 2 Rich Text Editor {#switch-to-coralui-rich-text-editor}

På en sida kan du antingen inkludera CoralUI 2 RTE clientlib eller CoralUI 3 RTE clientlib. Som standard innehåller textredigeraren klienten CoralUI 3 RTE. Så här byter du till CoralUI 2 RTE:

>[!NOTE]
>
>Adobe rekommenderar inte att bytet är en bra metod. Växla till CoralUI 2 RTE som sista utväg. Anpassade plugin-program för CoralUI 2 RTE fungerar med CoralUI 3 RTE om plugin-programmen inte är beroende av interna RTE-komponenter, till exempel klasser. Om du använder anpassade plugin-program för CoralUI 3 RTE ska du använda `rte.coralui3` bibliotek.

1. Täck över noden `/libs/cq/gui/components/authoring/editors/clientlibs/core` under `/apps`och gör följande:

   * Ersätt `rte.coralui3` med `rte.coralui2` för egenskapen för beroenden.
   * Ersätt `cq.authoring.editor.core.inlineediting.rte.coralui3` med `cq.authoring.editor.core.inlineediting.rte.coralui2` för egenskapen embed.
   * Ersätt `cq.authoring.rte.coralui3` med `cq.authoring.rte.coralui2` för egenskapen embed.

1. Täck över noderna `/libs/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui3` och `/libs/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui2` under `/apps`.

   Ta bort kategori `cq.authoring.dialog` från `/apps/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui3` och lägg till `/apps/cq/gui/components/authoring/dialog/richtext/clientlibs/rte/coralui2`.

1. Ändra eventuellt annat beroende som ska tas med på sidan från `rte.coralui3` till `rte.coralui2`. Till exempel efter att noden har ersatts `/libs/mcm/campaign/components/touch-ui/clientlibs/rte` under `/apps`, ändra beroende av det från `rte.coralui3` till `rte.coralui2`.

1. Täck över noden `cq/ui/widgets` under `/apps`. Ersätt beroendet `cq.rte` på noden `/apps/cq/ui/widgets` med `cq.coralui2.rte`.

>[!NOTE]
>
>CoralUI 2 RTE använder handspelsmallar för plugin-dialogrutor. Därför var CoralUI 2 RTE-klienten beroende av handlisten clientlib. CoralUI 3 RTE använder inte handspelsmallar och har inget associerat beroende. Om dina anpassade plugin-program använder mallar för verktygsfält, ska du ta med clientlib för verktygsfält på webbsidan.

## Ytterligare information {#further-information}

Mer information om hur du konfigurerar RTE finns i [API för AEM](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html) referens.

Du kan särskilt se vilka plugin-program och relaterade alternativ som är tillgängliga:

* The [CQ.form.RichText](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.RichText) innehåller ett formulärfält för redigering av formaterad textinformation (RTF). Mer information om alla parametrar som finns tillgängliga för RTF-formuläret finns i Konfigurationsalternativ.
* Komponenten RichText har ett stort antal funktioner med hjälp av plugin-program som listas under [CQ.form.rate.plugins.Plugin](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/widgets-api/index.html?class=CQ.form.rte.plugins.Plugin). För varje plugin:

   * Se Funktioner för mer information om funktioner som kan aktiveras (eller inaktiveras).
   * Se Konfigurera alternativ för alla tillgängliga parametrar för detaljerad konfiguration av lämpligt plugin-program.

* Mer information om HTML Rules för länkar finns också.

Ovanstående alternativ kan användas för att utöka och anpassa din egen RTE. Om du till exempel vill lista de ankare som är tillgängliga på sidan när du skapar en länk kan du ange en egen implementering av `LinkPlugin`.

## Kända begränsningar {#known-limitations}

AEM har följande begränsningar:

* RTE-funktioner stöds bara i AEM komponentdialogrutor. RTE stöds inte i guider eller Foundation-formulär som [Sidegenskaper](/help/sites-developing/page-properties-views.md) och [Ställning](/help/sites-authoring/scaffolding.md) på användargränssnittet med pekskärm.

* AEM fungerar inte på [Hybridenheter](/help/release-notes/known-issues.md).

* Namnge inte RTE-konfigurationsnoden `config`. I annat fall gäller RTE-konfigurationen bara för administratörerna och inte för användarna i gruppen `content-author`.

* RTE stöder inte infogad bildruta eller iframe för att bädda in innehåll.

>[!MORELIKETHIS]
>
>* [Konfigurera RTE-plugin-program](configure-rich-text-editor-plug-ins.md)
>* [Använd RTF-redigerare för att skapa](../sites-authoring/rich-text-editor.md)
>* [Konfigurera RTE för hjälpmedelsanpassade webbplatser](rte-accessible-content.md)
>* [Funktionsparitet för Touch UI och Classic UI](../release-notes/touch-ui-features-status.md)
>* [Självstudiekurs för att skapa en sammansatt flerfältskomponent](https://experience-aem.blogspot.com/2019/05/aem-65-touchui-composite-multifield-with-coral3-rte-rich-text.html)

