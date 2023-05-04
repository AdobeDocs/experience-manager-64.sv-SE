---
title: Testnings- och spårningsverktyg
seo-title: Testing and Tracking Tools
description: AEM tillhandahåller ett ramverk för testning av komponentens användargränssnitt och en mekanism för testning och felsökning av komponenter
seo-description: AEM provides a framework for testing component UI and a mechanism for testing and debugging components
uuid: 29c43202-0a4e-41ba-9176-92fa77c627d5
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 0f977264-fe58-4478-bd38-aca5c75f36aa
exl-id: 9387cdb4-f8de-4229-90d1-59218ac17561
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 0%

---

# Testnings- och spårningsverktyg{#testing-and-tracking-tools}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Testning {#testing}

AEM tillhandahåller:

* [ett ramverk för testning av komponentens användargränssnitt](/help/sites-developing/hobbes.md).
* [en mekanism för testning och felsökning av komponenter](/help/sites-developing/developer-mode.md).

Här följer två testverktyg för öppen källkod:

**Selen**

Selenium används för funktionstestning i en webbläsare med en användare per aktivitet. Det registrerar teststeg (klickningar) som HTML-tabeller eller Java-klasser.

Mer information finns i [https://www.seleniumhq.org/](https://www.seleniumhq.org/).

**JMeter**

JMeter används för att spåra förfrågningar och kan användas för funktions-, prestanda- och stresstester.

Mer information finns i [http://jakarta.apache.org/jmeter/](http://jakarta.apache.org/jmeter/).

Det finns också många egna verktyg för att automatisera tester och hantera testplaner.

## Spårning {#tracking}

Följande verktyg är enkelt tillgängliga. Men ett nyckelproblem i alla fall är att alla medlemmar i projektteamet - partner och kund - har tillgång till data.

**Bugzilla**

Ett felsökningssystem som kan konfigureras efter dina egna behov.

**Kalkylblad**

Även om kalkylblad inte är specifikt ett felsökningsverktyg, används de ofta felaktigt i detta syfte eftersom de är lätta att förstå och de flesta användare har erfarenhet av sin funktionalitet.

Om dessa används för spårning:

* de ska vara enkla.
* Antalet enskilda kalkylblad bör begränsas till ett minimum.
* måste uppdateras regelbundet.
* endast en överordnad kopia ska bevaras och alla ska veta var den överordnad kopian finns.
* De ska vara tillgängliga för alla projektmedlemmar.
* Om säkerhet är ett problem (ofta i stora företag) och gemensam åtkomst inte är möjlig, kan kopior distribueras så länge alla förstår att det är kopior som inte kan uppdateras.

Det finns också många egna verktyg för att spåra buggar och funktionsbehov.
