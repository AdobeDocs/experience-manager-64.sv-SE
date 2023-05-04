---
title: AEM Forms Workspace Architecture
seo-title: AEM Forms Workspace Architecture
description: Konceptuell information och översikt över arkitekturen för arbetsytan i LiveCycle AEM Forms.
seo-description: Conceptual information and overview of the architecture of LiveCycle AEM Forms workspace.
uuid: e1a48452-ed44-4ea7-ba38-d961c8faafa5
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: c3a312fb-f684-477d-916d-2d3c99aa7607
exl-id: 30bde8d6-7959-4e4b-a6f4-faf52444e67a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# AEM Forms Workspace Architecture {#aem-forms-workspace-architecture}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM Forms arbetsyta är ett webbprogram som finns på CRX™. När arbetsytan öppnas i en webbläsare öppnas en CRX-resurs och programmet återges som HTML i webbläsaren.

Programmet får åtkomst till AEM Forms-servern på REST-slutpunkter för att göra följande:

* Hämta användaruppgifter, processstartpunkter, processhistorik och användarinformation
* Utför åtgärd för uppgifter
* Fråga uppgifter i databasen
* Uppdatera användarinställningar med mera

AEM Forms-servern har åtkomst till AEM Forms-databasen via JDBC. Databasen innehåller uppgifter, processer och instanser, användare och relaterad information.

AEM Forms arbetsyta är utformad i modulära JavaScript™-komponenter som kan anpassas individuellt och återanvändas i andra webbprogram. Komponenterna baseras på BackBone, som är ett JavaScript-bibliotek som ger struktur åt webbprogram. En detaljerad artikel som beskriver hur komponenter samverkar med BackBone är [här](/help/forms/using/backbone-interaction.md). Hur komponenterna i mappstrukturen för CRX är organiserade beskrivs i [this](/help/forms/using/folder-structure.md) artikel.

Paket för AEM Forms:

* `adobe-lc-workspace-pkg-<version>.zip`: Det är ett CRX-paket, dvs. det kan distribueras i CRX med hjälp av pakethanteraren.
* `adobe-lc-workspace-<version>-src.zip`: Det är ett arkiv som innehåller fullständig kod för AEM Forms arbetsyta och skript för att skapa distributionspaketen Ship, Debug och Dev.
