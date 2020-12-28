---
title: Integrera med Adobe Search & Promote
seo-title: Integrera med Adobe Search & Promote
description: Lär dig integrera med Adobe Search & Promote.
seo-description: Lär dig integrera med Adobe Search & Promote.
uuid: ddc4510a-9bd1-4238-a8a8-5f4f563edd8d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 87e62346-98d5-40ec-a3ef-904adf667425
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '842'
ht-degree: 0%

---


# Integrera med Adobe Search &amp; Promote{#integrating-with-adobe-search-promote}

Gör så här för att ringa tjänsten Adobe Search &amp; Promote från din webbplats:

1. Ange URL:en för molnet.
1. Konfigurera anslutningen till Search &amp; Promote.
1. Lägg till Search &amp; Promote i [!UICONTROL Sidekick].
1. Använd komponenterna för att skapa innehållet. (Se [Lägga till Search &amp; Promote på en webbsida](/help/sites-authoring/search-and-promote.md).)
1. Lägg till banderoller på sidorna. Banderollbilder är känsliga för Search &amp; Promote data.
1. Generera en webbplatskarta som Search &amp; Promote ska använda.

>[!NOTE]
>
>Om du använder Search &amp; Promote med en anpassad proxykonfiguration måste du konfigurera både HTTP-klientproxykonfigurationer eftersom vissa funktioner i AEM använder 3.x-API:erna och andra 4.x-API:er:
>
>* 3.x har konfigurerats med [http://localhost:4502/system/console/configMgr/com.day.commons.httpclient](http://localhost:4502/system/console/configMgr/com.day.commons.httpclient)
>* 4.x har konfigurerats med [http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator](http://localhost:4502/system/console/configMgr/org.apache.http.proxyconfigurator)

>



## Ändra Search &amp; Promote tjänst-URL {#changing-the-search-promote-service-url}

Standardwebbadressen som är konfigurerad för Search &amp; Promote är `https://searchandpromote.omniture.com/px/`. Om du vill använda en annan tjänst använder du OSGi-konsolen för att ange en annan URL.

**Så här ändrar du Search &amp; Promote tjänst-URL**:

1. Öppna [!UICONTROL OSGi]-konsolen och tryck på fliken **[!UICONTROL Configuration]**. ([http://localhost:4502/system/console/configMgr.](http://localhost:4502/system/console/configMgr))

1. Klicka på **[!UICONTROL Day CQ Search&Promote Configuration]**-objektet.
1. Ange URL-adressen i textfältet **[!UICONTROL Remote Server URI]** och tryck sedan på **[!UICONTROL Save]**.

## Konfigurerar anslutningen till Search &amp; Promote {#configuring-the-connection-to-search-promote}

Konfigurera en eller flera anslutningar till Search &amp; Promote så att dina webbsidor kan interagera med tjänsten. För att kunna ansluta måste du ha medlems-ID och kontonummer för ditt Search &amp; Promote-konto.

**Så här konfigurerar du anslutningen till Search &amp; Promote**:

1. Välj **[!UICONTROL Cloud Services]** från ikonen **[!UICONTROL Tools]** > **[!UICONTROL Deployment]**.

   Du kommer nu till Cloud Services Dashboard. Om du använder en lokal dator ser kontrollpanelens URL ut ungefär så här:

   [http://localhost:4502/libs/cq/core/content/tools/cloudservices.html](http://localhost:4502/libs/cq/core/content/tools/cloudservices.html)

1. På sidan [!UICONTROL Cloud Services] trycker du på länken **[!UICONTROL Adobe Search&Promote]** eller på ikonen **[!UICONTROL Search&Promote]**.

1. Om det här är första gången du konfigurerar Adobe Search &amp; Promote trycker du på **[!UICONTROL Configure Now]** för att öppna panelen [!UICONTROL Create Configuration].

   Om du vill veta mer om Search &amp; Promote klickar du på **[!UICONTROL Learn more]** i stället.

   ![chlimage_1-409](assets/chlimage_1-409.png)

1. Ange ett **[!UICONTROL Title]**-värde som sidförfattare kan känna igen, ange ett unikt **[!UICONTROL Name]** och tryck sedan på **[!UICONTROL Create]**.

   Dessutom visas den nya konfigurationen under **[!UICONTROL Available Configurations]** på listobjektet **[!UICONTROL Cloud Services dashboard]** Adobe Search &amp; Promote.

   ![chlimage_1-410](assets/chlimage_1-410.png)

1. Lägg till följande i fälten i dialogrutan [!UICONTROL Edit Component]:

   * **[!UICONTROL Member ID]**
   * **[!UICONTROL Account number]**

   >[!NOTE]
   >
   >Logga in på följande för att få tillgång till informationen själv:
   >
   >[https://searchandpromote.omniture.com/center/](https://searchandpromote.omniture.com/center/)
   >
   >med dina giltiga Seach&amp;Promote-inloggningsuppgifter (e-post/lösenord).
   >
   >Lägg märke till webbadressen i webbläsarens adressfält. Det ska se ut ungefär så här:
   >
   >[](https://searchandpromote.omniture.com/px/home/?sp_id=XXXXXXXX-spYYYYYYYY)
   >
   >[https://searchandpromote.omniture.com/px/home/?sp_id=XXXXXXXX-spYYYYYYYY](https://searchandpromote.omniture.com/px/home/?sp_id=XXXXXXXX-spYYYYYYYY)
   >
   >Där **XXXXXX** motsvarar ditt **[!UICONTROL Member id]** och **[!UICONTROL spYYYYYYYY]** motsvarar ditt kontonummer.

1. Tryck på **[!UICONTROL Connect To Search&Promote]**.

   När meddelandet om att anslutningen lyckades visas trycker du på **[!UICONTROL OK]**.

   (Efter anslutningen ändras knapptexten till **[!UICONTROL Re-Connect To Search&Promote]**.)

1. Tryck på **[!UICONTROL OK]**. Sidan Inställningar för Search &amp; Promote visas för den konfiguration som du just har skapat.

## Konfigurera datacentret {#configuring-the-data-center}

Om ditt Search &amp; Promote-konto finns i Asien eller Europa måste du ändra standarddatacentret så att det pekar till rätt datacenter (standarddatacentret är för nordamerikanska konton).

**Så här konfigurerar du datacentret**:

1. Gå till webbkonsolen på `http://localhost:4502/system/console/configMgr/com.day.cq.searchpromote.impl.SearchPromoteServiceImpl`

   ![chlimage_1-411](assets/chlimage_1-411.png)

1. Beroende på var servern finns ändrar du URI:n till något av följande:

   * Nordamerika: [https://center.atomz.com/px/](https://center.atomz.com/px/)
   * EMEA: [https://center.lon5.atomz.com/px/](https://center.lon5.atomz.com/px/)
   * APAC: [https://center.sin2.atomz.com/px/](https://center.sin2.atomz.com/px/)

1. Tryck på **[!UICONTROL Save]**.

## Lägga till Search &amp; Promote-komponenter i Sidekick {#adding-search-promote-components-to-sidekick}

I [!UICONTROL Design]-läget redigerar du en **[!UICONTROL par]**-komponent för att tillåta Search &amp; Promote i [!UICONTROL Sidekick]. (Mer information finns i [dokumentationen för komponenter](/help/sites-developing/components.md).)

Mer information om hur du använder komponenterna finns i [Lägga till Search &amp; Promote på en webbsida](/help/sites-authoring/search-and-promote.md).

## Ange vilken Search &amp; Promote som dina sidor använder {#specifying-the-search-promote-service-that-your-pages-use}

Konfigurera webbsidor så att de använder en viss Search &amp; Promote. Search &amp; Promote använder automatiskt tjänsten på sin värdsida.

När du konfigurerar sidegenskaperna för en Search &amp; Promote ärver alla underordnade sidor inställningarna. Om det behövs kan du konfigurera underordnade sidor så att de åsidosätter de ärvda inställningarna.

>[!NOTE]
>
>Tjänstanslutningen måste redan vara konfigurerad. Se [Konfigurera anslutningen till Search &amp; Promote](#configuring-the-connection-to-search-promote).

1. Öppna dialogrutan **[!UICONTROL Page Properties]**. På sidan **[!UICONTROL Websites]** högerklickar du på sidan och klickar på **[!UICONTROL Properties]**.

1. Klicka på fliken **[!UICONTROL Cloud Services]**.

1. Om du vill inaktivera arvet av molntjänstkonfigurationer från en överordnad sida klickar du på hänglåsikonen bredvid arvsökvägen.

   ![sandpinheritpadlock](assets/sandpinheritpadlock.png)

1. Klicka på **[!UICONTROL Add Service]**, välj **[!UICONTROL Adobe Search&Promote]** och klicka sedan på **[!UICONTROL OK]**.

1. Markera anslutningskonfigurationen för ditt Search &amp; Promote-konto och klicka sedan på **[!UICONTROL OK]**.

## Produktfeed {#product-feed}

Med integreringen av Search &amp; Promote kan du göra följande:

* Använd API:t [!UICONTROL eCommerce], oberoende av den underliggande databasstrukturen och e-handelsplattformen.
* Utnyttja [!UICONTROL Index Connector]-funktionen i Search &amp; Promote för att få en produktfeed i XML-format.
* Utnyttja funktionen [!UICONTROL Remote Control] i Search &amp; Promote för att utföra on-demand-begäranden eller schemalagda förfrågningar från produktflödet.
* Flödesgenerering för olika Search &amp; Promote, konfigurerade som molntjänster.

Mer information finns i [Produktfeed](/help/sites-administering/product-feed.md).
