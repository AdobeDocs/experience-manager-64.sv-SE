---
title: XMP-tillbakaskrivning till återgivningar
description: Lär dig hur XMP-återskrivningsfunktionen sprider metadataändringar för en resurs till alla eller vissa återgivningar av resursen.
contentOwner: AG
translation-type: tm+mt
source-git-commit: eb135e5898fe521498eecae7109b39f54d274cce

---


# XMP-tillbakaskrivning till återgivningar {#xmp-writeback-to-renditions}

Den här XMP-återskrivningsfunktionen i Adobe Experience Manager (AEM) Assets replikerar ändringar i resursens återgivningar av metadata.

När du ändrar metadata för en resurs i AEM Resurser eller när du överför resursen, lagras ändringarna i resursnoden i Crx-De.

Funktionen XMP-återställning sprider metadataändringarna till alla eller specifika återgivningar av resursen.

Tänk dig ett scenario där du ändrar egenskapen [!UICONTROL Title] för resursen som har namnet `Classic Leather` på `Nylon`.

![metadata](assets/metadata.png)

I det här fallet sparar AEM Resurser ändringarna av egenskapen **[!UICONTROL Title]** i parametern `dc:title` för resursens metadata som lagras i resurshierarkin.

![metadata_stored](assets/metadata_stored.png)

AEM Resurser sprider dock inte automatiskt några metadataändringar i återgivningarna av en resurs.

Med funktionen XMP-återställning kan du sprida metadataändringarna till alla eller specifika återgivningar av resursen. Ändringarna lagras dock inte under metadatanoden i resurshierarkin. I stället bäddar den här funktionen in ändringarna i de binära filerna för återgivningarna.

## Aktivera XMP-tillbakaskrivning {#enabling-xmp-writeback}

Om du vill att metadataändringarna ska kunna spridas till återgivningarna av resursen när du överför den ändrar du konfigurationen **Adobe CQ DAM Rendition Maker** i Configuration Manager.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM Rendition Maker]** -konfigurationen.
1. Välj alternativet **[!UICONTROL Sprid XMP]** och spara sedan ändringarna.

   ![chlimage_1-346](assets/chlimage_1-346.png)

## Aktivera XMP-tillbakaskrivning för specifika återgivningar {#enabling-xmp-writeback-for-specific-renditions}

Om du vill att XMP-återskrivningsfunktionen ska kunna sprida metadataändringar för att välja återgivningar, anger du dessa återgivningar i XMP-återskrivningssteget i arbetsflödet för DAM-metadata WriteBack. Som standard konfigureras det här steget med den ursprungliga återgivningen.

Utför dessa steg för XMP-återskrivningsfunktionen som sprider metadata till återgivningsminiatyrerna 140.100.png och 319.319.png.

1. Navigera till **[!UICONTROL Verktyg > Arbetsflöde > Modeller]** i Experience Manager.
1. Öppna arbetsflödesmodellen [!UICONTROL DAM-metadataåterställning] på sidan **[!UICONTROL Modeller]** .
1. Öppna steget för **[!UICONTROL XMP-återskrivningsprocess]** på sidan med egenskaper för **[!UICONTROL DAM-metadataåterställning]** .
1. I dialogrutan **[!UICONTROL Stegegenskaper]** trycker/klickar du på fliken **[!UICONTROL Process]** .
1. Lägg till i rutan **[!UICONTROL Argument]** `rendition:cq5dam.thumbnail.140.100.png,rendition:cq5dam.thumbnail.319.319.png`. Tryck/klicka på **[!UICONTROL OK]**.

   ![step_properties](assets/step_properties.png)

1. To regenerate the pyramid TIFF renditions for Dynamic Media images with the new attributes, add the **[!UICONTROL Dynamic Media Process Image Assets]** step to the DAM Metadata Writeback workflow.
PTIFF-renderingar skapas och lagras endast lokalt i läget Dynamic Media Hybrid. Spara arbetsflödet.

Metadataändringarna sprids till återgivningarna `thumbnail.140.100.png` och `thumbnail.319.319.png` till resursen, inte till de andra.

>[!NOTE]
>
>Information om XMP-återskrivningsproblem i 64-bitars Linux finns i [Så här aktiverar du XMP-återskrivningsproblem i 64-bitars RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).
>
>Mer information om vilka plattformar som stöds finns i [XMP-metadatavillkor](/help/sites-deploying/technical-requirements.md#requirements-for-aem-assets-xmp-metadata-write-back).

## Filtrera XMP-metadata {#filtering-xmp-metadata}

AEM Resurser stöder både svartlistsfiltrering och vitlistsfiltrering av egenskaper/noder för XMP-metadata som läses från resurbinärfiler och lagras i JCR när resurser hämtas.

Med svartlistsfiltrering kan du importera alla XMP-metadataegenskaper utom de egenskaper som anges för uteslutning. För resurstyper som INDD-filer som har stora mängder XMP-metadata (till exempel 1 000 noder med 10 000 egenskaper) är namnen på de noder som ska filtreras inte alltid kända i förväg. Om svartlistsfiltrering tillåter ett stort antal resurser med flera XMP-metadata att importeras, kan AEM-instansen/klustret stöta på stabilitetsproblem, till exempel övervakningsköer som stoppats.

Vitlistsfiltrering av XMP-metadata löser problemet genom att du kan definiera de XMP-egenskaper som ska importeras. På så sätt ignoreras andra/okända XMP-egenskaper. Du kan lägga till några av dessa egenskaper i svartlistningsfiltret för bakåtkompatibilitet.

>[!NOTE]
>
>Filtrering fungerar bara för egenskaper som härletts från XMP-källor i objektbinärfiler. För egenskaper som härleds från andra källor än XMP, t.ex. EXIF- och IPTC-format, fungerar inte filtreringen. Datumet då resursen skapades sparas till exempel i egenskapen EXIF TIFF `CreateDate` . AEM lagrar det här värdet i metadatafältet med namnet `exif:DateTimeOriginal`. Eftersom källan inte är en XMP-källa fungerar inte filtrering på den här egenskapen.

1. Öppna Configuration Manager från `https://[aem_server]:[port]/system/console/configMgr`.
1. Öppna **[!UICONTROL Adobe CQ DAM XmpFilter]** -konfigurationen.
1. Om du vill använda vitlistsfiltrering väljer du **[!UICONTROL Använd vitlista på XMP-egenskaper]** och anger de egenskaper som ska importeras i rutan XML-namn i listan **[!UICONTROL över godkända för XMP-filtrering]** .

   ![chlimage_1-347](assets/chlimage_1-347.png)

1. Om du vill filtrera bort svartlistade XMP-egenskaper efter att ha använt vitlistsfiltrering anger du dem i rutan XML-namn med **[!UICONTROL svartlistning för XMP-filtrering]** . Spara ändringarna.

   >[!NOTE]
   >
   >Alternativet **[!UICONTROL Använd svartlista för XMP-egenskaper]** är markerat som standard. Svartlistsfiltrering är alltså aktiverat som standard. Om du vill inaktivera svartlistsfiltrering avmarkerar du **[!UICONTROL Använd svartlista för XMP-egenskaper]**.
