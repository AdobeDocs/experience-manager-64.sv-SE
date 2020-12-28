---
title: Återge 3D-resurser
seo-title: Återge 3D-resurser
description: Du kan återge 3D-resurser som du har manipulerat och sparat i AEM för att skapa 2D-bilder som ska användas på webbinnehållssidorna.
seo-description: Du kan återge 3D-resurser som du har manipulerat och sparat i AEM för att skapa 2D-bilder som ska användas på webbinnehållssidorna.
uuid: fbbe4fb4-cf21-4752-a2b8-bec2d40e8362
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: bf155d8c-c012-4cb4-89a6-ceead715630e
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 0%

---


# Återge 3D-resurser{#rendering-d-assets}

Du kan återge 3D-resurser som du har manipulerat och sparat i AEM för att skapa 2D-bilder som ska användas på webbinnehållssidorna.

Se [Redigera sidinnehåll](/help/sites-authoring/qg-page-authoring.md#editing-your-page-content).

## Prestandaöverväganden vid återgivning av 3D-resurser {#performance-considerations-when-rendering-d-assets}

Återgivning av 3D-innehåll kräver stora serverresurser, som processor och minne. Därför kan återgivning ofta ta lång tid. Återgivningstiden varierar avsevärt beroende på olika faktorer, utöver den uppenbara modellstorleken och servermaskinvaran:

* **Val** av renderare.

   Standardrenderaren för Rapid Refine™ i AEM 3D ger viss kvalitet vilket ger kortare renderingstider. Det ger ändå högkvalitativa resultat för många program. Återgivare som tillhandahålls via tredjepartsprogram (t.ex. V-Ray™ eller NVIDIA® Mental Ray® som används i Autodesk® Maya® eller Autodesk® 3ds Max®) är i stort konfigurerbara och prestanda-/kvalitetshandel görs när scenen utformas.

* **IBL jämfört med traditionell belysning**.

   Även om den här faktorn har mindre betydelse för standardåtergivningen av Rapid Refine, går det betydligt långsammare att återge tredjepartsrenderare som Mental Ray med IBL-stadier än med traditionella punkt- eller spotlights.

Renderingen Snabb förfining tar normalt några minuter att återge större bilder. Återgivare från tredje part tar ofta många minuter, till och med timmar, när de är konfigurerade för maximal kvalitet.

Konverterings-, bearbetnings- och renderingsjobb köas på servern efter behov för att förhindra serveröverbelastning. Meddelandet&quot;Väntar på återgivning..&quot; visas på nyligen överförda resurser i [!UICONTROL Card View]. Den här statusen anger att andra behandlings- eller återgivningsjobb måste slutföras innan det aktuella återgivningsjobbet kan startas.

>[!NOTE]
>
>En 3D-resurs återges alltid med det ursprungliga materialet, oavsett vilket material som visas i den AEM interaktiva 3D-vyn. Den här funktionaliteten gäller både den inbyggda renderaren Rapid Refine och alla inbyggda renderare.

**Så här återger du 3D-resurser**:

1. Öppna en 3D-resurs för visning.

   Se [Visa 3D-resurser](/help/sites-classic-ui-authoring/classicui-view-3d-assets.md).

1. På **Adobe Experience Manager**-sidan **[!UICONTROL Navigation]** trycker du på **[!UICONTROL Assets]**.
1. Tryck på **[!UICONTROL Card View]** i den nedrullningsbara listan **[!UICONTROL View]** i sidans övre högra hörn.
1. Navigera till ett 3D-objekt som du vill återge.

1. Tryck på 3D-objektets kort för att öppna det på sidan med resursinformation.
1. I närheten av sidans övre vänstra hörn trycker du på listrutan och väljer **[!UICONTROL Render]**.

   ![chlimage_1-13](assets/chlimage_1-13.png)

1. I närheten av det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Stage Selector]** (spotlight) och väljer sedan ett scennamn med bakgrunden och ljuset som du vill använda på 3D-objektet.

   Se [Använda faser i AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

   ![chlimage_1-14](assets/chlimage_1-14.png)

   [!UICONTROL Stage Selector] icon

1. Välj en renderare i listrutan **[!UICONTROL Render]** till vänster på sidan med resursinformation.

   Standardåtergivaren för **[!UICONTROL Rapid Refine]** är alltid tillgänglig. Om den scen du har valt är i ett ursprungligt format, blir motsvarande tredjepartsrenderare även tillgänglig i listan så att du kan välja den.

   Se [Använda faser i AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

1. Gör följande:

   * I **[!UICONTROL Width and Height]**-fälten anger du pixelbredden och -höjden som du vill att bilden ska återges.
   * I fältet **[!UICONTROL Image Name]** anger du namnet på den återgivna bilden.
   * I fältet **[!UICONTROL Export Path]** anger du sökvägen där du vill att den återgivna bilden ska lagras. Du kan också trycka på ikonen **[!UICONTROL Browse]** och navigera till en plats.
   * (Valfritt) Markera eller avmarkera kryssrutan **[!UICONTROL Overwrite existing image]**.

1. I det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Camera Selector]**. Välj en kameravy som du vill använda på den återgivna bilden.

   Vänster- och högerstaplar eller övre och nedre staplar är en visuell indikator på vilka delar av vyn som ska återges. När kameran finns på den valda scenen kan du välja en fördefinierad kamera.

   ![chlimage_1-15](assets/chlimage_1-15.png)

   [!UICONTROL Camera Selector] icon

1. Tryck på **[!UICONTROL Start Render]** för att starta återgivningsprocessen.

   Ett meddelande visas tillfälligt som anger att återgivningen har startat. För enkelhetens skull innehåller det här meddelandet även en länk till det markerade [!UICONTROL Output Folder] så att du kan navigera direkt till det.

