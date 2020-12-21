---
title: Kalenderfunktion
seo-title: Kalenderfunktion
description: Tillhandahåller information om communityevent i ett kalenderformat
seo-description: Tillhandahåller information om communityevent i ett kalenderformat
uuid: 6f1f327f-bf4b-4357-b8fd-4bec74016921
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 8b8e74c5-8b65-4117-9ef0-da9d9e47191f
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60
workflow-type: tm+mt
source-wordcount: '1089'
ht-degree: 0%

---


# Kalenderfunktion {#calendar-feature}

## Introduktion {#introduction}

Kalenderfunktionen har stöd för att tillhandahålla information om communityevent i ett kalenderformat antingen för alla webbplatsbesökare eller endast för inloggade webbplatsbesökare (community-medlemmar), medan endast behöriga medlemmar kan lägga till händelser.

I det här avsnittet av dokumentationen beskrivs:

* Lägga till kalenderfunktionen på en AEM webbplats
* Konfigurationsinställningar för `Calendar`komponenter

## Lägga till en kalender på en sida {#adding-a-calendar-to-a-page}

Om du vill lägga till en `Calendar`-komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på

* `Communities / Calendar`

och dra den till rätt plats på en sida, t.ex. i förhållande till funktionen som användarna kan granska.

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](calendar-basics-for-developers.md#essentials-for-client-side) inkluderas visas `Calendar`-komponenten så här.

![chlimage_1-112](assets/chlimage_1-112.png)

### Konfigurerar kalendern {#configuring-calendar}

Markera den monterade `Calendar`komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-113](assets/chlimage_1-113.png) ![chlimage_1-114](assets/chlimage_1-114.png)

#### Fliken Inställningar {#settings-tab}

Under fliken **[!UICONTROL Settings]** anger du om du vill tillåta att taggar tillämpas på kalenderposter eller inte.

* **[!UICONTROL Events Per Page]**

   Definierar antalet händelser som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]**

   Om det här alternativet är markerat måste publicering av kalenderhändelser och kommentarer godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Closed]**

   Om du markerar det här alternativet stängs kalendern för nya händelseposter och kommentarer. Standard är avmarkerat.

* **[!UICONTROL Rich Text Editor]**

   Om det här alternativet är markerat kan kalenderhändelser och kommentarer infogas med markeringar. Standard är markerat.

* **[!UICONTROL Allow Tagging]**

   Om det här alternativet är markerat kan medlemmar lägga till taggetiketter i de händelser som de postar (se **Tagg field** tab). Standard är markerat.

* **[!UICONTROL Allow File Uploads]**

   Om du markerar det här alternativet kan du tillåta att bifogade filer läggs till i en kalenderhändelse eller kommentar. Standard är markerat.

* **[!UICONTROL Allow Following]**

   Om det här alternativet är markerat tillåter du medlemmar att följa händelser som har bokförts i kalendern. Standard är markerat.

* **[!UICONTROL Max File Size]**

   Endast relevant om `Allow File Uploads` är markerat. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**

   Endast relevant om `Allow File Uploads` är markerat. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Max Attach Image File Size]**

   Endast relevant om Tillåt filöverföringar är markerat. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Allowed Cover Image Types]**

   En kommaavgränsad lista med bildfilstillägg med&quot;punktavgränsaren&quot;. Standardvärdet är `.jpg,.jpeg,.png,.gif,.bmp`.

* **[!UICONTROL Allow Threaded Replies]**

   Om det här alternativet är markerat tillåts svar på kommentarer som har bokförts i kalenderhändelsen. Standard är markerat.

* **[!UICONTROL Allow Users to Delete Comments and Events]**

   Om det här alternativet är markerat kan medlemmar ta bort kommentarer och kalenderhändelser som de har bokfört. Standard är markerat.

* **[!UICONTROL Allow Voting]**

   Om du markerar det här alternativet inkluderas röstningsfunktionen med en kalenderhändelse. Standard är markerat.

* **[!UICONTROL Show Breadcrumbs]**

   Visa vägbeskrivningar på händelsesidan. Standard är markerat.

* **[!UICONTROL Date Range Filter]**

   Definierar antalet dagar som läggs till i det aktuella datumet för att beräkna Till-värdet för kalenderns sidfiltret för listsidan. Standardvärdet är 30.

* **[!UICONTROL Allow Featured Content]**

   Om det här alternativet är markerat kan idén identifieras som [aktuellt innehåll](featured.md). Standard är avmarkerat.

På fliken **[!UICONTROL User Moderation]** anger du hur publicerade ämnen och svar (användargenererat innehåll) ska hanteras. Mer information finns i [Moderating User Generated Content](moderate-ugc.md).

#### Fliken Användarmoderering {#user-moderation-tab}

* **[!UICONTROL Deny Posts]**

   Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka inlägg och förhindra att posten visas på det offentliga forumet. Standard är markerat.

* **[!UICONTROL Close/Reopen Events]**

   Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga en händelse för ytterligare redigeringar och kommentarer och även öppna en händelse igen. Standard är markerat.

* **[!UICONTROL Flag Posts]**

   Om det här alternativet är markerat kan medlemmar flagga andras händelser eller kommentarer som olämpliga. Standard är markerat.

* **[!UICONTROL Flag Reason List]**

   Om det här alternativet är markerat kan medlemmarna i en nedrullningsbar lista välja orsaken till att en händelse eller kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Custom Flag Reason]**

   Om det här alternativet är markerat kan medlemmarna ange en egen orsak till att en händelse eller kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Moderation Threshold]**

   Ange hur många gånger en händelse eller kommentar måste flaggas av medlemmar innan moderatorerna meddelas. Standardvärdet är 1 (en gång).

* **[!UICONTROL Flagging Limit]**

   Ange hur många gånger en händelse eller kommentar måste flaggas innan den döljs för den offentliga vyn. Om värdet är -1 döljs aldrig det flaggade ämnet eller kommentaren från den offentliga vyn. Annars måste talet vara större än eller lika med modereringströskeln. Standardvärdet är 5.

#### Tagg field tab {#tag-field-tab}

Under fliken **[!UICONTROL Tag field]** är de taggar som kan användas, om de tillåts under fliken **[!UICONTROL Settings]**, begränsade enligt de namnutrymmen som valts.

* **[!UICONTROL Allowed Namespaces]**

   Relevant om `Allow Tagging` är markerat under fliken **[!UICONTROL Settings]**. De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Suggestion Limit]**

   Ange antalet taggar som ska visas som ett förslag till medlemmens inlägg i forumet. Standardvärdet är `-1` (inga gränser).

>[!NOTE]
>
>Gå till [Administrera taggar](../../help/sites-administering/tags.md) om du vill veta hur du lägger till ett nytt taggnamnutrymme (taxonomi).

#### Översättningsflik {#translation-tab}

Om översättning är aktiverat för communitywebbplatsen på fliken **[!UICONTROL Translation]** kan översättning ställas in så att hela tråden (händelse och kommentarer) översätts i stället för specifika inlägg.

* **[!UICONTROL Translate All]**

   Om det här alternativet är markerat översätts händelsen och kommentarerna till användarens språk. Standard är markerat.

## Site Visitor Experience {#site-visitor-experience}

I publiceringsmiljön visar kalenderfunktionen ett sökfält med ett standarddatumintervall och alla kalenderhändelser som ligger inom det intervallet.

När en kalenderhändelse är markerad visas kalenderhändelseinformation, beskrivning och kommentarer.

Andra funktioner beror på om besökaren är en moderator, administratör, community-medlem, privilegierad medlem eller anonym.

### Moderatorer och administratörer {#moderators-and-administrators}

När den inloggade användaren har moderator- eller administratörsbehörighet kan han/hon utföra [modereringsåtgärder](moderate-ugc.md) (enligt komponentens konfiguration) för alla kalenderhändelser och kommentarer som publiceras till en händelse.

![chlimage_1-115](assets/chlimage_1-115.png)

### Medlemmar {#members}

När den inloggade användaren är en community-medlem eller [privilegierad medlem](users.md#privileged-members-group) (beroende på konfiguration) kan användaren välja `New Event` för att skapa och publicera en ny kalenderhändelse.

De kan

* Skapa en ny kalenderhändelse
* Publicera en kommentar i en kalenderhändelse
* Redigera en egen kalenderhändelse eller kommentar
* Ta bort en egen kalenderhändelse eller kommentar
* Flagga andras kalenderhändelser eller kommentarer

![chlimage_1-116](assets/chlimage_1-116.png) ![chlimage_1-117](assets/chlimage_1-117.png)

### Anonym {#anonymous}

Webbplatsbesökare som inte är inloggade kan bara läsa publicerade kalenderhändelser, översätta dem om de stöds, men kan inte lägga till en händelse eller kommentar eller flagga andras händelser eller kommentarer.

![chlimage_1-118](assets/chlimage_1-118.png)

## Ytterligare information {#additional-information}

Mer information finns på sidan [Calendar Essentials](calendar-basics-for-developers.md) för utvecklare.

moderering av kalenderhändelser och kommentarer finns i [Moderating User Generated Content](moderate-ugc.md).

Information om hur du taggar kalenderhändelser och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).

Översättning av kalenderhändelser och kommentarer finns i [Översätta användargenererat innehåll](translate-ugc.md).
