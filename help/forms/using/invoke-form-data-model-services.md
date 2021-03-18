---
title: API för att anropa formulärdatamodelltjänst från anpassningsbara formulär
seo-title: API för att anropa formulärdatamodelltjänst från anpassningsbara formulär
description: 'Beskriver det invokeWebServices-API som du kan använda för att anropa webbtjänster som skrivits i WSDL inifrån ett adaptivt formulärfält. '
seo-description: 'Beskriver det invokeWebServices-API som du kan använda för att anropa webbtjänster som skrivits i WSDL inifrån ett adaptivt formulärfält. '
uuid: 40561086-e69d-4e6a-9543-1eb2f54cd836
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: aa3e50f1-8f5a-489d-a42e-a928e437ab79
feature: Adaptiv Forms
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '384'
ht-degree: 1%

---


# API för att anropa formulärdatamodelltjänst från adaptiva formulär {#api-to-invoke-form-data-model-service-from-adaptive-forms}

## Översikt {#overview}

Med AEM Forms kan formulärförfattare ytterligare förenkla och förbättra ifyllandet av formulär genom att anropa tjänster som konfigurerats i en formulärdatamodell inifrån ett adaptivt formulärfält. Om du vill anropa en datamodelltjänst kan du antingen skapa en regel i den visuella redigeraren eller ange ett JavaScript med hjälp av API:t `guidelib.dataIntegrationUtils.executeOperation` i kodredigeraren för [regelredigeraren](/help/forms/using/rule-editor.md).

Det här dokumentet fokuserar på att skriva ett JavaScript med hjälp av `guidelib.dataIntegrationUtils.executeOperation`-API:t för att anropa en tjänst.

## Använda API {#using-the-api}

API:t `guidelib.dataIntegrationUtils.executeOperation` anropar en tjänst från ett adaptivt formulärfält. API-syntaxen är följande:

```
guidelib.dataIntegrationUtils.executeOperation(operationInfo, inputs, outputs)
```

API kräver följande parametrar.

| Parameter | Beskrivning |
|---|---|
| `operationInfo` | Struktur för att ange identifierare för formulärdatamodell, åtgärdstitel och åtgärdsnamn |
| `inputs` | Struktur för att ange formulärobjekt vars värden är indata till serviceåtgärden |
| `outputs` | Struktur för att ange formulärobjekt som ska fyllas med värden som returneras av tjänståtgärden |

Strukturen för API:t `guidelib.dataIntegrationUtils.executeOperation` anger information om tjänståtgärden. Strukturen har följande syntax.

```
var operationInfo = {
formDataModelId,
operationTitle,
operationName
};
var inputs = {
inputField1,
inputFieldN
};
var outputs = {
outputField1,
outputFieldN
}
```

API-strukturen anger följande information om tjänståtgärden.

<table> 
 <tbody> 
  <tr> 
   <th>Parameter</th> 
   <th>Beskrivning</th> 
  </tr> 
  <tr> 
   <td><code>forDataModelId</code></td> 
   <td>Ange databassökvägen till formulärdatamodellen inklusive dess namn</td> 
  </tr> 
  <tr> 
   <td><code>operationName</code></td> 
   <td>Ange namnet på den tjänståtgärd som ska köras</td> 
  </tr> 
  <tr> 
   <td><code>input</code></td> 
   <td>Mappa ett eller flera formulärobjekt till indataargumenten för serviceåtgärden</td> 
  </tr> 
  <tr> 
   <td>Utdata</td> 
   <td>Mappa ett eller flera formulärobjekt till utdatavärden från tjänståtgärden för att fylla i formulärfält<br /> </td> 
  </tr> 
 </tbody> 
</table>

## Exempelskript för att anropa en tjänst {#sample-script-to-invoke-a-service}

Följande exempelskript använder API:t `guidelib.dataIntegrationUtils.executeOperation` för att anropa den `getAccountById`-tjänståtgärd som konfigurerats i formulärdatamodellen `employeeAccount`.

Åtgärden `getAccountById` tar värdet i formulärfältet `employeeID` som indata för argumentet `empId` och returnerar medarbetarens namn, kontonummer och kontosaldo för motsvarande medarbetare. Utdatavärdena fylls i i de angivna formulärfälten. Värdet i argumentet `name` fylls till exempel i i formulärelementet `fullName` och värdet för argumentet `accountNumber` i formulärelementet `account`.

```
var operationInfo = {
"formDataModelId": "/content/dam/formsanddocuments-fdm/employeeAccount",
"operationName": "getAccountDetails"
};
var inputs = {
"empid" : employeeID
};
var outputs = {
"name" : fullName,
"accountNumber" : account,
"balance" : balance
};
guidelib.dataIntegrationUtils.executeOperation(operationInfo, inputs, outputs);
```

