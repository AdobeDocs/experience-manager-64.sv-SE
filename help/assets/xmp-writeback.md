---
title: XMP till återgivning
description: Lär dig hur XMP återskrivningsfunktionen sprider metadataändringar för en resurs till alla eller vissa återgivningar av resursen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 31d652ee04fe75e96f96c9ddc5a6f2c3c64bd630
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 3%

---


# XMP till återgivning {#xmp-writeback-to-renditions}

Den här XMP återskrivningsfunktionen i Adobe Experience Manager (AEM) Resurser replikerar ändringar i resursens återgivningar av metadata.

När du ändrar metadata för en resurs i AEM Assets eller när du överför resursen lagras ändringarna i resursnoden i Crx-De.

XMP återskrivningsfunktion sprider metadataändringarna till alla eller specifika återgivningar av resursen.

Tänk dig ett scenario där du ändrar egenskapen [!UICONTROL Title] för resursen som har namnet `Classic Leather` på `Nylon`.

![metadata](assets/metadata.png)

I det här fallet sparar AEM Assets ändringarna i **[!UICONTROL Title]** egenskapen i `dc:title` -parametern för resursens metadata som lagras i resurshierarkin.

![metadata_stored](assets/metadata_stored.png)

AEM Assets sprider dock inte automatiskt några metadataändringar till återgivningar av en resurs.

Med funktionen XMP kan du sprida metadataändringarna till alla eller vissa återgivningar av resursen. Ändringarna lagras dock inte under metadatanoden i resurshierarkin. I stället bäddar den här funktionen in ändringarna i de binära filerna för återgivningarna.

## Aktivera XMP {#enabling-xmp-writeback}

Om du vill att metadataändringarna ska kunna spridas till återgivningarna av resursen när du överför den ändrar du konfigurationen för **Adobe CQ DAM Rendition Maker** i Configuration Manager.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM Rendition Maker]** konfigurationen.
1. Markera **[!UICONTROL Propagate XMP]** alternativet och spara sedan ändringarna.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## Aktivera XMP för specifik återgivning {#enabling-xmp-writeback-for-specific-renditions}

Om du vill att XMP återskrivningsfunktion ska kunna sprida metadataändringar för att välja återgivningar, anger du dessa återgivningar i arbetsflödet XMP återskrivningsprocessen i arbetsflödet för DAM-metadata WriteBack. Som standard konfigureras det här steget med den ursprungliga återgivningen.

Utför följande steg för XMP återskrivningsfunktion som sprider metadata till återgivningsminiatyrerna 140.100.png och 319.319.png.

1. Gå till Experience Manager **[!UICONTROL Tools > Workflow > Models]**.
1. Öppna arbetsflödesmodellen från [!UICONTROL Models] sidan **[!UICONTROL DAM Metadata Writeback]** .
1. På egenskapssidan för **[!UICONTROL DAM Metadata Writeback]** öppnar du steget **[!UICONTROL XMP Writeback Process]**.
1. I dialogrutan **[!UICONTROL Step Properties]** trycker/klickar du på fliken **[!UICONTROL Process]**.
1. Lägg till i **[!UICONTROL Arguments]** rutan `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png`. Tryck/klicka på **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. To regenerate the pyramid TIFF renditions for Dynamic Media images with the new attributes, add the **[!UICONTROL Dynamic Media Process Image Assets]** step to the DAM Metadata Writeback workflow.
PTIFF-renderingar skapas och lagras endast lokalt i läget Dynamic Media Hybrid. Spara arbetsflödet.

Metadataändringarna sprids till återgivningarna `thumbnail.140.100.png` och `thumbnail.319.319.png` till resursen, inte till de andra.

>[!NOTE]
>
>För problem med XMP av återskrivningen i 64-bitars Linux, se [Så här aktiverar du XMP återskrivning i 64-bitars RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).
>
>Mer information om plattformar som stöds finns i Krav för [XMP](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## Filtrera XMP metadata {#filtering-xmp-metadata}

[!DNL Experience Manager Assets] har stöd för både blockeringslista och tillåtelselista-filtrering av egenskaper/noder för XMP metadata som läses från objektbinärfiler och lagras i JCR när resurser hämtas.

Om du filtrerar med hjälp av blockeringslista kan du importera alla XMP metadataegenskaper utom de egenskaper som anges för undantag. För resurstyper som INDD-filer som har stora mängder XMP metadata (till exempel 1 000 noder med 10 000 egenskaper) är namnen på de noder som ska filtreras inte alltid kända i förväg. Om filtrering med hjälp av blockeringslista tillåter att ett stort antal resurser med flera XMP metadata importeras, kan AEM eller klustret stöta på stabilitetsproblem, till exempel övervakningsköer som har stängts.

Filtrering av XMP metadata via tillåtelselista löser problemet genom att du kan definiera de XMP egenskaper som ska importeras. På så sätt ignoreras alla andra eller okända XMP. För bakåtkompatibilitet kan du lägga till några av dessa egenskaper i filtret som använder blockeringslista.

>[!NOTE]
>
>Filtrering fungerar bara för egenskaper som härletts från XMP källor i objektbinärfiler. För egenskaper som härleds från andra källor än XMP, som EXIF- och IPTC-format, fungerar inte filtreringen. Datumet då resursen skapades sparas till exempel i egenskapen EXIF TIFF `CreateDate` . AEM lagrar det här värdet i metadatafältet med namnet `exif:DateTimeOriginal`. Eftersom källan inte är en XMP källa fungerar inte filtrering på den här egenskapen.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM XmpFilter]** konfigurationen.
1. Om du vill använda filtrering via tillåtelselista markerar du **[!UICONTROL Apply Allowlist to XMP Properties]** och anger de egenskaper som ska importeras i **[!UICONTROL Allowed XML Names for XMP filtering]** rutan.

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Om du vill filtrera bort blockerade XMP efter att ha använt filtrering via tillåtelselista anger du egenskaperna i **[!UICONTROL Blocked XML Names for XMP filtering]** rutan. Spara ändringarna.

   >[!NOTE]
   >
   >The **[!UICONTROL Apply Blocklist to XMP Properties]** option is selected by default. Filtrering med blockeringslista är alltså aktiverat som standard. Om du vill inaktivera sådan filtrering avmarkerar du **[!UICONTROL Apply Blocklist to XMP Properties]** alternativet.
