---
title: Arbeta med Adobe Dimension-resurser
seo-title: Arbeta med Adobe Dimension-resurser
description: Arbeta med Adobe Dimension-resurser i AEM 3D.
seo-description: Arbeta med Adobe Dimension-resurser i AEM 3D.
uuid: 476e6758-b3a1-42ba-a18d-bfc407c6a72e
contentOwner: Rick Brough
topic-tags: 3D
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: 4a601c2a-4ea1-4308-8ae8-704155f63c21
translation-type: tm+mt
source-git-commit: 5acb16b1734331767554261bbcf9640947f2e23f

---


# Arbeta med Adobe Dimension-resurser {#working-with-adobe-dimension-assets}

Funktionspaketet AEM 3D har stöd för Adobe Dimension-resurser (filer`.dn` ) i AEM Assets, AEM Sites och AEM Screens.

Ett nytt 3D-visningsprogram som baseras på den öppna glTF-standarden har funktioner för förhandsgranskning och visning av webbplatser och skärmar för Adobe Dimension-resurser.

## Om den molnbaserade konverteringstjänsten {#about-the-cloud-based-conversion-service}

När en Dimension-resurs överförs till AEM vidarebefordras en kopia av filen till en molnbaserad Adobe-tjänst som är värd för Amazon AWS. Den här tjänsten konverterar från Adobes egna Dimension-filformat till det öppna standard-GlTF-formatet. Den konverterade 3D-modellen paketeras som en binär glTF (`.glb`). AEM lagrar den konverterade modellen med den primära Dimension-resursen som en återgivning.

Du kan konfigurera konverteringsformatet på något av två sätt (mer information finns i `.glb` Installera och konfigurera AEM 3D [](install-config-3d.md) ):

* Inkludera Adobe-specifika tillägg för att maximera den visuella kvaliteten när du använder Adobe glTF-visningsprogrammet för att visa Dimension-resurser i AEM Assets, AEM Sites eller AEM Screens. Detta gör att `.glb` återgivningarna inte är kompatibla med de flesta tredjepartsprogram.
* Uteslut Adobe-specifika tillägg för att uppnå kompatibilitet mellan återgivningen och program från tredje part `.glb` . Detta begränsar den visuella kvaliteten vid visning i AEM Assets, AEM Sites eller AEM Screens (t.ex. ingen IBL-belysning) för att simulera kvaliteten i vanliga tredjepartsprogram.

Överföringen av Dimension/glTF-filer till eller från Amazon AWS och deras tillfälliga lagring i AWS är helt skyddad. Dessa filer finns kvar i Amazon AWS under en begränsad tid. vanligtvis inte mer än några minuter under normala operationer.

Om du vill aktivera stöd för Dimension-resurser måste du hämta inloggningsuppgifter från Adobe för att få tillgång till konverteringstjänsten. Se [Installera och konfigurera AEM 3D](install-config-3d.md).

>[!NOTE]
>
>Om du installerar och använder de angivna inloggningsuppgifterna, förstår och godkänner du att dina Adobe Dimension 3D-resurser kommer att överföras till - och bearbetas av - den Adobe-hanterade, molnbaserade konverteringstjänsten på Amazon AWS.

### Visa på AEM Resurser {#viewing-on-aem-assets}

Funktionspaketet AEM 3D innehåller ett nytt visningsprogram som baseras på den öppna glTF-standarden som används för att visa Adobe Dimension-resurser. Det här visningsprogrammet väljs automatiskt när en Dimension-fil eller en zippad glTF öppnas i detaljvyn i AEM Resurser eller med 3D-komponenten i AEM Sites.

Observera att glTF-visningsprogrammets användargränssnitt skiljer sig något från det vanliga 3D-visningsprogrammet som används för alla andra 3D-resurstyper.

#### Se även följande: {#see-also-the-following}

* [Versionsinformation](/help/release-notes/aem3d-release-notes.md) om AEM 3D för begränsningar och begränsningar som gäller för Dn-resurser och glTF-visningsprogrammet.
* [Arbeta med 3D-platskomponenten](using-the-3d-sites-component.md) för komponentegenskaper som är specifika för Adobe Dimension-resurser.
* [Installera och konfigurera AEM 3D](install-config-3d.md) för att konfigurera den molnbaserade konverteringstjänsten.

