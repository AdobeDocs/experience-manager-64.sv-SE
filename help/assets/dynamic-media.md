---
title: Arbeta med Dynamic Media
seo-title: Working with Dynamic Media
description: Lär dig hur du använder Dynamic Media för att leverera mediefiler för webben, mobiler och sociala medier.
seo-description: Learn how to use Dynamic Media to deliver assets for consumption on web, mobile, and social sites.
uuid: 4dc0f436-d20e-4e8b-aeff-5515380fa44d
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: introduction
content-type: reference
discoiquuid: a8063d43-923a-42ac-9a16-0c7fadd8f73f
exl-id: f8a3936e-82b5-46c7-9614-b97162e27d6a
feature: Asset Management,Renditions
role: Admin,User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 7%

---

# Arbeta med Dynamic Media {#working-with-dynamic-media}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

[Dynamic Media](https://www.adobe.com/solutions/web-experience-management/dynamic-media.html) hjälper till att leverera visuellt marknadsförings- och marknadsföringsmaterial on demand, som automatiskt skalas för konsumtion på webben, mobiler och sociala medier. Med en uppsättning överordnad resurser genererar och levererar Dynamic Media flera varianter av multimedieinnehåll i realtid via sitt globala, skalbara, prestandaoptimerade nätverk.

Dynamiska medier ger interaktiva tittarupplevelser som zoomning, 360-graders rotation och video. Dynamic Media innehåller arbetsflödena från Adobe Experience Manager Digital Asset Management (Assets) för att förenkla och effektivisera hanteringen av digitala kampanjer.

<!-- DEAD ARTICLE >[!NOTE]
>
>A Community article is available on [Working with Adobe Experience Manager and Dynamic Media](https://helpx.adobe.com/experience-manager/using/aem_dynamic_media.html). -->

## Vad du kan göra med Dynamic Media {#what-you-can-do-with-dynamic-media}

Med Dynamic Media kan du hantera dina resurser innan du publicerar dem. Hur du arbetar med resurser i allmänhet beskrivs i detalj [Arbeta med digitala resurser](managing-assets-touch-ui.md). Allmänna ämnen är bland annat att ladda upp, ladda ned, redigera och publicera material. visa och redigera egenskaper och söka efter resurser.

Funktioner som bara är dynamiska media inkluderar följande:

* [Karusellbanner](carousel-banners.md)
* [Bilduppsättningar](image-sets.md)
* [Interaktiva bilder](interactive-images.md)
* [Interaktiva videoklipp](interactive-videos.md)
* [Blandade medieuppsättningar](mixed-media-sets.md)
* [Panoramabilder](panoramic-images.md)

* [Snurrande uppsättningar](spin-sets.md)
* [Video](video.md)
* [Leverera Dynamic Media Assets](delivering-dynamic-media-assets.md)
* [Hantera resurser](managing-assets.md)
* [Använda snabbvyer för att skapa anpassade popup-fönster](custom-pop-ups.md)

Se även [Konfigurera Dynamic Media](administering-dynamic-media.md).

>[!NOTE]
>
>För att förstå skillnaderna mellan att använda Dynamic Media och integrera Dynamic Media Classic med AEM, se [Dynamic Media Classic-integrering jämfört med Dynamic Media](/help/sites-administering/scene7.md#aem-scene-integration-versus-dynamic-media).

## Dynamic Media-aktiverat jämfört med Dynamic Media inaktiverat {#dynamic-media-on-versus-dynamic-media-off}

Du kan se om Dynamic Media är aktiverat (aktiverat) enligt följande:

* Dynamiska återgivningar är tillgängliga när du hämtar eller förhandsgranskar resurser.
* Bilduppsättningar, snurruppsättningar, blandade medieuppsättningar är tillgängliga.
* PTIFF-återgivningar skapas.

När du klickar på en bildresurs ser resursen annorlunda ut än Dynamic Media [aktiverad](config-dynamic.md#enabling-dynamic-media). Dynamic Media använder on-demand-visningsprogrammen för HTML 5.

### Dynamiska renderingar {#dynamic-renditions}

Dynamiska återgivningar som bild- och visningsinställningar (under **[!UICONTROL Dynamic]**) är tillgängligt när Dynamic Media är aktiverat.

![chlimage_1-358](assets/chlimage_1-358.png)

### Bilduppsättningar, snurruppsättningar, blandade medieuppsättningar {#image-sets-spins-sets-mixed-media-sets}

Uppsättningar med bilder, snurra och blandade medieuppsättningar är tillgängliga om Dynamic Media är aktiverat.

![chlimage_1-359](assets/chlimage_1-359.png)

### PTIFF-återgivningar {#ptiff-renditions}

Dynamiska medieaktiverade resurser innehåller `pyramid.tiffs`.

![chlimage_1-360](assets/chlimage_1-360.png)

### Ändra resursvyer {#asset-views-change}

När Dynamic Media är aktiverat kan du zooma in och ut genom att klicka på `+` och `-` knappar. Du kan också klicka/trycka för att zooma in i ett visst område. Med Återställ återgår du till den ursprungliga versionen och du kan göra bilden i helskärmsläge genom att klicka på de diagonala pilarna. Dynamic Media-aktiverad ser ut så här:

![chlimage_1-361](assets/chlimage_1-361.png)

Med Dynamic Media inaktiverat kan du zooma in och ut och återställa till den ursprungliga storleken:

![chlimage_1-362](assets/chlimage_1-362.png)
