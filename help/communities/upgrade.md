---
title: Uppgradera till AEM 6.4 Communities
seo-title: Upgrading to AEM 6.4 Communities
description: Hur man uppgraderar från en tidigare version till AEM 6.4 Communities
seo-description: How to upgrade from an earlier version to AEM 6.4 Communities
uuid: c6c2846e-38d4-4e99-9038-bfb486afd8b9
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: deploying
discoiquuid: 7aa28e36-6b31-4447-b800-cab2dc78c93c
exl-id: ef622ac3-d96d-48bf-bfb2-61516d9deb5c
source-git-commit: 0f82e82cf6e09a2734893a98d67ed1a84b1fec5e
workflow-type: tm+mt
source-wordcount: '658'
ht-degree: 0%

---

# Uppgradera till AEM 6.4 Communities {#upgrading-to-aem-communities}

Beroende på de olika platsernas topologi och funktioner kan följande åtgärder vara nödvändiga när du uppgraderar till AEM Communities 6.4 eller installerar det senaste funktionspaketet.

Detta avsnitt är specifikt för Communities och kompletterar informationen i [Uppgradera till AEM 6.4](../../help/sites-deploying/upgrade.md) (plattform).

## Uppgradera från AEM 6.1 eller senare {#upgrading-from-aem-or-later}

### Indexera om Solr {#reindex-solr}

När du installerar ett nytt funktionspaket för Communities på en distribution som konfigurerats med MSRP måste du:

1. Installera [det senaste funktionspaketet](deploy-communities.md#latestfeaturepack)
2. Installera [de senaste Solr-konfigurationsfilerna](msrp.md#upgrading)
3. Indexera om MSRP

   se avsnitt [MSRP Reindex Tool](msrp.md#msrp-reindex-tool)

### Aktivera 2.0 {#enablement}

Från och med AEM 6.3 lagras inte längre rapportinformation i MySQL i aktiveringsfunktionerna. MySQL-beroendet finns bara där för att spåra SCORM-innehåll.

Kontakta [kundtjänst](https://helpx.adobe.com/marketing-cloud/contact-support.html) om du behöver hjälp med att migrera innehåll från Enablement 1.0.

## Uppgradera från AEM 6.0 {#upgrading-from-aem}

Om befintlig UGC måste behållas beror det på om distributionen lagrades i UGC [lokalt](#on-premise-storage) eller i [Adobe-molnet](#adobe-cloud-storage).

### Adobe Cloud-lagring {#adobe-cloud-storage}

Om den uppgraderade webbplatsen har konfigurerats för att använda molnlagring i Adobe kan den visas (felaktigt) som om all UGC har förlorats eftersom SRP-metoderna inte kan hitta den befintliga UGC:n på den gamla platsen.

Det går alltså att instruera ASRP att använda `AEM 6.0 compatability-mode` för att få åtkomst till UGC.

För alla AEM 6.3-instanser:

1. Logga in med administratörsbehörighet och konfigurera [ASRP](asrp.md).
1. Följ de här stegen för att göra den befintliga UGC-filen synlig:

   i. Bläddra till webbkonsolen. Standardwebbadressen är
   `https://localhost:4502/system/console/configMgr`.

   ii. Leta reda på konfigurationen **[!UICONTROL AEM Communities Utilities]** och välj för att expandera konfigurationspanelen.

   iii. Avmarkera **[!UICONTROL Cloud Storage]** och klicka på **[!UICONTROL Save]**.

![chlimage_1-126](assets/chlimage_1-126.png)

### Lokal lagring {#on-premise-storage}

Om den uppgraderade webbplatsen inte använde molnlagring måste eventuell befintlig UGC konverteras så att den överensstämmer med den nya struktur som introducerades i AEM 6.1 Communities till stöd för den gemensamma butiken.

Ett migreringsverktyg med öppen källkod är tillgängligt på GitHub:\
[AEM Communities UGC-migreringsverktyg](https://github.com/Adobe-Marketing-Cloud/communities-ugc-migration)

### Java API:er {#java-apis}

När du uppgraderar från AEM 6.0 sociala communityn till AEM 6.3 Communities bör du vara medveten om att många API:er har omorganiserats till olika paket. De flesta bör vara lätta att lösa när man använder en integrerad utvecklingsmiljö för anpassning av communityfunktioner.

Mer information om det borttagna paketet SocialUtils finns på [SocialUtils Refactoring](socialutils.md).

Se även [Använda Maven för Communities](maven.md).

### Inga JSP-komponentmallar {#no-jsp-component-templates}

I [ramverket för sociala komponenter](scf.md) (SCF) används [HandlebarsJS](https://handlebarsjs.com/) (HBS) mallspråk i stället för Java Server Pages (JSP) som användes före AEM 6.0.

I AEM 6.0 låg JSP-komponenterna kvar tillsammans med de nya HBS-ramverkskomponenterna på samma plats, där HBS-komponenterna vanligtvis finns i undermappar med namnet&quot;hbs&quot;.

Från och med AEM 6.1 togs JSP-komponenterna bort helt. För Communities rekommenderas att all användning av JSP-komponenter ersätts med SCF-komponenter.

## AEM Communities UGC-migreringsverktyg {#aem-communities-ugc-migration-tool}

[AEM Communities UGC-migreringsverktyg](https://github.com/Adobe-Marketing-Cloud/communities-ugc-migration) är ett migreringsverktyg med öppen källkod, som finns på GitHub, som kan anpassas för att exportera UGC från tidigare versioner av AEM sociala communities och importera till AEM Communities 6.1 eller senare.

Förutom att flytta UGC från tidigare versioner går det också att använda verktyget för att flytta UGC från en [SRP](working-with-srp.md) till en annan, till exempel från MSRP till DSRP.

## Uppgradera från AEM 5.6.1 eller tidigare {#upgrading-from-aem-or-earlier}

Det finns tre generationer av communitykomponenter:

**Gen 1**: CQ 5.4 till AEM 5.6.0 - dessa är de  **** samverkande komponenter som lagrade UGC i den lokala databasen med replikering som ett sätt att synkronisera UGC mellan olika plattformar. Andra skillnader är implementeringen med Java Server Pages (JSP) och bloggfunktionen som bara består av redigering i författarmiljön.

**Gen 2**: från AEM 5.6.1 till och med AEM 6.1 - detta är en blandning av  **** kollaband  **** sociala komponenter. AEM 6.0 introducerade det nya [ramverket för sociala komponenter](scf.md) (SCF) och AEM 6.2 introducerade en [gemensam UGC-butik](working-with-srp.md) där UGC används med en [lagringsresursprovider](srp.md) (SRP).

**Gen 3**: Från AEM 6.2 och framåt finns det bara  **** sociala komponenter som implementeras i SCF som HBS-komponenter (Handlebars) som kräver val av SRP för UGC.
