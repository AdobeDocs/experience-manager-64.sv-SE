---
title: Forumfunktion
seo-title: Forumfunktion
description: Lägga till och konfigurera forumfunktionen
seo-description: Lägga till och konfigurera forumfunktionen
uuid: ced860ef-6f8a-4df2-acc8-6a48140fca83
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 3495f983-d71e-4704-be4e-8a42a63f72db
translation-type: tm+mt
source-git-commit: 28948f1f8678512f8fc970a4289cb01cde86c5c2
workflow-type: tm+mt
source-wordcount: '958'
ht-degree: 0%

---


# Forumfunktion {#forum-feature}

## Introduktion {#introduction}

Forumfunktionen tillhandahåller ett område där besökare (community-medlemmar) som loggat in kan besöka webbplatsen i publiceringsmiljön:

* Skapa nya ämnen
* Visa och svara på ämnen
* Följ ett avsnitt
* Sök i ett forum
* Hjälp till att moderera foruminnehållet
* Flytta forumämnen från en sida till en annan

Detta avsnitt i dokumentationen beskriver

* Lägga till forumfunktionen på en AEM webbplats
* Konfigurationsinställningar för `Forum`komponenten

## Lägga till ett forum på en sida {#adding-a-forum-to-a-page}

Om du vill lägga till en `Forum`-komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på

* `Communities / Forum`

Och dra den till rätt plats på en sida där forumet ska visas.

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](essentials-forum.md#essentials-for-client-side) inkluderas visas `Forum`komponenten så här:

![chlimage_1-60](assets/chlimage_1-60.png)

## Konfigurera ett forum {#configuring-a-forum}

Markera den monterade `Forum`-komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-61](assets/chlimage_1-61.png) ![chlimage_1-62](assets/chlimage_1-62.png)

### Fliken Inställningar {#settings-tab}

Ange inställningar för ämnen och svar på fliken **[!UICONTROL Settings]**:

* **[!UICONTROL Topics Per Page]**
Definierar antalet ämnen/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]**
Om det här alternativet är markerat måste publicering av ämnen och kommentarer godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Closed]**
Om det här alternativet är markerat stängs forumet för nya ämnen och kommentarer. Standard är avmarkerat.

* **[!UICONTROL Rich Text Editor]**
Om det här alternativet är markerat kan du skriva in ämnen och kommentarer med markeringar. Standard är avmarkerat.

* **[!UICONTROL Allow Tagging]**
Om det här alternativet är markerat kan medlemmar lägga till taggetiketter i sina inlägg (se  **[!UICONTROL Tag field]** flik). Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om du markerar det här alternativet kan du tillåta att bifogade filer läggs till i ämnet eller kommentaren. Standard är avmarkerat.

* **[!UICONTROL Allow Following]**
Om det här alternativet är markerat kan du inkludera följande funktion för foruminlägg, som gör att medlemmar kan  [](notifications.md) meddelas om nya inlägg. Standard är avmarkerat.

* **[!UICONTROL Allow Pinning]**
Om det här alternativet är markerat kan forumämnen fästas överst i ämneslistan. Standard är avmarkerat.

* **[!UICONTROL Allow Featured Content]**
om du markerar det här alternativet kan idén identifieras som  [aktuellt innehåll](featured.md). Standard är avmarkerat.

* **[!UICONTROL Allow Email Subscriptions]**
Om det här alternativet är markerat kan medlemmar meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver att `Allow Following` kontrolleras och [e-post konfigureras](email.md). Standard är avmarkerat.

* **[!UICONTROL Max File Size]**
Endast relevant om 
`Allow File Uploads` är markerad. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**
Endast relevant om 
`Allow File Uploads` är markerad. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Max Attach Image File Size]**
Endast relevant om Tillåt filöverföringar är markerat. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Allow Threaded Replies]**
Om det här alternativet är markerat tillåts svar på kommentarer som har publicerats i ämnet. Standard är avmarkerat.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**
Om det här alternativet är markerat kan medlemmarna ta bort kommentarer och ämnen som de har skickat in. Standard är avmarkerat.

* **[!UICONTROL Allow Voting]**
Inkludera röstfunktionen med ett ämne om det är markerat. Standard är avmarkerat.

* **[!UICONTROL Show Breadcrumbs]**
Om du markerar det här alternativet visas navigeringsbeskrivningar på ämnessidor. Standard är markerat.

* **[!UICONTROL Display Badges]**
Om det här alternativet är markerat visas intjänade och tilldelade  [](implementing-scoring.md) märken med en medlems blogginlägg. Standard är avmarkerat.

>[!NOTE]
>
>Du kan behöva kontrollera både `AllowThreaded Replies` och `Allow users to Delete Comments and Topics` för att kunna aktivera kommentarer om ett ämne.

### Fliken Användarmoderering {#user-moderation-tab}

På fliken **[!UICONTROL User Moderation]** anger du hur publicerade ämnen och svar (användargenererat innehåll) ska hanteras. Mer information finns i [Moderating User Generated Content](moderate-ugc.md).

* **[!UICONTROL Deny Posts]**
Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka inlägg och förhindra att posten visas på det offentliga forumet. Standard är avmarkerat.

* **[!UICONTROL Close / Reopen Topics]**
Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga ett ämne för ytterligare redigeringar och kommentarer, och kan även öppna ett avsnitt på nytt. Standard är avmarkerat.

* **[!UICONTROL Move Topics]**
Om det här alternativet är markerat kan du tillåta moderatorer på publiceringssidan att flytta ämnen. Standard är markerat.

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

### Tagg field tab {#tag-field-tab}

Under fliken **[!UICONTROL Tag field]** är de taggar som kan användas, om de tillåts under fliken **[!UICONTROL Settings]**, begränsade enligt de namnutrymmen som valts.

* **[!UICONTROL Allowed Namespaces]**
Relevant om  `Allow Tagging` är markerat under  **[!UICONTROL Settings]** fliken. De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Suggestion Limit]**
Ange antalet taggar som ska visas som ett förslag till medlemmens inlägg i forumet. Standard är 
**-** 1 (inga gränser).

### Översättningsflik {#translation-tab}

Om översättning är aktiverat för communitywebbplatsen på fliken **[!UICONTROL Translation]** kan översättning ställas in för att översätta hela ämnet eller valda inlägg.

* **[!UICONTROL Translate All]**
Om det här alternativet är markerat översätts forumtråden till användarens önskade språk. Standard är avmarkerat.

### Fliken Sorteringsinställningar {#sort-settings-tab}

Under fliken **[!UICONTROL Sort Settings]** anger du hur de bokförda kommentarerna ska sorteras när de visas.

* **[!UICONTROL Sort By]**
Markera alla tillåtna sorteringsval: 
`Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standardvärdet är `Newest, Oldest, Last Updated`.

* **[!UICONTROL Set as Default]**
Dra nedåt om du vill välja något av de markerade sorteringsalternativen som ska visas som standard. Standard är 
`Newest`.

* **[!UICONTROL Select Time Options for Analytics Sorting]**
Dra ned för att välja något av 
`All, Last 24 Hours, Last 7 Days, Last 30 Days`. Standardvärdet är `All`.

## Ytterligare information {#additional-information}

Mer information finns på sidan [Forum Essentials](essentials-forum.md) för utvecklare.

moderering av publicerade ämnen och kommentarer finns i [Moderating User Generated Content](moderate-ugc.md).

Information om hur du taggar publicerade ämnen och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).

Översättning av publicerade ämnen och kommentarer finns i [Översätta användargenererat innehåll](translate-ugc.md).
