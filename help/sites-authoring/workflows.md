---
title: Arbeta med arbetsflöden
seo-title: Working with Workflows
description: Med arbetsflöden i AEM kan du automatisera en serie steg som utförs på en sida eller en resurs.
seo-description: Workflows in AEM allow you to automate a series of steps that are performed on a page or asset.
uuid: c4442d2a-c6b0-49d4-a1ce-384017c45bf0
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 7cb99618-d903-4cfb-b0d9-b23d189f6e78
exl-id: 8d318fd5-3d8f-4144-95c8-d90685378a91
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '216'
ht-degree: 6%

---

# Arbeta med arbetsflöden{#working-with-workflows}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM arbetsflöden gör att du kan automatisera en serie steg som utförs på (en eller flera) sidor och/eller resurser.

Vid publicering måste till exempel en redigerare granska innehållet innan en webbplatsadministratör aktiverar sidan. Ett arbetsflöde som automatiserar det här exemplet meddelar varje deltagare när det är dags att utföra det arbete de behöver:

1. Författaren tillämpar arbetsflödet på sidan.
1. Redigeraren får ett arbetsobjekt som anger att de måste granska sidinnehållet. När de är klara anger de att deras arbetsuppgifter är slutförda.
1. Webbplatsadministratören får sedan ett arbetsobjekt som begär att sidan aktiveras. När de är klara anger de att deras arbetsuppgifter är slutförda.

Vanligtvis:

* Innehållsförfattare använder arbetsflöden både på sidor och i arbetsflöden.
* De arbetsflöden du använder är specifika för organisationens affärsprocesser.

Följande sidor omfattar:

* [Använda arbetsflöden på sidor](/help/sites-authoring/workflows-applying.md)
* [Delta i arbetsflöden](/help/sites-authoring/workflows-participating.md)
