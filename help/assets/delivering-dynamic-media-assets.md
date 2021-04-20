---
title: Leverera Dynamic Media Assets
seo-title: Leverera Dynamic Media Assets
description: Lär dig leverera dynamiska medieresurser
seo-description: Lär dig leverera dynamiska medieresurser
uuid: e87754a9-4c34-4658-9971-cd7ceb26523f
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: ec394bd3-2fa6-4f50-b974-bc10f643ecac
exl-id: e5110a90-ddc9-4244-8466-f91adfca8469
feature: Asset Management
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 9%

---

# Leverera Dynamic Media Assets {#delivering-dynamic-media-assets}

Hur du kan leverera dynamiska medieresurser - både video och bilder - beror på hur webbplatsen implementeras.

Med Dynamic Media har du flera alternativ:

* Om du har AEM som värd för webbplatsen vill du lägga till de dynamiska medieresurserna direkt på sidan.
* Om webbplatsen inte finns AEM kan du välja mellan följande:

   * Bädda in videon eller bilden på webbplatsen.
   * Länka URL:er till webbprogrammet. Använd länkning när du vill leverera en videospelare som ett popup-fönster eller modalt fönster.
   * Om webbplatsen är responsiv kan du [leverera optimerade bilder.](responsive-site.md)

>[!NOTE]
>
>Smart bildbehandling fungerar med befintliga bildförinställningar och använder intelligens under de sista millisekunderna i leveransen för att ytterligare minska bildfilens storlek baserat på webbläsarens eller nätverkets anslutningshastighet. Mer information finns i [Smart bildbehandling](imaging-faq.md).

Mer information finns i följande avsnitt:

* [Lägga till Dynamic Media Assets på webbsidor](adding-dynamic-media-assets-to-pages.md)
* [Bädda in video- eller bildvisningsprogrammet på en webbsida](embed-code.md)
* [Aktivera hotlink-skydd i Dynamic Media](https://helpx.adobe.com/experience-manager/6-4/assets/using/hotlink-protection.html)
* Integrera digital icke-synlig vattenstämpel (Digimarc) med Dynamic Media (kommer snart)
* [Länka URL till ett webbprogram](linking-urls-to-yourwebapplication.md)
* [Leverera optimerade bilder för en responsiv webbplats](responsive-site.md)
* [Leverera innehåll med HTTP2](http2.md)
* [Upphäva CDN-cachelagrat innehåll](invalidate-cdn-cached-content.md)
* [Omforma URL:er med regeluppsättningar](using-rulesets-to-transform-urls.md)

## HTTP/2-leverans av Dynamic Media-resurser {#http-delivery-of-dynamic-media-assets}

AEM har nu stöd för leverans av allt Dynamic Media-innehåll (bilder och video) via HTTP/2. Det betyder att en publicerad URL eller inbäddningskod för bilden eller videon är tillgänglig för integrering med alla program som accepterar en värdbaserad resurs. Den publicerade resursen levereras sedan via HTTP/2-protokollet. Den här leveransmetoden förbättrar kommunikationen mellan webbläsare och servrar, vilket ger bättre respons och laddningstider för alla dina Dynamic Media-resurser.

Mer information finns i [HTTP/2 Delivery of Content Frequently Asked Questions](/help/sites-administering/scene7-http2faq.md).
