---
title: Lazy Content Migration
seo-title: Lazy Content Migration
description: Läs mer om migrering av Lazy-innehåll i AEM 6.4.
seo-description: Learn about Lazy Content Migration in AEM 6.4.
uuid: 9c84f7fe-31d3-4b63-8975-9e75a6c44b7d
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: upgrading
discoiquuid: 282a828a-edb2-4643-9bf7-ec30c29dc6ce
feature: Upgrading
exl-id: 8dc2dfb8-037f-40ae-a962-ced89dd3fdd0
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 3%

---

# Lazy Content Migration{#lazy-content-migration}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

För bakåtkompatibilitet, innehåll och konfiguration i **/etc** och **/content** från och med AEM 6.3 inte kommer att ändras eller ändras omedelbart med uppgraderingen. Detta görs för att säkerställa att kundapplikationernas beroenden av dessa strukturer förblir intakta. Funktionerna för dessa innehållsstrukturer är fortfarande desamma även om innehållet i en av rutorna AEM 6.4 ligger på en annan plats.

Även om inte alla dessa platser kan omvandlas automatiskt är det några fördröjda `CodeUpgradeTasks` kallas även Lazy Content Migration. Detta gör att kunderna kan utlösa dessa automatiska omformningar genom att starta om instansen med den här systemegenskapen:

```shell
-Dcom.adobe.upgrade.forcemigration=true
```

Detta orsakar `CodeUpgradeTasks` som ska köras under migreringen.

Målet är en effektiv exekvering, men den här uppgraderingsprocessen är synkron och har därför en driftstopp beroende på hur mycket innehåll som behöver bearbetas. Vi rekommenderar att du utvärderar körningstiderna i en scenmiljö framför ett produktionssystem för att planera en underhållsperiod.

Eftersom detta vanligtvis även kräver att du justerar programmet bör aktiviteten utföras tillsammans med motsvarande programdistribution.

Nedan finns en fullständig lista över `CodeUpgradeTasks` som introducerades i 6.4:

| **Namn** | **Relevant för AEM versioner före** | **Migreringstyp** | **Detaljer** |
|---|---|---|---|
| `Cq561ProjectContentUpgrade` | &lt; 5.6.1 | Omedelbar |  |
| `Cq60MSMContentUpgrade` | &lt; 6.0 | Omedelbar | Identifierar alla `LiveRelationShips` från `VersionStorage` som har tagits bort och lägga till undantagsegenskap i överordnad |
| `Cq61CloudServicesContentUpgrade` | &lt; 6.1 | Omedelbar | Omstrukturerar molntjänster för säker som standard |
| `Cq62ConfContentUpgrade` | &lt; 6.2 | Omedelbar | Tar bort egenskapsbaserad länkning från **/content** till **/conf** (ersätts av OSGi-mekanismen), genererar motsvarande OSGi-konfiguration |
| `Cq62FormsContentUpgrade` | &lt; 6.2 | Omedelbar | På grund av hanteringen av merge_preserve åsidosätter regeln för säkert som standard behörigheter som leder till behovet av att beställa om vid uppgradering |
| `CQ62Html5SmartFileUpgrade` | &lt; 6.2 | Omedelbar | Identifierar komponenter med hjälp av HTML5SmartFile-widgeten, söker efter användning av komponenten i innehållet och omstrukturerar beständighet, vilket innebär att binärfilen flyttas en nivå nedåt och inte lagras på komponentnivå. |
| `Cq62ProjectsCodeUpgrade` | &lt; 6.2 | Omedelbar | Flyttar gamla stilprojekt från **/etc/projects** till **/content/projects** |
| `Cq62TargetCampaignsContentUpgrade` | &lt; 6.2 | Omedelbar | Lägger till ett behållarlager i hierarkin (områden) och justerar referenser. |
| `Cq62TargetContentUpgrade` | &lt; 6.2 | Omedelbar | Anger namn på fasta platser som målkomponenter. |
| `Cq62WorkflowContentUpgrade` | &lt; 6.2 | Omedelbar | Komplex omvandling av arbetsflödesmodeller som föregår 6.2-strukturer, instanser, meddelanden och sedan sammanfogas från säkerhetskopieringsplatsen **/var/backup** |
| `CQ63AssetsMetadataFormsUpdate` | &lt; 6.3 | Omedelbar | Flyttar resurser, anpassade metadatamatchningar och bearbetningsprofiler från **/apps** till **/conf** och översätter metadataram och metadataprofiler från coral2 till coral3. |
| `CQ63AssetsSearchFacetsUpdate` | &lt; 6.3 | Omedelbar | Flyttar resurser och anpassade sökfaktorer från **/apps** till **/conf** och översätter metadataram och metadataprofiler från coral2 till coral3. |
| `CQ63InboxItemsUpgrade` | &lt; 6.3 | Omedelbar | Uppdaterar InboxItems för att ordna inkorgsobjekt (justera metadata för effektiv sortering) |
| `CQ63MetadataSchemaConfigUpdate` | &lt; 6.3 | Omedelbar | Justerar egenskapen metadataSchema i mappen genom att ersätta relativa sökvägar till **/conf** i stället för **/apps** |
| `CQ63MobileAppsNavUpgrade` | &lt; 6.3 | Omedelbar | Justera navigeringsstrukturen |
| `CQ63MonitoringDashboardsConfigUpdate` | &lt; 6.3 | Omedelbar | Flyttar anpassade konfigurationer för kontrollpaneler från **/libs** och **/apps** |
| `CQ63ProcessingProfileConfigUpdate` | &lt; 6.3 | Omedelbar | Översätter egenskapen processingProfile (används till och med 6.1) i Assets för att matcha 6.3-strukturen och senare. Justerar även profilens relativa sökvägar till **/conf** i stället för **/apps**. |
| `CQ63ToolsMenuEntriesContentUpgrade` | &lt; 6.3 | Omedelbar | Uppgraderingsåtgärd som tar bort inaktuella menyposter i CRXDE Lite och webbkonsolen vid en uppgradering. |
| `CQ64CommunitiesConfigsCleanupTask` | &lt; 6.3 | Fördröjd | Flytta SRP-molnkonfigurationer, community watchwords-konfigurationer, rensa upp **/etc/social** och **/etc/enablement** (alla referenser och data måste justeras när en lat migrering körs - ingen programdel ska längre vara beroende av den här strukturen). |
| `CQ64LegacyCloudSettingsCleanupTask` | &lt; 6.4 | Fördröjd | Rensar **/etc/molninställningar** (innehåller ContextHub-konfiguration). Konfigurationen migreras automatiskt vid första åtkomsten. Om Lazy Content Migration startas tillsammans med en uppgradering av det här innehållet i **/etc/molninställningar** måste bevaras via paketet innan uppgraderingen och installeras om för att den implicita omvandlingen ska komma igång, tillsammans med en efterföljande avinstallation av paketet efter att det har slutförts. |
| `CQ64UsersTitleFixTask` | &lt; 6.4 | Fördröjd | Justerar den äldre rubrikstrukturen till titeln i användarprofilnoden. |
| `CQ64CommerceMigrationTask` | &lt; 6.4 | Fördröjd | Migrera e-handelsinnehåll från **/etc/commerce** till **/var/commerce**. När migreringsinnehållet flyttas och referenser till flyttat innehåll uppdateras för att återspegla den nya platsen. |
