---
title: Ställa in ett standardstadium med Autodesk Maya och Mental Ray
seo-title: Ställa in ett standardstadium med Autodesk Maya och Mental Ray
description: Konfigurera en standardscen med Autodesk Maya och Mental Ray
seo-description: Konfigurera en standardscen med Autodesk Maya och Mental Ray
uuid: 3895fda6-29ae-46f5-b2bc-abc989808648
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: da8fc33b-84ae-4ead-87bb-5a7870a38b1f
exl-id: facd0411-8a3c-4b1a-af9d-0d59e0399b2c
feature: 3D-resurser
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '414'
ht-degree: 0%

---

# Konfigurera en standardscen med Autodesk Maya och Mental Ray {#setting-up-a-standard-stage-with-autodesk-maya-and-mental-ray}

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

   Konfigurera renderingsinställningarna med följande förslag:

   * **[!UICONTROL Common]** tab

      Avmarkera kryssrutan **[!UICONTROL Alpha channel (mask)]** för alla återgivningsbara kameror.

   * **[!UICONTROL Quality]** tab

      * **[!UICONTROL Overall quality]** `- 0.5` eller mindre
      * **[!UICONTROL Indirect Diffuse (GI) Mode]** - `Final Gather`
      * **[!UICONTROL Filter Size]** - `2.0`, `2.0`
   * Rendera scenen med de typiska bildstorlekar som du förväntar dig att använda. Om det behövs kan du finjustera ljusen, renderingsinställningarna eller båda för att få önskat resultat.

      Tänk på att återgivning med Mental Ray, med bildbaserat ljus, är mycket långsamt och processorintensivt. Adobe rekommenderar att du konfigurerar de inställningar för lägsta kvalitet som fortfarande kan ge önskad återgivningskvalitet.


1. Ta bort referensen som du skapade i steg 2.

1. Spara scenen och avsluta Autodesk Maya.
1. Överför scenen till AEM och vänta tills överföringen är klar.

   Se [Överför resurser](managing-assets-touch-ui.md#uploading-assets).

   Om Autodesk® Maya® inte är konfigurerad på AEM server exporterar du en FBX från Maya och överför den till AEM.

1. Öppna Resursegenskaper i AEM. Ange **[!UICONTROL Title]** till en lämplig sträng som ska visas i listrutan **[!UICONTROL Stage Selector]**. Kontrollera att **[!UICONTROL Class]** är **[!UICONTROL 3D Stage]**. Spara och avsluta.
1. Öppna en 3D-resurs, markera den nya scenen och verifiera att den förhandsvisar och återger som förväntat.
