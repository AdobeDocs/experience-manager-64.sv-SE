---
title: Använd Apache Tika för att identifiera MIME-typ av digitalt material
description: Aktivera Apache Tika för att hjälpa AEM Assets att identifiera MIME-typen för resurser från innehållsströmmen under överföringen i stället för filtillägget.
contentOwner: AG
feature: Metadata,Utvecklarverktyg,Resurshantering
role: Administratör,Arkitekt
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '192'
ht-degree: 3%

---


# Använd Apache Tika för att identifiera MIME-typ för digitala resurser {#detecting-mime-type-of-assets-using-apache-tika}

Vanligtvis identifierar Adobe Experience Manager (AEM) Assets MIME-typen för resurser som du överför från filtillägget. Om du använder Apache Tika för att överföra resurser, identifierar AEM Assets deras MIME-typ från innehållsströmmen under överföringen i stället för filtillägget.

Den här funktionen är inaktiverad som standard. Om du vill aktivera funktionen konfigurerar du tjänsten **Day CQ DAM Mime Type** från Configuration Manager.

>[!NOTE]
>
>MIME-typidentifiering med Apache Tika-biblioteket är en resurskrävande åtgärd.

1. Gå till `https://[AEM_server]:[port]/system/console/configMgr` och öppna Configuration Manager-webbkonsolen.
1. Leta reda på **[!UICONTROL Day CQ DAM Mime Type Service]** i listan över tjänster och tryck/klicka på ikonen **[!UICONTROL Edit]** bredvid den för att öppna den i redigeringsläget.

1. Välj alternativet **[!UICONTROL Detect MIME from content]** om du vill aktivera parsning av överförda resurser för att bestämma deras MIME-typ samtidigt som filtillägg ignoreras. Som standard är det här alternativet avmarkerat.

   ![chlimage_1-333](assets/chlimage_1-333.png)

1. Klicka/tryck på **[!UICONTROL Save]** för att spara ändringarna.
