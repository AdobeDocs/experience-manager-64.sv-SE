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

---


# Kalenderfunktion {#calendar-feature}

## Introduktion {#introduction}

Kalenderfunktionen har stöd för att tillhandahålla information om communityevent i ett kalenderformat antingen för alla webbplatsbesökare eller endast för inloggade webbplatsbesökare (community-medlemmar), medan endast behöriga medlemmar kan lägga till händelser.

I det här avsnittet av dokumentationen beskrivs:

* Lägga till kalenderfunktionen på en AEM-webbplats
* Konfigurationsinställningar för `Calendar`komponenter

## Lägga till en kalender på en sida {#adding-a-calendar-to-a-page}

Om du vill lägga till en `Calendar` komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på

* `Communities / Calendar`

och dra den till rätt plats på en sida, t.ex. i förhållande till funktionen som användarna kan granska.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](calendar-basics-for-developers.md#essentials-for-client-side) inkluderas visas `Calendar` komponenten på det här sättet.

![chlimage_1-112](assets/chlimage_1-112.png)

### Konfigurerar kalender {#configuring-calendar}

Markera den monterade `Calendar`komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![chlimage_1-113](assets/chlimage_1-113.png) ![chlimage_1-114](assets/chlimage_1-114.png)

#### Fliken Inställningar {#settings-tab}

Under fliken **[!UICONTROL Inställningar]** anger du om du vill tillåta att taggar används på kalenderposter eller inte.

* **[!UICONTROL Händelser per sida]**

   Definierar antalet händelser som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Kontrollerad]**

   Om det här alternativet är markerat måste publicering av kalenderhändelser och kommentarer godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Stängd]**

   Om du markerar det här alternativet stängs kalendern för nya händelseposter och kommentarer. Standard är avmarkerat.

* **[!UICONTROL RTF-redigerare]**

   Om det här alternativet är markerat kan kalenderhändelser och kommentarer infogas med markeringar. Standard är markerat.

* **[!UICONTROL Tillåt taggning]**

   Om det här alternativet är markerat kan medlemmar lägga till taggetiketter i de händelser som de publicerar (se fliken **Tagg field** ). Standard är markerat.

* **[!UICONTROL Tillåt filöverföringar]**

   Om du markerar det här alternativet kan du tillåta att bifogade filer läggs till i en kalenderhändelse eller kommentar. Standard är markerat.

* **[!UICONTROL Tillåt följande]**

   Om det här alternativet är markerat tillåter du medlemmar att följa händelser som har bokförts i kalendern. Standard är markerat.

* **[!UICONTROL Maximal filstorlek]**

   Relevant endast om `Allow File Uploads` är markerat. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Tillåtna filtyper]**

   Relevant endast om `Allow File Uploads` är markerat. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Maximal filstorlek för bifogad bild]**

   Endast relevant om Tillåt filöverföringar är markerat. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Tillåtna omslagsbildtyper]**

   En kommaavgränsad lista med bildfilstillägg med&quot;punktavgränsaren&quot;. Standardvärdet är `.jpg,.jpeg,.png,.gif,.bmp`.

* **[!UICONTROL Tillåt kopplade svar]**

   Om det här alternativet är markerat tillåts svar på kommentarer som har bokförts i kalenderhändelsen. Standard är markerat.

* **[!UICONTROL Tillåt användare att ta bort kommentarer och händelser]**

   Om det här alternativet är markerat kan medlemmar ta bort kommentarer och kalenderhändelser som de har bokfört. Standard är markerat.

* **[!UICONTROL Tillåt röstning]**

   Om du markerar det här alternativet inkluderas röstningsfunktionen med en kalenderhändelse. Standard är markerat.

* **[!UICONTROL Visa vägbeskrivningar]**

   Visa vägbeskrivningar på händelsesidan. Standard är markerat.

* **[!UICONTROL Datumintervallfilter]**

   Definierar antalet dagar som läggs till i det aktuella datumet för att beräkna Till-värdet för kalenderns sidfiltret för listsidan. Standardvärdet är 30.

* **[!UICONTROL Tillåt innehåll]**

   Om du markerar det här alternativet kan idén identifieras som [aktuellt innehåll](featured.md). Standard är avmarkerat.

På fliken **[!UICONTROL Användarmoderering]** anger du hur publicerade ämnen och svar (användargenererat innehåll) ska hanteras. Mer information finns i [Hantera användargenererat innehåll](moderate-ugc.md).

#### Fliken Användarmoderering {#user-moderation-tab}

* **[!UICONTROL Neka inlägg]**

   Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka inlägg och förhindra att posten visas på det offentliga forumet. Standard är markerat.

* **[!UICONTROL Stäng/öppna händelser igen]**

   Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga en händelse för ytterligare redigeringar och kommentarer och även öppna en händelse igen. Standard är markerat.

* **[!UICONTROL Flagga inlägg]**

   Om det här alternativet är markerat kan medlemmar flagga andras händelser eller kommentarer som olämpliga. Standard är markerat.

* **[!UICONTROL Flaggorsakslista]**

   Om det här alternativet är markerat kan medlemmarna i en nedrullningsbar lista välja orsaken till att en händelse eller kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Anledning till anpassad flagga]**

   Om det här alternativet är markerat kan medlemmarna ange en egen orsak till att en händelse eller kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Modereringströskel]**

   Ange hur många gånger en händelse eller kommentar måste flaggas av medlemmar innan moderatorerna meddelas. Standardvärdet är 1 (en gång).

* **[!UICONTROL Flaggningsgräns]**

   Ange hur många gånger en händelse eller kommentar måste flaggas innan den döljs för den offentliga vyn. Om värdet är -1 döljs aldrig det flaggade ämnet eller kommentaren från den offentliga vyn. Annars måste talet vara större än eller lika med modereringströskeln. Standardvärdet är 5.

#### Fliken Taggfält {#tag-field-tab}

Under fliken **[!UICONTROL Tagg]** begränsas de taggar som kan användas, om de tillåts under fliken **[!UICONTROL Inställningar]** , enligt de namnutrymmen som valts.

* **[!UICONTROL Tillåtna namnutrymmen]**

   Relevant om `Allow Tagging` är markerat under fliken **[!UICONTROL Inställningar]** . De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Förslagsgräns]**

   Ange antalet taggar som ska visas som ett förslag till medlemmens inlägg i forumet. Standardvärdet är `-1` (inga gränser).

>[!NOTE]
>
>Gå till [Administrera taggar](../../help/sites-administering/tags.md) för att lära dig hur du lägger till ett nytt taggnamnutrymme (taxonomi).

#### Fliken Översättning {#translation-tab}

Om översättning är aktiverat för communitywebbplatsen på fliken **[!UICONTROL Översättning]** kan översättningen ställas in så att hela tråden (händelse och kommentarer) översätts i stället för specifika inlägg.

* **[!UICONTROL Översätt alla]**

   Om det här alternativet är markerat översätts händelsen och kommentarerna till användarens språk. Standard är markerat.

## Site Visitor Experience {#site-visitor-experience}

I publiceringsmiljön visar kalenderfunktionen ett sökfält med ett standarddatumintervall och alla kalenderhändelser som ligger inom det intervallet.

När en kalenderhändelse är markerad visas kalenderhändelseinformation, beskrivning och kommentarer.

Andra funktioner beror på om besökaren är en moderator, administratör, community-medlem, privilegierad medlem eller anonym.

### Styrelsemedlemmar och administratörer {#moderators-and-administrators}

När den inloggade användaren har moderator- eller administratörsbehörighet kan han/hon utföra [modereringsåtgärder](moderate-ugc.md) (som tillåts av komponentens konfiguration) för alla kalenderhändelser och kommentarer som publiceras till en händelse.

![chlimage_1-115](assets/chlimage_1-115.png)

### Medlemmar {#members}

När den inloggade användaren är en community-medlem eller [behörig medlem](users.md#privileged-members-group) (beroende på konfiguration) kan användaren välja `New Event` att skapa och publicera en ny kalenderhändelse.

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

## Additional Information {#additional-information}

Mer information finns på sidan [Calendar Essentials](calendar-basics-for-developers.md) för utvecklare.

Mer information om moderering av kalenderhändelser och kommentarer finns i [Hantera användargenererat innehåll](moderate-ugc.md).

Mer information om hur du taggar kalenderhändelser och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).

Översättning av kalenderhändelser och kommentarer finns i [Översätta användargenererat innehåll](translate-ugc.md).
