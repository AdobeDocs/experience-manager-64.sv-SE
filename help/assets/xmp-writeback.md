---
title: XMP till återgivning
description: Lär dig hur XMP återskrivningsfunktionen sprider metadataändringar för en resurs till alla eller vissa återgivningar av resursen.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: 456f8c91-aacf-4db5-a329-2d1650ff0f2f
source-git-commit: 1e3cd6ce3138113721183439f7cfb9daed6e0e58
workflow-type: tm+mt
source-wordcount: '712'
ht-degree: 3%

---

# XMP till återgivning {#xmp-writeback-to-renditions}

Den här XMP återskrivningsfunktionen i [!DNL Adobe Experience Manager Assets] replikerar metadataändringarna till återgivningarna av den ursprungliga resursen. När du ändrar metadata för en resurs i Resurser eller när du överför resursen, lagras ändringarna först i metadatanoden i resurshierarkin.

Med funktionen XMP kan du sprida metadataändringarna till alla eller vissa återgivningar av resursen. Funktionen skriver bara tillbaka de metadataegenskaper som använder namnutrymmet `jcr`, d.v.s. egenskapen `dc:title` skrivs tillbaka, men egenskapen `mytitle` skrivs inte tillbaka.

Tänk dig ett scenario där du ändrar egenskapen [!UICONTROL Title] för resursen `Classic Leather` till `Nylon`.

![metadata](assets/metadata.png)

I det här fallet sparar [!DNL Experience Manager]-resurserna ändringarna av egenskapen **[!UICONTROL Title]** i parametern `dc:title` för de metadata för resursen som lagras i resurshierarkin.

![metadata_stored](assets/metadata_stored.png)

[!DNL Experience Manager Assets] sprider dock inte automatiskt några metadataändringar till återgivningarna av en resurs. Se [hur du aktiverar XMP-tillbakaskrivning](#enabling-xmp-writeback).

## Aktivera XMP {#enabling-xmp-writeback}

Om du vill att metadataändringarna ska kunna spridas till återgivningarna av resursen när du överför den ändrar du konfigurationen **Adobe CQ DAM Rendition Maker** i Configuration Manager.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM Rendition Maker]**-konfigurationen.
1. Välj alternativet **[!UICONTROL Propagate XMP]** och spara sedan ändringarna.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## Aktivera XMP för specifik återgivning {#enabling-xmp-writeback-for-specific-renditions}

Om du vill att XMP återskrivningsfunktion ska kunna sprida metadataändringar för att välja återgivningar, anger du dessa återgivningar i arbetsflödet XMP återskrivningsprocessen i arbetsflödet för DAM-metadata WriteBack. Som standard konfigureras det här steget med den ursprungliga återgivningen.

Utför följande steg för XMP återskrivningsfunktion som sprider metadata till återgivningsminiatyrerna 140.100.png och 319.319.png.

1. Gå till **[!UICONTROL Tools > Workflow > Models]** i Experience Manager.
1. Öppna arbetsflödesmodellen **[!UICONTROL DAM Metadata Writeback]** på sidan [!UICONTROL Models].
1. På egenskapssidan för **[!UICONTROL DAM Metadata Writeback]** öppnar du steget **[!UICONTROL XMP Writeback Process]**.
1. I dialogrutan **[!UICONTROL Step Properties]** trycker/klickar du på fliken **[!UICONTROL Process]**.
1. Lägg till `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png` i rutan **[!UICONTROL Arguments]**. Tryck/klicka på **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. Om du vill återskapa pyramidens TIFF-återgivningar för Dynamic Media-bilder med de nya attributen lägger du till steget **[!UICONTROL Dynamic Media Process Image Assets]** i arbetsflödet för DAM-metadataåterskrivning.
PTIFF-återgivningar skapas och lagras bara lokalt i ett Dynamic Media-hybridläge. Spara arbetsflödet.

Metadataändringarna sprids till återgivningarna `thumbnail.140.100.png` och `thumbnail.319.319.png` för resursen, inte till de andra.

>[!NOTE]
>
>Information om XMP återskrivningsproblem i 64-bitars Linux finns i [Så här aktiverar du XMP återskrivning i 64-bitars RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).
>
>Mer information om plattformar som stöds finns i [XMP krav för återskrivning av metadata](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## Filtrera XMP metadata {#filtering-xmp-metadata}

[!DNL Experience Manager Assets] har stöd för både blockeringslista och tillåtelselista-filtrering av egenskaper/noder för XMP metadata som läses från objektbinärfiler och lagras i JCR när resurser hämtas.

Om du filtrerar med hjälp av blockeringslista kan du importera alla XMP metadataegenskaper utom de egenskaper som anges för undantag. För resurstyper som INDD-filer som har stora mängder XMP metadata (till exempel 1 000 noder med 10 000 egenskaper) är namnen på de noder som ska filtreras inte alltid kända i förväg. Om filtrering med hjälp av blockeringslista tillåter att ett stort antal resurser med flera XMP metadata importeras, kan [!DNL Experience Manager]-instansen eller klustret stöta på stabilitetsproblem, till exempel övervakningsköer som har stängts.

Filtrering av XMP metadata via tillåtelselista löser problemet genom att du kan definiera de XMP egenskaper som ska importeras. På så sätt ignoreras alla andra eller okända XMP. För bakåtkompatibilitet kan du lägga till några av dessa egenskaper i filtret som använder blockeringslista.

>[!NOTE]
>
>Filtrering fungerar bara för egenskaper som härletts från XMP källor i objektbinärfiler. För egenskaper som härleds från andra källor än XMP, som EXIF- och IPTC-format, fungerar inte filtreringen. Datumet då resursen skapades sparas till exempel i egenskapen `CreateDate` i EXIF TIFF. [!DNL Experience Manager] lagrar det här värdet i metadatafältet med namnet  `exif:DateTimeOriginal`. Eftersom källan inte är en XMP källa fungerar inte filtrering på den här egenskapen.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM XmpFilter]**-konfigurationen.
1. Om du vill använda filtrering via ett tillåtelselista väljer du **[!UICONTROL Apply Allowlist to XMP Properties]** och anger de egenskaper som ska importeras i rutan **[!UICONTROL Allowed XML Names for XMP filtering]**.

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Om du vill filtrera bort blockerade XMP efter att ha använt filtrering via tillåtelselista anger du egenskaperna i rutan **[!UICONTROL Blocked XML Names for XMP filtering]**. Spara ändringarna.

   >[!NOTE]
   >
   >Alternativet **[!UICONTROL Apply Blocklist to XMP Properties]** är markerat som standard. Filtrering med blockeringslista är alltså aktiverat som standard. Om du vill inaktivera sådan filtrering avmarkerar du alternativet **[!UICONTROL Apply Blocklist to XMP Properties]**.
