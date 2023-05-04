---
title: Hur processrapportering fungerar
seo-title: How Process Reporting Works
description: Beskrivning av de tjänster som utgör AEM Forms on JEE Process Reporting och en introduktion till användargränssnittet för processrapportering
seo-description: Description of the services that make up the AEM Forms on JEE Process Reporting and an introduction to the Process Reporting UI
uuid: 00a2dd6d-8a6f-4c7b-b03e-81cfd4bcf50d
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: process-reporting
discoiquuid: 4afc68fc-6b39-4c31-95fa-2ef3111c57da
exl-id: 05ef8b08-bb1d-441d-8b02-5f047efbabcb
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '381'
ht-degree: 0%

---

# Hur processrapportering fungerar {#how-process-reporting-works}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Processrapportering är rapporteringsmodulen för AEM Forms i JEE.

Med processrapportering kan du köra rapporter om AEM Forms processer och uppgifter.

Processrapportering använder den inbäddade Process Reporting-databasen för att publicera Forms-data. Sedan används dessa data för att köra rapporter.

Processrapportering består av följande moduler:

* [ProcessDataPublisher-tjänst](/help/forms/using/process-reporting/process-reporting-architecture.md#p-processdatapublisher-service-br-p)
* [Tjänsten ProcessDataStorage](/help/forms/using/process-reporting/process-reporting-architecture.md#p-processdatastorageprovider-service-br-p)
* [OSGi-tjänst](/help/forms/using/process-reporting/process-reporting-architecture.md#p-osgi-service-br-p)
* [Frågedataserver](/help/forms/using/process-reporting/process-reporting-architecture.md#p-querydataservlet-service-br-p)
* [Användargränssnittet för processrapportering](/help/forms/using/process-reporting/process-reporting-architecture.md#p-process-reporting-user-interface-br-p)

## Processrapporteringsarkitektur {#process-reporting-architecture-br}

![processrapportarkitektur](assets/processreportingarchitecture.png)

## Processrapporteringsmoduler {#process-reporting-modules}

### ProcessDataPublisher-tjänst {#processdatapublisher-service-br}

ProcessDataPublisher-servern körs regelbundet på AEM Forms-databasen och extraherar de data som har ändrats sedan den senaste körningen av tjänsten. Sedan publiceras data till datalagringstjänsten för processdata.

Mer information om hur du konfigurerar tjänsten finns i [Konfigurera tjänsten ProcessDataPublisher](/help/forms/using/process-reporting/install-start-process-reporting.md#p-reportconfiguration-service-p).

### Tjänsten ProcessDataStorageProvider {#processdatastorageprovider-service-br}

ProcessDataStorageProvider-tjänsten tar emot processdata från ProcessDataPublisher-tjänsten och sparar data i Process Reporting-databasen.

Mer information om hur du konfigurerar tjänsten finns i [Konfigurera tjänsten ProcessDataStorageProvider](/help/forms/using/process-reporting/install-start-process-reporting.md#p-to-configure-the-process-reporting-repository-locations-p).

### OSGi-tjänst {#osgi-service-br}

QueryDataServlet använder den här tjänsten för att hämta rapportdata från Process Reporting-databasen.

### Tjänsten QueryDataServlet {#querydataservlet-service-br}

Tjänsten QueryDataServlet accepterar frågor från användargränssnittet för processrapportering.

Tjänsten använder sedan OSGi-tjänster för att hämta relevanta rapporteringsdata, bearbetar data och returnerar data till användargränssnittet.

### Användargränssnittet för processrapportering {#process-reporting-user-interface-br}

Användargränssnittet Process Reporting är ett webbläsarbaserat gränssnitt. Du använder det här gränssnittet för att visa process- och uppgiftsinformation som publiceras från AEM Forms-databasen.

### Tjänsten QueryDataServlet {#querydataservlet-service-br-1}

Tjänsten QueryDataServlet accepterar frågor från användargränssnittet för processrapportering.

Tjänsten använder sedan OSGi-tjänster för att hämta relevanta rapporteringsdata, bearbetar data och returnerar data till användargränssnittet.

### Anpassade rapporter {#custom-reports-br}

Du kan skapa egna anpassade rapporter och visa dessa rapporter på fliken Anpassade rapporter i användargränssnittet för processrapportering.

Anvisningar om hur du skapar en anpassad rapport finns i Skapa en anpassad rapport i artikeln [Anpassade rapporter i processrapportering](/help/forms/using/process-reporting/process-reporting-custom-reports.md).
