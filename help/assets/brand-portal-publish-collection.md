---
title: Publicera samlingar på varumärkesportalen
description: Lär dig hur du publicerar och avpublicerar samlingar på varumärkesportalen.
contentOwner: VG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1

---


# Publicera samlingar på varumärkesportalen {#publish-collections-to-brand-portal}

Som administratör för Adobe Experience Manager-resurser (AEM) kan du publicera samlingar till instansen AEM Assets Brand Portal för din organisation. Du måste dock först integrera AEM Assets med varumärkesportalen. Mer information finns i [Konfigurera AEM Assets-integrering med varumärkesportalen](brand-portal-configuring-integration.md).

Om du gör senare ändringar i den ursprungliga samlingen i AEM Resurser återspeglas inte ändringarna i varumärkesportalen förrän du publicerar samlingen igen. Den här egenskapen ser till att ändringar i pågående arbete inte är tillgängliga i varumärkesportalen. Endast godkända ändringar som publiceras av en administratör är tillgängliga i varumärkesportalen.

>[!NOTE]
>
>Det går inte att publicera innehållsfragment till varumärkesportalen. Om du väljer innehållsfragment på AEM Author är åtgärden **[Publicera på varumärkesportalen]** därför inte tillgänglig.
>
>Om samlingar som innehåller innehållsfragment publiceras från AEM Author till Brand Portal replikeras allt innehåll i mappen, förutom innehållsfragment, till gränssnittet Brand Portal.

## Publicera en samling på varumärkesportalen {#publish-a-collection-to-brand-portal}

1. I gränssnittet för AEM Resurser trycker/klickar du på AEM-logotypen. Gå sedan till **[!UICONTROL Resurser > Samlingar]** på **[!UICONTROL navigeringssidan]** .
2. På Samlingar-konsolen väljer du den samling du vill publicera på varumärkesportalen.

   ![select_collection](assets/select_collection.png)

3. Tryck/klicka på **[!UICONTROL Publicera till varumärkesportal]** i verktygsfältet.

   ![publish_to_bp_icon](assets/publish_to_bp_icon.png)

4. Tryck/klicka på **[!UICONTROL Publicera]** i bekräftelsedialogrutan.
5. Stäng bekräftelsemeddelandet.
6. Logga in på varumärkesportalen som administratör. Den publicerade samlingen är tillgänglig i Samlingar-konsolen.

   ![published_collection](assets/published_collection.png)

## Avpublicera samlingar {#unpublish-collections}

Du kan avpublicera samlingar som du publicerar från AEM Assets till varumärkesportalen. När du har avpublicerat den ursprungliga samlingen är dess kopia inte längre tillgänglig för Brand Portal-användare.

1. Från Samlingar-konsolen i din AEM Resurser-instans och välj den samling du vill avpublicera.

   ![select_collection-1](assets/select_collection-1.png)

2. Tryck/klicka på ikonen **[!UICONTROL Ta bort från varumärkesportal]** i verktygsfältet.

   ![remove_from_bp_icon](assets/remove_from_bp_icon.png)

3. Tryck/klicka på **[!UICONTROL Avpublicera]** i dialogrutan.
4. Stäng bekräftelsemeddelandet. Samlingen tas bort från gränssnittet för varumärkesportalen.
