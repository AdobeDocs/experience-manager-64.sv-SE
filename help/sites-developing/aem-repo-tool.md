---
title: AEM
seo-title: AEM
description: AEM är en enkel lösning för att överföra JCR-innehåll mellan det lokala filsystemet och den AEM servern via kommandoraden som kan jämföras med FTP. AEM liknar Jacka-kanins FileVault-verktyg, men är snabbare, har minimalt med beroenden och är ett enkelt basskript.
seo-description: AEM är en enkel lösning för att överföra JCR-innehåll mellan det lokala filsystemet och den AEM servern via kommandoraden som kan jämföras med FTP. AEM liknar Jacka-kanins FileVault-verktyg, men är snabbare, har minimalt med beroenden och är ett enkelt basskript.
uuid: 6c4a3504-e8e8-46c0-83cb-c18d9791f93e
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: development-tools
content-type: reference
discoiquuid: 7de7b2f9-770e-4af3-8a31-c7b4de64fd43
translation-type: tm+mt
source-git-commit: 7b39a715166eeefdf20eb22a4449068ff1ed0e42
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 0%

---


# AEM{#aem-repo-tool}

AEM är en enkel lösning för att överföra JCR-innehåll mellan det lokala filsystemet och den AEM servern via kommandoraden som kan jämföras med FTP. AEM liknar [Jackrabbit FileVault-verktyget](/help/sites-developing/ht-vlttool.md), men är snabbare, har minimalt med beroenden och är ett enkelt basskript.

Det här verktyget förenklar filöverföringen för utvecklaren och kan även integreras i IntelliJ och Eclipse för ännu effektivare utveckling.

## Översikt {#overview}

För en given sökväg i en `jcr_root` filstruktur i filsystemet skapar AEM ett paket med ett enda filter för hela underträdet och skickar det till servern (liknande FTP `put`), hämtar det från servern ( `get`) eller jämför skillnaderna ( `status` och `diff`).

Verktyget stöder inte flera filtersökvägar eller FileVault-sökvägar `filter.xml`.

>[!CAUTION]
>
>Observera att AEM alltid skriver över hela filen eller katalogen som anges.

## Ladda ned och dokumentation {#download-and-documentation}

Verktyget [AEM finns på GitHub via den här länken](https://github.com/Adobe-Marketing-Cloud/tools/tree/master/repo) tillsammans med detaljerade installations- och användningsanvisningar.

Om du vill hämta källan till AEM kan du läsa GitHub-projektet som är länkat nedan.

KOD PÅ GITHUB

Koden för den här sidan finns på GitHub

* [Öppna verktygsprojekt på GitHub](https://github.com/Adobe-Marketing-Cloud/tools)
* Hämta projektet som [en ZIP-fil](https://github.com/Adobe-Marketing-Cloud/tools/archive/master.zip)

