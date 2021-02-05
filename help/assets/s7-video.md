---
title: Video
description: Läs om den centraliserade hanteringen av videoresurser där du kan överföra videor för Experience Manager Assets för automatisk kodning till Dynamic Media Classic. Du kan även komma åt Dynamic Media Classic-videor direkt från Experience Manager Assets. Dynamic Media Classic-videointegrering gör att optimerad video kan användas på alla skärmar med automatisk enhets- och automatisk bandbreddsdetektering.
contentOwner: rbrough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
translation-type: tm+mt
source-git-commit: 53fab119fc178e5ac88257cab1e930d4472eaa14
workflow-type: tm+mt
source-wordcount: '1551'
ht-degree: 0%

---


# Video {#video}

Med resurser kan du centralisera hanteringen av videoresurser där du kan överföra videor direkt till Assets för automatisk kodning till Dynamic Media Classic. Du kan även komma åt Dynamic Media Classic-videor direkt från Assets för sidredigering.

Integrering med Dynamic Media Classic för video ger optimerad video även på alla skärmar (automatisk enhets- och bandbreddsidentifiering).

Komponenten **[!UICONTROL Scene7 Video]** utför automatiskt enhets- och bandbreddsidentifiering för att spela upp video i rätt format och med rätt kvalitet på datorer, surfplattor och mobiler.

Du kan inkludera adaptiva videouppsättningar i stället för bara enskilda videoresurser. En adaptiv videouppsättning är en behållare för alla videoåtergivningar som krävs för att spela upp video sömlöst på flera skärmar. En adaptiv videouppsättning grupperar versioner av samma video som är kodade med olika bithastigheter och format. Exempel: 400 kbit/s, 800 kbit/s och 1 000 kbit/s. Du använder en adaptiv videouppsättning, tillsammans med S7-videokomponenten, för adaptiv videoströmning över flera skärmtyper. Till exempel mobila enheter för datorer, iOS, Android, BlackBerry och Windows.

Mer information finns i [Dynamic Media Classic-dokumentationen om adaptiva videouppsättningar](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/video-profiles.html#dynamicmedia).

## Om FFMPEG och Dynamic Media Classic {#about-ffmpeg-and-scene}

Standardprocessen för videokodning bygger på den FFMPEG-baserade integrationen med videoprofiler. Därför innehåller det körklara arbetsflödet för DAM-inmatning följande två åtgärder:

* FFMPEG-miniatyrbilder
* FFMPEG-kodning

Om du aktiverar och konfigurerar integreringen med Dynamic Media Classic tas inte dessa två arbetsflödessteg bort automatiskt från det körklara arbetsflödet för DAM-hämtning. Om du redan använder FFMPEG-baserad videokodning i Experience Manager är det troligt att du har FFMPEG installerat i dina redigeringsmiljöer. I det här fallet kodas en ny video som hämtas med DAM två gånger: en gång från FFMPEG-kodaren och en gång från Dynamic Media Classic-integreringen.

Om du har konfigurerat den FFMPEG-baserade videokodningen i AEM och FFMPEG kan du ta bort de två FFMPEG-arbetsflödena från arbetsflödena för DAM-inhämtning.

## Format som stöds {#supported-formats}

Följande format stöds för komponenten Scene7 Video:

* F4V H.264
* MP4 H.264

## Bestäm var videon ska överföras {#deciding-where-to-upload-your-video}

Hur du avgör var du ska överföra dina videoresurser beror på följande:

* Behöver du ett arbetsflöde för videoresursen?
* Behöver du versionskontroll för videoresursen?

Om svaret är ja på någon av eller båda dessa frågor överför du videon direkt till Adobe DAM. Om svaret är nej på båda frågorna överför du videon direkt till Dynamic Media Classic. Arbetsflödet för varje scenario beskrivs i de följande avsnitten.

### Om du överför videon direkt till Adobe DAM {#if-you-are-uploading-your-video-directly-to-adobe-dam}

Om du behöver ett arbetsflöde eller en versionshantering för dina resurser ska du först överföra till Adobe DAM. Här följer det rekommenderade arbetsflödet:

1. Ladda upp videomaterialet till Adobe DAM och koda och publicera automatiskt till Dynamic Media Classic.
1. I Experience Manager får du åtkomst till videomaterial i WCM på fliken **[!UICONTROL Movies]** i Content Finder.
1. Skapa med en **[!UICONTROL Scene7 Video]**- eller **[!UICONTROL Foundation Video]**-komponent.

### Om du överför din video till Scene7 {#if-you-are-uploading-your-video-to-scene}

Om du inte behöver ett arbetsflöde eller en versionshantering för dina resurser överför du dina resurser till Scene7. Här följer det rekommenderade arbetsflödet:

1. I Dynamic Media Classic [konfigurerar du en schemalagd FTP-överföring och -kodning till Scene7 (automatiskt system)](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/upload-publish/uploading-files.html#preparing-your-assets-and-folders-for-uploading).
1. I Experience Manager får du åtkomst till videomaterial i WCM på fliken **[!UICONTROL Scene7]** i Content Finder.
1. Skapa med komponenten **[!UICONTROL Scene7 Video]**.

## Konfigurera integrering med Scene7 Video {#configuring-integration-with-scene-video}

Så här konfigurerar du universella förinställningar:

1. I **[!UICONTROL Cloud Services]** navigerar du till din **[!UICONTROL Scene7]**-konfiguration och klickar på **[!UICONTROL Edit]**.
1. Välj fliken **[!UICONTROL Video]**.

   ![chlimage_1-363](assets/chlimage_1-363.png)

   >[!NOTE]
   >
   >Fliken **[!UICONTROL Video]** visas inte om sidan inte har någon molnkonfiguration.

1. Välj den adaptiva videokodningsprofilen, en färdig videokodningsprofil eller en anpassad videokodningsprofil.

   >[!NOTE]
   >
   >Mer information om vad videoförinställningarna betyder finns i [Dynamic Media Classic-dokumentationen](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/setup/application-setup.html#video-presets-for-encoding-video-files).
   >
   >Adobe rekommenderar att du antingen markerar båda adaptiva videouppsättningar när du konfigurerar de universella förinställningarna eller väljer alternativet **[!UICONTROL Adaptive Video Encoding]**.

1. De valda kodningsprofilerna tillämpas automatiskt på alla videoklipp som överförs till CQ DAM-målmappen som du konfigurerar för den här Scene7-molnkonfigurationen. Du kan konfigurera flera Scene7 molnkonfigurationer med olika målmappar för att tillämpa olika kodningsprofiler efter behov.

## Uppdaterar förinställningar för visningsprogram och kodning {#updating-viewer-and-encoding-presets}

Det är nödvändigt att uppdatera visningsprogrammet och kodningsförinställningarna för video i Experience Manager om förinställningarna uppdaterades i Scene7. I så fall navigerar du till Scene7-konfigurationen i molnkonfigurationen och klickar på **[!UICONTROL Update the viewer and encoding presets]**.

![chlimage_1-364](assets/chlimage_1-364.png)

## Överför din överordnad video till Scene7 från Adobe DAM {#uploading-your-master-video}

1. Navigera till målmappen för CQ DAM där du har konfigurerat molnkonfigurationen med Scene7-kodningsprofiler.
1. Klicka på **[!UICONTROL Upload]** för att överföra överordnad video. Överföringen och kodningen av videon är klar när arbetsflödet för DAM Update Asset har slutförts och **[!UICONTROL Publish to Scene7]** har en bock.

   >[!NOTE]
   >
   >Det tar en stund innan videominiatyrbilderna genereras.

   Genom att dra den överordnad DAM-videon till videokomponenten kommer du åt *alla* Scene7-kodade proxyåtergivningar för leverans.

## Foundation Video Component jämfört med Scene7 Video Component {#foundation-video-component-versus-scene-video-component}

När du använder Experience Manager har du tillgång till både videokomponenten som finns på Sites och videokomponenten i Scene7. Dessa komponenter är inte utbytbara.

Scene7 videokomponent fungerar bara för Scene7-videofilmer. Grundkomponenten fungerar med videofilmer som lagras från Experience Manager (med ffmpeg) och Scene7-videofilmer.

I följande matris förklaras när du ska använda vilken komponent:

![chlimage_1-365](assets/chlimage_1-365.png)

>[!NOTE]
>
>S7-videokomponenten är körklar och använder den universella videoprofilen. Du kan dock hämta den HTML5-baserade videospelaren i Experience Manager. Kopiera enkelt inbäddningskoden för den färdiga HTML5-videospelaren och placera den på Experience Manager-sidan.

## Experience Manager videokomponent {#aem-video-component}

Även om du bör använda videokomponenten för Scene7 för att visa Scene7-videofilmer bör du för fullständighetens skull använda Scene7-videofilmer med Foundation Video Component.

### Experience Manager Video and Scene7 Video comparison {#aem-video-and-scene-video-comparison}

Följande tabell innehåller en högnivåjämförelse mellan videokomponenten i Experience Manager Foundation och Scene7 Video-komponenten som stöds:

|  | Experience Manager Foundation Video | Scene7 Video |
|---|---|---|
| Metod | HTML5 first approach. Flash används endast för icke-HTML5-reservlösningar. | Flash på de flesta stationära datorer. HTML5 används för mobiler och surfplattor. |
| Leverans | Progressiv | Adaptiv strömning |
| Spårning | Ja | Ja |
| Utbyggbarhet | Ja | Ja (med [HTML5 Viewer SDK API-dokumentation](https://s7d1.scene7.com/s7sdk/3.10/docs/jsdoc/index.html)) |
| Mobilvideo | Ja | Ja |

### Konfigurera {#setting-up}

#### Skapar videoprofiler {#creating-video-profiles}

De olika videokodningarna skapas enligt de kodningsförinställningar för Scene7 som du har valt i Scene7 molnkonfiguration. För att komponenten Foundation Video ska kunna använda dem måste en videoprofil skapas för varje vald kodningsförinställning för Scene7. Med den här metoden kan videokomponenten välja DAM-återgivningar utifrån detta.

>[!NOTE]
>
>Nya videoprofiler och ändringar av dem måste aktiveras för publicering.

1. I Experience Manager trycker du på **[!UICONTROL Tools]>[!UICONTROL Configuration Console]**.
1. Navigera från **[!UICONTROL Configuration Console]** till **[!UICONTROL Tools > DAM > Video Profiles]** i navigeringsträdet.
1. Skapa en Scene7-videoprofil. I listrutan **[!UICONTROL New...]** väljer du **[!UICONTROL Create Page]** och sedan Scene7 videoprofilmall. Ge den nya videoprofilsidan ett namn och klicka på **[!UICONTROL Create]**.

   ![chlimage_1-366](assets/chlimage_1-366.png)

1. Redigera den nya videoprofilen. Välj molnkonfigurationen först. Välj sedan samma kodningsförinställning som du valde i molnkonfigurationen.

   ![chlimage_1-367](assets/chlimage_1-367.png)

   | Egenskap | Beskrivning |
   |---|---|
   | Scene7 Cloud-konfiguration | Den molnkonfiguration som ska användas för kodningsförinställningarna. |
   | Scene7 Encoding Preset | Den kodningsförinställning som den här videoprofilen ska kopplas till. |
   | HTML5-videotyp | Med den här egenskapen kan du ange värdet för type-egenskapen i HTML5-videokällelementet. Den här informationen finns inte i S7-kodningsförinställningarna, men krävs för att videorna ska kunna återges korrekt med HTML5-videoelementet. En lista över vanliga format tillhandahålls, men kan skrivas över för andra format. |

   Upprepa det här steget för alla kodningsförinställningar som är markerade i molnkonfigurationen och som du vill använda i videokomponenten.

#### Konfigurerar design {#configuring-design}

Komponenten **[!UICONTROL Foundation Video]** måste känna till vilka videoprofiler som ska användas för att skapa listan över videokällor. Öppna dialogrutan för videokomponentdesign och konfigurera komponentdesignen för användning av de nya videoprofilerna.

>[!NOTE]
>
>Om du använder komponenten **[!UICONTROL Foundation Video]** på en mobilsida upprepar du de här stegen i designen av mobilsidan.

>[!NOTE]
>
>Ändringar som görs i designen kräver att designen aktiveras så att de kan börja gälla vid publiceringen.

1. Öppna **[!UICONTROL Foundation Video]**-komponentens designdialogruta och ändra till fliken **[!UICONTROL Profiles]**. Ta sedan bort färdiga profiler och lägg till de nya videoprofilerna för S7. Ordningen på profillistan i designdialogrutan definierar ordningen på videokällelementet vid återgivning.
1. För webbläsare som inte stöder HTML5 kan du konfigurera ett Flash-reservläge med videokomponenten. Öppna dialogrutan för design av videokomponenter och ändra till fliken **[!UICONTROL Flash]**. Konfigurera inställningarna för Flash Player och tilldela en reservprofil för Flash Player.

#### Checklista {#checklist}

1. Skapa en S7 Cloud-konfiguration. Kontrollera att förinställningarna för videokodning är angivna och att importeraren körs.
1. Skapa en S7-videoprofil för varje videokodningsförinställning som har valts i molnkonfigurationen.
1. Videoprofilerna måste aktiveras.
1. Konfigurera designen för **[!UICONTROL Foundation Video]**-komponenten på sidan.
1. Aktivera designen när du är klar med designändringarna.

