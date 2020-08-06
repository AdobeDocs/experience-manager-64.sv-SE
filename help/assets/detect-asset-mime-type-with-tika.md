---
title: Använd Apache Tika för att identifiera MIME-typ av digitalt material
description: Aktivera Apache Tika för att hjälpa AEM Assets att identifiera MIME-typen för resurser från innehållsströmmen under överföringen i stället för filtillägget.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 3%

---


# Använd Apache Tika för att identifiera MIME-typ av digitalt material {#detecting-mime-type-of-assets-using-apache-tika}

Vanligtvis identifierar Adobe Experience Manager (AEM) Assets MIME-typen för resurser som du överför från filtillägget. Om du använder Apache Tika för att överföra resurser, identifierar AEM Assets deras MIME-typ från innehållsströmmen under överföringen i stället för filtillägget.

Den här funktionen är inaktiverad som standard. Om du vill aktivera funktionen konfigurerar du tjänsten **Day CQ DAM Mime Type** från Configuration Manager.

>[!NOTE]
>
>MIME-typidentifiering med Apache Tika-biblioteket är en resurskrävande åtgärd.

1. Gå `https://[AEM_server]:[port]/system/console/configMgr` till webbkonsolen för Configuration Manager.
1. I listan med tjänster letar du upp **[!UICONTROL Day CQ DAM Mime Type Service]** och trycker/klickar på **[!UICONTROL Edit]** ikonen bredvid den för att öppna den i redigeringsläget.

1. Välj **[!UICONTROL Detect MIME from content]** alternativet för att aktivera parsning av överförda resurser för att bestämma deras MIME-typ samtidigt som filtillägg ignoreras. Som standard är det här alternativet avmarkerat.

   ![chlimage_1-333](assets/chlimage_1-333.png)

1. Klicka/tryck på **[!UICONTROL Save]** för att spara ändringarna.
