---
title: Resursavlastare för arbetsflöde
seo-title: Assets Workflow Offloader
description: Lär dig mer om Assets Workflow Offloader.
seo-description: Learn about the Assets Workflow Offloader.
uuid: d1c93ef9-a0e1-43c7-b591-f59d1ee4f88b
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 91f0fd7d-4b49-4599-8f0e-fc367d51aeba
exl-id: 2ca8e786-042b-44f6-ac60-834eca64f79f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '628'
ht-degree: 2%

---

# Resursavlastare för arbetsflöde{#assets-workflow-offloader}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med Resursarbetsflödesavlastaren kan du aktivera flera instanser av Adobe Experience Manager (AEM) Resurser för att minska bearbetningsbelastningen på den primära (utlösande) instansen. Bearbetningsinläsningen fördelas mellan ledarinstansen och de olika förinläsarinstanser (arbetare) som du lägger till i den. Genom att distribuera materialets bearbetningsbelastning blir det effektivare och snabbare att bearbeta materialet i AEM Assets. Dessutom kan du tilldela dedikerade resurser för att bearbeta resurser av en viss MIME-typ. Du kan till exempel tilldela en specifik nod i din topologi till att endast bearbeta InDesign-resurser.

## Konfigurera offloader-topologi {#configure-offloader-topology}

Använd Configuration Manager för att lägga till URL:en för ledarinstansen och värdnamnen för offloader-instanser för anslutningsbegäranden i ledarinstansen.

1. Tryck/klicka på AEM logotyp och välj **verktyg** > **Operationer** > **Webbkonsol** för att öppna Configuration Manager.
1. På webbkonsolen väljer du **Sling** >  **Topologihantering**.

   ![chlimage_1-44](assets/chlimage_1-44.png)

1. Tryck/klicka på knappen **Konfigurera tjänsten Discovery.Oak** länk.

   ![chlimage_1-45](assets/chlimage_1-45.png)

1. På sidan Konfiguration av sökningstjänst anger du anslutnings-URL:en för ledarinstansen i **Topology Connector-URL:er** fält.

   ![chlimage_1-46](assets/chlimage_1-46.png)

1. I **Topology Connector Whitelist** anger du IP-adress eller värdnamn för offloader-instanser som tillåts ansluta till ledarinstansen. Tryck/klicka **Spara**.

   ![chlimage_1-47](assets/chlimage_1-47.png)

1. Om du vill se avlastarinstanserna som är kopplade till ledarinstansen går du till **verktyg** > **Distribution** > **Topologi** och tryck/klicka på klustervyn.

## Inaktivera avlastning {#disable-offloading}

1. Tryck/klicka på AEM logotyp och välj **verktyg** > **Distribution** > **Avlastning**. The **Avlastar webbläsare** på sidan visas ämnen och serverinstanser som kan använda ämnena.

   ![chlimage_1-48](assets/chlimage_1-48.png)

1. Inaktivera *com/adobe/granite/workflow/offloading* om de ledande instanserna som användare interagerar med för att överföra eller ändra AEM resurser.

   ![chlimage_1-49](assets/chlimage_1-49.png)

## Konfigurera startprogram för arbetsflöden i ledarinstansen {#configure-workflow-launchers-on-the-leader-instance}

Konfigurera startprogram för arbetsflöden att använda **DAM - uppdatera tillgångsavlastning** arbetsflöde på ledarinstansen i stället för **Dam Update Asset** arbetsflöde.

1. Tryck/klicka på AEM logotyp och välj **verktyg** > **Arbetsflöde** > **Startare** för att öppna **Starta arbetsflöden** konsol.

   ![chlimage_1-50](assets/chlimage_1-50.png)

1. Leta reda på de två startkonfigurationerna med händelsetyp **Noden har skapats** och **Noden ändrad** som kör **DAM-uppdateringsresurs** arbetsflöde.
1. För varje konfiguration markerar du kryssrutan före den och trycker/klickar på **Visa egenskaper** -ikonen i verktygsfältet för att visa **Egenskaper för startprogram** -dialogrutan.

   ![chlimage_1-51](assets/chlimage_1-51.png)

1. Från **Arbetsflöde** lista, välj **DAM - uppdatera tillgångsavlastning** och trycka/klicka **Spara**.

   ![chlimage_1-52](assets/chlimage_1-52.png)

1. Tryck/klicka på AEM logotyp och välj **verktyg** > **Arbetsflöde** > **Modeller** för att öppna **Arbetsflödesmodeller** sida.
1. Välj **DAM - uppdatera tillgångsavlastning** arbetsflöde och tryck/klicka **Redigera** i verktygsfältet för att visa information om det.

   ![chlimage_1-53](assets/chlimage_1-53.png)

1. Visa snabbmenyn för **Avlastning av arbetsflöde för DAM** och välja **Redigera**. Verifiera posten i **Jobbämne** fält för **Allmänna argument** -fliken i konfigurationsdialogrutan.

   ![chlimage_1-54](assets/chlimage_1-54.png)

## Inaktivera startfunktioner för arbetsflödet för offloader-instanser {#disable-the-workflow-launchers-on-the-offloader-instances}

Inaktivera startprogram för arbetsflöden som kör **DAM-uppdateringsresurs** arbetsflöde på ledarinstansen.

1. Tryck/klicka på AEM logotyp och välj **verktyg** > **Arbetsflöde** > **Startare** för att öppna **Starta arbetsflöden** konsol.

   ![chlimage_1-55](assets/chlimage_1-55.png)

1. Leta reda på de två startkonfigurationerna med händelsetyp **Noden har skapats** och **Noden ändrad** som kör **DAM-uppdateringsresurs** arbetsflöde.
1. För varje konfiguration markerar du kryssrutan före den och trycker/klickar på **Visa egenskaper** -ikonen i verktygsfältet för att visa **Egenskaper för startprogram** -dialogrutan.

   ![chlimage_1-56](assets/chlimage_1-56.png)

1. I avsnittet **Aktivera **drar du i skjutreglaget för att inaktivera startprogrammet för arbetsflödet och trycker/klickar **Spara** för att inaktivera den.

   ![chlimage_1-57](assets/chlimage_1-57.png)

1. Överför alla resurser av typen bild vid ledarinstansen. Kontrollera miniatyrbilderna som genereras och porteras tillbaka för resursen av den avlastade instansen.
