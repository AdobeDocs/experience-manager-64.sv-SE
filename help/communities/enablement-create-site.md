---
title: Skapa en ny communitywebbplats för aktivering
seo-title: Author a New Community Site for Enablement
description: Skapa en communitywebbplats för aktivering
seo-description: Create a community site for enablement
uuid: 6822cc99-e272-4661-bddf-aa0800b88c41
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: aff8b79f-dd4e-486e-9d59-5d09dfe34f27
exl-id: 5b16c775-3bd0-4a55-ba9e-f326224e8bae
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1720'
ht-degree: 2%

---

# Skapa en ny communitywebbplats för aktivering {#author-a-new-community-site-for-enablement}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Skapa communitywebbplats {#create-community-site}

[Skapa communitysajter](sites-console.md) använder en guide som vägleder dig genom de olika stegen för att skapa en community-webbplats. Det går att gå vidare till `Next`steg eller `Back`till föregående steg innan webbplatsen implementeras i det sista steget.

Så här kommer du igång med att skapa en ny community-webbplats:

Använda [författarinstans](http://localhost:4502/)

* Logga in med administratörsbehörighet
* Navigera till **[!UICONTROL Communities > Sites]**

* Välj **[!UICONTROL Create]**

### Steg 1: Webbplatsmall {#step-site-template}

![enablementsitettemplate](assets/enablementsitetemplate.png)

På **Webbplatsmall** anger du en titel, beskrivning, namnet på URL:en och väljer en mall för en community-webbplats, till exempel:

* **Rubrik för communitywebbplats**: `Enablement Tutorial`

* **Beskrivning av communityplats**: `A site for enabling the community to learn.`

* **Community-platsrot**: (lämna tomt för standardroten `/content/sites`)

* **Molnkonfigurationer**: (lämna tomt om ingen molnkonfiguration har angetts) ange sökvägen till de angivna molnkonfigurationerna.
* **Bas-språk för communitywebbplats**: (lämnas orört för ett enda språk: Engelska) använd listrutan för att välja en *eller mer* basspråk från tillgängliga språk - tyska, italienska, franska, japanska, spanska, portugisiska (Brasilien), kinesiska (traditionell) och kinesiska (förenklad). En community-webbplats skapas för varje språk som läggs till och finns i samma webbplatsmapp enligt de rutiner som beskrivs i [Översätta innehåll för flerspråkiga webbplatser](../../help/sites-administering/translation.md). Rotsidan för varje webbplats kommer att innehålla en underordnad sida med språkkoden för ett av de valda språken, till exempel &quot;en&quot; för engelska eller &quot;fr&quot; för franska.

* **[!UICONTROL Community Site Name]**: `enable`

   * den inledande URL:en visas under namnet på communityplatsen
   * för en giltig URL, lägg till en baskod + &quot;.html&quot;

      *till exempel*, http://localhost:4502/content/sites/ `enable/en.html`

* **[!UICONTROL Reference Site Template]**: dra nedåt för att välja `Reference Structured Learning Site Template`

Välj **[!UICONTROL Next]**

### Steg 2: Design {#step-design}

Designsteget presenteras i två avsnitt där du kan välja tema och varumärkesbanderoll:

#### TEMA PÅ GEMENSKAPENS WEBBPLATS {#community-site-theme}

Välj det format som du vill använda på mallen. När du väljer det här alternativet överlagras temat med en bockmarkering.

![enablementsitetema](assets/enablementsitetheme.png)

#### GEMENSKAPENS WEBBPLATSHANTERING {#community-site-branding}

(valfritt) Ladda upp en banderollbild som ska visas på webbplatsens sidor. Banderollen är fäst vid webbläsarens vänstra kant, mellan communitywebbplatsens sidhuvud och meny (navigeringslänkar). Banderollhöjden beskärs till 120 pixlar. Banderollens storlek ändras inte så att den passar webbläsarens bredd och höjden 120 pixlar.

![chlimage_1-284](assets/chlimage_1-284.png) ![chlimage_1](assets/chlimage_1.jpeg)

Välj **[!UICONTROL Next]**.

### Steg 3: Inställningar {#step-settings}

I steget Inställningar, innan du väljer `Next`, observera att det finns sju avsnitt som ger åtkomst till konfigurationer som användarhantering, taggning, roller, moderering, analys, översättning och aktivering.

#### ANVÄNDARHANTERING {#user-management}

Vi rekommenderar att [aktiveringscommunityn](overview.md#enablement-community) vara privat.

En communitywebbplats är privat när anonyma besökare på webbplatsen nekas åtkomst, inte får registrera sig själv och inte får använda social inloggning.

Kontrollera att de flesta kryssrutor inte är markerade [Användarhantering](sites-console.md#user-management):

* Tillåt INTE webbplatsbesökare att registrera sig själva
* Tillåt INTE anonyma webbplatsbesökare att visa webbplatsen
* Valfritt om meddelanden ska tillåtas bland communitymedlemmar eller inte
* Tillåt INTE inloggning med Facebook
* Tillåt INTE inloggning med Twitter

![chlimage_1-285](assets/chlimage_1-285.png)

#### TAGGNING {#tagging}

De taggar som kan användas för communityinnehåll kontrolleras genom att AEM namnutrymmen som tidigare definierats i [Taggningskonsolen](../../help/sites-administering/tags.md#tagging-console) (t.ex. [Namnutrymme för självstudiekurs](enablement-setup.md#create-tutorial-tags)).

Om du väljer Taggnamnutrymmen för communitywebbplatsen begränsas dessutom det urval som visas när du definierar kataloger och aktiveringsresurser. Se [Aktiveringsresurser för taggning](tag-resources.md) för viktig information.

Det är enkelt att hitta namnutrymmen med typsnittssökning. Till exempel,

* Skriv tut
* Välj `Tutorial`

![chlimage_1-286](assets/chlimage_1-286.png)

### ROLLER {#roles}

[Medlemsroller i communityn](users.md) tilldelas via inställningarna i avsnittet Roller.

Om du vill att en community-medlem (eller grupp av medlemmar) ska kunna uppleva webbplatsen som community-hanterare använder du typsnittssökningen och väljer medlemmens eller gruppens namn bland alternativen i listrutan.

Till exempel,

* Skriv &quot;q&quot;
* Välj [Quinn Harper](enablement-setup.md#publishcreateenablementmembers)

>[!NOTE]
>
>[Tunneltjänst](deploy-communities.md#tunnel-service-on-author) gör att du kan välja medlemmar och grupper som bara finns i publiceringsmiljön.

![community_roles](assets/community_roles.png)

#### MODERATION {#moderation}

Acceptera de globala standardinställningarna för [moderera](sites-console.md#moderation) användargenererat innehåll (UGC).

![chlimage_1-287](assets/chlimage_1-287.png)

#### ANALYS {#analytics}

I listrutan väljer du Analytics-molntjänstramverket som är konfigurerat för den här communitywebbplatsen.

Markeringen som visas på skärmbilden, `Communities`, är ramverksexemplet från [konfigurationsdokumentation.](analytics.md#aem-analytics-framework-configuration)

![chlimage_1-288](assets/chlimage_1-288.png)

#### ÖVERSÄTTNING {#translation}

The [Översättningsinställningar](sites-console.md#translation) Ange om användargenererat innehåll får översättas och till vilket språk.

* Kontrollera **[!UICONTROL Allow Machine Translation]**
* Använd standardinställningarna

![chlimage_1-289](assets/chlimage_1-289.png)

#### AKTIVERING {#enablement}

För en aktiveringscommunity måste du identifiera en eller flera aktiveringsansvariga i communityn.

* **[!UICONTROL Enablement Managers]**
(obligatoriskt) Medlemmar i 
`Community Enablement Managers` gruppen är tillgänglig för att väljas för att hantera den här communitywebbplatsen.

   * Skriv &quot;s&quot;
   * Välj `Sirius Nilson`

* **[!UICONTROL Marketing Cloud Org Id]**
(valfritt) ID:t för ett Adobe Analytics-konto som krävs när du inkluderar [Analys av pulsslag för video](analytics.md#video-heartbeat-analytics) i aktiveringsrapporteringen.

![chlimage_1-290](assets/chlimage_1-290.png)

Välj **[!UICONTROL Next]**.

### Steg 4: Skapa communitywebbplats {#step-create-community-site}

Välj **[!UICONTROL Create]**.

![chlimage_1-291](assets/chlimage_1-291.png)

När processen är klar visas mappen för den nya platsen i konsolen Communities - Sites.

![enablementsitecreated](assets/enablementsitecreated.png)

### Publicera den nya communitywebbplatsen {#publish-the-new-community-site}

Den skapade webbplatsen bör hanteras från konsolen Communities - Sites, samma konsol som nya platser kan skapas från.

När du har valt communityplatsens mapp för du muspekaren över platsikonen så att fyra åtgärdsikoner visas:

![siteactionicons](assets/siteactionicons.png)

När du markerar ellipsikonen (ikonen Fler åtgärder) visas alternativen Exportera plats och Ta bort plats.

![siteactionsnya](assets/siteactionsnew.png)

Från vänster till höger är de:

* **Öppna webbplats**
Välj pennikonen för att öppna communitywebbplatsen i redigeringsläge för författare, för att lägga till och/eller konfigurera sidkomponenter

* **Redigera webbplats**
Välj egenskapsikonen för att öppna communitywebbplatsen för ändring av egenskaper, som titeln eller för att ändra temat

* **Publicera webbplats**
Välj världsikonen om du vill publicera communitywebbplatsen (till localhost:4503 som standard)

* **Exportera webbplats**
Välj exportikonen för att skapa ett paket för communitywebbplatsen som båda lagras i [pakethanterare](../../help/sites-administering/package-manager.md) och laddas ned.

   Observera att UGC inte ingår i platspaketet.

* **Ta bort plats**
Om du vill ta bort communitywebbplatsen väljer du ikonen Ta bort plats som visas när du håller muspekaren över webbplatsen i Webbplatskonsolen. Den här åtgärden tar bort alla objekt som är associerade med platsen, till exempel UGC, användargrupper, resurser och databasposter.

![aktiveraAktivitetsåtgärder](assets/enablesiteactions.png)

#### Välj Publicera {#select-publish}

Välj världsikonen för att publicera communitywebbplatsen.

![chlimage_1-292](assets/chlimage_1-292.png)

Det kommer att finnas en indikation på att webbplatsen har publicerats.

![chlimage_1-293](assets/chlimage_1-293.png)

## Community-användare och användargrupper {#community-users-user-groups}

### Meddelande om nya användargrupper {#notice-new-community-user-groups}

Tillsammans med den nya communitywebbplatsen skapas nya användargrupper som har rätt behörigheter för olika administrativa funktioner. Mer information finns på [Användargrupper för communityplatser](users.md#usergroupsforcommunitysites).

Med tanke på webbplatsens namn&quot;enable&quot; i steg 1 kan de nya användargrupperna som finns i publiceringsmiljön ses från [Konsol för gruppmedlemmar och grupper](members.md#groups-console):

![chlimage_1-294](assets/chlimage_1-294.png)

### Tilldela medlemmar till gruppen Aktivera medlemmar {#assign-members-to-community-enable-members-group}

När tunneltjänsten är aktiverad kan du tilldela [användare som skapades under den första installationen](enablement-setup.md#publishcreateenablementmembers) till communitymedlemsgruppen för den nyligen skapade communitywebbplatsen.

Med hjälp av gruppkonsolen kan medlemmar läggas till individuellt eller genom medlemskap i en grupp.

I det här exemplet `Community Ski Class` läggs till som medlem i gruppen `Community Enable Members` samt medlem `Quinn Harper`.

* Navigera till **[!UICONTROL Communities > Groups]** konsol
* Välj **[!UICONTROL Community Enable Members]** grupp
* Retur `ski` till **[!UICONTROL Add Members To Group]** sökruta
* Välj **[!UICONTROL Community Ski Class]** (grupp av studerande)
* Retur `quinn` i sökrutan
* Välj **[!UICONTROL Quinn Harper]** (aktivera resurskontakt)

* Välj **[!UICONTROL Save]**

![chlimage_1-295](assets/chlimage_1-295.png)

## Konfigurationer vid publicering {#configurations-on-publish}

### http://localhost:4503/content/sites/enable/en.html {#http-localhost-content-sites-enable-en-html}

![chlimage_1-296](assets/chlimage_1-296.png)

### Konfigurera för autentiseringsfel {#configure-for-authentication-error}

När en webbplats har konfigurerats och publicerats, [konfigurera inloggningsmappning](sites-console.md#configure-for-authentication-error) ( `Adobe Granite Login Selector Authentication Handler`) på publiceringsinstansen. Fördelen är att när inloggningsuppgifter inte anges korrekt kommer autentiseringsfelet att visa inloggningssidan för communitywebbplatsen igen med ett felmeddelande.

Lägg till en `Login Page Mapping` as

* /content/sites/enable/en/signin:/content/sites/enable/en

### (Valfritt) Ändra standardhemsidan {#optional-change-the-default-home-page}

När du arbetar med publiceringswebbplatsen i demonstrationssyfte kan det vara praktiskt att ändra standardhemsidan till den nya webbplatsen.

För att göra detta måste du använda [CRX|DE](http://localhost:4503/crx/de) Lite för att redigera [resursmappning](../../help/sites-deploying/resource-mapping.md) tabell vid publicering.

För att komma igång

1. Vid publicering får du åtkomst till CRXDE och loggar in med administratörsbehörighet

   * Bläddra till exempel till [http://localhost:4503/crx/de](http://localhost:4503/crx/de) och logga in med `admin/admin`

1. Utöka i projektwebbläsaren `/etc/map`
1. Välj `http` nod

   * Välj **[!UICONTROL Create Node]**

      * **Namn** localhost.4503

         (Gör *not* use `:`)

      * **Typ** [sling:mappning](https://sling.apache.org/documentation/the-sling-engine/mappings-for-resource-resolution.html)

1. Med nyskapade `localhost.4503` markerad nod

   * Lägg till egenskap

      * **Namn** sling:match
      * **Typ** Sträng
      * **Värde** localhost.4503/\$

         (Måste sluta med tecknet &#39;$&#39;)
   * Lägg till egenskap

      * **Namn** sling:internalRedirect
      * **Typ** Sträng
      * **Värde** /content/sites/enable/en.html


1. Välj **[!UICONTROL Save All]**
1. (valfritt) Ta bort webbläsarhistoriken
1. Gå till http://localhost:4503/

   * Ankomst till http://localhost:4503/content/sites/enable/en.html

>[!NOTE]
>
>Om du vill inaktivera lägger du bara till `sling:match` egenskapsvärde med x - `xlocalhost.4503/$` - och **[!UICONTROL Save All]**.

![chlimage_1-297](assets/chlimage_1-297.png)

#### Felsökning: Fel när kartan sparades {#troubleshooting-error-saving-map}

Om det inte går att spara ändringarna måste du kontrollera att nodnamnet är `localhost.4503`, med en punktavgränsare, och inte `localhost:4503` med en kolonavgränsare, som `localhost`är inte ett giltigt namnområdesprefix.

![chlimage_1-298](assets/chlimage_1-298.png)

#### Felsökning: Det gick inte att omdirigera {#troubleshooting-fail-to-redirect}

The **$**&#39; i slutet av det reguljära uttrycket `sling:match`sträng är avgörande, så att bara exakt `http://localhost:4503/` är mappad, annars läggs omdirigeringsvärdet till en sökväg som kan finnas efter server:port i URL:en. När AEM försöker dirigera om till inloggningssidan misslyckas den alltså.

## Ändra communityplatsen {#modifying-the-community-site}

När webbplatsen har skapats kan författare använda [Ikonen Öppna webbplats](sites-console.md#authoring-site-content) för att utföra AEM.

Dessutom kan administratörer använda [Ikonen Redigera webbplats](sites-console.md#modifying-site-properties) om du vill ändra egenskaper för platsen, t.ex. titeln.

Kom ihåg att efter varje ändring **Spara** och **Publicera** sajten.

>[!NOTE]
>
>Om du inte känner till AEM kan du läsa dokumentationen om [grundläggande hantering](../../help/sites-authoring/basic-handling.md) och [snabbguide till framtagning av sidor](../../help/sites-authoring/qg-page-authoring.md).

### Lägg till en katalog {#add-a-catalog}

Den communityplatsmall som valts för den här communitywebbplatsen bör innehålla katalogfunktionen.

Om inte kan du enkelt lägga till katalogfunktionen. På så sätt kan andra medlemmar i communityn, som inte är tilldelade till aktiveringsresurser eller en utbildningsväg, välja aktiveringsresurser från en katalog.

Om platsstrukturen redan innehåller katalogfunktionen kan dess namn ändras.

Om du vill ändra platsens struktur går du till **[!UICONTROL Communities, Sites]** konsolen, öppna `enable` och väljer **Redigera webbplats** -ikonen för att komma åt egenskaperna för `Enablement Tutorial`.

Välj STRUKTURpanelen om du vill lägga till en katalog eller ändra en befintlig katalog:

* **Titel**: `Ski Catalog`

* **URL**: `catalog`

* **Markera alla namnutrymmen**: lämna som standard.
* Välj **[!UICONTROL Save]**

![chlimage_1-299](assets/chlimage_1-299.png)

Använd placeringsikonen för att flytta katalogfunktionen till den andra positionen, efter tilldelningar.

![chlimage_1-300](assets/chlimage_1-300.png)

Välj **[!UICONTROL Save]** i det övre högra hörnet för att spara ändringarna på communitywebbplatsen.

Gör sedan om **Publicera** sajten.
