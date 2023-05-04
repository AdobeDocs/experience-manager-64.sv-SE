---
title: Välja användargränssnitt
seo-title: Selecting your UI
description: För att underlätta för redigeringsanvändarna går det att växla till det klassiska användargränssnittet med det pekaktiverade gränssnittet när det behövs.
seo-description: For convenience to authoring users, the touch-enabled UI does allow for switching to the classic UI when necessary.
uuid: 755e513e-990c-4dba-8316-623f17bf5c33
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: dcac2a3a-3241-47de-96ce-982ab0bc05eb
exl-id: 997040d4-cf8f-4240-8423-a98d562aae02
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---

# Välja användargränssnitt{#selecting-your-ui}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Eftersom det beröringskänsliga användargränssnittet ersätter det klassiska användargränssnittet måste användaren eller administratören för den AEM instansen fatta ett aktivt beslut om att fortsätta använda det klassiska användargränssnittet. Eftersom det klassiska användargränssnittet inte längre underhålls går det inte att helt enkelt växla från det klassiska användargränssnittet till motsvarande i det beröringskänsliga användargränssnittet.

För att underlätta för redigeringsanvändarna går det att växla till det klassiska användargränssnittet med det pekaktiverade gränssnittet när det behövs. Se [Välja användargränssnitt](/help/sites-authoring/select-ui.md) i standarddokumentationen.

>[!NOTE]
>
>Instanser som uppgraderats från en tidigare version behåller det klassiska användargränssnittet för sidredigering.
>
>Efter uppgraderingen växlas inte sidredigering automatiskt till det beröringsaktiverade användargränssnittet, men du kan konfigurera detta med [OSGi-konfiguration](/help/sites-deploying/configuring-osgi.md) i **Tjänsten WCM för användargränssnittsläge vid redigering** ( `AuthoringUIMode` service). Se [Gränssnittsåsidosättningar för redigeraren](#uioverridesfortheeditor).

## Konfigurera standardgränssnittet för din instans {#configuring-the-default-ui-for-your-instance}

En systemadministratör kan konfigurera användargränssnittet som visas vid start och inloggning med [Rotmappning](/help/sites-deploying/osgi-configuration-settings.md#daycqrootmapping).

Detta kan åsidosättas av användarens standardinställningar eller sessionsinställningar.
