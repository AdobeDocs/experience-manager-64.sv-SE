---
title: Säkerhetskopieringsstrategi för Connector for EMC Documentum-användare
seo-title: Backup strategy for Connector for EMC Documentum users
description: Kontrollera hur du skapar en säkerhetskopieringsstrategi för Connector for EMC Documentum-användare.
seo-description: Check how to create a backup strategy for Connector for EMC Documentum users.
uuid: 5d8a0476-5231-4e1d-96c4-ae3df68e09f0
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e83b1a59-a730-4d22-9d58-1c9c38e5d534
exl-id: 933c3903-2040-41f4-b803-4d672ce9a2dc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 0%

---

# Säkerhetskopieringsstrategi för Connector for EMC Documentum-användare {#backup-strategy-for-connector-for-emc-documentum-users}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Om du har installerat Connector for EMC Documentum måste du, förutom instruktionerna i det här kapitlet, även säkerhetskopiera (eller återställa) den dator där respektive ECM-system är installerat. (Se ECM Documentum-dokumentationen).

Säkerhetskopiera AEM genom att använda ECM-databasen och utföra följande uppgifter:

* Säkerhetskopiera AEM genom att följa instruktionerna i det här dokumentet.
* Säkerhetskopiera ECM Documentum-systemet genom att följa instruktionerna i [Säkerhetskopiera EMC Documentum Content Server](/help/forms/using/admin-help/backing-recovering-emc-documentum-repository.md#back-up-the-emc-documentum-content-server).

Återställ AEM genom att använda ECM-databasen och utföra följande uppgifter:

* Återställ respektive ECM-system genom att följa instruktionerna i [Återställ EMC Documentum Content Server](/help/forms/using/admin-help/backing-recovering-emc-documentum-repository.md#restore-the-emc-documentum-content-server).
* Återställ AEM genom att följa instruktionerna i det här dokumentet.
