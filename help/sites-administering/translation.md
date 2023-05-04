---
title: Översätta innehåll för flerspråkiga webbplatser
seo-title: Translating Content for Multilingual Sites
description: Lär dig hur du översätter innehåll för flerspråkiga webbplatser.
seo-description: Learn how to translate content for multilingual sites.
uuid: b8047f6f-e86a-495d-9b80-731ac7d83c66
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 67faa2ee-cb12-44b0-8bfb-534d1d6c360a
legacypath: /content/docs/en/aem/6-0/administer/integration/third-party-services/machine-translation
feature: Language Copy
exl-id: 3a3f5c4d-6c3f-4201-acc8-dbd138bb59ba
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '290'
ht-degree: 0%

---

# Översätta innehåll för flerspråkiga webbplatser{#translating-content-for-multilingual-sites}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Automatisera översättning av sidinnehåll, resurser och användargenererat innehåll för att skapa och underhålla flerspråkiga webbplatser. Om du vill automatisera arbetsflöden för översättning integrerar du översättare med AEM och skapar projekt för översättning av innehåll till flera språk. AEM har stöd för arbetsflöden för översättning mellan människor och datorer.

* Översättning: Innehållet skickas till översättningsleverantören och översätts av professionella översättare. När det är klart returneras det översatta innehållet och importeras till AEM. När översättningsleverantören är integrerad med AEM skickas innehåll automatiskt mellan AEM och översättningsleverantören.
* Maskinöversättning: Maskinöversättningstjänsten översätter ditt innehåll omedelbart.

Översättning av innehåll omfattar följande steg:

1. [Anslut AEM till översättningstjänstleverantören](/help/sites-administering/tc-tic.md#connecting-to-a-translation-service-provider) och [skapa konfigurationer för översättningsintegreringsramverk](/help/sites-administering/tc-tic.md).

1. [Koppla samman sidorna på din språkinställning](/help/sites-administering/tc-tic.md#configuring-pages-for-translation) med översättningstjänsten och ramverkskonfigurationerna.
1. [Identifiera innehållstypen](/help/sites-administering/tc-rules.md) att översätta.
1. [Förbered innehållet för översättning](/help/sites-administering/tc-prep.md) genom att skapa det överordnad språket och skapa rotsidorna för språkkopior.
1. [Skapa översättningsprojekt](/help/sites-administering/tc-manage.md) för att samla det innehåll som ska översättas och förbereda översättningsprocessen.
1. Använd översättningsprojekt för att [hantera innehållsöversättningsprocessen](/help/sites-administering/tc-manage.md).

Om översättningstjänsten inte har någon koppling till AEM stöder AEM manuell extrahering och återinfogning av översättningsinnehåll i XML-format.

>[!NOTE]
>
>Användaren måste vara medlem i projektadministratörsgruppen för att kunna använda funktionerna för språkkopiering.

## Bästa praxis {#best-practices}

The [Bästa praxis för översättning](/help/sites-administering/tc-bp.md) sidan innehåller viktig information om implementeringen.
