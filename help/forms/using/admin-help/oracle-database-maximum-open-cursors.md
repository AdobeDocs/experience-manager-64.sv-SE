---
title: Tröskelvärde för högsta antal öppna markörer i oraclets databas
seo-title: Oracle database maximum open cursors threshold
description: Lär dig hur du konfigurerar ett maxvärde för öppna markörer i Oraclet.
seo-description: Learn about configuring a maximum value for open cursors in Oracle.
uuid: c1d20997-f853-4772-b1c6-8cea73221d0a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_aem_forms_database
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d3565776-1b7d-498c-9840-b17f80170d9b
exl-id: ad14ff27-964f-481f-a8ef-052d9cfb7734
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '120'
ht-degree: 0%

---

# Tröskelvärde för högsta antal öppna markörer i oraclets databas {#oracle-database-maximum-open-cursors-threshold}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Om du vill konfigurera ett maxvärde för öppna markörer i Oracle kanske du måste justera det här värdet till ett värde som passar ditt program. Det är uppenbart att under en måttlig belastning var de genomsnittliga öppna markörerna 2 700. Vi rekommenderar att du börjar med en övre gräns på 3 000. Mer information finns på [https://www.orafaq.com/node/758](https://www.orafaq.com/node/758).
