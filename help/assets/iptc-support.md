---
title: Stöd för IPTC-metadata
description: Läs om hur Adobe Experience Manager (AEM) Assets stöder IPTC-metadata, kreativa betyg och nyckelord som läggs till i resurser via Adobe Bridge och andra Creative-program.
contentOwner: AG
feature: Metadata
role: Business Practitioner,Administrator,Leader
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 7%

---


# Stöd för IPTC-metadata {#support-for-iptc-metadata}

Läs om hur Adobe Experience Manager (AEM) Assets stöder IPTC-metadata, kreativa betyg och nyckelord som läggs till i resurser via Adobe Bridge och andra Creative-program.

Adobe Experience Manager (AEM) Assets har stöd för IPTC-metadatastandarden som används ofta för att beskriva resurser. På så sätt blir AEM Assets bättre på att acceptera bilderna hos olika parter, bland annat fotografer, reklambyråer, bibliotek, museer osv.

Standardschemat för metadata för mediefiler innehåller nu metadatamodeller för IPTC Core och IPTC Extension för att definiera omfattande metadataegenskaper som gör att användare kan lägga till exakta och tillförlitliga data om personer, platser och produkter som visas i en bild. Det har även stöd för datum, namn och identifierare för att skapa bilden samt ett flexibelt sätt att uttrycka rättighetsinformation.

Egenskapssidan för resurser innehåller nu separata flikar för att visa IPTC-kärnan och IPTC-tilläggsmetadata i redigerbara fält.

1. Välj en bild i användargränssnittet Resurser.
1. Klicka på eller tryck på ikonen **[!UICONTROL Properties]** i verktygsfältet.
1. Klicka/tryck på fliken **[!UICONTROL IPTC]** på sidan Egenskaper för att visa IPTC-metadata för resursen.
1. Redigera IPTC-metadataegenskaperna efter behov.

   ![iptc_tab](assets/iptc_tab.png)

1. Klicka/tryck på fliken **[!UICONTROL IPTC Extension]** för att visa IPTC-tilläggsmetadata för resursen.
1. Redigera metadataegenskaperna för ITPC-tillägget efter behov.
1. Tryck/klicka på **[!UICONTROL Save & Close]** för att spara ändringarna.

## Kreativ klassificeringssupport {#creative-rating-support}

Förutom att visa enskilda användarklassificeringar och aggregerade klassificeringar, visar egenskapssidan nu de klassificeringar som tilldelats resurser via Adobe Bridge och andra Creative-program

Dessa klassificeringar finns i avsnittet **[!UICONTROL Creative Rating]** på fliken **[!UICONTROL Advanced]**.

Den här klassificeringen är en skrivskyddad egenskap och varierar mellan 1 och 5. Du kan söka efter resurser baserat på deras Creative Rating från sökpanelen.

Den här egenskapen är dock för närvarande inte indexerad för att undvika konflikter med anpassade ändringar som görs av användare.

## Stöd för nyckelord {#keyword-support}

På fliken **[!UICONTROL IPTC]** på sidan Egenskaper visas även nyckelord som har lagts till i resurser via Adobe Bridge och andra Creative-program. Du kan också redigera dessa nyckelord och lägga till fler nyckelord från fliken **[!UICONTROL IPTC]**.

![keywords](assets/keywords.png)

