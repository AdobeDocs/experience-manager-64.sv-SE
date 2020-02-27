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
translation-type: tm+mt
source-git-commit: 9cc06c16122b98146c51ac61d7fa27553a9d971e

---


# Om användning av faser i AEM 3D {#about-the-use-of-stages-in-aem-d}

Stegen är lättviktiga 3D-scenfiler som innehåller den grundläggande visningsmiljön (ljus, bakgrunder, markplan eller annan fast geometri), fördefinierade kameror (tillval) och renderingsinställningar för tredjepartsrenderare.

>[!NOTE]
>
>Formatet **[!UICONTROL OBJ 3D]** stöder inte ljus. Det kan därför inte användas för att tillhandahålla faser till AEM 3D.

Scenens filformat avgör vilken renderare du kan använda med den scenen. Om till exempel Autodesk® Maya® används för återgivning av hög kvalitet måste scenen vara i `.ma` eller i `.mb` format. Om du bara tänker använda standardåtergivaren för Rapid Refine™ kan du välja vilket scenfilformat som stöds.

Alla renderingsinställningar i AEM 3D, förutom bildtyp och storlek för utdata, måste vara förkonfigurerade och sparade i scenfilen innan de kan överföras till AEM.