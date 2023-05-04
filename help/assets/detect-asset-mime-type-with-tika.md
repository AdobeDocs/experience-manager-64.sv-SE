---
title: Använd Apache Tika för att identifiera MIME-typ av digitalt material
description: Aktivera Apache Tika som hjälp [!DNL Experience Manager] Resurser identifierar MIME-typen för resurser från innehållsströmmen under överföringen i stället för filtillägget.
contentOwner: AG
feature: Metadata,Developer Tools,Asset Management
role: Admin,Architect
exl-id: 6c9e53e9-5e54-4816-9431-41e796340d1e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '218'
ht-degree: 3%

---

# Använd Apache Tika för att identifiera MIME-typ av digitalt material {#detecting-mime-type-of-assets-using-apache-tika}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Vanligtvis identifierar Adobe Experience Manager Assets MIME-typen för resurser som du överför från filtillägget. Om du använder Apache Tika för att överföra resurser, [!DNL Experience Manager] Resurserna identifierar sin MIME-typ från innehållsströmmen under överföringen i stället för filtillägget.

Den här funktionen är inaktiverad som standard. Om du vill aktivera funktionen konfigurerar du **Dag CQ DAM Mime Type** från Configuration Manager.

>[!NOTE]
>
>MIME-typidentifiering med Apache Tika-biblioteket är en resurskrävande åtgärd.

1. Gå till `https://[AEM_server]:[port]/system/console/configMgr` för att öppna webbkonsolen för Configuration Manager.
1. I listan över tjänster letar du upp **[!UICONTROL Day CQ DAM Mime Type Service]** och tryck/klicka på **[!UICONTROL Edit]** -ikonen bredvid den för att öppna den i redigeringsläget.

1. Välj **[!UICONTROL Detect MIME from content]** om du vill aktivera parsning av överförda resurser för att bestämma deras MIME-typ samtidigt som filtillägg ignoreras. Som standard är det här alternativet avmarkerat.

   ![chlimage_1-333](assets/chlimage_1-333.png)

1. Klicka/tryck på **[!UICONTROL Save]** för att spara ändringarna.
