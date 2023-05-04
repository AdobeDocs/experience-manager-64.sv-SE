---
title: Använda röstning
seo-title: Using Voting
description: Lägga till komponenten Voting på en sida
seo-description: Adding the Voting component to a page
uuid: 56e6cced-2f2d-434a-8fde-92a6c2478a04
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 071cac6d-05c5-47ab-85bc-ead6693ca1f4
exl-id: 660a7106-0c21-4073-8319-4d6d20b9bc49
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 1%

---

# Använda röstning {#using-voting}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

The `Voting` är ett användbart verktyg som gör att communitymedlemmar kan betygsätta en viss del av innehållet, till exempel ett svar i en QnA-komponent. Med `Voting` -komponent väljer medlemmarna upp- eller nedpilar för att ange sin åsikt.

## Lägga till omröstning på en sida {#adding-voting-to-a-page}

Lägga till en `Voting` -komponent till en sida i redigeringsläge använder du komponentwebbläsaren för att leta upp `Communities / Voting` och dra den till rätt plats på en sida, t.ex. en position som är relativ till funktionen som användarna kan rösta på.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](essentials-voting.md#essentials-for-client-side) ingår så här `Voting` visas.

![chlimage_1-307](assets/chlimage_1-307.png)

## Konfigurerar röstning {#configuring-voting}

Markera den monterade `Voting` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-308](assets/chlimage_1-308.png)

Under **[!UICONTROL Texts & Labels]** anger du de egenskaper som används för att spela in röster.

![chlimage_1-309](assets/chlimage_1-309.png)

* **[!UICONTROL Positive Response Label]**
(
*Obligatoriskt*) Det interna egenskapsnamnet för ett positivt svar.

* **[!UICONTROL Negative Response Label]**
(
*Obligatoriskt*) Det interna egenskapsnamnet för ett negativt svar.

* **[!UICONTROL Tally Name]**
(
*Obligatoriskt*) Det interna, identifierbara egenskapsnamnet för den här instansen av en röstningskomponent.

## Site Visitor Experience {#site-visitor-experience}

### Medlemmar {#members}

Ledamöter får endast rösta en gång, men de får när som helst ändra sin röst.

### Anonym {#anonymous}

Anonym röstning stöds inte. Besökare måste registrera sig (bli medlem) och logga in för att kunna delta i omröstningen en gång.

## Ytterligare information {#additional-information}

Mer information finns på [Grundläggande röstning](essentials-voting.md) för utvecklare.
