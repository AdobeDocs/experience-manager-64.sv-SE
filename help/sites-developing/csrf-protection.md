---
title: CSRF Protection Framework
seo-title: The CSRF Protection Framework
description: Ramverket använder variabler för att garantera att kundens begäran är berättigad
seo-description: The framework makes use of tokens to guarantee that the client request is legitimate
uuid: 7cb222ba-fc7a-46ee-8b49-a5f39a53580b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: f453427d-c813-48b7-b2f9-adadea39c67d
exl-id: 533c348e-517f-4d70-a89c-bfc87f71a633
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---

# CSRF Protection Framework{#the-csrf-protection-framework}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Förutom referensfiltret för Apache Sling tillhandahåller Adobe även ett nytt CSRF-skyddsramverk som skyddar mot den här typen av attacker.

Ramverket använder tokens för att garantera att kundens begäran är berättigad. Token genereras när formuläret skickas till klienten och valideras när formuläret skickas tillbaka till servern.

>[!NOTE]
>
>Det finns inga token för publiceringsinstanserna för anonyma användare.

## Krav {#requirements}

### Beroenden {#dependencies}

Alla komponenter som är beroende av `granite.jquery` CSRF Protection Framework kommer automatiskt att dra nytta av beroendet. Om detta inte är fallet för någon av dina komponenter måste du deklarera ett beroende för `granite.csrf.standalone` innan du kan använda ramverket.

### Replikerar krypteringsnyckeln {#replicating-crypto-keys}

Om du vill använda dessa variabler måste du replikera `/etc/keys/hmac` binär till alla instanser i distributionen. Ett praktiskt sätt att kopiera HMAC-nyckeln till alla instanser är att skapa ett paket som innehåller nyckeln och installera den via Package Manager på alla instanser.

>[!NOTE]
>
>Se också till att du gör nödvändiga [Konfigurationsändringar för Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/user-guide.html) för att kunna använda ramverket för skydd av CSRF.

>[!NOTE]
>
>Om du använder manifest-cachen tillsammans med webbprogrammet måste du lägga till &quot;**&amp;ast;**&quot; till manifestet för att säkerställa att token inte tar genereringsanropet för CSRF-token offline. Mer information finns i [link](https://www.w3.org/TR/offline-webapps/).
>
>Mer information om CSRF-attacker och sätt att mildra dem finns i [OWASP-sida för korsdomänbegäran](https://owasp.org/www-community/attacks/csrf).
