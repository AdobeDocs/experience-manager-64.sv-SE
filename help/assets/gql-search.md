---
title: Fulltextsökning i GQL
description: Utforska fulltextsökningsfunktionen i AEM Assets. Använd det för att söka efter resurser baserat på specifika metadata, som titel, beskrivning och författarnamn.
contentOwner: AG
translation-type: tm+mt
source-git-commit: adf44677a0ac833a131aad8187529b094aaca9ef

---


# Fulltextsökning i GQL {#gql-full-text-search}

Utforska fulltextsökningsfunktionen i AEM Assets. Använd det för att söka efter resurser baserat på specifika metadata, som titel, beskrivning och författarnamn.

Med fulltextsökningsfunktionen i GQL kan du söka efter resurser baserat på specifika metadata, som titel, beskrivning, författare och så vidare.

Om du vill söka efter en resurs baserat på dess metadata, till exempel titel, anger du metadatanyckelordet följt av dess värde i sökpanelen. Funktionen för fulltextsökning i GQL hämtar endast resurser vars metadata exakt matchar det värde du anger.

Om du till exempel vill söka efter resurser som har titeln &quot;Mål&quot; utför du följande steg:

## Söka efter resurser {#searching-assets}

1. I verktygsfältet i Assets-användargränssnittet klickar eller trycker du på **[!UICONTROL sökikonen]** för att visa rutan Omnissearch.

   ![](assets/do-not-localize/chlimage_1.png)

1. Tryck på Retur med markören i rutan Sök.
1. Klicka på eller tryck på ikonen GlobalNav för att visa panelen **[!UICONTROL Filter]** .
1. Ange värdet &quot;Target&quot; i rutan Omni Search. Om du vill begränsa sökningen till en viss mapp klickar eller trycker du på bläddringsikonen på panelen Filter och väljer mappen. I det här fallet söks matchningen endast efter i mappen och i undermapparna under den.

   >[!NOTE]
   >
   >Du kan också utföra fulltextsökning i en mapp. I det här fallet måste du ange en icke-tom fulltextsökterm.

   ![gql_search](assets/gql_search.png)

1. Press **[!UICONTROL Enter]**. I användargränssnittet för AEM Resurser visas endast de resurser vars namn exakt matchar&quot;Mål&quot;.

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
| [!UICONTROL Titel] | title:John |
| [!UICONTROL Originalformat] | skapare:John |
| [!UICONTROL Medarbetare] | medarbetare:John |
| [!UICONTROL Plats] | plats:Indien |
| [!UICONTROL Beskrivning] | description:&quot;Sample Image&quot; |
| [!UICONTROL Skapare] | creator:&quot;Adobe Photoshop 7.0&quot; |
| [!UICONTROL Copyright-ägare] | copyrightowner:&quot;Adobe Systems&quot; |
| [!UICONTROL Medarbetare] | medarbetare:John |
| [!UICONTROL Användningsvillkor] | usageterms:&quot;CopyRights Reserved&quot; |
| [!UICONTROL Skapad] | skapat:YYY-MM-DDTHH:MM:SS.000+05:30..YYY-MM-DDTHH:MM:SS.000+05:30 |
| [!UICONTROL Utgångsdatum] | förfaller:ÅÅÅ-MM-DDTHH:MM:SS.000+05:30..YYY-MM-DDTHH:MM:SS.000+05:30 |
| [!UICONTROL I tid] | ontime:YYY-MM-DDTHH:MM:SS.000+05:30.YYY-MM-DDTHH:MM:SS.000+05:30 |
| [!UICONTROL Fråntid] | offtime:YYY-MM-DDTHH:MM:SS.000+05:30..YYY-MM-DDTHH:MM:SS.000+05:30 |
| [!UICONTROL Tidsintervall] (förfaller dateontime, offtime) | faktafält: nedsänkt..upperbound |
| [!UICONTROL Bana] | /content/dam/&lt;mappnamn> |
| [!UICONTROL PDF-titel] | pdftitle:&quot;Adobe Document&quot; |
| [!UICONTROL Ämne] | ämne:&quot;Utbildning&quot; |
| [!UICONTROL Taggar] | taggar:&quot;Plats och resa&quot; |
| [!UICONTROL Typ] | type:&quot;image\png&quot; |
| [!UICONTROL Bildens bredd] | width:lowerbound..upperbound |
| [!UICONTROL Bildens höjd] | height:lowerbound..upperbound |
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

* Så här visar du resurser som innehåller en viss sträng och har ett specifikt egenskapsvärde (till exempel: sök efter Adobe-sträng i resurser med titel=John Doe)

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

## Boosting Search {#boosting-search}

Du kan förbättra nyckelordens relevans för vissa resurser för att öka sökningen baserat på nyckelorden. Det innebär att de bilder som du befordrar särskilda nyckelord för visas högst upp i sökresultatet när du söker baserat på dessa nyckelord.

1. Öppna egenskapssidan för resursen som du vill befordra ett nyckelord för i resursgränssnittet.
1. Växla till fliken **[!UICONTROL Avancerat]** och klicka/tryck på **[!UICONTROL Lägg till]** under **[!UICONTROL Upphöjd för att söka efter nyckelord]**.

   ![elevate_for_search](assets/elevate_for_search.png)

1. I rutan **[!UICONTROL Sök efter]** ökning anger du ett nyckelord som du vill öka sökningen efter bilden för och klickar/trycker sedan på **[!UICONTROL Lägg till]**. Ange vid behov flera nyckelord på samma sätt.

   ![add_search_word](assets/add_search_word.png)

1. Klicka/tryck på **[!UICONTROL Spara och stäng]**.
1. Sök efter nyckelordet med rutan Sök. Den resurs som du befordrade nyckelordet för visas bland de översta sökresultaten.