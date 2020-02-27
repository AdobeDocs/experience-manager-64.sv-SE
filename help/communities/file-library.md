---
title: Filbiblioteksfunktion
seo-title: Filbiblioteksfunktion
description: Med funktionen Filbibliotek kan besökare på den inloggade webbplatsen överföra, hantera och hämta filer
seo-description: Med funktionen Filbibliotek kan besökare på den inloggade webbplatsen överföra, hantera och hämta filer
uuid: 7da94703-8334-4c02-ba2a-55b5cde22e6c
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: cdcae09f-c3cb-471e-863f-b33130e9df0f
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c

---


# Filbiblioteksfunktion {#file-library-feature}

## Introduktion {#introduction}

Funktionen för filbibliotek är en plats där besökare på den inloggade webbplatsen (community-medlemmar) kan överföra, hantera och hämta filer inom communitywebbplatsen.

Detta avsnitt i dokumentationen beskriver

* Lägga till filbiblioteksfunktionen på en AEM-webbplats
* Konfigurationsinställningar för `File Library` komponenten

## Lägga till ett filbibliotek på en sida {#adding-a-file-library-to-a-page}

Om du vill lägga till en `File Library` komponent på en sida i redigeringsläge letar du reda på komponenten

* `Communities / File Library`

och dra den till rätt plats på en sida.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](essentials-file-library.md#essentials-for-client-side) inkluderas visas `File Library` komponenten så här:

![chlimage_1-430](assets/chlimage_1-430.png)

## Konfigurerar filbibliotek {#configuring-file-library}

Markera den monterade `File Library` komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![chlimage_1-431](assets/chlimage_1-431.png) ![chlimage_1-432](assets/chlimage_1-432.png)

### Fliken Kommentarer {#comments-tab}

Under fliken **[!UICONTROL Kommentarer]** anger du om och hur kommentarer för överförda filer ska visas:

* **[!UICONTROL Tillåt kommentarer om filer]** Om det här alternativet är markerat tillåts kommentarer om överförda filer. Standard är avmarkerat.

* **[!UICONTROL Kommentarer per sida]** Begränsar antalet kommentarer som visas per sida samt antalet svar som visas. Standardvärdet är **10**.

* **[!UICONTROL Maximal filstorlek]** Det här värdet begränsar storleken på den överförda filen. Standardgränsen är 104857600 (10 MB).

* **[!UICONTROL Maximal meddelandelängd]** Maximalt antal tecken som kan anges i textrutan. Standardvärdet är 4 096 tecken.

* **[!UICONTROL Tillåtna filtyper]** En kommaavgränsad lista över filtillägg med avgränsaren &quot;punkt&quot;. Till exempel: .jpg, .jpeg, .png, .doc, .docx, .pdf. Om någon filtyp anges tillåts inte den som inte anges. Ingen standard har angetts så att alla filtyper tillåts.

* **[!UICONTROL RTF-redigerare]** Om det här alternativet är markerat kan kommentarerna infogas med kod. Standard är avmarkerat.

* **[!UICONTROL Ta bort kommentarer]** Om det här alternativet är markerat kan användarna ta bort sina egna kommentarer. Standard är markerat.

* **[!UICONTROL Tillåt taggning]** Om det här alternativet är markerat aktiveras möjligheten att lägga till en tagg i filen. Standard är avmarkerat.

* **[!UICONTROL Tillåtna namnutrymmen]** Om Tillåt taggning är markerat begränsas de tillgängliga taggarna till de namnutrymmen som är markerade. Om inga är markerade tillåts alla. Standard är alla namnutrymmen.

* **[!UICONTROL Förslagsgräns]** Om Tillåt taggning är markerat begränsas det antal föreslagna taggar som visas med den här inställningen. Om värdet är -1 finns det ingen gräns. Standardvärdet är -1.

* **[!UICONTROL Tillåt röstning]** Om det här alternativet är markerat aktiveras möjligheten att rösta för en fil. Standard är avmarkerat.

* **[!UICONTROL Tillåt följande]** om det är markerat inkluderar du följande funktion för bloggartiklar, som gör att medlemmar kan [meddelas](notifications.md) om nya inlägg. Standard är avmarkerat.

* **[!UICONTROL Tillåt kopplade svar]** Om det här alternativet är markerat tillåter du svar på bokförda kommentarer. Standard är avmarkerat.

### Fliken Användarmoderering {#user-moderation-tab}

Konfigurera moderering av kommentarer under fliken **[!UICONTROL Användarmoderering]** , om kommentarer tillåts:

* **[!UICONTROL Förhandsmoderering]** Om det här alternativet är markerat måste kommentarerna godkännas innan de visas på en publiceringsplats. Standard är avmarkerat.

* **[!UICONTROL Ta bort kommentarer]** Om det här alternativet är markerat kan den besökare som publicerade kommentaren ta bort den. Standard är markerat.

* **[!UICONTROL Neka kommentarer]** Om det här alternativet är markerat tillåter du pålitliga medlemsmoderatorer att neka kommentarer. Standard är avmarkerat.

* **[!UICONTROL Stäng/öppna kommentarer]** igen Om det här alternativet är markerat tillåter du pålitliga medlemsmoderatorer att stänga och öppna kommentarer igen. Standard är avmarkerat.

* **[!UICONTROL Flagga kommentarer]** Om det är markerat kan besökarna flagga kommentarer som olämpliga. Standard är avmarkerat.

* **[!UICONTROL Flaggorsakslista]** Om det här alternativet är markerat kan besökare välja, från en nedrullningsbar lista, orsaken till att en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Anledning]** till anpassad flagga Om den är markerad kan besökarna ange en egen orsak till att en kommentar flaggas som olämplig. Standard är avmarkerat.

* **[!UICONTROL Moderationströskel]** Ange hur många gånger en kommentar måste flaggas av besökare innan moderatorerna meddelas. Standard är en gång (**1**).

* **[!UICONTROL Flaggningsgräns]** Ange hur många gånger en kommentar måste flaggas innan den döljs i den offentliga vyn. Talet måste vara större än eller lika med **modereringströskeln**. Standardvärdet är 5.

## Additional Information {#additional-information}

Mer information finns på sidan [File Library Essentials](essentials-file-library.md) för utvecklare.

Mer information om moderering av publicerade ämnen och kommentarer finns i [Hantera användargenererat innehåll](moderate-ugc.md).

Information om hur du taggar publicerade ämnen och kommentarer finns i [Tagga användargenererat innehåll](tag-ugc.md).
