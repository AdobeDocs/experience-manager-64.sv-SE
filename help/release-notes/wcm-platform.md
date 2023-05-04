---
title: AEM Foundation & Repository
seo-title: AEM Foundation & Repository
description: Versionsinformation om Adobe Experience Manager 6.3 AEM Platform och Repository.
seo-description: Release notes specific to Adobe Experience Manager 6.3 AEM Platform and Repository.
uuid: 147b38d0-cf87-467c-a52d-3399d4af7e6e
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: e5dd9d0d-6d67-4430-aeb3-2be91356f624
exl-id: 6f131247-d35e-4298-958f-35b94ff08c58
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---

# AEM Foundation &amp; Repository {#aem-foundation-repository}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Ändringslista {#list-of-changes}

### Databas {#repository}

* Oak Segment tar MicroKernel

   * Snabb komprimering (slutkompakering) för rensning av onlinerevision
   * Förbättrade skrivfrekvenser
   * Segmentoperationsstatistik exponerad via JMXBean
   * Uppskattad varaktighet för rensning av offlinerevision

* Oak Mongo Microkernel

   * Continuous Revision Cleanup for MongoMK ersätter planerat rensningsunderhåll

* Förbättrad effektivitet vid rensning av revisioner i dokumentnoder
* Se [Apache Jackrabbit Oak Jira v. 1.8.0](https://archive.apache.org/dist/jackrabbit/oak/1.8.0/RELEASE-NOTES.txt), [Apache Jackrabbit Oak Jira v. 1.8.1](https://archive.apache.org/dist/jackrabbit/oak/1.8.1/RELEASE-NOTES.txt) och [Apache Jackrabbit Oak Jira v. 1.8.2](https://archive.apache.org/dist/jackrabbit/oak/1.8.2/RELEASE-NOTES.txt) för en fullständig översikt över åtgärdade problem.

>[!CAUTION]
>
>* Den nya versionen av Oak Segment-taggen som finns sedan AEM 6.3 kräver en databasmigrering. Det här steget är obligatoriskt om du uppgraderar från en äldre version av tarMK eller vill växla den nya segmenttaggen från en annan typ av beständighet. Mer information om fördelarna med den nya segmenttaggen finns i [Migrering till Oak Segment tar - frågor och svar](/help/sites-deploying/revision-cleanup.md#migrating-to-oak-segment-tar).
>


### Sökning och indexering {#search-amp-indexing}

* Förbättrat stöd för indexeringsåtgärder via ekrun (CLI):

   * Konsekvenskontroll för index
   * Indexeringsstatistik
   * Indexkonfiguration - IME/Export
   * Omindexering

* Minskad Lucene-relaterad databastillväxt för bättre systemprestanda
* Synkrona Lucene-egenskapsindex [(Fler infos)](https://wiki.apache.org/jackrabbit/Synchronous%20Lucene%20Property%20Indexes)
* Förklara frågan i indexhanteraren stöder nu AEM QueryBuilder-syntax
* Indexhanteraren visar nu indexvärden: storlek, senaste uppdaterade och konsekvenskontroll

### Användargränssnitt {#user-interface}

* Ett antal förbättringar har gjorts i användargränssnittet för att göra det mer produktivt och enklare att använda.
* Ny innehållsträd för att snabbt navigera i en hierarki. I kombination med listvyn återställs interaktionsmodellen för klassiskt användargränssnitt.
* Förbättrad bläddring i kort- och listvyn för stora mappar.
* Förbättrad interaktion med sökresultaten - knappen Bakåt återställer det tidigare sökresultatet.
* Ytterligare kortkommandon för de vanligaste åtgärderna, till exempel att öppna en viss rand, redigera, flytta och ta bort objekt eller öppna egenskaper.
* Möjlighet att inaktivera kortkommandon (aktivera/inaktivera i Inställningar).
* Sluta visa tidsstämplar i alla användargränssnittsrelativa efter 7 dagar (ange som standard i Inställningar).

>[!CAUTION]
>
>* Adobe planerar inte att göra fler förbättringar av det klassiska användargränssnittet. AEM 6.4 har det klassiska användargränssnittet och kunder som uppgraderar från tidigare versioner kan fortsätta använda det som det är. Observera att Classic UI fortfarande stöds fullt ut när det är föråldrat [Läs mer](/help/sites-deploying/ui-recommendations.md).
>


### Innehållsdistribution {#content-distribution}

* Förbättrade replikeringsprestanda för publicering av stora volymer
* Stöd för OAuth 2.0-autentisering i Distribution Transport
* Förbättrade prestanda för VLT-paket

### Övervakning {#monitoring}

* En ny systemöversikt ger en ögonblicksbild av all prestandarelaterad systemstatus och alla prestandarelaterade aktiviteter
* Nya hälsokontroller:

   * Identifiera stora Lucene-index
   * Asynkron indexeringshälsa
   * Stora Lucene-index
   * Frågeprestanda
   * Gränser för genomgång av frågor
   * Synkroniserade klockor
   * Systemunderhåll - Revision Cleanup
   * Systemunderhåll - DataStore GC
   * Systemunderhåll - Continuous Revision GC

* Användaren kan nu definiera omfattningen för status.zip-nedladdning

### Underhåll {#maintenance}

* Aktiv borttagning av Lucene-binärfiler med en underhållsåtgärd
* RevisionGC-underhållsaktiviteten för MongoDB har nu inaktiverats till förmån för Continuous Revision Cleanup. Se avsnittet Repository ovan.
* Konfiguration av versionsrensning tillåter att ett minsta antal versioner behålls
* Versionens tömningssteg avbryts i slutet av ett underhållsfönster. Den kan också startas och stoppas manuellt och fortsätter stegvis med nästa start.

### Uppgradera {#upgrade}

* Bakåtkompatibilitet: Bakåtkompatibla funktioner i 6.4 hjälper din anpassade kod att förbli kompatibel i de flesta fall och minskar uppgraderingsbehovet.
* Utvärdering av komplexitet för uppgradering: Det nya mönsterdetektorverktyget som du kan använda för att bedöma hur komplexa dina uppgraderingar är.
* Hållbara uppgraderingar: API-gränssnitt och innehållsklassificering introducerades för att hjälpa er att enkelt följa bästa praxis för en effektiv och sömlös uppgradering till nästa version under hela utvecklingscykeln.
* Omstrukturering av lager: Betydande omstrukturering (främst /etc) för att underlätta enklare uppgraderingar och främja bästa praxis för implementering. [Läs mer.](/help/sites-deploying/repository-restructuring.md)
* Se [Uppgraderingsdokumentation](/help/sites-deploying/upgrade.md) för mer information om dessa funktioner.

### Cloud Services {#cloud-services}

* Många Cloud Services kan nu konfigureras via Touch-gränssnittet. de återstående kan konfigureras under kortet för äldre Cloud Services.
* Platser och resursmappar kan konfigureras med Cloud Services som läses in på ett kontextmedvetet sätt.

### Dokumentskydd {#security}

* Förbättrat och förenklat användargränssnitt med stöd för flera användarprofiler.
* Förbättrade prestanda för stora gruppmedlemskap för användare.

### Projekt och arbetsflöden {#projects-and-workflows}

* Touch UI-baserad arbetsflödesredigerare för att hantera arbetsflödesmodeller på ett effektivare sätt.
* Stöd för rensning av projektaktiviteter i underhållsuppgifter.
