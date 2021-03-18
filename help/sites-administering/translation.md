---
title: Översätta innehåll för flerspråkiga webbplatser
seo-title: Översätta innehåll för flerspråkiga webbplatser
description: Lär dig hur du översätter innehåll för flerspråkiga webbplatser.
seo-description: Lär dig hur du översätter innehåll för flerspråkiga webbplatser.
uuid: b8047f6f-e86a-495d-9b80-731ac7d83c66
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 67faa2ee-cb12-44b0-8bfb-534d1d6c360a
legacypath: /content/docs/en/aem/6-0/administer/integration/third-party-services/machine-translation
feature: Språkkopia
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 0%

---


# Översätta innehåll för flerspråkiga webbplatser{#translating-content-for-multilingual-sites}

Automatisera översättning av sidinnehåll, resurser och användargenererat innehåll för att skapa och underhålla flerspråkiga webbplatser. Om du vill automatisera arbetsflöden för översättning integrerar du översättare med AEM och skapar projekt för översättning av innehåll till flera språk. AEM har stöd för arbetsflöden för översättning mellan människor och datorer.

* Översättning: Innehållet skickas till översättningsleverantören och översätts av professionella översättare. När det är klart returneras det översatta innehållet och importeras till AEM. När översättningsleverantören är integrerad med AEM skickas innehåll automatiskt mellan AEM och översättningsleverantören.
* Maskinöversättning: Maskinöversättningstjänsten översätter ditt innehåll omedelbart.

Översättning av innehåll omfattar följande steg:

1. [Koppla AEM med översättningstjänsten ](/help/sites-administering/tc-tic.md#connecting-to-a-translation-service-provider) och  [skapa konfigurationer](/help/sites-administering/tc-tic.md) för översättningsintegrering.

1. [Koppla sidorna i ditt språk till ](/help/sites-administering/tc-tic.md#configuring-pages-for-translation) översättningstjänsten och ramverkskonfigurationerna.
1. [Identifiera vilken typ av ](/help/sites-administering/tc-rules.md) innehåll som ska översättas.
1. [Förbered innehållet för ](/help/sites-administering/tc-prep.md) översättning genom att skapa språket överordnad och skapa rotsidorna för språkkopior.
1. [Skapa översättningsprojekt ](/help/sites-administering/tc-manage.md) för att samla in det innehåll som ska översättas och förbereda översättningsprocessen.
1. Använd översättningsprojekten för att [hantera innehållsöversättningsprocessen](/help/sites-administering/tc-manage.md).

Om översättningstjänsten inte har någon koppling till AEM stöder AEM manuell extrahering och återinfogning av översättningsinnehåll i XML-format.

>[!NOTE]
>
>Användaren måste vara medlem i projektadministratörsgruppen för att kunna använda funktionerna för språkkopiering.

## Bästa praxis {#best-practices}

Sidan [Bästa praxis för översättning](/help/sites-administering/tc-bp.md) innehåller viktig information om implementeringen.
