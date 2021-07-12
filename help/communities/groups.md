---
title: Community Groups Console
seo-title: Community Groups Console
description: Med gruppkonsolen kan du skapa communitygrupper
seo-description: Med gruppkonsolen kan du skapa communitygrupper
uuid: 7dac2d1b-78fc-4b39-a2cb-100f1e220c23
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 1293c01a-7308-494a-ab48-bd9938205b81
pagetitle: Community Groups Console
role: Admin
exl-id: f8f19ad6-d6cd-4abd-bc31-6baba3e0356e
source-git-commit: 3c050c33a384d586d74bd641f7622989dc1d6b22
workflow-type: tm+mt
source-wordcount: '1615'
ht-degree: 0%

---

# Community Groups Console {#community-groups-console}

Gruppkonsolen ger åtkomst till att skapa communitygrupper när en community-platses [mallstruktur](sites-console.md#step1) innehåller [gruppfunktionen](functions.md#groups-function).

* Grupper kan kapslas inom andra grupper. Detta inträffar när den nya gruppens [struktur](tools-groups.md) innehåller gruppfunktionen.
* Det finns bara en guide för att skapa grupper i författarmiljön som påminner om guiden Skapa webbplats.
* Om medlemmar kan skapa grupper från publiceringsmiljön eller inte kan konfigureras när en gruppfunktion läggs till i en community-webbplatsstruktur eller community-gruppstruktur.

Av de tre gruppmallarna som ingår är det bara mallen `Reference Group` som innehåller en gruppfunktion i sin struktur.

Flera aspekter av communitygrupper är:

* Skapande: ny grupp kan skapas vid författaren och eventuellt vid publicering
* Kontroll: gruppen kan vara öppen eller hemlig
* Kapsling: en grupp kan innehålla noll eller flera grupper

>[!NOTE]
>
>Community-grupper som skapats i publiceringsmiljön innan [Community Groups console](https://helpx.adobe.com/in/experience-manager/6-3/communities/using/version-history.html#FeaturePack1FP1) fanns, kommer inte att visas i Community Groups-konsolen och kan därför inte ändras med hjälp av konsolen.

>[!NOTE]
>
>Den här gruppkonsolen, som bara är tillgänglig från webbgruppskonsolen, ska inte blandas ihop med medlemskonsolen [Grupper console](members.md) för hantering av medlemsgrupper.
>
>Medlemsgrupper är användargrupper som är registrerade i publiceringsmiljön och som nås från författarmiljön med hjälp av [tunneltjänsten](deploy-communities.md#tunnel-service-on-author).

## Skapa grupp {#group-creation}

Så här kommer du åt gruppkonsolen:

* Logga in med administratörsbehörighet på författaren
* Från global navigering: **[!UICONTROL Communities > Sites]**
* Välj en befintlig community-webbplatsmapp för att öppna den
* Välj en instans av en community-plats i mappen

   * Strukturen på communitywebbplatsen måste innehålla en gruppfunktion
   * Skärmbilderna kommer från självstudiekursen Komma igång efter [att grupper har skapats vid publicering](published-site.md)

![chlimage_1-133](assets/chlimage_1-133.png)

Markera **[!UICONTROL Groups folder]** för att öppna den.

När de öppnas visas alla befintliga grupper, oavsett om de har skapats vid författare eller publicering.

Från den här gruppkonsolen går det att skapa nya grupper.

![chlimage_1-134](assets/chlimage_1-134.png)

* Välj knappen **[!UICONTROL Create Group]**

### Steg 1: Community-gruppmall {#step-community-group-template}

![flerspråkig grupp](assets/multilingualgroup.png)

* **[!UICONTROL Community Group Title]**: En visningsrubrik för gruppen.

   Titeln visas på den publicerade webbplatsen för gruppen.

* **[!UICONTROL Community Group Description]**: En beskrivning av gruppen.
* **[!UICONTROL Community Group Root]**: Rotsökvägen till gruppen.

   Standardroten är den överordnade platsen, men roten kan flyttas till valfri plats på webbplatsen. Vi rekommenderar inte att du ändrar den.

* **[!UICONTROL Additional Available Community Group Languages(s)]** meny: Använd listrutan för att välja tillgängliga språk för communitygrupper. Menyn innehåller alla språk som den överordnade communitywebbplatsen skapas i. Användarna kan välja mellan dessa språk för att skapa grupper i flera språkområden i det här steget. Samma grupp skapas på flera angivna språk i gruppkonsolen för respektive communityplats.

* **[!UICONTROL Community Group Name]**: Namnet på gruppens rotsida som visas i URL:en

   * Dubbelkontrollera namnet eftersom det inte är lätt att ändra efter att gruppen har skapats
   * Bas-URL:en visas under `Community Group Name`
   * Lägg till &quot;.html&quot; för en giltig URL

      *Till exempel*, `http://localhost:4502/content/sites/mysight/en/mygroup.html`

* **[!UICONTROL Community Group Template]** meny: Använd listrutan för att välja en tillgänglig mall för  [communitygrupper](tools.md).

### Steg 2: Design {#step-design}

#### SAMHÄLLSGRUPPTEMA {#community-group-theme}

![communitygrouptema](assets/communitygrouptheme.png)

Ramverket använder [Twitter Bootstrap](https://twitterbootstrap.org/) för att ge webbplatsen en responsiv, flexibel design. Ett av de många förinlästa Bootstrap-temana kan väljas för att formatera den valda communitygruppsmallen, eller så kan ett Bootstrap-tema överföras.

När du väljer det här alternativet överlagras temat med en ogenomskinlig blå bockmarkering.

Du kan välja ett tema som skiljer sig från den överordnade webbplatsens tema.

När communitywebbplatsen har publicerats går det att [redigera egenskaperna](#modifying-group-properties) och välja ett annat tema.

#### GEMENSKAPSGRUPPENS VARUMÄRKE {#community-group-branding}

![chlimage_1-135](assets/chlimage_1-135.png)

Webbplatsmärkning är en bild som visas som en rubrik högst upp på varje sida. Det går att visa en banderoll för gruppen som skiljer sig från andra webbplatssidor.

Bilden bör storleksändras så att den blir lika bred som den förväntade visningen av sidan i webbläsaren och 120 pixlar hög.

Tänk på följande när du skapar eller markerar en bild:

* Bildens höjd beskärs till 120 pixlar från bildens övre kant
* Bilden är fäst vid webbläsarfönstrets vänstra kant
* Det finns ingen storleksändring av bilden, så att när bildbredden är...

   * Bilden upprepas vågrätt under webbläsarens bredd
   * Bilden kommer att beskäras mer än webbläsarens bredd

### Steg 3: Inställningar {#step-settings}

#### MODERATION {#moderation}

![chlimage_1-136](assets/chlimage_1-136.png)

Som standard ärvs den överordnade communityplatsens lista över moderatorer.

Det går att lägga till moderatorer som är specifika för gruppen:

* Sök efter medlemmar (från publiceringsmiljön) för att lägga till dem som moderatorer

#### MEDLEMSKAP {#membership}

Med inställningen för medlemskap kan du välja ett av tre sätt att skydda en community-grupp.

![chlimage_1-137](assets/chlimage_1-137.png)

* Valfritt medlemskap

   Om du väljer det här alternativet är communitygruppen en offentlig grupp. Webbplatsmedlemmar kan delta i gruppen och publicera utan att explicit gå med i gruppen. Standard är valt.
* Obligatoriskt medlemskap

   om du väljer det här alternativet är communitygruppen en öppen grupp. Medlemmar på en community kan visa innehållet i gruppen, men måste gå med i gruppen innan de kan publicera innehållet. Medlemmar går med genom att välja knappen `Join` i publiceringsmiljön. Standard är inte valt.

* Begränsat medlemskap

   om du väljer det här alternativet är communitygruppen en hemlig grupp. Community-medlemmar måste uttryckligen bjudas in. Inbjudna medlemmar anges i sökrutan. Medlemmar kan läggas till senare med konsolerna [Medlemmar och grupper](members.md) i författarmiljön. Standard är inte valt.

#### MINIATYRBILD {#thumbnail}

![chlimage_1-138](assets/chlimage_1-138.png)

Miniatyrbilden är en bild som ska visas för gruppen vid författare och publicering.

Den optimala storleken för en gruppbild är 170 x 90 pixlar i ett bildformat som stöds (till exempel JPG eller PNG).

Om ingen bild läggs till visas en standardbild.

![chlimage_1-139](assets/chlimage_1-139.png)

### Steg 4: Skapa grupp {#step-create-group}

![chlimage_1-140](assets/chlimage_1-140.png)

Om det behövs justeringar använder du **Bakåt**-knappen för att göra dem.

När **Skapa** har valts och startats kan processen att skapa gruppen inte avbrytas.

När processen är klar visas kortet för den nya undercommunitywebbplatsen (gruppen) i konsolen Webbplatsgrupper, där författare kan lägga till sidinnehåll eller där administratörer kan ändra webbplatsens egenskaper.

![createcommunitygroup-1](assets/createcommunitygroup-1.png)

>[!NOTE]
>
>Gruppen skapas på alla språk enligt [steg 1: Community Group Template](groups.md#step1communitygrouptemplate) in Additional Available Community Group Languages, in the Community Groups console of the respective community sites.

## Innehåll för redigeringsgrupp {#authoring-group-content}

![chlimage_1-141](assets/chlimage_1-141.png)

Sidinnehållet i en grupp kan redigeras med samma verktyg som andra AEM. Om du vill öppna gruppen för redigering väljer du ikonen Öppna plats som visas när du håller pekaren över gruppkortet.

## Ändra gruppegenskaper {#modifying-group-properties}

Egenskaperna för en befintlig undergruppsplats, som anges när en community-grupp skapas, kan ändras genom att du väljer ikonen Redigera plats, som visas när du hovrar över gruppkortet:

![chlimage_1-142](assets/chlimage_1-142.png)

Information om följande egenskaper matchar beskrivningarna i [Gruppskapande](#group-creation)-avsnittet. Alla kapslade grupper kan ändras, oavsett om de har skapats i publiceringsmiljön eller författarmiljön.

![chlimage_1-143](assets/chlimage_1-143.png)

### Ändra grundläggande {#modify-basic}

På BASIC-panelen kan du ändra

* Gruppnamn
* Beskrivning av communitygrupp

Det går inte att ändra användargruppnamnet.

Om du väljer en annan mall för en community-grupp påverkas inte en befintlig community-gruppwebbplats eftersom det inte finns någon koppling mellan mallar och webbplatser.

I stället kan undergruppens [STRUKTUR](#modify-structure) ändras.

### Ändra struktur {#modify-structure}

STRUKTURpanelen gör det möjligt att ändra den struktur som ursprungligen skapades från den community-gruppmall som valdes när undercommunitywebbplatsen skapades från antingen författaren eller publiceringsmiljön. På panelen kan du

* Dra och släpp ytterligare [communityfunktioner](functions.md) i webbplatsstrukturen
* En instans av en communityfunktion i webbplatsstrukturen:

   * **`gear icon`**

      Redigera inställningar, inklusive visningsrubrik och URL-namn samt [behöriga medlemsgrupper](users.md#privilegedmembersgroups)

   * **`trashcan icon`**

      Ta bort (ta bort) funktioner från platsstrukturen

   * **`grid icon`**

      Ändra ordningen på funktioner som visas i navigeringsfältet på den översta nivån

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

#### Exempel: Lägga till en kalenderfunktion i en undergruppsstruktur {#example-adding-a-calendar-function-to-a-sub-community-group-structure}

![chlimage_1-144](assets/chlimage_1-144.png)

### Ändra design {#modify-design}

På designpanelen kan du ändra temat:

* [Community-grupptema](#community-group-theme)
* [Varumärkning för communitygrupper](#community-group-branding)

   * Bläddra till panelens nedre del för att ändra varumärkesbilden

### Ändra inställningar {#modify-settings}

På inställningspanelen kan du lägga till community [moderatorer](#moderation).

### Ändra medlemskap {#modify-membership}

Panelen [MEDLEMSKAP](#membership) är endast informativ. Det är inte möjligt att ändra vilken typ av gruppmedlemskap som har upprättats, oavsett om det är valfritt, obligatoriskt eller begränsat.

### Ändra miniatyrbild {#modify-thumbnail}

På panelen [MINIATYRBILD](#thumbnail) kan en bild överföras för att representera communitygruppen för webbplatsbesökare i publiceringsmiljön samt i gruppkonsolen för Communities-webbplatsen i författarmiljön.

## Publicera gruppen {#publishing-the-group}

![chlimage_1-145](assets/chlimage_1-145.png)

När en community-grupp har skapats eller ändrats på nytt kan du publicera (aktivera) gruppen genom att välja ikonen `Publish Site`.

När gruppen har publicerats visas ett meddelande:

![chlimage_1-146](assets/chlimage_1-146.png)

>[!CAUTION]
>
>Den överordnade communitywebbplatsen och överordnade grupper ska redan ha publicerats.
>
>Community-webbplatsen och kapslade grupper bör publiceras uppifrån och ned.

## Ta bort gruppen {#deleting-the-group}

![deleteicon](assets/deleteicon.png)

Ta bort en grupp från gruppkonsolen genom att markera ikonen Ta bort grupp, som visas när du håller muspekaren över gruppen.

Detta tar bort alla objekt som är kopplade till gruppen, till exempel så tas allt innehåll i gruppen bort permanent och användarmedlemskap tas bort från systemet.
