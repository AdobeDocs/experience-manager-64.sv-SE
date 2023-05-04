---
title: Hantera videoresurser
description: Lär dig hur du överför, förhandsgranskar, kommenterar och publicerar videomaterial.
uuid: 56a8c221-409f-4605-97b1-a054dd2abfab
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: f341fae1-dda3-4917-b6db-ad02fec63702
feature: Asset Management,Video
role: User
exl-id: eb652414-5b10-45af-a8b6-f1de649994c5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 6%

---

# Hantera videoresurser {#managing-video-assets}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Lär dig hur du hanterar och redigerar videoresurser i Adobe Experience Manager Assets. Om du har licens att använda Dynamic Media finns mer information i [Dokumentation för Dynamic Media Video](video.md).

## Överföra och förhandsgranska videomaterial {#uploading-and-previewing-video-assets}

[!DNL Experience Manager] Resurser genererar förhandsvisningar för videoresurser med filnamnstillägget MP4. Om resursens format inte är MP4 installerar du FFmpeg-paketet för att generera en förhandsvisning. FFmpeg skapar videoåtergivningar av typen OGG och MP4. Du kan förhandsgranska dessa återgivningar i dialogrutan [!DNL Experience Manager] Resursens användargränssnitt.

1. I mappen eller undermapparna Digital Assets navigerar du till den plats där du vill lägga till digitala resurser.
1. Klicka eller tryck för att överföra resursen **[!UICONTROL Create]** i verktygsfältet och välj **[!UICONTROL Files]**. Du kan också släppa det direkt i resursområdet. Se [Överför resurser](managing-assets-touch-ui.md#uploading-assets) om du vill ha information om överföringen.
1. Om du vill förhandsgranska en video i kortvyn trycker du på **[!UICONTROL Play]** på videomaterialet.

   ![chlimage_1-201](assets/chlimage_1-201.png)

   Du kan pausa eller spela upp video i **[!UICONTROL Card]** endast visa. Knappen Spela upp/Paus är inte tillgänglig i **[!UICONTROL List]** vy.

1. Tryck på **[!UICONTROL Edit]** på kortet för att förhandsgranska videon i **[!UICONTROL Details]** vy.

   Videon spelas upp i webbläsarens inbyggda videospelare. Du kan spela upp, pausa, styra volymen och zooma videon till helskärm.

   ![chlimage_1-202](assets/chlimage_1-202.png)

## Konfiguration för att överföra resurser som är större än 2 GB {#configuration-to-upload-video-assets-that-are-larger-than-gb}

Som standard är [!DNL Experience Manager] Med resurser kan du inte överföra resurser som är större än 2 GB på grund av en begränsad filstorlek. Du kan dock skriva över den här gränsen genom att gå till CRXDE Lite och skapa en nod under `/apps` katalog. Noden måste ha samma nodnamn, katalogstruktur och jämförbara nodegenskaper i ordningen.

Förutom [!DNL Experience Manager] Resurskonfiguration, ändra följande konfigurationer för att överföra stora resurser:

* Öka tokens förfallotid. Se [!UICONTROL Adobe Granite CSRF Servlet] i webbkonsolen på `https://[aem_server]:[port]/system/console/configMgr`. Mer information finns i [CSRF-skydd](/help/sites-developing/csrf-protection.md).
* Öka `receiveTimeout` i Dispatcher-konfiguration. Mer information finns i [Experience Manager Dispatcher-konfiguration](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#renders-options).

>[!NOTE]
>
>The [!DNL Experience Manager] Klassiskt användargränssnitt har ingen begränsning för filstorlek på två gigabyte. Slutgiltigt arbetsflöde för stor video stöds inte heller helt.

Om du vill konfigurera en större filstorleksgräns utför du följande steg i `/apps` katalog.

1. I AEM trycker du på **[!UICONTROL Tools > General > CRXDE Lite]**.
1. I **[!UICONTROL CRXDE Lite]** navigerar du till `/libs/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload`. Om du vill visa katalogfönstret trycker du på `>>` ikon.
1. Tryck på i verktygsfältet **[!UICONTROL Overlay Node]**. Du kan också välja **[!UICONTROL Overlay Node]** på snabbmenyn.
1. I dialogrutan **[!UICONTROL Overlay Node]** trycker du på **[!UICONTROL OK]**.

   ![chlimage_1-203](assets/chlimage_1-203.png)

1. Uppdatera webbläsaren. Överläggsnoden `/apps/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload` är markerat.
1. I **[!UICONTROL Properties]** anger du ett värde i byte för att öka storleksgränsen till önskad storlek. Skriv till exempel `32212254720` om du vill öka storleksgränsen till 30 GB.

1. Tryck på i verktygsfältet **[!UICONTROL Save All]**.
1. I AEM trycker du på **[!UICONTROL Tools > Operations > Web Console]**.
1. På **[!UICONTROL Adobe Experience Manager Web Console Bundles]** sida, under **[!UICONTROL Name]** kolumn i tabellen, söka efter och trycka på **[!UICONTROL Adobe Granite Workflow External Process Job Handler]**.
1. I **[!UICONTROL Adobe Granite Workflow External Process Job Handler]** sida, ange sekunder för båda **[!UICONTROL Default Timeout]** och **[!UICONTROL Max Timeout]** fält till `18000` (fem timmar).
1. Tryck på **[!UICONTROL Save]**.
1. I AEM trycker du på **[!UICONTROL Tools > Workflow > Models]**.
1. På **[!UICONTROL Workflow Models]** sida, markera **[!UICONTROL Dynamic Media Encode Video]** och sedan trycka **[!UICONTROL Edit]**.
1. På **[!UICONTROL Workflow]** sida, dubbeltrycka på **[!UICONTROL Dynamic Media Video Service Process]** -komponenten.
1. I **[!UICONTROL Step Properties]** dialogrutan, under **[!UICONTROL Common]** flik, expandera **[!UICONTROL Advanced Settings]**.
1. I fältet **[!UICONTROL Timeout]** anger du värdet `18000` och trycker sedan på **[!UICONTROL OK]** för att gå tillbaka till arbetsflödessidan **[!UICONTROL Dynamic Media Encode Video]**.
1. Nära sidans överkant, under **[!UICONTROL Dynamic Media Encode Video]** sidrubrik, tryck **[!UICONTROL Save]**.

## Publicera videomaterial {#publishing-video-assets}

När videomaterialet har publicerats kan du inkludera det på en webbsida via en URL eller genom att bädda in det på en webbsida. Se [Publicera resurser](publishing-dynamicmedia-assets.md).

## Kommentera videomaterial {#annotating-video-assets}

1. Tryck på knappen **[!UICONTROL Edit]** på resurskortet för att visa sidan med resursinformation.
1. Tryck på **[!UICONTROL Preview]** -ikon för att spela upp videon.
1. Om du vill kommentera videon trycker du på **[!UICONTROL Annotate]** -knappen. En anteckning läggs till vid den angivna tidpunkten (bildrutan) i videon.

   När du gör anteckningar kan du rita på arbetsytan och ta med en kommentar med ritningen. Kommentarerna sparas automatiskt i Adobe Experience Manager Assets.

   ![chlimage_1-204](assets/chlimage_1-204.png)

   Om du vill avsluta anteckningsguiden trycker du på **[!UICONTROL Close]**.

1. Om du vill hoppa till en viss punkt i videon anger du tiden i sekunder i textfältet och klickar på **[!UICONTROL Jump]**. Om du till exempel vill hoppa över de första 20 sekunderna av video anger du `20` i textfältet.

   ![chlimage_1-205](assets/chlimage_1-205.png)

1. Klicka på en anteckning för att visa den på tidslinjen. Tryck **[!UICONTROL Delete]** för att ta bort anteckningen från tidslinjen.

   ![chlimage_1-206](assets/chlimage_1-206.png)
