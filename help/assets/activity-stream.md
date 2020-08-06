---
title: Aktivitetsström på tidslinjen
description: 'I den här artikeln beskrivs hur du visar aktivitetsloggar för resurser på tidslinjen. '
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 26%

---


# Aktivitetsström på tidslinjen {#activity-stream-in-timeline}

Den här funktionen visar aktivitetsloggar för resurser på tidslinjen. Om du utför någon av följande resursrelaterade åtgärder i Adobe Experience Manager (AEM) Resurser uppdaterar funktionen för aktivitetsström tidslinjen för att återspegla aktiviteten.

Följande åtgärder är loggade i aktivitetsströmmen:

* Skapa
* Ta bort
* Ladda ned (inklusive återgivningar)
* Publicera
* Avpublicera
* Godkänn
* Avvisa
* Flytta

Aktivitetsloggarna som ska visas på tidslinjen hämtas från platsen `/var/audit/com.day.cq.dam/content/dam` i CRX, där loggfiler lagras.

Dessutom loggas tidslinjeaktiviteten när nya resurser överförs eller befintliga resurser ändras och checkas in i AEM via [Adobe Asset Link](https://helpx.adobe.com/se/enterprise/using/manage-assets-using-adobe-asset-link.html) eller [datorversionen av AEM](https://docs.adobe.com/content/help/en/experience-manager-desktop-app/using/introduction.html).

>[!NOTE]
>
>Övergående arbetsflöden visas inte på tidslinjen eftersom ingen historikinformation sparas för dessa arbetsflöden.

Om du vill visa aktivitetsströmmen utför du en eller flera av åtgärderna för resursen, markerar resursen och väljer sedan **[!UICONTROL Timeline]** i listan GlobalNav.

![tidslinje-3](assets/timeline-3.png)

Tidslinjen visar aktivitetsströmmen för de åtgärder du utför på resurserna.

![activity_stream](assets/activity_stream.png)

>[!NOTE]
>
>The default log storage location for **Publish** and **Unpublish** tasks is `/var/audit/com.day.cq.replication/content`. For **Move** tasks, the default location is `/var/audit/com.day.cq.wcm.core.page`.
