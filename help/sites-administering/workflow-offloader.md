---
title: Resursavlastare för arbetsflöde
seo-title: Resursavlastare för arbetsflöde
description: Lär dig mer om Assets Workflow Offloader.
seo-description: Lär dig mer om Assets Workflow Offloader.
uuid: d1c93ef9-a0e1-43c7-b591-f59d1ee4f88b
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 91f0fd7d-4b49-4599-8f0e-fc367d51aeba
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '601'
ht-degree: 2%

---


# Resursförskjutning av arbetsflöde{#assets-workflow-offloader}

Med Resursarbetsflödesavlastaren kan du aktivera flera instanser av Adobe Experience Manager (AEM) Resurser för att minska bearbetningsbelastningen på den primära (utlösande) instansen. Bearbetningsinläsningen fördelas mellan ledarinstansen och de olika förinläsarinstanser (arbetare) som du lägger till i den. Genom att distribuera materialets bearbetningsbelastning blir det effektivare och snabbare att bearbeta materialet i AEM Assets. Dessutom kan du tilldela dedikerade resurser för att bearbeta resurser av en viss MIME-typ. Du kan till exempel tilldela en specifik nod i din topologi till att endast bearbeta InDesign-resurser.

## Konfigurera offloader-topologi {#configure-offloader-topology}

Använd Configuration Manager för att lägga till URL:en för ledarinstansen och värdnamnen för offloader-instanser för anslutningsbegäranden i ledarinstansen.

1. Tryck/klicka på AEM logotyp och välj **Verktyg** > **Åtgärder** > **Webbkonsol** för att öppna Configuration Manager.
1. På webbkonsolen väljer du **Sling** > **Topologihantering**.

   ![chlimage_1-44](assets/chlimage_1-44.png)

1. Tryck/klicka på länken **Configure Discovery.Oak Service** på sidan Topology Management.

   ![chlimage_1-45](assets/chlimage_1-45.png)

1. På sidan Konfiguration av sökningstjänst anger du anslutnings-URL:en för ledarinstansen i fältet **Topology Connector URL:er**.

   ![chlimage_1-46](assets/chlimage_1-46.png)

1. I fältet **Topology Connector Whitelist** anger du IP-adress eller värdnamn för avlastarinstanser som tillåts ansluta till ledarinstansen. Tryck/klicka på **Spara**.

   ![chlimage_1-47](assets/chlimage_1-47.png)

1. Om du vill visa avlastarinstanserna som är anslutna till ledarinstansen går du till **Verktyg** > **Distribution** > **Topologi** och trycker/klickar på klustervyn.

## Inaktivera avlastning av {#disable-offloading}

1. Tryck/klicka på AEM logotyp och välj **Verktyg** > **Distribution** > **Avlastning**. Sidan **Avlastar webbläsare** visar ämnen och serverinstanser som kan använda ämnena.

   ![chlimage_1-48](assets/chlimage_1-48.png)

1. Inaktivera *com/adobe/granite/workflow/avloading*-avsnittet om de ledarinstanser som användare interagerar med för att överföra eller ändra AEM resurser.

   ![chlimage_1-49](assets/chlimage_1-49.png)

## Konfigurera startprogram för arbetsflöden i ledarinstansen {#configure-workflow-launchers-on-the-leader-instance}

Konfigurera startprocesser för arbetsflöden så att arbetsflödet **DAM Update Asset Offloading** används i ledarinstansen i stället för arbetsflödet **DAM Update Asset**.

1. Tryck/klicka på AEM logotyp och välj **Verktyg** > **Arbetsflöde** > **Startare** för att öppna konsolen **Arbetsflödesladdare**.

   ![chlimage_1-50](assets/chlimage_1-50.png)

1. Leta reda på de två startkonfigurationerna med händelsetypen **Noden har skapats** respektive **Noden har ändrats**, som kör arbetsflödet **DAM Update Asset**.
1. För varje konfiguration markerar du kryssrutan före den och trycker/klickar på ikonen **Visa egenskaper** i verktygsfältet för att visa dialogrutan **Startegenskaper**.

   ![chlimage_1-51](assets/chlimage_1-51.png)

1. Välj **DAM Update Asset Offloading** i listan **Arbetsflöde** och tryck/klicka på **Spara**.

   ![chlimage_1-52](assets/chlimage_1-52.png)

1. Tryck/klicka på AEM logotyp och välj **Verktyg** > **Arbetsflöde** > **Modeller** för att öppna sidan **Arbetsflödesmodeller**.
1. Välj arbetsflödet **DAM Update Asset Offloading** och tryck/klicka på **Redigera** i verktygsfältet för att visa informationen.

   ![chlimage_1-53](assets/chlimage_1-53.png)

1. Visa snabbmenyn för steget **DAM Workflow Offloading** och välj **Redigera**. Kontrollera posten i fältet **Jobbämne** på fliken **Generiska argument** i konfigurationsdialogrutan.

   ![chlimage_1-54](assets/chlimage_1-54.png)

## Inaktivera startfunktioner för arbetsflödet på avlastarinstanserna {#disable-the-workflow-launchers-on-the-offloader-instances}

Inaktivera arbetsflödet som startar arbetsflödet som kör arbetsflödet **DAM Update Asset** på ledarinstansen.

1. Tryck/klicka på AEM logotyp och välj **Verktyg** > **Arbetsflöde** > **Startare** för att öppna konsolen **Arbetsflödesladdare**.

   ![chlimage_1-55](assets/chlimage_1-55.png)

1. Leta reda på de två startkonfigurationerna med händelsetypen **Noden har skapats** respektive **Noden har ändrats**, som kör arbetsflödet **DAM Update Asset**.
1. För varje konfiguration markerar du kryssrutan före den och trycker/klickar på ikonen **Visa egenskaper** i verktygsfältet för att visa dialogrutan **Startegenskaper**.

   ![chlimage_1-56](assets/chlimage_1-56.png)

1. I avsnittet **Aktivera **drar du skjutreglaget för att inaktivera startprogrammet för arbetsflödet och trycker/klickar på **Spara** för att inaktivera det.

   ![chlimage_1-57](assets/chlimage_1-57.png)

1. Överför alla resurser av typen bild vid ledarinstansen. Kontrollera miniatyrbilderna som genereras och porteras tillbaka för resursen av den avlastade instansen.

