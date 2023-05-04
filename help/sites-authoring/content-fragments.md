---
title: Sidredigering med innehållsfragment
seo-title: Page Authoring with Content Fragments
description: Med AEM Content Fragments kan du utforma, skapa, strukturera och använda sidoberoende innehåll
seo-description: AEM Content Fragments allow you to design, create, curate, and use page-independent content
uuid: 66ccdff8-1658-4374-8562-97f81f434488
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 076a3064-80c3-454b-93f9-6ae925c54328
exl-id: bbe4ae86-e9b8-4c3f-ada3-82470e371c4e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1138'
ht-degree: 5%

---

# Sidredigering med innehållsfragment{#page-authoring-with-content-fragments}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!CAUTION]
>
>Vissa funktioner för innehållsfragment kräver att [AEM 6.4 Service Pack 2 (6.4.2.0) eller senare](/help/release-notes/sp-release-notes.md).

Innehållsfragment i Adobe Experience Manager (AEM) [skapas och hanteras som sidoberoende resurser](/help/assets/content-fragments.md).

Med dem kan du skapa kanalneutralt innehåll tillsammans med (eventuellt kanalspecifika) variationer. Du kan sedan använda dessa fragment och deras variationer när du redigerar innehållssidorna.

Tillsammans med den uppdaterade JSON-exporteraren kan strukturerade innehållsfragment även användas för att leverera AEM innehåll via Content Services till andra kanaler än AEM.

>[!NOTE]
>
>**Innehållsfragment** och **[Upplevelsefragment](/help/sites-authoring/experience-fragments.md)** har olika funktioner i AEM:
>
>* **Innehållsfragment** är redaktionellt innehåll, främst text och relaterade bilder. De är rent innehåll, utan design och layout.
>* **Upplevelsefragment** är helt utformat, ett fragment av en webbsida.
>
>Upplevelsefragment kan innehålla innehåll i form av innehållsfragment, men inte tvärtom.

>[!CAUTION]
>
>Den här sidan måste läsas tillsammans med [Arbeta med innehållsfragment](/help/assets/content-fragments.md) (och relaterade sidor) när det introducerar grundläggande terminologi och koncept, tillsammans med att skapa och hantera fragment.

Innehållsfragmenten aktiverar:

* **Marknadsförings- och kampanjstrategi**

   * Granska innehåll via centralt hanterade innehållsfragment.

* **Creative Pro**

   * Spåra kreativa resurser via samlingar som är kopplade till innehållsfragment.

* **Kopiera författare**

   * Skriv i AEM innehållsfragmentredigerare.
   * Kan skapa innehållsvariationer.
   * Kan associera relevant innehåll med innehållsfragmentet.
   * Kan använda versionshantering/arbetsflöde.
   * Kan dela innehållsfragment.
   * Kan hantera översättningar centralt.

* **Producenter och reseansvariga**

   * Välj bland fördefinierade fragment och variationer med redigering i AEM.
   * Kan förlita sig på att fragment och tillhörande innehåll alltid är uppdaterade när kopieringsförfattare och kreatörer uppdaterar centralt hanterade fragment och resurser.
   * Kan lita på att tillhörande medieinnehåll kurateras för relevans.
   * Kan skapa tillfälliga innehållsvariationer direkt samtidigt som dessa variationer förblir centralt hanterade i fragmentet.

## Lägga till ett innehållsfragment på sidan {#adding-a-content-fragment-to-your-page}

1. Öppna sidan för redigering.

1. Lägg till **[!UICONTROL Content Fragment]** komponent, från **[!UICONTROL Components]** webbläsare eller **[!UICONTROL Insert New Component]**.

1. Du kan antingen:

   * Öppna **[!UICONTROL Assets]** webbläsare och filter för **[!UICONTROL Content Fragments]** (standard är Bilder). Dra sedan det önskade fragmentet till komponentinstansen.
   * Markera innehållets fragmentkomponent och sedan **[!UICONTROL Configure]** i verktygsfältet. I dialogrutan kan du öppna urvalsdialogrutan för att bläddra och välja önskat alternativ **[!UICONTROL Content Fragment]**.

   >[!NOTE]
   >
   >Ett annat sätt är att dra ett visst innehållsfragment direkt till sidan. Då skapas automatiskt den associerade komponenten (innehållsfragment).

1. Inledningsvis innehållet från **[!UICONTROL Main]** Element och **[!UICONTROL Master]** (variation) visas. Du kan [markera andra element och/eller variationer](#selecting-the-element-or-variation) efter behov.

   ![cfm-6420-01](assets/cfm-6420-01.png)

   >[!NOTE]
   >
   >Mer information om ytterligare redigeringsfunktioner finns även i:
   >
   >* [Responsiv layout](/help/sites-authoring/responsive-layout.md)
   >* [Redigera sidinnehåll](/help/sites-authoring/editing-content.md)


## Markera elementet eller variationen {#selecting-the-element-or-variation}

Öppna fragmentets **[!UICONTROL Configuration]** för att konfigurera fragmentet för användning på den aktuella sidan. Dialogrutan kan vara beroende av vilken komponent som används.

I rätt konfigurationsdialogruta kan du välja tillgängliga parametrar, bland annat:

* **[!UICONTROL Content Fragment]**

   Ange det fragment som ska användas.

* **[!UICONTROL Display Mode]**:

   * **[!UICONTROL Single Text Element]**
   * **[!UICONTROL Multiple Element]**

* **[!UICONTROL Element]**

   * Standardvärdet **[!UICONTROL Main]** kommer alltid att vara tillgängligt.
   * En markering blir tillgänglig om fragmentet skapades med en lämplig mall.

   >[!NOTE]
   >
   >Vilka element som är tillgängliga beror på vilken mall som används.

* **[!UICONTROL Variation]**

   * Standardvärdet **[!UICONTROL Master]** kommer alltid att vara tillgängligt.
   * En markering blir tillgänglig om variationer har skapats för fragmentet.

* **[!UICONTROL Paragraphs]**: ange det eller de stycken som ska ingå:

   * **[!UICONTROL All]**
   * **[!UICONTROL Range]**: till exempel `1`, `3-5`, `9-*`

      * **[!UICONTROL Handle headings as their own paragraphs]**

* **[!UICONTROL Handle headings as their own paragraphs]**

## Snabb anslutning till Fragment Editor {#quick-connection-to-fragment-editor}

Du kan öppna fragmentkällan för redigering (resursen) med **[!UICONTROL Edit]** -ikonen i komponentens verktygsfält. Då kan du [redigera och hantera innehållsfragmentet](/help/assets/content-fragments.md).

>[!CAUTION]
>
>Som alltid kommer redigering av fragmentkällan att påverka alla sidor som refererar till det innehållsfragmentet.

## Lägga till mellaninnehåll {#adding-in-between-content}

När ett visst innehållsfragment läggs till på sidan finns det ett **[!UICONTROL Drag components here]** platshållare mellan styckena HTML (och längst upp/längst ned) i fragmentet.

Detta gör att du kan lägga till extra innehåll [in-between (dvs. in-between content)](/help/assets/content-fragments.md#in-between-content-when-page-authoring-with-content-fragments) fragmentinnehållet (vid någon av de tillgängliga punkterna), utan att behöva ändra rotfragmentet.

För mellanliggande innehåll kan du:

* Lägg till komponenter från [Komponentwebbläsare](/help/sites-authoring/author-environment-tools.md#components-browser).
* Lägg till resurser från [Resursläsaren](/help/sites-authoring/author-environment-tools.md#assets-browser).
* Använd [Associerat innehåll](#using-associated-content) som en källa för mellanliggande innehåll.

>[!CAUTION]
>
>Det mellanliggande innehållet är sidinnehåll. Den lagras inte i innehållsfragmentet.

![cfm-6420-02](assets/cfm-6420-02.png)

>[!NOTE]
>
>Du kan också [infoga visuella resurser (bilder) i själva fragmentet](/help/assets/content-fragments-variations.md#inserting-assets-into-your-fragment).
>
>Visuella resurser som infogats i själva fragmentet kopplas till föregående stycke i fragmentet. Det innebär att du inte kan placera innehåll mellan en visuell resurs och föregående stycke.

>[!CAUTION]
>
>När du har lagt till mellanliggande innehåll i ett innehållsfragment på sidan kan ändringar av strukturen för det underliggande innehållsfragmentet (dvs. i innehållsfragmentets redigerare) leda till felaktiga/oväntade resultat.
>
>När detta inträffar behålls det mellanliggande innehållet som det är:
>
>* Mellanliggande komponenter har en absolut position inom komponentsekvensen i fragmentflödet. Den här positionen ändras inte, även när innehållet i styckena i fragmentet ändras.\
   >  Detta kan få det att se ut som om den relativa placeringen har ändrats, eftersom mellanliggande stycken inte har någon kontextuell relation till (fragmentet) stycken som de är placerade bredvid.
>* Om inte de två styckestrukturerna står i konflikt med varandra. I så fall visas inte det mellanliggande innehållet (även om det fortfarande finns internt).
>


## Använda associerat innehåll {#using-associated-content}

Om du har [associerat innehåll](/help/assets/content-fragments-assoc-content.md) med [innehållsfragmentet](/help/assets/content-fragments.md) är dessa resurser tillgängliga från sidopanelen (när du har placerat fragmentet på innehållssidan). Associerat innehåll är i själva verket en särskild innehållskälla för [mellanliggande innehåll](#adding-in-between-content).

>[!NOTE]
>
>Det finns olika metoder att lägga till [visuella resurser (t.ex. bilder)](/help/assets/content-fragments.md#fragments-with-visual-assets) till fragmentet och/eller sidan.

>[!NOTE]
>
>Om du har flera innehållsfragment på en sida **[!UICONTROL Associated Content]** -fliken visar resurser som passar alla fragment.

När du har lagt till ett fragment med associerat innehåll på sidan visas en ny flik (**[!UICONTROL Associated Content]**) öppnas på sidopanelen.

Här kan du dra resurserna till önskad plats (antingen till en befintlig komponent eller till önskad plats där rätt komponent skapas):

![cfm-6420-03](assets/cfm-6420-03.png)

## Resurser som infogats i fragmentet {#assets-inserted-into-the-fragment}

If [resurser (t.ex. bilder) har infogats i själva avsnittet](/help/assets/content-fragments-variations.md#inserting-assets-into-your-fragment), är alternativen för att redigera dessa resurser i sidredigeraren begränsade.

För en bild kan du till exempel

* Beskär, rotera eller vänd bilden.
* Lägg till en titel eller alternativ text.
* Ange en storlek.
* Du kan också konfigurera layouten.

Andra ändringar, till exempel move, copy, delete, måste göras i fragmentredigeraren.

## Publicering {#publishing}

Fragment måste publiceras så att de kan användas på dina publicerade webbsidor:

* Ett fragment kan publiceras efter [skapa fragmentet i resurskonsolen](/help/assets/content-fragments-managing.md#publishing-and-referencing-a-fragment).
* Om en *opublicerat fragment* används på en sida som publiceras, kan fragmentet också publiceras just nu.
