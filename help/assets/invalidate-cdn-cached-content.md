---
title: Upphäva CDN-cachelagrat innehåll
seo-title: Invalidating your CDN cached content
description: Om du validerar ditt cachelagrade CDN-innehåll (Content Delivery Network) kan du snabbt uppdatera resurser som levereras av Dynamic Media, i stället för att vänta på att cachen ska upphöra att gälla.
seo-description: Invalidating your CDN (Content Delivery Network) cached content lets you quickly update assets that are delivered by Dynamic Media, instead of waiting for the cache to expire.
uuid: 0fd88e31-9745-4c98-a245-9f5d0766cad4
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: e6c9b50b-c27c-48bf-b3c0-9994e7bf6d7e
exl-id: 335c7a78-a00f-451b-8e53-225830d429c6
feature: Asset Management,CDN Cache
role: Admin,User,Developer
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '635'
ht-degree: 27%

---

# Upphäva CDN-cachelagrat innehåll {#invalidating-your-cdn-cached-content}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Dynamic Media-resurser cachas av CDN för snabb leverans. När du uppdaterar en resurs kanske du vill att ändringarna ska börja gälla omedelbart. Om du validerar ditt cachelagrade CDN-innehåll (Content Delivery Network) kan du snabbt uppdatera resurser som levereras av Dynamic Media, i stället för att vänta på att cachen ska upphöra att gälla.

Se även [Cacheöversikt i Dynamic Media Classic](https://helpx.adobe.com/experience-manager/scene7/kb/base/caching-questions/scene7-caching-overview.html).

**Så här gör du ditt CDN-cachelagrade innehåll ogiltigt:**

1. Logga in på ditt Dynamic Media Classic-program.

   [Dynamic Media Classic desktop application](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/intro/dynamic-media-classic-desktop-app.html#system-requirements-dmc-app)

   Dina autentiseringsuppgifter och din inloggning tillhandahölls av Adobe vid tidpunkten för etableringen. Om du inte har den här informationen kontaktar du teknisk support.

1. Klicka på **[!UICONTROL Setup > Application Setup > General Settings]**.
1. På sidan Allmänna inställningar för programmet, under grupprubriken Servrar, hittar du **[!UICONTROL CDN Invalidation Template]** textruta.

1. Ange den mall som används för att ogiltigförklara CDN-cachen (Content Delivery Network).

   Anta att du anger en bild-URL (inklusive bildförinställningar eller modifierare) som refererar till `<ID>`i stället för ett specifikt bild-ID, som i följande exempel:

   `https://server.com/is/image/Company/<ID>?$product$`

   Om mallen bara innehåller `<ID>`fylls sedan Dynamic Media i `https://<server>/is/image` där `<server>` är namnet på den publiceringsserver som definieras i Allmänna inställningar och &lt;id> är den eller de tillgångar som har valts för att ogiltigförklaras.

1. I sidans nedre högra hörn klickar du på **[!UICONTROL Close]**.
1. I användargränssnittet för Dynamic Media Classic-datorprogrammet väljer du en eller flera resurser och klickar sedan på **[!UICONTROL File > Invalidate CDN]**. Du ser en lista över en eller flera URL-adresser som genererats från mallen som du skapade och de resurser som du markerade. Den använder den server-URL som anges under &quot;Publicerat servernamn&quot; under Allmänna inställningar för programmet.

   Anta till exempel att du har valt en enda bild med namnet &quot;Invalidering av CDN&quot; i föregående steg `Backpack_B`. När du klickar **[!UICONTROL File > Invalidate CDN]** resulterar i följande genererade URL i användargränssnittet för CDN-validering:

   `https://server.com/is/image/Company/Backpack_B?$product$`

1. Klicka i listrutan URL **[!UICONTROL Continue]** för att rensa cacheminnet för varje specifik URL. Observera att du kan redigera en URL-adress eller lägga till en URL-adress genom att skriva eller klistra in den i URL-listrutan. Du behöver inte ställa in CDN Invalidate Template i förväg.

   När du har klickat **[!UICONTROL Continue]** visas en indikator som ger dig en uppskattning av hur lång tid det tar att rensa cachen.

   Om du har markerat flera resurser och sedan klickar på **[!UICONTROL File > Invalidate CDN]** refererar den sparade **[!UICONTROL Template URL]** till alla dessa resurser. Därför kan du definiera en **[!UICONTROL CDN Invalidate Template]** som refererar till alla URL-bildförinställningar som webbplatsen refererar till (exempelvis produktinformation och sökresultat). När du sedan väljer en eller flera bilder som ska ogiltigförklaras från cachen fylls gränssnittet automatiskt i med URL:erna.

   >[!NOTE]
   >
   >När du markerar resurser och sedan klickar på **[!UICONTROL File > Invalidate CDN]** använder Dynamic Media en mall för att automatiskt skapa URL:er som ska ogiltigförklaras i leveransnätverket (CDN, Content Delivery Network). Om det inte finns något i textrutan **[!UICONTROL CDN Invalidate Template]** visas en tom URL-lista. Cachelagring i leveransnätverket (CDN) är inte resursbaserad utan URL-baserad. Därför är det nödvändigt att känna till de fullständiga URL:erna på webbplatsen. När du har definierat dessa URL:er kan du lägga till dem i textrutan **[!UICONTROL Invalidate CDN Template]** tidigare i stegen. Sedan kan du markera dessa resurser och göra URL:erna ogiltiga i ett enda steg.
   >
   >Ett annat alternativ är att lägga till fullständiga URL:er i **[!UICONTROL Invalidate CDN]** lista. Om du väljer det här sättet behöver du inte markera resurser i Dynamic Media Classic innan du går till **[!UICONTROL File > Invalidate CDN]** alternativ.
