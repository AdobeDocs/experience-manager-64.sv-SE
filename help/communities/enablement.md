---
title: Konfigurera aktiveringsfunktioner
seo-title: Konfigurera aktiveringsfunktioner
description: Konfigurera aktiveringsfunktioner i Communities
seo-description: Konfigurera aktiveringsfunktioner i Communities
uuid: 27be3128-1a7d-412e-99a9-6e3b3b0aec1c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 765a3d9b-4552-403e-872c-fdf684ac271d
role: Administratör
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---


# Konfigurerar aktiveringsfunktioner {#configuring-enablement-features}

## Översikt {#overview}

Med aktiveringsfunktionerna kan du skapa [aktiveringsgrupper](overview.md#enablement-community).

* Den här funktionen kräver ytterligare licensiering för användning i en produktionsmiljö.

Användning av aktiveringsfunktionerna kräver följande:

Installation av:

* **SCORM (**
Sharable Content Object Reference Model) är en samling standarder och specifikationer för e-learning. SCORM definierar också hur innehåll kan paketeras i en överförbar ZIP-fil.

* ****
MySQLMySQL är en relationsdatabas som primärt används för SCORM-spårning och rapportdata för Enablement, samt för tabeller för att spåra videoförloppet. SCORM för aktiveringsfunktionspaketet kräver JDBC-drivrutinen MySQL.

* ****
FFmpegFFmpeg är en lösning för konvertering och direktuppspelning av ljud och video och används, när den är installerad, för korrekt omkodning av  [videomaterial](../../help/sites-authoring/default-components-foundation.md#video). För aktiveringscommunityn används den i redigeringsmiljön för att hämta metadata för överförda resurser och generera en miniatyrbild som visas när resursen listas.

Inställningar för:

* **Community**
ManagersFör aktiveringscommunityer, endast medlemmar i 
`Community Enablement Managers` användargruppen kan tilldelas rollen som  `*Community Site* Enablement Manager`, vars behörigheter kan omfatta innehållsskapande, uppdrag och medlemshantering i publiceringsmiljön.

Valfri konfiguration av:

* **Adobe**
AnalyticsIntegrering med Adobe Analytics ger omfattande rapporteringsfunktioner och stöder tillägget Video Heartbeat i Analytics.

* **Dispatcher**

## Konfigurationssteg {#configuration-steps}

Följande steg är nödvändiga för aktiveringscommunityn.

Varje steg länkar till dokumentation med nödvändig information.

**På alla författar-/publiceringsinstanser:**

1. **[installera JDBC-drivrutin för](deploy-communities.md#jdbc-driver-for-mysql)**
MySQLUse Web Console (paket): Installera  *http://localhost:4502/system/console/*
bundlesInstallera  ** innan du installerar SCORM-paketet

1. **[installera SCORM-](deploy-communities.md#scorm-package)**
paketAnvänd Package Manager: 
*http://localhost:4502/crx/packmgr/*

**På alla servrar:**

1. **[installera MySQL, MySQL Workbench](mysql.md)**

1. **[installera MySQL-](mysql.md#database-setup)**
databaserKör SQL-skript som hämtats från författarinstansen
\
   Använd MySQL Workbench

**På samma server som är värd för författarinstans:**

1. **[installera FFmpeg](ffmpeg.md)**

**På alla författar-/publiceringsinstanser:**

1. **[konfigurera JDBC Connections](mysql.md#configure-jdbc-connections)**
poolAnvänd webbkonsol (configMgr): 
*http://localhost:4502/system/console/configMgr*

1. **[konfigurera SCORM-motortjänsten](mysql.md#aem-communities-scormengine-service)**
Använd webbkonsol (configMgr): 
*http://localhost:4502/system/console/configMgr*

1. **[konfigurera CSRF-](mysql.md#adobe-granite-csrf-filter)**
filterAnvänd webbkonsol (configMgr): 
*http://localhost:4502/system/console/configMgr*

**On author instance:**

1. (*optional*) **[konfigurera tjänsten Analytics](analytics.md)**
Använd verktygs-, distributions- och Cloud Services-konsolen: 
*http://localhost:4502/etc/cloudservices/sitecatalyst.html*

1. **[konfigurera konsolen](ffmpeg.md#configure-ffmpeg-transcoding-service)**
FFmpegUse Workflow/Models

1. **[aktivera Tunnel](deploy-communities.md#tunnel-service-on-author)**
ServiceUse Web Console (configMgr): 
*http://localhost:4502/system/console/configMgr*

1. **[skapa Community-](users.md#creating-community-members)** administratörerI författarmiljön använder du Classic-UI Security console:  *http://localhost:4502/*
useradminskapa användare med sökväg = /home/users/community

   * Lägg till medlemmar i följande grupper:

      * Community Enablement Managers
      * Communities-administratörer

## Dispatcher {#dispatcher}

När distributionen innehåller [AEM Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher.html) måste avsnitten `clientheader`och `filter`ändras för att aktiveringsfunktionerna ska fungera korrekt. Se [Konfigurera Dispatcher för Communities](dispatcher.md#enablement).
