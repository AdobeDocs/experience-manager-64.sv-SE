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

* Lägga till forumfunktionen på en AEM-webbplats
* Konfigurationsinställningar för `Forum`komponenten

## Lägga till ett forum på en sida {#adding-a-forum-to-a-page}

Om du vill lägga till en `Forum` komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på

* `Communities / Forum`

Och dra den till rätt plats på en sida där forumet ska visas.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](essentials-forum.md#essentials-for-client-side) inkluderas visas `Forum`komponenten så här:

![chlimage_1-60](assets/chlimage_1-60.png)

## Konfigurera ett forum {#configuring-a-forum}

Markera den monterade `Forum` komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![chlimage_1-61](assets/chlimage_1-61.png) ![chlimage_1-62](assets/chlimage_1-62.png)

### Fliken Inställningar {#settings-tab}

Ange inställningar för ämnen och svar på fliken **[!UICONTROL Inställningar]** :

* **[!UICONTROL Ämnen per sida]** Definierar antalet ämnen/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]** Om det här alternativet är markerat måste publicering av ämnen och kommentarer godkännas innan de visas på en publiceringswebbplats. Standard är avmarkerat.

* **[!UICONTROL Stängt]** Om det här alternativet är markerat stängs forumet för nya ämnen och kommentarer. Standard är avmarkerat.

* **[!UICONTROL RTF-redigeraren]** Om det här alternativet är markerat kan du skriva in ämnen och kommentarer med markeringar. Standard är avmarkerat.

* **[!UICONTROL Tillåt taggning]** Om det här alternativet är markerat tillåter du medlemmar att lägga till taggetiketter i sitt inlägg (se fliken **[!UICONTROL Taggfält]** ). Standard är avmarkerat.

* **[!UICONTROL Tillåt filöverföringar]** Om det här alternativet är markerat tillåter du att bifogade filer läggs till i ämnet eller kommentaren. Standard är avmarkerat.

* **[!UICONTROL Tillåt följande]** om det är markerat, inkludera följande funktion för foruminlägg, som gör att medlemmar kan [meddelas](notifications.md) om nya inlägg. Standard är avmarkerat.

* **[!UICONTROL Tillåt fästa]** Om det här alternativet är markerat kan forumämnen fästas överst i ämneslistan. Standard är avmarkerat.

* **[!UICONTROL Tillåt innehåll]** om det är markerat kan idén identifieras som [aktuellt innehåll](featured.md). Standard är avmarkerat.

* **[!UICONTROL Tillåt e-postprenumerationer]** Om det här alternativet är markerat tillåter du medlemmar att meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver `Allow Following` att kontrolleras och att [e-post konfigureras](email.md). Standard är avmarkerat.

* **[!UICONTROL Maximal filstorlek]** relevant endast om `Allow File Uploads` markeras. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Tillåtna filtyper]**&#x200B;är bara relevanta om `Allow File Uploads` markeras. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Max Attach Image File Size]** Relevant only if Allow File Uploads is checked. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Tillåt kopplade svar]** Om det här alternativet är markerat tillåter du svar på kommentarer som publicerats i ämnet. Standard är avmarkerat.

* **[!UICONTROL Tillåt användare att ta bort kommentarer och ämnen]** Tillåt medlemmar att ta bort kommentarer och ämnen som de har skickat in om de är markerade. Standard är avmarkerat.

* **[!UICONTROL Tillåt röstning]** Om det här alternativet är markerat inkluderar du röstfunktionen med ett ämne. Standard är avmarkerat.

* **[!UICONTROL Visa vägbeskrivningar]** Om det här alternativet är markerat visas vägbeskrivningar av navigeringsinformation på ämnessidor. Standard är markerat.

* **[!UICONTROL Visa emblem]** Om det här alternativet är markerat visar du [märken](implementing-scoring.md) som tagits emot och tilldelats av en medlem i ett blogginlägg. Standard är avmarkerat.

>[!NOTE]
>
>Det kan vara nödvändigt att kontrollera både `AllowThreaded Replies` och `Allow users to Delete Comments and Topics` aktivera kommentarer om ett ämne.

### Fliken Användarmoderering {#user-moderation-tab}

På fliken **[!UICONTROL Användarmoderering]** anger du hur publicerade ämnen och svar (användargenererat innehåll) ska hanteras. Mer information finns i [Hantera användargenererat innehåll](moderate-ugc.md).

* **[!UICONTROL Neka inlägg]** Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka inlägg och förhindra att posten visas på det offentliga forumet. Standard är avmarkerat.

* **[!UICONTROL Stäng/öppna ämnen]** igen Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga ett avsnitt för ytterligare redigeringar och kommentarer och även öppna ett avsnitt på nytt. Standard är avmarkerat.

* **[!UICONTROL Flytta ämnen]** Om det är markerat tillåter du moderatorer på publiceringssidan att flytta ämnen. Standard är markerat.

* **[!UICONTROL Flagga inlägg]** Om det är markerat kan medlemmar flagga andras ämnen eller kommentarer som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flagga orsakslista]** Om det här alternativet är markerat kan medlemmarna välja, från en nedrullningsbar lista, orsaken till att ett ämne eller en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Anledning till anpassad flagga]** Om den är markerad kan medlemmar ange en egen orsak till att ett ämne eller en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Moderationströskel]** Ange hur många gånger ett ämne eller en kommentar måste flaggas av medlemmar innan moderatorerna meddelas. Standardvärdet är 1 (en gång).

* **[!UICONTROL Flaggningsgräns]** Ange hur många gånger ett ämne eller en kommentar måste flaggas innan det döljs för den offentliga vyn. Om värdet är -1 döljs aldrig det flaggade ämnet eller kommentaren från den offentliga vyn. Annars måste talet vara större än eller lika med modereringströskeln. Standardvärdet är 5.

### Fliken Taggfält {#tag-field-tab}

Under fliken **[!UICONTROL Tagg]** begränsas de taggar som kan användas, om de tillåts under fliken **[!UICONTROL Inställningar]** , enligt de namnutrymmen som valts.

* **[!UICONTROL Tillåtna]** relevanta namnutrymmen om `Allow Tagging` är markerat på fliken **[!UICONTROL Inställningar]** . De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Förslagsgräns]** Ange antalet taggar som ska visas som ett förslag till medlemmen som publicerar i forumet. Standardvärdet är **-** 1 (inga gränser).

### Fliken Översättning {#translation-tab}

Om översättning är aktiverat för communitywebbplatsen på fliken **[!UICONTROL Översättning]** kan översättning ställas in för att översätta hela ämnet eller valda inlägg.

* **[!UICONTROL Översätt alla]** Om det här alternativet är markerat översätts forumtråden till användarens önskade språk. Standard är avmarkerat.

### Fliken Sorteringsinställningar {#sort-settings-tab}

På fliken **[!UICONTROL Sorteringsinställningar]** anger du hur de skickade kommentarerna ska sorteras när de visas.

* **[!UICONTROL Sortera efter]** Markera alla tillåtna sorteringsval: `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standardvärdet är `Newest, Oldest, Last Updated`.

* **[!UICONTROL Ange som standard]** Dra nedåt om du vill välja något av de markerade sorteringsalternativen som ska visas som standard. Standardvärdet är `Newest`.

* **[!UICONTROL Välj Tidsalternativ för sortering]** i listrutan Analytics (Analyssortering) för att välja ett av `All, Last 24 Hours, Last 7 Days, Last 30 Days`. Standardvärdet är `All`.

## Additional Information {#additional-information}

Mer information finns på sidan [Forum Essentials](essentials-forum.md) för utvecklare.

Mer information om moderering av publicerade ämnen och kommentarer finns i [Hantera användargenererat innehåll](moderate-ugc.md).

Information om hur du taggar publicerade ämnen och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).

Översättning av publicerade ämnen och kommentarer finns i [Översätta användargenererat innehåll](translate-ugc.md).
