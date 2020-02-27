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
translation-type: tm+mt
source-git-commit: 7b39a715166eeefdf20eb22a4449068ff1ed0e42

---


# Översätta innehåll för flerspråkiga webbplatser{#translating-content-for-multilingual-sites}

Automatisera översättning av sidinnehåll, resurser och användargenererat innehåll för att skapa och underhålla flerspråkiga webbplatser. Om du vill automatisera översättningsarbetsflöden integrerar du översättningstjänster med AEM och skapar projekt för översättning av innehåll till flera språk. AEM har stöd för arbetsflöden för översättning mellan människor och datorer.

* Översättning: Innehållet skickas till översättningsleverantören och översätts av professionella översättare. När det är klart returneras det översatta innehållet och importeras till AEM. När din översättningsleverantör är integrerad med AEM skickas innehåll automatiskt mellan AEM och översättningsleverantören.
* Maskinöversättning: Maskinöversättningstjänsten översätter ditt innehåll omedelbart.

Översättning av innehåll omfattar följande steg:

1. [Anslut AEM till din översättningstjänst](/help/sites-administering/tc-tic.md#connecting-to-a-translation-service-provider) och [skapa konfigurationer](/help/sites-administering/tc-tic.md)för översättningsintegrering.

1. [Associera sidorna på din språkinställning](/help/sites-administering/tc-tic.md#configuring-pages-for-translation) med översättningstjänsten och ramverkskonfigurationerna.
1. [Identifiera vilken typ av innehåll](/help/sites-administering/tc-rules.md) som ska översättas.
1. [Förbered innehållet för översättning](/help/sites-administering/tc-prep.md) genom att skapa språkinställningen och skapa rotsidorna för språkkopior.
1. [Skapa översättningsprojekt](/help/sites-administering/tc-manage.md) för att samla in innehållet som ska översättas och förbereda översättningsprocessen.
1. Använd översättningsprojekten för att [hantera innehållsöversättningsprocessen](/help/sites-administering/tc-manage.md).

Om din översättningstjänst inte har någon koppling till integrationen med AEM, kan AEM extrahera och återinfoga översättningsinnehåll manuellt i XML-format.

>[!NOTE]
>
>Användaren måste vara medlem i projektadministratörsgruppen för att kunna använda funktionerna för språkkopiering.

## Bästa praxis {#best-practices}

Sidan [Översättningsmetodtips](/help/sites-administering/tc-bp.md) innehåller viktig information om implementeringen.
