---
title: Översikt över hälsoövervakning
seo-title: Overview of Health Monitor
description: Det här dokumentet innehåller en översikt över hälsoövervakaren och information om hur du kan komma åt den.
seo-description: This document provides the overview of the Health monitor, and details about how you can access it.
uuid: 5934fd2d-80a5-4c6d-b3ee-882c2865705b
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/health_monitor
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: c303e967-944d-40b0-96ca-f91e2f42a0d0
exl-id: 70ccc0ae-04c6-4af9-9150-72d0d71c945f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 0%

---

# Översikt över hälsoövervakning {#overview-of-health-monitor}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Health Monitor ger viktig information om AEM som serverinformation, minnesanvändning och processoranvändning. Det finns också tillgänglig statistik för Work Manager, t.ex. antalet arbetsobjekt eller jobb i kön och deras status. Du kan utföra följande uppgifter med Hälsoövervakning:

* Kontrollera att systemet körs som det ska
* Visa information för att hjälpa till att diagnostisera systemproblem när de uppstår
* Utför åtgärder på arbetsuppgifter eller jobb som visar problem
* Rensa inaktuella poster från Job Manager-databasen

Hälsoövervakarsidan i administrationskonsolen har tre flikar:

* På fliken System visas resursövervakningsdiagram och information om formulärservern (eller noden i en klustermiljö). (Se [Visa systeminformation](/help/forms/using/admin-help/view-system-information.md#view-system-information).)
* Fliken Arbetshanteraren visar data som är relaterade till Arbetshanteraren, t.ex. antalet arbetsobjekt i arbetshanterarkön. Du kan filtrera informationen genom att använda olika villkor eller hantera enskilda arbetsobjekt med åtgärdsverktygen. (Se [Visa statistik för Work Manager](/help/forms/using/admin-help/view-statistics-related-manager.md#view-statistics-related-to-work-manager).)
* På fliken Schemaläggaren för jobbtömning kan du rensa bort inaktuella poster från jobbhanterardatabasen. (Se [Rensa poster från Job Manager-databasen](/help/forms/using/admin-help/purge-records-job-manager-database.md#purge-records-from-the-job-manager-database).)

Webbsidan för Hälsoövervakaren innehåller statistik som samlats in via ett Gemfire-API. Denna API identifierar automatiskt alla noder i ett kluster. Det löser också säkerhetsproblem som uppstår vid insamling av statistik från proxyservrar eller belastningsutjämnare. Det finns Java-alternativ för att finjustera hälsoövervakaren och minska påverkan på prestanda i AEM formulärmiljö. (Se [Finjustera prestanda för hälsoövervakning](/help/forms/using/admin-help/fine-tuning-health-monitor-performance.md#fine-tuning-health-monitor-performance).)

**Hälsoövervakning för åtkomst**

1. Klicka på Hälsoövervakning i det övre högra hörnet på sidan i administrationskonsolen.
