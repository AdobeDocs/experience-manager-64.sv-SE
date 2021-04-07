---
title: Använda Dynamic Media bildförinställningar
seo-title: Använda Dynamic Media bildförinställningar
description: Lär dig hur du använder bildförinställningar i Dynamic Media
seo-description: Lär dig hur du använder bildförinställningar i Dynamic Media
uuid: 8bafcbd0-6df0-4d5b-b2f7-116ddb4ec060
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 5c1f60ac-3741-4002-9c5d-c128f118342b
exl-id: 07a4f315-a60e-456b-b02d-035b3f6ad9ad
feature: Bildförinställningar
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 9%

---

# Använda förinställningar för Dynamic Media-bilder {#applying-image-presets}

Med bildförinställningar kan resurser dynamiskt leverera bilder i olika storlekar, i olika format eller med andra bildegenskaper som genereras dynamiskt. Du kan välja en förinställning när du exporterar bilder. Då formateras bilderna också om till de specifikationer som administratören har angett.

Du kan dessutom välja en bildförinställning som är responsiv (anges av knappen **[!UICONTROL RESS]** när du har valt den).

I det här avsnittet beskrivs hur du använder bildförinställningar. [Administratörer kan skapa och konfigurera bildförinställningar](managing-image-presets.md).

>[!NOTE]
>
>Smart bildbehandling fungerar med befintliga bildförinställningar och använder intelligens under de sista millisekunderna i leveransen för att ytterligare minska bildfilens storlek baserat på webbläsarens eller nätverkets anslutningshastighet. Mer information finns i [Smart bildbehandling](imaging-faq.md).

Du kan använda en bildförinställning på en bild när du vill förhandsvisa den.

**Så här använder du Dynamic Media-bildförinställningar**:

1. Öppna resursen och tryck på den nedrullningsbara menyn till vänster och tryck sedan på **[!UICONTROL Renditions]**.

   >[!NOTE]
   >
   >* Statiska återgivningar visas i den övre halvan av rutan. Dynamiska återgivningar visas i den nedre halvan. Om du bara använder dynamiska återgivningar kan du använda URL-adressen för att visa bilden. Knappen **[!UICONTROL URL]** visas bara om du väljer en dynamisk återgivning. Knappen **[!UICONTROL RESS]** visas bara om du väljer en förinställning för responsiv bild.
      >
      >
   * Systemet visar flera renderingar när du väljer **[!UICONTROL Renditions]** i detaljvyn för en resurs. Du kan öka antalet förinställningar som visas. Se [Öka antalet bildförinställningar som visas](managing-image-presets.md#increasing-or-decreasing-the-number-of-image-presets-that-display).


   ![chlimage_1-208](assets/chlimage_1-208.png)

1. Gör något av följande:

   * Välj en dynamisk återgivning om du vill förhandsgranska bildförinställningen.
   * Tryck på **[!UICONTROL URL]**, **[!UICONTROL Embed]** eller **[!UICONTROL RESS]** för att visa popup-fönstret.

   >[!NOTE]
   >
   >Om resursen *och* bildförinställningen ännu inte har publicerats är knappen **[!UICONTROL URL]** (eller knapparna **[!UICONTROL URL]** och **[!UICONTROL RESS]**, i förekommande fall) inte tillgängliga.
   >
   >Observera också att bildförinställningar automatiskt publiceras på en Dynamic Media-server.
