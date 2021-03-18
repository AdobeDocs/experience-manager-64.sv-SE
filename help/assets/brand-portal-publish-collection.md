---
title: Publicera samlingar på varumärkesportalen
description: Lär dig hur du publicerar och avpublicerar samlingar på varumärkesportalen.
contentOwner: VG
feature: Varumärkesportal
role: Yrkesverksamma inom affärsverksamhet
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 22%

---


# Publicera samlingar på varumärkesportalen {#publish-collections-to-brand-portal}

Som Adobe Experience Manager (AEM) Assets-administratör kan du publicera samlingar till AEM Assets Brand Portal-instansen för din organisation. Du måste dock först integrera AEM Assets med Brand Portal. Mer information finns i [Konfigurera AEM Assets med varumärkesportalen](configure-aem-assets-with-brand-portal.md).

Om du gör senare ändringar i den ursprungliga samlingen i AEM Assets återspeglas inte ändringarna i varumärkesportalen förrän du publicerar samlingen igen. Den här egenskapen ser till att ändringar i pågående arbete inte är tillgängliga i varumärkesportalen. Endast godkända ändringar som publiceras av en administratör finns i varumärkesportalen.

>[!NOTE]
>
>Det går inte att publicera innehållsfragment på varumärkesportalen. Om du väljer innehållsfragment på AEM Author är därför inte åtgärden **[Publicera på varumärkesportalen]** tillgänglig.
>
>Om samlingar som innehåller innehållsfragment publiceras från AEM Author till Brand Portal replikeras allt innehåll i mappen, förutom innehållsfragment, till gränssnittet Brand Portal.

## Publicera en samling på varumärkesportalen {#publish-a-collection-to-brand-portal}

1. I AEM Assets-gränssnittet: tryck/klicka på AEM logotyp. Gå sedan till **[!UICONTROL Assets > Collections]** från sidan **[!UICONTROL Navigation]**.
2. På Samlingar-konsolen väljer du den samling du vill publicera på varumärkesportalen.

   ![select_collection](assets/select_collection.png)

3. Tryck/klicka på **[!UICONTROL Publish to Brand Portal]** i verktygsfältet.

   ![publish_to_bp_icon](assets/publish_to_bp_icon.png)

4. Tryck/klicka på **[!UICONTROL Publish]** i bekräftelsedialogrutan.
5. Stäng bekräftelsemeddelandet.
6. Logga in på varumärkesportalen som administratör. Den publicerade samlingen är tillgänglig i samlingskonsolen.

   ![published_collection](assets/published_collection.png)

## Avpublicera samlingar {#unpublish-collections}

Du kan avpublicera samlingar som du publicerar från AEM Assets till varumärkesportalen. När du har avpublicerat den ursprungliga samlingen är dess kopia inte längre tillgänglig för Brand Portal-användare.

1. Gå till Samlingar-konsolen för din AEM Assets-instans och välj den samling som du vill avpublicera.

   ![select_collection-1](assets/select_collection-1.png)

2. Tryck/klicka på ikonen **[!UICONTROL Remove from Brand Portal]** i verktygsfältet.

   ![remove_from_bp_icon](assets/remove_from_bp_icon.png)

3. Tryck/klicka på **[!UICONTROL Unpublish]** i dialogrutan.
4. Stäng bekräftelsemeddelandet. Samlingen tas bort från varumärkesportalens gränssnitt.
