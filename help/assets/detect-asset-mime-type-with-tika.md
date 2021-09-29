---
title: Använd Apache Tika för att identifiera MIME-typ av digitalt material
description: Aktivera Apache Tika för att hjälpa [!DNL Experience Manager] Resurser att identifiera MIME-typen för resurser från innehållsströmmen under överföringen i stället för filtillägget.
contentOwner: AG
feature: Metadata,Developer Tools,Asset Management
role: Admin,Architect
exl-id: 6c9e53e9-5e54-4816-9431-41e796340d1e
source-git-commit: 8948bca63f1f5ec9d94ede2fb845ed01b4e23333
workflow-type: tm+mt
source-wordcount: '182'
ht-degree: 3%

---

# Använd Apache Tika för att identifiera MIME-typ av digitalt material {#detecting-mime-type-of-assets-using-apache-tika}

Vanligtvis identifierar Adobe Experience Manager Assets MIME-typen för resurser som du överför från filtillägget. Om du använder Apache Tika för att överföra resurser, identifierar [!DNL Experience Manager] Assets deras MIME-typ från innehållsströmmen under överföringen i stället för filtillägget.

Den här funktionen är inaktiverad som standard. Om du vill aktivera funktionen konfigurerar du tjänsten **Day CQ DAM Mime Type** från Configuration Manager.

>[!NOTE]
>
>MIME-typidentifiering med Apache Tika-biblioteket är en resurskrävande åtgärd.

1. Gå till `https://[AEM_server]:[port]/system/console/configMgr` och öppna Configuration Manager-webbkonsolen.
1. Leta reda på **[!UICONTROL Day CQ DAM Mime Type Service]** i listan över tjänster och tryck/klicka på ikonen **[!UICONTROL Edit]** bredvid den för att öppna den i redigeringsläget.

1. Välj alternativet **[!UICONTROL Detect MIME from content]** om du vill aktivera parsning av överförda resurser för att bestämma deras MIME-typ samtidigt som filtillägg ignoreras. Som standard är det här alternativet avmarkerat.

   ![chlimage_1-333](assets/chlimage_1-333.png)

1. Klicka/tryck på **[!UICONTROL Save]** för att spara ändringarna.
