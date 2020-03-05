---
title: Publicera mappar på varumärkesportalen
description: Lär dig hur du publicerar och avpublicerar resurser på varumärkesportalen.
contentOwner: VG
translation-type: tm+mt
source-git-commit: f09853921dec6602952f369982a1563c7e4a9727

---


# Publicera resurser på varumärkesportalen {#publish-assets-to-brand-portal}

Som administratör för Adobe Experience Manager-resurser (AEM) kan du publicera resurser i instansen av AEM Assets Brand Portal (eller schemalägga publiceringsarbetsflödet till ett senare datum/tid) för organisationen. Du måste dock först konfigurera AEM Resurser med varumärkesportalen. Mer information finns i [Konfigurera AEM-resurser med varumärkesportalen](configure-aem-assets-with-brand-portal.md).

När du har publicerat en resurs är den tillgänglig för användare i varumärkesportalen.

Om du gör senare ändringar av den ursprungliga resursen i AEM Resurser återspeglas inte ändringarna i varumärkesportalen förrän du publicerar om resursen. Den här funktionen ser till att pågående ändringar inte är tillgängliga i varumärkesportalen. Endast godkända ändringar som publiceras av en administratör är tillgängliga i varumärkesportalen.

När replikeringen är klar kan du publicera resurser, mappar och samlingar på varumärkesportalen. Så här publicerar du resurser på varumärkesportalen:

>[!NOTE]
>
>Adobe rekommenderar att publiceringen staggats, helst under icke-topp-timmar, så att AEM-författaren inte tar upp för mycket resurser.

1. I resurskonsolen håller du muspekaren över de önskade resurserna och väljer **[!UICONTROL alternativet Publicera]** bland snabbåtgärderna.

   Du kan också välja de resurser du vill publicera på varumärkesportalen.

   ![publish2bp-2](assets/publish2bp-2.png)

2. Det finns två tillgängliga alternativ för att publicera resurserna på varumärkesportalen:
   * [Publicera resurser direkt](#publish-now)
   * [Publicera resurser senare](#publish-later)

## Publicera resurser nu {#publish-now}

Gör något av följande om du vill publicera de markerade resurserna på varumärkesportalen:

* Välj **[!UICONTROL Snabbpublicering]** i verktygsfältet. Välj sedan **[!UICONTROL Publicera på varumärkesportalen]** på menyn.

* Välj **[!UICONTROL Hantera publikation]** i verktygsfältet.

   1. Välj sedan **[!UICONTROL Publicera på varumärkesportal]** i **[!UICONTROL Åtgärd]** och välj **[!UICONTROL Now]** i **[!UICONTROL Scheduling]**. Tryck/klicka på **[!UICONTROL Nästa].**

   2. Bekräfta ditt val inom **[!UICONTROL scopet]** och tryck/klicka på **[!UICONTROL Publicera på varumärkesportalen]**.

Ett meddelande visas som anger att resurserna har placerats i kö för publicering på varumärkesportalen. Logga in i gränssnittet för varumärkesportalen för att se de publicerade resurserna.

## Publicera resurser senare {#publish-later}

Så här schemalägger du publicering av resurser på varumärkesportalen till ett senare datum eller en senare tidpunkt:

1. När du har valt resurser/mappar att publicera väljer du **[!UICONTROL Hantera publikation]** i verktygsfältet högst upp.
2. På sidan **[!UICONTROL Hantera publikation]** väljer du **[!UICONTROL Publicera på varumärkesportal]** från **[!UICONTROL åtgärd]** och väljer **[!UICONTROL Senare]** från **[!UICONTROL Schemaläggning]**.

   ![publishlaterbp-1](assets/publishlaterbp-1.png)

3. Välj ett **[!UICONTROL aktiveringsdatum]** och ange tid. Tryck/klicka på **[!UICONTROL Nästa]**.
4. Välj ett **[!UICONTROL aktiveringsdatum]** och ange tid. Tryck/klicka på **[!UICONTROL Nästa]**.
5. Ange en arbetsflödesrubrik under **[!UICONTROL Arbetsflöden]**. Tryck/klicka på **[!UICONTROL Publicera senare]**.

   ![publicerat arbetsflöde](assets/publishworkflow.png)

Logga nu in på Brand Portal för att se om de publicerade resurserna finns i gränssnittet Brand Portal.

![bp_631_landing_page](assets/bp_landing_page.png)
