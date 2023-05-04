---
title: Konfigurerar omdirigeringssida
seo-title: Configuring redirect page
description: När du har fyllt i ett anpassat formulär kan användarna omdirigeras till en webbsida som formulärförfattarna kan konfigurera när de skapar formuläret.
seo-description: After filling an adaptive form, users can be redirected to a webpage that form authors can configure while creating the form.
uuid: 5a5f912a-9696-4bc1-af3f-ead78f767e02
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: c51817aa-193a-4d4f-bd83-06518ddfb395
feature: Adaptive Forms
exl-id: bbe10952-d6a7-4adc-bab9-388c1ee8e56a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '274'
ht-degree: 0%

---

# Konfigurerar omdirigeringssida {#configuring-redirect-page}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Formulärförfattare kan konfigurera en sida för varje formulär som formuläranvändarna omdirigeras till efter att de har skickat in formuläret.

1. Markera en komponent i redigeringsläget och klicka sedan på ![fältnivå](assets/field-level.png) > **Adaptiv formulärbehållare** och klicka sedan på ![cmppr](assets/cmppr.png).

1. Klicka på **Inlämning**.

1. Ange URL-adressen till omdirigeringssidan under Tack-sidan i avsnittet Skicka.
1. Under Skicka-åtgärd kan du som alternativ konfigurera parametern som ska skickas till omdirigeringssidan för slutpunktsåtgärden Skicka till REST.

![Omdirigeringssidkonfiguration](assets/thank-you-setting-1.png)
**Bild:** *Omdirigeringssidkonfiguration*

Formulärförfattare kan använda följande parametrar som skickas till sidan Tack. För alla tillgängliga inskickningsåtgärder: `status` och `owner` parametrar skickas. Förutom dessa två parametrar skickas ytterligare några parametrar för följande skicka-åtgärder:

* **Åtgärden Lagra innehåll** (utgått): `contentPath`- sökvägen till noden i databasen där skickade data lagras skickas.

* **Åtgärden Lagra PDF** (utgått): `contentPath`- av skickade data och sökvägen till noden som lagrar PDF-filen i databasen - skickas.

* **Skicka till Forms-arbetsflöde**: Utdataparametrar som returneras från formulärarbetsflöden skickas.

* **Skicka till REST-slutpunkt**: Parametrar som lagts till för mappning mellan fältparametrar skickas. `status` och `owner` parametrar skickas inte i den här skicka-åtgärden. Mer information finns i [Konfigurera åtgärden Skicka till REST-slutpunkt](/help/forms/using/configuring-submit-actions.md).
