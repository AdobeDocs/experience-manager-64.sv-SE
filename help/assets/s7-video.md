---
title: Video
description: Läs om den centraliserade hanteringen av videoresurser där du kan överföra videor för Experience Manager Assets för automatisk kodning till Dynamic Media Classic. Du kan även komma åt Dynamic Media Classic-videor direkt från Experience Manager Assets. Tack vare Dynamic Media Classic videointegration kan optimerad video även användas på alla skärmar med automatisk enhets- och automatisk bandbreddsdetektering.
contentOwner: rbrough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: managing-assets
content-type: reference
exl-id: 081e7db0-95cc-4260-8f08-318cd7d9d5b4
feature: Video
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1587'
ht-degree: 0%

---

# Video {#video}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med resurser får du centraliserad hantering av videoresurser där du kan överföra videor direkt till Assets för automatisk kodning till Dynamic Media Classic. Du kan även komma åt Dynamic Media Classic-videor direkt från Assets för sidredigering.

Tack vare Dynamic Media Classic videointegration kan optimerad video även användas på alla skärmar (automatisk enhets- och bandbreddsidentifiering).

The **[!UICONTROL Scene7 Video]** -komponenten utför automatiskt enhets- och bandbreddsidentifiering för att spela upp video i rätt format och med rätt kvalitet på datorer, surfplattor och mobiler.

Du kan inkludera adaptiva videouppsättningar i stället för bara enskilda videoresurser. En adaptiv videouppsättning är en behållare för alla videoåtergivningar som krävs för att spela upp video sömlöst på flera skärmar. En adaptiv videouppsättning grupperar versioner av samma video som är kodade med olika bithastigheter och format. Exempel: 400 kbit/s, 800 kbit/s och 1 000 kbit/s. Du använder en adaptiv videouppsättning, tillsammans med S7-videokomponenten, för adaptiv videoströmning över flera skärmtyper. Till exempel mobila enheter som iOS, Android, BlackBerry och Windows.

Se [Dynamic Media Classic dokumentation om adaptiva videouppsättningar för mer information](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/video-profiles.html#dynamicmedia).

## Om FFMPEG och Dynamic Media Classic {#about-ffmpeg-and-scene}

Standardprocessen för videokodning bygger på den FFMPEG-baserade integrationen med videoprofiler. Därför innehåller det körklara arbetsflödet för DAM-inmatning följande två åtgärder:

* FFMPEG-miniatyrbilder
* FFMPEG-kodning

Om du aktiverar och konfigurerar Dynamic Media Classic-integreringen tas inte dessa två arbetsflödessteg bort automatiskt från det körklara arbetsflödet för DAM-import. Om du redan använder FFMPEG-baserad videokodning i Experience Manager är det troligt att du har FFMPEG installerat i dina redigeringsmiljöer. I det här fallet kodas en ny video som hämtas med DAM två gånger: en gång från FFMPEG-kodaren och en gång från Dynamic Media Classic-integreringen.

Om du har konfigurerat den FFMPEG-baserade videokodningen i AEM och FFMPEG kan du ta bort de två FFMPEG-arbetsflödena från arbetsflödena för DAM-inhämtning.

## Format som stöds {#supported-formats}

Följande format stöds för komponenten Scene7 Video:

* F4V H.264
* MP4 H.264

## Bestäm var videon ska överföras {#deciding-where-to-upload-your-video}

Hur du avgör var du ska överföra dina videoresurser beror på följande:

* Behöver du ett arbetsflöde för videoresursen?
* Behöver du versionskontroll för videoresursen?

Om svaret är ja på någon av eller båda dessa frågor överför du videon direkt till Adobe DAM. Om svaret är&quot;nej&quot; på båda frågorna överför du videon direkt till Dynamic Media Classic. Arbetsflödet för varje scenario beskrivs i de följande avsnitten.

### Om du överför videon direkt till Adobe DAM {#if-you-are-uploading-your-video-directly-to-adobe-dam}

Om du behöver ett arbetsflöde eller en versionshantering för dina resurser ska du först överföra till Adobe DAM. Här följer det rekommenderade arbetsflödet:

1. Ladda upp videomaterialet till Adobe DAM och koda och publicera automatiskt till Dynamic Media Classic.
1. I Experience Manager får du tillgång till videomaterial i WCM i **[!UICONTROL Movies]** i Content Finder.
1. Författare med **[!UICONTROL Scene7 Video]** eller **[!UICONTROL Foundation Video]** -komponenten.

### Om du överför din video till Scene7 {#if-you-are-uploading-your-video-to-scene}

Om du inte behöver ett arbetsflöde eller en versionshantering för dina resurser överför du dina resurser till Scene7. Här följer det rekommenderade arbetsflödet:

1. I Dynamic Media Classic [konfigurera en schemalagd FTP-överföring och -kodning till Scene7 (automatisk systeminstallation)](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/upload-publish/uploading-files.html#preparing-your-assets-and-folders-for-uploading).
1. I Experience Manager får du tillgång till videomaterial i WCM i **[!UICONTROL Scene7]** i Content Finder.
1. Författare med **[!UICONTROL Scene7 Video]** -komponenten.

## Konfigurera integrering med Scene7 Video {#configuring-integration-with-scene-video}

Så här konfigurerar du universella förinställningar:

1. I **[!UICONTROL Cloud Services]** navigera till **[!UICONTROL Scene7]** konfiguration och klicka på **[!UICONTROL Edit]**.
1. Välj **[!UICONTROL Video]** -fliken.

   ![chlimage_1-363](assets/chlimage_1-363.png)

   >[!NOTE]
   >
   >The **[!UICONTROL Video]** visas inte om sidan inte har någon molnkonfiguration.

1. Välj den adaptiva videokodningsprofilen, en färdig videokodningsprofil eller en anpassad videokodningsprofil.

   >[!NOTE]
   >
   >Mer information om vad videoförinställningarna betyder finns i [Dynamic Media Classic-dokumentation](https://experienceleague.adobe.com/docs/dynamic-media-classic/using/setup/application-setup.html#video-presets-for-encoding-video-files).
   >
   >Adobe rekommenderar att du antingen väljer båda adaptiva videouppsättningar när du konfigurerar de universella förinställningarna eller väljer **[!UICONTROL Adaptive Video Encoding]** alternativ.

1. De valda kodningsprofilerna tillämpas automatiskt på alla videoklipp som överförs till CQ DAM-målmappen som du konfigurerar för den här Scene7-molnkonfigurationen. Du kan konfigurera flera Scene7 molnkonfigurationer med olika målmappar för att tillämpa olika kodningsprofiler efter behov.

## Uppdatera visningsprogram och kodningsförinställningar {#updating-viewer-and-encoding-presets}

Det är nödvändigt att uppdatera visningsprogrammet och kodningsförinställningarna för video i Experience Manager om förinställningarna uppdaterades i Scene7. I sådana fall går du till Scene7-konfigurationen i molnkonfigurationen och klickar på **[!UICONTROL Update the viewer and encoding presets]**.

![chlimage_1-364](assets/chlimage_1-364.png)

## Överföra din överordnad video till Scene7 från Adobe DAM {#uploading-your-master-video}

1. Navigera till målmappen för CQ DAM där du har konfigurerat molnkonfigurationen med Scene7-kodningsprofiler.
1. Klicka **[!UICONTROL Upload]** för att ladda upp överordnad video. Överföring och kodning av video är klar när arbetsflödet för DAM-uppdatering av resurser är slutfört och **[!UICONTROL Publish to Scene7]** har en bock.

   >[!NOTE]
   >
   >Det tar en stund innan videominiatyrbilderna genereras.

   Dra den överordnad DAM-videon till videokomponentåtkomsten *alla* Scene7-kodade proxyrenderingar för leverans.

## Foundation Video Component jämfört med Scene7 Video Component {#foundation-video-component-versus-scene-video-component}

När du använder Experience Manager har du tillgång till både videokomponenten som finns på Sites och videokomponenten i Scene7. Dessa komponenter är inte utbytbara.

Scene7 videokomponent fungerar bara för Scene7-videofilmer. Grundkomponenten fungerar med videofilmer som lagras från Experience Manager (med ffmpeg) och Scene7-videofilmer.

I följande matris förklaras när du ska använda vilken komponent:

![chlimage_1-365](assets/chlimage_1-365.png)

>[!NOTE]
>
>S7-videokomponenten är körklar och använder den universella videoprofilen. Du kan dock hämta den HTML5-baserade videospelaren i Experience Manager. Kopiera enkelt inbäddningskoden för den färdiga HTML5-videospelaren och placera den på Experience Manager-sidan.

## Videokomponent för Experience Manager {#aem-video-component}

Även om du bör använda videokomponenten för Scene7 för att visa Scene7-videofilmer bör du för fullständighetens skull använda Scene7-videofilmer med Foundation Video Component.

### Experience Manager Video and Scene7 Video comparison {#aem-video-and-scene-video-comparison}

Följande tabell innehåller en högnivåjämförelse mellan videokomponenten i Experience Manager Foundation och Scene7 Video-komponenten som stöds:

|  | Experience Manager Foundation Video | Scene7 Video |
|---|---|---|
| Metod | HTML5:a första metoden. Flash används endast för reservlösningar som inte är HTML5. | Flash på de flesta stationära datorer. HTML5 används för mobiler och surfplattor. |
| Leverans | Progressiv | Adaptiv strömning |
| Spårning | Ja | Ja |
| Utbyggbarhet | Ja | Ja (med [API-dokumentation för HTML5 Viewer SDK](https://s7d1.scene7.com/s7sdk/3.10/docs/jsdoc/index.html)) |
| Mobilvideo | Ja | Ja |

### Konfigurera {#setting-up}

#### Skapa videoprofiler {#creating-video-profiles}

De olika videokodningarna skapas enligt de kodningsförinställningar för Scene7 som du har valt i Scene7 molnkonfiguration. För att komponenten Foundation Video ska kunna använda dem måste en videoprofil skapas för varje vald kodningsförinställning för Scene7. Med den här metoden kan videokomponenten välja DAM-återgivningar utifrån detta.

>[!NOTE]
>
>Nya videoprofiler och ändringar av dem måste aktiveras för publicering.

1. I Experience Manager: tryck **[!UICONTROL Tools]>[!UICONTROL Configuration Console]**.
1. Från **[!UICONTROL Configuration Console]** navigera till **[!UICONTROL Tools > DAM > Video Profiles]** i navigeringsträdet.
1. Skapa en Scene7-videoprofil. I **[!UICONTROL New...]** nedrullningsbar lista, välja **[!UICONTROL Create Page]** och sedan välja Scene7 videoprofilmall. Ge den nya videoprofilsidan ett namn och klicka på **[!UICONTROL Create]**.

   ![chlimage_1-366](assets/chlimage_1-366.png)

1. Redigera den nya videoprofilen. Välj molnkonfigurationen först. Välj sedan samma kodningsförinställning som du valde i molnkonfigurationen.

   ![chlimage_1-367](assets/chlimage_1-367.png)

   | Egenskap | Beskrivning |
   |---|---|
   | Scene7 Cloud-konfiguration | Den molnkonfiguration som ska användas för kodningsförinställningarna. |
   | Scene7 Encoding Preset | Den kodningsförinställning som den här videoprofilen ska kopplas till. |
   | HTML5-videotyp | Med den här egenskapen kan du ange värdet för type-egenskapen i HTML5-videokällelementet. Den här informationen finns inte i S7-kodningsförinställningarna, men krävs för att videofilerna ska kunna återges korrekt med videoelementet HTML5. En lista över vanliga format tillhandahålls, men kan skrivas över för andra format. |

   Upprepa det här steget för alla kodningsförinställningar som är markerade i molnkonfigurationen och som du vill använda i videokomponenten.

#### Konfigurera design {#configuring-design}

The **[!UICONTROL Foundation Video]** -komponenten måste känna till vilka videoprofiler som ska användas för att skapa listan över videokällor. Öppna dialogrutan för videokomponentdesign och konfigurera komponentdesignen för användning av de nya videoprofilerna.

>[!NOTE]
>
>Om du använder **[!UICONTROL Foundation Video]** på en mobilsida upprepar du de här stegen i designen av mobilsidan.

>[!NOTE]
>
>Ändringar som görs i designen kräver att designen aktiveras så att de kan börja gälla vid publiceringen.

1. Öppna **[!UICONTROL Foundation Video]** -komponentens designdialogruta och ändra till **[!UICONTROL Profiles]** -fliken. Ta sedan bort färdiga profiler och lägg till de nya videoprofilerna för S7. Ordningen på profillistan i designdialogrutan definierar ordningen på videokällelementet vid återgivning.
1. I webbläsare som inte stöder HTML5 kan du konfigurera ett Flash-reservläge med videokomponenten. Öppna dialogrutan för design av videokomponenter och ändra till **[!UICONTROL Flash]** -fliken. Konfigurera inställningarna för Flash Player och tilldela en reservprofil för Flash Player.

#### Checklista {#checklist}

1. Skapa en S7 Cloud-konfiguration. Kontrollera att förinställningarna för videokodning är angivna och att importeraren körs.
1. Skapa en S7-videoprofil för varje videokodningsförinställning som har valts i molnkonfigurationen.
1. Videoprofilerna måste aktiveras.
1. Konfigurera designen för **[!UICONTROL Foundation Video]** på sidan.
1. Aktivera designen när du är klar med designändringarna.
