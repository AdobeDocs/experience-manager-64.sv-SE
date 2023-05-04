---
title: Använda kommentarer
seo-title: Using Comments
description: Med kommentarsfunktionen kan besökare på den inloggade webbplatsen dela med sig av sina åsikter och kunskaper
seo-description: Comments feature lets signed-in site visitors share their opinions and knowledge
uuid: 30fc48ac-134c-4acb-a65c-398855c93829
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: b074ebfa-2894-4a2d-aa8e-28168049971a
exl-id: 8ad5ce3e-c5dd-48d7-8812-43172eda36cc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '961'
ht-degree: 0%

---

# Använda kommentarer {#using-comments}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

Kommentarsfunktionen används för att låta besökare (medlemmar) på den inloggade webbplatsen dela med sig av sina åsikter och kunskaper om innehållet på webbplatsen. Den här funktionen finns ofta redan i andra funktioner, men kan läggas till på alla webbplatser.

Detta avsnitt i dokumentationen beskriver

* Lägger till `Comments`till en sida
* Konfigurationsinställningar för `Comments`komponent

>[!NOTE]
>
>Anonym publicering av en kommentar stöds inte. Besökarna måste registrera sig (bli medlem) och logga in för att kunna delta.

## Lägga till kommentarer på en sida {#adding-comments-to-a-page}

Lägga till en `Comments`-komponent till en sida i redigeringsläge använder du komponentwebbläsaren för att leta upp

* `Communities / Comments`

och dra den till rätt plats på en sida, t.ex. en position i förhållande till funktionen som användarna kan kommentera på, eller helt enkelt längst ned på sidan.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](essentials-comments.md#essentials-for-client-side) ingår så här `Comments`visas.

![chlimage_1-428](assets/chlimage_1-428.png)

>[!NOTE]
>
>Bara en `Comments`-komponenten kan finnas på en sida. Observera att flera communityfunktioner redan innehåller kommentarer, t.ex. en blogg, kalender, forum, QnA och recensioner.

## Konfigurera kommentarer {#configuring-comments}

Markera den monterade `Comments` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![konfigurera](assets/configure.png) ![kommentarinställningar](assets/commentssettings.png)

### Fliken Kommentarer {#comments-tab}

Under **[!UICONTROL Comments]** anger du hur besökarna ska skriva sina kommentarer.

* **[!UICONTROL Allow replies]**

   Om det här alternativet är markerat kan medlemmarna svara på befintliga kommentarer. Standard är avmarkerat.

* **[!UICONTROL Comments Per Page]**

   Begränsar antalet kommentarer som visas per sida samt antalet svar som visas. Standardvärdet är 10.

* **[!UICONTROL Allow File Uploads]**

   Om du markerar det här alternativet visas textrutan för alternativet att överföra en fil. Standard är avmarkerat.

* **[!UICONTROL Max File Size]**

   Endast relevant om Tillåt filöverföringar är markerat. Det här värdet begränsar storleken på den överförda filen. Standardgränsen är 10 MB.

* **[!UICONTROL Max Message Length]**

   Maximalt antal tecken som kan anges i textrutan. Standardvärdet är 4 096 tecken.

* **[!UICONTROL Allowed File Types]**

   Endast relevant om Tillåt filöverföringar är markerat. En kommaavgränsad lista med filtillägg med punktavgränsaren. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp anges tillåts inte den som inte anges. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Rich Text Editor]**

   Om det här alternativet är markerat kan kommentarer skrivas in med markeringar. Standard är avmarkerat.

* **[!UICONTROL Allow Voting]**

   Om det här alternativet är markerat visas textrutan med alternativet att rösta upp eller ned. Standard är avmarkerat.

* **[!UICONTROL Allow Following]**

   Om det här alternativet är markerat kan medlemmarna följa kommentarerna. Standard är avmarkerat.

* **[!UICONTROL Display Badges]**

   Om du markerar det här alternativet tillåts visning av färdiga och tilldelade märken. Standard är avmarkerat.

### Fliken Användarmoderering {#user-moderation-tab}

Under **[!UICONTROL User Moderation]** anger du hur de bokförda kommentarerna ska hanteras. Mer information finns i [Modererar användargenererat innehåll](moderate-ugc.md).

* **[!UICONTROL Pre-Moderation]**

   Om det här alternativet är markerat måste kommentarerna godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Delete Comments]**

   Om det här alternativet är markerat kan den medlem som publicerade kommentaren ta bort den. Standard är avmarkerat.

* **[!UICONTROL Deny Comments]**

   Om det här alternativet är markerat tillåter du moderatorerna att neka kommentarer. Standard är avmarkerat.

* **[!UICONTROL Close/Reopen Comments]**

   Om det här alternativet är markerat kan moderatorerna stänga och öppna kommentarerna igen. Standard är avmarkerat.

* **[!UICONTROL Flag Comments]**

   Om alternativet är markerat kan medlemmarna flagga kommentarer som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flag Reason List]**

   Om det här alternativet är markerat kan medlemmarna i en nedrullningsbar lista välja orsaken till att en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Custom Flag Reason]**

   Om det här alternativet är markerat kan medlemmarna ange en egen orsak till att en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Moderation Threshold]**

   Ange hur många gånger en kommentar måste flaggas av medlemmar innan moderatorerna meddelas. Standard är en gång (1).

* **[!UICONTROL Flagging Limit]**

   Ange hur många gånger en kommentar måste flaggas innan den döljs för den offentliga vyn. Talet måste vara större än eller lika med **[!UICONTROL Moderation Threshold]**. Standardvärdet är 5.

### Fliken Sorteringsinställningar {#sort-settings-tab}

Under **[!UICONTROL Sort Settings]** anger du hur de bokförda kommentarerna ska sorteras när de visas.

* **[!UICONTROL Sort Field]**

   Dra ned för att välja något av `Newest, Oldest, Last Updated, Most Viewed, Most Active, Most Followed`, eller `Most Liked`.

* **[!UICONTROL Sort Order]**

   Dra ned för att välja något av `Ascending` eller `Descending`.

### Ändra till en anpassad kommentarstyp {#changing-to-a-custom-comment-type}

Genom att ändra kommentarsresurstypen kommer kommentarsystemet inte längre att generera en instans av en kommentar med standardinställningen, utan en som har anpassats (utökats) av utvecklarna.

När de anpassade resurstyperna är kända anger du [Designläge](../../help/sites-authoring/default-components-designmode.md) och dubbelklicka på `Comments` om du vill öppna en dialogruta med en extra flik.

Under **[!UICONTROL Resource Types]** anger du anpassad resourceType för nya instanser av `Comments or Voting`komponenter:

![chlimage_1-429](assets/chlimage_1-429.png)

* **[!UICONTROL Comment Resource Type]**

   Navigera till resourceType för en utökad `comment`-komponent (en kommentar) i /apps. Till exempel, `/apps/social/commons/components/hbs/comments/comment`

   Den här resursen identifierar den resourceType för den UGC som skapas när en besökare publicerar en kommentar.

* **[!UICONTROL Voting Resource Type]**

   Navigera till resourceType för en utökad `voting`i /apps. Till exempel, `/apps/social/components/hbs/voting`

   Den här resursen identifierar resurstypen för användargenererat innehåll som skapas när en besökare publicerar en röst.

* **[!UICONTROL Comment System Resource Type]**

   Navigera till resourceType för en utökad `comments`-komponent (kommentarsystem) i /apps. Lämna tomt om inte sidmallen [innehåller](scf.md#add-or-include-a-communities-component) kommentarsystemet i det underliggande skriptet i stället för att läggas till på sidan som en resurs (kommentarsnod). Läs mer om [{{include}} hjälpare](handlebars-helpers.md#include).

## Site Visitor Experience {#site-visitor-experience}

### Styrelsemedlemmar och administratörer {#moderators-and-administrators}

När den inloggade användaren har moderator- eller administratörsbehörighet kan de utföra de modereringsåtgärder som tillåts av komponentens konfiguration, oavsett vem som skapade kommentaren.

### Medlemmar {#members}

När besökaren är inloggad, beroende på konfigurationen, kan de

* Publicera en ny kommentar
* Redigera en egen kommentar
* Ta bort en egen kommentar
* Flagga andras kommentarer

### Anonym {#anonymous}

Besökare som inte är inloggade kan endast läsa publicerade kommentarer, översätta dem om de stöds, men kan inte lägga till en kommentar eller flagga andras kommentarer.

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande kommentarer](essentials-comments.md) för utvecklare.

Mer information om moderering av kommentarer finns i [Modererar användargenererat innehåll](moderate-ugc.md).

För översättning av bokförda kommentarer, se [Översätter användargenererat innehåll](translate-ugc.md).
