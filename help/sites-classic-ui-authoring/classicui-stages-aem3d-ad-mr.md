---
title: Ställa in ett standardstadium med Autodesk Maya och Mental Ray
seo-title: Ställa in ett standardstadium med Autodesk Maya och Mental Ray
description: Lär dig hur du skapar en standardscen med Autodesk Maya och Mental Ray.
seo-description: Lär dig hur du skapar en standardscen med Autodesk Maya och Mental Ray.
uuid: 05c4858b-6261-4de3-a87a-03dd6bc519a4
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: f30c4039-3bbf-4d02-a9b5-bda6ccce16b9
translation-type: tm+mt
source-git-commit: e0ce860380a28a9dcaa6f8ce94ad278cdbe49fad
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 0%

---


# Ställa in ett standardstadium med Autodesk Maya och Mental Ray{#setting-up-a-standard-stage-with-autodesk-maya-and-mental-ray}

1. I Maya skapar du en ny, tom scen.
1. Skapa en (tillfällig) referens till en representativ modell. Detta underlättar utvärdering av ljus, inställning av kameror och konfiguration av renderaren.

1. Lägg till ljus som vanligt. För närvarande stöder AEM 3D följande ljustyper:

   * Riktningsljus
   * Strålkastare
   * Punktljus

   Andra ljustyper ignoreras eller konverteras till någon av de ovanstående typerna som stöds när scenen överförs till AEM 3D. De konverterade typerna används när du visar resursen och när du återger med den inbyggda funktionen för snabb förfining. De ursprungliga ljustyperna används vid återgivning med Maya.

1. Skapa ett markplan, om det behövs, och använd lämpligt material.

   Adobe rekommenderar att du ställer in ett markplan som enkelsidigt. Om du gör det kan du se resursen nedan i AEM 3D utan att markplanet döljer resursen.

1. (Valfritt) Skapa och konfigurera kameror.

   Låt kamerorna &quot;titta&quot; mot mitten av scenen där resursen ska infogas. Var noga med att ställa in kamerorna på återgivning.

1. Konfigurera rendering med Mental Ray.

   Konfigurera **[!UICONTROL Render Settings]** med följande förslag:

   * **[!UICONTROL Common]** tab

      Avmarkera **[!UICONTROL Alpha channel (mask)]** kryssrutan för alla [!UICONTROL Renderable Cameras].

   * **[!UICONTROL Quality]** tab

      * **[!UICONTROL Overall quality]** `- 0.5` eller mindre
      * **[!UICONTROL Indirect Diffuse (GI) Mode]** - `Final Gather`
      * **[!UICONTROL Filter Size]** - `2.0`, `2.0`
   * Rendera scenen med de typiska bildstorlekar som du förväntar dig att använda. Om det behövs kan du finjustera ljuskällorna, eller [!UICONTROL Render settings]eller båda för att uppnå det resultat du vill ha.

      Tänk på att återgivning med Mental Ray, med bildbaserat ljus, är mycket långsamt och processorintensivt. Adobe rekommenderar att du konfigurerar de inställningar för lägsta kvalitet som fortfarande kan ge önskad återgivningskvalitet.


1. Ta bort referensen som du skapade i steg 2.
1. Spara scenen och avsluta Autodesk Maya.
1. Överför scenen till AEM och vänta tills överföringen är klar.

   Se [Överföra resurser](/help/assets/managing-assets-touch-ui.md#uploading-assets).

   Om Autodesk® Maya® inte är konfigurerad på AEM server exporterar du en FBX från Maya och överför den till AEM.

1. Öppna Resursegenskaper i AEM. Ange Titel till en lämplig sträng som ska visas i listrutan Scenväljare. Kontrollera att **[!UICONTROL Class]** är inställt på **[!UICONTROL 3D Stage]**. Spara och avsluta.
1. Öppna en 3D-resurs, markera den nya scenen och verifiera att den förhandsvisar och återger som förväntat.

