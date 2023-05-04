---
title: Skapa en ny communitywebbplats
seo-title: Author a New Community Site
description: Så här skapar du en ny AEM Communities-webbplats
seo-description: How to author a new AEM Communities site
uuid: b8557416-cae4-489e-ab3b-e94d56686b7a
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: bf182bb7-e305-45be-aadb-d71efd70f8cb
exl-id: 5d58f9c5-3210-48ef-94a3-805a1a57e3af
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1619'
ht-degree: 1%

---

# Skapa en ny communitywebbplats {#author-a-new-community-site}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Skapa en ny communitywebbplats {#create-a-new-community-site}

Använd författarinstansen för att skapa en ny community-webbplats

* Logga in med administratörsbehörighet
* Från global navigering: **[!UICONTROL Navigation > Communities > Sites]**

Konsolen Communities Sites innehåller en guide som hjälper dig att skapa en communityplats. Det går att gå vidare till `Next`steg eller `Back`till föregående steg innan webbplatsen implementeras i det sista steget.

Så här kommer du igång med att skapa en ny community-webbplats:

* Välj `Create` knapp

![createcommunitysite](assets/createcommunitysite.png)

### Steg 1: Webbplatsmall {#step-site-template}

![createsitetemplate63](assets/createsitetemplate63.png)

På [Steg för webbplatsmall](sites-console.md#step2013asitetemplate), ange en titel, beskrivning, namnet på URL:en och välj en mall för en community-webbplats, till exempel:

* **[!UICONTROL Community Site Title]**: `Getting Started Tutorial`

* **[!UICONTROL Community Site Description]**: `A site for engaging with the community.`

* **[!UICONTROL Community Site Root]**: (lämna tomt för standardroten `/content/sites`)

* **[!UICONTROL Cloud Configurations]**: (lämna tomt om ingen molnkonfiguration har angetts) ange sökvägen till de angivna molnkonfigurationerna.
* **[!UICONTROL Community Site Base Language]**: (lämnas orört för ett enda språk: Engelska) använd listrutan för att välja en *eller mer* basspråk från tillgängliga språk - tyska, italienska, franska, japanska, spanska, portugisiska (Brasilien), kinesiska (traditionell) och kinesiska (förenklad). En community-webbplats skapas för varje språk som läggs till och finns i samma webbplatsmapp enligt de rutiner som beskrivs i [Översätta innehåll för flerspråkiga webbplatser](../../help/sites-administering/translation.md). Rotsidan för varje webbplats kommer att innehålla en underordnad sida med språkkoden för ett av de valda språken, till exempel &quot;en&quot; för engelska eller &quot;fr&quot; för franska.

* **[!UICONTROL Community Site Name]**: engagera

   * Dubbelkontrollera namnet eftersom det inte är lätt att ändra efter att webbplatsen har skapats
   * Den inledande URL:en visas under namnet på communitywebbplatsen
   * Ange en giltig URL genom att lägga till en baskod + &quot;.html&quot;
   * *Till exempel*, http://localhost:4502/content/sites/ `engage/en.html`

* **[!UICONTROL Template]**: dra nedåt för att välja `Reference Site`

Välj **[!UICONTROL Next]**

### Steg 2: Design {#step-design}

Designsteget presenteras i två avsnitt där du kan välja tema och varumärkesbanderoll:

#### TEMA PÅ GEMENSKAPENS WEBBPLATS {#community-site-theme}

Välj det format som du vill använda på mallen. När du väljer det här alternativet överlagras temat med en bockmarkering.

![sitetema](assets/sitetheme.png)

#### GEMENSKAPENS WEBBPLATSHANTERING {#community-site-branding}

(Valfritt) Ladda upp en banderollbild som ska visas på webbplatsens sidor. Banderollen är fäst vid webbläsarens vänstra kant, mellan communitywebbplatsens sidhuvud och meny (navigeringslänkar). Banderollhöjden beskärs till 120 pixlar. Banderollens storlek ändras inte så att den passar webbläsarens bredd och höjden 120 pixlar.

![chlimage_1-353](assets/chlimage_1-353.png) ![chlimage_1-354](assets/chlimage_1-354.png)

Välj **[!UICONTROL Next]**.

### Steg 3: Inställningar {#step-settings}

I steget Inställningar, innan du väljer `Next`, observera att det finns sju avsnitt som ger åtkomst till konfigurationer som användarhantering, taggning, moderering, grupphantering, analys, översättning och aktivering.

Besök [Komma igång med AEM Communities för aktivering](getting-started-enablement.md) självstudiekurs om hur du arbetar med aktiveringsfunktionerna.

#### ANVÄNDARHANTERING {#user-management}

Markera alla kryssrutor för [Användarhantering](sites-console.md#user-management)

* Tillåta besökare att registrera sig själva
* Så här låter du besökare på webbplatsen visa den utan att logga in
* Så här tillåter du medlemmar att skicka och ta emot meddelanden från andra communitymedlemmar
* Så här tillåter du inloggning med Facebook i stället för att registrera och skapa en profil
* Så här tillåter du inloggning med Twitter i stället för att registrera och skapa en profil

>[!NOTE]
>
>I en produktionsmiljö måste du skapa anpassade Facebook- och Twitter-program. Se [Social inloggning med Facebook och Twitter](social-login.md).

![createplatserinställningar](assets/createsitesettings.png)

#### TAGGNING {#tagging}

De taggar som kan användas för communityinnehåll kontrolleras genom att AEM namnutrymmen som tidigare definierats i [Taggningskonsolen](../../help/sites-administering/tags.md#tagging-console) (t.ex. [Namnutrymme för självstudiekurs](setup.md#create-tutorial-tags)).

Det är enkelt att hitta namnutrymmen med typsnittssökning. Till exempel,

* Skriv tut
* Välj `Tutorial`

![chlimage_1-355](assets/chlimage_1-355.png)

#### ROLLER {#roles}

[Medlemsroller i communityn](users.md) tilldelas via inställningarna i avsnittet Roller.

Om du vill att en community-medlem (eller grupp av medlemmar) ska kunna uppleva webbplatsen som community-hanterare använder du typsnittssökningen och väljer medlemmens eller gruppens namn bland alternativen i listrutan.

Till exempel,

* Skriv &quot;q&quot;
* Välj [Quinn Harper](enablement-setup.md#publishcreateenablementmembers)

>[!NOTE]
>
>[Tunneltjänst](https://helpx.adobe.com/experience-manager/6-3/communities/using/deploy-communities.html#tunnel-service-on-author) gör att du kan välja medlemmar och grupper som bara finns i publiceringsmiljön.

![community_roles-1](assets/community_roles-1.png)

#### MODERATION {#moderation}

Acceptera de globala standardinställningarna för [moderera](sites-console.md#moderation) användargenererat innehåll (UGC).

![chlimage_1-356](assets/chlimage_1-356.png)

#### ANALYS {#analytics}

Om Adobe Analytics är licensierat och en molntjänst och ett ramverk för Analytics har konfigurerats går det att aktivera Analytics och välja ramverket.

Se [Analyskonfiguration för communityfunktioner](analytics.md).

![chlimage_1-357](assets/chlimage_1-357.png)

#### ÖVERSÄTTNING {#translation}

The [Översättningsinställningar](sites-console.md#translation) Ange basspråket för webbplatsen samt om användargenererat innehåll kan översättas och till vilket språk, om så är fallet.

* Kontrollera **[!UICONTROL Allow Machine Translation]**
* Låt standardspråken vara markerade för översättning av standardmaskinöversättningstjänsten
* Lämna standardöversättningsprovider och -konfiguration
* Ingen global butik behövs eftersom det inte finns några språkversioner
* Välj **[!UICONTROL Translate entire page]**
* Lämna standardalternativet för beständighet

![chlimage_1-358](assets/chlimage_1-358.png)

#### AKTIVERING {#enablement}

Lämna tomt när du skapar en engagemangscommunity.

Om du vill ha en liknande självstudiekurs för att snabbt skapa en [användargrupper](overview.md#enablement-community), se [Komma igång med AEM Communities för aktivering](getting-started-enablement.md).

Välj **[!UICONTROL Next]**.

### Steg 4: Skapa webbgruppsplats {#step-create-communities-site}

Välj **[!UICONTROL Create]**.

![chlimage_1-359](assets/chlimage_1-359.png)

När processen är klar visas mappen för den nya platsen i konsolen Communities - Sites.

![communityerplatskonsol](assets/communitiessitesconsole.png)

## Publicera den nya communitywebbplatsen {#publish-the-new-community-site}

Den skapade webbplatsen bör hanteras från konsolen Communities - Sites, samma konsol som nya platser kan skapas från.

När du har valt att öppna gruppplatsens mapp för att öppna den håller du pekaren över platsikonen så att fyra åtgärdsikoner visas:

![siteactionicons-1](assets/siteactionicons-1.png)

När du väljer den fjärde ellipsikonen (Fler åtgärder) visas alternativen Exportera plats och Ta bort plats.

![siteactionsnew-1](assets/siteactionsnew-1.png)

Från vänster till höger är de:

* **Öppna webbplats**
Välj pennikonen för att öppna communitywebbplatsen i redigeringsläge för författare, för att lägga till och/eller konfigurera sidkomponenter

* **Redigera webbplats**
Välj egenskapsikonen för att öppna communitywebbplatsen för ändring av egenskaper, som titeln eller för att ändra temat

* **Publicera webbplats**
Välj världsikonen om du vill publicera communitywebbplatsen (till exempel om publiceringsservern körs på den lokala datorn, och sedan till localhost:4503 som standard)

* **Exportera webbplats**
Välj exportikonen för att skapa ett paket för communitywebbplatsen som båda lagras i [pakethanterare](../../help/sites-administering/package-manager.md) och laddas ned.

   Observera att UGC inte ingår i platspaketet.

* **Ta bort plats**

   välj ikonen Ta bort för att ta bort communitywebbplatsen från **[!UICONTROL Communities > Sites console]**. Den här åtgärden tar bort alla objekt som är associerade med platsen, till exempel UGC, användargrupper, resurser och databasposter.

![siteactions-1](assets/siteactions-1.png)

>[!NOTE]
>
>Om du inte använder standardporten 4503 för publiceringsinstansen redigerar du standardreplikeringsagenten och anger portnumret till rätt värde.
>
>På författarinstansen, från huvudmenyn
>
>1. Navigera till **[!UICONTROL Tools > Operations > Replication]** meny
>1. Välj **[!UICONTROL Agents on author]**
>1. Välj **[!UICONTROL Default Agent (publish)]**
>1. Nästa till **[!UICONTROL Settings]** välj **[!UICONTROL Edit]**
>1. I popup-dialogrutan för agentinställningar väljer du fliken Transport
>1. I URI ändrar du portnumret 4503 till önskat portnummer

>
>Om du till exempel vill använda port 6103: `http://localhost:6103/bin/receive?sling:authRequestLogin=1`
>
>1. Välj **[!UICONTROL OK]**
>1. (Valfritt) Välj `Clear` eller `Force Retry` för att återställa replikeringskön


### Välj Publicera {#select-publish}

När du har kontrollerat att publiceringsservern körs väljer du världsikonen för att publicera communitywebbplatsen.

![chlimage_1-360](assets/chlimage_1-360.png)

När communitywebbplatsen har publicerats visas ett kort meddelande:

![chlimage_1-361](assets/chlimage_1-361.png)

### Meddelande om nya användargrupper {#notice-new-community-user-groups}

Tillsammans med den nya communitywebbplatsen skapas nya användargrupper som har rätt behörigheter för olika administrativa funktioner. Mer information finns på [Användargrupper för communityplatser](users.md#usergroupsforcommunitysites).

Med tanke på webbplatsens namn&quot;engagera&quot; i steg 1 kan de fyra nya användargrupperna ses från [Gruppkonsol](members.md) (global navigering: Communities, Groups):

* Community Engage Community Managers
* Gruppadministratörer för communityengagemang
* Medlemmar i communityengagemang
* Moderatorer för communityengagemang
* Behöriga medlemmar för communityengagemang
* Community Engage Sitecontentmanager

Observera att [Aaron McDonald](tutorials.md#demo-users) är medlem i

* Community Engage Community Managers
* Moderatorer för communityengagemang
* Medlemmar i communityn (indirekt som medlem i gruppen Moderatorer)

![chlimage_1-362](assets/chlimage_1-362.png)

#### http://localhost:4503/content/sites/engage/en.html {#http-localhost-content-sites-engage-en-html}

![chlimage_1-363](assets/chlimage_1-363.png)

## Konfigurera för autentiseringsfel {#configure-for-authentication-error}

När en webbplats har konfigurerats och publicerats, [konfigurera inloggningsmappning](sites-console.md#configure-for-authentication-error) ( `Adobe Granite Login Selector Authentication Handler`) på publiceringsinstansen. Fördelen är att när inloggningsuppgifter inte anges korrekt kommer autentiseringsfelet att visa inloggningssidan för communitywebbplatsen igen med ett felmeddelande.

Lägg till en `Login Page Mapping` as

* /content/sites/engage/en/signin:/content/sites/engage/en

## Valfria steg {#optional-steps}

### Ändra standardhemsidan {#change-the-default-home-page}

När du arbetar med publiceringswebbplatsen i demonstrationssyfte kan det vara praktiskt att ändra standardhemsidan till den nya webbplatsen.

För att göra detta måste du använda [CRXDE](http://localhost:4503/crx/de) Lite för att redigera [resursmappning](../../help/sites-deploying/resource-mapping.md) tabell vid publicering.

Så här kommer du igång:

1. Logga in med administratörsbehörighet vid publicering
1. Bläddra till [http://localhost:4503/crx/de](http://localhost:4503/crx/de)
1. Utöka i projektwebbläsaren `/etc/map`
1. Välj `http` nod

   * Välj **[!UICONTROL Create Node]**

      * **Namn** localhost.4503

         (do *not* use `:`)

      * **Typ** [sling:mappning](https://sling.apache.org/documentation/the-sling-engine/mappings-for-resource-resolution.html)

1. Med nyskapade `localhost.4503` markerad nod

   * Lägg till egenskap

      * **Namn** sling:match
      * **Typ** Sträng
      * **Värde** localhost.4503/\$

         (måste sluta med tecknet &#39;$&#39;)
   * Lägg till egenskap

      * **Namn** sling:internalRedirect
      * **Typ** Sträng
      * **Värde** /content/sites/engage/en.html


1. Välj **[!UICONTROL Save All]**
1. (valfritt) Ta bort webbläsarhistoriken
1. Gå till http://localhost:4503/

   * Ankomst till http://localhost:4503/content/sites/engage/en.html

>[!NOTE]
>
>Om du vill inaktivera lägger du bara till `sling:match` egenskapsvärde med x - `xlocalhost.4503/$` - och **[!UICONTROL Save All]**.

![chlimage_1-364](assets/chlimage_1-364.png)

#### Felsökning: Fel när kartan sparades {#troubleshooting-error-saving-map}

Om det inte går att spara ändringarna måste du kontrollera att nodnamnet är `localhost.4503`, med en punktavgränsare, och inte `localhost:4503` med en kolonavgränsare, som `localhost`är inte ett giltigt namnområdesprefix.

![chlimage_1-365](assets/chlimage_1-365.png)

#### Felsökning: Det gick inte att omdirigera {#troubleshooting-fail-to-redirect}

The **$**&#39; i slutet av det reguljära uttrycket `sling:match`sträng är avgörande, så att bara exakt `http://localhost:4503/` är mappad, annars läggs omdirigeringsvärdet till en sökväg som kan finnas efter server:port i URL:en. När AEM försöker dirigera om till inloggningssidan misslyckas den alltså.

### Ändra platsen {#modify-the-site}

När webbplatsen har skapats kan författare använda [Ikonen Öppna webbplats](sites-console.md#authoring-site-content) för att utföra AEM.

Dessutom kan administratörer använda [Ikonen Redigera webbplats](sites-console.md#modifying-site-properties) om du vill ändra egenskaper för platsen, t.ex. titeln.

Kom ihåg att efter varje ändring **spara** och **återpublicera** sajten.

>[!NOTE]
>
>Om du inte känner till AEM kan du läsa dokumentationen om [grundläggande hantering](../../help/sites-authoring/basic-handling.md) och [snabbguide till framtagning av sidor](../../help/sites-authoring/qg-page-authoring.md).
