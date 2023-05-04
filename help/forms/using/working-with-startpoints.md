---
title: Arbeta med startpunkter
seo-title: Working with Startpoints
description: Steg för att arbeta med en AEM Forms-process från din mobila enhet som definieras i Workbench.
seo-description: Steps to work with a AEM Forms process from your Mobile device defined in Workbench.
uuid: 9c51ce52-e7ba-43d3-a85c-67067f680ccb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 265eee8a-364e-4edf-b2a0-f42617169944
exl-id: ef9352c7-c164-4cbf-8f18-5b97aa5f56be
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '272'
ht-degree: 0%

---

# Arbeta med startpunkter {#working-with-startpoints}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

En startpunkt anropar en process som skapats i Workbench. Den är kopplad till ett formulär som anropar processen när formuläret skickas. Se [Genomgång av Geometrixx Finance Reference Site](/help/forms/using/finance-reference-site-walkthrough.md) för att förstå processerna.

>[!NOTE]
>
>Termerna startpunkter, startprocess och formulär används omväxlande när de refererar till det här konceptet.

Om du vill initiera en process från AEM Forms-appen måste du ha en startpunkt av typen **Arbetsyta** i processen. Du måste även välja **[!UICONTROL Visible in Mobile Workspace]** för startpunkten.

![mws_startpoint_select_option](assets/mws_startpoint_select_option.png)

**Så här startar du en process som definieras i Workbench**

1. Om du vill visa startpunkterna i AEM Forms-appen går du till [Hemskärm](/help/forms/using/home-screen.md).
1. På **[!UICONTROL Home]** som standard visas **[!UICONTROL All Forms]** visas.

   Startpunkten är kopplad till ett formulär. Tryck på det startpunktassocierade formuläret i listan för att öppna det.

   Formuläret som är kopplat till startpunkten öppnas.

1. Ange informationen i dialogrutan **[!UICONTROL Startpoint]** formulär.

   Du kan lägga till anteckningar i den här uppgiften med [bifogad](/help/forms/using/add-attachments.md) -knappen.

1. När du har fyllt i formuläret trycker du på **Skicka** -knappen.

Om programmet är offline sparas formuläret och dess data i mappen Utkorgen.

Om appen är online synkroniseras uppgiften med AEM Forms-servern och tilldelas den användare som anges i processen.

Information om hur du arbetar med uppgiften i uppgiftslistan finns i [Öppna en uppgift](/help/forms/using/open-task.md).
