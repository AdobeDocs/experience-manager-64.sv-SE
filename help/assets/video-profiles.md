---
title: Dynamic Media videoprofiler
description: Dynamic Media har en fördefinierad adaptiv videokodningsprofil. Inställningarna i den här färdiga profilen är optimerade för att ge dina kunder bästa möjliga videovisning.
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: administering
content-type: reference
exl-id: 3602e1b9-624d-408f-a7f6-1598b62dbd22
feature: Video Profiles,Video
role: Admin,User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2885'
ht-degree: 15%

---

# Dynamic Media videoprofiler {#video-profiles}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Dynamic Media har redan en fördefinierad adaptiv videokodningsprofil. Inställningarna i den här färdiga profilen är optimerade för att ge kunderna bästa möjliga visningsupplevelse. När du kodar dina överordnad videofilmer med den adaptiva videokodningsprofilen justeras videospelaren automatiskt i videoströmmens kvalitet under uppspelningen baserat på internetanslutningshastigheten hos dina kunder. Detta kallas adaptiv strömning.

Följande är andra faktorer som avgör kvaliteten på videoklipp:

* **Upplösning för den överförda överordnad videon**

   Om MP4-videon spelades in med en lägre upplösning, till exempel 240p eller 360p, kan den inte direktuppspelas i HD.

* **Videospelarens storlek**

   Som standard är **[!UICONTROL Width]** i profilen Adaptiv videokodning är inställd på **[!UICONTROL Auto]**. Under uppspelningen används återigen den bästa kvaliteten baserat på spelarens storlek.

Se även [Bästa tillvägagångssätt för videokodning](video.md#best-practices-for-encoding-videos).

>[!NOTE]
>
>Om du vill generera videons metadata och tillhörande videobildsminiatyrer måste själva videon gå igenom kodningsprocessen i Dynamic Media. I AEM kodar arbetsflödet **[!UICONTROL Dynamic Media Encode Video]** video om du har aktiverat dynamiska medier och konfigurerat videolmolntjänster. Det här arbetsflödet innehåller information om arbetsflödets processhistorik och fel.
>
>Se [Övervaka videokodning och publiceringsförlopp på YouTube](video.md#monitoring-video-encoding-and-youtube-publishing-progress). Om du har aktiverat Dynamic Media och konfigurerat videolmolntjänster kan du **[!UICONTROL Dynamic Media Encode Video]** arbetsflödet aktiveras automatiskt när du överför en video. (Om du inte använder dynamiska medier aktiveras arbetsflödet **[!UICONTROL DAM Update Asset]**.)
>
>Metadata är användbara när du söker efter resurser. Miniatyrbilderna är statiska videobilder som genereras under kodningen. De krävs av AEM och används i användargränssnittet för att du ska kunna identifiera videoklipp i **[!UICONTROL Cards View]**, **[!UICONTROL Search Results]** och **[!UICONTROL Asset List]** vy. Du kan se de genererade miniatyrbilderna när du trycker på **[!UICONTROL Renditions]** ikon (en målares palett) för en kodad video.

När du har skapat videoprofilen använder du den på en mapp eller flera mappar. Se [Tillämpa en videoprofil på mappar.](#applying-a-video-profile-to-folders)

Mer information om hur du definierar avancerade bearbetningsparametrar för andra resurstyper finns i [Konfigurerar resursbearbetning](config-dms7.md#configuring-asset-processing).

## Förinställningar för adaptiv videokodning {#adaptive-video-encoding-presets}

I följande tabell visas kodningsprofiler med bästa praxis för adaptiv videoströmning till mobiler, surfplattor och stationära datorer. Du kan använda de här förinställningarna för video med alla proportioner.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Videoformatkodek</strong></td> 
   <td><strong>Videostorlek - bredd (px)</strong></td> 
   <td><strong>Videostorlek - höjd (px)</strong></td> 
   <td><strong>Behåll proportioner?</strong></td> 
   <td><strong>Videobithastighet (kbit/s)</strong></td> 
   <td><strong>Bildrutefrekvens för video (fps)</strong></td> 
   <td><strong>Ljudkodek</strong></td> 
   <td><strong>Ljudbithastighet (kbit/s)</strong></td> 
  </tr> 
  <tr> 
   <td><p>MP4 H.264 (mp4)</p> </td> 
   <td>auto</td> 
   <td>360</td> 
   <td>Ja</td> 
   <td>730</td> 
   <td>30</td> 
   <td>Dolby HE-AAC</td> 
   <td>128</td> 
  </tr> 
  <tr> 
   <td><p>MP4 H.264 (mp4)</p> </td> 
   <td>auto</td> 
   <td>540</td> 
   <td>Ja</td> 
   <td>2000<br /> </td> 
   <td>30</td> 
   <td>Dolby HE-AAC</td> 
   <td>128</td> 
  </tr> 
  <tr> 
   <td><p>MP4 H.264 (mp4)</p> </td> 
   <td>auto</td> 
   <td>720<br /> </td> 
   <td>Ja</td> 
   <td>3000<br /> </td> 
   <td>30</td> 
   <td>Dolby HE-AAC</td> 
   <td>128</td> 
  </tr> 
 </tbody> 
</table>

## Skapa en Dynamic Media videokodningsprofil för adaptiv strömning {#creating-a-video-encoding-profile-for-adaptive-streaming}

Dynamic Media har redan en fördefinierad Adaptive Video Encoding-profil - en grupp inställningar för videoöverföring för MP4 H.264 - som är optimerade för bästa möjliga visningsupplevelse. Du kan använda den här profilen när du överför videoklipp.

Om den här fördefinierade profilen inte uppfyller dina behov kan du välja att skapa en egen adaptiv videokodningsprofil. När du använder inställningen **[!UICONTROL Encode for adaptive streaming]**-*bästa praxis*- alla kodningsförinställningar som du lägger till i profilen valideras så att alla videoklipp har samma proportioner. Dessutom hanteras de kodade videoklippen som en uppsättning med flera bithastigheter för direktuppspelning.

När du skapar videokodningsprofilen ser du att de flesta kodningsalternativen är förifyllda med rekommenderade standardinställningar. Om du väljer ett annat värde än det rekommenderade standardvärdet bör du vara medveten om att det kan leda till sämre videokvalitet under uppspelning och andra prestandaproblem.

För alla kodningsförinställningar för MP4 H.264-video i profilen valideras följande värden för att säkerställa att de är desamma i alla enskilda kodningsförinställningar i profilen, vilket gör adaptiv strömning möjlig:

* Videoformatkodek - MP4 H.264 (.mp4)
* Ljudkodek
* Bithastighet för ljud
* Behåll proportioner
* Kodning i två omgångar
* Konstant bithastighet
* H264-profil
* Samplingsfrekvens för ljud

Om värdena inte är desamma kan du fortsätta skapa profilen som den är. Tänk dock på att adaptiv strömning inte kommer att vara möjlig. I stället får användarna direktuppspelning med en bithastighet. Vi rekommenderar att du redigerar kodningsinställningarna så att samma värden används för de enskilda kodningsförinställningarna i profilen. (Observera att videoprofilen/förinställningsredigeraren bör använda paritet för de adaptiva videokodningsinställningarna om **[!UICONTROL Encode for adaptive streaming]** är aktiverat.)

Se även [Skapa en videokodningsprofil för progressiv direktuppspelning](#creating-a-video-encoding-profile-for-progressive-streaming).

Se även [Bästa tillvägagångssätt för videokodning](video.md#best-practices-for-encoding-videos).

Mer information om hur du definierar avancerade bearbetningsparametrar för andra resurstyper finns i [Konfigurerar resursbearbetning](config-dms7.md#configuring-asset-processing).

När du har skapat videoprofilen kan du använda den på en eller flera mappar.

**Skapa en Dynamic Media videokodningsprofil för adaptiv strömning**:

1. Tryck eller klicka på AEM logotyp och navigera till **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Tryck **[!UICONTROL Create]** för att lägga till en ny videoprofil.

1. Ange ett namn och en beskrivning för profilen.
1. Se till att **[!UICONTROL Encode for adaptive streaming]** är markerad (standard).
1. Tryck på **[!UICONTROL Add Video Encoding Preset]**.
1. På **[!UICONTROL Basic]** anger du alternativen för video och ljud.

   Tryck på informationsikonen bredvid varje alternativ för ytterligare beskrivningar eller rekommenderade inställningar baserat på den valda videoformatkodeken.

1. Under rubriken Videostorlek ser du till att **[!UICONTROL Keep aspect ratio]** är markerad.
1. Ställ in videobildrutans upplösning i pixlar. Använd **[!UICONTROL Auto]** värdet skalas automatiskt så att det matchar källproportionerna (bredd-/höjdförhållandet). Exempel: Auto x 480 eller 640 x Auto.

   Gör något av följande:

   * I **[!UICONTROL Width]** fält, ange **[!UICONTROL auto]**. I **[!UICONTROL Height]** anger du ett värde i pixlar.
   * Om du vill visualisera storleken på videon trycker du på **[!UICONTROL Information]** ikon (i) till höger om **[!UICONTROL Height]** för att öppna **[!UICONTROL Size Calculator]** sida. Använd **[!UICONTROL Size Calculator]** för att ange de videodimensioner (som representeras av den blå rutan) som du vill använda. Tryck **[!UICONTROL X]** i det övre högra hörnet när du är klar.

1. (Valfritt) Tryck på **[!UICONTROL Advanced]** -fliken och kontrollera att **[!UICONTROL Use Default Values]** är markerad (rekommenderas). Du kan också ändra avancerade video- och ljudinställningar.
1. Tryck på längst upp till höger på sidan **[!UICONTROL Save]** för att spara förinställningen.
1. Gör något av följande:

   * Upprepa steg 5-10 för att skapa ytterligare kodningsförinställningar. (Adaptiv videoströmning kräver mer än en videoförinställning.)
   * Tryck på längst upp till höger på sidan **[!UICONTROL Save]** igen för att spara profilen.

## Övervaka kodningsjobbets förlopp {#monitoring-the-progress-of-an-encoding-job}

En bearbetningsindikator (eller förloppsindikator) visas så att du visuellt kan övervaka förloppet för ett videokodningsjobb.

Du kan även visa `error.log` för att övervaka förloppet för ett kodningsjobb, för att se om kodningen är klar eller för att se eventuella jobbfel. The `error.log` finns i `logs` mapp där instansen av AEM är installerad.

## Skapa en Dynamic Media videokodningsprofil för progressiv strömning {#creating-a-video-encoding-profile-for-progressive-streaming}

Om du väljer att inte använda alternativet **[!UICONTROL Encode for adaptive streaming]** måste du tänka på att alla kodningsförinställningar som du lägger till i profilen behandlas som individuella videoåtergivningar för strömning med en bithastighet eller progressiv videoleverans. Dessutom går det inte att kontrollera att alla videoåtergivningar har samma proportioner.

Beroende på vilket läge du använder är videoformatets kodekar följande:

* Dynamic Media-Scene7-läge: H.264 (.mp4)
* Dynamic Media-hybridläge: H.264 (.mp4), WebM

Se även [Skapa en videokodningsprofil för adaptiv strömning](#creating-a-video-encoding-profile-for-adaptive-streaming).

Se även [Bästa tillvägagångssätt för videokodning](video.md#best-practices-for-encoding-videos).

Mer information om hur du definierar avancerade bearbetningsparametrar för andra resurstyper finns i [Konfigurerar resursbearbetning](config-dms7.md#configuring-asset-processing).

När du har skapat videoprofilen kan du använda den på en eller flera mappar.

**Så här skapar du en Dynamic Media videokodningsprofil för progressiv direktuppspelning:**

1. Tryck på AEM-logotypen och navigera till **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Tryck **[!UICONTROL Create]** för att lägga till en ny videoprofil.
1. Ange ett namn och en beskrivning för profilen.
1. Rensa **[!UICONTROL Encode for adaptive streaming]** kryssruta.
1. Tryck på **[!UICONTROL Add Video Encoding Preset]**.
1. På **[!UICONTROL Basic]** anger du alternativen för video och ljud.

   Tryck på **[!UICONTROL Information]** -ikonen bredvid varje alternativ för ytterligare beskrivningar eller rekommenderade inställningar baserat på den valda videoformatkodeken.

1. (Valfritt) Under **Videostorlek** rubrik, avmarkera **[!UICONTROL Keep aspect ratio]**.
1. I **[!UICONTROL Width]** fält, ange **[!UICONTROL auto]**; till höger om **[!UICONTROL Height]** fält, tryck på **[!UICONTROL Information]** ikon. Använd **[!UICONTROL Size Calculator]** för att ytterligare ange videodimensionen (blå ruta). Tryck **[!UICONTROL X]** när du är klar.
1. (Valfritt) Gör något av följande:

   * Tryck på **[!UICONTROL Advanced]** och se till att **[!UICONTROL Use Default Values]** är markerad (rekommenderas).
   * Rensa **[!UICONTROL Use Default Values]** och ange önskade videoinställningar och ljudinställningar.

      Tryck på **[!UICONTROL Information]** -ikonen bredvid varje alternativ för ytterligare beskrivningar eller rekommenderade inställningar baserat på den valda videoformatkodeken.

1. Tryck på längst upp till höger på sidan **[!UICONTROL Save]** för att spara förinställningen.
1. Gör något av följande:

   * Upprepa steg 5-10 för att skapa ytterligare kodningsförinställningar.
   * Tryck på **[!UICONTROL Save]** i det övre högra hörnet på sidan för att spara profilen.

## Använda egna parametrar för videokodning {#using-custom-added-video-encoding-parameters}

Du kan redigera en befintlig videokodningsprofil för att dra nytta av avancerade videokodningsparametrar som inte finns i användargränssnittet när du skapar eller redigerar en videoprofil i AEM. Du kan lägga till en eller flera avancerade parametrar, till exempel **[!UICONTROL minBitrate]** och **[!UICONTROL maxBitrate]**- till din befintliga profil.

**Använda egna videokodningsparametrar**:

1. Tryck på AEM-logotypen och navigera sedan till **[!UICONTROL Tools > General > CRXDE Lite]**.
1. Från **[!UICONTROL CRXDE Lite]** sida, på **[!UICONTROL Explorer]** till vänster navigerar du till följande:

   `/conf/global/settings/dam/dm/presets/video/*name_of_video_encoding_profile_to_edit*`

1. I panelen längst ned till höger på sidan, från **[!UICONTROL Properties]** -fliken, ange **[!UICONTROL Name]**, **[!UICONTROL Type]** och **[!UICONTROL Value]** för den parameter som du vill använda.

   Följande avancerade parametrar är tillgängliga:

   <table> 
    <tbody> 
    <tr> 
    <td><strong>Namn</strong></td> 
    <td><strong>Beskrivning</strong><br /> </td> 
    <td><strong>Typ</strong><br /> </td> 
    <td><strong>Värde</strong></td> 
    </tr> 
    <tr> 
    <td><code>h264Level</code></td> 
    <td>H.264-nivå som ska användas för kodning. Normalt bestäms detta automatiskt utifrån de kodningsinställningar som du använder.</td> 
    <td><code>String</code></td> 
    <td><p>10 * h264 nivå</p> <p>3.0 = 30, 1.3 = 13)</p> <p>Inget standardvärde.</p> </td> 
    </tr> 
    <tr> 
    <td><code>keyframe</code></td> 
    <td>Målantalet bildrutor mellan nyckelbildrutor. Beräkna det här värdet för att generera en nyckelbildruta var 2:10:e sekund. Exempel: vid 30 bildrutor per sekund ska nyckelbildruteintervallet vara 60-300.<br /> <br /> Lägre intervall för nyckelrutor förbättrar strömsöknings- och strömbrytningsbeteendet för adaptiv videokodning och kan även förbättra kvaliteten för videoklipp som har mycket rörelse. Men eftersom nyckelrutor ökar filstorleken resulterar ett lägre nyckelruteintervall vanligtvis i en lägre total videokvalitet med en viss bithastighet.</td> 
    <td><code>String</code></td> 
    <td><p>Positivt nummer.</p> <p>Standardvärdet är 300.</p> <p>Rekommenderat värde för HLS (HTTP Live Streaming) är 60-90.</p> </td> 
    </tr> 
    <tr> 
    <td><code>minBitrate</code></td> 
    <td><p>Minsta bithastighet som tillåter variabel bithastighetskodning, i kbit/s (kilobit per sekund).</p> <p>Den här parametern gäller bara när<strong> Använd konstant bithastighet</strong> är avmarkerat på fliken Avancerat när du skapar eller redigerar en videokodningsprofil.</p> <p>Se även <a href="/help/assets/video.md#bitrate">Bithastighet</a>.</p> </td> 
    <td><code>String</code></td> 
    <td><p>Positivt tal i kbit/s.</p> <p>Inget standardvärde.</p> </td> 
    </tr> 
    <tr> 
    <td><code>maxBitrate</code></td> 
    <td><p>Maximal bithastighet som tillåter variabel bithastighetskodning, i kbit/s.</p> <p>Den här parametern gäller bara när<strong> Använd konstant bithastighet</strong> är avmarkerat på fliken Avancerat när du skapar eller redigerar en videokodningsprofil.</p> <p>Se även <a href="/help/assets/video.md#bitrate">Bithastighet</a>.</p> </td> 
    <td><code>String</code></td> 
    <td><p>Positivt tal i kbit/s.</p> <p>Inget standardvärde. Det rekommenderade värdet är dock upp till två gånger högre än kodningsbithastigheten.</p> </td> 
    </tr> 
    <tr> 
    <td><code>audioBitrateCustom</code></td> 
    <td>Ange värde till <code>true</code> för att tvinga fram en konstant bithastighet för ljudströmmen, om detta stöds av ljudkodeken.</td> 
    <td><code>String</code></td> 
    <td><p><code>true</code>/<code>false</code></p> <p>Standard är <code>false</code>.</p> <p>Rekommenderat värde för HLS (HTTP Live Streaming) är <code>false</code>.</p> <p> </p> </td> 
    </tr> 
    </tbody> 
   </table>

   ![chlimage_1-516](assets/chlimage_1-516.png)

1. I sidans nedre högra hörn trycker du **[!UICONTROL Add]**.
1. Gör något av följande:

   * Upprepa steg 3 och 4 för att lägga till ytterligare en parameter i videokodningsprofilen.
   * Knacka i det övre vänstra hörnet av sidan **[!UICONTROL Save All]**.

1. I det övre vänstra hörnet av **[!UICONTROL CRXDE Lite]** tryck på **[!UICONTROL Back Home]** -ikonen för att återgå till AEM.

### Redigera en Dynamic Media videokodningsprofil {#editing-a-video-encoding-profile}

Du kan redigera alla videokodningsprofiler som du har skapat för att lägga till, redigera eller ta bort förinställningar för video i den profilen.

Som standard kan du inte redigera de fördefinierade, färdiga **[!UICONTROL Adaptive Video Encoding]** profil som medföljde Dynamic Media. I stället kan du enkelt kopiera profilen och spara den med ett nytt namn. Du kan sedan redigera de önskade förinställningarna i den kopierade profilen.

Se även [Bästa tillvägagångssätt för videokodning](video.md#best-practices-for-encoding-videos).

Mer information om hur du definierar avancerade bearbetningsparametrar för andra resurstyper finns i [Konfigurerar resursbearbetning](config-dms7.md#configuring-asset-processing).

**Så här redigerar du en videokodningsprofil för Dynamic Media**:

1. Tryck på AEM-logotypen och navigera till **[!UICONTROL Tools > Assets > Video Profiles]**.
1. På **[!UICONTROL Video Profiles]** markerar du ett videoprofilnamn.
1. Tryck på i verktygsfältet **[!UICONTROL Edit]**.
1. På **[!UICONTROL Video Encoding Profile]** kan du redigera namn och beskrivning efter behov.
1. Det är en god idé att se till att kryssrutan **[!UICONTROL Encode for adaptive streaming]** är markerad.

   Tryck på informationsikonen om du vill se en beskrivning av adaptiv strömning. (Om du redigerar en progressiv videoprofil ska du inte markera den här kryssrutan.)

1. Under **[!UICONTROL Video Encoding Presets]** rubrik, lägga till, redigera eller ta bort förinställningar för videokodning som utgör profilen.

   Tryck på **[!UICONTROL Information]** -ikonen bredvid varje alternativ på **[!UICONTROL Basic]** och **[!UICONTROL Advanced]** om du vill ha mer information eller rekommenderade inställningar baserat på den valda videoformatkodeken.

1. Tryck på längst upp till höger på sidan **[!UICONTROL Save]**.

### Kopiera en Dynamic Media videokodningsprofil {#copying-a-video-encoding-profile}

1. Tryck på AEM-logotypen och navigera till **[!UICONTROL Tools > Assets > Video Profiles]**.
1. På **[!UICONTROL Video Profiles]** markerar du ett videoprofilnamn.
1. Tryck på i verktygsfältet **[!UICONTROL Copy]**.
1. På **[!UICONTROL Video Encoding Profile]** anger du ett nytt namn för profilen.
1. Det är en god idé att se till att kryssrutan **[!UICONTROL Encode for adaptive streaming]** är markerad. Tryck på informationsikonen om du vill se en beskrivning av adaptiv strömning. (Om du kopierar en progressiv videoprofil markerar du inte kryssrutan.)

   I Dynamic Media - hybrid-läge, om en WebM-videoförinställning är en del av videoprofilen, **[!UICONTROL Encode for adaptive streaming]** är inte möjligt eftersom alla förinställningar måste vara MP4.
1. Under **[!UICONTROL Video Encoding Presets]** rubrik, lägga till, redigera eller ta bort förinställningar för videokodning som utgör profilen.

   Tryck på **[!UICONTROL Information]** -ikonen bredvid varje alternativ på **[!UICONTROL Basic]** och **[!UICONTROL Advanced]** för rekommenderade inställningar och beskrivningar.

1. Tryck på längst upp till höger på sidan **[!UICONTROL Save]**.

### Ta bort en Dynamic Media videokodningsprofil {#deleting-a-video-encoding-profile}

1. Tryck på AEM-logotypen och navigera till **[!UICONTROL Tools > Assets > Video Profiles]**.
1. På **[!UICONTROL Video Profiles]** markerar du ett eller flera videoprofilnamn.
1. Tryck på i verktygsfältet **[!UICONTROL Delete]**.
1. Tryck på **[!UICONTROL OK]**.

## Använda en Dynamic Media-videoprofil på mappar {#applying-a-video-profile-to-folders}

När du tilldelar en videoprofil till en mapp ärver alla undermappar automatiskt profilen från den överordnade mappen. Det innebär att du bara kan tilldela en videoprofil till en mapp. Fundera därför noga över mappstrukturen för var du överför, lagrar, använder och arkiverar resurser.

Om du har tilldelat en annan videoprofil till en mapp åsidosätter den nya profilen den tidigare profilen. De tidigare befintliga mappresurserna ändras inte. Den nya profilen används för resurser som läggs till i mappen senare.

Mappar som har tilldelats en profil visas i användargränssnittet med namnet på profilen som visas i kortnamnet.

![chlimage_1-517](assets/chlimage_1-517.png)

Du kan tillämpa videoprofiler på specifika mappar eller globalt på alla resurser.

### Tillämpa videoprofiler på specifika mappar {#applying-video-profiles-to-specific-folders}

Du kan använda en videoprofil på en mapp från menyn **[!UICONTROL Tools]** eller, om du är i mappen, från **[!UICONTROL Properties]**. I det här avsnittet beskrivs hur du använder videoprofiler på mappar på båda sätten.

För mappar som redan har tilldelats en profil visas profilens namn direkt under mappnamnet.

#### Använda Dynamic Media videoprofiler på mappar från användargränssnittet Profiles {#applying-video-profiles-to-folders-from-profiles-user-interface}

1. Tryck på AEM-logotypen och navigera till **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Välj den videoprofil som du vill använda för en eller flera mappar.
1. Tryck på **[!UICONTROL Apply Profile to Folder(s)]** och markera den eller de mappar som du vill ska ta emot de nyligen överförda resurserna och tryck sedan på **[!UICONTROL Apply]**. För mappar som redan har tilldelats en profil visas profilens namn direkt under mappnamnet.

#### Använda Dynamic Media videoprofiler på mappar från Egenskaper {#applying-video-profiles-to-folders-from-properties}

1. Tryck på AEM logotyp och navigera till **[!UICONTROL Assets]** och sedan till den mapp som du vill använda en videoprofil på.
1. Markera mappen genom att trycka på bockmarkeringen och sedan på **[!UICONTROL Properties]**.
1. Välj **[!UICONTROL Video Profiles]** och välj profilen i listrutan och tryck på **[!UICONTROL Save & Close]**. För mappar som redan har tilldelats en profil visas profilens namn direkt under mappnamnet.

   ![chlimage_1-518](assets/chlimage_1-518.png)

### Använda en Dynamic Media-videoprofil globalt {#applying-a-video-profile-globally}

Förutom att tillämpa en profil på en mapp kan du även tillämpa en profil globalt så att allt innehåll som överförs till AEM resurser i en mapp har den valda profilen.

**Använda en Dynamic Media-videoprofil globalt**:

1. Navigera till CRXDE Lite till följande nod: `/content/dam/jcr:content`.
1. Lägg till egenskapen **[!UICONTROL videoProfile]**: `/etc/dam/video/dynamicmedia/<name_of_video_encoding_profile>`
1. Tryck på **[!UICONTROL Save All]**.

![chlimage_1-519](assets/chlimage_1-519.png)

## Ta bort en Dynamic Media-videoprofil från mappar {#removing-a-video-profile-from-folders}

När du tar bort en videoprofil från en mapp ärver alla undermappar automatiskt borttagningen av profilen från den överordnade mappen. All bearbetning av filer som har inträffat i mapparna förblir dock oförändrad.

Du kan ta bort en videoprofil från en mapp från menyn **[!UICONTROL Tools]** eller, om du är i mappen, från **[!UICONTROL Folder Settings]**. I det här avsnittet beskrivs hur du tar bort videoprofiler från mappar på båda sätten.

### Ta bort Dynamic Media videoprofiler från mappar via profilanvändargränssnittet {#removing-video-profiles-from-folders-via-profiles-user-interface}

1. Tryck på AEM-logotypen och navigera till **[!UICONTROL Tools > Assets > Video Profiles]**.
1. Markera den videoprofil som du vill ta bort från en eller flera mappar.
1. Tryck på **[!UICONTROL Remove Profile from Folder(s)]** och markera den eller de mappar som du vill ta bort profilen från och tryck sedan på **[!UICONTROL Remove]**.

   Du kan bekräfta att videoprofilen inte längre används för en mapp eftersom namnet inte längre visas under mappnamnet.

### Ta bort Dynamic Media videoprofiler från mappar med hjälp av Egenskaper {#removing-video-profiles-from-folders-via-properties}

1. Tryck på AEM logotyp och navigera till **[!UICONTROL Assets]** och sedan till mappen som du vill ta bort en videoprofil från.
1. Markera mappen genom att trycka på bockmarkeringen och sedan trycka på **[!UICONTROL Properties]**.
1. Välj **[!UICONTROL Video Profiles]** och markera **[!UICONTROL None]** i listrutan och tryck på **[!UICONTROL Save & Close]**. För mappar som redan har tilldelats en profil visas profilens namn direkt under mappnamnet.
