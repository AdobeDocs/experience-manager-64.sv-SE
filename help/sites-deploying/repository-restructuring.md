---
title: Omstrukturering av lager i AEM 6.4
seo-title: Omstrukturering av lager i AEM 6.4
description: Läs mer om grunderna och resonemanget bakom omstruktureringen av databasen i AEM 6.4
seo-description: Läs mer om grunderna och resonemanget bakom omstruktureringen av databasen i AEM 6.4
uuid: e9cd3e88-e352-44a8-9b97-69488d3267cb
contentOwner: chaikels
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: repo_restructuring
discoiquuid: fc879b0b-823b-4bdc-aaa6-36f53a33fb22
feature: Uppgraderar
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 0%

---


# Omstrukturering av lager i AEM 6.4{#repository-restructuring-in-aem}

## Introduktion {#introduction}

Före AEM 6.4 driftsattes kundkoden i oförutsägbara områden av JCR som kunde komma att ändras vid uppgraderingar. På grund av detta var det vanligt att formella AEM skulle skriva över anpassad kod, konfiguration eller innehåll. Dessutom skriver kundens ändringar ibland över AEM produktkod eller innehåll, vilket bryter mot produktfunktionaliteten.

Genom att tydligt definiera hierarkier för AEM produktkod och kundkod kan dessa konflikter undvikas.

Med början i AEM 6.4 och som kommer att fortsätta i framtida versioner struktureras innehållet därför om från /etc till andra mappar i databasen, tillsammans med riktlinjer om vilket innehåll som ska placeras, enligt följande högnivåregler:

* AEM produktkod placeras alltid i /libs, som inte får skrivas över av anpassad kod
* Anpassad kod ska placeras i /apps, /content och /conf

## Påverkan på 6.4 uppgraderingar {#impact-on-upgrades}

När du uppgraderar till AEM 6.4 dupliceras en stor delmängd av innehållet under /etc i andra mappar i databasen. Dessa nya platser är de populäraste platser där innehållet refereras. Alla försök har dock gjorts att AEM 6.4-uppgraderingen ska vara bakåtkompatibel med de tidigare platserna i mappen /etc, och i de flesta fall kommer den gamla platsen att refereras av AEM tills ändringar görs aktivt - och i många fall manuellt - i kundens applikation. Från tidslinjeperspektiv finns det två typer av ändringar:

* Med uppgradering av version 6.4 är en handfull av de/etc-förändringar som gjorts inte bakåtkompatibla och därför bör ändringar planeras och genomföras som en del av uppgraderingen av AEM 6.4.
* Före uppgradering till version 6.5 - de flesta av omstruktureringsförändringarna kan skjutas upp till en viss tid i framtiden. Som tidigare nämnts kommer AEM 6.4-kod att fortsätta referera till de gamla platserna tills ändringarna implementeras som en del av en kundrelease. Även om det inte finns någon tvingad tidslinje som ändringarna ska göras för rekommenderar vi att de görs före uppgraderingen till version 6.5 eftersom framtida funktioner kan vara beroende av att nya platser refereras. Dokumentationen för en viss funktion refererar till de nya platserna enligt vedertaget bruk och det kan därför vara förvirrande om de gamla platserna fortfarande används.

### Omstruktureringsvägledning {#restructuring-guidance}

Vid planering av en uppgradering till AEM 6.4 ska följande sidor per lösning refereras för att bedöma arbetsinsatsen:

* [Omstrukturering av lager som är gemensamma för alla AEM](/help/sites-deploying/all-repository-restructuring-in-aem-6-4.md)
* [Omstrukturering av AEM Sites-arkiv](/help/sites-deploying/sites-repository-restructuring-in-aem-6-4.md)
* [Omstrukturering av AEM Assets-arkiv](/help/sites-deploying/assets-repository-restructuring-in-aem-6-4.md)
* [Omstrukturering av AEM Assets Dynamic Media-arkiv](/help/sites-deploying/dynamicmedia-repository-restructuring-in-aem-6-4.md)
* [Omstrukturering av AEM Forms-arkiv](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md)
* [Omstrukturering av AEM Communities-arkiv](/help/sites-deploying/communities-repository-restructuring-in-aem-6-4.md)
* [Omstrukturering av AEM handelslager](/help/sites-deploying/ecommerce-repository-restructuring-in-aem-6-4.md)

Varje sida innehåller två avsnitt som motsvarar hur angelägna ändringarna är. Allt under&quot;Med 6.4-uppgradering&quot; ska hanteras som en del av uppgraderingsprojektet för AEM 6.4. Allt under&quot;Före 6.5-uppgraderingen&quot; kan eventuellt skjutas upp till efter uppgraderingen.

Varje post på sidan innehåller ett fält för&quot;vägledning om omstrukturering&quot;, som beskriver den rekommenderade tekniska strategin för anpassning till den nya 6.4-databasmodellen så att det refereras till de nya platserna för innehåll som tidigare fanns under mappen /etc. Ett extra&quot;Anteckningsfält&quot; ger ytterligare användbar kontext.
