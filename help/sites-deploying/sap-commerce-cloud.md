---
title: SAP Commerce Cloud
seo-title: SAP Commerce Cloud
description: Lär er hur ni driftsätter e-handel med SAP Commerce Cloud.
seo-description: Learn how to deploy eCommerce with SAP Commerce Cloud.
uuid: a16ae42b-9c33-4da8-a130-52b72a779ec7
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: e-commerce
content-type: reference
discoiquuid: 44dfa10f-497e-473f-95d4-8dccae7ebf8e
pagetitle: Deploying eCommerce with SAP Commerce Cloud
feature: Commerce Integration Framework
exl-id: 71d0a249-8ad1-416e-ad78-d651b413e5c3
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '755'
ht-degree: 0%

---

# SAP Commerce Cloud{#sap-commerce-cloud}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>Den här sidan innehåller länkar till hybris webbplats. För vissa sidor behöver du ett konto för att logga in.

## Distribuera e-handel med SAP Commerce Cloud {#deploying-ecommerce-with-sap-commerce-cloud}

>[!NOTE]
>
>Följande procedurer använder följande demonstrationskatalog för att illustrera distributionen:
>
>`Geometrixx Outdoors Site English (US)`

Distribuera [nödvändiga e-handelspaket](#packages-needed-for-ecommerce-with-hybris) kommer att tillhandahålla e-handelsramverkets alla funktioner, tillsammans med en referensimplementering av e-handelsfunktionaliteten i enlighet med en hybris-implementering (inklusive en demonstrationskatalog),

Detta finns tillgängligt under den engelska (USA) grenen ( `/content/geometrixx-outdoors/en_US`) på Geometrixx Outdoors webbplats:

* [Produktinformation](#productinformationwithcolorvariants) (med färgvarianter när det är lämpligt)

* [Innehållsöversikter för kundvagn](#shoppingcartcontentoverview)
* [Kundregistrering](#customersignup) och [Kundinloggning](#customersignin)

* [Tillgång till hybris Management Console](#accesstothehybrismanagementconsole)

### Tekniska krav - hybris Server {#technical-requirements-hybris-server}

hybris-tillägget i eCommerce Integration Framework har uppdaterats för att stödja Hybris 5 (som standard), samtidigt som bakåtkompatibiliteten med [Hybris 4](/help/sites-developing/sap-commerce-cloud.md#developing-for-hybris).

>[!NOTE]
>
>* Stöder upp till hybris 6.4 med OCC version 2.
>* Du behöver Java 7 för att köra [hybris 5-server.](https://www.hybris.com/en/architecture-technology)
>* hybris-tillägget, [Telco Accelerator](https://www.hybris.com/en/products/telecommunication), stöds inte av AEM.
>


### Paket som behövs för e-handel med hybris {#packages-needed-for-ecommerce-with-hybris}

Så här installerar du e-handelsfunktioner:

* Din hybris-server
* AEM e-handelsramverk:

   * detta ingår i en AEM

* AEM Geometrixx-all-paket:

   * `cq-geometrixx-all-pkg`

* Innehållspaket AEM hybris:

   * `cq-hybris-content-6.3.2`
   * hybrisspecifik API-implementering
   * `cq-geometrixx-hybris-content-6.3.2`
   * en referensimplementering för att illustrera användningen av hybris ( `geometrixx-outdoors/en_US`)

### Installation av e-handel med hybris {#installation-of-ecommerce-with-hybris}

Så här installerar du en fullständig konfiguration (med demonstrationskatalogen Geometrixx Outdoors):

1. [Installera AEM](/help/sites-deploying/deploy.md).
1. Installera hela Geometrixx

   1. ` [cq-geometrixx-all-pkg](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq60/product/cq-geometrixx-all-pkg)`

1. Installera demonstrationsinnehållspaketen med [pakethanterare](/help/sites-administering/package-manager.md):

   1. ` [cq-hybris-content-6.3.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/cq-hybris-content)`
   1. ` [cq-geometrixx-hybris-content-6.3.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq630/product/cq-geometrixx-hybris-content)`

1. [Ladda ned och bygg upp hybris Server](#download-and-build-your-hybris-server).
1. Skapa din katalog i din e-handelsmotor:

   1. [Ställ in Geometrixx utomhusbutik](#setup-the-geometrixx-outdoors-store).

1. [Upphovsman](/help/sites-authoring/qg-page-authoring.md) eventuella tilläggssidor som du behöver i AEM.

>[!CAUTION]
>
>Användning av hybris-servern kräver en separat hybris-licens.

>[!NOTE]
>
>För utvecklare [API-dokumentation](/help/sites-developing/ecommerce.md#api-documentation) finns också för nedladdning.

### Ladda ned och bygg en hybris-server {#download-and-build-your-hybris-server}

Stegen i den här proceduren hämtar och bygger hybris-servern. Den kommer också att göra de initiala konfigurationer som krävs för kopplingarna mellan hybris och cq. Tillägget kan sedan användas med standardinställningarna.

>[!CAUTION]
>
>Hybriversioner tidigare än 5.5.1 stöds inte.

>[!NOTE]
>
>Du måste [Groovy](https://groovy-lang.org/) installerade på datorn.

1. Ladda ned **hybris Commerce Suite** distribution från hybris nedladdningssajt.

   >[!CAUTION]
   >
   >Du behöver ett konto (från hybris) för att få tillgång till detta.

1. Zippa upp distributionsfilen på önskad plats (kallas &lt;hybris-root-directory>).
1. Kör följande från kommandoraden:

   ```shell
   cd <hybris-root-directory>/bin/platform
   . ./setantenv.sh
   ant clean all 
   cd ../..
   ```

   >[!NOTE]
   >
   >Vid körning:
   >
   >`ant clean all`
   >
   >Tryck `Return` vid behov.

1. Ladda ned följande filer till rotmappen för din extraherade hybris-distribution,

   ```
       <hybris-root-directory>
   ```


[Hämta fil](assets/setup.groovy)

   >[!NOTE]
   >
   >För hybris 5.6.0 och senare, använd följande setup.groovy.

   5.6.0 och senare

[Hämta fil](assets/setup-1.groovy)

1. Kör följande från kommandoraden till:

   * uppdatera hybris-serverns konfiguration (som krävs av tillägget)
   * återskapa hybris-servern med den ändrade konfigurationen
   * starta servern

   ```shell
   groovy setup.groovy
   cd bin/platform
   ant clean all
   sh hybrisserver.sh
   ```

   >[!NOTE]
   >
   >Beroende på ditt system kan flera av dessa åtgärder ta flera minuter att slutföra.

1. I webbläsaren går du till **Administrationskonsol för hybris** vid:

   [http://localhost:9002](http://localhost:9002)

1. Klicka **Initiera** och bekräfta sedan initieringsåtgärden (eftersom den tar bort befintliga data).

   Förloppet visas på konsolen med `FINISHED` som anger att åtgärden har slutförts.

   >[!NOTE]
   >
   >Beroende på ditt system kan det ta flera minuter att slutföra detta.

### Konfigurera Geometrixx Outdoors Store {#setup-the-geometrixx-outdoors-store}

Den här proceduren överför och konfigurerar demonstrationsbutiken - Geometrixx Online.

1. Starta hybris-instansen. Kör följande från kommandoraden:

   ```shell
   cd <hybris-root-directory>/bin/platform
   sh hybrisserver.sh
   ```

1. I webbläsaren går du till **Hanteringskonsol för hybris** vid:

   [http://localhost:9002/hmc/hybris](http://localhost:9002/hmc/hybris)

1. Från sidofältsnavigeringen kan du utforska **System** och **verktyg**. Välj sedan **Importera** för att öppna **Guide: CSV-import** -fönstret.
1. I **Konfiguration** tab, **Överför** följande **Importera fil**:

[Hämta fil](assets/geometrixx-outdoors-export.csv)

1. Ange **Språkinställning** till:

   `en_US - English (United States)`

1. Öppna **Resurser** -fliken.
1. **Överför** följande **Media-Zip**:

[Hämta fil](assets/geometrixx-outdoors-images.zip)

1. Klicka **Starta** om du vill importera de angivna filerna. The **Resultat** kommer att visa loggposter.

1. Klicka **Klar** för att stänga importfönstret.

1. Välj **System** sedan **verktyg** sedan **Importera**.

1. **Överför** följande **Importera fil**:

[Hämta fil](assets/base-store.csv)

   För hybris 5.7, använd följande:

[Hämta fil](assets/base-store-5_7.csv)

1. Ange **Språkinställning** till:

   `en_US - English (United States)`

1. Klicka **Starta** om du vill importera de angivna filerna. The **Resultat** kommer att visa loggposter.

1. Klicka **Klar** för att stänga importfönstret.

1. Nu kan du använda produktcockpit för att visa de importerade katalogerna och produkterna:

   [http://localhost:9002/productcockpit](http://localhost:9002/productcockpit)
