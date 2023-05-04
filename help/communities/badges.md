---
title: Badges Console
seo-title: Badges Console
description: Med konsolen Communities Badges kan du lägga till egna emblem som kan visas för medlemmar när de har en viss roll i communityn (tilldelade) eller när de har en viss roll i communityn
seo-description: The Communities Badges console lets you add custom badges that can be displayed for members when earned (awarded) or when they take on a specific role in the community (assigned)
uuid: 9eeba240-f0d4-4937-baba-8bac0e0b2a36
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 4194278f-5127-4105-b181-60961c7a1def
role: Admin
exl-id: b6aa9d73-4e20-446a-a1fc-78f8968d6844
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# Badges Console {#badges-console}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Om Badges {#about-badges}

Konsolen Communities Badges innehåller funktioner för att lägga till egna emblem som kan visas för en medlem när den har tjänats in (tilldelats) eller när de har en specifik roll i communityn (tilldelats).

### Synlighet för emblem {#badge-visibility}

För närvarande visas emblem som en medlem i communityn får eller tilldelas tillsammans med sitt namn och avatar på följande platser:

* Profiler
* [Forum](forum.md)
* [QnA](working-with-qna.md)
* [Ledartavlor](enabling-leaderboard.md)
* [Ideation](ideation-feature.md)

För att nå Badges-konsolen i redigeringsmiljön

* Från global navigering: **[!UICONTROL Tools > Communities > Badges]**

Den här konsolen visar de emblem som är tillgängliga för tillfället och från vilka nya emblem kan läggas till.

![chlimage_1-242](assets/chlimage_1-242.png)

## Skapa märke {#create-badge}

Ett märke skapas genom att en lämplig liten bild (72 dpi med en höjd på mellan 26 och 32 pixlar) överförs och ett namn anges. Badge-bilden sparas i databasen på `/etc/community/badging/images` och replikeras automatiskt till publiceringsmiljön.

Om publiceringsmiljön är en grupp utgivare måste du konfigurera [användarsynkronisering](sync.md).

![chlimage_1-243](assets/chlimage_1-243.png)

* **[!UICONTROL Upload Image]**

   (*Obligatoriskt*) En badge-bild med en rekommenderad storlek på 32 x 32 pixlar vid 72 dpi i JPEG- eller PNG-format.

* **[!UICONTROL Name]**

   (*Obligatoriskt*) Namnet på märket. Det är standardinställningen `Display Name` samt databasens nodnamn. Om `Name` är inte ett giltigt databasnodnamn. Det kommer att ändras.

* **[!UICONTROL Display Name]**

   (*Valfritt*) Namnet som ska visas för märket i gränssnittet. Standard är den oförändrade text som anges för `Name`.

* **[!UICONTROL Description]**

   (*Valfritt*) En beskrivning av märket.

## Ytterligare information {#additional-information}

Mer information om hur du ställer in regler för poäng och badging finns i [Betygsättning och emblem](implementing-scoring.md).

Information om hur du hanterar emblem för medlemmar finns i [Medlemskonsolen](members.md).
