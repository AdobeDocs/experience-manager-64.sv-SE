---
title: XMP-tillbakaskrivning till återgivningar
description: Lär dig hur XMP-återskrivningsfunktionen sprider metadataändringar för en resurs till alla eller vissa återgivningar av resursen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: b7180dcc7b50dca1c101a3fd28e031ef8e08f37f
workflow-type: tm+mt
source-wordcount: '731'
ht-degree: 2%

---


# XMP-tillbakaskrivning till återgivningar {#xmp-writeback-to-renditions}

Den här XMP-återskrivningsfunktionen i Adobe Experience Manager (AEM) Resurser replikerar ändringar i resursens återgivningar av metadata.

När du ändrar metadata för en resurs inifrån AEM Assets eller när du överför resursen, lagras ändringarna först i resursnoden i Crx-De.

Funktionen XMP-återställning sprider metadataändringarna till alla eller specifika återgivningar av resursen.

Tänk dig ett scenario där du ändrar egenskapen [!UICONTROL Title] för resursen som har namnet `Classic Leather` på `Nylon`.

![metadata](assets/metadata.png)

I det här fallet sparar AEM Assets ändringarna av **[!UICONTROL Title]** egenskapen i `dc:title` parametern för de metadata för mediefiler som lagras i resurshierarkin.

![metadata_stored](assets/metadata_stored.png)

AEM Assets sprider dock inte automatiskt några metadataändringar till återgivningar av en resurs.

Med funktionen XMP-återställning kan du sprida metadataändringarna till alla eller specifika återgivningar av resursen. Ändringarna lagras dock inte under metadatanoden i resurshierarkin. I stället bäddar den här funktionen in ändringarna i de binära filerna för återgivningarna.

## Aktivera XMP-tillbakaskrivning {#enabling-xmp-writeback}

Om du vill att metadataändringarna ska kunna spridas till återgivningarna av resursen när du överför den ändrar du konfigurationen **Adobe CQ DAM Rendition Maker** i Configuration Manager.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM Rendition Maker]** konfigurationen.
1. Markera **[!UICONTROL Propagate XMP]** alternativet och spara sedan ändringarna.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## Aktivera XMP-tillbakaskrivning för specifika återgivningar {#enabling-xmp-writeback-for-specific-renditions}

Om du vill att XMP-återskrivningsfunktionen ska kunna sprida metadataändringar för att välja återgivningar, anger du dessa återgivningar i XMP-återskrivningssteget i arbetsflödet för DAM-metadata WriteBack. Som standard konfigureras det här steget med den ursprungliga återgivningen.

Utför dessa steg för XMP-återskrivningsfunktionen som sprider metadata till återgivningsminiatyrerna 140.100.png och 319.319.png.

1. Gå till Experience Manager **[!UICONTROL Tools > Workflow > Models]**.
1. Öppna arbetsflödesmodellen från [!UICONTROL Models] sidan **[!UICONTROL DAM Metadata Writeback]** .
1. På egenskapssidan för **[!UICONTROL DAM Metadata Writeback]** öppnar du steget **[!UICONTROL XMP Writeback Process]**.
1. I dialogrutan **[!UICONTROL Step Properties]** trycker/klickar du på fliken **[!UICONTROL Process]**.
1. Lägg till i **[!UICONTROL Arguments]** rutan `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png`. Tryck/klicka på **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. To regenerate the pyramid TIFF renditions for Dynamic Media images with the new attributes, add the **[!UICONTROL Dynamic Media Process Image Assets]** step to the DAM Metadata Writeback workflow.
PTIFF-återgivningar skapas och lagras bara lokalt i ett Dynamic Media-hybridläge. Spara arbetsflödet.

Metadataändringarna sprids till återgivningarna `thumbnail.140.100.png` och `thumbnail.319.319.png` till resursen, inte till de andra.

>[!NOTE]
>
>Information om XMP-återskrivningsproblem i 64-bitars Linux finns i [Så här aktiverar du XMP-återskrivningsproblem i 64-bitars RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).
>
>Mer information om vilka plattformar som stöds finns i [XMP-metadatavillkor](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## Filtrera XMP-metadata {#filtering-xmp-metadata}

[!DNL Experience Manager Assets] har stöd för både blockerad lista och tillåten listfiltrering av egenskaper/noder för XMP-metadata som läses från objektbinärfiler och lagras i JCR när resurser hämtas.

Genom att filtrera med hjälp av en blockerad lista kan du importera alla XMP-metadataegenskaper utom de egenskaper som har angetts för undantag. För resurstyper som INDD-filer som har stora mängder XMP-metadata (till exempel 1 000 noder med 10 000 egenskaper) är namnen på de noder som ska filtreras inte alltid kända i förväg. Om filtrering med hjälp av en blockerad lista tillåter att ett stort antal resurser med flera XMP-metadata importeras, kan AEM-instansen eller klustret stöta på stabilitetsproblem, till exempel övervakningskö med stoppning.

Filtrering av XMP-metadata via tillåten lista löser problemet genom att du kan definiera XMP-egenskaperna som ska importeras. På så sätt ignoreras alla andra eller okända XMP-egenskaper. För bakåtkompatibilitet kan du lägga till några av dessa egenskaper i filtret som använder en blockerad lista.

<!-- TBD: The instructions don't seem to match the UI. I see com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.description
in Config Manager. And the settings are,
com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.xmp.filter.apply_whitelist.name
com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.xmp.filter.whitelist.name
com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.xmp.filter.apply_blacklist.name
com.day.cq.dam.commons.metadata.XmpFilterBlackWhite.xmp.filter.blacklist.name
 
TBD: Make updates to configurations for allow and block list after product updates are done.
-->

>[!NOTE]
>
>Filtrering fungerar bara för egenskaper som härletts från XMP-källor i objektbinärfiler. För egenskaper som härleds från andra källor än XMP, t.ex. EXIF- och IPTC-format, fungerar inte filtreringen. Datumet då resursen skapades sparas till exempel i egenskapen EXIF TIFF `CreateDate` . AEM lagrar det här värdet i metadatafältet med namnet `exif:DateTimeOriginal`. Eftersom källan inte är en XMP-källa fungerar inte filtrering på den här egenskapen.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM XmpFilter]** konfigurationen.
1. Om du vill använda filtrering via en tillåten lista markerar du **[!UICONTROL Apply Allowlist to XMP Properties]** och anger de egenskaper som ska importeras i **[!UICONTROL Allowed XML Names for XMP filtering]** rutan.

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Om du vill filtrera bort blockerade XMP-egenskaper efter att ha använt filtrering via tillåten lista anger du egenskaperna i **[!UICONTROL Blocked XML Names for XMP filtering]** rutan. Spara ändringarna.

   >[!NOTE]
   >
   >The **[!UICONTROL Apply Blocklist to XMP Properties]** option is selected by default. Som standard är filtrering med hjälp av en blockerad lista aktiverat. Om du vill inaktivera sådan filtrering avmarkerar du **[!UICONTROL Apply Blocklist to XMP Properties]** alternativet.
