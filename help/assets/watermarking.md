---
title: Vattenstämpla dina bilder
description: Använd funktionen för vattenstämplar för att lägga till en digital vattenstämpel i PNG- OCH JPEG-bilder.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0e0e2aa693c30c8e1ef1033b936b82d83e5b348e

---


# Vattenstämpla dina resurser {#watermarking}

Med Adobe Experience Manager Assets (AEM) kan ni lägga till en digital vattenstämpel i bilder som hjälper användarna att verifiera autenticiteten och copyrightäganderätten för resurserna. AEM Resurser stöder text som ska användas som vattenstämpel i PNG- och JPEG-filer.

Om du vill kunna använda vattenstämpel på resurser lägger du till steget [!UICONTROL Vattenstämpel] i arbetsflödet för [!UICONTROL DAM-uppdatering av resurser] .

1. Tryck på AEM-logotypen och gå till **[!UICONTROL Verktyg]** > **[!UICONTROL Arbetsflöde]** > **[!UICONTROL Modeller]**.
1. På sidan Arbetsflödesmodeller väljer du arbetsflödet **[!UICONTROL DAM-uppdatering av resurs]** och klickar på **[!UICONTROL Redigera]**.

1. Dra steget **[!UICONTROL Lägg till vattenstämpel]** från sidopanelen och lägg till det i arbetsflödet för [!UICONTROL DAM-uppdatering av resurser] .

   ![Lägg till vattenstämpelsteg i arbetsflödet för DAM-uppdateringsresurser](assets/add_watermark_step_aem_assets.png)

   >[!NOTE]
   >
   >Placera steget [!UICONTROL Lägg till vattenstämpel] var som helst före steget [!UICONTROL Bearbeta miniatyrbild] .

1. Öppna steget **[!UICONTROL Lägg till vattenstämpel]** för att visa dess egenskaper.
1. På fliken **[!UICONTROL Argument]** anger du giltiga värden i de olika fälten, inklusive text, teckensnittstyp, storlek, färg, position, orientering och så vidare. Bekräfta ändringarna genom att trycka/klicka på ikonen Klar.

   ![Ange argumenten i steget Lägg till vattenstämpel i Resurser](assets/arguments_add_watermark_aem_assets.png)

1. Spara arbetsflödet för **[!UICONTROL DAM-uppdatering av resurser]** med steget [!UICONTROL Vattenstämpel] .
1. Ladda upp en exempelresurs från AEM-användargränssnittet. Vattenstämpeln visas med teckensnittsstorlek, färg o.s.v. på den plats som du konfigurerade i ovanstående steg.
