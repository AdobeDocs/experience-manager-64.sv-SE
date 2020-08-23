---
title: Ställa in en IBL-scen med Autodesk Maya och Mental Ray
seo-title: Ställa in en IBL-scen med Autodesk Maya och Mental Ray
description: Skapa en IBL-scen med Autodesk Maya och Mental Ray
seo-description: Skapa en IBL-scen med Autodesk Maya och Mental Ray
uuid: 353ff561-0d30-4d62-8cad-68890c883c92
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 752e521f-198f-425a-abfa-051993f9c694
translation-type: tm+mt
source-git-commit: b698a1348df3ec2ab455c236422784d10cbcf7c2
workflow-type: tm+mt
source-wordcount: '501'
ht-degree: 0%

---


# Ställa in en IBL-scen med Autodesk Maya och Mental Ray {#setting-up-an-ibl-stage-with-autodesk-maya-and-mental-ray}

1. I Maya skapar du en ny, tom scen.

1. Skapa en (tillfällig) referens till en representativ modell. Detta underlättar utvärdering av ljus, inställning av kameror och konfiguration av renderaren.
1. Ställ in bildbaserad ljussättning.

   1. I **[!UICONTROL Render Settings]** markerar du **[!UICONTROL Render Render Using: mental ray]** och öppnar fliken Scen.
   1. Öppna dragspelet **[!UICONTROL Render Environment]** och klicka **[!UICONTROL Render Create Image Based Lighting]**.
   1. Klicka på ruteikonen som har en högerpil till vänster om rutan för att markera IBL-noden `mentalRayIblShape1`och avsluta sedan **[!UICONTROL Render Settings]**.
   1. I **[!UICONTROL Attribute Editor]** markerar du omformningsnoden `mentalRayIbl1`och byter sedan namn på omformningsnoden till `AdobeIbl`.
   1. Ange skalan för noden så att systemsfären blir betydligt större än det största 3D-objektet som ska visas med den här scenen (till exempel `10000,10000,10000`).
   1. Markera `AdobeIblShape` noden och konfigurera den enligt följande:

      * **[!UICONTROL Mapping]** - Sfärisk
      * **[!UICONTROL Type]** - Bildfil
      * **[!UICONTROL Emit Light]** - true
   1. Koppla den önskade 32-bitars TIFF-bilden till `AdobeIbl` noden.


1. Ställ in markplanet.

   * Skapa ett lämpligt plan som ska användas som markplan och anpassa storleken så att den passar i IBL-sfären genom koordinatens ursprung.
   * Koppla ett **[!UICONTROL Use Background]** material till jordplanet och ge det ett namn `AdobeUseBackground` och koppla det till objektet för markplanet.

1. (Valfritt) Skapa och konfigurera kameror.

   Låt kamerorna &quot;titta&quot; mot mitten av scenen där resursen ska infogas. Var noga med att ställa in kamerorna på återgivning.

1. Konfigurera rendering med Mental Ray.

   Konfigurera **[!UICONTROL Render Settings]** med följande förslag.

   * **[!UICONTROL Common]** tab

      Avmarkera **[!UICONTROL Alpha channel (mask)]** kryssrutan för alla **[!UICONTROL Renderable Cameras]**.

   * **[!UICONTROL Quality]** tab

      * **Allmän kvalitet** - `0.5` eller mindre
      * **Läge** för indirekt diffus (GI) - `Final Gather`
      * **Filterstorlek** - `2.0`, `2.0`
   * Rendera scenen med de typiska bildstorlekar som du förväntar dig att använda. Om det behövs kan du förfina ljuskällorna, renderingsinställningarna eller båda för att få önskat resultat.

      Tänk på att återgivning med Mental Ray, med bildbaserat ljus, är mycket långsamt och processorintensivt. Adobe rekommenderar att du konfigurerar de inställningar för lägsta kvalitet som fortfarande kan ge önskad återgivningskvalitet.


1. Ta bort referensen som du skapade i steg 2.

1. Spara scenen och avsluta Autodesk Maya.

1. Ladda upp scenen och IBL PTIFF till AEM och vänta tills överföringen är klar.

   Se [Överföra resurser](managing-assets-touch-ui.md#uploading-assets).

1. Lös eventuella filberoenden.

   Se [Lösa filberoenden](resolve-file-dependencies.md).

   AEM 3D kanske inte kan identifiera den IBL-bild som konfigurerats på scenen. I sådana fall måste du lösa de saknade beroendena manuellt. Du kan tilldela samma tidigare överförda IBL PTIFF-bild för var och en av de saknade beroendena. Du kan också tilldela olika bilder för att ytterligare styra IBL-effekterna. När du har löst beroendena måste du trycka på **[!UICONTROL Save]** för att starta ombearbetningen.

1. Öppna Resursegenskaper i AEM. Ange **[!UICONTROL Title]** en lämplig sträng som ska visas i **[!UICONTROL Stage Selector]** listrutan. Kontrollera att **[!UICONTROL Class]** är inställt på **[!UICONTROL 3D Stage]**. Spara och avsluta.

1. Öppna en 3D-resurs, markera den nya scenen och verifiera att den förhandsvisar och återger som förväntat.

