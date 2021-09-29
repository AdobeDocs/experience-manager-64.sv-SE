---
title: Aktivitetsström på tidslinjen
description: 'I den här artikeln beskrivs hur du visar aktivitetsloggar för resurser på tidslinjen. '
contentOwner: AG
feature: Asset Management
role: User,Admin
exl-id: 52fa2d59-177f-49ca-a480-7213ce0ca7d7
source-git-commit: 1679bbab6390808a1988cb6fe9b7692c3db31ae4
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 11%

---

# Aktivitetsström på tidslinjen {#activity-stream-in-timeline}

Den här funktionen visar aktivitetsloggar för resurser på tidslinjen. Om du utför någon av följande resursrelaterade åtgärder i [!DNL Adobe Experience Manager Assets] uppdaterar funktionen för aktivitetsström tidslinjen för att återspegla aktiviteten.

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

Dessutom loggas tidslinjeaktiviteten när nya resurser överförs eller befintliga resurser ändras och checkas in i Experience Manager via [Adobe Asset Link](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-assets-using-adobe-asset-link.ug.html) eller [[!DNL Experience Manager] datorprogrammet](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/introduction.html).

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
