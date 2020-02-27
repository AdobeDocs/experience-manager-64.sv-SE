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
source-git-commit: 284339ee1ce0ffae97f732b569f73c732f063273

---


# Återge 3D-resurser{#rendering-d-assets}

Du kan återge 3D-resurser som du har manipulerat och sparat i AEM för att skapa 2D-bilder som ska användas på webbinnehållssidorna.

Se [Redigera sidinnehåll](/help/sites-authoring/qg-page-authoring.md#editing-your-page-content).

## Prestandaöverväganden vid återgivning av 3D-resurser {#performance-considerations-when-rendering-d-assets}

Återgivning av 3D-innehåll kräver stora serverresurser, som processor och minne. Därför kan återgivning ofta ta lång tid. Återgivningstiden varierar avsevärt beroende på olika faktorer, utöver den uppenbara modellstorleken och servermaskinvaran:

* **Val** av renderare.

   Standardrenderaren för Rapid Refine™ i AEM 3D ger en viss kvalitet som ger kortare renderingstider. Det ger ändå högkvalitativa resultat för många program. Återgivare som tillhandahålls via tredjepartsprogram (t.ex. V-Ray™ eller NVIDIA® Mental Ray® som används i Autodesk® Maya® eller Autodesk® 3ds Max®) är i stort konfigurerbara och prestanda-/kvalitetshandel görs när scenen utformas.

* **IBL jämfört med traditionell belysning**.

   Även om den här faktorn har mindre betydelse för standardåtergivningen av Rapid Refine, går det betydligt långsammare att återge tredjepartsrenderare som Mental Ray med IBL-stadier än med traditionella punkt- eller spotlights.

Renderingen Snabb förfining tar normalt några minuter att återge större bilder. Återgivare från tredje part tar ofta många minuter, till och med timmar, när de är konfigurerade för maximal kvalitet.

Konverterings-, bearbetnings- och renderingsjobb köas på servern efter behov för att förhindra serveröverbelastning. Meddelandet&quot;Väntar på återgivning..&quot; visas på nyligen överförda resurser i [!UICONTROL kortvyn]. Den här statusen anger att andra behandlings- eller återgivningsjobb måste slutföras innan det aktuella återgivningsjobbet kan startas.

>[!NOTE]
>
>En 3D-resurs återges alltid med det ursprungliga materialet, oavsett vilket material som visas i den interaktiva vyn i AEM 3D. Den här funktionaliteten gäller både den inbyggda renderaren Rapid Refine och alla inbyggda renderare.

**Så här återger du 3D-resurser**:

1. Öppna en 3D-resurs för visning.

   Se [Visa 3D-resurser](/help/sites-classic-ui-authoring/classicui-view-3d-assets.md).

1. Tryck på **[!UICONTROL Assets** på **[!UICONTROL navigeringssidan i Adobe Experience Manager]** ****.
1. I närheten av sidans övre högra hörn trycker du på **kortvyn** i listrutan **[!UICONTROL [!UICONTROL-vy]**.
1. Navigera till ett 3D-objekt som du vill återge.

1. Tryck på 3D-objektets kort för att öppna det på sidan med resursinformation.
1. I närheten av sidans övre vänstra hörn trycker du på listrutan och väljer sedan **[!UICONTROL Återgivning]**.

   ![chlimage_1-13](assets/chlimage_1-13.png)

1. I närheten av det övre högra hörnet på sidan med resursinformation trycker du på ikonen **[!UICONTROL Scenväljare]** (spotlight) och väljer sedan ett scennamn med bakgrunden och ljuset som du vill använda på 3D-objektet.

   Se [Använda scener i AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

   ![chlimage_1-14](assets/chlimage_1-14.png)

   [!UICONTROL Ikon för] scenväljare

1. Välj en renderare i listrutan **[!UICONTROL Återgivning]** till vänster på sidan med resursinformation.

   Standardrenderaren för **[!UICONTROL Snabb förfining]** är alltid tillgänglig. Om den scen du har valt är i ett ursprungligt format, blir motsvarande tredjepartsrenderare även tillgänglig i listan så att du kan välja den.

   Se [Använda scener i AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

1. Gör följande:

   * I fälten **[!UICONTROL Bredd och Höjd]** anger du den pixelbredd och -höjd som du vill att bilden ska återges med.
   * Ange namnet på den återgivna bilden i fältet **[!UICONTROL Bildnamn]** .
   * I fältet **[!UICONTROL Exportsökväg]** anger du sökvägen där du vill att den återgivna bilden ska lagras. Du kan också trycka på ikonen **[!UICONTROL Bläddra]** och navigera till en plats.
   * (Valfritt) Markera eller avmarkera kryssrutan **[!UICONTROL Skriv över befintlig bild]** .

1. I det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Kameraväljare]** . Välj en kameravy som du vill använda på den återgivna bilden.

   Vänster- och högerstaplar eller övre och nedre staplar är en visuell indikator på vilka delar av vyn som ska återges. När kameran finns på den valda scenen kan du välja en fördefinierad kamera.

   ![chlimage_1-15](assets/chlimage_1-15.png)

   [!UICONTROL Kameraväljare,] ikon

1. Tryck på **[!UICONTROL Starta återgivning]** för att påbörja återgivningen.

   Ett meddelande visas tillfälligt som anger att återgivningen har startat. För enkelhetens skull innehåller det här meddelandet även en länk till den valda [!UICONTROL utdatamappen] så att du kan navigera direkt till den.

