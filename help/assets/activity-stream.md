---
title: Aktivitetsström på tidslinjen
description: I den här artikeln beskrivs hur du visar aktivitetsloggar för resurser på tidslinjen.
contentOwner: AG
feature: Asset Management
role: User,Admin
exl-id: 52fa2d59-177f-49ca-a480-7213ce0ca7d7
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 8%

---

# Aktivitetsström på tidslinjen {#activity-stream-in-timeline}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Den här funktionen visar aktivitetsloggar för resurser på tidslinjen. Om du utför någon av följande resursrelaterade åtgärder i [!DNL Adobe Experience Manager Assets]uppdaterar funktionen för aktivitetsström tidslinjen så att den återspeglar aktiviteten.

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

Dessutom loggas tidslinjeaktiviteten när nya resurser överförs eller befintliga resurser ändras och checkas in i Experience Manager via [Adobe Asset Link](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/manage-assets-using-adobe-asset-link.ug.html) eller [[!DNL Experience Manager] datorprogram](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/introduction.html).

>[!NOTE]
>
>Övergående arbetsflöden visas inte på tidslinjen eftersom ingen historikinformation sparas för dessa arbetsflöden.

Om du vill visa aktivitetsströmmen utför du en eller flera av åtgärderna för resursen, markerar resursen och väljer sedan **[!UICONTROL Timeline]** från listan GlobalNav.

![tidslinje-3](assets/timeline-3.png)

Tidslinjen visar aktivitetsströmmen för de åtgärder du utför på resurserna.

![activity_stream](assets/activity_stream.png)

>[!NOTE]
>
>Standardplats för logglagring för **Publicera** och **Avpublicera** uppgifter är `/var/audit/com.day.cq.replication/content`. För **Flytta** uppgifter, standardplatsen är `/var/audit/com.day.cq.wcm.core.page`.
