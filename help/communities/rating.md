---
title: Använda klassificeringar
seo-title: Using Ratings
description: Lägga till en klassificeringskomponent på en sida
seo-description: Adding a Rating component to a page
uuid: a986970b-1221-4648-9a69-410f4480e0ae
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: a0e5491e-66bc-47b0-94a5-45a02bc558da
exl-id: 1de28140-5334-4ca2-a476-5ad253809808
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '238'
ht-degree: 1%

---

# Använda klassificeringar {#using-ratings}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

The `Rating`-komponenten används fristående eller tillsammans med andra webbgruppsfunktioner. Med den här komponenten kan inloggade communitymedlemmar uttrycka sina åsikter genom att gradera innehåll.

## Lägga till en klassificering på en sida {#adding-a-rating-to-a-page}

Lägga till en `Rating`till en sida i redigeringsläge, leta reda på komponenten `Communities / Rating` och dra den till plats på en sida, till exempel en position i förhållande till funktionen som medlemmarna kan betygsätta.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](rating-basics.md#essentials-for-client-side) ingår så här `Rating` visas.

![chlimage_1-493](assets/chlimage_1-493.png)

## Konfigurerar klassificering {#configuring-rating}

Markera den monterade `Rating` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-494](assets/chlimage_1-494.png)

Under **[!UICONTROL Texts & Labels]** kan du ange den interna identifieraren för klassificeringen.

![chlimage_1-495](assets/chlimage_1-495.png)

**[!UICONTROL Tally Name]**
(*Obligatoriskt*) Ett enkelt namn för `Rating`som unikt identifierar den här instansen. Måste vara ett giltigt nodnamn för databasen.

## Site Visitor Experience {#site-visitor-experience}

### Medlemmar {#members}

Endast en klassificering per medlem tillåts. Medlemmen kan när som helst ändra sin klassificering.

### Anonym {#anonymous}

Anonym publicering av en klassificering stöds inte. Besökarna måste registrera sig (bli medlem) och logga in för att kunna delta.

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande omdömen](rating-basics.md) för utvecklare.
