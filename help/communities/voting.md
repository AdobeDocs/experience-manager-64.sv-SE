---
title: Använda röstning
seo-title: Använda röstning
description: Lägga till komponenten Voting på en sida
seo-description: Lägga till komponenten Voting på en sida
uuid: 56e6cced-2f2d-434a-8fde-92a6c2478a04
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 071cac6d-05c5-47ab-85bc-ead6693ca1f4
translation-type: tm+mt
source-git-commit: 3d2b91565e14e85e9e701663c8d0ded03e5b430c
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 1%

---


# Använda röstning {#using-voting}

Komponenten `Voting` är ett användbart verktyg som gör att communitymedlemmar kan klassificera en viss del av innehållet, till exempel ett svar i en QnA-komponent. Med komponenten `Voting` markerar medlemmarna upp- eller nedpilar för att ange sin åsikt.

## Lägger till röstning på en sida {#adding-voting-to-a-page}

Om du vill lägga till en `Voting`-komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på `Communities / Voting` och dra den till rätt plats på en sida, t.ex. en relativ position till funktionen som användarna ska rösta på.

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](essentials-voting.md#essentials-for-client-side) inkluderas visas `Voting`-komponenten så här.

![chlimage_1-307](assets/chlimage_1-307.png)

## Konfigurerar röstning {#configuring-voting}

Markera den monterade `Voting`-komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-308](assets/chlimage_1-308.png)

Under fliken **[!UICONTROL Texts & Labels]** anger du de egenskaper som ska användas för att spela in röster.

![chlimage_1-309](assets/chlimage_1-309.png)

* **[!UICONTROL Positive Response Label]**
(
*Obligatoriskt*) Det interna egenskapsnamnet för ett positivt svar.

* **[!UICONTROL Negative Response Label]**
(
*Obligatoriskt*) Det interna egenskapsnamnet för ett negativt svar.

* **[!UICONTROL Tally Name]**
(
*Obligatoriskt*) Det interna, identifierbara egenskapsnamnet för den här instansen av en röstkomponent.

## Site Visitor Experience {#site-visitor-experience}

### Medlemmar {#members}

Ledamöter får endast rösta en gång, men de får när som helst ändra sin röst.

### Anonym {#anonymous}

Anonym röstning stöds inte. Besökare måste registrera sig (bli medlem) och logga in för att kunna delta i omröstningen en gång.

## Ytterligare information {#additional-information}

Mer information finns på [sidan Röstningsfunktioner](essentials-voting.md) för utvecklare.
