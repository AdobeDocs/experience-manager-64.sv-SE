---
title: Snabbguide till WCAG 2.0
seo-title: Quick Guide to WCAG 2.0
description: Läs en kort översikt över riktlinjerna för tillgänglighet i WCAG 2.0.
seo-description: Read a quick overview of the WCAG 2.0 accessibility guidelines.
uuid: a5cf463e-89e9-4cc0-9c91-69a1fd3d8ea2
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/MANAGING
topic-tags: managing-accessibility
content-type: reference
discoiquuid: 3cac0e34-7514-48ce-a93b-592bbdbcd252
exl-id: 80edcd53-bc3c-4f61-8dfb-c592e7e51f60
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1708'
ht-degree: 81%

---

# Snabbguide till WCAG 2.0{#quick-guide-to-wcag}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM har utvecklats för att maximera efterlevnaden av riktlinjerna för tillgänglighet för webbinnehåll:

The [Riktlinjer för tillgängligt webbinnehåll, version 2.0 (WCAG2)](https://www.w3.org/TR/WCAG/) är en uppsättning internationellt erkända riktlinjer som utarbetats av [World Wide Web Consortium (W3C)](https://www.w3.org/) enligt [Web Accessibility Initiative (WAI)](https://www.w3.org/WAI/).

WCAG 2.0 består av en uppsättning teknikoberoende riktlinjer och framgångskriterier för att göra webbinnehåll tillgängligt för och användbart för personer med funktionshinder. De ger råd till webbinnehållsförfattare, designers och utvecklare som ser till att de resurser de producerar är så tillgängliga som möjligt för så många människor som möjligt, oavsett vilka funktionshinder de har, t.ex. synnedsättning, hörselnedsättning, inlärningssvårigheter, åldersrelaterade begränsningar med mera.

Om du till exempel beskriver en bild (eller annat innehåll som inte är text) genom att använda attributet `alt` i HTML blir det till stor fördel för personer som är blinda eller har nedsatt syn. Textbeskrivningen i attributet `alt` kan antingen konverteras till tal eller överföras till elektroniska, uppdateringsbara blindskriftsskärmar. 

Dessutom kan WCAG 2.0 leda till fördelar för andra mottagare, inklusive personer som kan begränsas beroende på en viss *situation*. Det kan vara personer som på grund av omständigheter som surfteknik, nätverksanslutningshastighet eller surfmiljö kan uppleva hinder som liknar de personer med funktionshinder har.

Med Adobe Experience Manager kan författare och/eller webbplatsägare skapa webbinnehåll som uppfyller relevanta framgångskriterier för WCAG 2.0 nivå A och nivå AA.

Därför är det viktigt att förstå syftet med WCAG 2.0 och hur riktlinjerna är upplagda för att förstå webbtillgänglighet och hur riktlinjerna kan hjälpa till att skapa tillgängligt webbinnehåll.

Syftet med WCAG 2.0 är att tillhandahålla riktlinjer som:

* är **teknikagnostiker:**

   Riktlinjer som kan tillämpas på en rad olika webbinnehållsformat, inte bara HTML. WCAG 2.0 kan alltså omfatta innehåll som genereras som eller tillhandahålls i PDF, Flash, JavaScript och andra befintliga och framtida webbtekniker. Detta syftar till att åtgärda en svaghet i WCAG 1.0, eftersom det fokuserades på HTML på bekostnad av andra webbinnehållsformat.

* är **testbar:**

   Varje riktlinje är skriven på ett sådant sätt att den kan testas objektivt för att säkerställa att en grupp experter på tillgänglighet i allmänhet håller med om att riktlinjen har följts. En av utmaningarna med riktlinjerna för tillgänglighet är att vissa kan testas tekniskt medan andra kräver en mänsklig bedömning för att avgöra om riktlinjerna har följts eller inte. WCAG 2.0 har skrivits i syfte att minska den subjektivitet som fanns i vissa av WCAG 1.0-riktlinjerna och kontrollpunkterna.

* Stödjer **prioriterad och sammanhangsbaserad implementering:**

   Precis som i WCAG 1.0 ges WCAG 2.0-riktlinjerna prioriteringar som rör den troliga effekten av att inte följa en riktlinje för en viss grupp användare med funktionshinder. Detta gör det möjligt för författare att fatta ett välgrundat beslut om de viktigaste riktlinjerna för sin särskilda situation. Dessutom introduceras begreppet *tillgänglighet som stöds*. Detta gör att författare kan fatta beslut om hur de bäst använder webbtekniker som kanske inte har fullständigt stöd för tillgänglighet eller som kan kräva att användarna har särskilda hjälpmedelstekniker och/eller webbläsare för att kunna utnyttja tillgänglighetsfunktionerna.

Dessa mål har i hög grad påverkat strukturen i WCAG 2.0.

>[!NOTE]
>
>Det går inte att skapa en webbplats som tar hänsyn till alla tänkbara funktionshinder eller persontyper. Syftet med WCAG 2.0 är att hjälpa webbförfattare att skapa webbplatser som så långt det rimligen är möjligt är tillgängliga under vissa förhållanden.

>[!NOTE]
>
>Om du känner till WCAG 1.0 kommer du att märka vissa förändringar i WCAG 2.0. De rör omfattning, organisation och mål.

## Struktur {#structure}

WCAG 2.0 är strukturerat på ett sätt som introducerar begrepp för att skapa tillgängligt webbinnehåll på ett gradvis mer detaljerat sätt. Det kan ge intryck av att WCAG 2.0 är en mycket komplex uppsättning sammanlänkade dokument, men målet är att (stegvis) tillhandahålla mer detaljerad information när författarna behöver den, i stället för att tillhandahålla allt i ett mycket stort dokument.

WCAG 2.0 består av fyra huvudprinciper för hjälpmedelsanpassad design. Dessa är:

1. **Perceivable**: Kan en användare känna av webbinnehållet i fråga?
1. **Operable**: Kan en användare navigera, mata in data eller på annat sätt interagera med webbinnehållet?
1. **Understandable**: Kan en användare bearbeta och förstå det webbinnehåll som presenteras?
1. **Robust**: Är webbinnehållet tillgängligt på det sätt som avses för en mängd olika webbläsarmiljöer, inklusive äldre och kommande webbläsarmiljöer?

Dessa principer kallas ibland akronymen POUR.

* Varje **princip** består av en eller flera **riktlinjer**.

   * Riktlinjerna är skrivna som instruktioner som antingen är positiva (gör det här…) eller negativa (gör inte det här…).
   * Riktlinjerna är numrerade från 1.1 till 4.1 där den första siffran motsvarar den överordnade principen.

* Varje riktlinje består av ett eller flera **framgångskriterier**.

   * Framgångskriterier skrivs som programsatser, antingen `True` eller `False` för en given webbsida.
   * Framgångskriterier kan innehålla antingen/eller-alternativ eller undantag för situationer då framgångskriterierna inte behöver uppfyllas.
   * Framgångskriterierna är numrerade enligt den överordnade riktlinjen och principen, från 1.1.1 till 4.1.1. De har också ett kort namn som sammanfattar syftet med kriteriet för enklare referens. Framgångskriterium 1.1.1 är till exempel ett alternativ som inte är text.
   * Framgångskriterierna inkluderar en lista med relaterade **tekniker** (beskrivs nedan).

## Stödresurser {#supporting-resources}

Förutom WCAG 2.0-huvudkomponenterna som principer, riktlinjer och framgångskriterier finns det en rad stöddokument. Vissa av dem ger specifika råd om hur man uppfyller vissa aspekter av riktlinjerna, andra är mer allmänna referenser som hjälper webbförfattare, designers och utvecklare att förstå och använda WCAG 2.0 så effektivt som möjligt.

WCAG 2.0 är ett stabilt dokument och kommer inte att ändras, men de flesta av stödresurserna är dynamiska dokument som kommer att förändras och växa med tiden allt eftersom nya tekniker utvecklas och nya exempel upptäcks på hur webbtillgänglighet kan uppnås.

### WCAG 2.0-resurser {#wcag-resources}

* [En översikt över alla WCAG 2.0-relaterade dokument](https://www.w3.org/WAI/intro/wcag.php);
* [Förklaring av hur olika komponenter relaterar till varandra](https://www.w3.org/WAI/intro/wcag20);
* [WCAG 2.0 Frequently Asked Questions](https://www.w3.org/WAI/WCAG20/wcag2faq.html);

### Techniques for WCAG 2.0 {#techniques-for-wcag}

Techniques for WCAG 2.0 finns på sidan [Techniques for WCAG 2.0](https://www.w3.org/TR/WCAG20-TECHS/).

**Tekniker** utgör nivån under framgångskriterierna i WCAG 2.0-hierarkin. De klassas av WAI som informativa, inte normativa. En specifik teknik behöver alltså inte följas för att en resurs ska uppfylla kraven i WCAG 2.0.

Eftersom tekniker är mycket mer specifika än framgångskriterier avser de vanligtvis en viss teknologi eller innehållstyp (t.ex. HTML eller video) eller en situation (t.ex. e-handel eller e-utbildningsprogramvara). Du kan tänka på tekniker som beprövade exempel på hur specifika riktlinjer och framgångskriterier kan uppfyllas, därför är de till stor hjälp för författare och utvecklare som arbetar i särskilda sammanhang.

Du kan komma åt tekniker:

* Via samlingar (tekniker kan vara allmänna eller relaterade till en viss teknik eller ett visst format som HTML, CSS eller skript på klientsidan) eller
* Via relaterade framgångskriterier. Tekniker kan gälla mer än ett framgångskriterium.

Varje teknik har ett unikt nummer som refererar till dess samling. En av ARIA-teknikerna är till exempel *Technique ARIA2: Identifying required fields with the &quot;required&quot; property*.

Tekniker kan vara tillräckliga, rådgivande eller felaktiga:

* En *tillräcklig teknik* är en teknik som, om den följs, kommer att vara tillräcklig för att uppfylla ett visst framgångkriterium.
* En *rådgivande teknik* är en teknik som, om den följs, kommer att ha en positiv inverkan på tillgängligheten, men kanske inte i sig räcker för att uppfylla ett visst kriterium.
* En *felaktig teknik* är en teknik som beskriver ett specifikt exempel när ett framgångskriterium inte uppfylls.

Informationen om tekniker inkluderar en beskrivning, tillämplighet, exempel, resurser för mer information och detaljer om hur författare kan testa att tekniken har tillämpats korrekt.

Listan över tekniker är inte fullständig och WAI uppdaterar hela tiden listan med nya exempel som återspeglar utvecklingen inom webbteknik, designstrategier och forskningsresultat. Det är därför bra att regelbundet titta efter nyheter i listan över tekniker.

### Understanding WCAG 2.0 {#understanding-wcag}

Detta är en serie dokument som innehåller råd som hjälper läsarna att förstå syftet med specifika riktlinjer och framgångskriterier. Du kan [ladda ned en introduktion samt länkar till mer detaljerad information](https://www.w3.org/TR/2008/NOTE-UNDERSTANDING-WCAG20-20081211/Overview.html).

Varje riktlinje och framgångskriterium har också en egen Understanding-sida med information om:

* Syftet med riktlinjen
* Särskilda framgångskriterier
* Rådgivande tekniker som hjälper till att uppfylla kraven i riktlinjen, men som inte omfattas av något särskilt framgångskriterium.

Sidan Understanding för varje framgångskriterium innehåller information om:

* Syftet med framgångskriteriet.
* Allmänna exempel på hur framgångskriteriet kan uppfyllas.
* Relaterade resurser (ej från W3C) om hur man uppfyller framgångskriteriet.
* Tekniker och fel: specifika och detaljerade exempel på hur framgångskriteriet kan uppfyllas (beskrivs nedan)
* Viktiga termer – en ordlista med termer som är viktiga för att förstå framgångskriteriet.

Ett exempel finns på: [Understanding Success Criterion 1.1.1 (&quot;Non-text content&quot;)](https://www.w3.org/TR/2008/NOTE-UNDERSTANDING-WCAG20-20081211/text-equiv-all.html).

### Så här uppfyller du WCAG 2.0 {#how-to-meet-wcag}

Avsnittet How to Meet finns på sidan [How To Meet WCAG 2.0](https://www.w3.org/WAI/WCAG20/quickref/). Avsnittet innehåller en alternativ presentation av WCAG som förfinar innehållet i riktlinjerna till de som är mest relevanta för en läsares intressen eller omständigheter. Läsare kan filtrera de framgångskriterier som de vill visa genom att ange särskilda tekniker för webbinnehåll, t.ex. Cascading Style Sheets eller skript eller genom att ange en eller flera prioritetsnivåer.

Utan filtrering visar den här resursen alla framgångskriterier grupperade efter riktlinjer. För varje framgångskriterium anges följande:

* Texten till framgångskriteriet.
* En länk till motsvarande Understanding-dokument.
* En lista över relaterade tillräckliga tekniker med länkar till information om varje teknik.
* En lista över relaterade rådgivande tekniker med länkar till information om varje teknik (om sådan finns).
* En lista över relaterade felaktiga tekniker med länkar till information om varje fel.
