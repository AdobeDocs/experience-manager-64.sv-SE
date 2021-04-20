---
title: Arbeta med Adobe Dimension-resurser
description: Arbeta med Adobe Dimension-resurser i AEM 3D.
contentOwner: Rick Brough
topic-tags: 3D
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
exl-id: be8f6361-607d-4529-aef0-e8978dfd04b4
feature: 3D Assets
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '498'
ht-degree: 0%

---

# Arbeta med Adobe Dimension-resurser {#working-with-adobe-dimension-assets}

>[!IMPORTANT]
>
>Det AEM 3D-funktionspaketet i AEM 6.4 stöds inte längre. Adobe rekommenderar att du använder funktionen 3D-resurser i [AEM som en Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html#dynamicmedia) eller [AEM 6.5.3 eller senare.](https://experienceleague.adobe.com/docs/experience-manager-65/assets/dynamic/assets-3d.html#dynamic) när du arbetar med Adobe Dimension-resurser.

Det AEM 3D-funktionspaketet har stöd för Adobe Dimension-resurser (`.dn`-filer) i AEM Assets, AEM Sites och AEM Screens.

Ett nytt 3D-visningsprogram som baseras på den öppna glTF-standarden har funktioner för förhandsgranskning och visning av webbplatser och skärmar för Adobe Dimension-resurser.

## Om den molnbaserade konverteringstjänsten {#about-the-cloud-based-conversion-service}

När en Dimension överförs till AEM vidarebefordras en kopia av filen till en molnbaserad tjänst som är Adobe-hanterad och värd i Amazon AWS. Den här tjänsten konverterar från det Adobe-ägda filformatet för Dimension till det öppna standardformatet glTF. Den konverterade 3D-modellen paketeras som en binär glTF (`.glb`). AEM lagrar den konverterade modellen med den primära Dimensionen som en återgivning.

Du kan konfigurera konverteringsformatet `.glb` på något av två sätt (se [Installera och konfigurera AEM 3D](install-config-3d.md) för instruktioner):

* Inkludera Adobe-specifika tillägg för att maximera den visuella kvaliteten när du använder visningsprogrammet Adobe glTF för att visa Dimension i AEM Assets, AEM Sites eller AEM Screens. Detta gör att `.glb`-återgivningarna inte är kompatibla med de flesta tredjepartsprogram.
* Exkludera Adobe-specifika tillägg för att uppnå kompatibilitet mellan `.glb`-renderingen och tredjepartsprogram. Detta begränsar den visuella kvaliteten vid visning i AEM Assets, AEM Sites eller AEM Screens (t.ex. ingen IBL-belysning) för att simulera kvaliteten i vanliga tredjepartsprogram.

Överföringen av Dimension-/glTF-filer till eller från Amazon AWS och deras tillfälliga lagring i AWS är helt skyddad. Dessa filer finns kvar i Amazon AWS så länge som möjligt. vanligtvis inte mer än några minuter under normala operationer.

Om du vill aktivera stöd för Dimensioner måste du hämta autentiseringsuppgifter från Adobe för att få åtkomst till konverteringstjänsten. Se [Installera och konfigurera AEM 3D](install-config-3d.md).

>[!NOTE]
>
>Om du installerar och använder de angivna inloggningsuppgifterna, är du införstådd med och samtycker till att dina Adobe Dimension 3D-resurser kommer att överföras till, och bearbetas av, den molnbaserade konverteringstjänsten i Amazon AWS som är värd för Adobe.

### Visa på AEM Assets {#viewing-on-aem-assets}

Det AEM 3D-funktionspaketet innehåller ett nytt visningsprogram baserat på den öppna glTF-standarden som används för att visa Adobe Dimension-resurser. Det här visningsprogrammet markeras automatiskt när du öppnar en Dimension eller en zippad glTF-fil i detaljvyn i AEM Assets eller med 3D-komponenten i AEM Sites.

Observera att glTF-visningsprogrammets användargränssnitt skiljer sig något från det vanliga 3D-visningsprogrammet som används för alla andra 3D-resurstyper.

#### Se även följande: {#see-also-the-following}

* [AEM 3D-](/help/release-notes/aem3d-release-notes.md) versionsinformation om begränsningar och begränsningar som gäller för Dn-resurser och glTF-visningsprogrammet.
* [Arbeta med 3D-platskomponenten ](using-the-3d-sites-component.md) för komponentegenskaper som är specifika för Adobe Dimension-resurser.
* [Installera och konfigurera AEM 3](install-config-3d.md) Dför att konfigurera den molnbaserade konverteringstjänsten.
