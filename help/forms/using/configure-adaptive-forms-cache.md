---
title: Konfigurera cacheminne för adaptiva formulär
seo-title: Konfigurera cacheminne för adaptiva formulär
description: 'Cacheminnet för anpassningsbara formulär är särskilt utformat för anpassningsbara formulär och dokument. Den cache-lagrar adaptiva formulär och adaptiva dokument i syfte att minska den tid som krävs för att återge ett adaptivt formulär eller dokument på klienten. '
seo-description: 'Cacheminnet för anpassningsbara formulär är särskilt utformat för anpassningsbara formulär och dokument. Den cache-lagrar adaptiva formulär och adaptiva dokument i syfte att minska den tid som krävs för att återge ett adaptivt formulär eller dokument på klienten. '
uuid: 3bd4e405-1eab-4e02-95cd-eb6ac25d18e3
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: dd18f7b5-882d-4e81-ab3d-85f1e5d74992
translation-type: tm+mt
source-git-commit: 49b7cff2c1583ee1eb929434f27c1989558e197f

---


# Konfigurera cacheminne för adaptiva formulär {#configure-adaptive-forms-cache}

Ett cacheminne är en mekanism som förkortar dataåtkomsttider, minskar latensen och förbättrar I/O-hastigheter (input/output). Cacheminnet för adaptiva formulär lagrar endast HTML-innehåll och JSON-strukturen i ett adaptivt formulär utan att några förfyllda data sparas. Det minskar tiden som krävs för att återge ett anpassat formulär eller dokument på klienten. Den är särskilt utformad för adaptiva formulär och stöder även adaptiva dokument.

>[!NOTE]
>
>När du använder cacheminnet för adaptiva formulär använder du AEM Dispatcher för att cachelagra klientbibliotek (CSS och JavaScript) för ett adaptivt formulär eller dokument.

>[!NOTE]
>
>När du utvecklar anpassade komponenter på servern som används för utveckling ska du inaktivera cachen för anpassade formulär.

## Konfigurera cacheminnet {#configure-the-cache}

Utför följande steg för att konfigurera cachen för adaptiva formulär:

1. Gå till konfigurationshanteraren för AEM-webbkonsolen på `https://[server]:[port]/system/console/configMgr`.
1. Klicka på **Adaptiv form och Interactive Communication Web Channel Configuration** för att redigera dess konfigurationsvärden.
1. I dialogrutan Redigera konfigurationsvärden anger du det maximala antalet formulär eller dokument som en instans av AEM Forms-servern kan cachelagra i fältet **Antal adaptiva formulär** . Standardvärdet är 100.

   >[!NOTE]
   >
   >Om du vill inaktivera cachen anger du värdet **0** i fältet Antal adaptiva formulär. Cacheminnet återställs och alla formulär och dokument tas bort från cacheminnet när du inaktiverar eller ändrar cachekonfigurationen.

   ![Konfigurationsdialogruta för HTML-cache för adaptiva formulär](assets/cache-configuration-edit.png)

1. Klicka på **Spara** för att spara konfigurationen.

