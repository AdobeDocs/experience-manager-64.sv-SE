---
title: Konfigurera lagringstjänster för utkast och överföringar
seo-title: Configuring storage services for drafts and submissions
description: Lär dig hur du konfigurerar lagring för utkast och överföringar
seo-description: Learn how to configure storage for drafts and submissions
uuid: 2f4efc07-312c-4908-8c91-84f4e6c5ad25
topic-tags: publish
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 6ebb6420-68b6-4abc-b298-c252db038416
exl-id: c73fd1c5-6f3f-4c62-a8d6-fcd22f02c0ca
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '567'
ht-degree: 0%

---

# Konfigurera lagringstjänster för utkast och överföringar {#configuring-storage-services-for-drafts-and-submissions}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Med AEM Forms kan du lagra:

* **Utkast**: Ett pågående formulär som slutanvändarna fyller i och sparar för senare och skickar därefter.

* **Inlämningar**: Skickade formulär som innehåller användardata.

AEM Forms portaldata och metadatatjänster har stöd för utkast och inlämning. Som standard lagras data i publiceringsinstansen, som sedan återreplikeras till den konfigurerade författarinstansen så att den blir tillgänglig för körning till andra publiceringsinstanser.

Problemet med den befintliga användningsklara metoden är att den lagrar alla data i publiceringsinstansen, inklusive data som kan vara personligt identifierbar information (PII).

Utöver det ovan nämnda standardtillvägagångssättet finns det även en alternativ implementering för att direkt överföra formulärdata till bearbetning i stället för att spara dem lokalt. Kunder som oroar sig för lagring av potentiellt känsliga data på en publiceringsinstans kan välja den alternativa implementering som data skickas till en bearbetningsserver. Eftersom bearbetningen sker på författarinstansen ligger den vanligtvis kvar i en säker zon.

>[!NOTE]
>
>När du använder Forms Portal-åtgärden för att skicka eller aktiverar alternativet Lagra data i formulärportalen i anpassad form, lagras formulärdata i AEM. I en produktionsmiljö bör du inte lagra utkast eller skickade formulärdata i AEM. Istället måste ni integrera utkasten och skicka-komponenten med en säker lagringsplats, t.ex. en företagsdatabas, för att lagra utkast och skickade formulärdata.
>
>Mer information finns i [Exempel för att integrera komponent för utkast och inlämning med databas](/help/forms/using/integrate-draft-submission-database.md).

## Konfigurera Forms Portal-utkast och inskickningstjänster {#configuring-forms-portal-drafts-and-submissions-services}

I AEM webbkonsolkonfiguration ( `https://[*host*]:[*port*]/system/console/configMgr`), klicka för att öppna **Utkastskonfiguration för Forms Portal** i redigeringsläge.

Ange värden för egenskaper baserat på dina krav enligt beskrivningen nedan:

### Körklara tjänster för lagring av data i publiceringsinstansen {#out-of-the-box-services-to-store-data-on-publish-instance}

Data replikeras omvänt till den konfigurerade författarinstansen.

<table> 
 <tbody>
  <tr>
   <th>Egenskap</th> 
   <th>Värde</th> 
  </tr>
  <tr>
   <td>Forms Portal Draft Data Service(Identifierare för Project Data Service)<strong>draft.data.service</strong>))</td> 
   <td>com.adobe.fd.fp.service.impl.DraftDataServiceImpl<br /> </td> 
  </tr>
  <tr>
   <td>Forms Portal Draft Metadata Service (identifierare för utkast till metadatatjänst)<strong>draft.metadata.service</strong>))</td> 
   <td>com.adobe.fd.fp.service.impl.DraftMetadataServiceImpl<br /> </td> 
  </tr>
  <tr>
   <td>Forms Portal Submit Data Service (identifierare för Skicka data Service) (<strong>submit.data.service</strong>))</td> 
   <td>com.adobe.fd.fp.service.impl.SubmitDataServiceImpl<br /> </td> 
  </tr>
  <tr>
   <td>Forms Portal Submit Metadata Service (identifierare för Skicka metadata) (<strong>submit.metadata.service</strong>))</td> 
   <td>com.adobe.fd.fp.service.impl.SubmitMetadataServiceImpl<br /> </td> 
  </tr>
 </tbody>
</table>

### Utgångstjänster för lagring av data på fjärrbearbetningsinstansen {#out-of-the-box-services-to-store-data-on-remote-processing-instance}

Data skickas direkt till den konfigurerade fjärrinstansen

<table> 
 <tbody>
  <tr>
   <th>Egenskap</th> 
   <th>Värde</th> 
  </tr>
  <tr>
   <td>Forms Portal Draft Data Service(Identifierare för Project Data Service)<strong>draft.data.service</strong>))</td> 
   <td>com.adobe.fd.fp.service.impl.DraftDataServiceRemoteImpl<br /> </td> 
  </tr>
  <tr>
   <td>Forms Portal Draft Metadata Service (identifierare för utkast till metadatatjänst)<strong>draft.metadata.service</strong>))</td> 
   <td>com.adobe.fd.fp.service.impl.DraftMetadataServiceRemoteImpl<br /> </td> 
  </tr>
  <tr>
   <td>Forms Portal Submit Data Service (identifierare för Skicka data Service) (<strong>submit.data.service</strong>))</td> 
   <td>com.adobe.fd.fp.service.impl.SubmitDataServiceRemoteImpl<br /> </td> 
  </tr>
  <tr>
   <td>Forms Portal Submit Metadata Service (identifierare för Skicka metadata) (<strong>submit.metadata.service</strong>))</td> 
   <td>com.adobe.fd.fp.service.impl.SubmitMetadataServiceRemoteImpl<br /> </td> 
  </tr>
 </tbody>
</table>

Förutom konfigurationen ovan anger du information om den konfigurerade fjärrbearbetningsinstansen.

I AEM webbkonsolkonfiguration ( `https://[*host*]:[*port*]/system/console/configMgr`), klicka för att öppna **Tjänsten AEM DS-inställningar** i redigeringsläge. I dialogrutan AEM DS-inställningstjänst anger du information om bearbetning av server-URL, användarnamn för bearbetning av server och lösenord.

>[!NOTE]
>
>Ett exempel på implementering finns också för lagring av användardata i en databas. Mer information om hur du konfigurerar data- och metadatatjänster för att lagra användardata i en extern databas finns i [Exempel för att integrera komponent för utkast och inlämning med databas](/help/forms/using/integrate-draft-submission-database.md).
