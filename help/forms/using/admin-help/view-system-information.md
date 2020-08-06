---
title: Visa systeminformation
seo-title: Visa systeminformation
description: Lär dig hur du kan visa resursövervakningsdiagram och information om servern som kör AEM formulär.
seo-description: Lär dig hur du kan visa resursövervakningsdiagram och information om servern som kör AEM formulär.
uuid: 983c1cc7-a8b3-48b2-a4c8-7b28a2e32537
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/health_monitor
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d51460d9-c96c-4661-b93e-e015427878ab
translation-type: tm+mt
source-git-commit: d04e08e105bba2e6c92d93bcb58839f1b5307bd8
workflow-type: tm+mt
source-wordcount: '561'
ht-degree: 0%

---


# Visa systeminformation {#view-system-information}

På fliken System visas resursövervakningsdiagram och information om servern som kör AEM formulär. Om du vill komma åt den här informationen klickar du på Hälsoövervakning i det övre högra hörnet på sidan i administrationskonsolen. Om du kör AEM formulär i en klustermiljö visas informationen för den nod som valts i serverlistan.

Om du vill spara den aktuella systeminformationen som en egenskapsfil klickar du på Spara.

I den högra rutan på fliken System visas grafiska representationer av följande information:

* Jobb- och arbetsräkningsobjekt
* Användning av heap och Allmän heap
* Användning utan heap och implementerad utan heap

Du kan dra pekaren längs tidslinjen för att hämta värden för en viss tidpunkt.

>[!NOTE]
>
>Diagramdata, serverinformationsvärden och klockslag uppdateras var 10:e minut. Informationen visas inte i realtid.

I den vänstra rutan på fliken System visas följande information om servern eller noden:

**Virtuell dator:** Java Virtual Machine-version (JVM) på servern.

**Leverantör av virtuell dator:** Tillverkare av JVM.

**Version för virtuell dator:** JVM-versionsnummer

**Datornamn:** Värdnamn för den server där AEM har installerats.

**Starttid:** Den tid, i timmar och minuter, som servern har körts.

**Just-In-Time Compiler:** The name of the compiler being used.

**Compile Time:** The amount of time spent in compile.

**Number of Live Threads:** The total number of threads currently present in the AEM forms system.

**Number of Threads Peak:** Largest number of live threads ever recorded on the system.

**Number of Loaded Classes:** Number of classes Loaded into the JVM.

**Number of Unloaded Classes:** Number of classes Unloaded from the JVM.

**Minimum Heap:** The minimum amount of heap that was used.

**Maximum Heap:** The maximum amount of heap that was used.

**Operating System Name:** The name of the operating system running on the AEM forms server.

**Operativsystemversion:** Versionsnummer för det operativsystem som körs på AEM formulärserver.

**Operativsystem:** Den operativsystemsarkitektur som JVM körs på.

**Number of Processors:** The number of processors on the system.

**Argument för virtuell dator:** Argumentet som används av JVM.

**Klasssökväg:** Klasssökvägen som används av JVM.

**Bibliotekssökväg:** Bibliotekssökvägen som används av JVM.

**Startklasssökväg:** Den sökväg till startklassen som används av JVM.

**Application Server Type:** Type of application server used to run AEM forms.

**Application Server Version:** Version number of the application server used to run AEM forms.

**Application Server Vendor:** Manufacturer of the application server used to run AEM forms.

**Installation Date:** Date (in yyyy-mm-dd format) that AEM forms was installed.

**AEM forms Version:** Version of AEM forms that is installed.

**Lappningsversion:** AEM formulärkorrigeringsnummer.

**Databasnamn:** Typ av databas som används av AEM formulär.

**Databasversion:** Versionsnummer för den databas som används av AEM formulär.

**Namn på databasenhet:** Namnet på den drivrutin som JVM använder för att ansluta till databasen.

**Databasdrivrutinsversion:** Den version av drivrutinen som JVM använder för att ansluta till databasen.

Med knappen **Spara** kan du spara systeminformationen i en egenskapsfil.
