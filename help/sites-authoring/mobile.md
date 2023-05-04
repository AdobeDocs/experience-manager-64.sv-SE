---
title: Skapa en sida för mobila enheter
seo-title: Authoring a Page for Mobile Devices
description: När du skapar för mobilen kan du växla mellan flera emulatorer för att se vad slutanvändaren ser
seo-description: When authoring for mobile, you can switch between several emulators to see what the end-user sees
uuid: a7a1ba68-d608-4819-88d1-0dab5955d3f4
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 9554cdb3-b604-4d50-9760-89b9e7a7755f
exl-id: 97f0b0d2-7d7b-4a90-a4e5-348a306e1622
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 0%

---

# Skapa en sida för mobila enheter{#authoring-a-page-for-mobile-devices}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När du skapar en mobilsida visas sidan på ett sätt som emulerar den mobila enheten. När du redigerar sidan kan du växla mellan flera emulatorer för att se vad slutanvändaren ser när han/hon öppnar sidan.

Enheterna grupperas i kategorierna, funktion, smart och touchfunktion enligt enhetens funktioner för att återge en sida. När slutanvändaren öppnar en mobilsida upptäcker AEM enheten och skickar den representation som motsvarar enhetsgruppen.

>[!NOTE]
>
>Om du vill skapa en mobilwebbplats baserad på en befintlig standardwebbplats skapar du en live-kopia av standardwebbplatsen. (Se [Skapa en Live-kopia för olika kanaler](/help/sites-administering/msm-livecopy.md).)
>
>AEM utvecklare kan skapa nya enhetsgrupper. (Se [Skapa enhetsgruppsfilter](/help/sites-developing/groupfilters.md).)

Använd följande procedur för att skapa en mobilsida:

1. Från global navigering öppnar du **Webbplatser** konsol.
1. Öppna sidan **Vi.butik** -> **Amerikas förenta stater** -> **Engelska**.

1. Växla till **Förhandsgranska** läge.
1. Växla till önskad emulator genom att klicka på enhetsikonen högst upp på sidan.
1. Dra och släpp komponenter från komponentwebbläsaren till sidan.

Sidan ser ut ungefär så här:

![mobileipademu](assets/mobileipademu.png)

>[!NOTE]
>
>Emulatorerna inaktiveras när en sida på författarinstansen begärs från en mobilenhet.
