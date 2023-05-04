---
title: Integrera Acrobat Sign med AEM Forms
seo-title: Integrate Acrobat Sign with AEM Forms
description: Lär dig konfigurera Acrobat Sign för AEM Forms
seo-description: Learn how to configure Acrobat Sign for AEM Forms
uuid: 9efd5c44-3d87-4c56-aa6c-e65397fff243
contentOwner: sashanka
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: 7d494c2e-d457-4d52-89be-a77ffa07eb88
feature: Adaptive Forms, Acrobat Sign
exl-id: e7c27623-a889-4bd5-bfff-cfe513cd1a35
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '978'
ht-degree: 0%

---

# Integrera Acrobat Sign med AEM Forms {#integrate-adobe-sign-with-aem-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Acrobat Sign möjliggör e-signaturarbetsflöden för anpassningsbara formulär. E-signaturer förbättrar arbetsflödena för att bearbeta dokument inom juridik, försäljning, löneadministration, personaladministration och många andra områden.

I ett typiskt Acrobat Sign och anpassningsbara formulär fyller en användare i ett anpassat formulär för att **ansöka om en tjänst**. Till exempel kan en kreditkortsansökan och en medborgare få förmåner. När en användare fyller i, skickar och signerar ansökningsformuläret skickas formuläret till tjänsteleverantören för ytterligare åtgärder. Tjänsteleverantören granskar programmet och använder Acrobat Sign för att markera det som godkänt. För att möjliggöra liknande arbetsflöden för elektroniska signaturer kan du integrera Acrobat Sign med AEM Forms.

Konfigurera Acrobat Sign i AEM Cloud Services om du vill använda Acrobat Sign med AEM Forms:

## Förutsättningar {#prerequisites}

Du behöver följande för att kunna integrera Acrobat Sign med AEM Forms:

* En aktiv [Acrobat Sign utvecklarkonto.](https://acrobat.adobe.com/us/en/why-adobe/developer-form.html)
* An [SSL är aktiverat](/help/sites-administering/ssl-by-default.md) AEM Forms-server.
* An [Acrobat Sign API-program](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/create_app.md).
* Autentiseringsuppgifter (klient-ID och klienthemlighet) för Acrobat Sign API-program.
* När du konfigurerar om tar du bort den befintliga Acrobat Sign-konfigurationen från både författare- och publiceringsinstanser.
* Använd [identisk krypteringsnyckel](/help/sites-administering/security-checklist.md#make-sure-you-properly-replicate-encryption-keys-when-needed) för författare och publiceringsinstanser.

## Konfigurera Acrobat Sign med AEM Forms {#configure-adobe-sign-with-aem-forms}

När förutsättningarna är uppfyllda utför du följande steg för att konfigurera Acrobat Sign med AEM Forms på Author-instansen:

1. I AEM Forms-författarinstansen går du till **verktyg** ![hammare](assets/hammer.png) > **Allmänt** > **Konfigurationsläsaren**.
   * Se [Configuration Browser-dokumentation](/help/sites-administering/configurations.md) för mer information.
1. På **[!UICONTROL Configuration Browser]** sida, tryck **[!UICONTROL Create]**.
1. I **[!UICONTROL Create Configuration]** dialogruta, ange **[!UICONTROL Title]** för konfigurationen, aktivera **[!UICONTROL Cloud Configurations]** och trycka **[!UICONTROL Create]**. Den skapar en konfigurationsbehållare för molntjänster.
1. Navigera till **verktyg** ![hammare](assets/hammer.png) > **Cloud Services** > **Acrobat Sign** och välj den konfigurationsbehållare som du skapade i steget ovan.

   >[!NOTE]
   >
   >Du kan antingen utföra steg 1-4 för att skapa en ny konfigurationsbehållare och skapa en Acrobat Sign-konfiguration i behållaren eller använda den befintliga `global` mapp i **verktyg** ![hammare](assets/hammer.png) > **Cloud Services** > **Acrobat Sign**. Om du skapar konfigurationen i den nya konfigurationsbehållaren måste du ange behållarnamnet i dialogrutan **[!UICONTROL Configuration Container]** när du skapar ett anpassat formulär.

   >[!NOTE]
   Kontrollera att URL:en för konfigurationssidan för molntjänster börjar med **HTTPS**. Om inte, [aktivera SSL](/help/sites-administering/ssl-by-default.md) för AEM Forms-server.

1. Tryck på **[!UICONTROL Create]** för att skapa Acrobat Sign-konfiguration i AEM Forms.
1. I **[!UICONTROL General]** -fliken i **[!UICONTROL Create Acrobat Sign Configuration]** sida, ange en **Namn** för konfigurationen och tryck **Nästa**. Du kan också ange en titel och bläddra för att välja en miniatyrbild för konfigurationen.

1. Kopiera URL-adressen i det aktuella webbläsarfönstret till en anteckningsruta. Du måste konfigurera Acrobat Sign-programmet med AEM Forms.

1. Konfigurera OAuth-inställningar för Acrobat Sign-programmet:

   1. Öppna ett webbläsarfönster och logga in på Acrobat Sign utvecklarkonto.
   1. Markera programmet som konfigurerats för AEM Forms och tryck på Konfigurera OAuth för program.
   1. I **Omdirigerings-URL** lägger du till HTTPS-URL:en som kopierades i föregående steg och klickar på **Spara**.
   1. Aktivera följande OAuth-inställningar för Acrobat Sign-programmet och klicka på **Spara**.
   * aggrement_read
   * aggrement_write
   * aggrement_send
   * widget_write
   * workflow_read

   Stegvis information om hur du konfigurerar OAuth-inställningar för ett Acrobat Sign-program och hämtar nycklarna finns i [Konfigurera autentiseringsinställningar för programmet](https://www.adobe.io/apis/documentcloud/sign/docs.html#!adobedocs/adobe-sign/master/gstarted/configure_oauth.md) dokumentation för utvecklare.

   ![OAuth-konfiguration](assets/oauthconfig_new.png)

1. Gå tillbaka till **Skapa Acrobat Sign-konfiguration** sida. I **[!UICONTROL Settings]** -fliken **[!UICONTROL OAuth URL]** I fältet anges följande standard-URL:

   `https://secure.na1.echosign.com/public/oauth`

   där:

   **na1** refererar till standarddatabasfragmentet.

   Du kan ändra värdet för databasdelningen. Starta om servern för att kunna använda det nya värdet för databasdelningen.

1. Ange **Klient-ID** (kallas även program-ID) och **Klienthemlighet**. Välj **Aktivera även Acrobat Sign för bilagor** om du vill lägga till filer som är kopplade till ett adaptivt formulär i motsvarande Acrobat Sign-dokument som skickats för signering.

   Tryck på **[!UICONTROL Connect to Acrobat Sign]**. Ange användarnamn och lösenord för kontot som används när Acrobat Sign-programmet skapas när du uppmanas att ange inloggningsuppgifter.

   Tryck **[!UICONTROL Create]** för att skapa Acrobat Sign-konfigurationen.

1. Öppna AEM webbkonsol. URL:en är `https://'[server]:[port]'/system/console/configMgr`
1. Öppna **Forms Common Configuration Service.**
1. I **Tillåt** fält, **välj** Alla användare - Alla användare, anonyma eller inloggade, kan förhandsgranska bilagor, verifiera och signera formulär och klicka på **Spara.** Författarinstansen är konfigurerad att använda Acrobat Sign.
1. Använd [replikering](/help/sites-deploying/replication.md) om du vill skapa en identisk konfiguration för motsvarande publiceringsinstanser.

Nu är Acrobat Sign integrerat med AEM Forms och klart att användas i anpassningsbara formulär. Till [använda Acrobat Sign-tjänsten i ett adaptivt formulär](../../forms/using/working-with-adobe-sign.md#configure-adobe-sign-for-an-adaptive-form)anger du den konfigurationsbehållare som skapas ovan i anpassningsbara formuläregenskaper.

## Konfigurera Acrobat Sign-schemaläggaren för att synkronisera signeringsstatusen {#configure-adobe-sign-scheduler-to-sync-the-signing-status}

Ett anpassat formulär som har aktiverats av Acrobat Sign skickas endast när alla signerare har slutfört signeringsprocessen. Som standard är Acrobat Sign Scheduler-tjänster schemalagda att kontrollera (avfråga) signerarens svar efter 24 timmars intervall. Du kan ändra standardintervallet för din miljö. Utför följande steg för att ändra standardintervallet:

1. Logga in på AEM Forms server med administratörsuppgifter och navigera till **verktyg** > **Operationer** > **Webbkonsol**.

   Du kan även öppna följande URL-adress i ett webbläsarfönster:
   `https://[localhost]:'port'/system/console/configMgr`

1. Leta reda på och öppna **Konfigurationstjänst för Acrobat Sign** alternativ. Ange en [cron-uttryck](https://en.wikipedia.org/wiki/Cron#CRON_expression) i **Schemaläggarens uttryck för statusuppdatering** fält och klicka **Spara**. Om du till exempel vill köra konfigurationstjänsten varje dag klockan 00:00 anger du `0 0 0 1/1 * ? *` i **Schemaläggarens uttryck för statusuppdatering** fält.

Standardintervallet för synkroniseringsstatus för Acrobat Sign har ändrats.

## Relaterade artiklar {#related-articles}

* [Använda Acrobat Sign i en adaptiv form](../../forms/using/working-with-adobe-sign.md)
* [Använda Acrobat Sign med AEM Forms (video)](https://helpx.adobe.com/experience-manager/kt/forms/using/adobe-sign-integration-feature-video.html)
* [Integrera Acrobat Sign med AEM Forms](../../forms/using/adobe-sign-integration-adaptive-forms.md)
