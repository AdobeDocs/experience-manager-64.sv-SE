---
title: ContextHub Diagnostics
seo-title: ContextHub Diagnostics
description: ContextHub tillhandahåller en diagnostiksida där du kan se en översikt över ContextHub-ramverket
seo-description: ContextHub provides a diagnostics page where you can see an overview of the ContextHub framework
uuid: 94ef0696-3977-4781-ad32-9f4f117eb096
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: 6aa88583-5d34-4f77-a932-d47d84785eca
exl-id: 31926737-1a06-4fb9-b851-665095954875
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 0%

---

# ContextHub Diagnostics {#contexthub-diagnostics}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

ContextHub tillhandahåller en diagnostiksida där du kan se en översikt över ContextHub-ramverket. Öppna sidan genom att gå till `contexthub.diagnostics.html` sidan med AEM författarinstans, till exempel:

`http://<host>:<port>/conf/<tenant>/settings/cloudsettings/default/contexthub.diagnostics.html`

På sidan ContextHub Diagnostics (ContextHub-diagnostik) finns information om de butiker och gränssnittsmoduler som har skapats, vilka mappar i klientbiblioteket som har lästs in samt länkar till användbara sidor.

>[!NOTE]
>
>Felsökningsläget måste vara aktiverat för att diagnostikinformation ska kunna returneras, annars är diagnostiksidan tom. Se [det här dokumentet](/help/sites-administering/contexthub-config.md#debugging-contexthub) om du vill ha mer information om hur du aktiverar felsökningsläget.

>[!NOTE]
>
>För ContextHub-konfigurationer som fortfarande finns under sina tidigare sökvägar är platsen för diagnostiksidan `http://<host>:<port>/libs/settings/cloudsettings/legacy/contexthub.diagnostics.html`.

## Lager {#stores}

I avsnittet Lager visas alla ContextHub-butiker som har konfigurerats. Varje post i listan består av följande information:

* **Titel:** The [butikstyp](/help/sites-developing/ch-samplestores.md) som butiken baseras på.
* **sökväg:** Sökvägen till databasnoden som innehåller konfigurationen.
* **resourceType:** Sökvägen till databasnoden där lagringstypen har definierats.
* **clientlibs:** Kategorierna för de klientbibliotek som läses in och som implementerar lagringstypen.

## Moduler {#modules}

I avsnittet Moduler visas alla ContextHub-gränssnittsmoduler som har konfigurerats. Varje post i listan består av följande information:

* **Titel:** The [Modultyp för användargränssnitt](/help/sites-developing/ch-samplemodules.md) som användargränssnittsmodulen baseras på.
* **sökväg:** Sökvägen till databasnoden som innehåller konfigurationen.
* **resourceType:** Sökvägen till databasnoden där gränssnittsmodultypen definieras.
* **clientlibs:** De kategorier av klientbiblioteken som är inlästa och som implementerar UI-modultypen.

## Clientlibs {#clientlibs}

I Clientlibs-avsnittet visas alla klientbiblioteksmappar som ContextHub har läst in. Klientbiblioteken är kategoriserade:

* **kernel.js:** Klientbibliotek som implementerar ContextHub-ramverket, segmentmotorn och lagringstyperna.
* **ui.js:** Klientbibliotek som implementerar gränssnittstyperna ContextHub och UI.
* **style.css:** CSS-filer som läses in från klientbibliotek.

## URL:er {#urls}

Avsnittet URL:er innehåller länkar till ContextHub-funktioner:

* **Konfigurationsredigerare:** Öppnar [Konfigurationssida för ContextHub](/help/sites-administering/contexthub-config.md) där du kan konfigurera butiker, gränssnittslägen och gränssnittsmoduler.

* **Konfiguration av ContextHub-moduler:** Öppnar filen /etc/cloudsettings/default/contexthub.config.kernel.js, som innehåller Javascript-objektrepresentationen av ContextHub-lagringskonfigurationerna.
* **Konfiguration av ContextHub-gränssnitt:** Öppnar filen /etc/cloudsettings/default/contexthub.config.ui.js, som innehåller Javascript-objektrepresentationen av ContextHub-gränssnittets lägeskonfigurationer.
* **kernel.js:** Öppnar filen /etc/cloudsettings/default/contexthub.kernel.js, som innehåller källkoden för klientbiblioteken som implementerar ContextHub-ramverket, segmentmotorn och lagringstyperna.
* **ui.js:** Öppnar filen /etc/cloudsettings/default/contexthub.ui.js, som innehåller källkoden för de klientbibliotek som implementerar gränssnittstyperna för ContextHub och UI.
* **style.css:** Öppnar filen /etc/cloudsettings/default/contexthub.styles.css, som innehåller CSS-formaten för ContextHub-gränssnittsmodulerna och UI.
