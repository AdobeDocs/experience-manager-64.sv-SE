---
title: Publicera mappar på varumärkesportalen
description: Lär dig hur du publicerar och avpublicerar resurser på Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: 6b78124d-4022-452f-8d0f-b667de337bf4
source-git-commit: de5632ff0ee87a4ded88e792b57e818baf4c01a3
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 34%

---

# Publicera resurser på varumärkesportalen {#publish-assets-to-brand-portal}

Som Adobe Experience Manager Assets-administratör kan du publicera resurser på [!DNL Experience Manager Assets Brand Portal]-instansen (eller schemalägga publiceringsarbetsflödet till ett senare datum/tid) för din organisation. Du måste dock först konfigurera [!DNL Assets] med [!DNL Brand Portal]. Mer information finns i [Konfigurera [!DNL Assets] med [!DNL Brand Portal]](configure-aem-assets-with-brand-portal.md).

När du har publicerat en resurs är den tillgänglig för användare i Brand Portal.

Om du gör senare ändringar i den ursprungliga resursen i [!DNL Assets] återspeglas inte ändringarna i Brand Portal förrän du publicerar resursen på nytt. Funktionen säkerställer att pågående ändringar inte finns i varumärkesportalen. Endast godkända ändringar som publiceras av en administratör finns i varumärkesportalen.

När replikeringen är klar kan du publicera resurser, mappar och samlingar till [!DNL Brand Portal]. Så här publicerar du resurser på Brand Portal:

>[!NOTE]
>
>Adobe rekommenderar att publiceringen stagneras, helst under icke-toppade timmar, så att författaren [!DNL Experience Manager] inte tar upp för mycket resurser.

1. I resurskonsolen håller du muspekaren över de önskade resurserna och väljer **[!UICONTROL Publish]**-alternativ bland snabbåtgärderna.

   Du kan också välja de mediefiler du vill publicera till Brand Portal.

   ![publish2bp-2](assets/publish2bp-2.png)

2. Följande två alternativ är tillgängliga när du vill publicera mediefiler till Brand Portal:
   * [Publicera resurser direkt](#publish-now)
   * [Publicera resurser senare](#publish-later)

## Publicera resurser nu {#publish-now}

Gör något av följande för att publicera de markerade resurserna på varumärkesportalen:

* Välj **[!UICONTROL Quick Publish]** i verktygsfältet. Välj sedan **[!UICONTROL Publish to Brand Portal]** på menyn.

* Välj **[!UICONTROL Manage Publication]** i verktygsfältet.

   1. Välj sedan **[!UICONTROL Publish to Brand Portal]** från **[!UICONTROL Action]** och välj **[!UICONTROL Now]** från **[!UICONTROL Scheduling]**. Tryck/klicka på **[!UICONTROL Next].**

   2. Bekräfta ditt val i **[!UICONTROL Scope]** och tryck/klicka på **[!UICONTROL Publish to Brand Portal]**.

Ett meddelande visas som anger att resurserna har placerats i kö för publicering på varumärkesportalen. Logga in i Brand Portal gränssnitt för att se de publicerade resurserna.

## Publicera resurser senare {#publish-later}

Gör så här för att schemalägga publicering av resurser på varumärkesportalen till ett senare datum eller en senare tid:

1. När du har valt resurser/mappar att publicera väljer du **[!UICONTROL Manage Publication]** i verktygsfältet högst upp.
2. På sidan **[!UICONTROL Manage Publication]** väljer du **[!UICONTROL Publish to Brand Portal]** från **[!UICONTROL Action]** och väljer **[!UICONTROL Later]** från **[!UICONTROL Scheduling]**.

   ![publishlaterbp-1](assets/publishlaterbp-1.png)

3. Markera en **[!UICONTROL Activation date]** och ange en tid. Tryck/klicka på **[!UICONTROL Next]**.
4. Markera en **[!UICONTROL Activation date]** och ange en tid. Tryck/klicka på **[!UICONTROL Next]**.
5. Ange en arbetsflödestitel under **[!UICONTROL Workflows]**. Tryck/klicka på **[!UICONTROL Publish Later]**.

   ![publishworkflow](assets/publishworkflow.png)

Logga sedan in på Brand Portal för att se om de publicerade resurserna är tillgängliga i Brand Portal gränssnitt.

![bp_631_landing_page](assets/bp_landing_page.png)
