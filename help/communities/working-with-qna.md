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

* Lägga till QnA-forumfunktionen på en AEM-webbplats
* Konfigurationsinställningar för `QnA`komponenten

## Lägga till ett forum med frågor och svar på en sida {#adding-a-q-a-forum-to-a-page}

Om du vill lägga till en `QnA` komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på `Communities / QnA` och dra komponenten till en sida där QnA-forumet ska visas.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](qna-essentials.md#essentials-for-client-side) inkluderas visas `QnA` komponenten så här:

![chlimage_1-280](assets/chlimage_1-280.png)

### Konfigurera QnA {#configuring-qna}

Markera den monterade `QnA` komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![chlimage_1-281](assets/chlimage_1-281.png) ![chlimage_1-282](assets/chlimage_1-282.png)

#### Fliken Inställningar {#settings-tab}

Under fliken **[!UICONTROL Inställningar]** anger du inställningar för ämnen (frågor) och svar (svar):

* **[!UICONTROL Ämnen per sida]** Definierar antalet frågor/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]** Om det här alternativet är markerat måste publicering av ämnen och kommentarer godkännas innan de visas på en publiceringswebbplats. Standard är avmarkerat.

* **[!UICONTROL Stängt]** Om det här alternativet är markerat stängs forumet för nya frågor och kommentarer. Standard är avmarkerat.

* **[!UICONTROL RTF-redigeraren]** Om det här alternativet är markerat kan du skriva in ämnen och kommentarer med markeringar. Standard är avmarkerat.

* **[!UICONTROL Tillåt taggning]** Om det här alternativet är markerat tillåter du medlemmar att lägga till taggetiketter i sitt inlägg (se fliken **[!UICONTROL Taggfält]** ). Standard är avmarkerat.

* **[!UICONTROL Tillåt filöverföringar]** Om det här alternativet är markerat tillåter du att bifogade filer läggs till i frågan eller kommentaren. Standard är avmarkerat.

* **[!UICONTROL Maximal filstorlek]** relevant endast om `Allow File Uploads` markeras. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Tillåtna filtyper]**&#x200B;är bara relevanta om `Allow File Uploads` markeras. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Max Attach Image File Size]** Relevant only if Allow File Uploads is checked. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Tillåt följande]** om det är markerat, inkludera följande funktion för foruminlägg, som gör att medlemmar kan [meddelas](notifications.md) om nya inlägg. Standard är avmarkerat.

* **[!UICONTROL Tillåt fästa]** Om det här alternativet är markerat kan forumämnen fästas överst i ämneslistan. Standard är avmarkerat.

* **[!UICONTROL Tillåt e-postprenumerationer]** Om det här alternativet är markerat tillåter du medlemmar att meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver `Allow Following` att kontrolleras och att [e-post konfigureras](email.md). Standard är avmarkerat.

* **[!UICONTROL Tillåt svar]** Om det här alternativet är markerat tillåter du svar på kommentarer som skickats till frågan. Standard är avmarkerat.

* **[!UICONTROL Tillåt användare att ta bort kommentarer och ämnen]** Om det är markerat tillåter du medlemmarna att ta bort de kommentarer och frågor som de har skickat in. Standard är avmarkerat.

* **[!UICONTROL Tillåt röstning]** om det är markerat, inkludera röstfunktionen med en fråga. Standard är avmarkerat.

* **[!UICONTROL Flytta markerat svar till överst]** om markerat är det första svar som visas ett markerat svar. Standard är markerat.

* **[!UICONTROL Visa emblem]** Om det här alternativet är markerat visar du [märken](implementing-scoring.md) som tagits emot och tilldelats av en medlem i ett blogginlägg. Standard är avmarkerat.

* **[!UICONTROL Tillåt innehåll]** om det är markerat kan idén identifieras som [aktuellt innehåll](featured.md). Standard är avmarkerat.

#### Fliken Användarmoderering {#user-moderation-tab}

På fliken **[!UICONTROL Användarmoderering]** anger du hur bokförda ämnen (frågor) och svar (användargenererat innehåll) ska hanteras. Mer information finns i [Hantera användargenererat innehåll](moderate-ugc.md).

* **[!UICONTROL Neka svar]** Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka publicerade svar och förhindra att svaret visas på det offentliga forumet för frågor och svar. Standard är avmarkerat.

* **[!UICONTROL Stäng/öppna ämnen]** igen Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga en fråga (ämne) för ytterligare redigeringar och svar och kan även öppna en fråga igen. Standard är avmarkerat.

* **[!UICONTROL Flytta ämnen]** Om det här alternativet är markerat tillåter du moderatorer på publiceringssidan att flytta frågor. Standard är avmarkerat.

* **[!UICONTROL Flagga inlägg]** Om det är markerat kan medlemmar flagga andras frågor eller svar som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flaggorsakslista]** Om det här alternativet är markerat kan medlemmarna välja, från en nedrullningsbar lista, orsaken till att en fråga eller ett svar flaggas som olämpligt. Standard är avmarkerat.

* **[!UICONTROL Anledning till anpassad flagga]** Om den är markerad kan medlemmar ange en egen orsak för att flagga en fråga eller ett svar som olämpligt. Standard är avmarkerat.

* **[!UICONTROL Moderationströskel]** Ange hur många gånger en fråga eller ett svar måste flaggas av medlemmar innan moderatorerna meddelas. Standardvärdet är 1 (en gång).

* **[!UICONTROL Flaggningsgräns]** Ange hur många gånger en fråga eller ett svar måste flaggas innan det döljs för den offentliga vyn. Om värdet är -1 döljs aldrig den flaggade frågan eller svaret från den offentliga vyn. Annars måste talet vara större än eller lika med modereringströskeln. Standardvärdet är 5.

#### Fliken Taggfält {#tag-field-tab}

Under fliken **[!UICONTROL Tagg]** begränsas de taggar som kan användas, om de tillåts under fliken **[!UICONTROL Inställningar]** , enligt de namnutrymmen som valts.

* **[!UICONTROL Tillåtna]** relevanta namnutrymmen om `Allow Tagging` är markerat på fliken **Inställningar** . De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Förslagsgräns]** Ange antalet taggar som ska visas som ett förslag till medlemmen som publicerar i forumet. Värdet `-1` betyder inga gränser. Standardvärdet är 0.

#### Fliken Sorteringsinställningar {#sort-settings-tab}

På fliken **[!UICONTROL Sorteringsinställningar]** anger du hur de skickade kommentarerna ska sorteras när de visas.

* **[!UICONTROL Sortera efter]** Markera alla tillåtna sorteringsval: `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standardvärdet är `Newest, Oldest, Last Updated`.

* **[!UICONTROL Ange som standard]** Dra nedåt om du vill välja något av de markerade sorteringsalternativen som ska visas som standard. Standardvärdet är `Newest`.

* **[!UICONTROL Välj Tidsalternativ för sortering]** i listrutan Analytics (Analyssortering) för att välja ett av `All, Last 24 Hours, Last 7 Days, Last 30 Days`. Standardvärdet är `All`.

## Site Visitor Experience {#site-visitor-experience}

### Identifiera svar {#identifying-answers}

Ett svar kan markeras som ett korrekt eller användbart svar med `Select Answer` knappen. När en fråga har markerats som besvarad kan du inte välja ett annat svar förrän den första har avmarkerats med `Unmark Chosen Answer`knappen.

När du har valt det som ett användbart svar kan det avmarkeras med `Unmark Chosen Answer` knappen.

När ett svar har valts som ett möjligt svar `Answered`visas en indikation på att frågan har ställts bredvid frågeämnet på QnA-huvudsidan.

### Styrelsemedlemmar och administratörer {#moderators-and-administrators}

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

## Additional Information {#additional-information}

Mer information finns på sidan [QnA Essentials](qna-essentials.md) för utvecklare.

Mer information om moderering av publicerade ämnen och kommentarer finns i [Hantera användargenererat innehåll](moderate-ugc.md).

Information om hur du taggar publicerade ämnen och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).
