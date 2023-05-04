---
title: Åtkomst till enhetsfunktioner
seo-title: Access Device Features
description: Följ den här sidan om du vill veta mer om hur du skapar AEM komponenter som har åtkomst till enhetsfunktioner. AEM PhoneGap Kitchen Sink Github-databasen ger utvecklare en funktionell AEM-app som illustrerar användningen av ett antal centrala Cordova-API:er.
seo-description: Follow this page to learn about building AEM components that access device features. The AEM PhoneGap Kitchen Sink Github repository provides developers with a functional AEM app that illustrates the use of a number of core Cordova APIs.
uuid: 1996f017-21d3-4d90-9f55-95c626bc4c60
contentOwner: User
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/MOBILE
topic-tags: developing-adobe-phonegap-enterprise
discoiquuid: 0019e367-8edc-4a23-bfa4-5beda266ace6
exl-id: 7f3a5081-9640-49ce-a8e7-8061fc080ec1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Åtkomst till enhetsfunktioner{#access-device-features}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>Adobe rekommenderar att du använder SPA Editor för projekt som kräver ramverksbaserad klientåtergivning för en sida (t.ex. Reagera). [Läs mer](/help/sites-developing/spa-overview.md).

## Bygga AEM komponenter som har åtkomst till enhetsfunktioner {#building-aem-components-that-access-device-features}

The [AEM PhoneGap Kitchen Sink](https://github.com/blefebvre/aem-phonegap-kitchen-sink) I Github-databasen finns en funktionell AEM som illustrerar användningen av ett antal centrala Cordova-API:er. När programmet körs på iOS eller Android via PhoneGap CLI öppnas det på följande sida, som innehåller en länk till varje enhets-API som det visar:

![chlimage_1-107](assets/chlimage_1-107.png)

Källkoden för var och en av dessa enhets-API-komponenter är [finns på Github](https://github.com/blefebvre/aem-phonegap-kitchen-sink/tree/master/content/src/main/content/jcr_root/apps/brucelefebvre/kitchen-sink/components).

Mer information om hur varje API används finns i [Cordova plugin-dokumentation](https://docs.phonegap.com/en/4.0.0/cordova_plugins_pluginapis.md.html).

## Nästa steg {#the-next-steps}

Se [Spåra appprestanda med Adobe Mobile Analytics](/help/mobile/phonegap-intro-to-app-analytics.md).
