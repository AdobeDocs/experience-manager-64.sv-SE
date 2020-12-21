---
title: Forumfunktion för frågor och svar
seo-title: Forumfunktion för frågor och svar
description: Lägga till QnA-forumfunktionen på en sida
seo-description: Lägga till QnA-forumfunktionen på en sida
uuid: 006c0bf0-c230-4890-8080-65651f4b4dac
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: bbbe32bb-9d97-461e-822f-a7ddc6c9f9ef
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60
workflow-type: tm+mt
source-wordcount: '1119'
ht-degree: 0%

---


# Forumfunktion för frågor och svar {#q-a-forum-feature}

## Introduktion {#introduction}

Forumfunktionen QnA (frågor och svar) ger ett område där communitymedlemmar kan ställa och besvara frågor:

* Skapa nya frågor
* Textbundna bilder (med stöd för dra och släpp)
* Visa och svara på frågor
* Sök efter en fråga
* Hjälp till att moderera QnA-innehållet
* Identifiera de bästa svaren
* Flytta QnA-frågor från en sida till en annan

Detta avsnitt i dokumentationen beskriver

* Lägga till QnA-forumfunktionen på en AEM
* Konfigurationsinställningar för `QnA`komponenten

## Lägga till ett fråge- och frågeforum på en sida {#adding-a-q-a-forum-to-a-page}

Om du vill lägga till en `QnA`-komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på `Communities / QnA` och dra den till rätt plats på en sida där QnA-forumet ska visas.

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](qna-essentials.md#essentials-for-client-side) inkluderas visas `QnA`-komponenten så här:

![chlimage_1-280](assets/chlimage_1-280.png)

### Konfigurerar QnA {#configuring-qna}

Markera den monterade `QnA`-komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-281](assets/chlimage_1-281.png) ![chlimage_1-282](assets/chlimage_1-282.png)

#### Fliken Inställningar {#settings-tab}

På fliken **[!UICONTROL Settings]** anger du inställningar för ämnen (frågor) och svar (svar):

* **[!UICONTROL Topics Per Page]**
Definierar antalet frågor/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]**
Om det här alternativet är markerat måste publicering av ämnen och kommentarer godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Closed]**
Om det här alternativet är markerat stängs forumet för nya frågor och kommentarer. Standard är avmarkerat.

* **[!UICONTROL Rich Text Editor]**
Om det här alternativet är markerat kan du skriva in ämnen och kommentarer med markeringar. Standard är avmarkerat.

* **[!UICONTROL Allow Tagging]**
Om det här alternativet är markerat kan medlemmar lägga till taggetiketter i sina inlägg (se  **[!UICONTROL Tag field]** flik). Standard är avmarkerat.

* **[!UICONTROL Allow File Uploads]**
Om du markerar det här alternativet kan du tillåta att bifogade filer läggs till i frågan eller kommentaren. Standard är avmarkerat.

* **[!UICONTROL Max File Size]**
Endast relevant om 
`Allow File Uploads` är markerad. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Allowed File Types]**
Endast relevant om 
`Allow File Uploads` är markerad. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Max Attach Image File Size]**
Endast relevant om Tillåt filöverföringar är markerat. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Allow Following]**
Om det här alternativet är markerat kan du inkludera följande funktion för foruminlägg, som gör att medlemmar kan  [](notifications.md) meddelas om nya inlägg. Standard är avmarkerat.

* **[!UICONTROL Allow Pinning]**
Om det här alternativet är markerat kan forumämnen fästas överst i ämneslistan. Standard är avmarkerat.

* **[!UICONTROL Allow Email Subscriptions]**
Om det här alternativet är markerat kan medlemmar meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver att `Allow Following` kontrolleras och [e-post konfigureras](email.md). Standard är avmarkerat.

* **[!UICONTROL Allow Replies]**
Om det här alternativet är markerat, tillåt svar på kommentarer som lagts in i frågan. Standard är avmarkerat.

* **[!UICONTROL Allow Users to Delete Comments and Topics]**
Om det här alternativet är markerat kan medlemmarna ta bort de kommentarer och frågor som de har skickat in. Standard är avmarkerat.

* **[!UICONTROL Allow Voting]**
Om du markerar det här alternativet inkluderas röstningsfunktionen med en fråga. Standard är avmarkerat.

* **[!UICONTROL Move Selected Answer To The Top]**
Om det här alternativet är markerat är det första svar som visas ett valt svar. Standard är markerat.

* **[!UICONTROL Display Badges]**
Om det här alternativet är markerat visas intjänade och tilldelade  [](implementing-scoring.md) märken med en medlems blogginlägg. Standard är avmarkerat.

* **[!UICONTROL Allow Featured Content]**
om du markerar det här alternativet kan idén identifieras som  [aktuellt innehåll](featured.md). Standard är avmarkerat.

#### Fliken Användarmoderering {#user-moderation-tab}

Under fliken **[!UICONTROL User Moderation]** anger du hur de bokförda avsnitten (frågor) och svaren (användargenererat innehåll) ska hanteras. Mer information finns i [Moderating User Generated Content](moderate-ugc.md).

* **[!UICONTROL Deny Answers]**
Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka publicerade svar och förhindra att svaret visas på det offentliga forumet för frågor och svar. Standard är avmarkerat.

* **[!UICONTROL Close / Reopen Topics]**
Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga en fråga (ämne) för ytterligare redigeringar och svar och kan även öppna en fråga igen. Standard är avmarkerat.

* **[!UICONTROL Move Topics]**
Om det här alternativet är markerat kan du tillåta moderatorer på publiceringssidan att flytta frågor. Standard är avmarkerat.

* **[!UICONTROL Flag Posts]**
Om det här alternativet är markerat kan medlemmarna flagga andras frågor eller svar som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flag Reason List]**
Om det här alternativet är markerat kan medlemmarna i en nedrullningsbar lista välja orsaken till att en fråga eller ett svar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Custom Flag Reason]**
Om det här alternativet är markerat kan medlemmarna ange en egen orsak till att en fråga eller ett svar flaggas som olämpligt. Standard är avmarkerat.

* **[!UICONTROL Moderation Threshold]**
Ange hur många gånger en fråga eller ett svar måste flaggas av medlemmar innan moderatorerna meddelas. Standardvärdet är 1 (en gång).

* **[!UICONTROL Flagging Limit]**
Ange hur många gånger en fråga eller ett svar måste flaggas innan det döljs för den offentliga vyn. Om värdet är -1 döljs aldrig den flaggade frågan eller svaret från den offentliga vyn. Annars måste talet vara större än eller lika med modereringströskeln. Standardvärdet är 5.

#### Tagg field tab {#tag-field-tab}

Under fliken **[!UICONTROL Tag field]** är de taggar som kan användas, om de tillåts under fliken **[!UICONTROL Settings]**, begränsade enligt de namnutrymmen som valts.

* **[!UICONTROL Allowed Namespaces]**
Relevant om 
`Allow Tagging` kontrolleras under fliken  **** Inställningar. De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Suggestion Limit]**
Ange antalet taggar som ska visas som ett förslag till medlemmens inlägg i forumet. Värdet för 
`-1` innebär inga gränser. Standardvärdet är 0.

#### Fliken Sorteringsinställningar {#sort-settings-tab}

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

## Site Visitor Experience {#site-visitor-experience}

### Identifierar svar {#identifying-answers}

Ett svar kan markeras som ett korrekt eller användbart svar med knappen `Select Answer`. När en fråga har markerats som besvarad kan du inte välja ett annat svar förrän det första har avmarkerats med knappen `Unmark Chosen Answer`.

När det har valts som ett möjligt svar kan det avmarkeras med knappen `Unmark Chosen Answer`.

När ett svar har valts som ett möjligt svar visas en indikation på att frågan har `Answered`bredvid frågeämnet på QnA-huvudsidan.

### Moderatorer och administratörer {#moderators-and-administrators}

När den inloggade användaren har moderator- eller administratörsbehörighet kan de utföra de modereringsåtgärder som tillåts av komponentens konfiguration, oavsett vem som skapade frågan eller svaret.

De kan också identifiera svaren.

### Medlemmar {#members}

När besökaren är inloggad, beroende på konfigurationen, kan de

* Lägg upp en ny fråga
* Redigera eller ta bort frågor som de skapat
* Kan även flagga andras frågor eller svar
* Kan identifiera svar på frågor de skapat

### Anonym {#anonymous}

Besökare som inte är inloggade kan endast läsa frågor och svar, översätta dem om de stöds, men kan inte lägga till en fråga eller ett svar, eller flagga andras inlägg.

## Ytterligare information {#additional-information}

Mer information finns på sidan [QnA Essentials](qna-essentials.md) för utvecklare.

moderering av publicerade ämnen och kommentarer finns i [Moderating User Generated Content](moderate-ugc.md).

Information om hur du taggar publicerade ämnen och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).
