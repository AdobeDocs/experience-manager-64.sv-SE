---
title: Ställning
seo-title: Scaffolding
description: Ibland kan du behöva skapa en stor uppsättning sidor som har samma struktur men olika innehåll. Med hjälp av ställningar kan du skapa ett formulär (en struktur) med fält som motsvarar den struktur du vill ha för sidorna och sedan använda det här formuläret för att enkelt skapa sidor som baseras på den strukturen.
seo-description: Sometimes you may need to create a large set of pages that share the same structure but have differing content. With scaffolding you can create a form (a scaffold) with fields that reflect the structure you want for your pages and then use this form to easily create pages based on this structure.
uuid: b1fdf2c0-e6d0-488a-96e5-dfbd6beb7610
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 884b3e75-78b5-421a-938e-97fe6d77c8c2
exl-id: 9f57087f-895d-43b9-9b6a-9cfb4c794c7b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1489'
ht-degree: 0%

---

# Ställning{#scaffolding}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Ibland kan du behöva skapa en stor uppsättning sidor som har samma struktur men olika innehåll. Genom det AEM standardgränssnittet skulle du behöva skapa varje sida, dra lämpliga komponenter till sidan och fylla i varje sida separat.

Med hjälp av ställningar kan du skapa ett formulär (en struktur) med fält som motsvarar den struktur du vill ha för sidorna och sedan använda det här formuläret för att enkelt skapa sidor som baseras på den strukturen.

>[!NOTE]
>
>Skällning (i det klassiska användargränssnittet) [respekterar MSM-arv](#scaffolding-with-msm-inheritance).

## Så fungerar Scaffolding {#how-scaffolding-works}

Scaffäler lagras i **verktyg** konsol för webbplatsadministratören.

* Öppna **verktyg** konsol och klicka på **Standardsidans placering**.

* Klicka på **geometrixx**.
* Under **geometrixx** du hittar en *avskalad sida* anropad **Nyheter**. Dubbelklicka för att öppna den här sidan.

![howscafels_work](assets/howscaffolds_work.png)

Ställningen består av ett formulär med ett fält för varje innehållspunkt som utgör den sida som ska skapas och fyra viktiga parametrar som är tillgängliga via **Sidegenskaper** på sidan med ställningar.

![pageprops](assets/pageprops.png)

Skolningssidans egenskaper är:

* **Titeltext**: Det här är namnet på själva byggnadssidan. I det här exemplet kallas det&quot;News&quot;.
* **Beskrivning**: Detta visas under rubriken på byggnadssidan.
* **Målmall**: Det här är mallen som används när den här strukturen skapar en ny sida. I det här exemplet är *Innehållssida för Geometrixx* mall.

* **Målsökväg**: Detta är sökvägen till den överordnade sidan under vilken det här skalet skapar nya sidor. I det här exemplet är sökvägen */content/geometrixx/en/news*.

Skaffets brödtext är formen. När en användare vill skapa en sida med hjälp av skalet fyller han i formuläret och klickar *Skapa*, längst ned. I **Nyheter** exemplet ovan innehåller följande fält:

* **Titel**: Det här är namnet på sidan som ska skapas. Det här fältet finns alltid på alla ställningar.
* **Text**: Det här fältet motsvarar en textkomponent på den slutliga sidan.
* **Bild**: Det här fältet motsvarar en bildkomponent på den slutliga sidan.
* **Bild/Avancerat**: **Titel**: Bildens titel.

* **Bild/Avancerat**: **Alt-text**: Alt-texten för bilden.

* **Bild/Avancerat**: **Beskrivning**: Beskrivning av bilden.

* **Bild/Avancerat**: **Storlek**: Bildens storlek.

* **Taggar/nyckelord**: Metadata som ska tilldelas den här sidan. Det här fältet finns alltid på alla ställningar.

## Skapa ett ställningar {#creating-a-scaffold}

Om du vill skapa en ny struktur går du till **verktyg** konsol, sedan **Standardsidans placering** och skapa en ny sida. En malltyp för en sida är tillgänglig, *Ställningsmall.*

*Gå till **Sidegenskaper**på den nya sidan och ange* Titeltext *,* Beskrivning *,* Målmall *och* Målsökväg *, enligt beskrivningen ovan.*

*Därefter måste du definiera strukturen för den sida som det här skalet ska skapa. Det gör du genom att gå till designläge på stödsidan. En länk visas där du kan redigera skalet i **dialogruteredigerare**.

![cq5_dialog_editor](assets/cq5_dialog_editor.png)

I dialogruteredigeraren anger du de egenskaper som ska skapas varje gång en ny sida skapas med det här skalet.

Dialogrutedefinitionen för ett ställningar fungerar på liknande sätt som för en komponent (se [Komponenter](/help/sites-developing/components.md)). Det finns dock några viktiga skillnader:

* Komponentdialogrutans definitioner återges som vanliga dialogrutor (som i t.ex. den mittersta rutan i dialogruteredigeraren) medan definitioner i dialogrutan för att ställa in skala, trots att de visas som vanliga dialogrutor i dialogruteredigeraren, återges som ett ställningar på den skalbara sidan (som visas i **Nyheter** ställningar ovan).
* Komponentdialogrutor innehåller endast fält för de värden som behövs för att definiera innehållet i en enskild specifik komponent. En strukturdialogruta måste innehålla fält för varje egenskap i varje stycke på sidan som ska skapas.
* I komponentdialogrutor är komponenten som används för att återge det angivna innehållet implicit och därför är `sling:resourceType` styckets egenskap fylls i automatiskt när stycket skapas. I ett schackmönster måste all information som definierar både innehållet och den tilldelade komponenten för ett visst stycke anges i själva dialogrutan. I schackold-dialogrutor måste den här informationen anges med *Dold* fält för att skicka den här informationen när sidor skapas.

En titt på exemplet **Nyheter** i dialogrutan kan du förklara hur det fungerar. Gå till designläge på scensidan och klicka på länken för dialogruteredigeraren.

Klicka på dialogrutan **Dialogruta > Tabb-panel > Text > Text**, så här:

![textedit](assets/textedit.png)

Egenskapslistan för det här fältet visas till höger i dialogruteredigeraren enligt följande:

![list_of_properties](assets/list_of_properties.png)

Observera namnegenskapen för det här fältet. Det har värdet

./jcr:content/par/text/text

Det här är namnet på den egenskap som innehållet i det här fältet ska skrivas till när skalet används för att skapa en sida. Egenskapen anges som en relativ sökväg från noden som representerar sidan som ska skapas. Den anger egenskapstexten, under nodtexten, som är under nodparentesen, som i sin tur är underordnad noden jcr:content under sidnoden.

Detta definierar platsen för innehållslagringen för texten som ska infogas i det här fältet. Men vi måste också specificera ytterligare två egenskaper för detta innehåll:

* Det faktum att strängen som lagras här måste tolkas som *RTF* och
* vilken komponent som ska användas för att återge innehållet till den resulterande sidan.

Observera att i en normal komponentdialogruta behöver du inte ange den här informationen eftersom den är implicit eftersom dialogrutan redan är bunden till en viss komponent.

Om du vill ange dessa två informationsdelar använder du dolda fält. Klicka på det första dolda fältet **Dialog > Tab Panel > Text > Hidden**, så här:

![dold](assets/hidden.png)

Egenskaperna för det här dolda fältet är följande:

![hidden_list_props](assets/hidden_list_props.png)

Egenskapen name för det här dolda fältet är

`./jcr:content/par/text/textIsRich`

Det här är en boolesk egenskap som används för att tolka textsträngen som lagras på `./jcr:content/par/text/text.`

Eftersom vi vet att texten bör tolkas som en rik text anger vi `value` egenskap för det här fältet som `true`.

>[!CAUTION]
>
>I dialogruteredigeraren kan användaren ändra värdena för *befintlig* egenskaper i dialogdefinitionen. Användaren måste använda för att lägga till en ny egenskap [CRXDE Lite](/help/sites-developing/developing-with-crxde-lite.md). När ett nytt dolt fält läggs till i en dialogrutedefinition med dialogruteredigeraren har det inte något *value* property (dvs. en egenskap med namnet &quot;value&quot;). Om det dolda fältet i fråga kräver ett standardvärde *value* egenskapen som ska ställas in måste den här egenskapen läggas till manuellt med något av CRX-verktygen. Värdet kan inte läggas till med själva dialogruteredigeraren. Men när egenskapen finns kan dess värde redigeras med dialogruteredigeraren.

Det andra dolda fältet visas om du klickar på det så här:

![hidden2](assets/hidden2.png)

Egenskaperna för det här dolda fältet är följande:

![hidden_list_props2](assets/hidden_list_props2.png)

Egenskapen name för det här dolda fältet är

`./jcr:content/par/text/sling:resourceType`

och det fasta värde som anges för den här egenskapen är

`foundation/components/textimage`

&quot;This specifies that component to be used to render text content of this paragraph is the *Textbild* -komponenten. Använda med `isRichText` booleskt, som anges i det andra dolda fältet, kan komponenten återge den faktiska textsträngen som lagras på `./jcr:content/par/text/text` på önskat sätt.

## Skällning med MSM-arv {#scaffolding-with-msm-inheritance}

I det klassiska användargränssnittet är ställningar helt integrerade med MSM-arv (om tillämpligt).

När du öppnar en sida i **Ställning** läge (med ikonen längst ned i sidosparken) alla komponenter som är föremål för arv indikeras av:

* en låssymbol (för de flesta komponenter), t.ex. Text och rubrik)
* en mask med texten **Klicka för att avbryta arv** (för bildkomponenter)

Dessa visar att komponenten inte kan redigeras - förrän arvet avbryts.

![chlimage_1](assets/chlimage_1.jpeg)

>[!NOTE]
>
>Detta är jämförbart med [ärvda komponenter vid redigering av sidinnehåll](/help/sites-authoring/editing-content.md#inheritedcomponentsclassicui).

Om du klickar på låssymbolen eller bildikonen kan du bryta arvet:

* symbolen ändras till ett öppet hänglås.
* när innehållet är olåst kan du redigera det.

![chlimage_1-1](assets/chlimage_1-1.jpeg)

När du har låst upp kan du återställa arvet genom att klicka på den olåsta hänglåssymbolen. Då försvinner alla ändringar du har gjort.

>[!NOTE]
>
>Om arvet avbryts på sidnivå (från fliken Livecopy i Sidegenskaper) kan alla komponenter redigeras i **Ställning** (de visas i olåst läge).
