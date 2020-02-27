---
title: Bloggfunktion
seo-title: Bloggfunktion
description: Community-information i ett journalformat
seo-description: Community-information i ett journalformat
uuid: 01f1a547-d22b-4da6-a69c-ab420e5a9e19
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: d5519211-8a04-4699-97bc-e162ec0f3781
translation-type: tm+mt
source-git-commit: 13d890d08a032fe4eef1dac793dcf2a3e682a52c

---


# Bloggfunktion {#blog-feature}

## Introduktion {#introduction}

Bloggfunktionen för AEM Communities har transformerats från en redigeringsaktivitet till en verklig communityaktivitet som äger rum i publiceringsmiljön.

Bloggfunktionen har stöd för att tillhandahålla communityinformation i journalformat. Bloggposterna görs i publiceringsmiljön av behöriga medlemmar (registrerade, inloggade användare).

Bloggfunktionen innehåller:

* Publicera och skapa bloggartiklar och kommentarer
* RTF-redigering
* Textbundna bilder (med stöd för dra och släpp)
* Inbäddat innehåll i sociala nätverk ([inbäddat stöd](blog-developer-basics.md#allowing-rich-media))
* Snabbläge
* Schemalagd publicering
* Disponera för (en [behörig medlem](users.md#privileged-members-group) kan skapa innehåll för en annan community-medlems räkning)
* [Sammanhangsberoende och gruppmoderering](moderate-ugc.md) av bloggartiklar och kommentarer

Detta avsnitt i dokumentationen beskriver

* Lägga till bloggfunktionen på en AEM-webbplats
* Konfigurationsinställningar för bloggkomponenter

>[!NOTE]
>
>Komponenterna `Journal`och `Journal Sidebar` kallas `Blog` och `Blog Sidebar`.
>
>Bloggfunktionen i AEM 6.0 och tidigare versioner har nu tagits bort. Det baserades på en mall och tilläts endast författare att skapa innehåll i författarmiljön.

## Lägga till bloggkomponenter på en sida {#adding-blog-components-to-a-page}

Om du vill lägga till en blogg på en sida i redigeringsläge använder du komponentwebbläsaren för att hitta

* `Communities / Blog`
* `Communities / Blog Sidebar`

Dra dem till en plats på en sida där bloggen ska visas.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](blog-developer-basics.md#essentials-for-client-side) inkluderas visas `Blog`komponenten så här:

![chlimage_1-147](assets/chlimage_1-147.png)

Och hur `Blog Sidebar` kommer att se ut:

![chlimage_1-148](assets/chlimage_1-148.png)

### Konfigurerar blogg {#configuring-blog}

Markera den monterade `Blog` komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![konfigurera](assets/chlimage_1-149.png) inställningar för ikoner ![i bloggen](assets/Blog-configure.png)

#### Fliken Inställningar {#settings-tab}

Ange bloggens grundläggande funktioner på fliken **[!UICONTROL Inställningar]** :

* **[!UICONTROL Tillåt miniatyrbild]** för bifogad fil Om det här alternativet är markerat skapas en miniatyrbild av den bifogade bilden.

* **[!UICONTROL Maximal storlek]** för miniatyrbildsminiatyr för bifogad miniatyrbild (i pixlar). Standardvärdet är 800 x 800.

* **[!UICONTROL Minsta bildstorlek för miniatyrbilder]** Minsta bildstorlek (i byte) för generering av miniatyrbilder för textbundna bilder. Standardvärdet är 100000 byte (100 kB).

* **[!UICONTROL Maximal miniatyrbildsstorlek]** Maximal storlek (i pixlar) för miniatyrbilden för textbunden bild. Standardvärdet är 800 x 800.

* **[!UICONTROL Tillåt behöriga medlemmar]** Om det här alternativet är markerat tillåts endast behöriga medlemmar att skapa innehåll.

* **[!UICONTROL Tillåtna behöriga medlemmar]** Lägg till behöriga medlemmar som har behörighet att skapa innehåll.

* **[!UICONTROL Blockera användargenererat innehåll i redigeringsläge]** Om det är aktiverat blockerar användargenererat innehåll när redigering pågår i redigeringsläget.

* **[!UICONTROL Journaltitel]** Den bloggtitel som ska visas på sidan.
   >Obs!
   >Journaltiteln används för att automatiskt skapa en URL för bloggen. Maximalt 50 tecken (med ytterligare 5 tecken för unikt utseende) används från journaltiteln som du anger här för att skapa en URL för bloggen.

* **[!UICONTROL Journalbeskrivning]** Bloggbeskrivningen.

* **[!UICONTROL Ämnen per sida]**

   Definierar antalet blogginlägg/kommentarer som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Kontrollerad]**

   Om du markerar det här alternativet måste du godkänna att blogginlägg och kommentarer skickas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Stängd]**

   Om du markerar det här alternativet stängs bloggen för nya blogginlägg och kommentarer. Standard är avmarkerat.

* **[!UICONTROL RTF-redigerare]**

   Om du markerar det här alternativet kan blogginlägg och kommentarer skrivas in med kod. Standard är markerat.

* **[!UICONTROL Tillåt taggning]**

   Om det här alternativet är markerat kan medlemmar lägga till taggetiketter i sina inlägg (se fliken **[!UICONTROL Taggfält]** ). Standard är avmarkerat.

* **[!UICONTROL Tillåt filöverföringar]**

   Om du markerar det här alternativet kan du tillåta att bifogade filer läggs till i ett blogginlägg eller en kommentar. Standard är avmarkerat.

* **[!UICONTROL Maximal filstorlek]**

   Relevant endast om `Allow File Uploads` är markerat. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Tillåtna filtyper]**

   Relevant endast om `Allow File Uploads` är markerat. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Maximal filstorlek för bifogad bild]**

   Endast relevant om Tillåt filöverföringar är markerat. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Tillåt svar]**

   Om det här alternativet är markerat tillåts svar på kommentarer som har skickats till blogginlägget. Standard är avmarkerat.

* **[!UICONTROL Tillåt användare att ta bort kommentarer och ämnen]**

   Om det här alternativet är markerat kan medlemmar ta bort kommentarer och blogginlägg som de har skickat in. Standard är avmarkerat.

* **[!UICONTROL Tillåt följande]**

   Om det här alternativet är markerat kan du inkludera följande funktion för bloggartiklar, som gör att medlemmar kan [meddelas](notifications.md) om nya inlägg. Standard är avmarkerat.

* **[!UICONTROL Tillåt e-postprenumerationer]**

   Om det här alternativet är markerat kan medlemmar meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver `Allow Following` att kontrolleras och att [e-post konfigureras](email.md). Standard är avmarkerat.

* **[!UICONTROL Tillåt röstning]**

   Om du markerar det här alternativet inkluderas röstningsfunktionen med ett blogginlägg. Standard är avmarkerat.

* **[!UICONTROL Visa emblem]**

   Om det här alternativet är markerat visas färdiga och tilldelade [märken](implementing-scoring.md) med en medlems blogginlägg. Standard är avmarkerat.

* **[!UICONTROL Tillåt innehåll]**

   om du markerar det här alternativet kan idén identifieras som [aktuellt innehåll](featured.md). Standard är avmarkerat.

#### Fliken Användarmoderering {#user-moderation-tab}

Under fliken **[!UICONTROL Användarmoderering]** anger du modereringsinställningarna:

* **[!UICONTROL Neka inlägg]**

   Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka inlägg och förhindra att posten visas på det offentliga forumet. Standard är avmarkerat.

* **[!UICONTROL Stäng/öppna avsnitt igen]**

   Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga ett ämne för ytterligare redigeringar och kommentarer, och kan även öppna ett avsnitt på nytt. Standard är avmarkerat.

* **[!UICONTROL Flagga inlägg]**

   Om det här alternativet är markerat kan medlemmar flagga andras ämnen eller kommentarer som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flaggorsakslista]**

   Om det här alternativet är markerat kan medlemmarna välja, från en nedrullningsbar lista, orsaken till att ett ämne eller en kommentar har flaggats som olämplig. Standard är avmarkerat.

* **[!UICONTROL Anledning till anpassad flagga]**

   Om det här alternativet är markerat kan medlemmarna ange en egen orsak till att ett ämne eller en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Modereringströskel]**

   Ange hur många gånger ett ämne eller en kommentar måste flaggas av medlemmar innan moderatorerna meddelas. Standardvärdet är 1 (en gång).

* **[!UICONTROL Flaggningsgräns]**

   Ange hur många gånger ett ämne eller en kommentar måste flaggas innan det döljs för den offentliga vyn. Om värdet är -1 döljs aldrig det flaggade ämnet eller kommentaren från den offentliga vyn. Annars måste talet vara större än eller lika med modereringströskeln. Standardvärdet är 5.

#### Fliken Taggfält {#tag-field-tab}

Under fliken **[!UICONTROL Tagg]** anger du vilka taggar som kan användas om **[!UICONTROL Tillåt taggning]** är markerat på fliken **[!UICONTROL Inställningar]** :

* **[!UICONTROL Tillåtna namnutrymmen]**

   Relevant om `Allow Tagging` är markerat under fliken **[!UICONTROL Inställningar]** . De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Förslagsgräns]**

   Ange antalet taggar som ska visas som ett förslag till medlemmens inlägg i forumet. Värdet -1 betyder inga gränser. Standardvärdet är 0.

### Konfigurerar bloggmarginallist {#configuring-blog-sidebar}

När du dubbelklickar på `Blog Sidebar` komponenten öppnas en redigeringsdialogruta.

Under fliken Inställningar **[!UICONTROL för]** journalmarginaler anger du datumformatet för arkiv och vilken typ av poster som ska visas i sidofältet:

![chlimage_1-151](assets/chlimage_1-151.png)

* **[!UICONTROL Datumformat]**

   Det format som används för att visa arkiv för blogginlägg. Formatet använder platshållare enligt Java-konventionen.

   * yyyy: hela året, till exempel 2015
   * yy: kort år, som &quot;15&quot;
   * MMMMM: hel månad, som juni
   * MMM: kort månad, som Jun
   * MM: månadsnummer, som 06
   Standardvärdet är&quot;yyyy MMMM&quot;, som skulle visas t.ex.&quot;2015 Juni&quot;

* **[!UICONTROL Vytyp]**

   Titel och typ av blogginlägg som ska visas i sidlisten. Valet är mellan

   *  Författare
   * Kategorier
   * Arkiv

* **[!UICONTROL Sökväg för journalkomponent]**

   *(Valfritt)* Platsen för den bloggresurs som bloggartiklar ska listas från. Om det lämnas tomt används komponenten för resourceType `social/journal/components/hbs/journal` som visas på samma sida.

   * Exempel, `/content/sites/engage/en/blog/jcr:content/content/primary/blog`

* **[!UICONTROL Förslagsgräns]**

   Antalet bloggartiklar som ska visas. Värdet -1 betyder ingen gräns. Standardvärdet är -1.

## Site Visitor Experience {#site-visitor-experience}

I publiceringsmiljön kommer bloggfunktionen att visa den senaste bloggartikeln följt av äldre bloggartiklar i fallande ordning. Bloggsidofälten gör att besökare kan använda filter för att begränsa urvalet av bloggartiklar.

Bloggartikeln följs av en länk för att skicka eller visa kommentarer.

När en bloggartikel är markerad visas bloggartikeln och kommentarerna (om den är aktiverad).

Andra funktioner beror på om besökaren är en moderator, administratör, community-medlem, privilegierad medlem eller anonym.

### Arbeta med artiklar {#working-with-articles}

När du skapar en ny bloggartikel kan du välja att

1. Publicera omedelbart
1. Publicera ett utkast
1. Publicera vid ett schemalagt datum och en schemalagd tidpunkt

Bloggartiklarna visas under lämplig flik (Publicerad, Utkast eller Schemalagd) för medlemmar som kan skriva vid publicering.

#### Styrelsemedlemmar och administratörer {#moderators-and-administrators}

När den inloggade användaren har moderator- eller administratörsbehörighet kan han/hon utföra [modereringsåtgärder](moderate-ugc.md) (som tillåts av komponentens konfiguration) på alla bloggartiklar och kommentarer som publiceras på en blogg.

![chlimage_1-152](assets/chlimage_1-152.png)

### Medlemmar {#members}

När den inloggade användaren är en community-medlem eller [behörig medlem](users.md#privileged-members-group) (beroende på konfiguration) kan användaren välja `New Article` att skapa och publicera en ny bloggartikel.

De får särskilt

* Skapa en ny bloggartikel
* Skicka en ny bloggartikel för en annan medlem
* Skicka en kommentar till en bloggartikel
* Redigera en egen bloggartikel eller kommentar
* Ta bort en egen bloggartikel eller kommentar
* Flagga andras blogginlägg eller kommentarer

![chlimage_1-153](assets/chlimage_1-153.png) ![chlimage_1-154](assets/chlimage_1-154.png)

### Anonym {#anonymous}

Besökare som inte är inloggade kan endast läsa inlagda bloggartiklar och kommentarer, översätta dem om de stöds, men kan inte lägga till en bloggartikel eller kommentar eller flagga andras artiklar eller kommentarer.

![chlimage_1-155](assets/chlimage_1-155.png)

## Additional Information {#additional-information}

Mer information finns på [Blog Essentials](blog-developer-basics.md) -sidan för utvecklare.

Mer information om moderering av blogginlägg och kommentarer finns i [Hantera användargenererat innehåll](moderate-ugc.md).

Information om hur du taggar blogginlägg och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).

Information om översättning av blogginlägg och kommentarer finns i [Översätta användargenererat innehåll](translate-ugc.md).
