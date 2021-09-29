---
title: Publicera samlingar på varumärkesportalen
description: Lär dig hur du publicerar och avpublicerar samlingar till Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: c2c6759e-f763-405e-9e45-5a90b9d32df2
source-git-commit: de5632ff0ee87a4ded88e792b57e818baf4c01a3
workflow-type: tm+mt
source-wordcount: '310'
ht-degree: 23%

---

# Publicera samlingar på varumärkesportalen {#publish-collections-to-brand-portal}

Som Adobe Experience Manager Assets-administratör kan du publicera samlingar till [!DNL Experience Manager Assets Brand Portal]-instansen för din organisation. Du måste dock först integrera Assets med Brand Portal. Mer information finns i [Konfigurera Assets med varumärkesportalen](configure-aem-assets-with-brand-portal.md).

Om du gör senare ändringar i den ursprungliga samlingen i Assets återspeglas inte ändringarna i Brand Portal förrän du publicerar samlingen igen. Den här egenskapen ser till att ändringar i pågående arbete inte är tillgängliga i Brand Portal. Endast godkända ändringar som publiceras av en administratör finns i varumärkesportalen.

>[!NOTE]
>
>Det går inte att publicera innehållsfragment på varumärkesportalen. Om du väljer innehållsfragment på [!DNL Experience Manager] Författare är **[Publicera till Brand Portal]**-åtgärden inte tillgänglig.
>
>Om samlingar som innehåller innehållsfragment publiceras från [!DNL Experience Manager] Författare till Brand Portal replikeras allt innehåll i mappen, förutom innehållsfragment, till Brand Portal-gränssnittet.

## Publicera en samling på Brand Portal {#publish-a-collection-to-brand-portal}

1. I resursgränssnittet: tryck/klicka på logotypen [!DNL Experience Manager]. Gå sedan till **[!UICONTROL Assets > Collections]** från sidan **[!UICONTROL Navigation]**.
2. På Samlingar-konsolen väljer du den samling du vill publicera till Brand Portal.

   ![select_collection](assets/select_collection.png)

3. Tryck/klicka på **[!UICONTROL Publish to Brand Portal]** i verktygsfältet.

   ![publish_to_bp_icon](assets/publish_to_bp_icon.png)

4. Tryck/klicka på **[!UICONTROL Publish]** i bekräftelsedialogrutan.
5. Stäng bekräftelsemeddelandet.
6. Logga in på Brand Portal som administratör. Den publicerade samlingen är tillgänglig i samlingskonsolen.

   ![published_collection](assets/published_collection.png)

## Avpublicera samlingar {#unpublish-collections}

Du kan avpublicera samlingar som du publicerar från Assets till Brand Portal. När du har avpublicerat originalsamlingen är kopian inte längre tillgänglig för Brand Portal-användare.

1. Från Samlingar-konsolen för din [!DNL Assets]-instans och välj den samling som du vill avpublicera.

   ![select_collection-1](assets/select_collection-1.png)

2. Tryck/klicka på ikonen **[!UICONTROL Remove from Brand Portal]** i verktygsfältet.

   ![remove_from_bp_icon](assets/remove_from_bp_icon.png)

3. Tryck/klicka på **[!UICONTROL Unpublish]** i dialogrutan.
4. Stäng bekräftelsemeddelandet. Samlingen tas bort från varumärkesportalens gränssnitt.
