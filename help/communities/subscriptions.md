---
title: Communities-prenumerationer
seo-title: Communities Subscriptions
description: Medlemmar i communityn interagerar med andra medlemmar via e-post
seo-description: Community members interact with other members through email
uuid: a4b98769-c219-4e18-8e80-9a806ab979ff
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 33c85af4-4c56-487a-ba60-55211cb9f72c
role: Admin
exl-id: 8a756328-0405-49b7-b94d-3dd5a87c782a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 1%

---

# Communities-prenumerationer {#communities-subscriptions}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Från och med Communities [FP1](deploy-communities.md#latestfeaturepack)kan communitymedlemmar interagera med communityn via e-post med en funktion som kallas prenumerationer.

Prenumerationer liknar [meddelanden](notifications.md) som medlemmar kan prenumerera när de följer bloggartiklar, forumämnen eller QnA-frågor.

Det som skiljer prenumerationer från meddelanden är:

* Medlemmar får inte prenumerera efter andra medlemmar
* Den enda åtgärd som medlemmar kan utföra är att välja `Email Subscriptions` när du följer
* När e-postsvar har konfigurerats kan medlemmar effektivt publicera innehållet genom att helt enkelt svara på det mottagna e-postmeddelandet

### Krav {#requirements}

**Konfigurera e-post**

E-post måste konfigureras för att prenumerationerna ska fungera och för att medlemmarna ska kunna svara via e-post.

Instruktioner om hur du konfigurerar e-post finns i [Konfigurerar e-post](email.md).

**Aktivera prenumerationer och följ**

Komponenter måste konfigureras för att aktivera prenumerationer *och* följer. Funktioner som tillåter prenumerationer är [blogg](blog-feature.md), [forum](forum.md) och [QnA](working-with-qna.md).

## Prenumerationer från följande {#subscriptions-from-following}

![chlimage_1-5](assets/chlimage_1-5.png)

The **Följ** Med knappen kan du följa upp tävlingsbidrag som aktiviteter, prenumerationer och/eller meddelanden. Varje gång **Följ** är markerad går det att aktivera eller inaktivera en markering.

Om någon av följande metoder är markerad ändras texten för knappen till **Följande**. Det går att välja `Unfollow All` för att växla mellan olika metoder.

The **Följ** knappen innehåller `Email Subscriptions` bara när ett forum, QnA eller blogg har konfigurerats för att aktivera e-postprenumerationer. Den här knappen visas

* På huvudfunktionssidan för det aktiverade forumet, QnA eller bloggen

   * Skickar ett e-postmeddelande för all aktivitet under den funktionen

* För ett visst inlägg, t.ex. ett forumämne, en QnA-fråga eller en bloggartikel

   * Skickar ett e-postmeddelande när det finns aktivitet för det specifika inlägget

## Svara via e-post {#reply-by-email}

När e-post [konfigurerad för att svara via e-post](email.md#configure-polling-importer), får den prenumererande medlemmen ett e-postmeddelande med det publicerade innehållet och en länk till onlineinnehållet.

Om de svarar på e-postmeddelandet visas det innehåll de anger i svaret som innehåll online.

![chlimage_1-6](assets/chlimage_1-6.png)

Hur lång tid det tar för ett svar att bokföras styrs av [avsökningimporterarens uppdateringsintervall](email.md#configure-polling-importer).

![chlimage_1-7](assets/chlimage_1-7.png)
