---
title: Arbeta med startpunkter
seo-title: Arbeta med startpunkter
description: Steg för att arbeta med en AEM Forms-process från din mobila enhet som definieras i Workbench.
seo-description: Steg för att arbeta med en AEM Forms-process från din mobila enhet som definieras i Workbench.
uuid: 9c51ce52-e7ba-43d3-a85c-67067f680ccb
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 265eee8a-364e-4edf-b2a0-f42617169944
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f
workflow-type: tm+mt
source-wordcount: '254'
ht-degree: 0%

---


# Arbeta med startpunkter {#working-with-startpoints}

En startpunkt anropar en process som skapats i Workbench. Den är kopplad till ett formulär som anropar processen när formuläret skickas. Se [Genomgång av Geometrixx Finance Reference Site](/help/forms/using/finance-reference-site-walkthrough.md) för att förstå processerna.

>[!NOTE]
>
>Termerna startpunkter, startprocess och formulär används omväxlande när de refererar till det här konceptet.

Om du vill initiera en process från AEM Forms-appen måste du ha en startpunkt av typen **Workspace** i processen. Du måste även välja alternativet **[!UICONTROL Visibile in Mobile Workspace]** för startpunkten.

![mws_startpoint_select_option](assets/mws_startpoint_select_option.png)

**Så här startar du en process som definieras i Workbench**

1. Gå till [Startskärmen](/help/forms/using/home-screen.md) för att visa startpunkterna i AEM Forms-appen.
1. Listan **[!UICONTROL All Forms]** visas som standard på skärmen **[!UICONTROL Home]**.

   Startpunkten är kopplad till ett formulär. Tryck på det startpunktassocierade formuläret i listan för att öppna det.

   Formuläret som är kopplat till startpunkten öppnas.

1. Ange informationen i **[!UICONTROL Startpoint]**-formuläret.

   Du kan lägga till anteckningar i den här aktiviteten med knappen [attachment](/help/forms/using/add-attachments.md).

1. När du har fyllt i formuläret trycker du på **Skicka**.

Om programmet är offline sparas formuläret och dess data i mappen Utkorgen.

Om appen är online synkroniseras uppgiften med AEM Forms-servern och tilldelas den användare som anges i processen.

Information om hur du arbetar med uppgiften i uppgiftslistan finns i [Öppna en uppgift](/help/forms/using/open-task.md).
