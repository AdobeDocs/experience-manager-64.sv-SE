---
title: Använd funktionen för resursinsikter för att spåra användningen av dina bilder
description: Med funktionen för tillgångsinsikter kan ni spåra användarbetyg och användningsstatistik för bilder som används på tredjepartswebbplatser, marknadsföringskampanjer och kreativa lösningar från Adobe.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0e0e2aa693c30c8e1ef1033b936b82d83e5b348e
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 2%

---


# Asset Insights {#asset-insights}

Lär dig hur funktionen för tillgångsinsikter gör att du kan spåra användarbetyg och användningsstatistik för resurser som används på tredjepartswebbplatser, marknadsföringskampanjer och Adobe kreativa lösningar.

Med funktionen för tillgångsinsikter kan ni spåra användarbetyg och användningsstatistik för resurser som används på tredjepartswebbplatser, marknadsföringskampanjer och Adobe kreativa lösningar för att få insikter om deras prestanda och popularitet.

Assets Insights samlar in användaraktivitetsinformation, t.ex. hur många gånger en resurs klassificeras, klickas och hur många gånger den läses in på webbplatsen. Det tilldelar poäng till tillgångar baserat på denna statistik. Du kan använda resultat och prestandastatistik för att välja populära mediefiler som ska inkluderas i kataloger, marknadsföringskampanjer och så vidare. Man kan till och med utforma arkiverings- och licensförnyelseregler för mediefiler baserat på denna statistik.

För att Assets Insights ska kunna samla in användningsstatistik för resurser från en webbplats måste du inkludera inbäddningskoden för resursen i webbplatskoden.

Om du vill att tillgångsinsikter ska visa användningsstatistik för resurser måste du först konfigurera funktionen att hämta rapportdata från [!DNL Adobe Analytics]. Mer information finns i [Konfigurera tillgångsinsikter](touch-ui-configuring-asset-insights.md).

>[!NOTE]
>
>Insikter stöds och tillhandahålls endast för bilder.

## Visa statistik för en tillgång {#viewing-statistics-for-an-asset}

Du kan visa poängen för resursinsikter från metadatasidan.

1. I resursanvändargränssnittet markerar du resursen och trycker/klickar sedan på **[!UICONTROL Properties]** ikonen i verktygsfältet.
1. Tryck/klicka på **[!UICONTROL Insights]** fliken på sidan Egenskaper.
1. Granska användningsinformationen för resursen på **[!UICONTROL Insights]** fliken. I avsnittet **[!UICONTROL Score]** beskrivs den totala resursanvändningen och prestandan för en tillgång.

   Användningspoäng beskriver hur många gånger resursen används i olika lösningar.

   Poängen **[!UICONTROL Impressions]** är antalet gånger som resursen läses in på webbplatsen. Siffran som visas under **[!UICONTROL Clicks]** är antalet gånger som användaren klickar på resursen.

1. Läs igenom **[!UICONTROL Usage Statistics]** avsnittet för att ta reda på vilka enheter resursen ingick i och vilka kreativa lösningar som nyligen använt den. Ju högre användning, desto större chans att resursen är populär bland användarna. Användningsdata visas under följande rubriker:

   * **[!UICONTROL Asset]**: Antalet gånger som tillgången var en del av en samling eller sammansatt tillgång
   * **[!UICONTROL Web & Mobile]**: Antalet gånger som resursen ingick i webbplatser och appar
   * **[!UICONTROL Social]**: Antalet gånger som resursen användes i lösningar som Adobe Social och Adobe Campaign
   * **[!UICONTROL Email]**: Antalet gånger som resursen användes i e-postkampanjer

   ![användningsstatistik](assets/usage_statistics.png)

   >[!NOTE]
   >
   >Eftersom funktionen Resursinsikter vanligtvis hämtar data från lösningar från Adobe Analytics regelbundet, kanske inte avsnittet Lösningar visar de senaste data. Den tidsperiod som data visas för beror på schemat för hämtningsåtgärden som resursinsikter körs för att hämta analysdata.

1. To view performance statistics for the asset graphically over a period of time, select period in the **[!UICONTROL Performance Statistics]** section. Detaljer, inklusive klick och visningar, visas som trendlinjer i ett diagram.

   ![chlimage_1-3](assets/chlimage_1-3.jpeg)

   >[!NOTE]
   >
   >Till skillnad från data i avsnittet Lösningar visar avsnittet Prestandastatistik de senaste data.

1. Om du vill hämta inbäddningskoden för resursen som du inkluderar på webbplatser för att få prestandadata trycker/klickar du **[!UICONTROL Get Embed Code]** nedanför miniatyrbilden för resursen. Mer information om hur du inkluderar din inbäddningskod på webbsidor från tredje part finns i [Använda sidspåraren och bädda in kod på webbsidor](touch-ui-using-page-tracker.md).

   ![chlimage_1-303](assets/chlimage_1-303.png)

## Visa sammanställd statistik för tillgångar {#viewing-aggregate-statistics-for-assets}

You can view scores of all assets within a folder simultaneously using **[!UICONTROL Insights View]**.

1. I resursgränssnittet navigerar du till den mapp som innehåller de resurser som du vill visa insikter för.
1. Tryck/klicka på layoutikonen i verktygsfältet och välj sedan **[!UICONTROL Insights View]**.
1. På sidan visas användningsresultat för resurserna. Jämför omdömen om de olika tillgångarna och få insikter.

## Schemalägg bakgrundsjobb {#scheduling-background-job}

Resursinsikter hämtar användningsdata för resurser från Adobe Analytics rapportsviter regelbundet. Som standard körs ett bakgrundsjobb var 24:e timme i resursinsikter för att hämta data. Du kan dock ändra både frekvens och tid genom att konfigurera **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** tjänsten från webbkonsolen.

1. Tap the AEM logo, and go to **[!UICONTROL Tools > Operations > Web Console]**.
1. Öppna **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** tjänstkonfigurationen.

   ![chlimage_1-304](assets/chlimage_1-304.png)

1. Ange önskad schemaläggningsfrekvens och starttid för jobbet i egenskapsschemaläggaruttrycket. Spara ändringarna.
