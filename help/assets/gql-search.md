---
title: Fulltextsökning i GQL
description: Utforska fulltextsökningsfunktionen i GQL i AEM Assets. Använd det för att söka efter resurser baserat på specifika metadata, som titel, beskrivning och författarnamn.
contentOwner: AG
feature: Search,Metadata
role: Business Practitioner
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '840'
ht-degree: 0%

---


# GQL fulltextsökning {#gql-full-text-search}

Utforska fulltextsökningsfunktionen i GQL i AEM Assets. Använd det för att söka efter resurser baserat på specifika metadata, som titel, beskrivning och författarnamn.

Med fulltextsökningsfunktionen i GQL kan du söka efter resurser baserat på specifika metadata, som titel, beskrivning, författare och så vidare.

Om du vill söka efter en resurs baserat på dess metadata, till exempel titel, anger du metadatanyckelordet följt av dess värde i sökpanelen. Funktionen för fulltextsökning i GQL hämtar endast resurser vars metadata exakt matchar det värde du anger.

Om du till exempel vill söka efter resurser som har titeln &quot;Mål&quot; utför du följande steg:

## Söker resurser {#searching-assets}

1. Klicka eller tryck på ikonen **[!UICONTROL Search]** i verktygsfältet i användargränssnittet för Resurser för att visa Omnissökrutan.

   ![](assets/do-not-localize/chlimage_1.png)

1. Tryck på Retur med markören i rutan Sök.
1. Klicka på eller tryck på ikonen GlobalNav för att visa panelen **[!UICONTROL Filters]**.
1. Ange värdet &quot;Target&quot; i rutan Omni Search. Om du vill begränsa sökningen till en viss mapp klickar eller trycker du på ikonen Bläddra i panelen Filter och väljer mappen. I det här fallet söks matchningen endast efter i mappen och i undermapparna under den.

   >[!NOTE]
   >
   >Du kan också utföra fulltextsökning i en mapp. I det här fallet måste du ange en icke-tom fulltextsökterm.

   ![gql_search](assets/gql_search.png)

1. Tryck på **[!UICONTROL Enter]**. AEM Assets användargränssnitt visar endast de resurser vars namn exakt matchar&quot;Target&quot;.

Med fulltextsökningsfunktionen i GQL kan du söka efter resurser baserat på följande:

* Komplex fråga som skapats genom en kombination av en And-åtgärd, de värden som du anger för flera metadatafält (egenskaper)
* Flera värden för ett metadatafält
* Delsträngsmatchningar

Med fulltextsökningsfunktionen i GQL kan du söka efter resurser baserat på följande metadataegenskaper. Namn på egenskaper (till exempel författare, titel och så vidare) samt värden är skiftlägeskänsliga.

>[!NOTE]
>
>GQL-fulltextsökning fungerar endast för fulltextpredikat.

| Egenskap | Sökformat (fasetvärde) |
|---|---|
| [!UICONTROL Title] | title:John |
| [!UICONTROL Creator] | skapare:John |
| [!UICONTROL Contributor] | medarbetare:John |
| [!UICONTROL Location] | plats:Indien |
| [!UICONTROL Description] | description:&quot;Sample Image&quot; |
| [!UICONTROL Creator tool] | creatortool:&quot;Adobe Photoshop 7.0&quot; |
| [!UICONTROL Copyright Owner] | copyrightowner:&quot;Adobe Systems&quot; |
| [!UICONTROL Contributor] | medarbetare:John |
| [!UICONTROL Usage Terms] | usageterms:&quot;CopyRights Reserved&quot; |
| [!UICONTROL Created] | skapat:YYY-MM-DDTHH:MM:SS.000+05:30..YYY-MM-DDTHH:MM:SS.000+05:30 |
| [!UICONTROL Expires Date] | förfaller:ÅÅÅ-MM-DDTHH:MM:SS.000+05:30..YYY-MM-DDTHH:MM:SS.000+05:30 |
| [!UICONTROL On time] | ontime:YYY-MM-DDTHH:MM:SS.000+05:30.YYY-MM-DDTHH:MM:SS.000+05:30 |
| [!UICONTROL Off time] | offtime:YYY-MM-DDTHH:MM:SS.000+05:30..YYY-MM-DDTHH:MM:SS.000+05:30 |
| [!UICONTROL Range of time] (förfaller dateontime, offtime) | faktafält: nedsänkt..upperbound |
| [!UICONTROL Path] | /content/dam/&lt;mappnamn> |
| [!UICONTROL PDF Title] | pdftitle:&quot;Adobe-dokument&quot; |
| [!UICONTROL Subject] | ämne:&quot;Utbildning&quot; |
| [!UICONTROL Tags] | taggar:&quot;Plats och resa&quot; |
| [!UICONTROL Type] | type:&quot;image\png&quot; |
| [!UICONTROL Width of image] | width:lowerbound..upperbound |
| [!UICONTROL Height of image] | height:lowerbound..upperbound |
| [!UICONTROL Person] | person:John |

Här är några exempel på sökformat för komplexa frågor:

* Så här visar du alla resurser med flera facets-fält (till exempel: title=John Doe and creator tool = Adobe Photoshop):

tiltle:&quot;John Doe&quot; creatortool: Adobe&amp;ast;

* Så här visar du alla resurser när värdet för facets inte är ett enda ord utan en mening (till exempel: title=Scott Reynolds)

title:&quot;Scott Reynolds&quot;

* Så här visar du resurser med flera värden för en enda egenskap (till exempel: title=Scott Reynolds eller John Doe)

title:&quot;Scott Reynolds&quot; ELLER &quot;John Doe&quot;

* Så här visar du resurser med egenskapsvärden som börjar med en viss sträng (till exempel: heter Scott Reynolds)

title:&quot;Scott&quot;

* Så här visar du resurser med egenskapsvärden som slutar med en viss sträng (till exempel: heter Scott Reynolds)

title:&quot;Reynolds&quot;

* Så här visar du resurser med ett egenskapsvärde som innehåller en viss sträng (till exempel: title = Basel Meeting Room)

title:&quot;Meeting&quot;;

* Så här visar du resurser som innehåller en viss sträng och har ett specifikt egenskapsvärde (till exempel: sök efter strängen Adobe i resurser med rubriken=John Doe)

&amp;ast;Adobe&amp;ast; title:&quot;John Doe &quot;OR title:&quot;John Doe&quot; &amp;ast;Adobe&amp;ast;

>[!NOTE]
>
>Egenskapernas sökväg, gräns, storlek och sorteringsordning kan inte vara ELLERed med någon annan egenskap.
>
>Nyckelordet för en användargenererad egenskap är dess fältetikett i egenskapsredigeraren i gemener, med borttagna blanksteg.


>[!NOTE]
>
>Om du skriver en JCR-fråga och bara söker efter delresurser, visas även de matchande refererade resurserna tillsammans med de matchande delresurserna.

Fulltextsökning stöder även operatorer som -, ^ och så vidare. Om du vill söka efter de här bokstäverna som stränglitteraler omger du sökuttrycket med citattecken. Använd till exempel &quot;Anteckningsbok - Skönhet&quot; i stället för Anteckningsbok - Skönhet.

## Startar sökning {#boosting-search}

Du kan förbättra nyckelordens relevans för vissa resurser för att öka sökningen baserat på nyckelorden. Det innebär att de bilder som du befordrar särskilda nyckelord för visas högst upp i sökresultatet när du söker baserat på dessa nyckelord.

1. Öppna egenskapssidan för resursen som du vill befordra ett nyckelord för i resursgränssnittet.
1. Växla till fliken **[!UICONTROL Advanced]** och klicka/tryck på **[!UICONTROL Add]** under **[!UICONTROL Elevate for search keywords]**.

   ![elevate_for_search](assets/elevate_for_search.png)

1. I rutan **[!UICONTROL Search Promote]** anger du ett nyckelord för vilket du vill öka sökningen efter bilden och klickar/trycker sedan på **[!UICONTROL Add]**. Ange vid behov flera nyckelord på samma sätt.

   ![add_search_word](assets/add_search_word.png)

1. Klicka/tryck på **[!UICONTROL Save & Close]**.
1. Sök efter nyckelordet med rutan Sök. Den resurs som du befordrade nyckelordet för visas bland de översta sökresultaten.