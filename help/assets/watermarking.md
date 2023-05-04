---
title: Lägg till vattenstämpel i dina digitala resurser
description: Lär dig hur du använder funktionen Vattenstämpel för att lägga till en digital vattenstämpel till resurser.
contentOwner: AG
feature: Asset Management
role: User,Admin
exl-id: ed01143c-b516-44f8-aceb-ad2e3f0106b2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 0%

---

# Vattenstämpla era digitala resurser {#watermarking}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

[!DNL Adobe Experience Manager Assets] gör att du kan lägga till en digital vattenstämpel till resurser som hjälper användarna att verifiera autenticiteten och upphovsrätten till resurserna. [!DNL Experience Manager Assets] stöder text som ska användas som vattenstämpel i PNG- och JPEG-filer.

Med Adobe Experience Manager Assets kan du lägga till en digital vattenstämpel i bilder som hjälper användarna att verifiera autenticiteten och upphovsrättsinnehållet i materialet. [!DNL Experience Manager] Resurser har stöd för text som ska användas som vattenstämpel i PNG- och JPEG-filer.

Om du vill kunna använda vattenstämpel på resurser lägger du till vattenstämpelsteget i dialogrutan [!UICONTROL DAM Update Asset] arbetsflöde.

1. Öppna [!DNL Experience Manager] användargränssnitt och gå till **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]**.
1. På sidan Arbetsflödesmodeller väljer du **[!UICONTROL DAM Update Asset]** arbetsflöde och klicka **[!UICONTROL Edit]**.

1. Dra från sidopanelen **[!UICONTROL Add Watermark]** och lägga till det i [!UICONTROL DAM Update Asset] arbetsflöde.

   ![Dra steget Lägg till vattenstämpel i arbetsflödet för DAM-uppdateringsresurs](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Placera [!UICONTROL Add Watermark] var som helst före [!UICONTROL Process Thumbnail] steg.

1. Öppna **[!UICONTROL Add Watermark]** för att visa dess egenskaper.
1. I **[!UICONTROL Arguments]** anger du giltiga värden i de olika fälten, inklusive text, teckensnittstyp, storlek, färg, position, orientering och så vidare. Bekräfta ändringarna genom att klicka på **[!UICONTROL Done]**.

   ![Ange argumenten i steget Lägg till vattenstämpel i Resurser](assets/arguments_add_watermark_aem_assets.png)

1. Spara **[!UICONTROL DAM Update Asset]** arbetsflöde med [!UICONTROL Watermark] steg.
1. Från [!DNL Experience Manager] -användargränssnittet, överföra en exempelresurs. Vattenstämpeln visas med teckensnittsstorlek, färg o.s.v. på den plats som du konfigurerade i ovanstående steg.

Om du vill lägga till en vattenstämpel i PDF-dokument med programkod eller med dynamisk information bör du överväga att använda [[!DNL Experience Manager] Dokumenttjänster](/help/forms/using/overview-aem-document-services.md) erbjuder.

## Tips och begränsningar {#tips-limitations}

* Endast textbaserade vattenstämplar stöds. Bilder används inte som vattenstämplar, även om du kan överföra bilder när du skapar [!UICONTROL Add Watermark Process].
* Endast PNG- och JPEG-filer kan ha vattenstämplar. Andra resursformat har ingen vattenstämpel.
