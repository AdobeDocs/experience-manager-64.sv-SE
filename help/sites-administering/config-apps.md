---
title: Konfigurera för AEM program
seo-title: Configuring for AEM Apps
description: Lär dig hur du konfigurerar AEM.
seo-description: Learn how to configure AEM Apps.
uuid: ab9acd93-da7f-4bb7-8d26-224044899068
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: operations
content-type: reference
discoiquuid: 34f24837-f5e2-41f0-a359-fdb695e1b8f2
exl-id: 593a588c-02f1-4b48-ac57-9348d6652bcc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '177'
ht-degree: 0%

---

# Konfigurera för AEM program{#configuring-for-aem-apps}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med Adobe Experience Manager Apps kan du uppdatera innehållet i programmet direkt (OTA). Det uppdaterade innehållet lagras på publiceringsinstansen. Om du vill att appen på enheten ska kunna ansluta till publiceringsinstansen och söka efter uppdateringar måste publiceringsinstansen konfigureras så att en tom referensrubrik tillåts.

## Konfigurerar tomt referenshuvud {#configuring-empty-referrer-header}

Så här konfigurerar du referenspunktsfiltertjänsten:

* Öppna Apache Felix-konsolen (**Konfigurationer**) på:
* https://&lt;server>:&lt;port_number>/system/console/configMgr
* Logga in som administratör.
* I **Konfigurationer** väljer du: *Apache Sling Referer-filter*
* Markera fältet Tillåt tomt om du vill tillåta tomma/saknade hänvisningsrubriker.
* Klicka **Spara** för att spara ändringarna.

![chlimage_1-58](assets/chlimage_1-58.png)

Se [OSGI-konfigurationsinställningar](/help/sites-deploying/osgi-configuration-settings.md) och [Säkerhetschecklista - Problem med förfalska begäran mellan webbplatser](/help/sites-administering/security-checklist.md#protect-against-cross-site-request-forgery) för mer information.
