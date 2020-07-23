---
title: Lägg till sök&stämpel;amp;Befordra funktioner till sidan
seo-title: Lägg till sök&stämpel;amp;Befordra funktioner till sidan
description: Integrera Search&amp;Promote-funktioner på din webbplats, du kan använda Search&amp;Promote-komponenter för att lägga till funktioner på dina sidor, som nyckelordssökning, förfining av sökresultatsidor och banners.
seo-description: Integrera Search&amp;Promote-funktioner på din webbplats, du kan använda Search&amp;Promote-komponenter för att lägga till funktioner på dina sidor, som nyckelordssökning, förfining av sökresultatsidor och banners.
uuid: 8831aa56-9d7f-44ca-9d32-5901bf762154
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 277d7e67-5778-48cb-89bb-29bcc734a485
translation-type: tm+mt
source-git-commit: 263a1e514fa48f7aa7b696c801718ceff1e43ed7
workflow-type: tm+mt
source-wordcount: '1184'
ht-degree: 0%

---


# Lägga till Search&amp;Promote på sidan {#adding-search-promote-features-to-your-page}

Om du vill integrera Search&amp;Promote på webbplatsen använder du komponenterna för att lägga till följande funktioner på dina : [!UICONTROL Search&Promote]

* Nyckelordssökning
* Sökresultatsida
* Sökförfining
* Banderoller

Observera att du bara kan använda Search&amp;Promote om AEM-administratören har aktiverat dem. Se [Integrera med Adobe-Search&amp;Promote](/help/sites-administering/search-and-promote.md).

Ansikten konfigureras på Search&amp;Promote, liksom den information som varje komponent tillhandahåller. Följande tabell innehåller en kort beskrivning av varje komponent. Efterföljande avsnitt innehåller detaljerad information om hur de används.

<table> 
 <tbody> 
  <tr> 
   <th>Search&amp;Promote-komponent</th> 
   <th>Beskrivning</th> 
  </tr> 
  <tr> 
   <td>Banderoller</td> 
   <td>Visar banderollannonser. Banderoller väljs baserat på data som samlats in via Search&amp;Promote.<br /> </td> 
  </tr> 
  <tr> 
   <td>Breadcrumbs</td> 
   <td>Visar söknyckelordet och den filtersekvens som användaren har tillämpat på sökresultaten.</td> 
  </tr> 
  <tr> 
   <td>Kryssrutelista-Fasett</td> 
   <td>En lista med kryssrutor för att välja aspekter för filtrering av sökresultat.</td> 
  </tr> 
  <tr> 
   <td>Listrutefrekvens</td> 
   <td>En nedrullningsbar lista med aspekter för filtrering av sökresultat.</td> 
  </tr> 
  <tr> 
   <td>Länklistefaktor</td> 
   <td>En lista med facet-länkar för filtrering av sökresultat.</td> 
  </tr> 
  <tr> 
   <td>Sidnumrering</td> 
   <td>Kontroller för navigering i sökresultatsidor.</td> 
  </tr> 
  <tr> 
   <td>Resultat</td> 
   <td>Visar resultatet av en nyckelordssökning.</td> 
  </tr> 
  <tr> 
   <td>Sökning</td> 
   <td>Lägger till ett sökfält på sidan.</td> 
  </tr> 
 </tbody> 
</table>

## Skapa sidan med sökresultat {#creating-the-search-results-page}

Använd WCM-webbplatskonsolen för att skapa en sida för att visa sökresultat. Resultatet av en sökning från en sökkomponent kan visas på den här sidan om samma Search&amp;Promote används.

De komponenter som gör det möjligt för användare att granska sökresultat är Resultat och Sidnumrering. Komponenten **[!UICONTROL Results]** har inga konfigurerbara egenskaper i [!UICONTROL Edit] eller [!UICONTROL Design] läge. Komponenten Results visar bara sökresultaten, som innehåller länkar till andra sidor, och visar antalet resultat för söknyckelordet.

![srchresultatscomp](assets/srchresultscomp.png)

Med **[!UICONTROL Pagination]** komponenten kan användarna navigera på flera sidor i sökresultaten. Användaren kan se antalet sidor, gå till nästa eller föregående sida, välja en sida som ska öppnas eller sammanställa alla resultat på en sida.

![sidnumrering](assets/srchpagination.png)

Du kan konfigurera följande komponentegenskaper i [!UICONTROL Edit] läge för att styra körningsbeteendet:

* **[!UICONTROL Hide single result page]** - Välj det här alternativet om du vill dölja sidnavigeringskontrollerna när sökningen returnerar en enda resultatsida.
* **[!UICONTROL Hide First/Last]** - Välj det här alternativet om du vill förhindra att användare hoppar till första eller sista resultatsidan.
* **[!UICONTROL Hide Previous/Next]** - Avgör om användare kan navigera på resultatsidor i förhållande till den aktuella sidan.
* **[!UICONTROL Hide view all]** - Avgör om användaren kan konsolidera alla sökresultat på en enda sida. Vanligtvis blir användningen av serverresurser effektivare om du tillhandahåller växlingsdata. Välj det här alternativet om du vill förhindra överföring av stora datauppsättningar i ett svarsmeddelande.

## Aktivera filtrering av resultat efter facets {#enabling-the-filtering-of-results-by-facets}

Du kan göra det möjligt för användare att filtrera sökresultat efter aspekter. Med komponenterna **[!UICONTROL Checkbox List Facet]**, **[!UICONTROL Dropdown Facet]** och **[!UICONTROL Link List Facet]** kan användarna välja en eller flera aspekter för filtrering. När du använder dessa komponenter bör du även ta med **[!UICONTROL Breadcrumbs]** komponenten. Bläddringarna anger vilka filter som används.

Komponenterna **[!UICONTROL Checkbox List Facet]**, **[!UICONTROL Dropdown Facet]** och **[!UICONTROL Link List Facet]** har var och en följande egenskaper som du konfigurerar i **[!UICONTROL Edit]** läget:

* **[!UICONTROL Facet Name]** - Namnet på det facet som används för filter.

Komponenten **[!UICONTROL Checkbox List Facet]** visar en lista med ansikten med en medföljande kryssruta. Använd en **[!UICONTROL Checkbox List Facet]** så att användarna kan visa en delmängd av resultaten som innehåller objekt från flera aspekter. Exempelvis är varumärkesaspekten lämplig eftersom flera varumärken tillhandahåller samma typ av produkt.

En kryssruta visas för varje aspekt som är associerad med ett sökresultat. När en användare markerar en kryssruta, läses sidan in igen med en uppdaterad resultatuppsättning. Alla kryssrutor finns kvar på sidan så att kunderna kan lägga till eller ta bort ansikten i filtret när som helst:

![sandpcheckbox comp](assets/sandpcheckboxcomp.png)

Komponenten gör det möjligt för kunderna att välja ett sidobjekt i en nedrullningsbar lista. **[!UICONTROL Dropdown Facet]** Den här komponenten är användbar när du vill att kunderna ska fokusera på ett enda sidobjekt samtidigt. Avdelningsaspekten är till exempel lämplig för att göra det möjligt för kunderna att begränsa produktsökningar efter kön. John söker efter *jeans* och filmar sedan på Men&#39;s Department.

Listrutan fylls i med de aspekter som är associerade med alla sökresultat. När du väljer ett objekt i listrutan läses sidan in igen med en uppdaterad resultatuppsättning. Objekten i listrutan ändras inte så att kunderna när som helst kan växla från aspekten till aspekten.

![sandpdropdown-avdelning](assets/sandpdropdowndepartment.png)

Komponenten gör det möjligt för kunderna att gradvis begränsa sitt fokus till objekt som är kategoriserade under flera fasmedlemmar eller facets. **[!UICONTROL Link List Facet]**

Fasettmedlemmar visas som en lista med länkar. Texten för varje länk är namnet på en fasmedlem som är associerad med det aktuella sökresultatet. När en kund klickar på en facet-länk läses sidan in igen och en delmängd av sökresultaten visas. Listan med länkar uppdateras för att ge ännu mindre fokus.

![sandplinklistcomp](assets/sandplinklistcomp.png)

Länkarna i listan ändras också när ett filter tillämpas från en annan typ av [!UICONTROL Search&Promote] komponent. Användning av flera typer av filterkomponenter kan ge effektiva filterkombinationer.

Komponenten gör det möjligt för kunderna att se de filter som för närvarande tillämpas på sökresultaten, i den ordning som de tillämpades. **[!UICONTROL Breadcrumbs]** Kunder kan klicka på objekten i den synliga sökvägen för att återgå till den filterkombinationen.

![sandpbreadcrumbcomp](assets/sandpbreadcrumbcomp.png)

Du kan konfigurera följande egenskaper för vägbeskrivningar i redigeringsläget för att anpassa komponentens utseende:

* **[!UICONTROL Delimiter]** - Definiera det tecken eller den teckensträng som ska fungera som avgränsare mellan de olika flödena. I fältet Avgränsare accepteras alla teckensträngar som indata. Standardinställningen är: &quot;>&quot; (utan citattecken)
* **[!UICONTROL Trailing Delimiter]** - Definiera ett tecken eller en teckensträng som ska visas i slutet av kolumnerna. Fältet Avgränsare accepterar alla teckensträngar som indata. Standardinställningen för detta är &quot;blank&quot; (d.v.s. inget visas i slutet av den synliga raden)

## Lägga till sökrutor {#adding-search-boxes}

Komponenten **[!UICONTROL Search]** gör det möjligt för kunderna att söka efter nyckelord. Lägg till sökkomponenter på varje sida där du vill ha tillgång till sökningen.

Konfigurera följande egenskaper i **[!UICONTROL Edit]** läge för att styra körningsbeteendet:

* **[!UICONTROL Result Page Path]** - Sökvägen till den sida som visar sökresultaten.
* **[!UICONTROL Enable Auto-Complete]** - Välj det här alternativet om du vill att föreslagna söknyckelord ska visas när kunden börjar skriva i sökrutan.

![sandpsearchcomp](assets/sandpsearchcomp.png)

## Lägga till banners {#adding-banners}

I **[!UICONTROL Banners]** komponenten visas banderollannonser utifrån kundens Search&amp;Promote. Logiken på Search&amp;Replace-servern avgör vilken banderoll som ska visas. En sökning på jeans kan till exempel få en moderelaterad banderoll att visas. Filtrering på Men&#39;s Department kan ytterligare förfina valet av banderoll.

Komponenten **[!UICONTROL Banners]** innehåller en konfigurerbar egenskap med namnet **[!UICONTROL Banner Area]**. I **[!UICONTROL Edit]** läget väljer du ett av egenskapsvärdena för att ange hur banderollen ska visas. Search&amp;Promote avgör vilka värden du kan välja från.

## Exempel på söksida för Search&amp;Promote {#example-search-promote-search-page}

I det här diagrammet visas de komponenter som läggs till på en sida för att skapa den fullt fungerande Search&amp;Promote nedan.

![1328213789109](assets/1328213789109.png) ![sandpage example](assets/sandppageexample.png)

