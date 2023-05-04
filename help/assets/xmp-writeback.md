---
title: XMP till återgivning
description: Lär dig hur XMP återskrivningsfunktionen sprider metadataändringar för en resurs till alla eller vissa återgivningar av resursen.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: 456f8c91-aacf-4db5-a329-2d1650ff0f2f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '748'
ht-degree: 2%

---

# XMP till återgivning {#xmp-writeback-to-renditions}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Den här XMP återskrivningsfunktionen i [!DNL Adobe Experience Manager Assets] återger metadataändringarna i återgivningarna av den ursprungliga resursen. När du ändrar metadata för en resurs i Resurser eller när du överför resursen, lagras ändringarna först i metadatanoden i resurshierarkin.

Med funktionen XMP kan du sprida metadataändringarna till alla eller vissa återgivningar av resursen. Funktionen skriver bara tillbaka de metadataegenskaper som använder `jcr` namespace, d.v.s. en egenskap med namnet `dc:title` skrivs tillbaka men egenskapen heter `mytitle` inte.

Tänk dig ett scenario där du ändrar [!UICONTROL Title] egenskap för tillgången i namnet `Classic Leather` till `Nylon`.

![metadata](assets/metadata.png)

I det här fallet [!DNL Experience Manager] Resurser sparar ändringarna i **[!UICONTROL Title]** -egenskapen i `dc:title` parameter för resursens metadata som lagras i resurshierarkin.

![metadata_stored](assets/metadata_stored.png)

Men [!DNL Experience Manager Assets] sprider inte automatiskt metadataändringar till återgivningar av en resurs. Se [aktivera XMP-tillbakaskrivning](#enabling-xmp-writeback).

## Aktivera XMP {#enabling-xmp-writeback}

Om du vill att metadataändringarna ska kunna spridas till återgivningarna av resursen när du överför den ändrar du **Adobe CQ DAM Rendition Maker** konfiguration i Configuration Manager.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM Rendition Maker]** konfiguration.
1. Välj **[!UICONTROL Propagate XMP]** och spara sedan ändringarna.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## Aktivera XMP för specifik återgivning {#enabling-xmp-writeback-for-specific-renditions}

Om du vill att XMP återskrivningsfunktion ska kunna sprida metadataändringar för att välja återgivningar, anger du dessa återgivningar i arbetsflödet XMP återskrivningsprocessen i arbetsflödet för DAM-metadata WriteBack. Som standard konfigureras det här steget med den ursprungliga återgivningen.

Utför följande steg för XMP återskrivningsfunktion som sprider metadata till återgivningsminiatyrerna 140.100.png och 319.319.png.

1. I Experience Manager går du till **[!UICONTROL Tools > Workflow > Models]**.
1. Från [!UICONTROL Models] sida, öppna **[!UICONTROL DAM Metadata Writeback]** arbetsflödesmodell.
1. På egenskapssidan för **[!UICONTROL DAM Metadata Writeback]** öppnar du steget **[!UICONTROL XMP Writeback Process]**.
1. I dialogrutan **[!UICONTROL Step Properties]** trycker/klickar du på fliken **[!UICONTROL Process]**.
1. I **[!UICONTROL Arguments]** ruta, lägga till `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png`. Tryck/klicka på **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. Om du vill återskapa pyramidens TIFF-renderingar för Dynamic Media-bilder med de nya attributen lägger du till **[!UICONTROL Dynamic Media Process Image Assets]** till arbetsflödet för DAM-metadataåterställning.
PTIFF-återgivningar skapas och lagras bara lokalt i ett Dynamic Media-hybridläge. Spara arbetsflödet.

Metadataändringarna sprids till återgivningarna `thumbnail.140.100.png` och `thumbnail.319.319.png` av tillgången, inte de andra.

>[!NOTE]
>
>Information om XMP återskrivningsproblem i 64-bitars Linux finns i [Aktivera XMP för 64-bitars RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).
>
>Mer information om plattformar som stöds finns i [XMP för metadataåterskrivning](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## Filtrera XMP metadata {#filtering-xmp-metadata}

[!DNL Experience Manager Assets] har stöd för både blockeringslista och tillåtelselista-filtrering av egenskaper/noder för XMP metadata som läses från objektbinärfiler och lagras i JCR när resurser hämtas.

Om du filtrerar med hjälp av blockeringslista kan du importera alla XMP metadataegenskaper utom de egenskaper som anges för undantag. För resurstyper som INDD-filer som har stora mängder XMP metadata (till exempel 1 000 noder med 10 000 egenskaper) är namnen på de noder som ska filtreras inte alltid kända i förväg. Om du filtrerar med blockeringslista kan ett stort antal resurser med många XMP metadata importeras, [!DNL Experience Manager] instans eller kluster kan stöta på stabilitetsproblem, t.ex. övervakningsköer.

Filtrering av XMP metadata via tillåtelselista löser problemet genom att du kan definiera de XMP egenskaper som ska importeras. På så sätt ignoreras alla andra eller okända XMP. För bakåtkompatibilitet kan du lägga till några av dessa egenskaper i filtret som använder blockeringslista.

>[!NOTE]
>
>Filtrering fungerar bara för egenskaper som härletts från XMP källor i objektbinärfiler. För egenskaper som härleds från andra källor än XMP, som EXIF- och IPTC-format, fungerar inte filtreringen. Datumet då en resurs skapas sparas till exempel i egenskapen med namnet `CreateDate` i EXIF TIFF. [!DNL Experience Manager] lagrar det här värdet i metadatafältet med namnet `exif:DateTimeOriginal`. Eftersom källan inte är en XMP källa fungerar inte filtrering på den här egenskapen.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM XmpFilter]** konfiguration.
1. Om du vill använda filtrering via tillåtelselista väljer du **[!UICONTROL Apply Allowlist to XMP Properties]** och ange de egenskaper som ska importeras i **[!UICONTROL Allowed XML Names for XMP filtering]** box.

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Om du vill filtrera bort blockerade XMP efter att ha använt filtrering via tillåtelselista anger du egenskaperna i dialogrutan **[!UICONTROL Blocked XML Names for XMP filtering]** box. Spara ändringarna.

   >[!NOTE]
   >
   >The **[!UICONTROL Apply Blocklist to XMP Properties]** är markerat som standard. Filtrering med blockeringslista är alltså aktiverat som standard. Om du vill inaktivera sådan filtrering avmarkerar du **[!UICONTROL Apply Blocklist to XMP Properties]** alternativ.
