---
title: Vattenstämpla dina bilder
description: Använd funktionen för vattenstämplar för att lägga till en digital vattenstämpel i PNG- OCH JPEG-bilder.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 04de28347ddf0082d2e224aa3853297cad3aacd8
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# Vattenstämpla dina resurser {#watermarking}

Med Adobe Experience Manager (AEM) Assets kan du lägga till en digital vattenstämpel i bilder som hjälper användare att verifiera autenticiteten och upphovsrättsinnehållet i materialet. AEM Assets stöder text som ska användas som vattenstämpel i PNG- och JPEG-filer.

Om du vill kunna använda vattenstämpel på resurser lägger du till [!UICONTROL Watermark] steget i [!UICONTROL DAM Update Asset] arbetsflödet.

1. Tap the AEM logo, and go to **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]**.
1. Välj arbetsflödet på sidan Arbetsflödesmodeller och klicka på **[!UICONTROL DAM Update Asset]** det **[!UICONTROL Edit]**.

1. Dra **[!UICONTROL Add Watermark]** steget från sidopanelen och lägg till det i [!UICONTROL DAM Update Asset] arbetsflödet.

   ![Lägg till vattenstämpelsteg i arbetsflödet för DAM-uppdateringsresurser](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Placera [!UICONTROL Add Watermark] steget var som helst före [!UICONTROL Process Thumbnail] steget.

1. Öppna **[!UICONTROL Add Watermark]** steget för att visa dess egenskaper.
1. Ange giltiga värden i de olika fälten på **[!UICONTROL Arguments]** fliken, inklusive text, teckensnittstyp, storlek, färg, position, orientering och så vidare. Bekräfta ändringarna genom att trycka/klicka på ikonen Klar.

   ![Ange argumenten i steget Lägg till vattenstämpel i Resurser](assets/arguments_add_watermark_aem_assets.png)

1. Save the **[!UICONTROL DAM Update Asset]** workflow with the [!UICONTROL Watermark] step.
1. Ladda upp en exempelresurs från AEM-användargränssnittet. Vattenstämpeln visas med teckensnittsstorlek, färg o.s.v. på den plats som du konfigurerade i ovanstående steg.

Om du vill skapa vattenstämplar i PDF-dokument med programkod eller med dynamisk information bör du överväga att använda [AEM Document Services](/help/forms/using/overview-aem-document-services.md) .
