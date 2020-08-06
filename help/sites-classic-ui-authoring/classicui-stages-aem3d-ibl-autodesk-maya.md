---
title: Ställa in en IBL-scen med Autodesk Maya och Mental Ray
seo-title: Ställa in en IBL-scen med Autodesk Maya och Mental Ray
description: Lär dig hur du skapar en IBL-scen med Autodesk Maya och Mental Ray.
seo-description: Lär dig hur du skapar en IBL-scen med Autodesk Maya och Mental Ray.
uuid: 99878112-74c1-4a52-a7c2-c39927ce0e2a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 00f7ed25-276b-42c2-ae4c-11de357a9ec6
translation-type: tm+mt
source-git-commit: e0ce860380a28a9dcaa6f8ce94ad278cdbe49fad
workflow-type: tm+mt
source-wordcount: '502'
ht-degree: 0%

---


# Ställa in en IBL-scen med Autodesk Maya och Mental Ray{#setting-up-an-ibl-stage-with-autodesk-maya-and-mental-ray}

1. I Maya skapar du en ny, tom scen.

1. Skapa en (tillfällig) referens till en representativ modell. Detta underlättar utvärdering av ljus, inställning av kameror och konfiguration av renderaren.
1. Ställ in bildbaserad ljussättning.

   1. Markera **[!UICONTROL Render Using: mental ray]** och öppna **[!UICONTROL Scene]** fliken i Återgivningsinställningar.
   1. Öppna dragspelsfönstret och **[!UICONTROL Environment]** klicka sedan på **[!UICONTROL Create Image Based Lighting]**.
   1. Klicka på ruteikonen som har en högerpil till vänster om rutan för att markera IBL-noden `mentalRayIblShape1`och avsluta sedan [!UICONTROL Render Settings].
   1. I **[!UICONTROL Attribute Editor]** markerar du omformningsnoden `mentalRayIbl1`och byter sedan namn på omformningsnoden till `AdobeIbl`.

   1. Ställ in nodens värde så att systemsfären blir betydligt större än det största 3D-objektet som ska visas med den här scenen (till exempel [!UICONTROL Scale] `10000,10000,10000`).
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

   Konfigurera [!UICONTROL Render Settings] med följande förslag.

   * **[!UICONTROL Common]** tab

      Avmarkera **[!UICONTROL Alpha channel (mask)]** kryssrutan för alla återgivningsbara kameror.

   * **[!UICONTROL Quality]** tab

      * **[!UICONTROL Overall quality]** - `0.5` eller mindre
      * **[!UICONTROL Indirect Diffuse (GI) Mode]** - `Final Gather`
      * **[!UICONTROL Filter Size]** - `2.0`, `2.0`
   * Rendera scenen med de typiska bildstorlekar som du förväntar dig att använda. Om det behövs kan du förfina ljuskällorna, renderingsinställningarna eller båda för att få önskat resultat.

      Tänk på att återgivning med Mental Ray, med bildbaserat ljus, är mycket långsamt och processorintensivt. Adobe rekommenderar att du konfigurerar de inställningar för lägsta kvalitet som fortfarande kan ge önskad återgivningskvalitet.


1. Ta bort referensen som du skapade i steg 2.

1. Spara scenen och avsluta Autodesk Maya.

1. Ladda upp scenen och IBL PTIFF till AEM och vänta tills överföringen är klar.

   Se [Överföra resurser](/help/assets/managing-assets-touch-ui.md#uploading-assets).

1. Lös eventuella filberoenden.

   Se [Lösa filberoenden](/help/sites-classic-ui-authoring/classicui-upload-proc-3d-resolve-dependencies.md).

   AEM 3D kanske inte kan identifiera den IBL-bild som konfigurerats på scenen. I sådana fall måste du lösa de saknade beroendena manuellt. Du kan tilldela samma tidigare överförda IBL PTIFF-bild för var och en av de saknade beroendena. Du kan också tilldela olika bilder för att ytterligare styra IBL-effekterna. När du har löst beroendena ska du trycka på **Spara** för att starta ombearbetningen.

1. Öppna Resursegenskaper i AEM. Ange Titel till en lämplig sträng som ska visas i listrutan Scenväljare. Kontrollera att **[!UICONTROL Class]** är inställt på **[!UICONTROL 3D Stage]**. Spara och avsluta.

1. Öppna en 3D-resurs, markera den nya scenen och verifiera att den förhandsvisar och återger som förväntat.

