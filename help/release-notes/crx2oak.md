---
title: CRX2OAK-migreringsverktyg
seo-title: CRX2OAK Migration Tool
description: Versionsinformation om Adobe Experience Manager 6.4 CRX2OAK-migreringsverktyget.
seo-description: Release notes specific to the Adobe Experience Manager 6.4 CRX2OAK Migration tool.
uuid: 1b582faf-2dc6-41a2-9419-7e82347f9d6c
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: cfdaceac-a5b3-4070-ad4c-f1457b1e2e4b
exl-id: 441c8ba0-f8b2-4c2c-b7be-cfdad9e1e498
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 0%

---

# CRX2OAK-migreringsverktyg {#crx-oak-migration-tool}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Lista över ändringar och korrigeringar {#list-of-changes-and-fixes}

### 1.8.6 (juni 2018) {#june}

* OAK-7339 Åtgärda alla sidbrytningar med UnsupportedOperationException i MissingBlobStore genom att införa LoopbackBlobStore
* Använd ak 1.8.4

### 1.8.4 (april 2018) {#april}

* Använd Oak version 1.8.2
* GRANITE-18104 Repo Migration error from 6.3 to 6.4 should be more purpose
* GRANITE-16571 Ersätt användningen av SHA-1

   * Verktygets kontrollsumma är nu SHA-512 när du använder alternativet —version

* GRANITE-17601 Bädda in ekuppgradering i CRX2Oak med ekblob-cloud
* GRANITE-18553 crx2oak lämnar versionsegenskaper på noden även när versionerna inte migreras

### Version 1.6.8 (mars 2017) {#version-march}

* Uppdaterad Oak-version till 1.6.1
* CQ-61847 Merge crx2oak-quickstart-extension with crx2oak (added migration profiles)
* CQ-97488 Körningslägen för AEM och släpp (genom att skriva om sling.options.file)
* GRANITE-12798/OAK-4260 Möjlighet att använda sidoklasser från eksegment till eksegment

### Version 1.4.2 (mars 2016) {#version-march-1}

* Uppgradera Oak-version till 1.4.1
* OAK-3846 / GRANITE-10748 Byt namn på SNS-noder om de bryter mot nodtypsbegränsningar
* OAK-3910 / GRANITE-10730 Migrera nod från `mix:versionable` utan versionshistorik
* OAK-4128 / GRANITE-11757 `RepositorySidegrade` kopierar inte rotnodegenskaper

### Version 1.3.4 (januari 2016) {#version-january}

* Uppgradera Oak-version till 1.3.16
* OAK-3844 / GRANITE-10730 Bättre stöd för versionshanteringsnoder utan versionshistorik
* OAK-3846 Byt namn på SNS-noder om de bryter mot nodtypsbegränsningar

### Version 1.3.2 (december 2015) {#version-december}

* Uppgraderar Oak-version till 1.3.12
* Datastorkatalogen bör inte flyttas efter migreringen (GRANITE-10447)
* Merge crx2oak-quickstart-extension with crx2oak (CQ-61847)
* crx2oak fungerar inte på dubblettvärden i databasen (CQ-61906)
* Lång AEM efter migrering från CQ 5.x (GRANITE-10309)
* Stöd för flera LDAP-servrar i crx2oak (GRANITE-9917)
* Tvinga kontroll efter maximal nodnamnslängd (OAK-3111)
* Stöd för S3DataSource som migreringskälla (OAK-3685)
