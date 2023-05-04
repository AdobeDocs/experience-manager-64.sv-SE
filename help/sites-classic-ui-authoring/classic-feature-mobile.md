---
title: Skapa en sida för mobila enheter
seo-title: Authoring a Page for Mobile Devices
description: När du skapar en mobilsida visas sidan på ett sätt som emulerar den mobila enheten. När du redigerar sidan kan du växla mellan flera emulatorer för att se vad slutanvändaren ser när han/hon öppnar sidan.
seo-description: When authoring a mobile page, the page is displayed in a way that emulates the mobile device. When authoring the page, you can switch between several emulators to see what the end-user sees when accessing the page.
uuid: ca16979d-6e5f-444d-b959-ae92542039b2
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 430a27b5-f344-404f-8bf8-0d91b49b605e
exl-id: 26324f89-f5e2-40bc-96b4-0f3faa08bdd1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '333'
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
>AEM utvecklare kan skapa nya enhetsgrupper. (Se [Skapar enhetsgruppsfilter.](/help/sites-developing/groupfilters.md))

Använd följande procedur för att skapa en mobilsida:

1. Gå till **Webbadministratör** konsol.
1. Öppna **Produkter** sida nedanför **Webbplatser** >> **Geometrixx Mobile Demo Site** >> **Engelska**.

1. Växla till en annan emulator. Om du vill göra det kan du antingen:

   * Klicka på enhetsikonen högst upp på sidan.
   * Klicka på **Redigera** i **Sidekick** och välj enheten i listrutan.

1. Dra och släpp **Text och bild** från fliken Mobile i Sidekick till sidan.
1. Redigera komponenten och lägg till text. Klicka **OK** för att spara ändringarna.

Sidan ser ut på samma sätt som följande:

![mobileipademu](assets/mobileipademu.png)

>[!NOTE]
>
>Emulatorerna inaktiveras när en sida på författarinstansen begärs från en mobilenhet. Du kan sedan skapa med hjälp av det pekaktiverade användargränssnittet.
