---
title: Integrera resurser med aktivitetsström
description: Beskriver inspelningsfunktionerna i AEM och hur du konfigurerar AEM för att spela in specifika händelser.
contentOwner: AG
feature: Asset Management
role: Developer
translation-type: tm+mt
source-git-commit: 4acf159ae1b9923a9c93fa15faa38c7f4bc9f759
workflow-type: tm+mt
source-wordcount: '273'
ht-degree: 1%

---


# Integrera resurser med aktivitetsströmmen {#integrating-assets-with-activity-stream}

Adobe Experience Manager (AEM) Assets-användare utför många åtgärder, till exempel att skapa, överföra och ta bort resurser. Dessa åtgärder kan spelas in så att du kan ge en historik över vad en användare har gjort. I det här avsnittet beskrivs inspelningsfunktionerna i AEM och hur du konfigurerar AEM för att spela in specifika händelser.

## Prestandaöverväganden och standardbeteende {#performance-considerations-and-default-behavior}

Den här integreringen kan ta processorkraft och diskutrymme, t.ex. vid bulkimport. Därför är AEM Assets-integreringen med aktivitetsströmmen inaktiverad som standard.

## Åtgärdshändelser som stöds {#supported-action-events}

Följande händelser kan konfigureras för inspelning:

* Licensen har godkänts (ACCEPTED)
* Skapad resurs (ASSET_CREATED)
* Resurs flyttad (ASSET_MOVED)
* Resursen har tagits bort (ASSET_REMOVED)
* Licensen avvisades (avvisades)
* Hämtade resurser (HÄMTADE)
* Resursversion (VERSIONED)
* Resursversionen har återställts (RESTORED)
* Metadata för resurs har uppdaterats (METADATA_UPDATED)
* Tillgång publicerad till externt system (PUBLISHED_EXTERNAL)
* Resursens ursprungliga uppdaterade (ORIGINAL_UPDATED)
* Resursåtergivning uppdaterad (RENDITION_UPDATED)
* Resursåtergivning borttagen (RENDITION_REMOVED)
* Undertillgången har uppdaterats (SUBASSET_UPDATED)
* Deltillgång borttagen (SUBASSET_REMOVED)

## Konfigurerar inspelning av AEM Assets-händelser {#configuring-aem-assets-events-recording}

[Webbkonsolen](/help/sites-deploying/configuring-osgi.md) ger åtkomst till AEM Assets Event Recorder-justering. Så här konfigurerar du AEM Assets Event Recorder:

1. Navigera till **[!UICONTROL Web console]**

1. Klicka på **[!UICONTROL Configuration]**.

1. Dubbelklicka på **[!UICONTROL Day CQ DAM Event Recorder]**.

1. Kontroll **[!UICONTROL Enables this service]**.

1. Kontrollera vilken **[!UICONTROL Event Types]** du vill spela in i användaraktivitetsströmmen.

1. Klicka på **[!UICONTROL Save]**.

## Läser registrerade händelser {#reading-recorded-events}

De registrerade händelserna lagras som aktiviteter. Du kan läsa dem programmatiskt med hjälp av [ActivityManager API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/granite/activitystreams/ActivityManager.html).
