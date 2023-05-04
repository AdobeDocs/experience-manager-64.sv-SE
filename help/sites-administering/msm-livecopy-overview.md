---
title: Översiktskonsol för Live Copy
seo-title: Live Copy Overview Console
description: Lär dig grunderna i Live Copy Overview Console.
seo-description: Learn about the basics of the Live Copy Overview Console.
uuid: 6b1841ec-950e-455b-9b30-b5f5050a67b8
contentOwner: AEM Docs
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 3763e985-7dd8-47fd-bfdf-2368b424c270
feature: Multi Site Manager
exl-id: 96238d40-c19a-4c1f-9400-c7bb8636b448
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '570'
ht-degree: 1%

---

# Översiktskonsol för Live Copy{#live-copy-overview-console}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

The **Live Copy - översikt** gör att du kan:

* Visa/hantera arv på en webbplats:

   * Visa det blå trädet och motsvarande Live-kopia-struktur, tillsammans med deras arvsstatus
   * Ändra arvsstatus; till exempel göra uppehåll, återuppta
   * Visa egenskaper för utkast och live-kopia

* Utför utrullningsåtgärder

## Öppna Live Copy-översikt {#opening-the-live-copy-overview}

Du kan öppna Live-kopieringsöversikt från:

* [Panelen Referenser till en översiktssida (Sites console)](#opening-live-copy-overview-references-for-a-blueprint-page)
* [Egenskaper för en ritningssida](#opening-live-copy-overview-properties-of-a-blueprint-page)

### Öppna Live Copy-översikt - referenser för en designsida {#opening-live-copy-overview-references-for-a-blueprint-page}

The **Live Copy - översikt** kan öppnas från **Referenser** sidpanelen på **Webbplatser** konsol:

1. I **Webbplatser** konsol, [navigera till din ritningssida och markera den](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).
1. Öppna **[Referenser](/help/sites-authoring/basic-handling.md#references)** panel och markera **Live-kopior**.

   ![chlimage_1-359](assets/chlimage_1-359.png)

   >[!NOTE]
   >
   >Du kan också öppna Referenser först och sedan välja en plan.

1. Välj **Live Copy - översikt** om du vill visa och använda översikten över alla live-kopior som hör till den valda planen.
1. Använd **Stäng** för att avsluta och återgå till **Webbplatser** konsol.

### Öppna Live Copy-översikt - egenskaper för en designsida {#opening-live-copy-overview-properties-of-a-blueprint-page}

The **Live Copy - översikt** kan öppnas när du visar egenskaper för en ritningssida:

1. Öppna **Egenskaper** för lämplig ritningssida.
1. Öppna **Blueprint** -fliken - **Live Copy - översikt** visas i det övre verktygsfältet:

   ![chlimage_1-360](assets/chlimage_1-360.png)

1. Välj **Live Copy - översikt** för att visa och använda översikten över alla live-kopior som hör till den aktuella planen.

   >[!NOTE]
   >
   >Mer information finns även i artikeln i kunskapsbasen [LiveCopy-statusmeddelande - uppdaterad/grön/synkroniserad](https://helpx.adobe.com/experience-manager/kb/livecopy-status-message---up-to-date-green-in-sync.html).

1. Använd **Stäng** för att avsluta och återgå till **Webbplatser** konsol.

## Använda Live Copy-översikt {#using-the-live-copy-overview}

The **Live Copy - översikt** kan även användas för att utföra åtgärder på live-kopian:

1. Öppna **Live Copy - översikt**.
1. Välj önskad skiss- eller Live copy-sida - verktygsfältet uppdateras för att visa tillgängliga åtgärder. The [funktionsmakron](/help/sites-administering/msm.md#terms-used) beroende på om du väljer [skiss](#actions-for-a-blueprint-page) eller [live copy](#actions-for-a-live-copy-page) sida:

### Åtgärder för en designsida {#actions-for-a-blueprint-page}

När du väljer en ritningssida är följande åtgärder tillgängliga:

![chlimage_1-361](assets/chlimage_1-361.png)

* Redigera

   * Öppna ritningssidan för redigering.

* [Utrullning](/help/sites-administering/msm.md#rollout-and-synchronize)

   * Utför en utrullning för att föra över ändringar från källan till livecopy.

### Åtgärder för en Live Copy-sida {#actions-for-a-live-copy-page}

När du väljer en live-kopieringssida är följande åtgärder tillgängliga:

![chlimage_1-362](assets/chlimage_1-362.png)

* Redigera

   * Öppna den aktiva kopieringssidan för redigering.

* [Relationsstatus](#relationship-status)

   * Visa information om status och arv.

* [Synkronisera](/help/sites-administering/msm.md#rollout-and-synchronize)

   * Synkronisera en live-kopia för att dra ändringar från källan till livecopy.

* [Återställ](/help/sites-administering/msm-livecopy.md#resetting-a-live-copy-page)

   * Återställ en live-kopieringssida om du vill ta bort alla arvsannulleringar och återställa sidan till samma läge som källsidan.

* [Gör uppehåll](/help/sites-administering/msm.md#suspending-and-cancelling-inheritance-and-synchronization)

   * Inaktiverar tillfälligt relationen mellan en live-kopia och dess ritningssida.

* [Återuppta](/help/sites-administering/msm-livecopy.md#resuming-inheritance-for-a-page)

   * Med Återuppta kan du återskapa en pausad relation.

* [Koppla loss](/help/sites-administering/msm.md#detaching-a-live-copy)

   * Tar permanent bort den aktiva relationen mellan en live-kopia och dess designsida.

## Relationsstatus {#relationship-status}

The **Relationsstatus** konsolen har två flikar med en rad funktioner:

* [Statusinformation för relation](#relationship-status-information)
* [Live Copy-information](#live-copy-information)

### Statusinformation för relation {#relationship-status-information}

På den här fliken finns detaljerad information om relationen mellan ritningen och den aktiva kopian:

![chlimage_1-363](assets/chlimage_1-363.png)

### Live Copy-information {#live-copy-information}

På den här fliken kan du visa och redigera konfigurationen av live-kopian:

![chlimage_1-364](assets/chlimage_1-364.png)
