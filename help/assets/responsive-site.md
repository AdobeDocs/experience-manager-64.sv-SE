---
title: Leverera optimerade bilder för en responsiv webbplats
description: Så här använder du funktionen för responsiv kod i Dynamic Media för att leverera optimerade bilder
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 5edcc765-c374-4368-a0d9-e02a713a24f2
exl-id: 36bb526c-a6d9-4296-8318-97ac72d6b3ba
feature: Publishing
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '360'
ht-degree: 11%

---

# Leverera optimerade bilder för en responsiv webbplats {#delivering-optimized-images-for-a-responsive-site}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Använd funktionen Responsiv kod när du vill dela koden för responsiv visning med webbutvecklaren. Du kopierar det responsiva (**[!UICONTROL RESS]**) till Urklipp så att du kan dela det med webbutvecklaren.

Den här funktionen är användbar om webbplatsen finns på en WCM-fil från tredje part. Om webbplatsen däremot finns på AEM återger en extern bildserver bilden och skickar den till webbsidan.

Se även [Bädda in Video Viewer på en webbsida.](embed-code.md)

Se även [Länka URL:er till webbprogrammet.](linking-urls-to-yourwebapplication.md)

**Leverera optimerade bilder för en responsiv webbplats**:

1. Navigera till bilden som du vill ange responsiv kod för och tryck på i listrutan **[!UICONTROL Renditions]**.

   ![chlimage_1-408](assets/chlimage_1-408.png)

1. Välj en responsiv bildförinställning. Knapparna **[!UICONTROL URL]** och **[!UICONTROL RESS]** visas.

   ![chlimage_1-409](assets/chlimage_1-409.png)

   >[!NOTE]
   >
   >Den valda resursen *och* den valda bildförinställningen eller visningsförinställningen måste publiceras för att knappen **[!UICONTROL URL]** eller **[!UICONTROL RESS]** ska vara tillgänglig.
   >
   >Dynamic Media - Hybrid-läget kräver att du publicerar bildförinställningar; Dynamic Media - Scene7-läget publicerar automatiskt bildförinställningar.

1. Tryck på **[!UICONTROL RESS]**.

   ![chlimage_1-410](assets/chlimage_1-410.png)

1. I **[!UICONTROL Embed Responsive Image]** markerar och kopierar den responsiva kodtexten och klistrar in den på din webbplats för att komma åt den responsiva resursen.
1. Redigera standardbrytpunkterna i inbäddningskoden så att de matchar dem för den responsiva webbplatsen direkt i koden. Testa dessutom de olika bildupplösningarna som används vid olika sidbrytpunkter.

## Använda HTTP/2 för att leverera dina Dynamic Media-resurser {#using-http-to-delivery-your-dynamic-media-assets}

HTTP/2 är det nya, uppdaterade webbprotokollet som förbättrar kommunikationen mellan webbläsare och servrar. Det ger snabbare överföring av information och minskar mängden processorkraft som behövs. Leverans av Dynamic Media-resurser stöds med HTTP/2 som ger bättre respons och laddningstider.

Se [HTTP2-leverans av innehåll](http2.md) om du vill ha fullständig information om hur du kommer igång med HTTP/2 med ditt Dynamic Media-konto.
