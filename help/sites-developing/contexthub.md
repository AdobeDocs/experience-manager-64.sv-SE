---
title: ContextHub
seo-title: ContextHub
description: ContextHub är ett ramverk för att lagra, ändra och presentera kontextdata
seo-description: ContextHub is a framework for storing, manipulating, and presenting context data
uuid: 14e6ff4f-ffbe-454a-b2ec-a35333526e27
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: acf5c17a-95b7-43ba-9734-241e20f4f374
exl-id: 0a6b815a-5055-4c44-96d1-ff238b4285f3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# ContextHub{#contexthub}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

ContextHub är ett ramverk för att lagra, ändra och presentera kontextdata. Javascript-API:t på klientsidan gör att du kan komma åt data för att anpassa innehåll.

>[!NOTE]
>
>The [Referensimplementering för Vi.butik](/help/sites-developing/we-retail.md) implementerar ContextHub och kan fungera som referens när du integrerar ContextHub i ditt eget projekt.

>[!CAUTION]
>
>Sökvägen som innehåller exempelkonfigurationen för ContextHub som används av [Referensimplementering för Vi.butik](/help/sites-developing/we-retail.md) ( `/libs/settings/cloudsettings/legacy`) ska bara användas som referens när du skapar en egen konfiguration.
>
>Den ska inte användas i ett projekt som din egen ContextHub-konfiguration.

## Persistence {#persistence}

ContextHub lagrar kontextdata på klienten. Med ContextHub Javascript API kan du komma åt arkiv för att skapa, uppdatera och ta bort data efter behov. Därför representerar ContextHub ett datalager på dina sidor.

Varje ContextHub-butik är en instans av en fördefinierad lagringstyp:

* ContextHub innehåller flera [exempelarkivtyper](/help/sites-developing/ch-samplestores.md).
* Använd AEM konsoler för att [skapa butiker](/help/sites-administering/contexthub-config.md#creating-a-contexthub-store).
* Utvecklare kan [skapa anpassade butikstyper](/help/sites-developing/ch-extend.md#creating-custom-store-candidates).
* Utvecklare kan [åtkomstarkivdata](/help/sites-developing/ch-adding.md#interacting-with-contexthub-stores) via Javascript.

## Segmentering {#segmentation}

ContextHub innehåller en segmenteringsmotor som hanterar segment och fastställer vilka segment som matchas för den aktuella kontexten. Flera segment är definierade. Du kan använda Javascript-API:t för att [identifiera matchade segment](/help/sites-developing/ch-adding.md#determining-resolved-contexthub-segments).

## Presentation {#presentation}

The [ContextHub-verktygsfältet](/help/sites-authoring/ch-previewing.md) gör det möjligt för marknadsförare och författare att se och ändra butiksdata för att simulera användarupplevelsen när de skapar sidor. Verktygsfältet består av grupper med gränssnittsmoduler som ger åtkomst till ContextHub-butiker.

Varje ContextHub-gränssnittsmodul är en instans av en fördefinierad modultyp:

* ContextHub innehåller flera [exempelmodultyper](/help/sites-developing/ch-samplemodules.md).
* Använd AEM konsoler för att [lägg till gränssnittsmoduler](/help/sites-administering/contexthub-config.md#adding-a-ui-module)och till [gruppera dem i gränssnittslägen](/help/sites-administering/contexthub-config.md#adding-a-ui-mode).

* Utvecklare kan [skapa anpassade modultyper](/help/sites-developing/ch-extend.md#creating-contexthub-ui-module-types).

Utvecklare måste [lägg till ContextHub-komponenten på sidan](/help/sites-developing/ch-adding.md).
