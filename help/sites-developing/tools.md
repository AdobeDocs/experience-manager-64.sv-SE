---
title: Testnings- och spårningsverktyg
seo-title: Testnings- och spårningsverktyg
description: AEM tillhandahåller ett ramverk för testning av komponentens användargränssnitt och en mekanism för testning och felsökning av komponenter
seo-description: AEM tillhandahåller ett ramverk för testning av komponentens användargränssnitt och en mekanism för testning och felsökning av komponenter
uuid: 29c43202-0a4e-41ba-9176-92fa77c627d5
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 0f977264-fe58-4478-bd38-aca5c75f36aa
translation-type: tm+mt
source-git-commit: 60f36a33471dbbd9ca877dbbedc82ade606a125c

---


# Testnings- och spårningsverktyg{#testing-and-tracking-tools}

## Testning {#testing}

AEM ger:

* [ett ramverk för testning av komponentens användargränssnitt](/help/sites-developing/hobbes.md).
* [en mekanism för att testa och felsöka komponenter](/help/sites-developing/developer-mode.md).

Här följer två testverktyg för öppen källkod:

**Selen**

Selenium används för funktionstestning i en webbläsare med en användare per aktivitet. Den registrerar teststeg (klickningar) som antingen HTML-tabeller eller Java-klasser.

Mer information finns på [https://www.seleniumhq.org/](https://www.seleniumhq.org/).

**JMeter**

JMeter används för att spåra förfrågningar och kan användas för funktions-, prestanda- och stresstester.

Mer information finns på [http://jakarta.apache.org/jmeter/](http://jakarta.apache.org/jmeter/).

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
* endast en originalkopia ska bevaras och alla ska veta var originalkopian finns.
* De ska vara tillgängliga för alla projektmedlemmar.
* Om säkerhet är ett problem (ofta i stora företag) och gemensam åtkomst inte är möjlig, kan kopior distribueras så länge alla förstår att det är kopior som inte kan uppdateras.

Det finns också många egna verktyg för att spåra buggar och funktionsbehov.
