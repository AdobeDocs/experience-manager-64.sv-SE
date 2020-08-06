---
title: Videoåtergivningar
description: Videoåtergivningar
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1
workflow-type: tm+mt
source-wordcount: '219'
ht-degree: 0%

---


# Videoåtergivningar {#video-renditions}

Adobe Experience Manager (AEM) Assets genererar videoåtergivningar för videoresurser i olika format, bland annat OGG, FLV.

AEM Assets har stöd för statiska och dynamiska återgivningar (DM-kodade återgivningar) för medieresurser.

Statiska återgivningar genereras internt med hjälp av FFMPEG (som är installerat och tillgängligt på systemsökvägen) och lagras i innehållsdatabasen.

DM-kodade återgivningar lagras på proxyservern och hanteras vid körning.

AEM resurser har uppspelningsstöd för dessa återgivningar på klientsidan.

Om du vill visa återgivningarna för en viss videoresurs öppnar du resurssidan och trycker på ikonen Global navigering. Välj sedan **[!UICONTROL Renditions]** från listan.

![chlimage_1-478](assets/chlimage_1-478.png)

Listan med videoåtergivningar visas på **[!UICONTROL Renditions]** panelen.

![chlimage_1-479](assets/chlimage_1-479.png)

Om du vill konfigurera proxyservern för DM-kodade återgivningar [konfigurerar du tjänsterna i Dynamic Media Cloud.](config-dynamic.md)

Om du vill generera videoåtergivningar med önskade parametrar [skapar du en motsvarande videoprofil](video-profiles.md).

När du har konfigurerat proxyservern och skapat videoprofiler kan du ta med den här videoförinställningen i en bearbetningsprofil och använda bearbetningsprofilen i en mapp.

>[!NOTE]
>
>Ljuduppspelning fungerar inte för OGG- och WAV-filer i Internet Explorer 11. Felet &quot;Ogiltig källa&quot; visas på sidan med resursinformation för resurser med filnamnstillägget OGG eller WAV.
>
>På MS Edge och iPad spelas inte OGG-filer upp och ett formatfel som inte stöds genereras.
