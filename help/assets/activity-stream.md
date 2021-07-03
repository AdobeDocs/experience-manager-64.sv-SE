---
title: Aktivitetsström på tidslinjen
description: 'I den här artikeln beskrivs hur du visar aktivitetsloggar för resurser på tidslinjen. '
contentOwner: AG
feature: Resurshantering
role: User,Admin
exl-id: 52fa2d59-177f-49ca-a480-7213ce0ca7d7
source-git-commit: 5d96c09ef764b02e08dcdf480da1ee18f4d9a30c
workflow-type: tm+mt
source-wordcount: '217'
ht-degree: 23%

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

Dessutom loggas tidslinjeaktiviteten när nya resurser överförs eller befintliga resurser ändras och checkas in i AEM via [Adobe Asset Link](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-assets-using-adobe-asset-link.ug.html) eller [datorversionen av AEM](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/introduction.html).

>[!NOTE]
>
>Övergående arbetsflöden visas inte på tidslinjen eftersom ingen historikinformation sparas för dessa arbetsflöden.

Om du vill visa aktivitetsströmmen utför du en eller flera av åtgärderna för resursen, markerar resursen och väljer sedan **[!UICONTROL Timeline]** i listan GlobalNav.

![tidslinje-3](assets/timeline-3.png)

Tidslinjen visar aktivitetsströmmen för de åtgärder du utför på resurserna.

![activity_stream](assets/activity_stream.png)

>[!NOTE]
>
>Standardplatsen för logglagring för **Publicera** och **Avpublicera**-åtgärder är `/var/audit/com.day.cq.replication/content`. För **Flytta**-åtgärder är standardplatsen `/var/audit/com.day.cq.wcm.core.page`.
