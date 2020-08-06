---
title: Idéfunktion
seo-title: Idéfunktion
description: Lägga till och konfigurera Ideation-funktionen
seo-description: Lägga till och konfigurera Ideation-funktionen
uuid: b21507da-10c8-4149-9e2c-a4ff5dec582b
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 7c0a9120-2edb-431b-b460-68398832d5ec
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 0%

---


# Idéfunktion {#ideation-feature}

## Introduktion {#introduction}

Idéfunktionen är ett område där besökare (community-medlemmar) som är inloggade kan publicera i publiceringsmiljön:

* Skapa idéer att dela med er av till communityn
* Visa och kommentera idéer
* Följ en idé
* Rösta på en idé

Detta avsnitt i dokumentationen beskriver

* Lägga till designfunktionen på en AEM
* Konfigurationsinställningar för Ideation-komponenten

## Lägga till en idé på en sida {#adding-a-ideation-to-a-page}

Om du vill lägga till en `Ideation` komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på `Communities / Ideation` och dra komponenten till en plats på en sida där idén ska visas.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](ideation.md#essentials-for-client-side) inkluderas visas `Ideation`komponenten så här:

![chlimage_1-29](assets/chlimage_1-29.png)

## Konfigurera en idé {#configuring-an-ideation}

Markera den monterade `Ideation` komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![chlimage_1-30](assets/chlimage_1-30.png) ![chlimage_1-31](assets/chlimage_1-31.png)

### Fliken Inställningar {#settings-tab}

Ange inställningar för idéer och kommentarer under **[!UICONTROL Settings]** fliken:

* **[!UICONTROL Ideation Title]**
Idéns visningsrubrik. Standard är 
`Ideation`.

* **[!UICONTROL Ideation Description]**
En beskrivning som ska visas som underrubrik till idén. Standardvärdet är ingen beskrivning.

* **[!UICONTROL Topics Per Page]**
Definierar antalet idéer/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]**
Om det här alternativet är markerat måste publicering av idéer och kommentarer godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Closed]**
Om det här alternativet är markerat är idéforumet stängt för nya idéer och kommentarer. Standard är avmarkerat.

* **[!UICONTROL Rich Text Editor]**
Om du markerar det här alternativet kan du lägga in kommentarer och idéer. Standard är avmarkerat.

* **[!UICONTROL Allow Tagging]**
Om det här alternativet är markerat kan medlemmar lägga till taggetiketter i sina inlägg (se **[!UICONTROL Tag field]** flik). Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om du markerar det här alternativet kan du tillåta att bifogade filer läggs till i idén eller kommentaren. Standard är avmarkerat.

* **[!UICONTROL Max File Size]**
Endast relevant om 
`Allow File Uploads` är markerad. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**
Endast relevant om 
`Allow File Uploads` är markerad. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Max Attach Image File Size]**
Endast relevant om Tillåt filöverföringar är markerat. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Allow Replies]**
Om det här alternativet är markerat tillåts svar på kommentarer som har lagts till i idén. Standard är avmarkerat.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**
Om det här alternativet är markerat kan medlemmarna ta bort de kommentarer och idéer som de publicerat. Standard är avmarkerat.

* **[!UICONTROL Allow Following]**
Om du markerar det här alternativet inkluderas följande funktion för idéinlägg, som gör att medlemmar kan [meddelas](notifications.md) om nya inlägg. Standard är avmarkerat.

* **[!UICONTROL Allow Email Subscriptions]**
Om det här alternativet är markerat kan medlemmar meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver `Allow Following` att kontrolleras och att [e-post konfigureras](email.md). Standard är avmarkerat.

* **[!UICONTROL Allow Voting]**
Om det här alternativet är markerat tillåts omröstning om en idés kommentarer. Standard är avmarkerat.

* **[!UICONTROL Display Badges]**
Om det här alternativet är markerat visar du färdiga och tilldelade [märken](implementing-scoring.md) med en medlems idé. Standard är avmarkerat.

* **[!UICONTROL Allow Featured Content]**
om du markerar det här alternativet kan idén identifieras som [aktuellt innehåll](featured.md). Standard är avmarkerat.

### Fliken Användarmoderering {#user-moderation-tab}

Under **[!UICONTROL User Moderation]** fliken anger du hur publicerade idéer och kommentarer (användargenererat innehåll) ska hanteras. Mer information finns i [Hantera användargenererat innehåll](moderate-ugc.md).

* **[!UICONTROL Deny Posts]**
Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka inlägg och förhindra att posten visas på det offentliga forumet. Standard är avmarkerat.

* **[!UICONTROL Close / Reopen Topics]**
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

### Fliken Taggfält {#tag-field-tab}

Under **[!UICONTROL Tag field]** fliken är de taggar som kan användas, om de tillåts under **[!UICONTROL Settings]** fliken, begränsade enligt de namnutrymmen som har valts.

* **[!UICONTROL Allowed Namespaces]**
Relevant om 
`Allow Tagging` är markerat under fliken **Inställningar** . De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Suggestion Limit]**
Ange antalet taggar som ska visas som ett förslag till medlemmens inlägg i forumet. Värdet för 
**-** 1 betyder ingen gräns. Standardvärdet är 0.

### Fliken Sorteringsinställningar {#sort-settings-tab}

Under **[!UICONTROL Sort Settings]** fliken anger du hur de bokförda kommentarerna ska sorteras när de visas.

* **[!UICONTROL Sort By]**
Markera alla tillåtna sorteringsval: 
`Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standardvärdet är `Newest, Oldest, Last Updated`.

* **[!UICONTROL Set as Default]**
Dra nedåt om du vill välja något av de markerade sorteringsalternativen som ska visas som standard. Standard är 
`Newest`.

* **[!UICONTROL Select Time Options for Analytics Sorting]**
Dra ned för att välja något av 
`All, Last 24 Hours, Last 7 Days, Last 30 Days`. Standardvärdet är `All`.

## Site Visitor Experience {#site-visitor-experience}

### Skapar Idea {#creating-idea}

Precis som med alla communityfunktioner kan en besökare på webbplatsen endast läsa idéer och se andra åsikter (genom kommentarer och röstning/gilla-markeringar).

När medlemmen har loggat in kan han eller hon skapa en ny idé.

![chlimage_1-32](assets/chlimage_1-32.png)

Innan du skickar in en idé kan medlemmen spara ett utkast.

Genom att markera `Save as Draft` knappen sparas ett utkast.

![chlimage_1-33](assets/chlimage_1-33.png)

När du visar sparade utkast på `My Drafts` fliken väljer du `Read More` att återgå till redigeringsläget:

![chlimage_1-34](assets/chlimage_1-34.png)

#### Ge feedback {#providing-feedback}

När idén har publicerats kan andra medlemmar logga in, öppna idén ( `Read More`) och gilla idén, och på så sätt lägga till fler röster och göra kommentarer.

![chlimage_1-35](assets/chlimage_1-35.png)

### Additional Information {#additional-information}

Mer information finns på sidan [Ideation Essentials](ideation.md) för utvecklare.

Mer information om moderering av publicerade ämnen och kommentarer finns i [Hantera användargenererat innehåll](moderate-ugc.md).

Information om hur du taggar publicerade ämnen och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).
