---
title: Forumfunktion
seo-title: Forum Feature
description: Lägga till och konfigurera forumfunktionen
seo-description: How to add and configure the forum feature
uuid: ced860ef-6f8a-4df2-acc8-6a48140fca83
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 3495f983-d71e-4704-be4e-8a42a63f72db
exl-id: fa6f28b4-3217-4b6a-b223-506da0ecca9e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '984'
ht-degree: 0%

---

# Forumfunktion {#forum-feature}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

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
* Konfigurationsinställningar för `Forum`komponent

## Lägga till ett forum på en sida {#adding-a-forum-to-a-page}

Lägga till en `Forum` -komponent till en sida i redigeringsläge använder du komponentwebbläsaren för att leta upp

* `Communities / Forum`

Och dra den till rätt plats på en sida där forumet ska visas.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](essentials-forum.md#essentials-for-client-side) ingår så här `Forum`visas:

![chlimage_1-60](assets/chlimage_1-60.png)

## Konfigurera ett forum {#configuring-a-forum}

Markera den monterade `Forum` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-61](assets/chlimage_1-61.png) ![chlimage_1-62](assets/chlimage_1-62.png)

### Fliken Inställningar {#settings-tab}

Under **[!UICONTROL Settings]** -fliken, ange inställningar för ämnen och svar:

* **[!UICONTROL Topics Per Page]**
Definierar antalet ämnen/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]**
Om det här alternativet är markerat måste publicering av ämnen och kommentarer godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Closed]**
Om det här alternativet är markerat stängs forumet för nya ämnen och kommentarer. Standard är avmarkerat.

* **[!UICONTROL Rich Text Editor]**
Om det här alternativet är markerat kan du skriva in ämnen och kommentarer med markeringar. Standard är avmarkerat.

* **[!UICONTROL Allow Tagging]**
Om det här alternativet är markerat kan medlemmar lägga till taggetiketter i sina inlägg (se **[!UICONTROL Tag field]** -fliken). Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om du markerar det här alternativet kan du tillåta att bifogade filer läggs till i ämnet eller kommentaren. Standard är avmarkerat.

* **[!UICONTROL Allow Following]**
Om du markerar det här alternativet inkluderas följande funktion för foruminlägg, som gör att medlemmar kan [meddelad](notifications.md) av nya tjänster. Standard är avmarkerat.

* **[!UICONTROL Allow Pinning]**
Om det här alternativet är markerat kan forumämnen fästas överst i ämneslistan. Standard är avmarkerat.

* **[!UICONTROL Allow Featured Content]**
om det är markerat kan idén identifieras som [innehåll](featured.md). Standard är avmarkerat.

* **[!UICONTROL Allow Email Subscriptions]**
Om det här alternativet är markerat, tillåt medlemmar att meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver `Allow Following` ska kontrolleras och [e-post konfigurerad](email.md). Standard är avmarkerat.

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
Om det här alternativet är markerat visas intjänad och tilldelad [emblem](implementing-scoring.md) med en medlems blogginlägg. Standard är avmarkerat.

>[!NOTE]
>
>Det kan vara nödvändigt att kontrollera båda `AllowThreaded Replies` och `Allow users to Delete Comments and Topics` för att aktivera kommentarer om ett ämne.

### Fliken Användarmoderering {#user-moderation-tab}

Under **[!UICONTROL User Moderation]** anger du hur publicerade ämnen och svar (användargenererat innehåll) ska hanteras. Mer information finns i [Modererar användargenererat innehåll](moderate-ugc.md).

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

### Fliken Taggfält {#tag-field-tab}

Under **[!UICONTROL Tag field]** -fliken, de taggar som kan användas, om de tillåts under **[!UICONTROL Settings]** är begränsade enligt de namnutrymmen som har valts.

* **[!UICONTROL Allowed Namespaces]**
Relevant om `Allow Tagging` kontrolleras under **[!UICONTROL Settings]** -fliken. De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Suggestion Limit]**
Ange antalet taggar som ska visas som ett förslag till medlemmens inlägg i forumet. Standard är 
**-** 1 (inga gränser).

### Fliken Översättning {#translation-tab}

Under **[!UICONTROL Translation]** om översättning är aktiverat för communitywebbplatsen kan översättning ställas in för att översätta hela ämnet eller valda inlägg.

* **[!UICONTROL Translate All]**
Om det här alternativet är markerat översätts forumtråden till användarens önskade språk. Standard är avmarkerat.

### Fliken Sorteringsinställningar {#sort-settings-tab}

Under **[!UICONTROL Sort Settings]** anger du hur de bokförda kommentarerna ska sorteras när de visas.

* **[!UICONTROL Sort By]**
Markera alla tillåtna sorteringsval: 
`Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standard är `Newest, Oldest, Last Updated`.

* **[!UICONTROL Set as Default]**
Dra nedåt om du vill välja något av de markerade sorteringsalternativen som ska visas som standard. Standard är 
`Newest`.

* **[!UICONTROL Select Time Options for Analytics Sorting]**
Dra ned för att välja något av 
`All, Last 24 Hours, Last 7 Days, Last 30 Days`. Standard är `All`.

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande om forum](essentials-forum.md) för utvecklare.

moderering av inlägg och kommentarer finns i [Modererar användargenererat innehåll](moderate-ugc.md).

Information om hur du taggar publicerade ämnen och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).

För översättning av publicerade ämnen och kommentarer, se [Översätter användargenererat innehåll](translate-ugc.md).
