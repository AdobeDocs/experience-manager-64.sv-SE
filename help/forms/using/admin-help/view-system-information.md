---
title: Visa systeminformation
seo-title: View system information
description: Lär dig hur du kan visa resursövervakningsdiagram och information om servern som kör AEM formulär.
seo-description: Learn how you can view resource monitoring charts and information about the server that is running AEM forms.
uuid: 983c1cc7-a8b3-48b2-a4c8-7b28a2e32537
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/health_monitor
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d51460d9-c96c-4661-b93e-e015427878ab
exl-id: e4542335-fcee-4506-965a-5bfe79f4b29a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---

# Visa systeminformation {#view-system-information}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

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

**Just-in-time-kompilator:** Namnet på den kompilator som används.

**Kompileringstid:** Den tid som har ägnats åt kompileringen.

**Antal live-trådar:** Det totala antalet trådar som för närvarande finns i AEM.

**Högsta antal trådar:** Det största antalet livetrådar som någonsin spelats in i systemet.

**Antal inlästa klasser:** Antal klasser som har lästs in i JVM.

**Antal ej inlästa klasser:** Antal klasser som inte har lästs in från JVM.

**Minsta heap:** Den minsta stackmängden som användes.

**Maximal heap:** Den maximala stackmängden som användes.

**Operativsystemets namn:** Namnet på operativsystemet som körs på AEM formulärserver.

**Operativsystemversion:** Versionsnummer för det operativsystem som körs på AEM formulärserver.

**Operativsystem:** Den operativsystemsarkitektur som JVM körs på.

**Antal processorer:** Antalet processorer i systemet.

**Argument för virtuell dator:** Argumentet som används av JVM.

**Klasssökväg:** Klasssökvägen som används av JVM.

**Bibliotekssökväg:** Bibliotekssökvägen som används av JVM.

**Startklasssökväg:** Den sökväg till startklassen som används av JVM.

**Programservertyp:** Typ av programserver som används för att köra AEM formulär.

**Programserverversion:** Versionsnummer för den programserver som används för att köra AEM formulär.

**Programserverleverantör:** Tillverkare av programservern som används för att köra AEM formulär.

**Installationsdatum:** Datum (i formatet åååå-mm-dd) när AEM har installerats.

**AEM:** AEM som är installerad.

**Lappningsversion:** AEM formulärkorrigeringsnummer.

**Databasnamn:** Typ av databas som används av AEM formulär.

**Databasversion:** Versionsnummer för den databas som används av AEM formulär.

**Namn på databasenhet:** Namnet på den drivrutin som JVM använder för att ansluta till databasen.

**Databasdrivrutinsversion:** Den version av drivrutinen som JVM använder för att ansluta till databasen.

The **Spara** kan du spara den här systeminformationen i en egenskapsfil.
