---
title: Bloggfunktion
seo-title: Blog Feature
description: Community-information i ett journalformat
seo-description: Community information in a journaling format
uuid: 01f1a547-d22b-4da6-a69c-ab420e5a9e19
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: d5519211-8a04-4699-97bc-e162ec0f3781
exl-id: 12ae8b4c-73c5-4ec9-beea-b682b55ebdfd
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1510'
ht-degree: 0%

---

# Bloggfunktion {#blog-feature}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

Bloggfunktionen för AEM Communities har transformerats från en redigeringsaktivitet till en verklig community-aktivitet som äger rum i publiceringsmiljön.

Bloggfunktionen har stöd för att tillhandahålla communityinformation i journalformat. Bloggposterna görs i publiceringsmiljön av behöriga medlemmar (registrerade, inloggade användare).

Bloggfunktionen innehåller:

* Publicera och skapa bloggartiklar och kommentarer
* RTF-redigering
* Textbundna bilder (med stöd för dra och släpp)
* Inbäddat innehåll i sociala nätverk ([Stöd för inbäddning](blog-developer-basics.md#allowing-rich-media))
* Snabbläge
* Schemalagd publicering
* Skapa för räkning (en [behörig medlem](users.md#privileged-members-group) kan skapa innehåll för en annan community-medlems räkning)
* [Kontext- och gruppmoderering](moderate-ugc.md) bloggartiklar och kommentarer

Detta avsnitt i dokumentationen beskriver

* Lägga till bloggfunktionen på en AEM webbplats
* Konfigurationsinställningar för bloggkomponenter

>[!NOTE]
>
>Komponenterna `Journal`och `Journal Sidebar` är namngivna `Blog` och `Blog Sidebar`.
>
>Bloggfunktionen i AEM 6.0 och tidigare versioner har nu tagits bort. Det baserades på en mall och tilläts endast författare att skapa innehåll i författarmiljön.

## Lägga till bloggkomponenter på en sida {#adding-blog-components-to-a-page}

Om du vill lägga till en blogg på en sida i redigeringsläge använder du komponentwebbläsaren för att hitta

* `Communities / Blog`
* `Communities / Blog Sidebar`

Dra dem till en plats på en sida där bloggen ska visas.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](blog-developer-basics.md#essentials-for-client-side) ingår så här `Blog`visas:

![chlimage_1-147](assets/chlimage_1-147.png)

Och hur `Blog Sidebar` visas:

![chlimage_1-148](assets/chlimage_1-148.png)

### Konfigurerar blogg {#configuring-blog}

Markera den monterade `Blog` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![konfigurera ikon](assets/chlimage_1-149.png) ![Blogginställningar](assets/Blog-configure.png)

#### Fliken Inställningar {#settings-tab}

Under **[!UICONTROL Settings]** anger du bloggens grundläggande funktioner:

* **[!UICONTROL Allow Attachment Thumbnail]**
Om du markerar det här alternativet skapas en miniatyrbild av den bifogade bilden.

* **[!UICONTROL Max Attach Thumbnail Size]**
Maximal storlek (i pixlar) för miniatyrbilden för den bifogade filen. Standardvärdet är 800 x 800.

* **[!UICONTROL Min Image Size for Thumbnail]**
Minsta bildstorlek (i byte) för generering av miniatyrbilder för textbundna bilder. Standardvärdet är 100000 byte (100 kB).

* **[!UICONTROL Max Thumbnail Size]**
Maximal storlek (i pixlar) för miniatyrbilden för textbunden bild. Standardvärdet är 800 x 800.

* **[!UICONTROL Allow Privileged Members]**
Om det här alternativet är markerat kan endast behöriga medlemmar skapa innehåll.

* **[!UICONTROL Allowed Privileged Members]**
Lägg till de behöriga medlemmar som har behörighet att skapa innehåll.

* **[!UICONTROL Block User Generated Content in Author Edit Mode]**
Om det här alternativet är aktiverat blockeras användargenererat innehåll när redigering i redigeringsläge.

* **[!UICONTROL Journal Title]**
Den bloggtitel som ska visas på sidan.
   >Obs!
   >Journaltiteln används för att automatiskt skapa en URL för bloggen. Maximalt 50 tecken (med ytterligare 5 tecken för unikt utseende) används från journaltiteln som du anger här för att skapa en URL för bloggen.

* **[!UICONTROL Journal Description]**
Bloggbeskrivningen.

* **[!UICONTROL Topics Per Page]**

   Definierar antalet blogginlägg/kommentarer som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]**

   Om du markerar det här alternativet måste du godkänna att blogginlägg och kommentarer skickas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Closed]**

   Om du markerar det här alternativet stängs bloggen för nya blogginlägg och kommentarer. Standard är avmarkerat.

* **[!UICONTROL Rich Text Editor]**

   Om du markerar det här alternativet kan blogginlägg och kommentarer skrivas in med kod. Standard är markerat.

* **[!UICONTROL Allow Tagging]**

   Om det här alternativet är markerat kan medlemmar lägga till taggetiketter i sina inlägg (se **[!UICONTROL Tag field]** -fliken). Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**

   Om du markerar det här alternativet kan du tillåta att bifogade filer läggs till i ett blogginlägg eller en kommentar. Standard är avmarkerat.

* **[!UICONTROL Max File Size]**

   Endast relevant om `Allow File Uploads` är markerad. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**

   Endast relevant om `Allow File Uploads` är markerad. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Max Attach Image File Size]**

   Endast relevant om Tillåt filöverföringar är markerat. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Allow Replies]**

   Om det här alternativet är markerat tillåts svar på kommentarer som har skickats till blogginlägget. Standard är avmarkerat.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**

   Om det här alternativet är markerat kan medlemmar ta bort kommentarer och blogginlägg som de har skickat in. Standard är avmarkerat.

* **[!UICONTROL Allow Following]**

   Om du markerar det här alternativet inkluderar du följande funktion för bloggartiklar, som gör att medlemmar kan [meddelad](notifications.md) av nya tjänster. Standard är avmarkerat.

* **[!UICONTROL Allow Email Subscriptions]**

   Om det här alternativet är markerat, tillåt medlemmar att meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver `Allow Following` ska kontrolleras och [e-post konfigurerad](email.md). Standard är avmarkerat.

* **[!UICONTROL Allow Voting]**

   Om du markerar det här alternativet inkluderas röstningsfunktionen med ett blogginlägg. Standard är avmarkerat.

* **[!UICONTROL Display Badges]**

   Om det här alternativet är markerat visas intjänad och tilldelad [emblem](implementing-scoring.md) med en medlems blogginlägg. Standard är avmarkerat.

* **[!UICONTROL Allow Featured Content]**

   om det är markerat kan idén identifieras som [innehåll](featured.md). Standard är avmarkerat.

#### Fliken Användarmoderering {#user-moderation-tab}

Under **[!UICONTROL User Moderation]** anger du modereringsinställningar:

* **[!UICONTROL Deny Posts]**

   Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka inlägg och förhindra att posten visas på det offentliga forumet. Standard är avmarkerat.

* **[!UICONTROL Close/Reopen Topics]**

   Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga ett ämne för ytterligare redigeringar och kommentarer, och kan även öppna ett avsnitt på nytt. Standard är avmarkerat.

* **[!UICONTROL Flag Posts]**

   Om det här alternativet är markerat kan medlemmar flagga andras ämnen eller kommentarer som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flag Reason List]**

   Om det här alternativet är markerat kan medlemmarna välja, från en nedrullningsbar lista, orsaken till att ett ämne eller en kommentar har flaggats som olämplig. Standard är avmarkerat.

* **[!UICONTROL Custom Flag Reason]**

   Om det här alternativet är markerat kan medlemmarna ange en egen orsak till att ett ämne eller en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Moderation Threshold]**

   Ange hur många gånger ett ämne eller en kommentar måste flaggas av medlemmar innan moderatorerna meddelas. Standardvärdet är 1 (en gång).

* **[!UICONTROL Flagging Limit]**

   Ange hur många gånger ett ämne eller en kommentar måste flaggas innan det döljs för den offentliga vyn. Om värdet är -1 döljs aldrig det flaggade ämnet eller kommentaren från den offentliga vyn. Annars måste talet vara större än eller lika med modereringströskeln. Standardvärdet är 5.

#### Fliken Taggfält {#tag-field-tab}

Under **[!UICONTROL Tag field]** anger du vilka taggar som ska användas om **[!UICONTROL Allow Tagging]** kontrolleras på **[!UICONTROL Settings]** tab:

* **[!UICONTROL Allowed Namespaces]**

   Relevant om `Allow Tagging` kontrolleras under **[!UICONTROL Settings]** -fliken. De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Suggestion Limit]**

   Ange antalet taggar som ska visas som ett förslag till medlemmens inlägg i forumet. Värdet -1 betyder inga gränser. Standardvärdet är 0.

### Konfigurerar bloggmarginallist {#configuring-blog-sidebar}

När du dubbelklickar på `Blog Sidebar` öppnas en redigeringsdialogruta.

Under **[!UICONTROL Journal Sidebar Settings]** anger du datumformatet för arkiv och vilken typ av poster som ska visas i sidofältet:

![chlimage_1-151](assets/chlimage_1-151.png)

* **[!UICONTROL Date format]**

   Det format som används för att visa arkiv för blogginlägg. Formatet använder platshållare enligt Java-konventionen.

   * yyyy: hela året, till exempel 2015
   * yy: kort år, som &quot;15&quot;
   * MMMMM: hel månad, som juni
   * MMM: kort månad, som Jun
   * MM: månadsnummer, som 06

   Standardvärdet är&quot;yyyy MMMM&quot;, som skulle visas t.ex.&quot;2015 Juni&quot;

* **[!UICONTROL View Type]**

   Titel och typ av blogginlägg som ska visas i sidlisten. Valet är mellan

   * Författare
   * Kategorier
   * Arkiv

* **[!UICONTROL Journal Component Path]**

   *(Valfritt)* Platsen för bloggresursen som bloggartiklar ska listas från. Om det lämnas tomt används komponenten för resourceType `social/journal/components/hbs/journal` som visas på samma sida.

   * Till exempel, `/content/sites/engage/en/blog/jcr:content/content/primary/blog`

* **[!UICONTROL Suggestion Limit]**

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

När den inloggade användaren har behörighet som moderator eller administratör kan de utföra [modereringsuppgifter](moderate-ugc.md) (enligt komponentens konfiguration) på alla bloggartiklar och kommentarer som har skickats till en blogg.

![chlimage_1-152](assets/chlimage_1-152.png)

### Medlemmar {#members}

När den inloggade användaren är en community-medlem eller [behörig medlem](users.md#privileged-members-group) (beroende på konfiguration) kan de välja `New Article` för att skapa och publicera en ny bloggartikel.

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

## Ytterligare information {#additional-information}

Mer information finns på [Blog Essentials](blog-developer-basics.md) för utvecklare.

Mer information om moderering av blogginlägg och kommentarer finns i [Modererar användargenererat innehåll](moderate-ugc.md).

Information om hur du taggar blogginlägg och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).

Information om översättning av blogginlägg och kommentarer finns i [Översätter användargenererat innehåll](translate-ugc.md).
