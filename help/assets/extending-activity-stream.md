---
title: Integrera resurser med aktivitetsström
description: Beskriver inspelningsfunktionerna i [!DNL Experience Manager] och konfigurera [!DNL Experience Manager] för att registrera specifika händelser.
contentOwner: AG
feature: Asset Management
role: Developer
exl-id: c25a4da7-1c58-41cf-9ff6-c094b50208e6
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 0%

---

# Integrera resurser med aktivitetsström {#integrating-assets-with-activity-stream}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets-användare utför många åtgärder, till exempel att skapa, överföra och ta bort resurser. Dessa åtgärder kan spelas in så att du kan ge en historik över vad en användare har gjort. I det här avsnittet beskrivs inspelningsfunktionerna i [!DNL Experience Manager] och konfigurera [!DNL Experience Manager] för att registrera specifika händelser.

## Prestandaöverväganden och standardbeteende {#performance-considerations-and-default-behavior}

Den här integreringen kan ta processorkraft och diskutrymme, t.ex. vid bulkimport. Av dessa anledningar [!DNL Experience Manager] Resursintegrering med aktivitetsströmmen är som standard inaktiverad.

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

## Konfigurerar [!DNL Assets] Inspelning av händelser {#configuring-aem-assets-events-recording}

The [Webbkonsol](/help/sites-deploying/configuring-osgi.md) ger åtkomst till [!DNL Assets] Justering av händelseinspelare. Så här konfigurerar du [!DNL Assets] Gör så här:

1. Navigera till **[!UICONTROL Web console]**

1. Klicka på **[!UICONTROL Configuration]**.

1. Dubbelklicka **[!UICONTROL Day CQ DAM Event Recorder]**.

1. Kontrollera **[!UICONTROL Enables this service]**.

1. Kontrollera vilken **[!UICONTROL Event Types]** du vill spelas in i användaraktivitetsströmmen.

1. Klicka på **[!UICONTROL Save]**.

## Läsa inspelade händelser {#reading-recorded-events}

De registrerade händelserna lagras som aktiviteter. Du kan läsa dem programmatiskt med [ActivityManager API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/granite/activitystreams/ActivityManager.html).
