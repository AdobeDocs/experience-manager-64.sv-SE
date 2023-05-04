---
title: Aktivera och inaktivera säkert säkerhetskopieringsläge
seo-title: Enabling and disabling safe backup mode
description: På sidan Säkerhetskopieringsinställningar kan du använda AEM formulär i säkert säkerhetskopieringsläge så att du kan säkerhetskopiera databasen och GDS-katalogen (Global Document Storage). Lär dig hur du aktiverar och inaktiverar läget för säker säkerhetskopiering.
seo-description: On the Backup Settings page, you can operate AEM forms in safe backup mode so that you can reliably back up your database and Global Document Storage (GDS) (GDS) directory. Learn how to enable and disable safe backup mode.
uuid: 2fdeaeaf-e969-40a4-8aee-1f2b627d3942
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 9fda71e4-78a1-4581-9d02-bf06a75c3bcb
exl-id: 309a8cef-e84d-485b-9a7c-786a93e83c85
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Aktivera och inaktivera säkert säkerhetskopieringsläge {#enabling-and-disabling-safe-backup-mode}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

På sidan Säkerhetskopieringsinställningar kan du använda AEM formulär i säkert säkerhetskopieringsläge så att du kan säkerhetskopiera databasen och GDS-katalogen (Global Document Storage).

AEM formulär är i säkert säkerhetskopieringsläge, men fungerar normalt, förutom att det inte aktivt tar bort filer från GDS-katalogen.

>[!NOTE]
>
>Om du ställer in det här alternativet säkerhetskopieras inte systemet; förbereder systemet för säkerhetskopiering.

## Aktivera säkert säkerhetskopieringsläge {#enable-safe-backup-mode}

1. I administrationskonsolen klickar du på Inställningar > Core Systems Settings > Backup Settings.
1. På sidan Säkerhetskopieringsinställningar väljer du Använd i säkert säkerhetskopieringsläge och klickar på OK.

>[!NOTE]
>
>Om systemet redan körs i säkert säkerhetskopieringsläge skapas ingen ny reservation när du klickar på OK.

## Inaktivera säkert säkerhetskopieringsläge {#disable-safe-backup-mode}

1. I administrationskonsolen klickar du på Inställningar > Core Systems Settings > Backup Settings.
1. Avmarkera Använd i säkert säkerhetskopieringsläge på sidan Inställningar för säkerhetskopiering och klicka på OK.
