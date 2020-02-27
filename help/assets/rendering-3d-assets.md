---
title: Återge 3D-resurser
seo-title: Återge 3D-resurser
description: Lär dig hur du återger 3D-resurser som du manipulerat och sparat i AEM för att skapa 2D-bilder för dina webbsidor.
seo-description: Lär dig hur du återger 3D-resurser som du manipulerat och sparat i AEM för att skapa 2D-bilder för dina webbsidor.
uuid: ee4d669c-72b1-4f7a-9a68-a7c6d59c7856
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 5b044519-d034-4f05-98c5-f1b299a3ea37
translation-type: tm+mt
source-git-commit: 8c6fdcea0def7720062edfc564c536f8d47e8402

---


# Återge 3D-resurser {#rendering-d-assets}

Du kan återge 3D-resurser som du har manipulerat och sparat i AEM för att skapa 2D-bilder som ska användas på webbinnehållssidorna.

Se [Redigera sidinnehåll](/help/sites-authoring/qg-page-authoring.md#editing-your-page-content).

## Prestandaöverväganden vid återgivning av 3D-resurser {#performance-considerations-when-rendering-d-assets}

Återgivning av 3D-innehåll kräver stora serverresurser, som processor och minne. Därför kan återgivning ofta ta lång tid. Återgivningstiden varierar avsevärt beroende på olika faktorer, utöver den uppenbara modellstorleken och servermaskinvaran:

* **Val** av renderare.

   Standardrenderaren för Rapid Refine™ i AEM 3D ger en viss kvalitet som ger kortare renderingstider. Det ger ändå högkvalitativa resultat för många program. Återgivare som tillhandahålls via tredjepartsprogram (t.ex. V-Ray™ eller NVIDIA® Mental Ray® som används i Autodesk® Maya® eller Autodesk® 3ds Max®) är i stort konfigurerbara och prestanda-/kvalitetshandel görs när scenen utformas.

* **IBL jämfört med traditionell belysning**.

   Även om den här faktorn har mindre betydelse för standardåtergivningen av Rapid Refine, går det betydligt långsammare att återge tredjepartsrenderare som Mental Ray med IBL-stadier än med traditionella punkt- eller spotlights.

Renderingen Snabb förfining tar normalt några minuter att återge större bilder. Återgivare från tredje part tar ofta många minuter, till och med timmar, när de är konfigurerade för maximal kvalitet.

Konverterings-, bearbetnings- och renderingsjobb köas på servern efter behov för att förhindra serveröverbelastning. Meddelandet&quot;Väntar på återgivning..&quot; visas på nyligen överförda resurser i kortvyn. Den här statusen anger att andra behandlings- eller återgivningsjobb måste slutföras innan det aktuella återgivningsjobbet kan startas.

>[!NOTE]
>
>En 3D-resurs återges alltid med det ursprungliga materialet, oavsett vilket material som visas i den interaktiva vyn i AEM 3D. Den här funktionaliteten gäller både den inbyggda renderaren Rapid Refine och alla inbyggda renderare.

**Så här återger du 3D-resurser**:

1. Öppna en 3D-resurs för visning.

   Se [Visa 3D-resurser](viewing-3d-assets.md).

1. Tryck på **[!UICONTROL Resurser]** på **[!UICONTROL navigeringssidan i Adobe Experience Manager]**.
1. I närheten av det övre högra hörnet på sidan, i listrutan **[!UICONTROL Visa]** , trycker du på **[!UICONTROL kortvyn]**.
1. Navigera till ett 3D-objekt som du vill återge.
1. Tryck på 3D-objektets kort för att öppna det på sidan med resursinformation.
1. I närheten av sidans övre vänstra hörn trycker du på listrutan och väljer sedan **[!UICONTROL Återgivning]**.

   ![chlimage_1-369](assets/chlimage_1-369.png)

1. I närheten av det övre högra hörnet på sidan med resursinformation trycker du på ikonen **[!UICONTROL Scenväljare]** (spotlight) och väljer sedan ett scennamn med bakgrunden och ljuset som du vill använda på 3D-objektet.

   Se [Använda scener i AEM 3D](about-the-use-of-stages-in-aem-3d.md).

   ![chlimage_1-370](assets/chlimage_1-370.png)

   **[!UICONTROL Ikon för]** scenväljare

1. Välj en renderare i listrutan **[!UICONTROL Återgivning]** till vänster på sidan med resursinformation.

   Standardrenderaren för **Snabb förfining** är alltid tillgänglig. Om den scen du har valt är i ett ursprungligt format, blir motsvarande tredjepartsrenderare även tillgänglig i listan så att du kan välja den.

   Se [Använda scener i AEM 3D](about-the-use-of-stages-in-aem-3d.md).

1. Gör följande:

   * I fälten **[!UICONTROL Bredd]** och **[!UICONTROL Höjd]** anger du pixelbredden och -höjden som du vill att bilden ska återges.
   * Ange namnet på den återgivna bilden i fältet **[!UICONTROL Bildnamn]** .
   * I fältet **[!UICONTROL Exportsökväg]** anger du sökvägen där du vill att den återgivna bilden ska lagras. Du kan också trycka på ikonen **[!UICONTROL Bläddra]** och navigera till en plats.
   * (Valfritt) Markera eller avmarkera kryssrutan **[!UICONTROL Skriv över befintlig]bild **.

1. I det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Kameraväljare]** . Välj en kameravy som du vill använda på den återgivna bilden.

   Vänster- och högerstaplar eller övre och nedre staplar är en visuell indikator på vilka delar av vyn som ska återges. När kameran finns på den valda scenen kan du välja en fördefinierad kamera.

   ![chlimage_1-371](assets/chlimage_1-371.png)

   **[!UICONTROL Kameraväljare,]** ikon

1. Tryck på **[!UICONTROL Starta återgivning]** för att påbörja återgivningen.

   Ett meddelande visas tillfälligt som anger att återgivningen har startat. För enkelhetens skull innehåller det här meddelandet även en länk till den valda utdatamappen så att du kan navigera direkt till den.

