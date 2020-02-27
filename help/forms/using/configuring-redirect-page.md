---
title: Konfigurerar omdirigeringssida
seo-title: Konfigurerar omdirigeringssida
description: När du har fyllt i ett anpassat formulär kan användarna omdirigeras till en webbsida som formulärförfattarna kan konfigurera när de skapar formuläret.
seo-description: När du har fyllt i ett anpassat formulär kan användarna omdirigeras till en webbsida som formulärförfattarna kan konfigurera när de skapar formuläret.
uuid: 5a5f912a-9696-4bc1-af3f-ead78f767e02
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: c51817aa-193a-4d4f-bd83-06518ddfb395
translation-type: tm+mt
source-git-commit: 8cbfa421443e62c0483756e9d5812bc987a9f91d

---


# Konfigurerar omdirigeringssida {#configuring-redirect-page}

Formulärförfattare kan konfigurera en sida för varje formulär som formuläranvändarna omdirigeras till efter att de har skickat in formuläret.

1. Markera en komponent i redigeringsläget, klicka på ![fältnivå](assets/field-level.png) > **Adaptiv formulärbehållare** och klicka sedan på ![cmpr](assets/cmppr.png).

1. Klicka på **Skicka** i sidlisten.

1. Ange URL-adressen till omdirigeringssidan under Tack-sidan i avsnittet Skicka.
1. Under Skicka-åtgärd kan du som alternativ konfigurera parametern som ska skickas till omdirigeringssidan för slutpunktsåtgärden Skicka till REST.

![](assets/thank-you-setting-1.png) Konfiguration **av omdirigeringssida** Bild: Konfigurera *omdirigeringssida*

Formulärförfattare kan använda följande parametrar som skickas till sidan Tack. Alla tillgängliga skicka-åtgärder `status` och - `owner` parametrar skickas. Förutom dessa två parametrar skickas ytterligare några parametrar för följande skicka-åtgärder:

* **Åtgärden** Lagra innehåll (borttagen): `contentPath`- sökvägen till noden i databasen där skickade data lagras - skickas.

* **Åtgärden** Lagra PDF (borttagen): `contentPath`- av skickade data och sökvägen till noden som lagrar PDF-filen i databasen - skickas.

* **Arbetsflödet** Skicka till formulär: Utdataparametrar som returneras från formulärarbetsflöden skickas.

* **Skicka till REST-slutpunkt**: Parametrar som lagts till för mappning mellan fältparametrar skickas. `status` och `owner` parametrar skickas inte i den här skicka-åtgärden. Mer information finns i [Konfigurera Skicka till REST-slutpunktsåtgärden](/help/forms/using/configuring-submit-actions.md).

