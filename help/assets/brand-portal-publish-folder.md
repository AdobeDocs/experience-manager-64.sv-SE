---
title: Publicera mappar på varumärkesportalen
description: Lär dig hur du publicerar och avpublicerar mappar till Brand Portal.
contentOwner: VG
feature: Brand Portal
role: User
exl-id: f41ab750-5780-42ae-a131-5bc748280215
source-git-commit: 3c050c33a384d586d74bd641f7622989dc1d6b22
workflow-type: tm+mt
source-wordcount: '496'
ht-degree: 31%

---

# Publicera mappar på varumärkesportalen {#publish-folders-to-brand-portal}

Som Adobe Experience Manager (AEM) Assets-administratör kan du publicera resurser och mappar i AEM Assets Brand Portal-instansen (eller schemalägga publiceringsarbetsflödet till ett senare datum/tid) för din organisation. Du måste dock först integrera AEM Assets med Brand Portal. Mer information finns i [Konfigurera AEM Assets med varumärkesportalen](configure-aem-assets-with-brand-portal.md).

När du har publicerat en resurs eller mapp är den tillgänglig för användare i Brand Portal.

Om du gör senare ändringar i den ursprungliga resursen eller mappen i AEM Assets återspeglas inte ändringarna i Brand Portal förrän du publicerar resursen eller mappen på nytt. Funktionen säkerställer att pågående ändringar inte finns i varumärkesportalen. Endast godkända ändringar som publiceras av en administratör finns i varumärkesportalen.

## Publicera mappar på varumärkesportalen {#publish-folders-to-brand-portal-1}

1. I AEM Assets-gränssnittet för du pekaren över den önskade mappen och väljer **[!UICONTROL Publish]**-alternativ bland snabbåtgärderna.

   Du kan också markera önskad mapp och följa stegen nedan.

   ![publish2bp](assets/publish2bp.png)

2. **Publicera mappar nu**

   Gör något av följande för att publicera de markerade mapparna på varumärkesportalen:

   * Välj **[!UICONTROL Quick Publish]** i verktygsfältet. Välj sedan **[!UICONTROL Publish to Brand Portal]** på menyn.
   * Välj **[!UICONTROL Manage Publication]** i verktygsfältet.

3. Välj sedan **[!UICONTROL Publish to Brand Portal]** från **[!UICONTROL Action]** och välj **[!UICONTROL Now]** från **[!UICONTROL Scheduling]**. Tryck på **[!UICONTROL Next].**
4. Bekräfta ditt val i **[!UICONTROL Scope]** och tryck på **[!UICONTROL Publish to Brand Portal]**.

   Ett meddelande visas som anger att mappen har placerats i kö för publicering på varumärkesportalen. Logga in i Brand Portal-gränssnittet för att se den publicerade mappen.

   **Publicera mappar senare**

   Så här schemalägger du publiceringen i Brand Portal-arbetsflödet för resursmappar till ett senare datum eller en senare tidpunkt:

   1. När du har valt resurser/mappar att publicera väljer du **[!UICONTROL Manage Publication]** i verktygsfältet högst upp.
   2. På sidan **[!UICONTROL Manage Publication]** väljer du **[!UICONTROL Publish to Brand Portal]** från **[!UICONTROL Action]** och väljer **[!UICONTROL Later]** från **[!UICONTROL Scheduling]**.

      ![publishlaterbp](assets/publishlaterbp.png)

   3. Markera en **[!UICONTROL Activation date]** och ange en tid. Tryck på **[!UICONTROL Next]**.
   4. Bekräfta ditt val i **[!UICONTROL Scope]**. Tryck på **[!UICONTROL Next]**.
   5. Ange en arbetsflödestitel under **[!UICONTROL Workflows]**. Tryck på **[!UICONTROL Publish Later]**.

      ![manageschedulepub](assets/manageschedulepub.png)

## Avpublicera mappar från varumärkesportalen {#unpublish-folders-from-brand-portal}

Du kan ta bort en resursmapp som publicerats till Brand Portal genom att avpublicera den från AEM Author-instansen. När du har avpublicerat originalmappen har varumärkesportalens användare har inte längre tillgång till kopian.

Du kan avpublicera mappar från Brand Portal snabbt eller schemalägga dem för ett senare datum och en senare tidpunkt. Gör så här för att avpublicerar resursmappar från varumärkesportalen:

1. I AEM Assets-gränssnittet i AEM Author-instansen väljer du den mapp du vill avpublicera.

   ![publish2bp-1](assets/publish2bp-1.png)

2. Tryck/klicka på **[!UICONTROL Manage Publication]** i verktygsfältet.

3. **Avpublicera från Brand Portal nu**

   Så här avpublicerar du snabbt den önskade mappen från Brand Portal:

   1. På sidan **[!UICONTROL Manage Publication]** väljer du **[!UICONTROL Action]** från **[!UICONTROL Unpublish from Brand Portal]** och från **[!UICONTROL Scheduling]** **[!UICONTROL Now]**.
   2. Tryck/klicka på **[!UICONTROL Next].**
   3. Bekräfta ditt val i **[!UICONTROL Scope]** och tryck på **[!UICONTROL Unpublish from Brand Portal]**.

   ![confirm-unpublish](assets/confirm-unpublish.png)

   **Avpublicera från Brand Portal senare**

   Så här schemalägger du publiceringen av en mapp från Brand Portal till ett senare datum och tid:

   1. På **[!UICONTROL Manage Publication]**-sidan väljer du **[!UICONTROL Action]** från **[!UICONTROL Unpublish from Brand Portal]** och från **[!UICONTROL Scheduling]** välj **[!UICONTROL Later].**
   2. Markera ett **[!UICONTROL Activation date]** och ange tiden. Tryck på **[!UICONTROL Next]**.
   3. Bekräfta ditt val i **[!UICONTROL Scope]** och tryck på **[!UICONTROL Next]**.
   4. Ange **[!UICONTROL Workflow title]** under **[!UICONTROL Workflows]**. Tryck på **[!UICONTROL Unpublish Later].**

      ![unpublishworkflows](assets/unpublishworkflows.png)


>[!NOTE]
>
>Proceduren för att publicera/avpublicera en resurs till/från Brand Portal liknar motsvarande procedur för en mapp.
