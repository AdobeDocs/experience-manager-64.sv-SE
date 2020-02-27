---
title: Komponenter för innehållsfragment
seo-title: Komponenter för innehållsfragment
description: AEM-innehållsfragment skapas och hanteras som sidoberoende resurser
seo-description: AEM-innehållsfragment skapas och hanteras som sidoberoende resurser
uuid: 289ed9cb-9531-43a9-b0d8-a3499e2e9ee5
contentOwner: Alison Heimoz
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: components
content-type: reference
discoiquuid: 76b63c7c-f7ea-46be-8d10-6c1a30af2e2b
pagetitle: Components for Content Fragments
translation-type: tm+mt
source-git-commit: ce717994831eb3ef90baaffa7413de50f671b07c

---


# Komponenter för innehållsfragment{#components-for-content-fragments}

>[!CAUTION]
>
>Vissa funktioner för innehållsfragment kräver att [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md)används.

## Komponenter för fragmentredigering {#components-for-fragment-authoring}

>[!CAUTION]
>
>Vi rekommenderar inte att du utökar eller ändrar de faktiska komponenterna som används i Fragment Editor eftersom de fortfarande kan ändras.

Se API:t för hantering av [innehållsfragment - klientsidan](/help/sites-developing/customizing-content-fragments.md#the-content-fragment-management-api-client-side).

## Komponenter för sidredigering {#components-for-page-authoring}

>[!CAUTION]
>
>Core-komponenten för [innehållsfragment](https://helpx.adobe.com/experience-manager/core-components/using/content-fragment-component.html) rekommenderas nu. Mer information finns i [Utveckla kärnkomponenter](https://helpx.adobe.com/experience-manager/core-components/using/developing.html) .
>
>I det här avsnittet beskrivs den ursprungliga komponenten som levererats för användning med innehållsfragment (**Content Fragment** i gruppen **General** ).

Adobe Experience Manager-innehållsfragment (AEM) [skapas och hanteras som sidoberoende resurser](/help/assets/content-fragments.md). Med dem kan du skapa kanalneutralt innehåll tillsammans med (eventuellt kanalspecifika) variationer. [Du kan sedan använda dessa fragment och deras variationer när du redigerar innehållssidorna](/help/sites-authoring/content-fragments.md). Du kan också använda en befintlig resurs för innehållsfragment genom [att dra den från resursläsaren till sidan](/help/sites-authoring/content-fragments.md#adding-a-content-fragment-to-your-page) (som för andra resursbaserade komponenter, som exempelvis image-konfigurationen för grundkomponenten). Komponenten för innehållsfragment som inte är klar att användas visar bara ett [element](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) i det refererade innehållsfragmentet. Med komponentdialogrutan kan du definiera [element, variationer och intervall för fragmentstycken](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) som du vill visa på sidan.

>[!NOTE]
>
>Den här innehållskomponenten infördes i AEM 6.2 som en förbättrad version av artikelkomponenten, som har tagits bort.

>[!NOTE]
>
>Innehållsfragment stöds inte i det klassiska användargränssnittet.

### Definition {#definition}

Komponenten **Innehållsfragment** används för att hålla en referens till en resurs för innehållsfragment (förbättrade textresurser). Resurstypen för innehållsfragmentet är:

* `dam/cfm/components/contentfragment/contentfragment`

Referensen definieras i egenskapen:

* `fileReference`

Det är bara redigeraren av det beröringskänsliga användargränssnittet som helt stöder komponenter för innehållsfragment, som inkluderar klientbiblioteket:

* `cq.authoring.editor.plugin.cfm`

Det här biblioteket lägger till funktioner som är specifika för innehållsfragment i redigeraren. Det finns till exempel stöd för att lägga till och konfigurera innehållsfragment på sidan, möjlighet att söka efter innehållsfragmentresurser i resursläsaren och efter associerat innehåll på sidopanelen.

### Mellan innehåll {#in-between-content}

Med komponenten **Content** Fragment kan du släppa ytterligare komponenter mellan de olika styckena i det visade [elementet](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment). Elementet som visas består i själva verket av olika stycken (varje stycke markeras med en radmatning). Du kan infoga innehåll med andra komponenter mellan styckena.

Ur teknisk synvinkel finns varje stycke i det visade elementet i en egen parsys, och varje komponent som du lägger till mellan styckena infogas (under huven) i parsytan.

Det innebär att om instansen av innehållsavsnittskomponenten består av tre stycken, kommer komponenten att ha tre olika parsyser i databasen. Allt mellanliggande innehåll som läggs till i innehållsfragmentet finns i dessa parsyser.

I databasen lagras det mellanliggande innehållet i förhållande till dess placering inuti den övergripande styckestrukturen, dvs. det är inte kopplat till det faktiska styckeinnehållet.

För att illustrera detta anser vi att vi har:

* En instans av ett innehållsfragment bestående av tre stycken
* Och att en del innehåll redan har infogats efter det andra stycket

   * Det innebär att innehållet lagras i den andra parsysen.

Om styckestrukturen i den här instansen ändras (genom att ändra variationen, elementet eller styckeintervallet som visas) kan det påverka det mellanliggande innehållet som visas när innehållet i innehållsfragmentet:

* Redigeras och ett annat stycke läggs till före det andra stycket:

   * Det mellanliggande innehållet visas efter det nya stycket (det nya stycket finns nu i det andra stycket).

* Redigeras och det andra stycket tas bort:

   * Det mellanliggande innehållet visas efter det stycke som tidigare var det tredje (det andra stycket gäller nu det föregående tredje stycket).

* Har konfigurerats så att endast det första stycket visas:

   * Det mellanliggande innehållet visas inte (den andra parsysen återges inte längre på grund av den nya konfigurationen).

### Anpassa komponenten Innehållsfragment {#customizing-the-content-fragment-component}

Om du vill använda fragmentkomponenten som finns i kartongen som en plan för tillägg måste du följa följande kontrakt:

* Återanvänd HTML-återgivningsskriptet och tillhörande POJO för att se hur funktionen för mellanliggande innehåll implementeras.
* Återanvänd noden för innehållsfragment: `cq:editConfig`

   * Avlyssnarna `afterinsert`/ `afteredit`/ `afterdelete` används för att utlösa JS-händelser. Dessa händelser hanteras i `cq.authoring.editor.plugin.cfm` klientbiblioteket för att visa det associerade innehållet på sidopanelen.
   * De `cq:dropTargets` är konfigurerade att ha stöd för att dra innehållsfragmentresurser.
   * `cq:inplaceEditing` är konfigurerat för att stödja redigering av ett innehållsfragment i sidredigeraren. Fragmentets redigerare på plats definieras i `cq.authoring.editor.plugin.cfm` klientbiblioteket och tillåter en snabblänk att öppna det aktuella [elementet/varianten](/help/assets/content-fragments.md#constituent-parts-of-a-content-fragment) i [fragmentredigeraren](/help/assets/content-fragments-variations.md).

### Återgivning av resurser före återgivning {#asset-rewriting-before-rendering}

I Content Fragment Management används en intern återgivningsprocess för att generera det slutliga HTML-resultatet för en sida. Detta används internt av komponenten Content Fragment, men också av bakgrundsprocessen som uppdaterar refererade fragment på refererande sidor.

Internt används Sling Rewriter för den återgivningen. Motsvarande konfiguration finns på `/libs/dam/config/rewriter/cfm` och kan justeras vid behov. Mer information finns i [Apache Sling Rewriter](https://sling.apache.org/documentation/bundles/output-rewriting-pipelines-org-apache-sling-rewriter.html) .

I konfigurationen som är klar att användas används följande transformatorer:

* `transformer-cfm-payloadfilter` - endast för att hämta `body` delen ( `<body>...</body>`) av fragmentets HTML

* `transformer-cfm-parfilter` - filtrerar bort oönskade stycken om ett styckeintervall anges (som kan göras med komponenten Innehållsfragment)
* `transformer-cfm-assetprocessor` - används internt för att hämta en lista över resurser som är inbäddade i fragmentet

Återgivningsprocessen visas genom ` [com.adobe.cq.dam.cfm.content.FragmentRenderService](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/dam/cfm/ContentFragment.html)` och kan utnyttjas (till exempel) av anpassade komponenter om det behövs.