---
title: Resurser för HTTP API i [!DNL Adobe Experience Manager].
description: Skapa, läsa, uppdatera, ta bort, hantera digitala resurser med HTTP API i [!DNL Adobe Experience Manager Assets].
contentOwner: AG
feature: APIs,Assets HTTP API,Developer Tools
role: Developer
exl-id: 3d7d078c-5046-489a-a8e0-258acaea7191
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1576'
ht-degree: 0%

---

# HTTP API för Assets {#assets-http-api}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med Assets HTTP API kan du skapa, läsa, uppdatera och ta bort (CRUD)-åtgärder för digitala resurser, inklusive metadata, återgivningar och kommentarer, samt strukturerat innehåll med [!DNL Experience Manager] Innehållsfragment. Den exponeras vid `/api/assets` och implementeras som REST API.

Så här kommer du åt API:

1. Öppna API-tjänstdokumentet på `https://[hostname]:[port]/api.json`.
1. Följ länken för Assets-tjänsten för att `https://[hostname]:[server]/api/assets.json`.

API-svaret är en JSON-fil för vissa MIME-typer och en svarskod för alla MIME-typer. JSON-svaret är valfritt och kanske inte är tillgängligt, till exempel för PDF-filer. Använd svarskoden för ytterligare analyser eller åtgärder.

Efter [!UICONTROL Off Time], är en resurs och dess återgivningar inte tillgängliga via [!DNL Assets] webbgränssnitt och via HTTP API. API:t returnerar 404-felmeddelande om [!UICONTROL On Time] kommer i framtiden eller [!UICONTROL Off Time] har redan varit.

>[!CAUTION]
>
>[HTTP API uppdaterar metadataegenskaperna](#update-asset-metadata) i `jcr` namnutrymme. Experience Manager uppdaterar emellertid metadataegenskaperna i `dc` namnutrymme.

## Datamodell {#data-model}

Resursens HTTP-API visar två huvudelement, mappar och resurser (för standardresurser).

### Mappar {#folders}

Mappar är som kataloger i traditionella filsystem. De är behållare för andra mappar eller kontroller. Mappar har följande komponenter:

**Enheter**: Enheterna i en mapp är dess underordnade element, som kan vara mappar och resurser.

**Egenskaper**:

* `name` är namnet på mappen. Detta är samma som det sista segmentet i URL-sökvägen utan tillägget.
* `title` är en valfri mapptitel som kan visas i stället för dess namn.

>[!NOTE]
>
>Vissa egenskaper för mapp eller resurs är mappade till ett annat prefix. The `jcr` prefix för `jcr:title`, `jcr:description`och `jcr:language` ersätts med `dc` prefix. I den returnerade JSON-koden `dc:title` och `dc:description` innehåller värdena för `jcr:title` och `jcr:description`, respektive.

**Länkar** I mapparna visas tre länkar:

* `self`: Länka till sig själv.
* `parent`: Länka till den överordnade mappen.
* `thumbnail`: (Valfritt) länka till en mappminiatyrbild.

### Assets {#assets}

I Experience Manager innehåller en resurs följande element:

* Resursens egenskaper och metadata.
* Flera återgivningar, till exempel den ursprungliga återgivningen (som är den ursprungliga överförda resursen), en miniatyrbild och olika andra återgivningar. Ytterligare återgivningar kan vara bilder av olika storlek, olika videokodningar eller extraherade sidor från PDF- eller Adobe InDesign-filer.
* Valfria kommentarer.

I [!DNL Experience Manager] en mapp har följande komponenter:

* Enheter: Resursernas underordnade är dess återgivningar.
* Egenskaper.
* Länkar.

Resursens HTTP-API innehåller följande funktioner:

* [Hämta en mapplista](#retrieve-a-folder-listing).
* [Skapa en mapp](#create-a-folder).
* [Skapa en resurs](#create-an-asset).
* [Uppdatera resursens binära](#update-asset-binary).
* [Uppdatera metadata för resurs](#update-asset-metadata).
* [Skapa en resursåtergivning](#create-an-asset-rendition).
* [Uppdatera en resursåtergivning](#update-an-asset-rendition).
* [Skapa en resurskommentar](#create-an-asset-comment).
* [Kopiera en mapp eller resurs](#copy-a-folder-or-asset).
* [Flytta en mapp eller resurs](#move-a-folder-or-asset).
* [Ta bort en mapp, resurs eller återgivning](#delete-a-folder-asset-or-rendition).

>[!NOTE]
>
>För att underlätta läsbarheten utelämnar följande exempel den fullständiga cURL-notationen. Faktum är att notationen korrelerar med [Återställ](https://github.com/micha/resty) som är en skriptwrapper för `cURL`.

**Förutsättningar**

* Öppna `https://[aem_server]:[port]/system/console/configMgr`.
* Navigera till **[!UICONTROL Adobe Granite CSRF Filter]**.
* Kontrollera egenskapen **[!UICONTROL Filter Methods]** innehåller: `POST`, `PUT`, `DELETE`.

## Hämta en mapplista {#retrieve-a-folder-listing}

Hämtar en siren-representation av en befintlig mapp och av dess underordnade enheter (undermappar eller resurser).

**Begäran**: `GET /api/assets/myFolder.json`

**Svarskoder**: Svarskoderna är:

* 200 - OK - framgång.
* 404 - HITTADES INTE - mappen finns inte eller är inte tillgänglig.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

**Svar**: Klassen för enheten som returneras är en resurs eller en mapp. Egenskaperna för enheter som ingår är en deluppsättning av alla egenskaper för varje enhet. För att få en fullständig representation av enheten bör kunderna hämta innehållet i den URL som länken pekar på med en `rel` av `self`.

## Skapa en mapp {#create-a-folder}

Skapar en ny `sling`: `OrderedFolder` vid den angivna sökvägen. Om en `*` anges i stället för ett nodnamn, används parameternamnet som nodnamn. Godkänt som begärandedata är antingen en Siren-representation av den nya mappen eller en uppsättning namn/värde-par, kodade som `application/www-form-urlencoded` eller `multipart`/ `form`- `data`, användbart när du vill skapa en mapp direkt från ett HTML-formulär. Dessutom kan mappens egenskaper anges som URL-frågeparametrar.

Ett API-anrop misslyckas med en `500` svarskod om den överordnade noden för den angivna sökvägen inte finns. Ett anrop returnerar en svarskod `409` om mappen redan finns.

**Parametrar**: `name` är mappnamnet.

**Begäran**

* `POST /api/assets/myFolder -H"Content-Type: application/json" -d '{"class":"assetFolder","properties":{"title":"My Folder"}}'`
* `POST /api/assets/* -F"name=myfolder" -F"title=My Folder"`

**Svarskoder**: Svarskoderna är:

* 201 - SKAPAD - när den skapades.
* 409 - CONFLICT - om mappen redan finns.
* 412 - PRECONDITION MISSLYCKADES - om rotsamlingen inte kan hittas eller nås.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

## Skapa en resurs {#create-an-asset}

Placera den angivna filen på den angivna sökvägen för att skapa en resurs i DAM-databasen. Om en `*` anges i stället för ett nodnamn, används parameternamnet eller filnamnet som nodnamn.

**Parametrar**: Parametrarna är `name` för resursnamnet och `file` för filreferensen.

**Begäran**

* `POST /api/assets/myFolder/myAsset.png -H"Content-Type: image/png" --data-binary "@myPicture.png"`
* `POST /api/assets/myFolder/* -F"name=myAsset.png" -F"file=@myPicture.png"`

**Svarskoder**: Svarskoderna är:

* 201 - SKAPAD - om resursen har skapats.
* 409 - CONFLICT - om tillgången redan finns.
* 412 - PRECONDITION MISSLYCKADES - om rotsamlingen inte kan hittas eller nås.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

## Uppdatera en resurbinär {#update-asset-binary}

Uppdaterar en resurs binärfil (återgivning med namnet original). En uppdatering utlöser standardarbetsflödet för resurshantering som körs, om det är konfigurerat.

**Begäran**: `PUT /api/assets/myfolder/myAsset.png -H"Content-Type: image/png" --data-binary @myPicture.png`

**Svarskoder**: Svarskoderna är:

* 200 - OK - Om resursen har uppdaterats utan fel.
* 404 - HITTADES INTE - Om det inte gick att hitta eller få åtkomst till resursen på angiven URI.
* 412 - PRECONDITION MISSLYCKADES - om rotsamlingen inte kan hittas eller nås.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

## Uppdatera metadata för resurs {#update-asset-metadata}

Uppdaterar egenskaperna för resursmetadata. Om du uppdaterar någon egenskap i `dc:` namnutrymme, uppdaterar API-gränssnittet samma egenskap i `jcr` namnutrymme. API:t synkroniserar inte egenskaperna under de två namnutrymmena.

**Begäran**: `PUT /api/assets/myfolder/myAsset.png -H"Content-Type: application/json" -d '{"class":"asset", "properties":{"jcr:title":"My Asset"}}'`

**Svarskoder**: Svarskoderna är:

* 200 - OK - Om resursen har uppdaterats utan fel.
* 404 - HITTADES INTE - Om det inte gick att hitta eller få åtkomst till resursen på angiven URI.
* 412 - PRECONDITION MISSLYCKADES - om rotsamlingen inte kan hittas eller nås.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

### Synkronisera metadatauppdatering mellan `dc` och `jcr` namespace {#sync-metadata-between-namespaces}

API-metoden uppdaterar metadataegenskaperna i `jcr` namnutrymme. Uppdateringarna som görs med Touch-UI ändrar metadataegenskaperna i `dc` namnutrymme. Synkronisera metadatavärdena mellan `dc` och `jcr` I kan du skapa ett arbetsflöde och konfigurera Experience Manager för att köra arbetsflödet när resursen redigeras. Använd ett ECMA-skript för att synkronisera de metadataegenskaper som krävs. Följande exempelskript synkroniserar titelsträngen mellan `dc:title` och `jcr:title`.

```javascript
var workflowData = workItem.getWorkflowData();
if (workflowData.getPayloadType() == "JCR_PATH")
{
 var path = workflowData.getPayload().toString();
 var node = workflowSession.getSession().getItem(path);
 var metadataNode = node.getNode("jcr:content/metadata");
 var jcrcontentNode = node.getNode("jcr:content");
if (jcrcontentNode.hasProperty("jcr:title"))
{
 var jcrTitle = jcrcontentNode.getProperty("jcr:title");
 metadataNode.setProperty("dc:title", jcrTitle.toString());
 metadataNode.save();
}
}
```

## Skapa en resursåtergivning {#create-an-asset-rendition}

Skapa en ny resursåtergivning för en resurs. Om parameternamnet för begäran inte anges används filnamnet som återgivningsnamn.

**Parametrar**: Parametrarna är `name` för renderingens namn och `file` som en filreferens.

**Begäran**

* `POST /api/assets/myfolder/myasset.png/renditions/web-rendition -H"Content-Type: image/png" --data-binary "@myRendition.png"`
* `POST /api/assets/myfolder/myasset.png/renditions/* -F"name=web-rendition" -F"file=@myRendition.png"`

**Svarskoder**: Svarskoderna är:

* 201 - SKAPAD - om återgivningen har skapats.
* 404 - HITTADES INTE - Om det inte gick att hitta eller få åtkomst till resursen på angiven URI.
* 412 - PRECONDITION MISSLYCKADES - om rotsamlingen inte kan hittas eller nås.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

## Uppdatera en resursåtergivning {#update-an-asset-rendition}

Uppdateringar ersätter en resursåtergivning med nya binära data.

**Begäran**: `PUT /api/assets/myfolder/myasset.png/renditions/myRendition.png -H"Content-Type: image/png" --data-binary @myRendition.png`

**Svarskoder**: Svarskoderna är:

* 200 - OK - Om återgivningen har uppdaterats.
* 404 - HITTADES INTE - Om det inte gick att hitta eller få åtkomst till resursen på angiven URI.
* 412 - PRECONDITION MISSLYCKADES - om rotsamlingen inte kan hittas eller nås.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

## Lägga till en kommentar till en resurs {#create-an-asset-comment}

Skapar en ny resurskommentar.

**Parametrar**: Parametrarna är `message` för kommentarens meddelandetext och `annotationData` för anteckningsdata i JSON-format.

**Begäran**: `POST /api/assets/myfolder/myasset.png/comments/* -F"message=Hello World." -F"annotationData={}"`

**Svarskoder**: Svarskoderna är:

* 201 - SKAPAD - om kommentaren har skapats.
* 404 - HITTADES INTE - Om det inte gick att hitta eller få åtkomst till resursen på angiven URI.
* 412 - PRECONDITION MISSLYCKADES - om rotsamlingen inte kan hittas eller nås.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

## Kopiera en mapp eller en resurs {#copy-a-folder-or-asset}

Kopierar en mapp eller resurs som är tillgänglig på den angivna sökvägen till ett nytt mål.

**Begäranrubriker**: Parametrarna är:

* `X-Destination` - en ny mål-URI inom API-lösningens omfång att kopiera resursen till.
* `X-Depth` - antingen `infinity` eller `0`. Använda `0` kopierar bara resursen och dess egenskaper och inte dess underordnade.
* `X-Overwrite` - Användning `F` för att förhindra att en resurs skrivs över på det befintliga målet.

**Begäran**: `COPY /api/assets/myFolder -H"X-Destination: /api/assets/myFolder-copy"`

**Svarskoder**: Svarskoderna är:

* 201 - SKAPAD - om mappen/resursen har kopierats till ett icke-befintligt mål.
* 204 - INGET INNEHÅLL - om mappen/resursen har kopierats till ett befintligt mål.
* 412 - PRECONDITION MISSLYCKADES - om ett begärandehuvud saknas.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

## Flytta en mapp eller en resurs {#move-a-folder-or-asset}

Flyttar en mapp eller resurs vid den angivna sökvägen till ett nytt mål.

**Begäranrubriker**: Parametrarna är:

* `X-Destination` - en ny mål-URI inom API-lösningens omfång att kopiera resursen till.
* `X-Depth` - antingen `infinity` eller `0`. Använda `0` kopierar bara resursen och dess egenskaper och inte dess underordnade.
* `X-Overwrite` - Använd antingen `T` för att tvinga bort befintliga resurser eller `F` för att förhindra att en befintlig resurs skrivs över.

**Begäran**: `MOVE /api/assets/myFolder -H"X-Destination: /api/assets/myFolder-moved"`

**Svarskoder**: Svarskoderna är:

* 201 - SKAPAD - om mappen/resursen har kopierats till ett icke-befintligt mål.
* 204 - INGET INNEHÅLL - om mappen/resursen har kopierats till ett befintligt mål.
* 412 - PRECONDITION MISSLYCKADES - om ett begärandehuvud saknas.
* 500 - INTERNT SERVERFEL - Om något annat går fel.

## Ta bort en mapp, en resurs eller en återgivning {#delete-a-folder-asset-or-rendition}

Tar bort en resurs (-tree) vid den angivna sökvägen.

**Begäran**

* `DELETE /api/assets/myFolder`
* `DELETE /api/assets/myFolder/myAsset.png`
* `DELETE /api/assets/myFolder/myAsset.png/renditions/original`

**Svarskoder**: Svarskoderna är:

* 200 - OK - Om mappen har tagits bort.
* 412 - PRECONDITION MISSLYCKADES - om rotsamlingen inte kan hittas eller nås.
* 500 - INTERNT SERVERFEL - Om något annat går fel.
