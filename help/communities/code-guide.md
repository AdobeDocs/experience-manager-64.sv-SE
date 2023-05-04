---
title: Riktlinjer för kodning
seo-title: Coding Guidelines
description: Användarforum, tips och tricks
seo-description: Communities developer guidelines, tips, and tricks
uuid: 311ef4f7-7f2c-44c3-bcf2-f68713752623
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 244cd43c-a573-495d-b80c-b97ba9d19b75
exl-id: 022043cd-35ed-49b1-b5b4-5cc92d29cef4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 0%

---

# Riktlinjer för kodning {#coding-guidelines}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Riktlinjer, tips och tricks {#guidelines-tips-and-tricks}

Arbetet med AEM Communities har utvecklats från att vara starkt beroende av Java Server Pages till flexibilitet när det gäller valet av skriptspråk där affärslogik, format och sidinnehåll skiljer sig från varandra.

Ytterligare flexibilitet när det gäller att arbeta med användargenererat innehåll (UGC) är via API:t SocialResourceProvider, som eliminerar behovet av att vara medveten om vilka [SRP](srp.md) för distributionen.

Nedan följer olika riktlinjer för kodning och metodtips för AEM Communities-utvecklare:

### Code {#code}

* [Åtkomst till UGC med SRP](accessing-ugc-with-srp.md) - hur du undviker att skriva ett program som bara fungerar när UGC lagras i JCR (JSRP).
* [Omfaktorisering för SocialUtils](socialutils.md) - verktygsmetoder för SRP som ersätter SocialUtils.
* [Namnkonventioner](naming-conventions.md) - namnkonventioner för anpassade Java-klasser.

### Skript {#scripts}

* [Komponenter för sidoinläsning av communities](sideloading.md) - hur du lägger till en komponent dynamiskt när sidan har lästs in.
* [Grundläggande om Rich Text Editor](rte.md) - Anpassa det RTF-gränssnitt som medlemmarna får för att publicera innehåll.

### IDE {#ide}

* [Använda Maven for Communities](maven.md) - hur du tar med Communities API jar.
* [Omfaktorisering för SocialUtils](socialutils.md) - verktygsmetoder för SRP som ersätter SocialUtils.
