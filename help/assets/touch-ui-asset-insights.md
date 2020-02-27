---
title: Använd funktionen för resursinsikter för att spåra användningen av dina bilder
description: Med funktionen för tillgångsinsikter kan du spåra användarbetyg och användningsstatistik för bilder som används på tredjepartswebbplatser, marknadsföringskampanjer och Adobes kreativa lösningar.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0e0e2aa693c30c8e1ef1033b936b82d83e5b348e

---


# Resursinsikter {#asset-insights}

Lär dig hur funktionen för tillgångsinsikter gör att du kan spåra användarbetyg och användningsstatistik för resurser som används på tredjepartswebbplatser, marknadsföringskampanjer och Adobes kreativa lösningar.

Med funktionen Asset Insights kan ni spåra användarbetyg och användningsstatistik för resurser som används på tredjepartswebbplatser, marknadsföringskampanjer och Adobes kreativa lösningar för att få insikter om deras prestanda och popularitet.

Assets Insights samlar in användaraktivitetsinformation, t.ex. hur många gånger en resurs klassificeras, klickas och hur många gånger den läses in på webbplatsen. Det tilldelar poäng till tillgångar baserat på denna statistik. Du kan använda resultat och prestandastatistik för att välja populära mediefiler som ska inkluderas i kataloger, marknadsföringskampanjer och så vidare. Man kan till och med utforma arkiverings- och licensförnyelseregler för mediefiler baserat på denna statistik.

För att Assets Insights ska kunna samla in användningsstatistik för resurser från en webbplats måste du inkludera inbäddningskoden för resursen i webbplatskoden.

Om du vill att tillgångsinsikter ska visa användningsstatistik för resurser måste du först konfigurera funktionen att hämta rapportdata från [!DNL Adobe Analytics]. Mer information finns i [Konfigurera tillgångsinsikter](touch-ui-configuring-asset-insights.md).

>[!NOTE]
>
>Insikter stöds och tillhandahålls endast för bilder.

## Visa statistik för en tillgång {#viewing-statistics-for-an-asset}

Du kan visa poängen för resursinsikter från metadatasidan.

1. Välj resursen i användargränssnittet för Resurser och tryck/klicka sedan på ikonen **[!UICONTROL Egenskaper]** i verktygsfältet.
1. Tryck/klicka på fliken **[!UICONTROL Insikter]** på sidan Egenskaper.
1. Granska användningsinformationen för resursen på fliken **[!UICONTROL Insikter]** . I avsnittet **[!UICONTROL Poäng]** beskrivs den totala resursanvändningen och resultatstegen för en tillgång.

   Användningspoäng beskriver hur många gånger resursen används i olika lösningar.

   Poängen **[!UICONTROL Impressions]** är antalet gånger som resursen läses in på webbplatsen. Antalet som visas under **[!UICONTROL Klickningar]** är antalet gånger som användaren klickar på resursen.

1. I avsnittet **[!UICONTROL Användningsstatistik]** ser du vilka enheter resursen ingick i och vilka kreativa lösningar som nyligen använt den. Ju högre användning, desto större chans att resursen är populär bland användarna. Användningsdata visas under följande rubriker:

   * **[!UICONTROL Resurs]**: Antalet gånger som tillgången var en del av en samling eller sammansatt tillgång
   * **[!UICONTROL Webb och mobil]**: Antalet gånger som resursen ingick i webbplatser och appar
   * **[!UICONTROL Socialt]**: Antalet gånger som resursen användes i lösningar som Adobe Social och Adobe Campaign
   * **[!UICONTROL E-post]**: Antalet gånger som resursen användes i e-postkampanjer
   ![användningsstatistik](assets/usage_statistics.png)

   >[!NOTE]
   >
   >Eftersom funktionen för tillgångsinsikter vanligtvis hämtar data från lösningar från Adobe Analytics regelbundet, kanske inte avsnittet Lösningar visar de senaste data. Den tidsperiod som data visas för beror på schemat för hämtningsåtgärden som resursinsikter körs för att hämta analysdata.

1. Om du vill visa prestandastatistik för resursen grafiskt över en tidsperiod väljer du period i avsnittet **[!UICONTROL Prestandastatistik]** . Detaljer, inklusive klickningar och intryckningar, visas som trendlinjer i ett diagram.

   ![chlimage_1-3](assets/chlimage_1-3.jpeg)

   >[!NOTE]
   >
   >Till skillnad från data i avsnittet Lösningar visar avsnittet Prestandastatistik de senaste data.

1. Om du vill hämta inbäddningskoden för resursen som du inkluderar på webbplatser för att få prestandadata trycker/klickar du på **[!UICONTROL Hämta inbäddningskod]** under miniatyrbilden för resursen. Mer information om hur du inkluderar din inbäddningskod på webbsidor från tredje part finns i [Använda sidspåraren och bädda in kod på webbsidor](touch-ui-using-page-tracker.md).

   ![chlimage_1-303](assets/chlimage_1-303.png)

## Visa sammanställd statistik för tillgångar {#viewing-aggregate-statistics-for-assets}

Du kan visa bakgrundsmusik över alla resurser i en mapp samtidigt med hjälp av **[!UICONTROL Insights-vyn]**.

1. I resursgränssnittet navigerar du till den mapp som innehåller de resurser som du vill visa insikter för.
1. Tryck/klicka på layoutikonen i verktygsfältet och välj sedan **[!UICONTROL Insights-vy]**.
1. På sidan visas användningsresultat för resurserna. Jämför omdömen om de olika tillgångarna och få insikter.

## Schemalägg bakgrundsjobb {#scheduling-background-job}

Resursinsikter hämtar användningsdata för resurser från Adobe Analytics-rapportsviter regelbundet. Som standard körs ett bakgrundsjobb var 24:e timme i resursinsikter för att hämta data. Du kan dock ändra både frekvens och tid genom att konfigurera **[!UICONTROL tjänsten Synkroniseringsjobb]** för Adobe CQ DAM-resursprestandarapport från webbkonsolen.

1. Tryck på AEM-logotypen och gå till **[!UICONTROL Verktyg > Åtgärder > Webbkonsol]**.
1. Öppna konfigurationen för tjänsten **[!UICONTROL Adobe CQ DAM Asset Performance Report Sync Job]** .

   ![chlimage_1-304](assets/chlimage_1-304.png)

1. Ange önskad schemaläggningsfrekvens och starttid för jobbet i egenskapsschemaläggaruttrycket. Spara ändringarna.
