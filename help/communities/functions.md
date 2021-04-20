---
title: Community-funktioner
seo-title: Community-funktioner
description: Lär dig hur du får åtkomst till användarfunktionskonsolen
seo-description: Lär dig hur du får åtkomst till användarfunktionskonsolen
uuid: 5cce05f5-1dd7-496d-94c2-8fccc0177d13
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: cc993b71-e2f2-48e7-ad4e-469cb5ce2dc1
role: Administrator
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '2432'
ht-degree: 0%

---


# Community-funktioner {#community-functions}

Den typ av funktioner som förväntas av en community-upplevelse är välkända. Community-funktioner är tillgängliga som communityfunktioner. De är i princip en eller flera sidor som är färdiga för implementering av en communityfunktion som kräver mer än att bara lägga till en komponent på en sida i redigeringsläge. De är byggstenarna som används för att definiera strukturen för en [community-webbplatsmall](sites.md) från vilken communitywebbplatser [skapas](sites-console.md).

När en communitywebbplats har skapats kan innehåll läggas till på de resulterande sidorna med hjälp av standardredigeringsläget [AEM](../../help/sites-authoring/editing-content.md).

Ett antal communityfunktioner är omedelbart tillgängliga enligt vad som visas i användarfunktionskonsolen. Fler communityfunktioner kommer att levereras i framtida versioner och anpassade funktioner kan också skapas.

>[!NOTE]
>
>Konsolerna för att skapa [communitywebbplatser](sites-console.md), [mallar för communitywebbplatser](sites.md), [mallar för communitygrupper](tools-groups.md) och [communityfunktioner](functions.md) får endast användas i författarmiljön.

## Community Function Console {#community-functions-console}

För att nå användarfunktionskonsolen i redigeringsmiljön

* Från global navigering: **[!UICONTROL Tools > Communities > Community Functions]**

![chlimage_1-379](assets/chlimage_1-379.png)

## Fördefinierade funktioner {#pre-built-functions}

Här följer en kort beskrivning av funktionerna i AEM Communities. Varje funktion består av en eller flera AEM sidor som innehåller webbgruppskomponenter som har kopplats ihop till en funktion som enkelt kan integreras i en [communityplatsmall](sites.md).

En mall för en community-webbplats innehåller strukturen för en community-webbplats, inklusive inloggning, användarprofiler, meddelanden, meddelanden, webbplatsmeny, sökning, teman och varumärken.

### Titel- och URL-inställningar {#title-and-url-settings}

**Titlar** och  **** URL är egenskaper som är gemensamma för alla communityfunktioner.

När en communityfunktion läggs till i en mall för en community-webbplats eller läggs till när [strukturen för en community-webbplats ändras, öppnas funktionens dialogruta så att titeln och URL:en kan konfigureras.](sites-console.md#modifying-site-properties)

#### Information om konfigurationsfunktion {#configuration-function-details}

![chlimage_1-380](assets/chlimage_1-380.png)

* **[!UICONTROL Title]**
(
*obligatorisk*) Den text som visas på menyn med funktioner för webbplatsen

* **[!UICONTROL URL]**
(*obligatoriskt*) Namnet som används för att generera URI:n. Namnet måste följa de [namnkonventioner](../../help/sites-developing/naming-conventions.md) som AEM och JCR har infört.

Använd till exempel den webbplats som skapas från följande [självstudiekurs för att komma igång](getting-started.md), om

* Titel = webbsida
* URL = sida

Därefter är URL:en till sidan http://local_host:4503/content/sites/engage/en/page.html och menylänken för sidan visas som:

![chlimage_1-381](assets/chlimage_1-381.png)

### Funktion för aktivitetsström {#activity-stream-function}

Aktivitetsströmsfunktionen är en sida med en [aktivitetsströmkomponent](activities.md) med alla vyer markerade (alla aktiviteter, användaraktiviteter och följande). Se även [Activity Stream Essentials](essentials-activities.md) för utvecklare.

När du lägger till en mall öppnas följande dialogruta:

#### Information om konfigurationsfunktion {#configuration-function-details-1}

![chlimage_1-382](assets/chlimage_1-382.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Show "My Activities" view]**
Om det här alternativet är markerat innehåller sidan Aktiviteter en flik som filtrerar aktiviteter baserat på aktiviteter som genererats i communityn av den aktuella medlemmen. Standard är markerat.

* **[!UICONTROL Show "All Activities" view]**
Om det här alternativet är markerat innehåller sidan Aktiviteter en flik som innehåller alla aktiviteter som har skapats i den community som den aktuella medlemmen har åtkomst till. Standard är markerat.

* **[!UICONTROL Show "News Feed" view]**
Om det här alternativet är markerat innehåller sidan Aktiviteter en flik som filtrerar aktiviteter baserat på de som den aktuella medlemmen följer. Standard är markerat.

### Tilldelningsfunktion {#assignments-function}

Tilldelningsfunktionen är den grundläggande funktionen som definierar en [community-webbplats för aktivering](overview.md#enablement-community). Det gör det möjligt att tilldela aktiveringsresurser till communitymedlemmar. Se även [Tilldelningar Grundläggande](essentials-assignments.md) för utvecklare.

Den här funktionen är tillgänglig som en funktion i [aktiveringstillägget](enablement.md). Tillägget kräver ytterligare licenser för användning i en produktionsmiljö.

När du lägger till en mall är den enda konfigurationen för [titel- och URL-inställningarna](#title-and-url-settings).

### Bloggfunktion {#blog-function}

Bloggfunktionen är en sida med en [Blog-komponent](blog-feature.md) som är konfigurerad för taggning, filöverföringar, följda, medlemmar som kan redigera själva, rösta och moderera. Se även [Blog Essentials](blog-developer-basics.md) för utvecklare.

När du lägger till en mall öppnas följande dialogruta:

![chlimage_1-383](assets/chlimage_1-383.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Allow Privileged Members]**
Om det här alternativet är markerat tillåter bloggen endast behöriga medlemmar att skapa artiklar genom att tillåta val av en  [privilegierad medlemsgrupp](users.md#privileged-members-group). Om det inte är markerat kan alla community-medlemmar skapa. Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om det här alternativet är markerat innehåller bloggen möjligheten för medlemmar att överföra filer. Standard är markerat.

* **[!UICONTROL Allow Threaded Replies]**
Om den inte är markerad tillåter bloggen svar (kommentarer) på en artikel, men det är inte tillåtet att svara på kommentarer. Standard är markerat.

* **[!UICONTROL Allow Featured Content]**
Om du markerar det här alternativet kan idén identifieras som  [aktuellt innehåll](featured.md). Standard är markerat.

### Kalenderfunktion {#calendar-function}

Kalenderfunktionen är en sida med en [kalenderkomponent](calendar.md) som är konfigurerad för att tillåta taggning. Se även [Calendar Essentials](calendar-basics-for-developers.md) för utvecklare.

När du lägger till en mall öppnas följande dialogruta:

![chlimage_1-384](assets/chlimage_1-384.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Om det här alternativet är markerat kan ämnessvar fästas i början av kommentarlistan. Standard är markerat.

* **[!UICONTROL Allow Privileged Members]**
Om det här alternativet är markerat tillåter bloggen endast behöriga medlemmar att skapa artiklar genom att tillåta val av en  [privilegierad medlemsgrupp](users.md#privileged-members-group). Om det inte är markerat kan alla community-medlemmar skapa. Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om det här alternativet är markerat innehåller bloggen möjligheten för medlemmar att överföra filer. Standard är markerat.

* **[!UICONTROL Allow Threaded Replies]**
Om den inte är markerad tillåter bloggen svar (kommentarer) på en artikel, men det är inte tillåtet att svara på kommentarer. Standard är markerat.

* **[!UICONTROL Allow Featured Content]**
Om du markerar det här alternativet kan idén identifieras som  [aktuellt innehåll](featured.md). Standard är markerat.

### Katalogfunktion {#catalog-function}

Katalogfunktionen gör att medlemmar i [communityn för aktivering](overview.md#enablement-community) kan bläddra bland aktiveringsresurser som de inte har tilldelats. Se [Tagga aktiveringsresurser](tag-resources.md) och [Catalog Essentials](catalog-developer-essentials.md) för utvecklare.

Alla aktiveringsresurser och utbildningsvägar för communitywebbplatsen visas i alla kataloger om egenskapen ` [Show in Catalog](resources.md)` är inställd på true. Om du vill inkludera resurser och utbildningsvägar explicit måste du använda ett [förfilter](catalog-developer-essentials.md#pre-filters) i katalogen.

När den läggs till i en mall tillåter konfigurationen att du anger taggnamnutrymmen som används för att konfigurera taggfiltret som visas för webbplatsens besökare:

![catalogfunc](assets/catalogfunc.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Select All Namespaces]**

   * De markerade taggnamnutrymmena definierar vilka taggar som besökare kan markera för att filtrera listan med aktiveringsresurser som finns i katalogen.
   * Om det här alternativet är markerat är alla taggnamnutrymmen som är tillåtna för communitywebbplatsen tillgängliga.
   * Om alternativet inte är markerat går det att välja ett eller flera namnutrymmen som är tillåtna för communitywebbplatsen.
   * Standard är markerat.

### Funktionen Innehåll {#featured-content-function}

Funktionen för aktuellt innehåll är en sida med en [innehållskomponent](featured.md) som är konfigurerad för att tillåta att kommentarer läggs till och tas bort.

Möjligheten att använda innehåll kan vara tillåten eller otillåten per komponent (se [Bloggfunktion](#blog-function), [Kalenderfunktion](#calendar-function), [Forumfunktion](#forum-function), [Ideationsfunktion](#ideation-function) och [QnA-funktion](#qna-function)).

När du lägger till en mall är den enda konfigurationen för [titel- och URL-inställningarna](#title-and-url-settings).

### Filbiblioteksfunktion {#file-library-function}

Filbiblioteksfunktionen är en sida med en [filbibliotekskomponent](file-library.md) som är konfigurerad för att tillåta att kommentarer läggs till och tas bort.

När du lägger till en mall är den enda konfigurationen för [titel- och URL-inställningarna](#title-and-url-settings).

### Forum Function {#forum-function}

Forumfunktionen är en sida med en [forumkomponent](forum.md) som är konfigurerad för taggning, filöverföringar, och efterföljande medlemmar som kan redigera, rösta och moderera själva.

När du lägger till en mall öppnas följande dialogruta:

#### Information om konfigurationsfunktion {#configuration-function-details-2}

![chlimage_1-385](assets/chlimage_1-385.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Om det här alternativet är markerat kan ämnessvar fästas i början av kommentarlistan. Standard är markerat.

* **[!UICONTROL Allow Privileged Members]**
Om det här alternativet är markerat tillåter forumet endast behöriga medlemmar att publicera ämnen genom att tillåta val av en  [privilegierad medlemsgrupp](users.md#privileged-members-group). Om det inte är markerat kan alla community-medlemmar publicera. Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om det här alternativet är markerat innehåller forumet möjlighet för medlemmar att överföra filer. Standard är markerat.

* **[!UICONTROL Allow Threaded Replies]**
Om det inte är markerat tillåter forumet kommentarer om ett ämne, men svar på dessa kommentarer tillåts inte. Standard är markerat.

* **[!UICONTROL Allow Featured Content]**
Om du markerar det här alternativet kan idén identifieras som  [aktuellt innehåll](featured.md). Standard är markerat.

### Gruppfunktion {#groups-function}

>[!CAUTION]
>
>Gruppfunktionen får *inte* vara *först eller den enda*-funktionen i strukturen för en plats eller i en community-platsmall.
>
>Alla andra funktioner, till exempel [sidfunktionen](#page-function), måste inkluderas och visas först.

Med gruppfunktionen kan communitymedlemmar skapa undergrupper på communitywebbplatsen i publiceringsmiljön.

Beroende på [inställningarna](sites-console.md#groupmanagement) när funktionen Grupper ingår i en [community-webbplatsmall](sites.md), kan grupperna vara offentliga eller privata och en eller flera community-gruppmallar kan konfigureras för att tillhandahålla ett urval av mallar när communitygruppen faktiskt skapas (t.ex. från publiceringsmiljön). En [community-gruppmall](tools-groups.md) anger vilka communityfunktioner som skapas för gruppsidorna, till exempel forum och kalendrar.

När en community-grupp skapas skapas en medlemsgrupp dynamiskt för den nya gruppen, som medlemmar kan tilldelas eller ansluta till. Mer information finns i [Hantera användare och användargrupper](users.md).

Från och med Communities [feature pack 1](deploy-communities.md#latestfeaturepack) skapas communitygrupper i författarmiljön med [Konsolen Webbgrupper](groups.md), och kan skapas i publiceringsmiljön när den är aktiverad.

När du lägger till en mall öppnas följande dialogruta:

![chlimage_1-386](assets/chlimage_1-386.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Select Group Templates]**
En nedrullningsbar meny som gör att du kan välja mellan en eller flera aktiverade gruppmallar som den som skapar en ny community (i publiceringsmiljön) kan välja mellan.

* **[!UICONTROL Allow Privileged Members]**
Om det här alternativet är markerat tillåter forumet endast behöriga medlemmar att publicera ämnen genom att tillåta val av en  [behörig medlemssäkerhetsgrupp](users.md#privileged-members-group). Om det inte är markerat kan alla community-medlemmar publicera. Standard är avmarkerat.

* **[!UICONTROL Allow Publish Creation]**
Om det här alternativet är markerat kan behöriga communitymedlemmar skapa en grupp i publiceringsmiljön. Om alternativet inte är markerat kan nya grupper (undergrupper) bara skapas i författarmiljön från gruppkonsolen för Communities.

   Standardvärdet är `checked`.

### Ideationsfunktion {#ideation-function}

Idéfunktionen är en sida med en [Ideation-komponent](ideation-feature.md).

När du lägger till en mall öppnas följande dialogruta, som anger standardnamn för titel och URL samt standardvisningsinställningar för mallen:

![chlimage_1-387](assets/chlimage_1-387.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Allow Privileged Members]**
Om det här alternativet är markerat tillåter forumet endast behöriga medlemmar att publicera ämnen genom att tillåta val av en  [behörig medlemssäkerhetsgrupp](users.md#privileged-members-group). Om det inte är markerat kan alla community-medlemmar publicera. Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om alternativet är markerat innehåller idén möjligheten för medlemmar att överföra filer. Standard är markerat.

* **[!UICONTROL Allow Threaded Replies]**
Om alternativet inte är markerat tillåts svar (kommentarer) på ett ämne, men det är inte tillåtet att svara på kommentarer. Standard är markerat.

* **[!UICONTROL Allow Featured Content]**
Om du markerar det här alternativet kan idén identifieras som  [aktuellt innehåll](featured.md). Standard är markerat.

### Ledarpanelsfunktion {#leaderboard-function}

Ledpanelsfunktionen är en sida med en [Leaderboard-komponent](enabling-leaderboard.md).

**OBS**: För att komponenten Leaderboard ska kunna konfigureras ytterligare  ** när en community-webbplats har skapats från en community-mall som innehåller funktionen Ledarpanel. Leaderboard-komponentens [regler](enabling-leaderboard.md#rules-tab) måste anges, vilket beror på konfigurationen av [poängsättning och badges](implementing-scoring.md) för communityplatsen.

När du lägger till en mall öppnas följande dialogruta, som anger standardnamn för titel och URL samt standardvisningsinställningar för mallen:

![chlimage_1-388](assets/chlimage_1-388.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Display Badge]**
Om du markerar det här alternativet inkluderas en kolumn för ikoner för emblem i rankningspanelen.

   Standard är avmarkerat.

* **[!UICONTROL Display Badge Name]**
Om du markerar det här alternativet inkluderas en kolumn för märkordsnamnet i resultatlistan.

   Standard är avmarkerat.

* **[!UICONTROL Display Avatar]**
Om det här alternativet är markerat inkluderas medlemmens avatarbild i ledningsgruppen bredvid namnlänken till medlemsprofilen.

   Standard är avmarkerat.

### Sidfunktion {#page-function}

Sidfunktionen lägger till en tom sida på communitywebbplatsen som den är kopplad till funktionerna på communitywebbplatsen: inloggning, meny, meddelanden, meddelanden, teman och branding. Innehåll kan läggas till på sidan med [AEM standardredigeringsläge](../../help/sites-authoring/editing-content.md).

När du lägger till en mall är den enda konfigurationen för [titel- och URL-inställningarna](#title-and-url-settings).

### QnA-funktion {#qna-function}

QnA-funktionen är en sida med en [QnA-komponent](working-with-qna.md) som är konfigurerad för taggning, filöverföringar, följda medlemmar för självredigering, röstning och moderering.

När konfigurationen läggs till i en mall tillåts begränsningar för behöriga medlemmar:

![chlimage_1-389](assets/chlimage_1-389.png)

* Se [Titel- och URL-inställningar](#title-and-url-settings)
* **[!UICONTROL Allow Pinning]**
Om det här alternativet är markerat kan ämnessvar fästas i början av kommentarlistan. Standard är markerat.

* **[!UICONTROL Allow Privileged Members]**
Om alternativet är markerat tillåter QnA-forumet endast behöriga medlemmar att ställa frågor genom att tillåta val av en  [privilegierad medlemsgrupp](users.md#privileged-members-group). Om det inte är markerat kan alla community-medlemmar publicera. Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om det här alternativet är markerat innehåller QnA-forumet möjlighet för medlemmar att överföra filer. Standard är markerat.

* **[!UICONTROL Allow Threaded Replies]**
Om det inte är markerat tillåter QnA-forumet att det finns kommentarer (svar) på en publicerad fråga, men svar på svar tillåts inte. Standard är markerat.

* **[!UICONTROL Allow Featured Content]**
Om du markerar det här alternativet kan idén identifieras som  [aktuellt innehåll](featured.md). Standard är markerat.

## Skapa communityfunktion {#create-community-function}

Du kan skapa en communityfunktion genom att välja ikonen `Create Community Function` längst upp i användarfunktionskonsolen. Flera funktioner som är baserade på samma AEM kan skapas och sedan anpassas unikt genom att du öppnar i redigeringsläget.

![chlimage_1-390](assets/chlimage_1-390.png)

### Community-funktionsnamn {#community-function-name}

![chlimage_1-391](assets/chlimage_1-391.png)

På panelen Community Function Name konfigureras ett namn, en beskrivning och om funktionen är aktiverad eller inaktiverad:

* **[!UICONTROL Community Function Name]**
Det funktionsnamn som används för visning och lagring

* **[!UICONTROL Community Function Description]**
Funktionsbeskrivningen för visning

* **[!UICONTROL Disabled/Enabled]**
En växlingsväxling som styr om funktionen kan refereras

### AEM blå {#aem-blueprint}

![chlimage_1-392](assets/chlimage_1-392.png)

På panelen `AEM Blueprint` är det möjligt att välja den plan som är den underliggande implementeringen av communityfunktionen.

Community-funktionen är en liten webbplats som består av en eller flera sidor, färdiga för att ingå i en community-webbplats, inklusive inloggning, användarprofiler, meddelanden, meddelanden, webbplatsmeny, söknings-, teman- och varumärkesfunktioner. När funktionen har skapats är det möjligt att [öppna funktionen](#open-community-function) i redigeringsläget för författare och anpassa sid- och/eller komponentinställningarna.

Eftersom communityfunktionen är implementerad som en [live-kopia](../../help/sites-administering/msm.md#live-copies) av en [plan](../../help/sites-administering/msm-livecopy.md#creatingablueprint), är det möjligt att göra ändringar i en funktion som påverkar alla communitywebbplatssidor som skapats från [communitywebbplatsmallen](sites.md) eller [communitygruppsmallen](tools-groups.md) som innehåller funktionen. Det går också att ta bort kopplingen mellan en sida och dess överordnade plan för att göra ändringar på sidnivå.

Se även [Multi Site Manager](../../help/sites-administering/msm.md).

### Miniatyrbild {#thumbnail}

![chlimage_1-393](assets/chlimage_1-393.png)

På miniatyrpanelen kan en bild överföras för visning i [Community Function-konsolen](#community-functions-console).

## Öppna communityfunktion {#open-community-function}

![chlimage_1-394](assets/chlimage_1-394.png)

Välj ikonen `Open Community Function` för att öppna redigeringsläget för författare för redigering av sidinnehållet och ändring av konfigurationen av funktionskomponenterna.

### Konfigurerar komponenter {#configuring-components}

En communityfunktion implementeras som en Live-kopia av en AEM, som beskrivs i [Multi Site Manager](../../help/sites-administering/msm.md).

Det går inte bara att skapa sidinnehåll utan även att konfigurera komponenter.

Om du konfigurerar en komponent på en sida i en skapad community-webbplats kan det vara nödvändigt att avbryta [arv](../../help/sites-administering/msm-livecopy.md#changing-live-copy-content) för att konfigurera komponenten. Arv bör återupprättas när konfigurationen slutförs.

Mer konfigurationsinformation finns på [Webbgruppskomponenter](author-communities.md) för författare.

## Redigera communityfunktion {#edit-community-function}

![chlimage_1-395](assets/chlimage_1-395.png)

Välj ikonen `Edit Community Function` om du vill redigera funktionens egenskaper med samma paneler som [när du skapar en community-funktion](#create-community-function), inklusive att aktivera eller inaktivera funktionen.
