---
title: Skapa en ny communitywebbplats för aktivering
seo-title: Skapa en ny communitywebbplats för aktivering
description: Skapa en communitywebbplats för aktivering
seo-description: Skapa en communitywebbplats för aktivering
uuid: 6822cc99-e272-4661-bddf-aa0800b88c41
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: aff8b79f-dd4e-486e-9d59-5d09dfe34f27
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c

---


# Skapa en ny communitywebbplats för aktivering {#author-a-new-community-site-for-enablement}

## Skapa communitywebbplats {#create-community-site}

[När du skapar](sites-console.md) en community-webbplats används en guide som vägleder dig genom de olika stegen för att skapa en community-webbplats. Du kan gå vidare till `Next`steget eller `Back`till föregående steg innan du implementerar platsen i det sista steget.

Så här kommer du igång med att skapa en ny community-webbplats:

Använda [författarinstansen](http://localhost:4502/)

* Logga in med administratörsbehörighet
* Navigera till **[!UICONTROL Communities > Sites]**

* Välj **[!UICONTROL Skapa]**

### Steg 1: Webbplatsmall {#step-site-template}

![enablementsitettemplate](assets/enablementsitetemplate.png)

I steget **Webbplatsmall** anger du en titel, en beskrivning, namnet på webbadressen och väljer en mall för en community-webbplats, till exempel:

* **Webbplatstitel** för communityn: `Enablement Tutorial`

* **Beskrivning** av communityplats: `A site for enabling the community to learn.`

* **Rotadress** för communityplats: (lämna tomt för standardroten `/content/sites`)

* **Molnkonfigurationer**: (lämna tomt om ingen molnkonfiguration har angetts) ange sökvägen till de angivna molnkonfigurationerna.
* **Grundspråk** för communitywebbplats: (lämnas orört för ett enda språk: På engelska) använder du listrutan för att välja ett *eller flera* basspråk bland de tillgängliga språken - tyska, italienska, franska, japanska, spanska, portugisiska (Brasilien), kinesiska (traditionell) och kinesiska (förenklad). En communitywebbplats kommer att skapas för varje språk som läggs till och kommer att finnas i samma webbplatsmapp enligt bästa praxis som beskrivs i [Översätta innehåll för flerspråkiga webbplatser](../../help/sites-administering/translation.md). Rotsidan för varje webbplats kommer att innehålla en underordnad sida med språkkoden för ett av de valda språken, till exempel &quot;en&quot; för engelska eller &quot;fr&quot; för franska.

* **[!UICONTROL Namn på]** communitywebbplats: `enable`

   * den inledande URL:en visas under namnet på communityplatsen
   * för en giltig URL, lägg till en baskod + &quot;.html&quot;

      *till exempel* http://localhost:4502/content/sites/ `enable/en.html`

* **[!UICONTROL Referensplatsmall]**: dra nedåt för att välja `Reference Structured Learning Site Template`

Markera **[!UICONTROL nästa]**

### Steg 2:Design {#step-design}

Designsteget presenteras i två avsnitt där du kan välja tema och varumärkesbanderoll:

#### TEMA PÅ GEMENSKAPENS WEBBPLATS {#community-site-theme}

Välj det format som du vill använda på mallen. När du väljer det här alternativet överlagras temat med en bockmarkering.

![enablementsitetema](assets/enablementsitetheme.png)

#### GEMENSKAPENS WEBBPLATSHANTERING {#community-site-branding}

(valfritt) Ladda upp en banderollbild som ska visas på webbplatsens sidor. Banderollen är fäst vid webbläsarens vänstra kant, mellan communitywebbplatsens sidhuvud och meny (navigeringslänkar). Banderollhöjden beskärs till 120 pixlar. Banderollens storlek ändras inte så att den passar webbläsarens bredd och höjden 120 pixlar.

![chlimage_1-284](assets/chlimage_1-284.png) ![chlimage_1](assets/chlimage_1.jpeg)

Välj **[!UICONTROL Nästa]**.

### Steg 3: Inställningar {#step-settings}

Observera att det finns sju avsnitt som ger åtkomst till konfigurationer som användarhantering, taggning, roller, moderering, analys, översättning och aktivering i steget Inställningar innan du väljer `Next`.

#### ANVÄNDARHANTERING {#user-management}

Vi rekommenderar att [aktiveringscommunityn](overview.md#enablement-community) är privata.

En communitywebbplats är privat när anonyma besökare på webbplatsen nekas åtkomst, inte får registrera sig själv och inte får använda social inloggning.

Kontrollera att de flesta kryssrutor är avmarkerade för [användarhantering](sites-console.md#user-management):

* Tillåt INTE webbplatsbesökare att registrera sig själva
* Tillåt INTE anonyma webbplatsbesökare att visa webbplatsen
* Valfritt om meddelanden ska tillåtas bland communitymedlemmar eller inte
* Tillåt INTE inloggning med Facebook
* Tillåt INTE inloggning med Twitter

![chlimage_1-285](assets/chlimage_1-285.png)

#### TAGGNING {#tagging}

De taggar som kan användas för communityinnehåll kontrolleras genom att AEM-namnutrymmen som tidigare definierats via [taggningskonsolen](../../help/sites-administering/tags.md#tagging-console) (till exempel namnutrymmet [Tutorial](enablement-setup.md#create-tutorial-tags)) väljs.

Om du väljer Taggnamnutrymmen för communitywebbplatsen begränsas dessutom det urval som visas när du definierar kataloger och aktiveringsresurser. Viktig information finns i [Tagga aktiveringsresurser](tag-resources.md) .

Det är enkelt att hitta namnutrymmen med typsnittssökning. Exempel:

* Skriv tut
* Välj `Tutorial`

![chlimage_1-286](assets/chlimage_1-286.png)

### ROLLER {#roles}

[Gruppmedlemsroller](users.md) tilldelas via inställningarna i avsnittet Roller.

Om du vill att en community-medlem (eller grupp av medlemmar) ska kunna uppleva webbplatsen som community-hanterare använder du typsnittssökningen och väljer medlemmens eller gruppens namn bland alternativen i listrutan.

Exempel:

* Skriv &quot;q&quot;
* Välj [Quinn Harper](enablement-setup.md#publishcreateenablementmembers)

>[!NOTE]
>
>[Tunneltjänsten](deploy-communities.md#tunnel-service-on-author) tillåter endast urval av medlemmar och grupper som finns i publiceringsmiljön.

![community_roles](assets/community_roles.png)

#### MODERATION {#moderation}

Acceptera de globala standardinställningarna för [moderering](sites-console.md#moderation) av användargenererat innehåll (UGC).

![chlimage_1-287](assets/chlimage_1-287.png)

#### ANALYS {#analytics}

I listrutan väljer du Analytics-molntjänstramverket som är konfigurerat för den här communitywebbplatsen.

Det som visas på skärmbilden `Communities`är ramverksexemplet från [konfigurationsdokumentationen.](analytics.md#aem-analytics-framework-configuration)

![chlimage_1-288](assets/chlimage_1-288.png)

#### ÖVERSÄTTNING {#translation}

I [översättningsinställningarna](sites-console.md#translation) anges om UGC kan översättas och till vilket språk.

* Kontrollera **[!UICONTROL Tillåt maskinöversättning]**
* Använd standardinställningarna

![chlimage_1-289](assets/chlimage_1-289.png)

#### AKTIVERING {#enablement}

För en aktiveringscommunity måste du identifiera en eller flera aktiveringsansvariga i communityn.

* **[!UICONTROL Aktivitetshanterare]**(krävs) Medlemmar i `Community Enablement Managers` gruppen kan väljas för att hantera den här communitywebbplatsen.

   * Skriv &quot;s&quot;
   * Välj `Sirius Nilson`

* **[!UICONTROL Organisations-ID]** för Marketing Cloud (valfritt) ID:t för ett Adobe Analytics-konto som är nödvändigt när [Video Heartbeat Analytics](analytics.md#video-heartbeat-analytics) inkluderas i aktiveringsrapporten.

![chlimage_1-290](assets/chlimage_1-290.png)

Välj **[!UICONTROL Nästa]**.

### Steg 4:Skapa communitywebbplats {#step-create-community-site}

Välj **[!UICONTROL Skapa]**.

![chlimage_1-291](assets/chlimage_1-291.png)

När processen är klar visas mappen för den nya platsen i konsolen Communities - Sites.

![enablementsitecreated](assets/enablementsitecreated.png)

### Publicera den nya communitywebbplatsen {#publish-the-new-community-site}

Den skapade webbplatsen bör hanteras från konsolen Communities - Sites, samma konsol som nya platser kan skapas från.

När du har valt communityplatsens mapp för du muspekaren över platsikonen så att fyra åtgärdsikoner visas:

![siteactionicons](assets/siteactionicons.png)

När du väljer ellipsikonen (ikonen Fler åtgärder) visas alternativen Exportera plats och Ta bort plats.

![siteactionsnya](assets/siteactionsnew.png)

Från vänster till höger är de:

* **Öppna webbplats** Välj pennikonen för att öppna communitywebbplatsen i redigeringsläge, för att lägga till och/eller konfigurera sidkomponenter

* **Redigera webbplats** Välj egenskapsikonen om du vill öppna communitywebbplatsen för ändring av egenskaper, till exempel titeln, eller om du vill ändra temat

* **Publicera webbplats** Välj ikonen world för att publicera communitywebbplatsen (till localhost:4503 som standard)

* **Exportera plats** Välj exportikonen för att skapa ett paket för communitywebbplatsen som både lagras i [pakethanteraren](../../help/sites-administering/package-manager.md) och hämtas.

   Observera att UGC inte ingår i platspaketet.

* **Ta bort plats** Om du vill ta bort communitywebbplatsen väljer du ikonen Ta bort plats som visas när du håller muspekaren över webbplatsen i Webbplatskonsol. Den här åtgärden tar bort alla objekt som är associerade med platsen, till exempel UGC, användargrupper, resurser och databasposter.

![aktiveraAktivitetsåtgärder](assets/enablesiteactions.png)

#### Välj Publicera {#select-publish}

Välj världsikonen för att publicera communitywebbplatsen.

![chlimage_1-292](assets/chlimage_1-292.png)

Det kommer att finnas en indikation på att webbplatsen har publicerats.

![chlimage_1-293](assets/chlimage_1-293.png)

## Community-användare och användargrupper {#community-users-user-groups}

### Meddelande om nya användargrupper {#notice-new-community-user-groups}

Tillsammans med den nya communitywebbplatsen skapas nya användargrupper som har rätt behörigheter för olika administrativa funktioner. Mer information finns i [Användargrupper för communitysajter](users.md#usergroupsforcommunitysites).

Med tanke på webbplatsens namn&quot;enable&quot; i steg 1 kan de nya användargrupperna som finns i publiceringsmiljön ses från konsolen [](members.md#groups-console)Communities Members &amp; Groups för den nya communitywebbplatsen:

![chlimage_1-294](assets/chlimage_1-294.png)

### Tilldela medlemmar till gruppen Aktivera medlemmar {#assign-members-to-community-enable-members-group}

När tunneltjänsten är aktiverad kan [användare som skapats under den första konfigurationen](enablement-setup.md#publishcreateenablementmembers) tilldelas till communitymedlemsgruppen för den nyligen skapade communitywebbplatsen.

Med hjälp av gruppkonsolen kan medlemmar läggas till individuellt eller genom medlemskap i en grupp.

I det här exemplet `Community Ski Class` läggs gruppen till som medlem i gruppen `Community Enable Members` samt medlem `Quinn Harper`.

* Navigera till **[!UICONTROL Communities > Groups]** console
* Markera gruppen Aktivera medlemmar **[!UICONTROL för]** grupp
* Ange `ski` i sökrutan **[!UICONTROL Lägg till medlemmar i grupp]**
* Välj **[!UICONTROL Community Ski Class]** (grupp av elever)
* Ange `quinn` i sökrutan
* Välj **[!UICONTROL Quinn Harper]** (kontakt för aktiveringsresurs)

* Välj **[!UICONTROL Spara]**

![chlimage_1-295](assets/chlimage_1-295.png)

## Konfigurationer vid publicering {#configurations-on-publish}

### http://localhost:4503/content/sites/enable/en.html {#http-localhost-content-sites-enable-en-html}

![chlimage_1-296](assets/chlimage_1-296.png)

### Konfigurera för autentiseringsfel {#configure-for-authentication-error}

När en webbplats har konfigurerats och publicerats [konfigurerar du inloggningsmappningen](sites-console.md#configure-for-authentication-error) ( `Adobe Granite Login Selector Authentication Handler`) på publiceringsinstansen. Fördelen är att när inloggningsuppgifter inte anges korrekt kommer autentiseringsfelet att visa inloggningssidan för communitywebbplatsen igen med ett felmeddelande.

Lägg till en `Login Page Mapping` som

* /content/sites/enable/en/signin:/content/sites/enable/en

### (Valfritt) Ändra standardhemsidan {#optional-change-the-default-home-page}

När du arbetar med publiceringswebbplatsen i demonstrationssyfte kan det vara praktiskt att ändra standardhemsidan till den nya webbplatsen.

Om du vill göra det måste du använda [CRX|DE](http://localhost:4503/crx/de) Lite för att redigera [resursmappningstabellen](../../help/sites-deploying/resource-mapping.md) vid publicering.

För att komma igång

1. Vid publicering får du åtkomst till CRXDE och loggar in med administratörsbehörighet

   * Gå till exempel till [http://localhost:4503/crx/de](http://localhost:4503/crx/de) och logga in med `admin/admin`

1. Utöka i projektwebbläsaren `/etc/map`
1. Markera `http` noden

   * Välj **[!UICONTROL Skapa nod]**

      * **Namn** localhost.4503

         (Använd *inte* `:`)

      * **textsling** : [mappning](https://sling.apache.org/documentation/the-sling-engine/mappings-for-resource-resolution.html)

1. Med den nyskapade `localhost.4503` noden markerad

   * Lägg till egenskap

      * **Namnsling** :match
      * **Type** String
      * **Värde** localhost.4503/\$

         (Måste sluta med tecknet &#39;$&#39;)
   * Lägg till egenskap

      * **Namnsling** :internalRedirect
      * **Type** String
      * **Värde** /content/sites/enable/en.html


1. Välj **[!UICONTROL Spara alla]**
1. (valfritt) Ta bort webbläsarhistoriken
1. Gå till http://localhost:4503/

   * Ankomst till http://localhost:4503/content/sites/enable/en.html

>[!NOTE]
>
>Om du vill inaktivera det lägger du bara till egenskapsvärdet med&quot;x&quot; - `sling:match` - och `xlocalhost.4503/$` Spara alla ****.

![chlimage_1-297](assets/chlimage_1-297.png)

#### Felsökning: Fel när kartan sparades {#troubleshooting-error-saving-map}

Om det inte går att spara ändringarna måste du kontrollera att nodnamnet är `localhost.4503`, med en punktavgränsare och inte `localhost:4503` med en kolonavgränsare, eftersom det inte `localhost`är ett giltigt namnområdesprefix.

![chlimage_1-298](assets/chlimage_1-298.png)

#### Felsökning: Det gick inte att omdirigera {#troubleshooting-fail-to-redirect}

&quot;**$**&quot; i slutet av `sling:match`strängen för det reguljära uttrycket är avgörande, så att bara exakt `http://localhost:4503/` mappas. I annat fall läggs omdirigeringsvärdet till alla sökvägar som kan finnas efter server:port i URL:en. När AEM försöker dirigera om till inloggningssidan misslyckas den således.

## Ändra communityplatsen {#modifying-the-community-site}

När webbplatsen har skapats kan författare använda ikonen [](sites-console.md#authoring-site-content) Open Site för att utföra vanliga AEM-redigeringsaktiviteter.

Dessutom kan administratörer använda ikonen [](sites-console.md#modifying-site-properties) Redigera plats för att ändra egenskaper för platsen, till exempel titeln.

Kom ihåg att **spara** och **publicera** webbplatsen igen efter eventuella ändringar.

>[!NOTE]
>
>Om du inte känner till AEM läser du dokumentationen om [grundläggande hantering](../../help/sites-authoring/basic-handling.md) och en [snabbguide till redigeringssidorna](../../help/sites-authoring/qg-page-authoring.md).

### Lägg till en katalog {#add-a-catalog}

Den communityplatsmall som valts för den här communitywebbplatsen bör innehålla katalogfunktionen.

Om inte kan du enkelt lägga till katalogfunktionen. På så sätt kan andra medlemmar i communityn, som inte är tilldelade till aktiveringsresurser eller en utbildningsväg, välja aktiveringsresurser från en katalog.

Om platsstrukturen redan innehåller katalogfunktionen kan dess namn ändras.

Om du vill ändra platsens struktur går du till konsolen **[!UICONTROL Webbplatser]** , öppnar `enable` mappen och väljer ikonen **Redigera plats** för att komma åt egenskaperna för `Enablement Tutorial`.

Välj STRUKTURpanelen om du vill lägga till en katalog eller ändra en befintlig katalog:

* **Titel**: `Ski Catalog`

* **URL**: `catalog`

* **Markera alla namnutrymmen**: lämna som standard.
* Välj **[!UICONTROL Spara]**

![chlimage_1-299](assets/chlimage_1-299.png)

Använd placeringsikonen för att flytta katalogfunktionen till den andra positionen, efter tilldelningar.

![chlimage_1-300](assets/chlimage_1-300.png)

Välj **[!UICONTROL Spara]** i det övre högra hörnet om du vill spara ändringarna på communitywebbplatsen.

Publicera sedan om **webbplatsen** .