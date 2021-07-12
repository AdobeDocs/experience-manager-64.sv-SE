---
title: Communities-meddelanden
seo-title: Communities-meddelanden
description: AEM Communities har meddelanden som visar händelser av intresse för den inloggade communitymedlemmen
seo-description: AEM Communities har meddelanden som visar händelser av intresse för den inloggade communitymedlemmen
uuid: d6ef12f1-7367-49a5-b891-56800a38b2ab
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 47201e2d-338d-40e0-af82-c681a552807b
role: Admin
exl-id: f6c6619e-b386-4d34-9d17-654d7c97aedd
source-git-commit: 3c050c33a384d586d74bd641f7622989dc1d6b22
workflow-type: tm+mt
source-wordcount: '537'
ht-degree: 1%

---

# Communities-meddelanden {#communities-notifications}

## Översikt {#overview}

AEM Communities tillhandahåller ett meddelandeavsnitt som visar händelser av intresse för den signerade communitymedlemmen.

Meddelanden liknar [aktiviteter](essentials-activities.md) och [prenumerationer](subscriptions.md) eftersom de kan vara ett resultat av

* Medlemmen publicerar innehåll
* Medlemmen väljer att följa en annan medlem
* Medlemmen väljer att följa specifika ämnen, artiklar och andra trådar med innehåll

Det som skiljer meddelanden från aktiviteter och prenumerationer är

* En länk till meddelandeavsnittet finns alltid i en communitysajts rubrik
   * Aktiviteter kräver att funktionen [aktivitetsström](functions.md#activity-stream-function) inkluderas i communityplatsens struktur
   * Prenumerationer kräver [konfigurering av e-post](email.md)
* Implementeringen av meddelanden sker via skalbara och anslutningsbara kanaler
   * Aktiviteter är bara tillgängliga på webben
   * Prenumerationer är bara tillgängliga via e-post

Från och med webbgrupper [FP1](deploy-communities.md#latestfeaturepack) är meddelandekanalerna tillgängliga

* Webbkanalen som du kommer åt via länken `Notifications`
* E-postkanalen, tillgänglig när e-postmeddelandet har konfigurerats korrekt

Framtida kanaler är mobila och stationära.

### Krav {#requirements}

**Konfigurera e-post**

E-post måste konfigureras för att e-postkanalen ska fungera.

Instruktioner om hur du konfigurerar e-post finns i [Konfigurera e-post](analytics.md).

**Aktivera Följ**

Komponenter måste konfigureras för att aktivera följande. Följande funktioner tillåter [blogg](blog-feature.md), [forum](forum.md), [QnA](working-with-qna.md), [kalender](calendar.md), [filelibrary](file-library.md) och [kommentarer](comments.md).

Observera att

* Komponenter som används i community [webbplatsmallar](sites.md) och [gruppmallar](tools-groups.md) kan redan vara konfigurerade att tillåta följande

* Medlemsprofiler har redan konfigurerats så att andra medlemmar kan följa

## Meddelanden från följande {#notifications-from-following}

![chlimage_1-254](assets/chlimage_1-254.png)

Med knappen **Följ** kan du följa upp aktiviteter, prenumerationer och/eller meddelanden. Varje gång knappen **Följ** är markerad går det att aktivera eller inaktivera en markering. Markeringen `Email Subscriptions` finns bara när den är konfigurerad.

Om någon av följande metoder är markerad ändras knappens text till **Följande**. Du kan av praktiska skäl välja `Unfollow All` för att inaktivera alla metoder.

Knappen **Följ** visas

* När en annan medlems profil visas
* På en huvudfunktionssida, till exempel forum, QnA och bloggar
   * Följer alla aktiviteter för den allmänna funktionen
* För ett visst inlägg, t.ex. ett forumämne, en QnA-fråga eller en bloggartikel
   * Följer all aktivitet för den specifika posten

## Hantera meddelandeinställningar {#managing-notification-settings}

Genom att välja länken Meddelandeinställningar på meddelandesidan kan varje medlem hantera hur meddelanden tas emot.

Webbkanalen är alltid aktiverad.

![chlimage_1-255](assets/chlimage_1-255.png)

E-postkanalen, som är beroende av rätt [konfiguration av e-post](email.md), innehåller samma inställningar som för webbkanalen.

E-postkanalen är inaktiverad som standard.

![chlimage_1-256](assets/chlimage_1-256.png)

Den kan vara aktiverad av en medlem, men är ändå beroende av att e-post konfigureras.

![chlimage_1-257](assets/chlimage_1-257.png)

## Visa meddelanden {#viewing-notifications}

### Webbmeddelanden {#web-notifications}

En [guide skapade en communityplats](sites-console.md) innehåller nu en länk till funktionen `Notifications` i webbplatsens rubrikfält ovanför banderollen. Till skillnad från meddelanden skapas meddelanden för alla communitysajter, medan meddelanden måste aktiveras när webbplatsen skapas.

När du går till den publicerade webbplatsen och väljer länken `Notifications` visas alla meddelanden för medlemmen.

![chlimage_1-258](assets/chlimage_1-258.png)

### E-postmeddelanden {#email-notifications}

När e-postkanalen är aktiverad får medlemmen ett e-postmeddelande som innehåller en länk till innehållet på webben.

![chlimage_1-259](assets/chlimage_1-259.png)
