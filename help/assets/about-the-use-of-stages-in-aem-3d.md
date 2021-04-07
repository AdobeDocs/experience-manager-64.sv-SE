---
title: Om användning av faser i AEM 3D
seo-title: Om användning av faser i AEM 3D
description: Stegen är lättviktiga 3D-scenfiler som utgör den grundläggande visningsmiljön.
seo-description: Stegen är lättviktiga 3D-scenfiler som utgör den grundläggande visningsmiljön.
uuid: 9098278c-0467-45ea-98ad-7f345c314d9e
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 7b9d3b81-3bb4-4ca6-b6e1-f9adfb455855
exl-id: 6d82fec0-608e-4eaa-aebd-b3ce2f7d8088
feature: 3D-resurser
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 0%

---

# Om användning av faser i AEM 3D {#about-the-use-of-stages-in-aem-d}

Stegen är lättviktiga 3D-scenfiler som innehåller den grundläggande visningsmiljön (ljus, bakgrunder, markplan eller annan fast geometri), fördefinierade kameror (tillval) och renderingsinställningar för tredjepartsrenderare.

>[!NOTE]
>
>Formatet **[!UICONTROL OBJ 3D]** stöder inte ljus. Det kan därför inte användas för att tillhandahålla faser till AEM 3D.

Scenens filformat avgör vilken renderare du kan använda med den scenen. Om till exempel Autodesk® Maya® används för återgivning av hög kvalitet måste scenen vara i formatet `.ma` eller `.mb`. Om du bara tänker använda standardåtergivaren för Rapid Refine™ kan du välja vilket scenfilformat som stöds.

Alla renderingsinställningar i AEM 3D förutom utdatabildstyp och -storlek måste förkonfigureras och sparas i scenfilen innan du kan överföra till AEM.
