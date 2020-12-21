---
title: Använda Länk
seo-title: Använda Länk
description: Lägga till och konfigurera komponenten Länka
seo-description: Lägga till och konfigurera komponenten Länka
uuid: 12103ab7-1a1c-49cd-8dad-6c7508b4550e
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: dcde4e03-78ab-4779-96a1-05ac41f14701
translation-type: tm+mt
source-git-commit: f78f83ef3b9373bcbee3e5179a9bbec4d9462255
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---


# Använda länken {#using-liking}

Komponenten `Liking`är ett användbart verktyg som gör att användare kan uttrycka sin åsikt om en viss del av innehållet, till exempel en kommentar i ett forum. Med komponenten `Liking`väljer medlemmarna hjärtikonen för att ange en positiv åsikt.

## Lägger till länk på en sida {#adding-liking-to-a-page}

Om du vill lägga till en `Liking`-komponent på en sida i redigeringsläge använder du komponentwebbläsaren för att leta reda på

* `Communities / Liking`

och dra den till rätt plats på en sida, t.ex. i förhållande till funktionen som användarna kan gilla.

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När de [nödvändiga klientbiblioteken](essentials-liking.md#essentials-for-client-side) inkluderas visas `Liking`-komponenten så här.

![chlimage_1-93](assets/chlimage_1-93.png)

## Konfigurerar länken {#configuring-liking}

Markera den monterade `Liking`-komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-94](assets/chlimage_1-94.png)

Under fliken **[!UICONTROL Texts & Labels]** anger du de egenskaper som ska användas för att spela in gilla-markeringar.

![chlimage_1-95](assets/chlimage_1-95.png)

* **[!UICONTROL Positive Response Label]**
(
*Obligatoriskt*) Egenskapsnamnet för ett positivt svar.

* **[!UICONTROL Negative Response Label]**
(
*Obligatoriskt*) Egenskapsnamnet för ett negativt svar.

* **[!UICONTROL Tally Name]**
(
*Obligatoriskt*) Det interna, identifierbara egenskapsnamnet för den här instansen av en röstkomponent.

## Site Visitor Experience {#site-visitor-experience}

### Medlemmar {#members}

Medlemmarna kan när som helst ändra sig.

### Anonym {#anonymous}

Anonym länkning stöds inte. Besökare på webbplatsen måste registrera sig (bli medlem) och logga in för att kunna vara med.

## Ytterligare information {#additional-information}

Mer information finns på sidan [Liking Essentials](essentials-liking.md) för utvecklare.
