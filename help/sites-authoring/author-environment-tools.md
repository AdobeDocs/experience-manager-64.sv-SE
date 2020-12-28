---
title: Redigeringsmiljö och -verktyg
seo-title: Redigeringsmiljö och -verktyg
description: I redigeringsmiljön i AEM finns olika sätt att ordna och redigera ditt innehåll
seo-description: I redigeringsmiljön i AEM finns olika sätt att ordna och redigera ditt innehåll
uuid: 2fe17bbf-f431-49bc-9d27-7a95f1f76252
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 4f6a525d-d291-426f-be22-d2ef92c57156
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '2142'
ht-degree: 9%

---


# Redigeringsmiljö och verktyg{#authoring-the-environment-and-tools}

I redigeringsmiljön i AEM finns olika sätt att ordna och redigera ditt innehåll. Verktygen som tillhandahålls är tillgängliga från olika konsoler och sidredigerare.

## Hantera din plats {#managing-your-site}

Med konsolen **Platser** kan du navigera och hantera din webbplats med hjälp av sidhuvudsfältet, verktygsfältet, åtgärdsikonerna (gäller för den valda resursen), vägbeskrivningar och, när den är markerad, sekundära spår (t.ex. tidslinje och referenser).

Kortvyn:

![chlimage_1-290](assets/chlimage_1-290.png)

## Redigera sidinnehåll {#editing-page-content}

Du kan redigera en sida med sidredigeraren. Till exempel:

`http://localhost:4502/editor.html/content/we-retail/us/en/equipment.html`

![screen_shot_2018-03-22at141536](assets/screen_shot_2018-03-22at141536.png)

>[!NOTE]
>
>Första gången du öppnar en sida för redigering visas en serie bilder med en genomgång av funktionerna.
>
>Du kan när som helst hoppa över genomgången och upprepa den genom att välja **Sidinformation**-menyn.

## Få hjälp {#accessing-help}

När du redigerar en sida kan du komma åt **hjälpen** från:

* väljaren [**Sidinformation**](/help/sites-authoring/editing-page-properties.md#page-properties), Då visas introduktionsbilderna (som visas första gången du öppnar redigeraren).
* dialogrutan [configuration](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) för specifika komponenter (med ? ikon i dialogrutans verktygsfält); detta visar sammanhangsberoende hjälp.

Ytterligare [hjälprelaterade resurser är tillgängliga från konsoler](/help/sites-authoring/basic-handling.md#accessing-help).

## Komponentbläddraren {#components-browser}

Komponentwebbläsaren visar alla komponenter som är tillgängliga för användning på den aktuella sidan. Dessa kan dras till rätt plats och sedan redigeras för att lägga till ditt innehåll.

Komponentläsaren är en flik i sidopanelen (tillsammans med [resursläsaren](/help/sites-authoring/author-environment-tools.md#assets-browser) och [innehållsträdet](/help/sites-authoring/author-environment-tools.md#content-tree)). Om du vill öppna (eller stänga) sidopanelen använder du ikonen längst upp till vänster i verktygsfältet:

![](do-not-localize/screen_shot_2018-03-22at141659.png)

När du öppnar sidopanelen öppnas den från vänster sida (välj fliken **Komponenter** om det behövs). När du är öppen kan du bläddra igenom alla komponenter som är tillgängliga för sidan.

Det faktiska utseendet och hanteringen beror på vilken enhetstyp du använder:

>[!NOTE]
>
>En mobil enhet identifieras när bredden är mindre än 1 024 pixlar. Detta kan även vara fallet för ett litet skrivbordsfönster.

* **Mobil enhet (t.ex. iPad)**

   Komponentwebbläsaren täcker hela sidan som redigeras.

   Om du vill lägga till en komponent på sidan håller du ned pekaren på den och flyttar den åt höger. Komponentwebbläsaren stängs och sidan visas igen, där du kan placera komponenten.

   ![screen_shot_2018-03-22at141752](assets/screen_shot_2018-03-22at141752.png)

* **Skrivbordsenhet**

   Komponentwebbläsaren öppnas till vänster i fönstret.

   Om du vill lägga till en komponent på sidan klickar du på den önskade komponenten och drar den till önskad plats.

   ![screen_shot_2018-03-22at141808](assets/screen_shot_2018-03-22at141808.png)

   Komponenterna representeras av

   * Komponentnamn
   * Komponentgrupp (i grått)
   * Ikon eller förkortning

      * Standardkomponentens ikoner är monokroma.
      * Förkortningar är alltid de två första tecknen i komponentnamnet.

   I det övre verktygsfältet i komponentwebbläsaren kan du:

   * Filtrera komponenter efter namn.
   * Begränsa visningen till en viss grupp med listrutan.

   Om du vill ha en mer detaljerad beskrivning av komponenten kan du klicka eller trycka på informationsikonen bredvid komponenten i komponentläsaren (om den är tillgänglig).

   ![screen_shot_2018-03-22at141929](assets/screen_shot_2018-03-22at141929.png)

   Mer information om de komponenter som är tillgängliga finns i [komponentkonsolen](/help/sites-authoring/default-components-console.md).

## Resursläsaren {#assets-browser}

Resursläsaren visar alla resurser som är tillgängliga för direkt användning på den aktuella sidan.

Resursläsaren är en flik i sidopanelen tillsammans med [komponenterna browse](/help/sites-authoring/author-environment-tools.md#components-browser)r och [innehållsträdet](/help/sites-authoring/author-environment-tools.md#content-tree). Om du vill öppna eller stänga sidopanelen använder du ikonen längst upp till vänster i verktygsfältet:

![](do-not-localize/screen_shot_2018-03-22at141659-1.png)

När du öppnar sidopanelen öppnas den från vänster sida. Välj fliken **Resurser** om det behövs.

![](do-not-localize/screen_shot_2018-03-22at142035.png)

När resursläsaren är öppen kan du bläddra bland alla resurser som är tillgängliga för sidan. Oändlig rullning används för att expandera listan vid behov.

![chlimage_1-291](assets/chlimage_1-291.png)

Om du vill lägga till en resurs på sidan markerar och drar du den till önskad plats. Detta kan vara:

* En befintlig komponent av lämplig typ.

   * Du kan till exempel dra en resurs av typen bild till en bildkomponent.

* En [platshållare](/help/sites-authoring/editing-content.md#component-placeholder) i styckesystemet för att skapa en ny komponent av lämplig typ.

   * Du kan t.ex. dra en resurs av typen bild till styckesystemet för att skapa en bildkomponent.

>[!NOTE]
>
>Detta är tillgängligt för specifika resurser och komponenttyper. Mer information finns i [Infoga en komponent med Resursläsaren](/help/sites-authoring/editing-content.md#inserting-a-component-using-the-assets-browser).

I det övre verktygsfältet i resursläsaren kan du filtrera resurserna efter:

* Namn
* Bana
* Resurstyp som bilder, manuskript, dokument, videor, sidor, stycken och produkter
* Resursegenskaper som Orientation (stående, liggande, fyrkantig) och Style (färg, monokrom, gråskala)

   * Endast tillgängligt för vissa tillgångstyper

Det faktiska utseendet och hanteringen beror på vilken enhetstyp du använder:

>[!NOTE]
>
>En mobil enhet upptäcks när bredden är mindre än 1024px. dvs. även i ett litet skrivbordsfönster.

* **Mobil enhet som iPad**

   Resursläsaren täcker hela sidan som redigeras.

   Om du vill lägga till en resurs på sidan håller du pekaren över den resurs du behöver och sedan flyttar den åt höger. Resursläsaren stängs och sidan visas igen där du kan lägga till resursen i den nödvändiga komponenten.

   ![screen_shot_2018-03-22at14223](assets/screen_shot_2018-03-22at142223.png)

* **Skrivbordsenhet**

   Resursläsaren öppnas till vänster i fönstret.

   Om du vill lägga till en resurs på sidan klickar du på den önskade resursen och drar den till önskad komponent eller plats.

   ![screen_shot_2018-03-22at142337](assets/screen_shot_2018-03-22at142337.png)

Om du snabbt behöver göra en ändring i en resurs kan du starta [resursredigeraren](/help/assets/managing-assets-touch-ui.md) direkt från resursläsaren genom att klicka på redigeringsikonen som visas bredvid resursens namn.

![](do-not-localize/screen_shot_2018-03-22at142448.png)

## Innehållsträd {#content-tree}

**Innehållsträdet** ger en översikt över alla komponenter på sidan i en hierarki så att du snabbt kan se hur sidan är uppbyggd.

Innehållsträdet är en flik i sidopanelen (tillsammans med komponenterna och resursläsaren). Om du vill öppna (eller stänga) sidopanelen använder du ikonen längst upp till vänster i verktygsfältet:

![](do-not-localize/screen_shot_2018-03-22at142042.png)

När du öppnar sidopanelen öppnas den (från vänster sida). Välj fliken **Innehållsträd** om det behövs. När den är öppen kan du se en trädvyrepresentation av sidan eller mallen, så att det blir lättare att förstå hur innehållet är hierarkiskt strukturerat. På en komplex sida är det dessutom enklare att växla mellan sidans komponenter.

![screen_shot_2018-03-22at142526](assets/screen_shot_2018-03-22at142526.png)

En sida kan enkelt bestå av många av samma typ av komponenter, så komponentträdet visar beskrivande text (i grått) efter komponenttypens namn (i svart). Den beskrivande texten kommer från vanliga egenskaper för komponenten, t.ex. rubrik eller text.

Komponenttyper visas på användarspråket, medan komponentbeskrivningstexten kommer från sidspråket.

Om du klickar på markören bredvid en komponent kommer den nivån att komprimeras eller utökas.

![screen_shot_2018-03-22at142559](assets/screen_shot_2018-03-22at142559.png)

Om du klickar på komponenten markeras komponenten i sidredigeraren.

![screen_shot_2018-03-22at142647](assets/screen_shot_2018-03-22at142647.png)

Om komponenten som du klickar på i trädet är redigerbar visas en skiftnyckelsikon till höger om namnet. Om du klickar på den här ikonen öppnas redigeringsdialogrutan för komponenten.

![](do-not-localize/screen_shot_2018-03-22at142725.png)

>[!NOTE]
>
>Innehållsträdet är inte tillgängligt om du redigerar en sida på en mobil enhet (om webbläsarbredden är mindre än 1024px).

## Fragment - Associerad innehållsläsare {#fragments-associated-content-browser}

Om sidan innehåller innehållsfragment har du även åtkomst till [webbläsaren för associerat innehåll](/help/sites-authoring/content-fragments.md#using-associated-content).

## Referenser {#references}

**** Referenser visar anslutningar till den valda sidan:

* Ritningar
* Launches
* Live-kopior
* Språkversioner
* Användning av referenskomponenten
* Referenser till produktsidor (från Commerce - Products-konsolen)

Öppna den nödvändiga konsolen, gå till den önskade resursen och öppna **Referenser** med:

![screen_shot_2018-03-22at153653](assets/screen_shot_2018-03-22at153653.png)

[Välj önskad ](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources) resurs för att visa en lista över referenstyper som är relevanta för den resursen:

![screen_shot_2018-03-22at153731](assets/screen_shot_2018-03-22at153731.png)

Välj lämplig referenstyp för mer information. I vissa situationer är ytterligare åtgärder tillgängliga när du väljer en specifik referens, bland annat:

* Förekomster av komponenten Reference (t.ex. navigera till referenssidan/referenssidan)
* [Referenser till produktsidor](/help/sites-administering/generic.md#showing-product-references)  (finns i Commerce-Products-konsolen)
* [Launches](/help/sites-authoring/launches.md)
* [Live-](/help/sites-administering/msm.md) kopior visar sökvägarna för alla live-kopior som baseras på den valda resursen.
* [Blueprint](/help/sites-administering/msm-best-practices.md)
* [Språkkopior](/help/sites-administering/tc-manage.md#creating-translation-projects-using-the-references-panel)

Du kan till exempel korrigera en bruten referens i en Reference-komponent:

![chlimage_1-292](assets/chlimage_1-292.png)

## Händelser - Tidslinje {#events-timeline}

För lämpliga resurser (t.ex. sidor från konsolen **Platser** eller resurser från konsolen **Resurser**) kan tidslinjen [användas för att visa den senaste aktiviteten för valda objekt](/help/sites-authoring/basic-handling.md#timeline).

Öppna den nödvändiga konsolen, navigera sedan till önskad resurs och öppna **tidslinjen** med:

![screen_shot_2018-03-22at153952](assets/screen_shot_2018-03-22at153952.png)

[Välj önskad resurs](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources) och sedan  **Visa** alla  **** aktiviteter för att visa alla senaste åtgärder för de valda resurserna:

![screen_shot_2018-03-22at154130](assets/screen_shot_2018-03-22at154130.png)

## Sidinformation {#page-information}

Sidinformation (equalizer-ikonen) öppnar en meny som även innehåller information om den senaste redigeringen och det senaste dokumentet. Beroende på sidans egenskaper (och dess plats) kan det finnas fler eller färre alternativ:

![screen_shot_2018-03-22at154210](assets/screen_shot_2018-03-22at154210.png)

* [Öppna egenskaper](/help/sites-authoring/editing-page-properties.md)
* [Utrullningssida](/help/sites-administering/msm.md#msm-from-the-ui)
* [Starta arbetsflöde](/help/sites-authoring/workflows-applying.md#starting-a-workflow-from-the-page-editor)
* [Lås sida](/help/sites-authoring/editing-content.md#locking-a-page)
* [Publicera sida](/help/sites-authoring/publishing-pages.md#publishing-pages)
* [Avpublicera sida](/help/sites-authoring/publishing-pages.md#unpublishing-pages)
* [Visa som publicerad](/help/sites-authoring/editing-content.md#view-as-published)
* [Visa i Admin](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources)
* [Hjälp](/help/sites-authoring/basic-handling.md#accessing-help)

Om det är lämpligt har till exempel **Sidinformation** även följande alternativ:

* [Promote ](/help/sites-authoring/launches-promoting.md) Launchom sidan är en startsida.
* [Redigera ](/help/sites-authoring/templates.md) mall om sidan baseras på en  [redigerbar mall](/help/sites-authoring/templates.md#editable-and-static-templates)

* [Öppna i Classic ](/help/sites-authoring/select-ui.md#switching-to-classic-ui-when-editing-a-page) UIom det här alternativet har  [aktiverats av en administratör](/help/sites-administering/enable-classic-ui-editor.md)

Dessutom kan **Sidinformation** ge åtkomst till analyser och rekommendationer, när det är lämpligt.

## Sidlägen {#page-modes}

Det finns olika lägen när du redigerar en sida som tillåter olika åtgärder:

* [Redigera](/help/sites-authoring/editing-content.md)  - det läge som ska användas när sidinnehållet redigeras.
* [Layout](/help/sites-authoring/responsive-layout.md)  - gör att du kan skapa och redigera en responsiv layout beroende på enhet (om sidan baseras på en layoutbehållare)

* [Scofolding](/help/sites-authoring/scaffolding.md)  - hjälper dig att skapa en stor uppsättning sidor som har samma struktur men med olika innehåll.
* [Utvecklare](/help/sites-developing/developer-mode.md)  - gör att du kan utföra olika åtgärder (kräver behörighet). Dessa omfattar granskning av den tekniska informationen på en sida och dess komponenter.

* [Med Design](/help/sites-authoring/default-components-designmode.md)  kan du aktivera/inaktivera komponenter för användning på en sida och konfigurera komponentens design (om sidan är baserad på en  [statisk mall](/help/sites-authoring/templates.md#editable-and-static-templates)).

* [Målinriktning](/help/sites-authoring/content-targeting-touch.md)  - öka innehållets relevans genom målinriktning och mätning i alla kanaler.
* [Activity Map](/help/sites-authoring/pa-using.md) - visar analysdata för sidan.

* [Timewarp](/help/sites-authoring/working-with-page-versions.md#timewarp)  - gör att du kan visa ett sidläge vid en viss tidpunkt.
* [Live Copy-status](/help/sites-authoring/editing-content.md#live-copy-status)  - ger en snabb översikt av live-kopians status och vilka komponenter som ärvs/inte ärvs.
* [Förhandsgranska](/help/sites-authoring/editing-content.md#previewing-pages)  - används för att visa sidan så som den kommer att visas i publiceringsmiljön. eller navigera med hjälp av länkar i innehållet.

* [Anteckning](/help/sites-authoring/annotations.md)  - används för att lägga till eller visa anteckningar på sidan.

Du kommer åt dem med hjälp av ikonerna i det övre högra hörnet. Den faktiska ikonen ändras för att återspegla det läge som du använder för närvarande:

![chlimage_1-293](assets/chlimage_1-293.png)

>[!NOTE]
>
>* Beroende på sidans egenskaper kanske vissa lägen inte är tillgängliga.
>* Åtkomst till vissa lägen kräver lämplig behörighet/behörighet.
>* Utvecklarläget är inte tillgängligt på mobila enheter på grund av utrymmesbegränsningar.
>* Det finns ett [kortkommando](/help/sites-authoring/page-authoring-keyboard-shortcuts.md) (`Ctrl-Shift-M`) som du kan använda för att växla mellan **förhandsvisning** och det aktuella läget (t.ex. **Redigera** eller **Layout**).

>



## Banmarkering {#path-selection}

När du redigerar är det ofta nödvändigt att välja en annan resurs, till exempel när du definierar en länk till en annan sida eller resurs eller markerar en bild. För att enkelt kunna välja en sökväg erbjuder [sökvägsfält](/help/sites-authoring/author-environment-tools.md#path-fields) automatisk komplettering och [sökvägsläsaren](/help/sites-authoring/author-environment-tools.md#path-browser) ger ett stabilare urval.

### Sökvägsfält {#path-fields}

Det exempel som används här för att illustrera är bildkomponenten. Mer information om att använda och redigera komponenter finns i [Komponenter för sidredigering](/help/sites-authoring/default-components.md).

Sökvägsfält har automatisk komplettering och framåtblickande funktioner som gör det enklare att hitta en resurs. Börja skriva i sökvägsfältet så får AEM matchande sökvägar när du skriver.

![screen_shot_2018-03-22at154403](assets/screen_shot_2018-03-22at154403.png)

Om du klickar på knappen **Öppna markeringsdialogrutan** i sökvägsfältet öppnas dialogrutan [sökvägsvisning](/help/sites-authoring/author-environment-tools.md#path-browser) för mer detaljerade markeringsalternativ.

![](do-not-localize/screen_shot_2018-03-22at154427.png)

### Sökvägsläsaren {#path-browser}

Sökvägsläsaren är organiserad som [kolumnvyn](/help/sites-authoring/basic-handling.md#column-view) i platskonsolen, vilket ger ett mer detaljerat urval av resurser.

![screen_shot_2018-03-22at154521](assets/screen_shot_2018-03-22at154521.png)

När en resurs har valts aktiveras knappen **Välj** längst upp till höger i dialogrutan. Klicka eller tryck för att bekräfta markeringen eller **Avbryt** för att avbryta.

Om det går att välja flera resurser aktiveras även knappen Välj när du väljer en resurs och antalet valda resurser läggs till i det övre högra hörnet fönstret. Klicka på X bredvid talet för att avmarkera alla.

![chlimage_1-294](assets/chlimage_1-294.png)

Du kan använda vägbeskrivningar för att snabbt hoppa in i resurshierarkin.

![chlimage_1-295](assets/chlimage_1-295.png)

Du kan när som helst använda sökfältet högst upp i dialogrutan.

![chlimage_1-296](assets/chlimage_1-296.png)

Klicka på X i sökfältet för att rensa sökningen.

Om du vill begränsa sökningen kan du visa filteralternativen och filtrera resultaten baserat på en viss bana.

![chlimage_1-297](assets/chlimage_1-297.png)

## Kortkommandon {#keyboard-shortcuts}

Olika [kortkommandon](/help/sites-authoring/page-authoring-keyboard-shortcuts.md) är tillgängliga.
