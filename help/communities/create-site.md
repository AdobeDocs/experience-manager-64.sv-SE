---
title: Skapa en ny communitywebbplats
seo-title: Skapa en ny communitywebbplats
description: Skapa en ny AEM Communities-webbplats
seo-description: Skapa en ny AEM Communities-webbplats
uuid: b8557416-cae4-489e-ab3b-e94d56686b7a
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: bf182bb7-e305-45be-aadb-d71efd70f8cb
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c

---


# Skapa en ny communitywebbplats {#author-a-new-community-site}

## Skapa en ny communitywebbplats {#create-a-new-community-site}

Använd författarinstansen för att skapa en ny community-webbplats

* Logga in med administratörsbehörighet
* Från global navigering: **[!UICONTROL Navigation > Communities > Sites]**

Konsolen Communities Sites innehåller en guide som hjälper dig att skapa en communityplats. Du kan gå vidare till `Next`steget eller `Back`till föregående steg innan du implementerar platsen i det sista steget.

Så här kommer du igång med att skapa en ny community-webbplats:

* Markera `Create` knappen

![createcommunitysite](assets/createcommunitysite.png)

### Steg 1: Webbplatsmall {#step-site-template}

![createsitetemplate63](assets/createsitetemplate63.png)

I steget [](sites-console.md#step2013asitetemplate)Webbplatsmall anger du en titel, en beskrivning, namnet på webbadressen och väljer en mall för en community-webbplats, till exempel:

* **[!UICONTROL Webbplatstitel]** för communityn: `Getting Started Tutorial`

* **[!UICONTROL Beskrivning]** av communityplats: `A site for engaging with the community.`

* **[!UICONTROL Rotadress]** för communityplats: (lämna tomt för standardroten `/content/sites`)

* **[!UICONTROL Molnkonfigurationer]**: (lämna tomt om ingen molnkonfiguration har angetts) ange sökvägen till de angivna molnkonfigurationerna.
* **[!UICONTROL Grundspråk]** för communitywebbplats: (lämnas orört för ett enda språk: På engelska) använder du listrutan för att välja ett *eller flera* basspråk bland de tillgängliga språken - tyska, italienska, franska, japanska, spanska, portugisiska (Brasilien), kinesiska (traditionell) och kinesiska (förenklad). En communitywebbplats kommer att skapas för varje språk som läggs till och kommer att finnas i samma webbplatsmapp enligt bästa praxis som beskrivs i [Översätta innehåll för flerspråkiga webbplatser](../../help/sites-administering/translation.md). Rotsidan för varje webbplats kommer att innehålla en underordnad sida med språkkoden för ett av de valda språken, till exempel &quot;en&quot; för engelska eller &quot;fr&quot; för franska.

* **[!UICONTROL Namn på]** communitywebbplats: engagera

   * Dubbelkontrollera namnet eftersom det inte är lätt att ändra efter att webbplatsen har skapats
   * Den inledande URL:en visas under namnet på communitywebbplatsen
   * Ange en giltig URL genom att lägga till en baskod + &quot;.html&quot;
   * *Till exempel* http://localhost:4502/content/sites/ `engage/en.html`

* **[!UICONTROL Mall]**: dra nedåt för att välja `Reference Site`

Markera **[!UICONTROL nästa]**

### Steg 2:Design {#step-design}

Designsteget presenteras i två avsnitt där du kan välja tema och varumärkesbanderoll:

#### TEMA PÅ GEMENSKAPENS WEBBPLATS {#community-site-theme}

Välj det format som du vill använda på mallen. När du väljer det här alternativet överlagras temat med en bockmarkering.

![sitetema](assets/sitetheme.png)

#### GEMENSKAPENS WEBBPLATSHANTERING {#community-site-branding}

(Valfritt) Ladda upp en banderollbild som ska visas på webbplatsens sidor. Banderollen är fäst vid webbläsarens vänstra kant, mellan communitywebbplatsens sidhuvud och meny (navigeringslänkar). Banderollhöjden beskärs till 120 pixlar. Banderollens storlek ändras inte så att den passar webbläsarens bredd och höjden 120 pixlar.

![chlimage_1-353](assets/chlimage_1-353.png) ![chlimage_1-354](assets/chlimage_1-354.png)

Välj **[!UICONTROL Nästa]**.

### Steg 3: Inställningar {#step-settings}

I steget Inställningar, innan du väljer `Next`det, ska du lägga märke till att det finns sju avsnitt som ger åtkomst till konfigurationer som användarhantering, taggning, moderering, grupphantering, analys, översättning och aktivering.

Gå till [självstudiekursen Komma igång med AEM Communities för att få](getting-started-enablement.md) hjälp med att aktivera funktioner.

#### ANVÄNDARHANTERING {#user-management}

Markera alla kryssrutor för [användarhantering](sites-console.md#user-management)

* Tillåta besökare att registrera sig själva
* Så här låter du besökare på webbplatsen visa den utan att logga in
* Så här tillåter du medlemmar att skicka och ta emot meddelanden från andra communitymedlemmar
* Tillåt inloggning på Facebook i stället för att registrera och skapa en profil
* Så här tillåter du inloggning med Twitter i stället för att registrera och skapa en profil

>[!NOTE]
>
>För en produktionsmiljö är det nödvändigt att skapa anpassade Facebook- och Twitter-program. Se [Social Login med Facebook och Twitter](social-login.md).

![createplatserinställningar](assets/createsitesettings.png)

#### TAGGNING {#tagging}

De taggar som kan användas för communityinnehåll kontrolleras genom att AEM-namnutrymmen som tidigare definierats via [taggningskonsolen](../../help/sites-administering/tags.md#tagging-console) (till exempel namnutrymmet [Tutorial](setup.md#create-tutorial-tags)) väljs.

Det är enkelt att hitta namnutrymmen med typsnittssökning. Exempel:

* Skriv tut
* Välj `Tutorial`

![chlimage_1-355](assets/chlimage_1-355.png)

#### ROLLER {#roles}

[Gruppmedlemsroller](users.md) tilldelas via inställningarna i avsnittet Roller.

Om du vill att en community-medlem (eller grupp av medlemmar) ska kunna uppleva webbplatsen som community-hanterare använder du typsnittssökningen och väljer medlemmens eller gruppens namn bland alternativen i listrutan.

Exempel:

* Skriv &quot;q&quot;
* Välj [Quinn Harper](enablement-setup.md#publishcreateenablementmembers)

>[!NOTE]
>
>[Tunneltjänsten](https://helpx.adobe.com/experience-manager/6-3/communities/using/deploy-communities.html#tunnel-service-on-author) tillåter endast urval av medlemmar och grupper som finns i publiceringsmiljön.

![community_roles-1](assets/community_roles-1.png)

#### MODERATION {#moderation}

Acceptera de globala standardinställningarna för [moderering](sites-console.md#moderation) av användargenererat innehåll (UGC).

![chlimage_1-356](assets/chlimage_1-356.png)

#### ANALYS {#analytics}

Om Adobe Analytics är licensierat och en molntjänst och ett ramverk i Analytics har konfigurerats går det att aktivera Analytics och välja ramverket.

Se [Analyskonfiguration för communityfunktioner](analytics.md).

![chlimage_1-357](assets/chlimage_1-357.png)

#### ÖVERSÄTTNING {#translation}

I [översättningsinställningarna](sites-console.md#translation) anges grundspråket för webbplatsen samt om UGC kan översättas och till vilket språk.

* Kontrollera **[!UICONTROL Tillåt maskinöversättning]**
* Låt standardspråken vara markerade för översättning av standardmaskinöversättningstjänsten
* Lämna standardöversättningsprovider och -konfiguration
* Ingen global butik behövs eftersom det inte finns några språkversioner
* Markera **[!UICONTROL Översätt hela sidan]**
* Lämna standardalternativet för beständighet

![chlimage_1-358](assets/chlimage_1-358.png)

#### AKTIVERING {#enablement}

Lämna tomt när du skapar en engagemangscommunity.

En liknande självstudiekurs för att snabbt skapa en [aktiveringscommunity](overview.md#enablement-community)finns i [Komma igång med AEM Communities för aktivering](getting-started-enablement.md).

Välj **[!UICONTROL Nästa]**.

### Steg 4: Skapa webbgruppsplats {#step-create-communities-site}

Välj **[!UICONTROL Skapa]**.

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

* **Öppna webbplats** Välj pennikonen för att öppna communitywebbplatsen i redigeringsläge, för att lägga till och/eller konfigurera sidkomponenter

* **Redigera webbplats** Välj egenskapsikonen om du vill öppna communitywebbplatsen för ändring av egenskaper, till exempel titeln, eller om du vill ändra temat

* **Publicera webbplats** Välj ikonen world om du vill publicera communitywebbplatsen (om publiceringsservern till exempel körs på den lokala datorn, så till localhost:4503 som standard)

* **Exportera plats** Välj exportikonen för att skapa ett paket för communitywebbplatsen som både lagras i [pakethanteraren](../../help/sites-administering/package-manager.md) och hämtas.

   Observera att UGC inte ingår i platspaketet.

* **Ta bort plats**

   Markera borttagningsikonen om du vill ta bort communitywebbplatsen från **[!UICONTROL webbgrupper > Webbplatskonsolen]**. Den här åtgärden tar bort alla objekt som är associerade med platsen, till exempel UGC, användargrupper, resurser och databasposter.

![siteactions-1](assets/siteactions-1.png)

>[!NOTE]
>
>Om du inte använder standardporten 4503 för publiceringsinstansen redigerar du standardreplikeringsagenten och anger portnumret till rätt värde.
>
>På författarinstansen, från huvudmenyn
>
>1. Navigera till **[!UICONTROL Verktyg > Åtgärder > Replikering]** -menyn
>1. Välj **[!UICONTROL agenter på författare]**
>1. Välj **[!UICONTROL standardagent (publicera)]**
>1. Vid **[!UICONTROL Inställningar]** väljer du **[!UICONTROL Redigera]**
>1. I popup-dialogrutan för agentinställningar väljer du fliken Transport
>1. I URI ändrar du portnumret 4503 till önskat portnummer
>
>
Om du till exempel vill använda port 6103: `http://localhost:6103/bin/receive?sling:authRequestLogin=1`
>
>1. Välj **[!UICONTROL OK]**
>1. (Valfritt) Välj `Clear` eller `Force Retry` återställ replikeringskön


### Välj Publicera {#select-publish}

När du har kontrollerat att publiceringsservern körs väljer du världsikonen för att publicera communitywebbplatsen.

![chlimage_1-360](assets/chlimage_1-360.png)

När communitywebbplatsen har publicerats visas ett kort meddelande:

![chlimage_1-361](assets/chlimage_1-361.png)

### Meddelande om nya användargrupper {#notice-new-community-user-groups}

Tillsammans med den nya communitywebbplatsen skapas nya användargrupper som har rätt behörigheter för olika administrativa funktioner. Mer information finns i [Användargrupper för communitysajter](users.md#usergroupsforcommunitysites).

Med tanke på webbplatsens namn&quot;engagera&quot; i steg 1 kan de fyra nya användargrupperna ses från [gruppkonsolen](members.md) (global navigering: Communities, Groups):

* Community Engage Community Managers
* Gruppadministratörer för communityengagemang
* Medlemmar i communityengagemang
*  Moderatorer för communityengagemang
* Behöriga medlemmar för communityengagemang
* Community Engage Sitecontentmanager

Observera att [Aaron McDonald](tutorials.md#demo-users) är medlem i

* Community Engage Community Managers
*  Moderatorer för communityengagemang
* Medlemmar i communityn (indirekt som medlem i gruppen Moderatorer)

![chlimage_1-362](assets/chlimage_1-362.png)

#### http://localhost:4503/content/sites/engage/en.html {#http-localhost-content-sites-engage-en-html}

![chlimage_1-363](assets/chlimage_1-363.png)

## Konfigurera för autentiseringsfel {#configure-for-authentication-error}

När en webbplats har konfigurerats och publicerats [konfigurerar du inloggningsmappningen](sites-console.md#configure-for-authentication-error) ( `Adobe Granite Login Selector Authentication Handler`) på publiceringsinstansen. Fördelen är att när inloggningsuppgifter inte anges korrekt kommer autentiseringsfelet att visa inloggningssidan för communitywebbplatsen igen med ett felmeddelande.

Lägg till en `Login Page Mapping` som

* /content/sites/engage/en/signin:/content/sites/engage/en

## Valfria steg {#optional-steps}

### Ändra standardhemsidan {#change-the-default-home-page}

När du arbetar med publiceringswebbplatsen i demonstrationssyfte kan det vara praktiskt att ändra standardhemsidan till den nya webbplatsen.

Om du vill göra det måste du använda [CRXDE](http://localhost:4503/crx/de) Lite för att redigera [resursmappningstabellen](../../help/sites-deploying/resource-mapping.md) vid publicering.

Så här kommer du igång:

1. Logga in med administratörsbehörighet vid publicering
1. Gå till [http://localhost:4503/crx/de](http://localhost:4503/crx/de)
1. Utöka i projektwebbläsaren `/etc/map`
1. Markera `http` noden

   * Välj **[!UICONTROL Skapa nod]**

      * **Namn** localhost.4503

         (använd *inte* `:`)

      * **textsling** : [mappning](https://sling.apache.org/documentation/the-sling-engine/mappings-for-resource-resolution.html)

1. Med den nyskapade `localhost.4503` noden markerad

   * Lägg till egenskap

      * **Namnsling** :match
      * **Type** String
      * **Värde** localhost.4503/\$

         (måste sluta med tecknet &#39;$&#39;)
   * Lägg till egenskap

      * **Namnsling** :internalRedirect
      * **Type** String
      * **Värde** /content/sites/engage/en.html


1. Välj **[!UICONTROL Spara alla]**
1. (valfritt) Ta bort webbläsarhistoriken
1. Gå till http://localhost:4503/

   * Ankomst till http://localhost:4503/content/sites/engage/en.html

>[!NOTE]
>
>Om du vill inaktivera det lägger du bara till egenskapsvärdet med&quot;x&quot; - `sling:match` - och `xlocalhost.4503/$` Spara alla ****.

![chlimage_1-364](assets/chlimage_1-364.png)

#### Felsökning: Fel när kartan sparades {#troubleshooting-error-saving-map}

Om det inte går att spara ändringarna måste du kontrollera att nodnamnet är `localhost.4503`, med en punktavgränsare och inte `localhost:4503` med en kolonavgränsare, eftersom det inte `localhost`är ett giltigt namnområdesprefix.

![chlimage_1-365](assets/chlimage_1-365.png)

#### Felsökning: Det gick inte att omdirigera {#troubleshooting-fail-to-redirect}

&quot;**$**&quot; i slutet av `sling:match`strängen för det reguljära uttrycket är avgörande, så att bara exakt `http://localhost:4503/` mappas. I annat fall läggs omdirigeringsvärdet till alla sökvägar som kan finnas efter server:port i URL:en. När AEM försöker dirigera om till inloggningssidan misslyckas den således.

### Ändra platsen {#modify-the-site}

När webbplatsen har skapats kan författare använda ikonen [](sites-console.md#authoring-site-content) Open Site för att utföra vanliga AEM-redigeringsaktiviteter.

Dessutom kan administratörer använda ikonen [](sites-console.md#modifying-site-properties) Redigera plats för att ändra egenskaper för platsen, till exempel titeln.

Kom ihåg att **spara** och **publicera** om webbplatsen efter eventuella ändringar.

>[!NOTE]
>
>Om du inte känner till AEM läser du dokumentationen om [grundläggande hantering](../../help/sites-authoring/basic-handling.md) och en [snabbguide till redigeringssidorna](../../help/sites-authoring/qg-page-authoring.md).