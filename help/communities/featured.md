---
title: Innehållsfunktion
seo-title: Featured Content Feature
description: Funktionen Aktuellt innehåll gör att besökare på den inloggade webbplatsen kan markera innehåll
seo-description: The Featured Content feature lets signed-in site visitors highlight content
uuid: 7a2ff570-01bb-46fb-8d66-3b47e2efa72e
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: ee39435d-80f5-4758-ae01-1ea0d221b00b
exl-id: a0dcffed-1040-4d6d-b8e9-3bbe5f30deb4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 2%

---

# Innehållsfunktion {#featured-content-feature}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

Funktionen för innehåll är ett område där besökare på den inloggade webbplatsen (community-medlemmar) i publiceringsmiljön kan markera innehåll för

* [Bloggar](blog-feature.md)
* [Kalendrar](calendar.md)
* [Forum](forum.md)
* [Ideas](ideation-feature.md)
* [QnA](working-with-qna.md)

När innehållet har markerats som aktuellt kommer det att anges i den här komponenten, som kan placeras på specifika landningssidor eller områden som lätt fångar upp communitymedlemmens uppmärksamhet.

Möjligheten att använda innehåll kan vara tillåten eller otillåten per komponent.

Detta avsnitt i dokumentationen beskriver

* Lägga till aktuellt innehåll på en communitywebbplats
* Konfigurationsinställningar för `Featured Content`komponent

## Lägga till innehåll på en sida {#adding-featured-content-to-a-page}

Lägga till en `Featured Content` -komponent till en sida i redigeringsläge använder du komponentwebbläsaren för att leta upp

* `Communities / Featured Content`

och dra den till rätt plats på en sida där det aktuella innehållet ska visas.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](essentials-featured.md#essentials-for-client-side) ingår så här `Featured Content`visas:

![chlimage_1-13](assets/chlimage_1-13.png)

## Konfigurera aktuellt innehåll {#configuring-featured-content}

Markera den monterade `Featured Content` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-14](assets/chlimage_1-14.png) ![chlimage_1-15](assets/chlimage_1-15.png)

### Fliken Inställningar {#settings-tab}

Under **[!UICONTROL Settings]** identifierar du innehållet som ska visas:

* **[!UICONTROL Display Name]**
Namnet på listan med aktuellt innehåll. Till exempel 
`Featured Questions` eller `Featured Ideas`. Standard är `Featured Content` om det lämnas tomt.

* **[!UICONTROL Location of the Featured Content]**

   *(Obligatoriskt)* Bläddra till sidan med innehållet som kan vara en funktion (komponenterna på sidan måste vara konfigurerade för att tillåta aktuellt innehåll). Till exempel, `/content/sites/engage/en/forum`

* **[!UICONTROL Display Limit]**
Det maximala antalet innehåll som kan visas. Standardvärdet är 5.

## Site Visitor Experience {#site-visitor-experience}

Möjligheten att flagga innehåll som aktuellt innehåll kräver moderatorbehörighet.

När en moderator visar publicerat innehåll har de tillgång till modereringsflaggorna som innehåller det nya `Feature` flagga.

![chlimage_1-16](assets/chlimage_1-16.png)

När modellflaggan har flaggats som en funktion blir den `Unfeature`.

Sidan som innehåller `Featured Content` kommer nu att inkludera det här inlägget.

![chlimage_1-17](assets/chlimage_1-17.png)

`Read More` är en länk till själva inlägget.

## Ytterligare information {#additional-information}

Mer information finns på [Innehåll](essentials-featured.md) för utvecklare.

Information om hur du flaggar innehåll finns i [Modererar användargenererat innehåll](moderate-ugc.md).
