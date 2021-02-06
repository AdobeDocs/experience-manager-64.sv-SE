---
title: Konsolen Webbplatser
seo-title: Konsolen Webbplatser
description: Åtkomst till konsolen Communities Sites
seo-description: Åtkomst till konsolen Communities Sites
uuid: 85017055-b8af-4eeb-a8ab-1cbbba0f5a6a
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 5ac2fcef-05b8-46f7-9a15-997cdd79a3db
translation-type: tm+mt
source-git-commit: f4cdd3d5020b917676fe8715d4e21e98f3a096b4
workflow-type: tm+mt
source-wordcount: '3127'
ht-degree: 0%

---


# Webbplatskonsol för webbgrupper {#communities-sites-console}

Konsolen Communities Sites ger åtkomst till:

* Skapa webbplats
* Webbplatsredigering
* Platshantering
* [Skapa och redigera kapslade grupper](groups.md)  (undergrupper)

Se [Komma igång med AEM Communities](getting-started.md) om du vill veta hur snabbt en community kan skapas i redigeringsmiljön, samt hur du skapar communitygrupper från författaren och publiceringsmiljöer.

>[!NOTE]
>
>Huvudwebbgruppsmenyerna för att skapa [communitywebbplatser](sites-console.md), [mallar för communitywebbplatser](sites.md), [mallar för communitygrupper](tools-groups.md) och [communityfunktioner](functions.md) är endast avsedda att användas i författarmiljön.

## Förutsättningar {#prerequisites}

Innan du skapar en community-webbplats är det *obligatoriskt* att:

* Kontrollera att en eller flera publiceringsinstanser körs
* Aktivera [tunneltjänsten](deploy-communities.md#tunnel-service-on-author) för att hantera medlemmar och medlemsgrupper
* Identifiera [primär utgivare](deploy-communities.md#primary-publisher)
* [Konfigurera ](deploy-communities.md#replication-agents-on-author) replikering när den primära utgivarporten inte är standard (4503)

Det bästa sättet att se till att webbplatsen är förberedd för många funktioner är att utföra följande steg:

* Installera [det senaste funktionspaketet](deploy-communities.md#latestfeaturepack)
* Aktivera [Adobe Analytics](analytics.md) för AEM Communities
* Konfigurera [e-post](email.md)
* Identifiera [communityadministratörer](users.md#creating-community-members)
* [Aktivera OAuth-](social-login.md#adobe-granite-oauth-authentication-handler) hanterare för social inloggning

## Åtkomst till webbgruppskonsolen {#accessing-communities-sites-console}

För att nå konsolen Webbplatser i författarmiljön:

* Från global navigering: **[!UICONTROL Communities > Sites]**

Konsolen Communities Sites visar alla befintliga communityplatser. Från den här konsolen kan communitywebbplatser skapas, redigeras, hanteras och tas bort.

Om du vill skapa en ny community-webbplats väljer du ikonen **Skapa**.

Om du vill få åtkomst till en befintlig communitywebbplats och skapa, ändra, publicera, exportera eller lägga till en kapslad grupp, markerar du platsens mappikon.

Följande bild visar till exempel huvudkonsolen Webbplatser i Communities som visar mapparna för två communityplatser: [aktivera](getting-started-enablement.md) och [engagera](getting-started.md):

![chlimage_1-448](assets/chlimage_1-448.png)

## Skapa webbplats {#site-creation}

Konsolen för att skapa webbplatser innehåller ett stegvis tillvägagångssätt för att samla ihop funktioner på webbplatsen baserat på en vald [mall för communityplats](sites.md) och inställningar.

Varje webbplats som skapas innehåller en inloggningsfunktion eftersom besökarna måste logga in innan de kan publicera innehåll, skicka meddelanden eller delta i en grupp. Andra funktioner som ingår är användarprofiler, meddelanden, meddelanden, webbplatsmenyer, sökning, teman och varumärken.

Processen startas genom att du väljer knappen `Create` längst upp i webbgruppskonsolen.

Skapandeprocessen är en serie steg som presenteras som paneler med en uppsättning funktioner som ska konfigureras (presenteras som underpaneler). Det går att gå vidare till **Nästa**-steget eller **Tillbaka** till föregående steg innan platsen implementeras i det sista steget.

### Steg 1: Platsmall {#step-site-template}

![newsitetemplate](assets/newsitetemplate.png)

På panelen Platsmall anges titel, beskrivning, platsrot, grundspråk, namn och platsmall:

* **[!UICONTROL Community Site Title]**: En visningsrubrik för webbplatsen.

   Titeln visas på den publicerade webbplatsen samt i användargränssnittet för webbplatsadministratörer.

* **[!UICONTROL Community Site Description]**: En beskrivning av platsen.

   Beskrivningen visas inte på den publicerade webbplatsen.

* **[!UICONTROL Community Site Root]**: Rotsökvägen till platsen.

   Standardroten är `/content/sites`, men roten kan flyttas till valfri plats på webbplatsen.

* **[!UICONTROL Community Site Base Language]**: (lämnas orört för ett enda språk: På engelska) använder du listrutan för att välja ett  *eller* flera språk bland de tillgängliga språken - tyska, italienska, franska, japanska, spanska, portugisiska (Brasilien), kinesiska (traditionell) och kinesiska (förenklad). En communityplats skapas för varje språk som läggs till och finns i samma webbplatsmapp enligt den bästa praxis som beskrivs i [Översätta innehåll för flerspråkiga platser](../../help/sites-administering/translation.md). Rotsidan för varje webbplats kommer att innehålla en underordnad sida med språkkoden för ett av de valda språken, till exempel &quot;en&quot; för engelska eller &quot;fr&quot; för franska.

* **[!UICONTROL Community Site Name]**: Namnet på webbplatsens rotsida som visas i URL:en

   * Dubbelkontrollera namnet eftersom det inte är lätt att ändra efter att webbplatsen har skapats
   * Bas-URL ( `https://*server:port/site root/site name*)`) visas under `Community Site Name`
   * Ange en giltig URL genom att lägga till en baskod + &quot;.html&quot;

      *Till exempel*, `http://localhost:4502/content/sites/mysight/en.html`

* **[!UICONTROL Community Site Template]** meny: Använd listrutan för att välja en tillgänglig mall för  [communitywebbplats](tools.md).

Välj **[!UICONTROL Next]**

### Steg 2: Design {#step-design}

Designpanelen innehåller två underpaneler för att välja tema och varumärkesbanderoll:

#### TEMA FÖR GEMENSKAPENS WEBBPLATS {#community-site-theme}

![sitetheme-1](assets/sitetheme-1.png)

Ramverket använder [Twitter Bootstrap](https://twitterbootstrap.org/) för att ge webbplatsen en responsiv, flexibel design. Ett av de många förinlästa Bootstrap-temana kan väljas för att formatera den valda communitywebbplatsmallen, eller så kan ett Bootstrap-tema överföras.

När du väljer det här alternativet överlagras temat med en ogenomskinlig blå bockmarkering.

När communitywebbplatsen har publicerats går det att [redigera egenskaperna](#modifying-site-properties) och välja ett annat tema.

#### GEMENSKAPENS WEBBPLATSVARNING {#community-site-branding}

![chlimage_1-449](assets/chlimage_1-449.png)

Webbplatsmärkning är en bild som visas som en rubrik högst upp på varje sida.

Bilden bör storleksändras så att den blir lika bred som den förväntade visningen av sidan i webbläsaren och 120 pixlar hög.

Tänk på följande när du skapar eller markerar en bild:

* Bildens höjd beskärs till 120 pixlar från bildens övre kant
* Bilden är fäst vid webbläsarfönstrets vänstra kant
* Det finns ingen storleksändring av bilden, så att när bildbredden är ...

   * Bilden upprepas vågrätt under webbläsarens bredd
   * Bilden blir större än webbläsarens bredd och ser ut att vara beskuren

Välj **[!UICONTROL Next]**.

### Steg 3: Inställningar {#step-settings}

Panelen Inställningar innehåller flera underpaneler med funktioner som ska konfigureras innan du går till det sista steget för att skapa webbplatsen.

* [ANVÄNDARHANTERING](#user-management)
* [TAGGNING](#tagging)
* [ROLLER](#roles)
* [MODERATION](#moderation)
* [ANALYS](#analytics)
* [ÖVERSÄTTNING](#translation)
* [AKTIVERING](#enablement)

>[!NOTE]
>
>**Aktivera tunneltjänsten**
>
>Flera av underpanelerna Inställningar tillåter tilldelning av en betrodd medlem till måttlig användargenererad kod, hantera grupper eller vara kontakter för aktiveringsresurser i publiceringsmiljön.
>
>Konventionen används för att publiceringssidan [användare och användargrupper](users.md) (medlemmar och medlemsgrupper) inte ska dupliceras i författarmiljön.
>
>När du skapar en community-webbplats i författarmiljön och tilldelar betrodda medlemmar till olika roller måste du därför hämta medlemsdata från publiceringsmiljön.
>
>Detta uppnås genom att aktivera ` [AEM Communities Publish Tunnel Service](deploy-communities.md#tunnel-service-on-author)`för författarmiljön.

#### ANVÄNDARHANTERING {#user-management}

![createsitesettings-1](assets/createsitesettings-1.png)

>[!NOTE]
>
>Vi rekommenderar att [aktiveringscommunitysajter](overview.md#enablement-community) är privata (kontakta din kontorepresentant för mer information).
>
>En communitywebbplats är privat när anonyma besökare på webbplatsen nekas åtkomst, inte får registrera sig själv och inte får använda social inloggning.

* **[!UICONTROL Allow User Registration]**

   Om det här alternativet är markerat kan besökarna bli communitymedlemmar genom självregistrering.

   Om alternativet inte är markerat är communitywebbplatsen *begränsad* och webbplatsbesökarna måste tilldelas medlemsgruppen för communitywebbplatsen, göra en begäran eller få en inbjudan via e-post. Om alternativet inte är markerat bör anonym åtkomst inte tillåtas.

   Avmarkera om det finns en *privat* community-webbplats. Standard är markerat.

* **[!UICONTROL Allow Anonymous Access]**

   Om det här alternativet är markerat är communitywebbplatsen *öppen* och alla besökare kan komma åt webbplatsen.

   Om alternativet inte är markerat kan bara inloggade medlemmar få åtkomst till webbplatsen.

   Avmarkera om det finns en *privat* community-webbplats. Standard är markerat.

* **[!UICONTROL Allow Messaging]**

   Om det här alternativet är markerat kan medlemmarna skicka meddelanden till varandra och till gruppen på communitywebbplatsen.

   Om alternativet inte är markerat är meddelanden inte konfigurerade för communityn.

   Standard är avmarkerat.

* **[!UICONTROL Allow Social Logins: Facebook]**

   Om det här alternativet är markerat kan webbplatsbesökare logga in med sina Facebook-kontouppgifter. Den valda [Facebook-molnkonfigurationen](social-login.md#create-a-facebook-connect-cloud-service) bör konfigureras att lägga till användare i medlemsgruppen för communitywebbplatsen när communitywebbplatsen har skapats.

   Om alternativet inte är markerat visas ingen Facebook-inloggning.

   Låt vara omarkerat för en *privat*-communitywebbplats. Standard är avmarkerat.

* **[!UICONTROL Allow Social Logins: Twitter]**

   Om det här alternativet är markerat tillåter du webbplatsbesökare att logga in med sina Twitter-kontouppgifter. Den valda [Twitter-molnkonfigurationen](social-login.md#create-a-twitter-connect-cloud-service) bör konfigureras att lägga till användare i medlemsgruppen för communitywebbplatsen när communitywebbplatsen har skapats.

   Om alternativet inte är markerat visas ingen Twitter-inloggning.

   Låt vara omarkerat för en *privat*-communitywebbplats. Standard är avmarkerat.

>[!NOTE]
>
>**[!UICONTROL Allowing Social Logins]**
>
>Det kan finnas exempelkonfigurationer för Facebook och Twitter och de kan markeras, men för en [produktionsmiljö](../../help/sites-administering/production-ready.md) måste du skapa anpassade Facebook- och Twitter-program. Se [Social inloggning på Facebook och Twitter](social-login.md).

#### TAGGAR {#tagging}

![chlimage_1-450](assets/chlimage_1-450.png)

De taggar som kan användas för communityinnehåll kontrolleras genom att du väljer Taggnamnutrymmen som tidigare definierats via [taggningskonsolen](../../help/sites-administering/tags.md#tagging-console).

Om du väljer taggnamnutrymmen för communitywebbplatsen begränsas dessutom det urval som visas när du definierar kataloger och resurser. Se [Tagga aktiveringsresurser](tag-resources.md) för viktig information.

* Textruta: börja skriva för att identifiera taggar som får användas på webbplatsen

#### ROLLER {#roles}

![chlimage_1-451](assets/chlimage_1-451.png)

[rollerna för community-medlemmar](users.md) tilldelas med dessa inställningar.

Det är enkelt att hitta communitymedlemmar med hjälp av typsnittssökning.

* **[!UICONTROL Community Managers]**

   Börja skriva för att välja en eller flera community-medlemmar eller medlemsgrupper som kan hantera community-medlemmar och medlemsgrupper.

* **[!UICONTROL Community Moderators]**

   Börja skriva för att välja en eller flera communitymedlemmar eller medlemsgrupper som ska betraktas som pålitliga som moderatorer för användargenererat innehåll.

* **[!UICONTROL Community Privileged Members]**

   Börja skriva för att välja en eller flera communitymedlemmar eller medlemsgrupper som ska kunna skapa nytt innehåll när `Allow Privileged Member` har valts för en [communityfunktion](functions.md).

#### MODERATION {#moderation}

![chlimage_1-452](assets/chlimage_1-452.png)

Den globala inställningen för moderering av användargenererat innehåll (UGC) styrs av dessa inställningar. Enskilda komponenter har ytterligare inställningar för att styra modereringen.

* **[!UICONTROL Content is Premoderated]**

   Om det här alternativet är markerat visas inte publicerat communityinnehåll förrän det har godkänts av en moderator. Standard är avmarkerat. Mer information finns i [Moderating Community Content](moderate-ugc.md#premoderation).

* **[!UICONTROL Flagging threshold before content is hidden]**

   Om värdet är större än 0 måste antalet gånger ett ämne eller ett inlägg flaggas innan det döljs för den offentliga vyn. Om värdet är -1 döljs aldrig det markerade ämnet eller inlägget från den offentliga vyn. Standardvärdet är 5.

#### ANALYTIK {#analytics}

![chlimage_1-453](assets/chlimage_1-453.png)

* **[!UICONTROL Enable Analytics]**

   Endast tillgängligt när Adobe Analytics har [konfigurerats](analytics.md) för webbgruppsfunktioner.

   Standard är avmarkerat. När det här alternativet är markerat visas ytterligare en markeringsmeny:

![chlimage_1-454](assets/chlimage_1-454.png)

* **[!UICONTROL Cloud Config Framework Reference]**

   I listrutan väljer du Analytics-molntjänstramverket som är konfigurerat för den här communitywebbplatsen.

   `Communities`är ramverksexemplet från  [Analytics Configuration for Communities ](analytics.md#aem-analytics-framework-configuration) Featuresdocumentation.

#### TRANSLATION {#translation}

![chlimage_1-455](assets/chlimage_1-455.png)

* **[!UICONTROL Allow Machine Translation]**
När det här alternativet är markerat (standardinställningen är avmarkerad) aktiveras maskinöversättning för UGC på platsen. Detta påverkar inte annat innehåll, t.ex. sidinnehåll, även om webbplatsen är konfigurerad som en flerspråkig webbplats. Mer information om hur du konfigurerar en licensierad översättningstjänst för AEM Communities finns i [Translating User Generated Content](translate-ugc.md). En fullständig översikt finns i [Översätta innehåll för flerspråkiga platser](../../help/sites-administering/translation.md).

![chlimage_1-456](assets/chlimage_1-456.png)

* **[!UICONTROL Enable Machine Translation for selected languages]**

   Språken som är aktiverade för maskinöversättning är standardinställningen för den systeminställning som anges av [översättningsintegrationskonfigurationen](translate-ugc.md#translation-integration-configuration). Dessa standardinställningar kan åsidosättas för den här webbplatsen genom att standardinställningar tas bort och/eller genom att andra språk väljs i listrutan.

* **[!UICONTROL Choose translation provider]**

   Som standard är tjänsteleverantören en provtjänst som endast använder `microsoft`som exempel. Om ingen översättningstjänstleverantör är licensierad bör **Tillåt maskinöversättning** inte vara markerat.

* **[!UICONTROL Choose global shared store]**

   För en webbplats med flera språkkopior innehåller ett globalt delat arkiv en enda konversationstråd som är synlig från varje språkkopia. Detta uppnås genom att välja ett av språken som ingår som en språkkopia. Standardvärdet är *Ingen global delad lagring*.

* **[!UICONTROL Choose translation provider config]**

   Välj ett [ramverk för översättningsintegrering](../../help/sites-administering/tc-tic.md) som skapats för den licensierade översättningsprovidern.

* **Välj översättningsalternativ för communitywebbplatsen**

   * **[!UICONTROL Translate entire page]**

      Om du väljer det här alternativet översätts all UGC på en sida till sidans basspråk.

      Standardvärdet är *inte markerat*.

   * **[!UICONTROL Translate selection only]**

      Om du väljer det här alternativet visas ett översättningsalternativ intill varje inlägg som gör att enskilda inlägg kan översättas till sidans grundspråk.

      Standardvärdet är *markerat*.

* **Välj alternativ för beständighet**

   * **[!UICONTROL Translate contributions on user request and persist afterwards]**

      Om du väljer det här alternativet översätts inte innehållet förrän en begäran har gjorts. När översättningen är klar sparas översättningen i databasen.

      Standardvärdet är *inte markerat*.

   * **[!UICONTROL Don't persist translations]**

      Om du väljer det här alternativet lagras inte översättningar i databasen.

      Om det inte är markerat bevaras översättningar.

      Standardvärdet är *inte markerat*.

* **[!UICONTROL Smart Render]**
Välj en av

   * `Always show contributions in the original language` (standard)
   * `Always show contributions in user preferred language`
   * `Show contributions in user preferred language for only logged-in users`

#### AKTIVERA {#enablement}

![chlimage_1-457](assets/chlimage_1-457.png)

`ENABLEMENT`Inställningarna gäller när den valda communityplatsmallen innehåller [tilldelningsfunktionen](functions.md#assignments-function), som är tillgänglig när aktiveringsfunktionerna är licensierade och [konfigurerade](enablement.md). Referensplatsmallen som innehåller tilldelningsfunktionen är `Reference Structured Learning Site Template.`

* **[!UICONTROL Enablement Managers]**

   (obligatoriskt) Endast medlemmar i `Community Enablementmanagers`-gruppen är tillgängliga för att hantera den här aktiveringscommunityn. Aktivitetshanterare ansvarar för att tilldela medlemmar till resurser. Se även [Hantera användare och användargrupper](users.md).

* **[!UICONTROL Marketing Cloud Org Id]**

   (valfritt) ID:t för en [Video Heartbeat Analytics](analytics.md#video-heartbeat-analytics)-licens.

Välj **[!UICONTROL Next]**.

### Steg 4: Skapa webbgruppsplats {#step-create-communities-site}

Om det behövs justeringar använder du **Bakåt**-knappen för att göra dem.

När **Skapa** har valts och startats kan processen att skapa platsen inte avbrytas.

När webbplatsen har skapats:

* Det går inte att ändra URL:en (nodnamn)
* Framtida ändringar av communitywebbplatsmallen kommer inte att påverka den skapade communitywebbplatsen
* Om du inaktiverar communityplatsmallen påverkas inte den skapade communitywebbplatsen
* Det går att redigera [STRUKTUREN](#modify-structure) för en community-webbplats genom att ändra dess egenskaper

![chlimage_1-458](assets/chlimage_1-458.png)

När processen är klar visas mappen för den nya platsen i konsolen Webbplatser, där författare kan lägga till sidinnehåll eller administratören kan ändra platsens egenskaper.

![chlimage_1-459](assets/chlimage_1-459.png)

Om du vill ändra en community-plats väljer du projektmappen för den:

![siteactions-2](assets/siteactions-2.png)

När du hovrar över en webbplats med en mus eller vidrör ett platskort visas ikoner som gör att du kan [redigera webbplatsen i redigeringsläge](#authoring-site-content), [öppna webbplatsegenskaperna för ändring](#modifying-site-properties), [publicera webbplatsen](#publishing-the-site), [exportera platsen](#exporting-the-site) och [ta bort platsen](#deleting-the-site).

## Redigerar webbplatsinnehåll {#authoring-site-content}

![chlimage_1-460](assets/chlimage_1-460.png)

Innehållet i en webbplats kan redigeras med samma verktyg som andra AEM. Om du vill öppna webbplatsen för redigering väljer du ikonen `Open Site` som visas när du hovrar webbplatsen med musen. Webbplatsen öppnas på en ny flik så att konsolen Webbplatser fortfarande är tillgänglig.

![chlimage_1-461](assets/chlimage_1-461.png)

>[!NOTE]
>
>Om du inte känner till AEM kan du läsa dokumentationen om [grundläggande hantering](../../help/sites-authoring/basic-handling.md) och en [snabbguide till redigeringssidor](../../help/sites-authoring/qg-page-authoring.md).

## Ändra webbplatsegenskaper {#modifying-site-properties}

![chlimage_1-462](assets/chlimage_1-462.png)

Egenskaperna för en befintlig plats, som anges när webbplatsen skapas, kan ändras genom att du väljer ikonen `Edit Site`som visas när du hovrar webbplatsen med musen.

`Details of the following properties match the descriptions provided in the` [Site ](#site-creation) Creation.

![chlimage_1-463](assets/chlimage_1-463.png)

### Ändra grundläggande {#modify-basic}

På BASIC-panelen kan du ändra

* Rubrik för communitywebbplats
* Beskrivning av communityplats

Det går inte att ändra namnet på communityplatsen.

Om du väljer en annan mall för en community-webbplats påverkas inte en befintlig community-webbplats eftersom det inte finns någon koppling mellan mallar och webbplatser.

I stället kan [STRUKTUREN](#modify-structure) för communitywebbplatsen ändras.

### Ändra struktur {#modify-structure}

STRUKTURpanelen gör att du kan ändra den struktur som ursprungligen skapades från den valda mallen för communitywebbplatser. På panelen kan du

* Dra och släpp ytterligare [communityfunktioner](functions.md) i webbplatsstrukturen
* En instans av en communityfunktion i webbplatsstrukturen:

   * **`gear icon`**

      redigera inställningar, inklusive visningsrubrik och URL-namn&amp;stämpel;ast;

      samt [behöriga medlemsgrupper](users.md#privilegedmembersgroups)

   * **`trashcan icon`**

      ta bort (ta bort) funktioner från platsstrukturen

   * **`grid icon`**

      ändra ordningen på funktioner som visas i navigeringsfältet på den översta nivån

>[!NOTE]
>
>Du kan ändra ordningen på alla funktioner i platsstrukturen förutom funktionen längst upp. Det innebär att det inte går att ändra startsidan för communitywebbplatsen.

>[!CAUTION]
>
>Visningsrubriken kan ändras utan biverkningar, men du bör inte redigera URL-namnet för en community-funktion som tillhör en community-webbplats.
>
>Om du t.ex. byter namn på URL:en flyttas inte den befintliga UGC:n, vilket resulterar i&quot;UGC-förlust&quot;.

>[!CAUTION]
>
>Gruppfunktionen får *inte* vara *först eller den enda*-funktionen i platsstrukturen.
>
>Alla andra funktioner, till exempel [sidfunktionen](functions.md#page-function), måste inkluderas och visas först.

#### Exempel: Lägga till en katalogfunktion i en community-platsstruktur {#example-adding-a-catalog-function-to-a-community-site-structure}

![chlimage_1-464](assets/chlimage_1-464.png)

### Ändra design {#modify-design}

På designpanelen kan du använda ett nytt tema:

* [Community Site Theme](#community-site-theme)
* [Varumärkning för communitysajter](#community-site-branding)
   * Bläddra till panelens nedre del för att ändra varumärkesbilden

### Ändra inställningar {#modify-settings}

Med hjälp av inställningspanelen får du tillgång till de flesta inställningarna under underpanelerna i steg 3 för att skapa en community-webbplats:

* [Användarhantering](#user-management)
* [Taggar](#tagging)
* [Moderering](#moderation)
* [Medlemsroller](#roles)
* [Analyser](#analytics)
* [Översättning](#translation)

### Ändra miniatyrbild {#modify-thumbnail}

På panelen MINIATYRBILD kan en bild överföras för att representera webbplatsen i webbgruppskonsolen.

### Ändra aktivering {#modify-enablement}

ENABLEMENT-panelen ger åtkomst till inställningarna som anges när en community-webbplats skapas.

Se beskrivningen av [ENABLEMENT](#enablement).

## Publicera platsen {#publishing-the-site}

När en communitywebbplats har skapats eller ändrats kan du publicera (aktivera) webbplatsen genom att välja ikonen `Publish Site`, som visas när du håller muspekaren över webbplatsen.

![chlimage_1-465](assets/chlimage_1-465.png)

En indikation visas när webbplatsen har publicerats.

![chlimage_1-466](assets/chlimage_1-466.png)

### Publicera med kapslade grupper {#publishing-with-nested-groups}

När du har publicerat en community-webbplats måste du publicera varje undergrupp (kapslad grupp) som skapats med [gruppkonsolen](groups.md) individuellt.

## Exporterar platsen {#exporting-the-site}

![chlimage_1-467](assets/chlimage_1-467.png)

Välj exportikonen när du hovrar musen över webbplatsen för att skapa ett paket av communitywebbplatsen som båda lagras i [pakethanteraren](../../help/sites-administering/package-manager.md) och hämtas.\
Observera att UGC inte ingår i platspaketet.

## Tar bort platsen {#deleting-the-site}

![deleteicon-1](assets/deleteicon-1.png)

Om du vill ta bort communitywebbplatsen väljer du ikonen Ta bort plats som visas när du håller muspekaren över webbplatsen i Webbplatskonsolen. Den här åtgärden tar bort alla objekt som är associerade med platsen, till exempel UGC, användargrupper, resurser och databasposter.

## Skapade communityanvändargrupper {#created-community-user-groups}

När den nya communitywebbplatsen har publicerats skapas nya medlemsgrupper (användargrupper i publiceringsmiljön) som har rätt behörigheter för olika administrativa roller och medlemsroller.

Namnet som skapas för medlemsgrupperna innehåller *site-name* som anges i [Steg 1](#step13asitetemplate) (namnet som visas i URL:en) samt ett unikt ID för att undvika konflikter med communityplatser och grupper som har samma platsnamn för olika communityrötter.

Om namnet till exempel är &quot;engage&quot; för en webbplats med namnet &quot;Getting Started Tutorial&quot; blir användargruppen för moderatorer:

* Titel: Moderatorer för communityengagemang
* Namn: community-*engage-uid*-moderators

Observera att alla medlemmar som tilldelats roller som moderatorer eller gruppadministratörer när platsen skapas, kommer att tilldelas till rätt grupp samt till medlemsgruppen. Dessa grupper och medlemstilldelningar skapas vid publicering när den nya webbplatsen publiceras.

Mer information finns i [Hantera användare och användargrupper](users.md).

>[!NOTE]
>
>Om [Tillåt social inloggning: Facebook](#user-management) är aktiverat när användargruppen har
>
>* community-*&lt;platsnamn>*-*&lt;uid>*-medlemmar

skapas bör den använda [Facebook-molntjänsten](social-login.md#createafacebookcloudservice) konfigureras att lägga till användare i den här gruppen.

## Konfigurera för autentiseringsfel {#configure-for-authentication-error}

Som standard dirigeras en communitywebbplats om till en exempelinloggningssida när användaren anger fel inloggningsuppgifter och inte kan logga in. Denna exempelinloggning kommer inte att finnas på en [produktionsserver](../../help/sites-administering/production-ready.md).

Om du vill omdirigera korrekt, när en webbplats har konfigurerats och publicerats, slutför du de här stegen för att få autentiseringsfel att omdirigera till communitywebbplatsen:

* På varje AEM publiceringsinstans
* Första inloggningen med administratörsbehörighet
* Åtkomst till [webbkonsolen](../../help/sites-deploying/configuring-osgi.md)
   * Till exempel [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Sök efter `Adobe Granite Login Selector Authentication Handler`
* Välj ikonen `pencil`för att öppna konfigurationen för redigering
* Ange en **[!UICONTROL Login Page Mappings]** enligt följande:

   `/content/sites/<site-name>/path/to/login/page:/content/sites/<site-name>`

   till exempel:

   `/content/sites/engage/en/signin:/content/sites/engage/en`

* Välj **[!UICONTROL Save]**

![chlimage_1-468](assets/chlimage_1-468.png)

### Testa autentiseringsomdirigering {#test-authentication-redirection}

På samma AEM har publiceringsinstansen konfigurerats med en inloggningssidmappning för communitywebbplatsen:

* Bläddra till startsidan för communitywebbplatsen
   * Till exempel [http://localhost:4503/content/sites/engage/en.html](http://localhost:4503/content/sites/engage/en.html)

* Välj Logga ut
* Välj inloggning
* Ange uppenbart felaktiga inloggningsuppgifter, till exempel användarnamnet &quot;x&quot; och lösenordet &quot;x&quot;
* Inloggningssidan ska visas med felmeddelandet&quot;ogiltig inloggning&quot;

![chlimage_1-469](assets/chlimage_1-469.png)

## Åtkomst till communityplatser från huvudplatskonsolen {#accessing-community-sites-from-main-sites-console}

På den globala navigeringskonsolen finns communityplatser i mappen `Community Sites`.

Det går att komma åt en community-webbplats på det här sättet, men för administrativa uppgifter bör communitywebbplatsen nås från konsolen Webbplatser för communities.

![chlimage_1-470](assets/chlimage_1-470.png)

