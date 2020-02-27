---
title: Använd arbetsflöden för att bearbeta digitala resurser
description: Lär dig hur du använder arbetsflöden på resurser, mappar och samlingar i AEM Assets för att bearbeta dina digitala resurser.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1

---


# Tillämpa arbetsflöden på resurser {#applying-workflows-to-assets}

Att använda arbetsflöden på digitala resurser är detsamma som för webbsidor. En fullständig guide om hur du skapar och använder arbetsflöden i AEM finns i [Starta arbetsflöden](../sites-authoring/workflows-participating.md).

Använd arbetsflöden i digitala resurser för att aktivera resursen eller skapa vattenstämplar. Många av arbetsflödena för resurser aktiveras automatiskt. Arbetsflödet som automatiskt skapar en återgivning efter att en bild har redigerats aktiveras till exempel automatiskt.

Om ett arbetsflöde som är tillgängligt i det klassiska användargränssnittet inte är tillgängligt i det beröringsaktiverade användargränssnittet, som begäran om aktivering och begäran om inaktivering, ska du läsa [Göra arbetsflödesmodeller tillgängliga i användargränssnittet](../sites-developing/workflows-models.md#make-workflow-models-available-in-touchui)för touchredigering.

## Tillämpa ett arbetsflöde på en AEM-resurs {#applying-a-workflow-to-an-aem-asset}

Mer information om hur du tillämpar ett arbetsflöde på en AEM-resurs finns i [Starta ett arbetsflöde på en resurs](managing-assets-touch-ui.md#starting-a-workflow-on-an-asset).

## Tillämpa ett arbetsflöde på flera resurser {#applying-a-workflow-to-multiple-assets}

1. I resurskonsolen navigerar du till platsen för de resurser som du vill starta ett arbetsflöde för och väljer resurser.
1. Klicka på ikonen GlobalNav och välj **[!UICONTROL Tidslinje]** på menyn för att visa tidslinjen.

   ![chlimage_1-136](assets/chlimage_1-136.png)

1. Klicka på ikonen **[!UICONTROL Åtgärder]** (pil) längst ned.

   ![chlimage_1-137](assets/chlimage_1-137.png)

1. Klicka på **[!UICONTROL Starta arbetsflöde]**.
1. Välj en arbetsflödesmodell i listan i dialogrutan **[!UICONTROL Starta arbetsflöde]** .

   ![chlimage_1-138](assets/chlimage_1-138.png)

1. (Valfritt) Ange en rubrik för arbetsflödet som kan användas som referens för arbetsflödesinstansen.
1. Klicka på **[!UICONTROL Start]** och sedan på **[!UICONTROL Bekräfta]** i dialogrutan. Arbetsflödet körs på alla resurser som du har valt.

## Tillämpa ett arbetsflöde på flera mappar {#applying-a-workflow-to-multiple-folders}

Hur du tillämpar ett arbetsflöde på flera mappar liknar hur du tillämpar ett arbetsflöde på flera resurser. Markera mapparna i resurskonsolen och utför steg 2-7 i proceduren [Tillämpa ett arbetsflöde på flera resurser](assets-workflow.md#applying-a-workflow-to-multiple-assets).

## Tillämpa ett arbetsflöde på en samling {#applying-a-workflow-to-a-collection}

Mer information om hur du använder ett arbetsflöde i en samling finns i [Köra ett arbetsflöde i en samling](managing-collections-touch-ui.md#running-a-workflow-on-a-collection).
