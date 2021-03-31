---
title: Lägg till vattenstämpel i dina digitala resurser
description: Lär dig hur du använder funktionen Vattenstämpel för att lägga till en digital vattenstämpel till resurser.
contentOwner: AG
feature: Resurshantering
role: Affärsledare,Administratör
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 0%

---


# Vattenstämpla dina digitala resurser {#watermarking}

[!DNL Adobe Experience Manager Assets] gör att du kan lägga till en digital vattenstämpel till resurser som hjälper användarna att verifiera autenticiteten och upphovsrätten till resurserna. [!DNL Experience Manager Assets] stöder text som ska användas som vattenstämpel i PNG- och JPEG-filer.

Med Adobe Experience Manager (AEM) Assets kan du lägga till en digital vattenstämpel i bilder som hjälper användare att verifiera materialets äkthet och upphovsrättsinnehavare. AEM Assets stöder text som ska användas som vattenstämpel i PNG- och JPEG-filer.

Om du vill kunna använda vattenstämpel på resurser lägger du till vattenstämpelsteget i [!UICONTROL DAM Update Asset]-arbetsflödet.

1. Gå till [!DNL Experience Manager]-användargränssnittet och gå till **[!UICONTROL Tools]** > **[!UICONTROL Workflow]** > **[!UICONTROL Models]**.
1. På sidan Arbetsflödesmodeller väljer du arbetsflödet **[!UICONTROL DAM Update Asset]** och klickar på **[!UICONTROL Edit]**.

1. Dra steget **[!UICONTROL Add Watermark]** från sidopanelen och lägg till det i arbetsflödet för [!UICONTROL DAM Update Asset].

   ![Dra steget Lägg till vattenstämpel i arbetsflödet för DAM-uppdateringsresurs](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Placera [!UICONTROL Add Watermark]-steget var som helst före [!UICONTROL Process Thumbnail]-steget.

1. Öppna **[!UICONTROL Add Watermark]**-steget för att visa dess egenskaper.
1. På fliken **[!UICONTROL Arguments]** anger du giltiga värden i de olika fälten, inklusive text, teckensnittstyp, storlek, färg, position, orientering och så vidare. Bekräfta ändringarna genom att klicka på **[!UICONTROL Done]**.

   ![Ange argumenten i steget Lägg till vattenstämpel i Resurser](assets/arguments_add_watermark_aem_assets.png)

1. Spara arbetsflödet **[!UICONTROL DAM Update Asset]** med steget [!UICONTROL Watermark].
1. Ladda upp en exempelresurs från AEM användargränssnitt. Vattenstämpeln visas med teckensnittsstorlek, färg o.s.v. på den plats som du konfigurerade i ovanstående steg.

Om du vill skapa en vattenstämpel i PDF-dokument med programkod eller med dynamisk information kan du använda [AEM Document Services](/help/forms/using/overview-aem-document-services.md)-erbjudandet.

## Tips och begränsningar {#tips-limitations}

* Endast textbaserade vattenstämplar stöds. Bilder används inte som vattenstämplar, även om du kan överföra bilder när du skapar [!UICONTROL Add Watermark Process].
* Endast PNG- och JPEG-filer kan ha vattenstämplar. Andra resursformat har ingen vattenstämpel.
