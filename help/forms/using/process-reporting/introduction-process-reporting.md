---
title: Introduktion till processrapportering
seo-title: Introduction to Process Reporting
description: Introduktion och viktiga funktioner i AEM Forms om JEE Process Reporting
seo-description: Introduction and key capabilities of AEM Forms on JEE Process Reporting
uuid: a33ea729-7e1f-4093-bdb6-b8dc3afd59a7
content-type: reference
topic-tags: process-reporting
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 0cfe62b8-839e-414b-95e5-1bfce6a9d16a
exl-id: 279b2f89-5b91-4b8f-ab0f-8ade9b9f3932
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 0%

---

# Introduktion till processrapportering {#introduction-to-process-reporting}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

![processrapportering](assets/process-reporting.png)

Process Reporting är ett webbläsarbaserat verktyg som du använder för att skapa och visa rapporter om AEM Forms processer och uppgifter.

Processrapportering innehåller en uppsättning användningsklara rapporter som gör att du kan filtrera, visa information om långvariga processer, processers varaktighet och arbetsflödesvolym.

Ytterligare processrapportering är ett gränssnitt för att köra ad hoc-frågor och integrera anpassade rapportvyer i användargränssnittet för processrapportering.

En lista över webbläsare som stöds finns i [Plattformar som stöds av AEM Forms](/help/forms/using/aem-forms-jee-supported-platforms.md).

Processrapportering bygger på moduler som:

* Läs processdata från AEM Forms-databasen
* Publicera processdata till en inbäddad Process Reporting-databas
* Tillhandahåller ett webbläsarbaserat användargränssnitt för att visa rapporter

## Nyckelfunktioner {#key-capabilities}

### Alltid aktiverad rapportering {#always-on-reporting}

![platshantering](assets/site-management.png)

Visa listan över långvariga processer, processens tidsplaneringsdiagram och kör anpassade frågor med filter.

Med Process Reporting kan du också exportera rapport- och frågedata i CSV-format.

### Ad hoc-rapporter {#adhoc-reports}

![print-&amp;-color](assets/print-&-colour.png)

Använd filter för att få en specifik vy över dina data.

Du kan söka efter processer eller uppgifter efter ID, varaktighet, start- och slutdatum, processinitierare osv.

Du kan kombinera flera filter för att skapa specifika rapporter.

Du kan sedan spara rapportfiltren så att de kan köras vid ett senare datum eller en senare tidpunkt.

### Process-/aktivitetshistorik {#process-task-history}

![filhantering](assets/file-management.png)

AEM Forms-servrar kör flera processer parallellt. Dessa processer fortsätter att gå från ett läge till ett annat. Genom att publicera Forms-data till Process Reporting-databasen med regelbundna intervall, bevarar Process Reporting övergångsinformationen om de processer som körs i AEM Forms.

### Åtkomstkontroll {#access-control-br}

![namnlös](assets/untitled.png)

Processrapportering ger behörighetsbaserad åtkomst till användargränssnittet.

Det innebär att bara användare med rapportbehörigheter har åtkomst till användargränssnittet för processrapportering.
