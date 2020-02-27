---
title: Layoutdesign
seo-title: Layoutdesign
description: Layoutdesigndetaljer förklarar hur du kan skapa layouter som ska användas för brev och interaktiv kommunikation.
seo-description: Layoutdesigndetaljer förklarar hur du kan skapa layouter som ska användas för brev och interaktiv kommunikation.
uuid: b21af474-07f5-4bfe-af7d-0c322e2452ae
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: interactive-communications
discoiquuid: 046b1bf9-1ac7-4e2e-ab37-6fe5422dfa20
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Layoutdesign {#layout-design}

XFA-formulärmallar eller XDP-mallar är mallar för:

* [Bokstäver](/help/forms/using/create-letter.md)
* [Tryckkanal](/help/forms/using/web-channel-print-channel.md#printchannel) för [interaktiv kommunikation](/help/forms/using/interactive-communications-overview.md)

* Layoutfragment

En XDP har utformats i Adobe Forms Designer. I den här artikeln finns information om hur du utformar XDP:er för att skapa effektiva korrespondenser/interaktiv kommunikation, till exempel var formulärfält eller målområden ska användas och när layoutfragment ska användas.

## Skapa en layout för brev eller för tryckkanalen Interactive Communications {#creating-a-layout-for-letters-or-for-interactive-communications-print-channel}

En layout definierar den grafiska layouten för en brev-/tryckkanal i ett interaktivt meddelande. Layouten kan innehålla typiska formulärfält som &quot;Adress&quot; och &quot;Referensnummer&quot;. Den innehåller också tomma delformulär som anger målområden. Skapa layouten i formulärdesignern och när den är klar skickar Application Specialist den till AEM-servern. Därifrån kan du välja layout när du skapar en brevbrevmall eller en tryckt kanal för en interaktiv kommunikation.

![Designer: skapa en layout](assets/claimsubrogationlayout.png)

Följ de här stegen för att skapa layouter för brev/tryckkanaler i interaktiv kommunikation:

1. Analysera layouten och avgöra vilket innehåll som upprepas på alla sidor. oftast anpassas sidhuvud och sidfot till den här kategorin. Det här innehållet placeras på mallsidor för layout. Det återstående innehållet går till layoutens innehållssidor. I en policyjacka kan logotypen och företagsadressen läggas till i mallsidans sidhuvud och sidfot. Anmärkning om annullering använder till exempel samma layout.
1. När du utformar innehållssidor delar du upp sidinnehållet i avsnitt. Varje avsnitt är utformat som ett delformulär inbäddat i själva layouten eller som en fragmentlayout. Om avsnittet innehåller tabeller, modellerar du avsnittet som ett layoutfragment.
1. En layout kan utformas så här:

   1. Gör varje avsnitt till ett separat delformulär som innehåller alla element i avsnittet.
   1. Gör varje avsnittsdelformulär underordnat till samma överordnade delformulär. Det överordnade delformulärets layout är inställd på att flöda så att avsnitten kan flyttas nedan om stora data sammanfogas i föregående avsnitt.
   1. Sektion Primär bosättning kan återanvändas även i andra layouter. Skapa den som en fragmentlayout.
   1. Avsnittet Ytterligare intresseinformation innehåller bara två element som placerats under varandra, kan innehålla stora data och är utformad som flödande.
   1. Andra avsnitt innehåller element vid specifika positioner så att de är utformade som positionerade layouter.
   1. Dela upp ett avsnitt i delformulär om avsnittet innehåller element vid specifika positioner och dessa element innehåller stora mängder data. Ordna sedan delformulären så att de fungerar som du vill.
   1. Lägg till ett målområde som platshållare för området Primär bosättning. Den här platshållaren är bunden till fragmentets primära plats vid designen av brev/interaktiv kommunikation.
   1. Överför layouten (och eventuella fragment som använder layouten) till AEM Forms-servern.

## Använda schema {#using-schema}

Du kan använda ett schema i ett layout- eller layoutfragment, men det behövs inte. Om du använder ett schema bör du kontrollera följande:

1. Layout och alla fragmentlayouter som används i en bokstav/interaktiv kommunikation använder samma schema som bokstaven/interaktiv kommunikation.
1. Alla fält som måste fyllas i med data är bundna till schemat.

## Skapa relaterade fält {#creating-relatable-fields}

Som standard anses alla fält vara relaterade till olika andra datakällor. Om layouten innehåller fält som inte är relaterade till en datakälla namnger du fältet med suffixet &quot;_int&quot; (internal); pageCount_int.

Ett relaterbart fält måste:

* vara en XFA &lt;fält> eller &lt;exkl. grupp>
* har en XFA-bindningsreferens
* Om det är en &lt;exklGroup> måste det ha minst ett underordnat alternativknappsfält. annars kan dess värdetyp inte bestämmas

Ett relaterbart fält måste:

* har ett namn

Ett relaterbart fält får inte

* Inkludera ett &quot;_int&quot;-suffix i namnet
* har bindningen angiven som &quot;none&quot;
* vara underordnad ett &lt;exklGroup>-element

Så länge ett relaterbart fält uppfyller villkoren ovan kan det finnas på vilken plats som helst och på vilket kapslingsdjup som helst i layouten. Du kan använda relaterade fält på mallsidor.

Fälten är flexiblare i layoutkonfigurationen än målområdesdelformulär. de är dock knutna till en enda värdetyp. Du kan göra ett fält stort eller ange en fast bredd och höjd och så vidare. Den lösta modulen eller regelresultatet överförs till fältet.

## Bestäm när delformulär och textfält ska användas {#deciding-when-to-use-subforms-and-text-nbsp-fields}

Använd ett delformulär om du vill samla in flera modulinnehåll i en lodrät flödeslayout uppifrån och ned (flera stycken eller bilder). Layouten måste hantera det faktum att delformuläret växer i höjd så att innehållet får plats. Om du inte kan vara säker på att längden på innehållet som är associerat med delformuläret/målet aldrig överstiger det utrymme som är reserverat för delformuläret i layouten, skapar du delformuläret som ett underordnat formulär i en flödeslänkad delformulärsbehållare. Med den här processen ser du till att layoutobjekt under delformuläret flyttas nedåt när delformuläret växer.

Använd ett fält om du vill hämta moduldata eller data från dataordlisteelement till layoutens schema (eftersom fält är bundna till data) eller visa modulinnehåll på en mallsida. Kom ihåg att innehåll på en mallsida inte kan flöda med innehåll på innehållssidan, så du måste se till att bildfältet används som rubriklogotyp. Tabellen innehåller fler kriterier för att bestämma när ett delformulär eller fält ska användas i en layout.

<table> 
 <tbody> 
  <tr> 
   <td><p><strong>Använd ett delformulär när</strong></p> </td> 
   <td><p><strong>Använd ett textfält när</strong></p> </td> 
  </tr> 
  <tr> 
   <td><p>Den innehåller en kombination av element, till exempel Efternamn och Förnamn</p> </td> 
   <td><p>Den innehåller ett enda element, till exempel ett principnummer.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Den innehåller flera stycken</p> </td> 
   <td><p>Texten är figursatt och marginaljusterad</p> </td> 
  </tr> 
  <tr> 
   <td><p>Upprepade, valfria och villkorsstyrda datagrupper är bundna till delformulär, vilket minskar risken för designfel som kan uppstå om skript används för att uppnå samma resultat</p> </td> 
   <td><p>Element som organisationens logotyp och adress visas på alla sidor i ett brev/interaktiv kommunikation. I det här fallet skapar du formulärfält för dessa element och placerar dem på mallsidan. Om du anger att fältbindningen ska vara "Ingen databindning" visas inga fält som relaterade fält i Letter/Interactive Communication Editor. Om du vill relatera någon typ av innehåll till dessa fält måste de ha bindning.</p> <p>Om din företagsadress innehåller mer än en rad med data kan du använda textfältet med alternativet "Tillåt flera rader" för att representera adressen i layouten.</p> <p>Om datatypen för ett textfält är normal text, används den oformaterade textversionen av modulutdata i stället för RTF-versionen (all formatering ignoreras). Om du vill bevara formateringen anger du datatypen för textfältet till RTF.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Texten flödas</p> </td> 
   <td><p>Textfält och bildfält används på mallsidor. Mallsidor kan inte använda delformulär som målområden.</p> </td> 
  </tr> 
  <tr> 
   <td><p>Objekten grupperas och ordnas utan att delformuläret binds till ett dataelement</p> </td> 
   <td><p> </p> </td> 
  </tr> 
  <tr> 
   <td><p>Det finns ett textfält i delformuläret. Delformuläret kan växa och inte skriva över andra objekt under det i layouten.</p> </td> 
   <td><p>Ni behöver enkel åtkomst till data i postprocessen.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Ställa in repetitiva element {#setting-up-repetitive-elements}

När element som organisationens logotyp och adress visas på alla sidor i ett brev/interaktiv kommunikation skapar du formulärfält för dessa element och placerar dem på mallsidan. Använd namnbindning (fältnamn) för dessa fält.

## Ange serveråtergivningsformat {#specify-the-server-nbsp-render-format}

Använd layoutens serveråtergivningsformat till dynamiskt XML-formulär, annars kan inga bokstäver/interaktiv kommunikation som baseras på den här layouten återges korrekt. Som standard är serveråtergivningsformatet i Forms Designer inställt på dynamiskt XML-formulär. För att vara säker på att du använder rätt format:

* I Designer klickar du på **[!UICONTROL Arkiv > Formuläregenskaper > Standard]** och kontrollerar att inställningen PDF-återgivning/format är inställd på dynamiskt XML-formulär.

