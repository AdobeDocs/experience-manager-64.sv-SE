---
title: Modereringskonsol
seo-title: Modereringskonsol
description: Åtkomst till modereringskonsolen
seo-description: Åtkomst till modereringskonsolen
uuid: 920124b9-af6f-4622-adb6-b8e294c5607d
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 6c405543-e339-4916-aa0f-b61d0b798cf3
translation-type: tm+mt
source-git-commit: f78f83ef3b9373bcbee3e5179a9bbec4d9462255

---


# Modereringskonsol {#moderation-console}

I AEM Communities är det möjligt att [moderera communityinnehåll](moderate-ugc.md) både från författaren och publiceringsmiljöer av administratörer och community moderators (betrodda communitymedlemmar som utsetts till moderatorer).

Administratörer och moderatorer för communityn kan också utföra moderering [i sitt sammanhang](in-context.md) i publiceringsmiljön.

En funktion på alla [communitysajter](sites-console.md) är ett `Administration`menyalternativ som är tillgängligt för användare som loggar in med administratörsbehörighet. Via `Administration`länken får du tillgång till modereringskonsolen.

Från modereringskonsolen har administratörer och moderatorer åtkomst till allt användargenererat innehåll (UGC) som de har behörighet att moderera. Om du tillåter att flera webbplatser modereras kan du visa inlägg på alla webbplatser eller filtrera efter utvalda communityplatser.

Mer information finns i [Hantera användare och användargrupper](users.md).

Moderationskonsolen har stöd för:
* Utföra flera modereringsuppgifter samtidigt
* Söker i UGC
* Visa UGC-information
* Visa information om UGC-författare

Det är bara när du är inloggad som administratör, eller som medlem med ` [moderator permissions](in-context.md#identifyingtrustedmembers)`, som modereringsåtgärder kan utföras.

## Publiceringsmiljöåtkomst {#publish-environment-access}

Åtkomst till moderationskonsolen från en publicerad communitywebbplats sker via en administrationslänk som visas när en community-moderator är inloggad.

![publicweretail](assets/publishweretail.png)

Genom att välja administrationslänken visas modereringskonsolen:

![moderationconsole-publish](assets/moderationconsole-publish.png)

## Åtkomst till författarmiljö {#author-environment-access}

I författarmiljön kan du nå Kontrollen för moderering

* Från global navigering: **[!UICONTROL Navigation > Communities > Moderation]**

Det är bara när du är inloggad som administratör, eller som medlem med ` [moderator permissions](in-context.md#identifyingtrustedmembers)`, som modereringsåtgärder kan utföras. Det enda communityinnehåll som visas är det som den inloggade medlemmen får moderera.

>[!NOTE]
>
>UGC från publiceringsmiljön visas bara för författaren om den valda SRP implementerar en gemensam butik. Som standard är exempelvis lagringen JSRP, som inte är en gemensam butik för författare och publicering. Se [Community Content Storage](working-with-srp.md).

![moderationkonsoleförfattare](assets/moderationconsoleauthor.png)

## Användargränssnitt för modereringskonsol {#moderation-console-ui}

Bortsett från den vänstra navigeringslisten (som visas på författaren men inte vid publicering) har modereringsgränssnittet följande huvudområden:

* **[Övre navigeringsfältet](#top-navigation-bar)**
* **[Verktygsfält](#toolbar)**
* **[Innehållsområde](#content-area)**

### Övre navigeringsfält {#top-navigation-bar}

Det övre navigeringsfältet är konstant för alla konsoler. Mer information finns i [Grundläggande hantering](../../help/sites-authoring/basic-handling.md).

### Toolbar {#toolbar}

Verktygsfältet, som finns under det övre navigeringsfältet, har följande växlingsknapp till vänster:

* [Filterremsa](moderation.md#filter-rail) öppnar en räl där du kan välja vilka egenskaper som innehållet ska filtreras efter.

Verktygsfältet, som finns under det övre navigeringsfältet, har följande växlingsknapp till vänster:

![växlarSwitch](assets/toggleswitch.png)

[Filterspår](moderation.md#filter-rail)\
Öppnar ett spår när du väljer Sök, vilket gör att du kan välja vilka egenskaper som innehållet ska filtreras efter.

![filterrail](assets/filterrail.png)

### Innehållsområde {#content-area}

Innehållsområdet innehåller information för publicerad UGC:

* UGC har bokförts
* Medlemsnamn
* Medlem avatar
* Postens plats
* När den bokförs
* Antal svar i posten
* [Sentiment](moderate-ugc.md#sentiment) som är associerad med posten
* Om det godkänns visas en bock
* Om det finns en bifogad fil visas ett gem

>[!NOTE]
>
>Innehållsområdet har en *oändlig rullning*, vilket innebär att du kan fortsätta rulla tills du har nått slutet av innehållet. Verktygsfältet ligger kvar på en fast, synlig plats ovanför innehållsområdet även när du bläddrar.

### Filterspår {#filter-rail}

![chlimage_1-472](assets/chlimage_1-472.png)

Ikonen för sidopanelen öppnar filterlisten. Filtercirkeln, som visas till vänster om innehållsområdet, innehåller olika filter, som båda har en omedelbar effekt på den refererade UGC:n som visas i innehållsområdet.

Filtren inom varje kategori är **** ELLERed tillsammans och filtren i olika kategorier **** OCH sammanfogas.

Om du till exempel markerar både **Fråga** och **Svar** visas innehåll som antingen är en **fråga** *eller* ett **svar**.

Om du markerar **Fråga** och **Väntande**, visas bara innehåll som är en **fråga** och som **väntar**.

>[!NOTE]
>
>Moderatorer för communityn kan skapa bokmärken för fördefinierade filter i modereringskonsolens användargränssnitt. När dessa filter läggs till i slutet av URL:en (som frågesträngsparametrar) kan moderatorerna senare gå tillbaka till bokmärkesfiltren och även dela dessa länkar.

![sökningsikon](assets/searchicon.png)

När filterlisten är öppen växlar ikonen Sök och sidopanelen stängs. Om du vill stänga filterfältet och bara visa det innehåll som användaren skapat klickar du på ikonen Sök och väljer alternativet Endast innehåll.

#### Innehållsbana {#content-path}

Innehållssökväg begränsar den UGC-referens som visas för inlägg i den angivna innehållsdatabasen.

![content-path](assets/content-path.png)

#### Textsökning {#text-search}

Textsökning begränsar den refererade UGC som visas till inlägg som innehåller den angivna texten.

![chlimage_1-473](assets/chlimage_1-473.png)

#### Plats {#site}

Webbplatsen begränsar den refererade UGC som visas till inlägg på valda communitywebbplatser. Om inga platser är markerade visas alla referenser till UGC.

![chlimage_1-474](assets/chlimage_1-474.png)

>[!NOTE]
>
>När en administratör öppnar konsolen för massmoderering visas alla referenser till UGC, även webbplatser som inte skapats med guiden [Skapa](sites-console.md)plats, till exempel Geometrixxxexemplen.
>
>När gruppmodereringskonsolen öppnas vid publicering av en betrodd community-medlem visas endast referenser till UGC som skapats för communitywebbplatser som medlemmen har behörighet att moderera och kan filtreras med platsfiltret.

#### Innehållstyp {#content-type}

Innehållstyp begränsar den refererade UGC-enheten som visas till inlägg av den valda resurstypen. Du kan välja en eller flera av följande typer. Alla typer visas om inget är markerat.

* **Kommentar**
* **Forum**
* **Forum Reply**
* **QnA-fråga**
* **QnA-svar**
* **Bloggartikel**
* **Bloggkommentar**
* **Kalenderhändelse**
* **Kalenderkommentar**
* **Filbiblioteksmapp**
* **Filbiblioteksdokument**
* **Idea**
* **Idékommentar**

![innehållstyper](assets/content-types.png)

#### Ytterligare innehållstyper {#additional-content-types}

Så här lägger du till ytterligare resurser att filtrera:

* På en författarinstans
* Logga in som administratör
* Öppna [webbkonsol](http://localhost:4502/system/console/configMgr)
* Sök `AEM Communities Moderation Dashboard Filters`
* Välj konfigurationen som ska öppnas i redigeringsläge
* Ange den ResourceType för en komponent som ska filtreras
   * Om du till exempel vill filtrera på de medföljande röstkomponenterna anger du:\
      `Voting=social/tally/components/hbs/voting`

![chlimage_1-475](assets/chlimage_1-475.png)

* Välj Spara
* Uppdatera webbgrupperna - modereringskonsolen

Resultatet är ett nytt valbart filter för `Voting`under `Content Type` filtergruppen.

När det filtret är markerat visar kontrollpanelens innehåll UGC som matchar någon av de ResourceTypes som har angetts.

#### Status {#status}

Status begränsar den refererade UGC:n som visas till inlägg med den valda statusen, som kan vara en eller flera av Väntande, Godkänd, Nekad eller Stängd, samt Utkast eller Schemalagt för Blog-artiklar samt Svarat eller Inte besvarat för QnA-frågor. Om ingen är markerad visas alla.

>[!NOTE]
>
>Om du bara väljer statusen Inte besvarat visas allt innehåll (för alla innehållstyper) utom de besvarade frågorna. Det beror på att den egenskap som ansvarar för den besvarade frågan inte finns för frågor som inte besvarats och annat innehåll som forumämne, bloggartikel eller kommentarer.

![status](assets/statuses.png)

#### Flaggning {#flagging}

Flaggning begränsar det refererade användargenererat innehåll som visas till inlägg som är flaggade eller dolda.

När ett innehåll har flaggats förblir det flaggat tills du bryter flaggan för det enskilda innehållet genom att markera knappen **[!UICONTROL Flagga]** en gång till. Observera att det inte finns några flaggningsnivåer, som important eller följup.

![chlimage_1-476](assets/chlimage_1-476.png)

#### Medlemmar {#members}

Medlemmar begränsar den refererade UGC som visas för UGC som har bokförts av det angivna medlemsnamnet.

![chlimage_1-477](assets/chlimage_1-477.png)

#### Anslaget senast {#posted-in-the-last}

Bokförd i sista begränsa hur den refererade UGC:n visas för inlägg gjorda i sista timmen, dagen, veckan, månaden eller året.

![chlimage_1-478](assets/chlimage_1-478.png)

#### Sentiment {#sentiment}

[Sentiment](moderate-ugc.md#sentiment) begränsar den refererade UGC som visas till inlägg med ett känslomässigt värde som är antingen positivt, negativt eller neutralt.

![chlimage_1-479](assets/chlimage_1-479.png)

## Modereringsåtgärder {#moderation-actions}

[Modereringsåtgärder](moderate-ugc.md#moderation-actions) kan utföras på en eller flera markeringar som gjorts i innehållsområdet eller när du visar innehållsdetaljer.

Om du vill moderera inläggen i stor skala klickar du på ikonen Markera ( ![markering](assets/selecticon.png)) i innehållsområdet på ett inlägg, som visas när du håller muspekaren över det (skrivbordet) eller trycker och håller ett finger på posten (mobilen). Genom att göra detta aktiverar du flervalsläget och kan nu välja de efterföljande inlägg som ska gruppmodereras genom att klicka på dem. Använd de knappar som visas i verktygsfältet för att utföra modereringsåtgärder för de valda inläggen. Alla åtgärder uppmanas att bekräfta.

Om du vill ändra ett inlägg i innehållsområdet till en viss nivå håller du pekaren över det med musen (skrivbordet) eller trycker och håller ned ett finger på posten (mobilen) så att knapparna visas på posten. När du arbetar med en enskild innehållsdetalj uppmanas du bara att bekräfta borttagningsåtgärden.

### Moderering av flera inlägg {#moderating-multiple-posts}

Ange läget för gruppval genom att klicka på `Select` ikonen för ett inlägg:

![select-icon](assets/select-icon.png)

Om du vill avsluta gruppmarkeringsläget väljer du ikonen Avbryt (x) i verktygsfältet:

Modereringsåtgärderna som kan utföras på flera inlägg är:

* Neka
* Ta bort
* Stäng/öppna inlägg igen

Ikonerna som tillåter dessa åtgärder visas bara i verktygsfältet när flera inlägg är markerade.

![bulkmoderat](assets/bulkmoderate.png)

### Moderera ett enstaka inlägg {#moderating-a-single-post}

I läget för en markering är det möjligt att

* Visa användarinformation genom att välja användarens namn
* Visa inlägget i sitt sammanhang genom att markera länken till inlägget
* [Svara](#reply)
* [Tillåt](#allow)
* [Neka](#deny)
* [Ta bort](#delete)
* [Stäng](#close)
* Visa [modereringshistorik](#moderation-history)
* [Visa detaljer](#viewdetails)

Visas på kortvyn ovanför ikonerna för modereringsåtgärder är texten i inlägget och nedan är data som indikerar

* Om har svar, och om så är fallet, föregås av antalet svar
* Om har flaggats
* Om har godkänts
* När användargenererat innehåll bokfördes

![singleselectmode](assets/singleselectmode.png)

#### Svara {#reply}

![chlimage_1-480](assets/chlimage_1-480.png)

När du arbetar med ett enstaka inlägg visas en svarsikon om UGC-typen stöder svar och är konfigurerad för att tillåta svar.

#### Tillåt {#allow}

![chlimage_1-481](assets/chlimage_1-481.png)

När du arbetar med ett enstaka inlägg visas ikonen Tillåt när inlägget antingen har flaggats eller nekats. Om du väljer Tillåt kommer alla flaggor att tas bort.

#### Neka {#deny}

![chlimage_1-482](assets/chlimage_1-482.png)

Modereringsåtgärden **Neka** är bara tillgänglig för innehåll som är modererat och inte visas på omodererat innehåll förutom i flervalsläge.

Innehåll som inte är modererat godkänns alltid.

Innehåll som modereras till en början försätts i ett väntande läge och kan senare ändras för att godkännas eller nekas.

Innehåll som lämnar det väntande läget kan aldrig återgå till ett väntande läge. Innehåll som markerats som godkänt eller nekat kan när som helst ändras till ett annat läge.

#### Ta bort {#delete}

![chlimage_1-483](assets/chlimage_1-483.png)

I envalsläge eller gruppläge kan du markera objekt och ta bort dem. Borttagningsåtgärden resulterar i en bekräftelsedialogruta. När de har tagits bort försvinner dessa objekt omedelbart från innehållsområdet. **När UGC har tagits bort tas den bort permanent från databasen och kan inte hämtas senare.**

#### Stäng {#close}

![chlimage_1-484](assets/chlimage_1-484.png)

När du arbetar med ett enstaka inlägg visas en stängningsikon om UGC-typen stöder möjligheten att förhindra fler inlägg för den resursen.

#### Modereringshistorik {#moderation-history}

![chlimage_1-485](assets/chlimage_1-485.png)

När du arbetar med ett enstaka inlägg visas en ikon för historik för moderering när du hovrar över det. Om du väljer ikonen visas en ruta med en historik över åtgärder som har vidtagits för UGC-inlägget.

Om du vill återgå till visning av flera UGC-inlägg i innehållsområdet markerar du X:et i det övre högra hörnet av rutan med vydetaljer.

Exempel:

![chlimage_1-486](assets/chlimage_1-486.png)

#### Visa detaljer {#view-detail}

![chlimage_1-487](assets/chlimage_1-487.png)

När du arbetar med ett enstaka inlägg kan du visa mer information genom att öppna UGC i detaljerat läge.

Om du vill göra det håller du pekaren över inlägget för att visa `View Detail` ikonen och markerar det. Då visas en panel med mer information om inlägget.

Om du vill återgå till visning av flera UGC-inlägg i innehållsområdet markerar du X:et i det övre högra hörnet av rutan med vydetaljer.

Exempel:

![chlimage_1-488](assets/chlimage_1-488.png)

