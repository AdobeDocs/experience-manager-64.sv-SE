---
title: Anpassa spårning av formulärhändelser
seo-title: Customizing form event tracking
description: Om en användare spenderar mer än 60 sekunder på ett fält utlöses en fältbesökshändelse och informationen om fältet skickas till Adobe SiteCatalyst.
seo-description: If a user spends more than 60 seconds on a field, a fieldvisit event is triggered and the details of the field are sent to Adobe SiteCatalyst.
uuid: 2f790085-2f1a-45be-9a69-6100c76dcae0
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
discoiquuid: 60d67c6b-5994-42ef-b159-ed6edf5cf9d4
exl-id: e07adddb-e904-4a80-9b1c-8028b12c0e37
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 0%

---

# Anpassa spårning av formulärhändelser {#customizing-form-event-tracking}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Följande händelser spåras automatiskt i en analysaktiverad Adaptiv form:

<table> 
 <tbody> 
  <tr> 
   <th>Händelse</th> 
   <th>Tillgängliga variabler</th> 
  </tr> 
  <tr> 
   <td>återge</td> 
   <td>formName, formTitle, formInstance, källa</td> 
  </tr> 
  <tr> 
   <td>överge</td> 
   <td>formName, formTitle, formInstance, panelName, panelTitle</td> 
  </tr> 
  <tr> 
   <td>spara</td> 
   <td>formName, formTitle, formInstance, panelName, source</td> 
  </tr> 
  <tr> 
   <td>skicka</td> 
   <td>formName, formTitle, formInstance, källa</td> 
  </tr> 
  <tr> 
   <td>fel</td> 
   <td>formName, formTitle, fieldName, fieldTitle, panelTitle</td> 
  </tr> 
  <tr> 
   <td>help</td> 
   <td>formName, formTitle, fieldName, fieldTitle, panelTitle</td> 
  </tr> 
  <tr> 
   <td>fieldVisit</td> 
   <td>formName, formTitle, fieldName, fieldTitle, panelTitle<br /> </td> 
  </tr> 
  <tr> 
   <td>panelBesök</td> 
   <td>formName, formTitle, panelName, panelTitle</td> 
  </tr> 
 </tbody> 
</table>

## Anpassa tidsgränsen för fältbesökshändelser {#customizing-the-field-visit-event-timeout}

Om en användare tillbringar mer än 60 sekunder på ett fält AEM standardinställningen är `fieldvisit` -händelsen utlöses och informationen om fältet skickas till Adobe Analytics. Du kan anpassa baslinjen för spårning av fälttid under Konfiguration av AEM Forms Analytics på AEM Configuration Console (/system/console/configMgr) för att öka eller minska tidsgränsen.

## Anpassa spårningshändelser {#customizing-the-tracking-events}

Du kan ändra `trackEvent`funktion finns i `/libs/afanalytics/js/custom.js` fil för att anpassa händelsespårningen. När en händelse som spåras inträffar i en adaptiv form är `trackEvent`funktionen anropas. The `trackEvent` funktionen accepterar två parametrar: `eventName`och `variableValueMap`.

Du kan utvärdera värdet för *eventName *och *variableValueMap* argument för att ändra spårningsbeteendet för händelser. Du kan till exempel välja att skicka informationen till analysservern efter att ett visst antal felhändelser har inträffat. Du kan även välja att utföra någon av följande anpassningar:

* Du kan ange en tröskeltid innan du skickar händelsen.
* Du kan behålla ett läge för att bestämma åtgärd, till exempel *fieldVisit* överför en dummy-händelse baserat på tidsstämpeln för den senaste händelsen.
* Du kan använda `pushEvent` funktion som skickar händelsen till analysservern *.*

* Du kan välja att inte skicka händelsen till analysservern alls.

### Exempel {#sample}

I följande exempel är läget för *fel* händelse för varje *fieldName *attribut bevaras*. *Händelsen skickas bara till analysservern om ett fel inträffar igen.

```
case 'error':
        if(errorOccurred[variableValueMap.fieldName] == true) {
            pushEvent(eventName, variableValueMap)
        }
        errorOccurred[variableValueMap.fieldName] = true;
        break;
```

## Anpassa panelbesökshändelsen {#customizing-the-panelvisit-event}

I standardinställningen för AEM Forms kontrolleras det efter var 60:e sekund om fönstret som innehåller det adaptiva formuläret är aktivt. Om fönstret är aktivt visas en `panelVisit`-händelsen utlöses för Adobe Analytics. Det hjälper till att kontrollera att dokumentet eller formuläret är aktivt och beräknar hur lång tid som har ägnats åt motsvarande formulär eller dokument.

>[!NOTE]
>
>Händelsenamnet som används för att bevara aktivitet och beräkna hur lång tid som har ägnats åt är &quot;panelVisit&quot;. Den här händelsen skiljer sig från panelbesökshändelsen som listas i tabellen ovan.

Du kan ändra funktionen scheduleHeartBeatCheck som finns i `/libs/afanalytics/js/custom.js` om du vill ändra eller stoppa den här händelsen som skickas till Adobe Analytics med ett regelbundet intervall.
