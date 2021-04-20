---
title: Använd funktionen för resursinsikter för att spåra användningen av dina bilder
description: Med funktionen för tillgångsinsikter kan ni spåra användarbetyg och användningsstatistik för bilder som används på tredjepartswebbplatser, marknadsföringskampanjer och kreativa lösningar från Adobe.
contentOwner: AG
feature: Asset Insights,Asset Reports
role: Business Practitioner,Administrator
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 2%

---


# Asset Insights {#asset-insights}

Lär dig hur funktionen för tillgångsinsikter gör att du kan spåra användarbetyg och användningsstatistik för resurser som används på tredjepartswebbplatser, marknadsföringskampanjer och Adobe kreativa lösningar.

Med funktionen för tillgångsinsikter kan ni spåra användarbetyg och användningsstatistik för resurser som används på tredjepartswebbplatser, marknadsföringskampanjer och Adobe kreativa lösningar för att få insikter om deras prestanda och popularitet.

Assets Insights samlar in användaraktivitetsinformation, t.ex. hur många gånger en resurs klassificeras, klickas och hur många gånger den läses in på webbplatsen. Det tilldelar poäng till tillgångar baserat på denna statistik. Du kan använda resultat och prestandastatistik för att välja populära mediefiler som ska inkluderas i kataloger, marknadsföringskampanjer och så vidare. Man kan till och med utforma arkiverings- och licensförnyelseregler för mediefiler baserat på denna statistik.

För att Assets Insights ska kunna samla in användningsstatistik för resurser från en webbplats måste du inkludera inbäddningskoden för resursen i webbplatskoden.

Om du vill att tillgångsinsikter ska visa användningsstatistik för resurser måste du först konfigurera funktionen så att den hämtar rapporteringsdata från [!DNL Adobe Analytics]. Mer information finns i [Konfigurera tillgångsinsikter](touch-ui-configuring-asset-insights.md).

>[!NOTE]
>
>Insikter stöds och tillhandahålls endast för bilder.

## Visa statistik för en resurs {#viewing-statistics-for-an-asset}

Du kan visa poängen för resursinsikter från metadatasidan.

1. I resursanvändargränssnittet markerar du resursen och trycker/klickar sedan på ikonen **[!UICONTROL Properties]** i verktygsfältet.
1. Tryck/klicka på fliken **[!UICONTROL Insights]** på sidan Egenskaper.
1. Granska användningsinformationen för resursen på fliken **[!UICONTROL Insights]**. Avsnittet **[!UICONTROL Score]** beskriver den totala resursanvändningen och prestandan för en tillgång.

   Användningspoäng beskriver hur många gånger resursen används i olika lösningar.

   **[!UICONTROL Impressions]**-poängen är antalet gånger som resursen läses in på webbplatsen. Siffran som visas under **[!UICONTROL Clicks]** är antalet gånger som användaren klickar på resursen.

1. Gå igenom **[!UICONTROL Usage Statistics]**-avsnittet för att ta reda på vilka enheter resursen var en del av och vilka kreativa lösningar som nyligen har använt den. Ju högre användning, desto större chans att resursen är populär bland användarna. Användningsdata visas under följande rubriker:

   * **[!UICONTROL Asset]**: Antalet gånger som tillgången var en del av en samling eller sammansatt tillgång
   * **[!UICONTROL Web & Mobile]**: Antalet gånger som resursen ingick i webbplatser och appar
   * **[!UICONTROL Social]**: Antalet gånger som resursen användes i lösningar som Adobe Social och Adobe Campaign
   * **[!UICONTROL Email]**: Antalet gånger som resursen användes i e-postkampanjer

   ![användningsstatistik](assets/usage_statistics.png)

   >[!NOTE]
   >
   >Eftersom funktionen Resursinsikter vanligtvis hämtar data från lösningar från Adobe Analytics regelbundet, kanske inte avsnittet Lösningar visar de senaste data. Den tidsperiod som data visas för beror på schemat för hämtningsåtgärden som resursinsikter körs för att hämta analysdata.

1. Om du vill visa prestandastatistik för resursen grafiskt över en tidsperiod väljer du period i **[!UICONTROL Performance Statistics]**-avsnittet. Detaljer, inklusive klick och visningar, visas som trendlinjer i ett diagram.

   ![chlimage_1-3](assets/chlimage_1-3.jpeg)

   >[!NOTE]
   >
   >Till skillnad från data i avsnittet Lösningar visar avsnittet Prestandastatistik de senaste data.

1. Om du vill hämta inbäddningskoden för resursen som du inkluderar på webbplatser för att få prestandadata trycker/klickar du på **[!UICONTROL Get Embed Code]** under miniatyrbilden för resursen. Mer information om hur du inkluderar din inbäddade kod i tredjepartswebbsidor finns i [Använda sidspåraren och bädda in kod i webbsidor](touch-ui-using-page-tracker.md).

   ![chlimage_1-303](assets/chlimage_1-303.png)

## Visa sammanställd statistik för resurser {#viewing-aggregate-statistics-for-assets}

Du kan visa bakgrundsmusik för alla resurser i en mapp samtidigt med **[!UICONTROL Insights View]**.

1. I resursgränssnittet navigerar du till den mapp som innehåller de resurser som du vill visa insikter för.
1. Tryck/klicka på layoutikonen i verktygsfältet och välj sedan **[!UICONTROL Insights View]**.
1. På sidan visas användningsresultat för resurserna. Jämför omdömen om de olika tillgångarna och få insikter.

## Schemalägg bakgrundsjobb {#scheduling-background-job}

Resursinsikter hämtar användningsdata för resurser från Adobe Analytics rapportsviter regelbundet. Som standard körs ett bakgrundsjobb var 24:e timme i resursinsikter för att hämta data. Du kan dock ändra både frekvens och tid genom att konfigurera tjänsten **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** från webbkonsolen.

1. Tryck på AEM logotyp och gå till **[!UICONTROL Tools > Operations > Web Console]**.
1. Öppna tjänstkonfigurationen för **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]**.

   ![chlimage_1-304](assets/chlimage_1-304.png)

1. Ange önskad schemaläggningsfrekvens och starttid för jobbet i egenskapsschemaläggaruttrycket. Spara ändringarna.
