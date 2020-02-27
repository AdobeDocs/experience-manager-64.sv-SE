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

---


# Idéfunktion {#ideation-feature}

## Introduktion {#introduction}

Idéfunktionen är ett område där besökare (community-medlemmar) som är inloggade kan publicera i publiceringsmiljön:

* Skapa idéer som du kan dela med dig av till communityn
* Visa och kommentera idéer
* Följ en idé
* Rösta på en idé

Detta avsnitt i dokumentationen beskriver

* Lägga till designfunktionen på en AEM-webbplats
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

Ange inställningar för idéer och kommentarer på fliken **[!UICONTROL Inställningar]** :

* **[!UICONTROL Ideation Title]** The display title for the ideas. Standardvärdet är `Ideation`.

* **[!UICONTROL Ideation Description]** A description to display as a sub title for the ideas. Standardvärdet är ingen beskrivning.

* **[!UICONTROL Ämnen per sida]** Definierar antalet idéer/inlägg som visas per sida. Standardvärdet är 10.

* **[!UICONTROL Moderated]** Om det här alternativet är markerat måste publicering av idéer och kommentarer godkännas innan de visas på en publiceringswebbplats. Standard är avmarkerat.

* **[!UICONTROL Stängt]** Om det här alternativet är markerat stängs idéforumet för nya idéer och kommentarer. Standard är avmarkerat.

* **[!UICONTROL RTF-redigerare]** Om den är markerad kan du skriva in idéer och kommentarer med markeringar. Standard är avmarkerat.

* **[!UICONTROL Tillåt taggning]** Om det här alternativet är markerat tillåter du medlemmar att lägga till taggetiketter i sitt inlägg (se fliken **[!UICONTROL Taggfält]** ). Standard är avmarkerat.

* **[!UICONTROL Tillåt filöverföringar]** Om det här alternativet är markerat tillåter du att bifogade filer läggs till i idén eller kommentaren. Standard är avmarkerat.

* **[!UICONTROL Maximal filstorlek]** relevant endast om `Allow File Uploads` markeras. Det här fältet begränsar storleken (i byte) på en överförd fil. Standardvärdet är 104857600 (10 MB).

* **[!UICONTROL Tillåtna filtyper]**&#x200B;är bara relevanta om `Allow File Uploads` markeras. En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp har angetts kan de som inte har angetts inte överföras. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Max Attach Image File Size]** Relevant only if Allow File Uploads is checked. Maximalt antal byte som en överförd bildfil kan ha. Standardvärdet är 2097152 (2 MB).

* **[!UICONTROL Tillåt svar]** Om det här alternativet är markerat tillåter du svar på kommentarer som har lagts till i idén. Standard är avmarkerat.

* **[!UICONTROL Tillåt användare att ta bort kommentarer och ämnen]** Tillåt medlemmar att ta bort kommentarer och idéer som de publicerat om de är markerade. Standard är avmarkerat.

* **[!UICONTROL Tillåt följande]** om det är markerat, inkludera följande funktion för idéinlägg, som gör att medlemmar kan [meddelas](notifications.md) om nya inlägg. Standard är avmarkerat.

* **[!UICONTROL Tillåt e-postprenumerationer]** Om det här alternativet är markerat tillåter du medlemmar att meddelas om nya inlägg via e-post ([prenumeration](subscriptions.md)). Kräver `Allow Following` att kontrolleras och att [e-post konfigureras](email.md). Standard är avmarkerat.

* **[!UICONTROL Tillåt röstning]** om det här alternativet är markerat, tillåt röstning om en idés kommentarer. Standard är avmarkerat.

* **[!UICONTROL Visa emblem]** Om det är markerat visas [emblem](implementing-scoring.md) som har skapats och tilldelats av en medlem. Standard är avmarkerat.

* **[!UICONTROL Tillåt innehåll]** om det är markerat kan idén identifieras som [aktuellt innehåll](featured.md). Standard är avmarkerat.

### Fliken Användarmoderering {#user-moderation-tab}

På fliken **[!UICONTROL Användarmoderering]** anger du hur publicerade idéer och kommentarer (användargenererat innehåll) ska hanteras. Mer information finns i [Hantera användargenererat innehåll](moderate-ugc.md).

* **[!UICONTROL Neka inlägg]** Om det här alternativet är markerat kan pålitliga medlemsmoderatorer neka inlägg och förhindra att posten visas på det offentliga forumet. Standard är avmarkerat.

* **[!UICONTROL Stäng/öppna ämnen]** igen Om det här alternativet är markerat kan pålitliga medlemsmoderatorer stänga ett avsnitt för ytterligare redigeringar och kommentarer och även öppna ett avsnitt på nytt. Standard är avmarkerat.

* **[!UICONTROL Flagga inlägg]** Om det är markerat kan medlemmar flagga andras ämnen eller kommentarer som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flagga orsakslista]** Om det här alternativet är markerat kan medlemmarna välja, från en nedrullningsbar lista, orsaken till att ett ämne eller en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Anledning till anpassad flagga]** Om den är markerad kan medlemmar ange en egen orsak till att ett ämne eller en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Moderationströskel]** Ange hur många gånger ett ämne eller en kommentar måste flaggas av medlemmar innan moderatorerna meddelas. Standardvärdet är 1 (en gång).

* **[!UICONTROL Flaggningsgräns]** Ange hur många gånger ett ämne eller en kommentar måste flaggas innan det döljs för den offentliga vyn. Om värdet är -1 döljs aldrig det flaggade ämnet eller kommentaren från den offentliga vyn. Annars måste talet vara större än eller lika med modereringströskeln. Standardvärdet är 5.

### Fliken Taggfält {#tag-field-tab}

Under fliken **[!UICONTROL Tagg]** begränsas de taggar som kan användas, om de tillåts under fliken **[!UICONTROL Inställningar]** , enligt de namnutrymmen som valts.

* **[!UICONTROL Tillåtna]** relevanta namnutrymmen om `Allow Tagging` är markerat på fliken **Inställningar** . De taggar som kan användas är begränsade till de inom de namnutrymmeskategorier som kontrolleras. Listan med namnutrymmen innehåller &quot;Standardtaggar&quot; (standardnamnutrymmet) och &quot;Inkludera alla taggar&quot;. Standardvärdet är inget markerat, vilket betyder att alla namnutrymmen är tillåtna.

* **[!UICONTROL Förslagsgräns]** Ange antalet taggar som ska visas som ett förslag till medlemmen som publicerar i forumet. Värdet **-** 1 betyder ingen gräns. Standardvärdet är 0.

### Fliken Sorteringsinställningar {#sort-settings-tab}

På fliken **[!UICONTROL Sorteringsinställningar]** anger du hur de skickade kommentarerna ska sorteras när de visas.

* **[!UICONTROL Sortera efter]** Markera alla tillåtna sorteringsval: `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed and Most Liked`. Standardvärdet är `Newest, Oldest, Last Updated`.

* **[!UICONTROL Ange som standard]** Dra nedåt om du vill välja något av de markerade sorteringsalternativen som ska visas som standard. Standardvärdet är `Newest`.

* **[!UICONTROL Välj Tidsalternativ för sortering]** i listrutan Analytics (Analyssortering) för att välja ett av `All, Last 24 Hours, Last 7 Days, Last 30 Days`. Standardvärdet är `All`.

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
