---
title: Konfigurera datakällor
seo-title: Konfigurera datakällor
description: Lär dig hur du konfigurerar olika typer av datakällor och använder dem för att skapa formulärdatamodeller.
seo-description: Lär dig hur du konfigurerar olika typer av datakällor och använder dem för att skapa formulärdatamodeller.
uuid: 292217c2-8110-4232-a78b-edea212765d2
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: integration
discoiquuid: 1dafd400-16c0-416d-9e81-7bf53b761f98
translation-type: tm+mt
source-git-commit: d0bb877bb6a502ad0131e4f1a7e399caa474a7c9
workflow-type: tm+mt
source-wordcount: '1236'
ht-degree: 0%

---


# Konfigurera datakällor {#configure-data-sources}

Lär dig hur du konfigurerar olika typer av datakällor och använder dem för att skapa formulärdatamodeller.

![](do-not-localize/data-integeration.png)

Med dataintegrering i AEM Forms kan du konfigurera och ansluta till olika datakällor. Följande typer stöds inte. Men med liten anpassning kan ni också integrera andra datakällor.

* Relationsdatabaser - MySQL, Microsoft SQL Server, IBM DB2 och Oracle RDBMS
* AEM-användarprofil
* RESTful web services
* SOAP-baserade webbtjänster
* OData-tjänster

Dataintegrering har stöd för autentiseringstyperna OAuth2.0, Grundläggande autentisering och API Key som är färdiga och tillåter implementering av anpassad autentisering för åtkomst till webbtjänster. Medan RESTful, SOAP-baserade tjänster och OData-tjänster är konfigurerade i AEM Cloud Services, konfigureras JDBC för relationsdatabaser och koppling för AEM-användarprofiler i AEM-webbkonsolen.

## Konfigurera relationsdatabas {#configure-relational-database}

Du kan konfigurera relationsdatabaser med hjälp av AEM Web Console Configuration. Gör följande:

1. Gå till AEM-webbkonsolen på `https://[server]:[host]/system/console/configMgr`.
1. Leta efter **[!UICONTROL Apache Sling Connection Pooled DataSource]** konfiguration. Tryck för att öppna konfigurationen i redigeringsläge.
1. I konfigurationsdialogrutan anger du information för den databas som du vill konfigurera, till exempel:

   * Datakällans namn
   * Egenskapen för datakälltjänst som lagrar datakällans namn
   * Java-klassnamn för JDBC-drivrutinen
   * URI för JDBC-anslutning
   * Användarnamn och lösenord för anslutning till JDBC-drivrutinen
   >[!NOTE] {grayBox=&quot;true&quot;}
   >
   >Kontrollera att du krypterar känslig information, t.ex. lösenord, innan du konfigurerar datakällan. Så här krypterar du:
   >
   >1. Gå till `https://[server]:[port]/system/console/crypto`.
   >1. I **[!UICONTROL Plain Text]** fältet anger du lösenordet eller en valfri sträng som ska krypteras och klickar på **[!UICONTROL Protect]**.
   >
   >Den krypterade texten visas i fältet Skyddad text som du kan ange i konfigurationen.

1. Aktivera **[!UICONTROL Test on Borrow]** eller **[!UICONTROL Test on Return]** ange att objekten valideras innan de lånas eller returneras från respektive till poolen.
1. Ange en SELECT-fråga (SQL) i **[!UICONTROL Validation Query]** fältet för att validera anslutningar från poolen. Frågan måste returnera minst en rad. Baserat på din databas anger du något av följande:

   * SELECT 1 (MySQL och MS SQL)
   * SELECT 1 from dual (Oracle)

1. Tryck **[!UICONTROL Save]** för att spara konfigurationen.

## Konfigurera AEM-användarprofil {#configure-aem-user-profile}

Du kan konfigurera AEM-användarprofilen med hjälp av konfigurationen för anslutning av användarprofil i AEM Web Console. Gör följande:

1. Gå till AEM-webbkonsolen på `https://[server]:[host]/system/console/configMgr`.
1. Leta efter **[!UICONTROL AEM Forms Data Integrations - User Profile Connector Configuration]** och tryck för att öppna konfigurationen i redigeringsläge.
1. I dialogrutan Konfiguration av anslutning till användarprofil kan du lägga till, ta bort eller uppdatera egenskaper för användarprofiler. De angivna egenskaperna kommer att vara tillgängliga för användning i formulärdatamodellen. Använd följande format för att ange egenskaper för användarprofiler:

   `name=[property_name_with_location_in_user_profile],type=[property_type]`

   Exempel:

   * `name=profile/phoneNumber,type=string`
   * `name=profile/empLocation/*/city,type=string`
   >[!NOTE] {grayBox=&quot;true&quot;}
   >
   >The **&amp;ast;** i ovanstående exempel betecknar alla noder under `profile/empLocation/` noden i AEM-användarprofilen i CRXDE-strukturen. Det innebär att formulärdatamodellen kan komma åt den `city` egenskap av typen som `string` finns i en nod under `profile/empLocation/` noden. Noderna som innehåller den angivna egenskapen måste dock följa en konsekvent struktur.

1. Tryck **[!UICONTROL Save]** för att spara konfigurationen.

## Konfigurera mapp för molntjänstkonfigurationer {#cloud-folder}

>[!NOTE]
>
>Konfiguration för molntjänstmappen krävs för konfigurering av molntjänster för RESTful-, SOAP- och OData-tjänster.

Alla molntjänstkonfigurationer i AEM konsolideras i mappen `/conf` i AEM-databasen. Mappen innehåller som standard den `conf` mapp där du kan skapa molntjänstkonfigurationer `global` . Du måste dock manuellt aktivera den för molnkonfigurationer. Du kan också skapa ytterligare mappar i `conf` för att skapa och organisera molntjänstkonfigurationer.

Så här konfigurerar du mappen för molntjänstkonfigurationer:

1. Gå till **[!UICONTROL Tools > General > Configuration Browser]**.
1. Gör följande för att aktivera den globala mappen för molnkonfigurationer eller hoppa över det här steget för att skapa och konfigurera en annan mapp för molntjänstkonfigurationer.

   1. I **[!UICONTROL Configuration Browser]** markerar du `global` mappen och trycker på **[!UICONTROL Properties]**.
   1. In the **[!UICONTROL Configuration Properties]** dialog, enable **[!UICONTROL Cloud Configurations]**.
   1. Tryck för **[!UICONTROL Save & Close]** att spara konfigurationen och stänga dialogrutan.

1. In the **[!UICONTROL Configuration Browser]**, tap **[!UICONTROL Create]**.
1. I **[!UICONTROL Create Configuration]** dialogrutan anger du en rubrik för mappen och aktiverar **[!UICONTROL Cloud Configurations]**.
1. Tryck för **[!UICONTROL Create]** att skapa mappen som är aktiverad för molntjänstkonfigurationer.

## Konfigurera RESTful-webbtjänster {#configure-restful-web-services}

RESTful-webbtjänsten kan beskrivas med [Swagger-specifikationer](https://swagger.io/specification/) i JSON- eller YAML-format i en Swagger-definitionsfil. Om du vill konfigurera RESTful-webbtjänsten i AEM-molntjänster måste du ha antingen Swagger-filen i filsystemet eller URL:en där filen finns.

Gör följande för att konfigurera RESTful-tjänster:

1. Gå till **[!UICONTROL Tools > Cloud Services > Data Sources]**. Tryck för att välja den mapp där du vill skapa en molnkonfiguration.

   Mer information om hur du skapar och konfigurerar en mapp för molntjänstkonfigurationer finns i [Konfigurera mapp för molntjänstkonfigurationer](/help/forms/using/configure-data-sources.md#cloud-folder) .

1. Tryck **[!UICONTROL Create]** för att öppna **[!UICONTROL Create Data Source Configuration dialog]**. Ange ett namn och eventuellt en rubrik för konfigurationen, välj **[!UICONTROL RESTful Service]** i **[!UICONTROL Service Type]** listrutan, bläddra och välj en miniatyrbild för konfigurationen och tryck sedan på **[!UICONTROL Next]**.
1. Ange följande information för RESTful-tjänsten:

   * Välj URL eller Fil i listrutan Växlingskälla och ange därför SWAGGER-URL:en till Swagger-definitionsfilen eller överför Swagger-filen från det lokala filsystemet.
   * Välj autentiseringstyp - Ingen, OAuth2.0, Grundläggande autentisering, API-nyckel eller Anpassad autentisering - för att få åtkomst till RESTful-tjänsten och ange därefter information för autentisering.

1. Tryck för **[!UICONTROL Create]** att skapa molnkonfigurationen för RESTful-tjänsten.

## Konfigurera SOAP-webbtjänster {#configure-soap-web-services}

SOAP-baserade webbtjänster beskrivs med hjälp av WSDL-specifikationer ( [Web Services Description Language)](https://www.w3.org/TR/wsdl). Om du vill konfigurera en SOAP-baserad webbtjänst i AEM-molntjänster kontrollerar du att du har WSDL-webbadressen för webbtjänsten och gör följande:

1. Gå till **[!UICONTROL Tools > Cloud Services > Data Sources]**. Tryck för att välja den mapp där du vill skapa en molnkonfiguration.

   Mer information om hur du skapar och konfigurerar en mapp för molntjänstkonfigurationer finns i [Konfigurera mapp för molntjänstkonfigurationer](/help/forms/using/configure-data-sources.md#cloud-folder) .

1. Tryck **[!UICONTROL Create]** för att öppna **[!UICONTROL Create Data Source Configuration dialog]**. Ange ett namn och eventuellt en rubrik för konfigurationen, välj **[!UICONTROL SOAP Web Service]** i **[!UICONTROL Service Type]** listrutan, bläddra och välj en miniatyrbild för konfigurationen och tryck sedan på **[!UICONTROL Next]**.
1. Ange följande för SOAP-webbtjänsten:

   * WSDL-URL för webbtjänsten.
   * Välj autentiseringstyp - Ingen, OAuth2.0, Grundläggande autentisering eller Anpassad autentisering - för att få åtkomst till SOAP-tjänsten och ange därefter information för autentisering.

1. Tryck för **[!UICONTROL Create]** att skapa molnkonfigurationen för SOAP-webbtjänsten.

## Konfigurera OData-tjänster {#config-odata}

En OData-tjänst identifieras av tjänstens rot-URL. Om du vill konfigurera en OData-tjänst i AEM-molntjänster kontrollerar du att du har tjänstens rot-URL och gör följande:

>[!NOTE]
>
>Stegvisa anvisningar om hur du konfigurerar Microsoft Dynamics 365, online eller lokalt, finns i [Microsoft Dynamics OData-konfiguration](/help/forms/using/ms-dynamics-odata-configuration.md).

1. Gå till **[!UICONTROL Tools > Cloud Services > Data Sources]**. Tryck för att välja den mapp där du vill skapa en molnkonfiguration.

   Mer information om hur du skapar och konfigurerar en mapp för molntjänstkonfigurationer finns i [Konfigurera mapp för molntjänstkonfigurationer](/help/forms/using/configure-data-sources.md#cloud-folder) .

1. Tryck **[!UICONTROL Create]** för att öppna **[!UICONTROL Create Data Source Configuration dialog]**. Ange ett namn och eventuellt en rubrik för konfigurationen, välj **[!UICONTROL OData Service]** i **[!UICONTROL Service Type]** listrutan, bläddra och välj en miniatyrbild för konfigurationen och tryck sedan på **[!UICONTROL Next]**.
1. Ange följande information för OData-tjänsten:

   * Tjänstens rot-URL för OData-tjänsten som ska konfigureras.
   * Välj autentiseringstyp - Ingen, OAuth2.0, Grundläggande autentisering eller Anpassad autentisering - för att få åtkomst till OData-tjänsten och ange därefter information för autentisering.
   >[!NOTE]
   >
   >Du måste välja autentiseringstypen OAuth 2.0 om du vill ansluta till Microsoft Dynamics-tjänster med OData-slutpunkten som tjänstrot.

1. Tryck på **Skapa** för att skapa molnkonfigurationen för OData-tjänsten.

## Nästa steg {#next-steps}

Du har konfigurerat datakällorna. Därefter kan du skapa en formulärdatamodell eller, om du redan har skapat en formulärdatamodell utan en datakälla, associera den med de datakällor du just konfigurerade. Mer information finns i [Skapa formulärdatamodell](/help/forms/using/create-form-data-models.md) .
