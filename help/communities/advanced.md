---
title: Advanced Scoring and Badges
seo-title: Advanced Scoring and Badges
description: Konfigurera avancerad poängsättning
seo-description: Setting up advanced scoring
uuid: 3854b668-729a-42b8-b7cd-5d5ec1ca8380
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 42fb3c50-8728-4897-ade9-6b839294a10e
role: Admin
exl-id: c9406aae-288e-4cdf-ac01-cb26b423639e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1164'
ht-degree: 0%

---

# Advanced Scoring and Badges {#advanced-scoring-and-badges}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Med avancerad poängsättning kan man tilldela märken för att identifiera medlemmar som experter. Avancerad poängsättning tilldelar poäng baserat på kvantitet *och* kvalitet på innehåll som skapats av en medlem, medan grundläggande poängsättning bara tilldelar poäng baserat på mängden innehåll som skapas.

Denna skillnad beror på poängsättningsmotorn som används för att beräkna poängen. Den grundläggande poängsättningsmotorn använder enkel matematik. Den avancerade bedömningsmotorn är en adaptiv algoritm som belönar aktiva medlemmar som bidrar med värdefullt och relevant innehåll, som dras av genom ämnesens naturliga språkbearbetning.

Förutom innehållets relevans tar bedömningsalgoritmerna hänsyn till medlemsaktiviteter, som röstning och procent av svaren. Även om grundläggande poängsättning innehåller dem kvantitativt, används de algoritmiskt i avancerad poängsättning.

Den avancerade bedömningsmotorn kräver därför tillräckligt med data för att göra analysen meningsfull. Tröskelvärdet för att bli expert omprövas ständigt när algoritmen kontinuerligt anpassas till volymen och kvaliteten på det innehåll som skapas. Det finns också ett koncept *minska* av en medlems äldre inlägg. Om en expertmedlem slutar att delta i det ämne där han eller hon fick expertstatus, vid någon i förväg bestämd tidpunkt (se [poängsättningsmotorkonfiguration](#configurable-scoring-engine)) kan de förlora sin status som expert.

Att ställa in avancerad poängsättning är i stort sett detsamma som grundläggande poängsättning:

* Grundläggande och avancerade regler för poängsättning och märkning är [används på innehåll](implementing-scoring.md#apply-rules-to-content) på samma sätt
   * Grundläggande och avancerade regler för poängsättning och märkning kan tillämpas på samma innehåll
* [Aktivera emblem för komponenter](implementing-scoring.md#enable-badges-for-component) är allmän

Skillnaderna i hur du ställer in poängsättnings- och badging-regler är:

* Konfigurerbar avancerad bedömningsmotor
* Avancerade poängregler:
   * `scoringType` ange till **[!UICONTROL advanced]**
   * Kräver stoppord

* Avancerade märkningsregler:
   * `badgingType` ange till **[!UICONTROL advanced]**
   * `badgingLevels` ange till antalet expertnivåer att tilldela
   * Kräver `badgingPaths` matris med emblem i stället för trösklar, matrismappas punkter till badges

>[!NOTE]
>
>Installera [Expertidentifieringspaket](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq610%2Fsocial%2Ffeaturepack%2Fcq-social-expert-identification-pkg).

## Konfigurerbar bedömningsmotor {#configurable-scoring-engine}

Den avancerade bedömningsmotorn tillhandahåller en OSGi-konfiguration med parametrar som påverkar den avancerade bedömningsalgoritmen.

![chlimage_1-260](assets/chlimage_1-260.png)

* **[!UICONTROL Scoring weights]**
För ett ämne anger du det verb som ska ha högst prioritet när poängen beräknas. Ett eller flera avsnitt kan anges, men begränsat till **ett verb per ämne**. Se [Ämnen och verb](implementing-scoring.md#topics-and-verbs).

   Anges som `topic,verb` med kommat rymt. Till exempel:

   `/social/forum/hbs/social/forum\,ADD`

   Standardvärdet är ADD-verbet för QnA- och forumkomponenter.


* **[!UICONTROL Scoring range]**

   Intervallet för avancerade poängtal definieras av det här värdet (högsta möjliga poäng) och 0 (lägsta möjliga poäng).

   Standardvärdet är 100 så att poängintervallet är 0-100.


* **[!UICONTROL Entity decay time interval]**

   Den här parametern representerar det antal timmar efter vilket alla entitetspoäng dekoreras. Detta krävs för att inte längre inkludera gammalt innehåll i poängen för en community-webbplats.

   Standardvärdet är 216000 timmar (~24 år).


* **[!UICONTROL Scoring growth rate]**

   Detta anger poängen. mellan 0 och poängintervallet, där tillväxten saktar ned för att begränsa antalet experter.

   Standardvärdet är 50.

## Avancerade poängregler {#advanced-scoring-rules}

Vid grundläggande poängsättning är den kvantitet som behövs för att få ett märke känd.

Vid avancerad poängsättning justeras mängden som behövs hela tiden baserat på mängden kvalitetsdata i systemet. Poängen beräknas kontinuerligt på ungefär samma sätt som en klockkurva.

Om en medlem har fått ett expertmärke för ett ämne som inte längre är aktivt, finns det en möjlighet att de förlorar sitt emblem på grund av att de har gått ner över tiden.

### ScoringType {#scoringtype}

En resultatregel är en uppsättning underregler, som vart och ett deklarerar `scoringType`.

Om du vill anropa den avancerade bedömningsmotorn `scoringType`ska anges till `advanced`.

Se [Underregler för poängsättning](implementing-scoring.md#scoring-sub-rules).

![chlimage_1-261](assets/chlimage_1-261.png)

### Stoppord {#stopwords}

Det avancerade poängsättningspaketet installerar en konfigurationsmapp som innehåller en stoppordsfil:

* `/etc/community/scoring/configuration/stopwords`

Den avancerade bedömningsalgoritmen använder listan med ord i stoppordsfilen för att identifiera vanliga engelska ord som ignoreras under innehållsbearbetningen.

Det finns ingen anledning att anta att den här filen kommer att ändras.

Om stoppordsfilen saknas genereras ett fel i den avancerade bedömningsmotorn.

## Avancerade märkningsregler {#advanced-badging-rules}

Egenskaperna för den avancerade badging-regeln skiljer sig från [grundläggande märkningsregelegenskaper](implementing-scoring.md#badging-rules).

I stället för att associera punkter med en badge-bild är det bara nödvändigt att identifiera det antal experter som tillåts och den badge-bild som ska tilldelas.

![chlimage_1-262](assets/chlimage_1-262.png)

| **Egenskap** | **Typ** | **Värdebeskrivning** |
|---------------|----------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| badgingPath | Sträng[] | (Obligatoriskt) En sträng med flera värden av badge-bilder upp till antalet badgingLevels. Sökvägarna för taggbilder måste beställas så att den första tilldelas den högsta experten. Om det finns färre emblem än vad som anges av badgingLevels fyller det sista märket i arrayen ut resten av arrayen. Exempelpost:/etc/community/badging/images/expert-badge/jcr:content/expert.png |
| badgingLevels | Lång | (Valfritt) Anger vilka kunskapsnivåer som ska tilldelas. Om det till exempel ska finnas en expert och en nästan expert (två emblem), ska värdet anges till 2. badgingLevel ska motsvara antalet expertrelaterade badge-bilder som anges för egenskapen badgingPath. Standardvärdet är 1. |
| badgingType | Sträng | (Obligatoriskt) Identifierar bedömningsmotorn som antingen &quot;grundläggande&quot; eller &quot;avancerad&quot;. Ange som &quot;avancerat&quot;, annars är standardvärdet &quot;grundläggande&quot;. |
| scoringRules | Sträng[] | (Valfritt) En sträng med flera värden som begränsar badging-regeln till de poäng som identifieras av de listade poängsättningsreglerna.Exempelpost:/etc/community/scoring/rules/adv-comments-scoringDefault är ingen begränsning. |

## Inkluderade regler och emblem {#included-rules-and-badge}

### Inkluderat märke {#included-badge}

I den här betaversionen ingår ett belöningsbaserat expertmärke:

* expert

   `/etc/community/badging/images/expert-badge/jcr:content/expert.png`

![chlimage_1-263](assets/chlimage_1-263.png)

För att expertmärket ska kunna visas som en belöning för en aktivitet måste två saker hända:

* `badges` måste aktiveras för funktionen, till exempel ett forum eller QnA-komponent
* avancerade regler för bedömning och märkning måste tillämpas på den sida (eller det överordnade) som komponenten placeras på

Se den grundläggande informationen för:

* [Aktivera emblem för en komponent](implementing-scoring.md#enable-badges-for-component)
* [Tillämpar regler](implementing-scoring.md#apply-rules-to-content)

### Inkluderade poängsättningsregler och underregler {#included-scoring-rules-and-sub-rules}

I betaversionen finns två avancerade poängregler för [forumfunktion](functions.md#forum-function) (en var för forumets och kommentarernas komponenter):

1. /etc/community/scoring/rules/adv-comments-scoring

   * `subRules[]` =

      /etc/community/scoring/rules/sub-rules/adv-comments-rule

      /etc/community/scoring/rules/sub-rules/adv-voice-rule-owner

      /etc/community/scoring/rules/sub-rules/adv-voice-rule

2. /etc/community/scoring/rules/adv-forums-scoring

   * `subRules[]` =

      /etc/community/scoring/rules/sub-rules/adv-forums-rule

      /etc/community/scoring/rules/sub-rules/adv-comments-rule

      /etc/community/scoring/rules/sub-rules/adv-voice-rule-owner

**Anteckningar:**

* Båda `rules`och `sub-rules` noder är av typen `cq:Page`
* `subRules` är ett attribut av typen String[] på regelns `jcr:content` nod
* `sub-rules` kan delas mellan olika poängregler
* `rules` ska finnas på en databasplats med läsbehörighet för alla
   * regelnamn måste vara unika oavsett plats

### Inkluderade märkningsregler {#included-badging-rules}

I releasen finns två avancerade regler för märkning som motsvarar [avancerade forum och kommentarsregler](#included-scoring-rules-and-sub-rules).

* /etc/community/badging/rules/adv-comments-badging
* /etc/community/badging/rules/adv-forums-badging

**Anteckningar:**

* `rules` noder är av typen `cq:Page`
* `rules`ska finnas på en databasplats med läsbehörighet för alla
   * regelnamn måste vara unika oavsett plats
