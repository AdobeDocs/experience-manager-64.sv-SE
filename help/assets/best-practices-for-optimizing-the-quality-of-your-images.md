---
title: Bästa tillvägagångssätt för att optimera bildkvalitet
description: Lär dig de bästa sätten att optimera bildkvaliteten i dynamiska medier
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
exl-id: 2e90bea1-eaac-457b-8588-b18d3a6e8d91
feature: Asset Management,Renditions
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1483'
ht-degree: 5%

---

# Bästa tillvägagångssätt för att optimera bildkvalitet {#best-practices-for-optimizing-the-quality-of-your-images}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Att optimera bildkvaliteten kan vara en tidskrävande process eftersom många faktorer bidrar till att återge godtagbara resultat. Resultatet är delvis subjektivt eftersom individer upplever olika bildkvalitet. Strukturerade experiment är avgörande.

AEM innehåller över 100 kommandon för leverans av dynamiska mediabilder för justering och optimering av bilder och återgivning. Följande riktlinjer kan hjälpa dig att effektivisera processen och uppnå goda resultat snabbt med några viktiga kommandon och bästa metoder.

## Bästa tillvägagångssätt för bildformat (&amp;fmt=) {#best-practices-for-image-format-fmt}

* JPG eller PNG är de bästa alternativen för att leverera bilder med god kvalitet och hanterbar storlek och vikt.
* Om inget formatkommando anges i URL:en är Dynamic Media Image Delivery standard JPG för leverans.
* JPG komprimerar 10:1 och ger vanligtvis mindre bildfilsstorlekar. PNG komprimeras med ett förhållande på cirka 2:1, utom i vissa fall, till exempel när bilder innehåller en vit bakgrund. Vanligtvis är PNG-filernas storlek större än JPG-filer.
* JPG använder förstörande komprimering, vilket innebär att bildelement (pixlar) tas bort under komprimeringen. PNG använder däremot förlustfri komprimering.
* JPG komprimerar ofta fotografiska bilder med bättre återgivning än syntetiska bilder med skarpa kanter och kontrast.
* Om dina bilder innehåller genomskinlighet bör du använda PNG eftersom JPG inte har stöd för genomskinlighet.

Ett tips för bildformat är att börja med den vanligaste inställningen `&fmt=JPG`.

## Bästa tillvägagångssätt för bildstorlek {#best-practices-for-image-size}

Att minska bildstorleken dynamiskt är en av de vanligaste uppgifterna. Det handlar om att ange storleken och, om så önskas, vilket nedsamplingsläge som används för att nedskala bilden.

* För bildstorlek är det bästa och enklaste sättet att använda `&wid=<value>` och `&hei=<value>,`eller bara `&hei=<value>`. Dessa parametrar ställer automatiskt in bildbredden i enlighet med proportionerna.
* `&resMode=<value>`styr den algoritm som används för nedsampling. Börja med `&resMode=sharp2`. Det här värdet ger den bästa bildkvaliteten. När nedsampling används `value =bilin` är snabbare, leder det ofta till aliasing av artefakter.

Ett tips om hur du kan ändra storlek på bilder är att använda `&wid=<value>&hei=<value>&resMode=sharp2` eller `&hei=<value>&resMode=sharp2`

## Bästa tillvägagångssätt för bildskärpa {#best-practices-for-image-sharpening}

Bildskärpa är den mest komplicerade aspekten när det gäller att styra bilder på webbplatsen och var många misstag görs. Ta dig tid att lära dig mer om hur skärpa och oskarp maskning fungerar i AEM genom att titta på [Adobe Dynamic Media Classic bästa praxis för bildkvalitet och skärpa](/help/assets/assets/sharpening_images.pdf) som även gäller för AEM.

Se även [Öka skärpan i en bild med oskarp mask](https://helpx.adobe.com/photoshop/using/adjusting-image-sharpness-blur.html).

Med AEM kan du öka skärpan i bilder vid intag, vid leverans eller både och. I de flesta fall bör du emellertid skärpa upp bilder med endast en metod eller med en annan, men inte med båda metoderna. Att skärpa bilderna vid leverans, på en URL-adress, ger oftast bäst resultat.

Det finns två metoder för bildskärpa:

* Enkel skärpa ( `&op_sharpen`) - Precis som det skärpefilter som används i Photoshop, tillämpar enkel skärpa den grundläggande skärpan på den slutliga vyn av bilden efter den dynamiska storleksändringen. Den här metoden kan dock inte konfigureras av användaren. Det bästa sättet är att inte använda &amp;op_sharpen om det inte behövs.
* Oskarp maskering ( `&op_USM`) - Oskarp maskning är ett skärpefilter som är branschstandard. Det bästa sättet är att göra bilder skarpare med oskarp maskering enligt riktlinjerna nedan. Med Oskarp maskning kan du styra följande tre parametrar:

   * `&op_sharpen=`belopp,radie,tröskelvärde

      * **[!UICONTROL amount]** (0-5, effektens styrka.)
      * **[!UICONTROL radius]** (0-250, bredden på de&quot;skärpelinjer&quot; som ritas runt objektet med skärpa, mätt i pixlar.)

             Tänk på att parametrarnas radie och mängd fungerar mot varandra. Reducerad radie kan kompenseras genom ett ökat belopp. Med radie får du bättre kontroll eftersom ett lägre värde ökar skärpan endast för kantpixlarna, medan ett högre värde ökar skärpan för ett större antal pixlar.
         
      * **[!UICONTROL threshold]** (0-255, effektkänslighet.)

             Den här parametern avgör hur annorlunda de pixlar som ska göras skarpare måste vara jämfört med det omgivande området innan de betraktas som kantpixlar och filtret gör dem skarpare. The **[!UICONTROL threshold]**-parametern hjälper till att undvika att göra områden med liknande färger skarpare, som hudtoner, för mycket. Ett tröskelvärde på 12 ignorerar till exempel små variationer i hudtonens ljusstyrka för att undvika att lägga till ”brus”, men lägger ändå till kantkontrast i områden med hög kontrast, till exempel där ögonfransarna möter huden.
         
         Mer information om hur du ställer in de här tre parametrarna, inklusive de bästa metoderna att använda med filtret, finns i [Adobe Dynamic Media Classic bästa praxis för bildkvalitet och skärpa](/help/assets/assets/sharpening_images.pdf) (gäller även för Dynamic Media AEM).
   * AEM kan du även styra en fjärde parameter: monokrom (0,1). Den här parametern avgör om oskarp maskning används separat på varje färgkomponent med värdet 0 eller på bildens intensitet/intensitet med värdet 1.


Det bästa sättet är att börja med parametern oskarp maskradie. Radie-inställningar som du kan börja med är följande:

* **[!UICONTROL Website]**: 0,2-0,3 pixlar
* **[!UICONTROL Photographic printing (250-300 ppi)]**: 0,3-0,5 pixlar
* **[!UICONTROL Offset printing (266-300 ppi)]**: 0,7-1,0 pixlar
* **[!UICONTROL Canvas printing (150 ppi)]**: 1,5-2,0 pixlar

Öka mängden gradvis från 1,75 till 4. Om skärpan fortfarande inte är som du vill ha den ökar du radien med ett decimalkomma och kör mängden igen från 1,75 till 4. Upprepa vid behov.

Lämna den monokroma parameterinställningen på 0.

### Metodtips för komprimering av JPEG (&amp;qlt=) {#best-practices-for-compression-qlt}

* Den här parametern styr kodningskvaliteten för JPG. Ett högre värde innebär en bild av högre kvalitet men en stor filstorlek. Ett lägre värde innebär en bild med lägre kvalitet men mindre filstorlek. Intervallet för den här parametern är 0-100.
* Om du vill optimera kvaliteten ska du inte ställa in parametervärdet på 100. Skillnaden mellan en inställning på 90 eller 95 och 100 är nästan otydlig, men 100 ökar storleken på bildfilen i onödan. Om du vill optimera kvaliteten men undvika att bildfilerna blir för stora anger du `qlt=<value>` till 90 eller 95.
* Om du vill optimera för en liten bildfilsstorlek men behålla bildkvaliteten på en acceptabel nivå anger du `qlt=<value>` till 80. Värden under 70 till 75 ger en signifikant försämring av bildkvaliteten.
* Det bästa sättet att vara i mitten är att ställa in `qlt=<value>` till 85 om du vill stanna i mitten.
* Använda chroma-flaggan i `qlt=`

   * The `qlt=` parametern har en andra inställning som gör att du kan aktivera nedsampling av färgvärden i RGB `,1` eller avaktivera med hjälp av värdet `,0`.
   * Börja med att stänga av nedsampling av kromaticitet i RGB (`,0`). Den här inställningen ger vanligtvis bättre bildkvalitet, särskilt för syntetiska bilder med många skarpa kanter och kontrast.

Ett tips för komprimering i JPG `&qlt=85,0`.

## Bästa tillvägagångssätt för storleksändring av JPEG (&amp;jpegSize=) {#best-practices-for-jpeg-sizing-jpegsize}

jpegSize är en användbar parameter om du vill försäkra dig om att en bild inte överskrider en viss storlek för leverans till enheter som har begränsat minne.

* Den här parametern anges i kilobyte (`jpegSize=<size_in_kilobytes>`). Det definierar den största tillåtna storleken för bildleverans.
* `&jpegSize=` interagerar med komprimeringsparametern JPG `&qlt=`. Om JPG svarar med den angivna komprimeringsparametern JPG (`&qlt=`) överstiger inte ejpegSize-värdet, bilden returneras med `&qlt=` enligt definition. I annat fall `&qlt=` minskas gradvis tills bilden får plats i den tillåtna maxstorleken eller tills systemet fastställer att den inte får plats och returnerar ett fel.

Som bästa praxis `&jpegSize=` och lägg till parametern `&qlt=` om du levererar JPG-bilder till enheter med begränsat minne.

## Sammanfattning av bästa praxis {#best-practices-summary}

Det bästa sättet att uppnå en hög bildkvalitet och liten filstorlek är att börja med följande kombination av parametrar:

`fmt=jpg&qlt=85,0&resMode=sharp2&op_usm=1.75,0.3,2,0`

Den här kombinationen av inställningar ger utmärkta resultat under de flesta omständigheter.

Om bilden behöver optimeras ytterligare finjusterar du stegvis skärpeparametrarna (oskarp maskning) genom att börja med radien 0,2 eller 0,3. Därefter ökar du mängden gradvis från 1,75 till maximalt 4 (vilket motsvarar 400 % i Photoshop). Kontrollera att resultatet är det önskade.

Om skärpeeffekten fortfarande inte är tillräcklig ökar du radien i decimalsteg. För varje decimalsteg startar du om beloppet vid 1,75 och ökar det gradvis till 4. Upprepa den här processen tills du uppnår önskat resultat. Värdena ovan är en metod som de kreativa studierna har validerat, men kom ihåg att du kan börja med andra värden och följa andra strategier. Oavsett om resultaten är tillfredsställande för dig eller inte är en subjektiv fråga, så är strukturerade experiment avgörande.

När du experimenterar kan du också hitta följande allmänna förslag som kan hjälpa dig att optimera arbetsflödet:

* Testa olika parametrar i realtid direkt på en URL.
* Det är en god vana att gruppera Dynamic Media Image Serving-kommandon i en bildförinställning. En bildförinställning är i princip URL-kommandomakron med egna förinställningsnamn, som `$thumb_low$` och `&product_high$`. Det anpassade förinställningsnamnet i en URL-sökväg gör att dessa förinställningar anropas. Den här funktionen hjälper dig att hantera kommandon och kvalitetsinställningar för olika användningsmönster för bilder på webbplatsen och förkortar den totala längden på URL-adresser.
* AEM erbjuder också mer avancerade sätt att finjustera bildkvaliteten, t.ex. att använda skärpebilder vid inhämtning. För avancerade användningsområden där detta kan vara ett alternativ för att ytterligare justera och optimera återgivningsresultaten, [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html) kan hjälpa er med skräddarsydda insikter och bästa praxis.
