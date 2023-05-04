---
title: Begränsningar för säkerhetskopiering i PDF Generator
seo-title: PDF Generator backup limitations
description: Läs mer om begränsningar för säkerhetskopiering i PDF Generator.
seo-description: Learn about PDF Generator backup limitations.
uuid: 9537ffde-4396-46d1-81ea-edcd25923ffb
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/aem_forms_backup_and_recovery
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 23386353-b2bf-49f1-947a-dd7587bba175
noindex: true
exl-id: d2ba9881-02b6-470b-b110-7d4609e6ab24
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '91'
ht-degree: 0%

---

# Begränsningar för säkerhetskopiering i PDF Generator {#pdf-generator-backup-limitations}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Den temporära katalog som PDF Generator använder för att konvertera filer kan inte säkerhetskopieras. Även om tjänsten återställs korrekt kan data gå förlorade eftersom PDF Generator granskar och rensar innehållet i den tillfälliga katalogen med angivna intervall.
