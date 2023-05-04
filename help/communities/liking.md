---
title: Använda Länk
seo-title: Using Liking
description: Lägga till och konfigurera komponenten Länka
seo-description: Adding and configuring the Liking component
uuid: 12103ab7-1a1c-49cd-8dad-6c7508b4550e
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: dcde4e03-78ab-4779-96a1-05ac41f14701
exl-id: b5918a54-ef7b-4b3f-bca7-ed0344bab4aa
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 1%

---

# Använda Länk {#using-liking}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

The `Liking`-komponenten är ett användbart verktyg som gör att användare kan uttrycka sin åsikt om en viss del av innehållet, till exempel en kommentar i ett forum. Med `Liking`-komponenten väljer medlemmarna hjärtikonen för att ange en positiv åsikt.

## Lägga till länkning på en sida {#adding-liking-to-a-page}

Lägga till en `Liking` -komponent till en sida i redigeringsläge använder du komponentwebbläsaren för att leta upp

* `Communities / Liking`

och dra den till rätt plats på en sida, t.ex. i förhållande till funktionen som användarna kan gilla.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När [nödvändiga bibliotek på klientsidan](essentials-liking.md#essentials-for-client-side) ingår så här `Liking` visas.

![chlimage_1-93](assets/chlimage_1-93.png)

## Konfigurerar länk {#configuring-liking}

Markera den monterade `Liking` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-94](assets/chlimage_1-94.png)

Under **[!UICONTROL Texts & Labels]** anger du de egenskaper som används för att spela in gilla-markeringar.

![chlimage_1-95](assets/chlimage_1-95.png)

* **[!UICONTROL Positive Response Label]**
(
*Obligatoriskt*) Egenskapsnamnet för ett positivt svar.

* **[!UICONTROL Negative Response Label]**
(
*Obligatoriskt*) Egenskapsnamnet för ett negativt svar.

* **[!UICONTROL Tally Name]**
(
*Obligatoriskt*) Det interna, identifierbara egenskapsnamnet för den här instansen av en röstningskomponent.

## Site Visitor Experience {#site-visitor-experience}

### Medlemmar {#members}

Medlemmarna kan när som helst ändra sig.

### Anonym {#anonymous}

Anonym länkning stöds inte. Besökare på webbplatsen måste registrera sig (bli medlem) och logga in för att kunna vara med.

## Ytterligare information {#additional-information}

Mer information finns på [Länka viktiga](essentials-liking.md) för utvecklare.
