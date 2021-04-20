---
title: Hantera videoresurser
description: Lär dig hur du överför, förhandsgranskar, kommenterar och publicerar videomaterial.
uuid: 56a8c221-409f-4605-97b1-a054dd2abfab
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: f341fae1-dda3-4917-b6db-ad02fec63702
feature: Asset Management,Video
role: Business Practitioner
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '705'
ht-degree: 6%

---


# Hantera videoresurser {#managing-video-assets}

Lär dig hur du hanterar och redigerar videoresurser i Adobe Experience Manager (AEM) Assets. Om du har licens att använda Dynamic Media läser du [Dynamic Media Video documentation](video.md).

## Överför och förhandsgranska videomaterial {#uploading-and-previewing-video-assets}

AEM Assets genererar förhandsgranskningar för videomaterial med filnamnstillägget MP4. Om resursens format inte är MP4 installerar du FFmpeg-paketet för att generera en förhandsvisning. FFmpeg skapar videoåtergivningar av typen OGG och MP4. Du kan förhandsgranska dessa återgivningar i AEM Assets användargränssnitt.

1. I mappen eller undermapparna Digital Assets navigerar du till den plats där du vill lägga till digitala resurser.
1. Om du vill överföra resursen klickar eller trycker du på **[!UICONTROL Create]** i verktygsfältet och väljer sedan **[!UICONTROL Files]**. Du kan också släppa det direkt i resursområdet. Mer information om överföring finns i [Överföra resurser](managing-assets-touch-ui.md#uploading-assets).
1. Om du vill förhandsgranska en video i kortvyn trycker du på **[!UICONTROL Play]**-knappen på videoresursen.

   ![chlimage_1-201](assets/chlimage_1-201.png)

   Du kan bara pausa eller spela upp video i vyn **[!UICONTROL Card]**. Knappen Spela upp/Pausa är inte tillgänglig i vyn **[!UICONTROL List]**.

1. Tryck på ikonen **[!UICONTROL Edit]** på kortet för att förhandsgranska videon i vyn **[!UICONTROL Details]**.

   Videon spelas upp i webbläsarens inbyggda videospelare. Du kan spela upp, pausa, styra volymen och zooma videon till helskärm.

   ![chlimage_1-202](assets/chlimage_1-202.png)

## Konfiguration för att överföra resurser som är större än 2 GB {#configuration-to-upload-video-assets-that-are-larger-than-gb}

Som standard kan du inte överföra resurser som är större än 2 GB på grund av en filstorleksgräns i AEM Assets. Du kan dock skriva över den här gränsen genom att gå till CRXDE Lite och skapa en nod under katalogen `/apps`. Noden måste ha samma nodnamn, katalogstruktur och jämförbara nodegenskaper i ordningen.

Förutom AEM Assets-konfigurationen kan du ändra följande konfigurationer för att överföra stora resurser:

* Öka tokens förfallotid. Se [!UICONTROL Adobe Granite CSRF Servlet] i webbkonsolen på `https://[aem_server]:[port]/system/console/configMgr`. Mer information finns i [CSRF-skydd](/help/sites-developing/csrf-protection.md).
* Öka `receiveTimeout` i Dispatcher-konfigurationen. Mer information finns i [Experience Manager Dispatcher configuration](https://docs.adobe.com/content/help/en/experience-manager-dispatcher/using/configuring/dispatcher-configuration.html#renders-options).

>[!NOTE]
>
>AEM Classic-användargränssnittet har ingen begränsning av filstorleken med två gigabyte. Slutgiltigt arbetsflöde för stor video stöds inte heller helt.

Utför följande steg i katalogen `/apps` om du vill konfigurera en större filstorleksgräns.

1. I AEM trycker du på **[!UICONTROL Tools > General > CRXDE Lite]**.
1. Gå till `/libs/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload` i katalogfönstret till vänster på sidan **[!UICONTROL CRXDE Lite]**. Om du vill visa katalogfönstret trycker du på ikonen `>>`.
1. Tryck på **[!UICONTROL Overlay Node]** i verktygsfältet. Du kan också välja **[!UICONTROL Overlay Node]** på snabbmenyn.
1. I dialogrutan **[!UICONTROL Overlay Node]** trycker du på **[!UICONTROL OK]**.

   ![chlimage_1-203](assets/chlimage_1-203.png)

1. Uppdatera webbläsaren. Överläggsnoden `/apps/dam/gui/content/assets/jcr:content/actions/secondary/create/items/fileupload` är markerad.
1. På fliken **[!UICONTROL Properties]** anger du lämpligt värde i byte för att öka storleksgränsen till önskad storlek. Ange till exempel `32212254720`-värdet om du vill öka storleksgränsen till 30 GB.

1. Tryck på **[!UICONTROL Save All]** i verktygsfältet.
1. I AEM trycker du på **[!UICONTROL Tools > Operations > Web Console]**.
1. På sidan **[!UICONTROL Adobe Experience Manager Web Console Bundles]**, under kolumnen **[!UICONTROL Name]** i tabellen, letar du reda på och trycker på **[!UICONTROL Adobe Granite Workflow External Process Job Handler]**.
1. På sidan **[!UICONTROL Adobe Granite Workflow External Process Job Handler]** anger du sekunder för både **[!UICONTROL Default Timeout]** och **[!UICONTROL Max Timeout]** fält till `18000` (fem timmar).
1. Tryck på **[!UICONTROL Save]**.
1. I AEM trycker du på **[!UICONTROL Tools > Workflow > Models]**.
1. På sidan **[!UICONTROL Workflow Models]** väljer du **[!UICONTROL Dynamic Media Encode Video]** och trycker sedan på **[!UICONTROL Edit]**.
1. Dubbeltryck på **[!UICONTROL Dynamic Media Video Service Process]**-komponenten på **[!UICONTROL Workflow]**-sidan.
1. Expandera **[!UICONTROL Advanced Settings]** under fliken **[!UICONTROL Common]** i dialogrutan **[!UICONTROL Step Properties]**.
1. I fältet **[!UICONTROL Timeout]** anger du värdet `18000` och trycker sedan på **[!UICONTROL OK]** för att gå tillbaka till arbetsflödessidan **[!UICONTROL Dynamic Media Encode Video]**.
1. Tryck **[!UICONTROL Save]** nära sidans överkant, under sidtiteln **[!UICONTROL Dynamic Media Encode Video]**.

## Publicera videoresurser {#publishing-video-assets}

När videomaterialet har publicerats kan du inkludera det på en webbsida via en URL eller genom att bädda in det på en webbsida. Se [Publicera resurser](publishing-dynamicmedia-assets.md).

## Kommentera videoresurser {#annotating-video-assets}

1. I resurskonsolen: tryck på ikonen **[!UICONTROL Edit]** på resurskortet för att visa sidan med resursinformation.
1. Tryck på ikonen **[!UICONTROL Preview]** för att spela upp videon.
1. Om du vill kommentera videon trycker du på **[!UICONTROL Annotate]**-knappen. En anteckning läggs till vid den angivna tidpunkten (bildrutan) i videon.

   När du gör anteckningar kan du rita på arbetsytan och ta med en kommentar med ritningen. Kommentarerna sparas automatiskt i Adobe Experience Manager Assets.

   ![chlimage_1-204](assets/chlimage_1-204.png)

   Tryck på **[!UICONTROL Close]** om du vill avsluta anteckningsguiden.

1. Om du vill hoppa till en viss punkt i videon anger du tiden i sekunder i textfältet och klickar på **[!UICONTROL Jump]**. Om du till exempel vill hoppa över de första 20 sekunderna av video anger du `20` i textfältet.

   ![chlimage_1-205](assets/chlimage_1-205.png)

1. Klicka på en anteckning för att visa den på tidslinjen. Tryck på **[!UICONTROL Delete]** för att ta bort anteckningen från tidslinjen.

   ![chlimage_1-206](assets/chlimage_1-206.png)
