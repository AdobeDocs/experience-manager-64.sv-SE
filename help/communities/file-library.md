---
title: Filbiblioteksfunktion
seo-title: File Library Feature
description: Med funktionen Filbibliotek kan besökare på den inloggade webbplatsen överföra, hantera och hämta filer
seo-description: The File Library feature lets signed-in site visitors upload, manage, and download files
uuid: 7da94703-8334-4c02-ba2a-55b5cde22e6c
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: cdcae09f-c3cb-471e-863f-b33130e9df0f
exl-id: c72b246d-442e-4841-810d-1045e83f60f9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '639'
ht-degree: 0%

---

# Filbiblioteksfunktion {#file-library-feature}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

Funktionen för filbibliotek är en plats där besökare på den inloggade webbplatsen (community-medlemmar) kan överföra, hantera och hämta filer inom communitywebbplatsen.

Detta avsnitt i dokumentationen beskriver

* Lägga till filbiblioteksfunktionen på en AEM
* Konfigurationsinställningar för `File Library` komponent

## Lägga till ett filbibliotek på en sida {#adding-a-file-library-to-a-page}

Lägga till en `File Library` till en sida i redigeringsläge, leta reda på komponenten

* `Communities / File Library`

och dra den till rätt plats på en sida.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](essentials-file-library.md#essentials-for-client-side) ingår så här `File Library` visas:

![chlimage_1-430](assets/chlimage_1-430.png)

## Konfigurerar filbibliotek {#configuring-file-library}

Markera den monterade `File Library` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-431](assets/chlimage_1-431.png) ![chlimage_1-432](assets/chlimage_1-432.png)

### Fliken Kommentarer {#comments-tab}

Under **[!UICONTROL Comments]** anger du om och hur kommentarer för överförda filer ska visas:

* **[!UICONTROL Allow Comments on Files]**
Om det här alternativet är markerat tillåts kommentarer för överförda filer. Standard är avmarkerat.

* **[!UICONTROL Comments Per Page]**
Begränsar antalet kommentarer som visas per sida samt antalet svar som visas. Standard är 
**10**.

* **[!UICONTROL Max File Size]**
Det här värdet begränsar storleken på den överförda filen. Standardgränsen är 104857600 (10 MB).

* **[!UICONTROL Max Message Length]**
Maximalt antal tecken som kan anges i textrutan. Standardvärdet är 4 096 tecken.

* **[!UICONTROL Allowed File Types]**
En kommaavgränsad lista med filtillägg med&quot;punktavgränsaren&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp anges tillåts inte den som inte anges. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL Rich Text Editor]**
Om det här alternativet är markerat kan kommentarer skrivas in med markeringar. Standard är avmarkerat.

* **[!UICONTROL Delete Comments]**
Om det här alternativet är markerat kan användarna ta bort sina egna kommentarer. Standard är markerat.

* **[!UICONTROL Allow Tagging]**
Om du markerar det här alternativet aktiveras möjligheten att lägga till en tagg i filen. Standard är avmarkerat.

* **[!UICONTROL Allowed Namespaces]**
Om Tillåt taggning är markerat begränsas de tillgängliga taggarna till de namnutrymmen som är markerade. Om inga är markerade tillåts alla. Standard är alla namnutrymmen.

* **[!UICONTROL Suggestion Limit]**
Om Tillåt taggning är markerat begränsas det antal föreslagna taggar som ska visas med den här inställningen. Om värdet är -1 finns det ingen gräns. Standardvärdet är -1.

* **[!UICONTROL Allow Voting]**
Om det här alternativet är markerat aktiveras möjligheten att rösta efter en fil. Standard är avmarkerat.

* **[!UICONTROL Allow Following]**
Om du markerar det här alternativet inkluderar du följande funktion för bloggartiklar, som gör att medlemmar kan [meddelad](notifications.md) av nya tjänster. Standard är avmarkerat.

* **[!UICONTROL Allow Threaded Replies]**
Om det här alternativet är markerat tillåts svar på publicerade kommentarer. Standard är avmarkerat.

### Fliken Användarmoderering {#user-moderation-tab}

Under **[!UICONTROL User Moderation]** -fliken, konfigurera moderering av kommentarer, om kommentarer tillåts:

* **[!UICONTROL Pre-Moderation]**
Om det här alternativet är markerat måste kommentarerna godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Delete Comments]**
Om det här alternativet är markerat kan den besökare som publicerade kommentaren ta bort den. Standard är markerat.

* **[!UICONTROL Deny Comments]**
Om det här alternativet är markerat tillåter du att pålitliga medlemsmoderatorer nekar kommentarer. Standard är avmarkerat.

* **[!UICONTROL Close / Reopen Comments]**
Om det här alternativet är markerat kan du tillåta att pålitliga medlemsmoderatorer stänger och öppnar kommentarer igen. Standard är avmarkerat.

* **[!UICONTROL Flag Comments]**
Om det här alternativet är markerat kan besökarna flagga kommentarer som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flag Reason List]**
Om det här alternativet är markerat kan besökare välja, från en nedrullningsbar lista, orsaken till att en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Custom Flag Reason]**
Om det här alternativet är markerat kan besökarna ange en egen orsak till att en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Moderation Threshold]**
Ange hur många gånger en kommentar måste flaggas av besökare innan moderatorerna meddelas. Standard är en gång (
**1**).

* **[!UICONTROL Flagging Limit]**
Ange hur många gånger en kommentar måste flaggas innan den döljs för den offentliga vyn. Talet måste vara större än eller lika med 
**Modereringströskel**. Standardvärdet är 5.

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande om filbibliotek](essentials-file-library.md) för utvecklare.

moderering av inlägg och kommentarer finns i [Modererar användargenererat innehåll](moderate-ugc.md).

Information om hur du taggar publicerade ämnen och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).
