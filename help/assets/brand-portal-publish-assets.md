---
title: Publicera mappar på varumärkesportalen
description: Lär dig hur du publicerar och avpublicerar resurser på varumärkesportalen.
contentOwner: VG
feature: Varumärkesportal
role: Yrkesverksamma inom affärsverksamhet
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '383'
ht-degree: 39%

---


# Publicera resurser på varumärkesportalen {#publish-assets-to-brand-portal}

Som Adobe Experience Manager (AEM) Assets-administratör kan du publicera resurser på AEM Assets Brand Portal-instansen (eller schemalägga publiceringsarbetsflödet till ett senare datum/tid) för din organisation. Du måste dock först konfigurera AEM Assets med varumärkesportalen. Mer information finns i [Konfigurera AEM Assets med varumärkesportalen](configure-aem-assets-with-brand-portal.md).

När du har publicerat en resurs är den tillgänglig för användare i varumärkesportalen.

Om du gör senare ändringar av den ursprungliga resursen i AEM Assets återspeglas inte ändringarna i varumärkesportalen förrän du publicerar om resursen. Funktionen säkerställer att pågående ändringar inte finns i varumärkesportalen. Endast godkända ändringar som publiceras av en administratör finns i varumärkesportalen.

När replikeringen är klar kan du publicera resurser, mappar och samlingar på varumärkesportalen. Så här publicerar du resurser på varumärkesportalen:

>[!NOTE]
>
>Adobe rekommenderar stegvis publicering, helst vid tidpunkter med låg belastning, för att AEM-författaren inte ska uppta för mycket resurser.

1. I resurskonsolen håller du muspekaren över de önskade resurserna och väljer **[!UICONTROL Publish]**-alternativ bland snabbåtgärderna.

   Du kan också välja de resurser du vill publicera på varumärkesportalen.

   ![publish2bp-2](assets/publish2bp-2.png)

2. Följande två alternativ är tillgängliga för att publicera resurserna på varumärkesportalen:
   * [Publicera resurser direkt](#publish-now)
   * [Publicera resurser senare](#publish-later)

## Publicera resurser nu {#publish-now}

Gör något av följande för att publicera de markerade resurserna på varumärkesportalen:

* Välj **[!UICONTROL Quick Publish]** i verktygsfältet. Välj sedan **[!UICONTROL Publish to Brand Portal]** på menyn.

* Välj **[!UICONTROL Manage Publication]** i verktygsfältet.

   1. Välj sedan **[!UICONTROL Publish to Brand Portal]** från **[!UICONTROL Action]** och välj **[!UICONTROL Now]** från **[!UICONTROL Scheduling]**. Tryck/klicka på **[!UICONTROL Next].**

   2. Bekräfta ditt val i **[!UICONTROL Scope]** och tryck/klicka på **[!UICONTROL Publish to Brand Portal]**.

Ett meddelande visas som anger att resurserna har placerats i kö för publicering på varumärkesportalen. Logga in i gränssnittet för varumärkesportalen för att se de publicerade resurserna.

## Publicera resurser senare {#publish-later}

Gör så här för att schemalägga publicering av resurser på varumärkesportalen till ett senare datum eller en senare tid:

1. När du har valt resurser/mappar att publicera väljer du **[!UICONTROL Manage Publication]** i verktygsfältet högst upp.
2. På sidan **[!UICONTROL Manage Publication]** väljer du **[!UICONTROL Publish to Brand Portal]** från **[!UICONTROL Action]** och väljer **[!UICONTROL Later]** från **[!UICONTROL Scheduling]**.

   ![publishlaterbp-1](assets/publishlaterbp-1.png)

3. Markera en **[!UICONTROL Activation date]** och ange en tid. Tryck/klicka på **[!UICONTROL Next]**.
4. Markera en **[!UICONTROL Activation date]** och ange en tid. Tryck/klicka på **[!UICONTROL Next]**.
5. Ange en arbetsflödestitel under **[!UICONTROL Workflows]**. Tryck/klicka på **[!UICONTROL Publish Later]**.

   ![publishworkflow](assets/publishworkflow.png)

Logga nu in på Brand Portal för att se om de publicerade resurserna finns i gränssnittet Brand Portal.

![bp_631_landing_page](assets/bp_landing_page.png)
