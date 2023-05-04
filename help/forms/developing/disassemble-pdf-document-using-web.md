---
title: Dela upp ett PDF-dokument med hjälp av webbtjänstens API
seo-title: Disassemble a PDF document usingthe web service API
description: Dela upp ett PDF-dokument med Assembler Service API
seo-description: Disassemble a PDF document using the Assembler Service API
uuid: d6283dc5-e333-49d0-abde-1d390662f4fe
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/programmatically_disassembling_pdf_documents
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 49584fb4-8c3a-4d73-acd6-0879a67f6093
role: Developer
exl-id: ea6a05ff-d8d8-4a4f-b1aa-e09670e40ba7
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '740'
ht-degree: 0%

---

# Dela upp ett PDF-dokument med hjälp av webbtjänstens API {#disassemble-a-pdf-document-usingthe-web-service-api}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Dela upp ett PDF-dokument med Assembler Service API (webbtjänst):

1. Inkludera projektfiler.

   Skapa ett Microsoft .NET-projekt som använder MTOM. Kontrollera att du använder följande WSDL-definition när du anger en tjänstreferens: `http://localhost:8080/soap/services/AssemblerService?WSDL&lc_version=9.0.1`.

   >[!NOTE]
   >
   >Ersätt `localhost` med IP-adressen till den server som är värd för AEM Forms.

1. Skapa en PDF Assembler-klient.

   * Skapa en `AssemblerServiceClient` genom att använda dess standardkonstruktor.
   * Skapa en `AssemblerServiceClient.Endpoint.Address` genom att använda `System.ServiceModel.EndpointAddress` konstruktor. Skicka ett strängvärde som anger WSDL till AEM Forms-tjänsten (till exempel `http://localhost:8080/soap/services/AssemblerService?blob=mtom`). Du behöver inte använda `lc_version` -attribut. Det här attributet används när du skapar en tjänstreferens.
   * Skapa en `System.ServiceModel.BasicHttpBinding` genom att hämta värdet för `AssemblerServiceClient.Endpoint.Binding` fält. Sänd returvärdet till `BasicHttpBinding`.
   * Ange `System.ServiceModel.BasicHttpBinding` objektets `MessageEncoding` fält till `WSMessageEncoding.Mtom`. Detta värde garanterar att MTOM används.
   * Aktivera grundläggande HTTP-autentisering genom att utföra följande åtgärder:

      * Tilldela AEM formuläranvändarnamn till fältet `AssemblerServiceClient.ClientCredentials.UserName.UserName`.
      * Tilldela motsvarande lösenordsvärde till fältet `AssemblerServiceClient.ClientCredentials.UserName.Password`.
      * Tilldela konstantvärdet `HttpClientCredentialType.Basic` till fältet `BasicHttpBindingSecurity.Transport.ClientCredentialType`.
      * Tilldela konstantvärdet `BasicHttpSecurityMode.TransportCredentialOnly` till fältet `BasicHttpBindingSecurity.Security.Mode`.

1. Referera till ett befintligt DDX-dokument.

   * Skapa en `BLOB` genom att använda dess konstruktor. The `BLOB` -objektet används för att lagra DDX-dokumentet.
   * Skapa en `System.IO.FileStream` genom att anropa dess konstruktor. Skicka ett strängvärde som representerar filplatsen för DDX-dokumentet och läget som filen ska öppnas i.
   * Skapa en bytearray som lagrar innehållet i `System.IO.FileStream` -objekt. Du kan bestämma storleken på bytearrayen genom att hämta `System.IO.FileStream` objektets `Length` -egenskap.
   * Fylla i bytearrayen med strömdata genom att anropa `System.IO.FileStream` objektets `Read` och skickar bytearrayen, startpositionen och den flödeslängd som ska läsas.
   * Fyll i `BLOB` genom att tilldela `MTOM` med bytearrayens innehåll.

1. Referera ett PDF-dokument som ska demonteras.

   * Skapa en `BLOB` genom att använda dess konstruktor. The `BLOB` -objektet används för att lagra indatadokumentet i PDF. Detta `BLOB` objektet skickas till `invokeOneDocument` som ett argument.
   * Skapa en `System.IO.FileStream` genom att anropa dess konstruktor och skicka ett strängvärde som representerar filplatsen för indata-PDF-dokumentet och läget som filen ska öppnas i.
   * Skapa en bytearray som lagrar innehållet i `System.IO.FileStream` -objekt. Du kan bestämma storleken på bytearrayen genom att hämta `System.IO.FileStream` objektets `Length` -egenskap.
   * Fylla i bytearrayen med strömdata genom att anropa `System.IO.FileStream` objektets `Read` och skickar bytearrayen, startpositionen och den flödeslängd som ska läsas.
   * Fyll i `BLOB` genom att tilldela `MTOM` fält innehållet i bytearrayen.
   * Skapa en `MyMapOf_xsd_string_To_xsd_anyType` -objekt. Samlingsobjektet används för att lagra PDF som ska demonteras.
   * Skapa en `MyMapOf_xsd_string_To_xsd_anyType_Item` -objekt.
   * Tilldela ett strängvärde som representerar nyckelnamnet till `MyMapOf_xsd_string_To_xsd_anyType_Item` objektets `key` fält. Detta värde måste matcha värdet för källelementet PDF som anges i DDX-dokumentet.
   * Tilldela `BLOB` objekt som lagrar PDF-dokumentet till `MyMapOf_xsd_string_To_xsd_anyType_Item` objektets `value` fält.
   * Lägg till `MyMapOf_xsd_string_To_xsd_anyType_Item` objekt till `MyMapOf_xsd_string_To_xsd_anyType` -objekt. Anropa `MyMapOf_xsd_string_To_xsd_anyType` object&quot; `Add` och skicka `MyMapOf_xsd_string_To_xsd_anyType` -objekt.

1. Ange körningsalternativ.

   * Skapa en `AssemblerOptionSpec` objekt som lagrar körningsalternativ med hjälp av dess konstruktor.
   * Ange körningsalternativ som uppfyller dina affärskrav genom att tilldela ett värde till en datamedlem som tillhör `AssemblerOptionSpec` -objekt. Om du till exempel vill instruera Assembler-tjänsten att fortsätta bearbeta ett jobb när ett fel inträffar tilldelar du `false` till `AssemblerOptionSpec` objektets `failOnError` fält.

1. Dela upp PDF-dokumentet.

   Anropa `AssemblerServiceClient` objektets `invokeDDX` och skicka följande värden:

   * A `BLOB` det objekt som representerar DDX-dokumentet som demonterar PDF-dokumentet
   * The `MyMapOf_xsd_string_To_xsd_anyType` objekt som innehåller det PDF-dokument som ska demonteras
   * An `AssemblerOptionSpec` objekt som anger körningsalternativ

   The `invokeDDX` returnerar en `AssemblerResult` objekt som innehåller jobbresultaten och eventuella undantag som inträffade.

1. Spara de upplösta PDF-dokumenten.

   Gör så här för att hämta de nya PDF-dokumenten:

   * Öppna `AssemblerResult` objektets `documents` fält, vilket är ett `Map` objekt som innehåller de uppdelade PDF-dokumenten.
   * Iterera genom `Map` -objekt för att hämta varje resulterande dokument. Sedan måste du byta ut den arraymedlemmens `value` till `BLOB`.
   * Extrahera de binära data som representerar PDF-dokumentet genom att öppna dess `BLOB` objektets `MTOM` -egenskap. Detta returnerar en array med byte som du kan skriva ut till en PDF-fil.

**Se även**

[Dela upp PDF-dokument programmatiskt](/help/forms/developing/programmatically-disassembling-pdf-documents.md#programmatically-disassembling-pdf-documents)

[Anropa AEM Forms med MTOM](/help/forms/developing/invoking-aem-forms-using-web.md#invoking-aem-forms-using-mtom)
