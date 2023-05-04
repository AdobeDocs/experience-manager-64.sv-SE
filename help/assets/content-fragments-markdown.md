---
title: Markdown
seo-title: Markdown
description: När du redigerar innehållsfragmentet använder redigeraren markeringssyntax så att du enkelt kan skriva innehåll.
seo-description: When you are authoring, the content fragment editor uses markdown syntax to allow you to easily write content.
uuid: 12b185a5-3d87-4d7c-8d09-8cc2726009a8
contentOwner: AEM Docs
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: content-fragments
content-type: reference
discoiquuid: bde54663-9050-4a5a-93cb-7cd84ac7f071
exl-id: 209f0e02-b883-4104-8358-01cab15e5db2
feature: Content Fragments
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 3%

---

# Markdown {#markdown}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!CAUTION]
>
>Vissa funktioner för innehållsfragment kräver att [AEM 6.4 Service Pack 2 (6.4.2.0) eller senare](/help/release-notes/sp-release-notes.md).

När du [redigering](content-fragments-variations.md#authoring-your-content)använder innehållsfragmentredigeraren *markering* så att du enkelt kan skriva innehåll:

![markeringsredigerare](/help/assets/assets/cfm-6420-08.png)

Du kan definiera:

* [Rubriknotation](/help/assets/content-fragments-markdown.md#heading-notation)
* [Stycken och radbrytningar](/help/assets/content-fragments-markdown.md#paragraphs-and-line-breaks)
* [Länkar](/help/assets/content-fragments-markdown.md#links)
* [Bilder](/help/assets/content-fragments-markdown.md#images)
* [Blockcitat](/help/assets/content-fragments-markdown.md#block-quotes)
* [Listor](/help/assets/content-fragments-markdown.md#lists)
* [Betoning](/help/assets/content-fragments-markdown.md#emphasis)
* [Kodblock](/help/assets/content-fragments-markdown.md#code-blocks)
* [Omvända snedstreck](/help/assets/content-fragments-markdown.md#backslash-escapes)

## Rubriknotation {#heading-notation}

Om du vill skapa en rubrik genom att placera en hash-tagg (#) framför rubriken. En hash-tagg (#) används för en H1, två hash-taggar (#) för en H2 osv. Du kan använda upp till 6 hash-taggar. Till exempel:

    `## This is an H2`

    `### This is an H3`

    `###### This is a H6`

Du kan också skapa en H1 genom att stryka under texten med lika stora tecken och skapa en H2 genom att stryka under texten med minustecken. Till exempel:

    `This is an H1`

    `=============`

    `This is an H2`

    `-------------`

## Stycken och radbrytningar {#paragraphs-and-line-breaks}

Ett stycke är en eller flera på varandra följande textrader, avgränsade med en eller flera tomma rader. En tom rad är en rad som bara innehåller blanksteg eller tabbar. Normala stycken får inte dras in med blanksteg eller tabbar.

En radbrytning skapas genom att en rad avslutas med två eller flera blanksteg och sedan returneras.

## Länkar {#links}

Du kan skapa textbundna länkar och referenslänkar.

I båda formaten avgränsas länktexten av hakparenteser `[]`.

Detta är exempel på textbundna länkar:

    `This is [an example](https://example.com/ "Title") inline link.`

    `This is [an example of an email link](emailto:myaddress@mydomain.info)`

    `[This link](https://example.net/) has no title attribute.`

En referenslänk har följande syntax:

    `Hey you should [checkout][0] this [cool thing][wiki] that I [made][].`

    `[0]: https://www.google.ca`

    `[wiki]: https://www.wikipedia.org`

    `[made]: https://www.stackoverflow.com`

## Bilder {#images}

Syntaxen för bilder liknar länkarna. Du kan skapa textbundna och refererade bilder.

En textbunden bild har till exempel följande syntax:

    `![Alt text](/path/to/img.jpg)`

    `![Alt text](/path/to/img.jpg "Optional title")`

Syntaxen innehåller:

* Ett utropstecken: !;
* följt av en uppsättning hakparenteser som innehåller alt-attributtexten för bilden,
* följt av en uppsättning parenteser, som innehåller URL:en eller sökvägen till bilden och ett valfritt rubrikattribut inom dubbla eller enkla citattecken.

En bild i referensstil har följande syntax:

    `![Alt text][id]`

Där &quot;id&quot; är namnet på en definierad bildreferens. Bildreferenser definieras med samma syntax som länkreferenser:

    `[id]: url/to/image "Optional title attribute"`

## Blockcitat {#block-quotes}

Du kan citera text genom att lägga till symbolen > före texten. Till exempel:

    `>This is block quotes`

    `>asdhfjlkasdhlf`

    `>asdfahsdlfasdfj`

Du kan ha kapslade blockcitattecken. Till exempel:

    `> This is the first level of quoting.`

    `>`

        `>> This is nested blockquote.`

    `>`

    `> Back to the first level.`

## Listor {#lists}

Du kan skapa både sorterade och osorterade listor.

Skapa en osorterad &amp;lista med hjälp av den sista; -symbolen före objekten i listan. Till exempel:

    `* item in list`

    `* item in list`

    `* item in list`

Om du vill skapa en ordnad lista lägger du till siffrorna, följt av en punkt, före varje objekt i listan. Till exempel:

    `1. First item in list.`

    `2. Second item in list.`

    `3. Third item in list.`

## Betoning {#emphasis}

Du kan lägga till kursiv stil eller fetstil i texten.

Så här lägger du till kursiv stil:

    `*single asterisks*`

    `_single underscores_`

    `Keyboard shortcut: Ctrl-I (Cmd-I)`

Du kan fet text enligt följande:

    `**double asterisks**`

    `__double underscores__`

    `Keyboard shortcut: Ctrl-B (Cmd-B)`

Om du vill ange ett kodomfång omsluter du det med citattecken (&grave;). Till skillnad från ett förformaterat kodblock anger ett kodintervall koden i ett normalt stycke.

Till exempel:

    ``Use the `printf()` function.``

## Kodblock {#code-blocks}

Kodblock används vanligtvis för att illustrera källkod. Du kan skapa kodblock genom att dra in koden med en tabb eller med minst fyra mellanslag. Till exempel:

    `This is a normal paragraph.`

        `This is a code block.`

## Omvända snedstreck {#backslash-escapes}

Du kan använda omvänt snedstreck för att generera litterala tecken som har en speciell betydelse för formateringssyntaxen. Om du till exempel vill omge ett ord med literala asterisker (i stället för en HTML-tagg) kan du använda omvända snedstreck före asteriskerna, enligt följande:

    `\\*literal asterisks\\*`

Omvända snedstreck är tillgängliga för följande tecken:

    ` \ backslash`

    `` ` backtick``

    ` * asterisk`

    ` _ underscore`

    ` {} curly braces`

    ` [] square brackets`

    ` () parentheses`

    ` # hash mark`

    ` + plus sign`

    ` - minus sign (hyphen)`

    ` . dot`
