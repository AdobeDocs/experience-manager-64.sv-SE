---
title: Konfigurera AEM Assets med varumärkesportalen
description: Lär dig hur du konfigurerar AEM Assets med Brand Portal för publicering av resurser och samlingar till Brand Portal.
contentOwner: VG
feature: Brand Portal
role: Admin
exl-id: cde35555-259f-4d16-999f-2b93d597b8a5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1586'
ht-degree: 36%

---

# Konfigurera AEM Assets med varumärkesportalen {#configure-integration-64}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets har konfigurerats med Brand Portal via [!DNL Adobe I/O], som köper en IMS-token för godkännande av din Brand Portal-klient.

>[!NOTE]
>
>Konfigurera AEM Assets med Brand Portal via [!DNL Adobe I/O] stöds i AEM 6.4.8.0 och senare.
>
>Tidigare konfigurerades Brand Portal i Classic UI via äldre OAuth-gateway, som använder JWT-tokenutbyte för att erhålla en IMS-åtkomsttoken för auktorisering.

>[!TIP]
>
>***Endast för befintliga kunder***
>
>Vi rekommenderar att du fortsätter använda den befintliga äldre OAuth Gateway-konfigurationen. Om du får problem med äldre OAuth Gateway-konfiguration tar du bort den befintliga konfigurationen och skapar en ny konfiguration via [!DNL Adobe I/O].

I den här hjälpen beskrivs följande två användningsområden:

* [Ny konfiguration](#configure-new-integration-64): Om du är en ny Brand Portal-användare och vill konfigurera din AEM Assets-författarinstans med Brand Portal kan du skapa en ny konfiguration på [!DNL Adobe I/O].
* [Uppgraderingskonfiguration](#upgrade-integration-64): Om du är en befintlig Brand Portal-användare med din AEM Assets-författarinstans konfigurerad med Brand Portal på en äldre OAuth Gateway rekommenderar vi att du tar bort de befintliga konfigurationerna och skapar en ny konfiguration på [!DNL Adobe I/O].

Informationen baseras på antagandet att alla som läser den här hjälpen känner till följande tekniker:

* Installera, konfigurera och administrera Adobe Experience Manager- och AEM-paket

* Använda operativsystemen Linux och Microsoft Windows

## Förutsättningar {#prerequisites}

Du behöver följande för att konfigurera AEM Assets med varumärkesportalen:

* En pågående AEM Assets-författarinstans med senaste Service Pack.
* Varumärkesportalens klientorganisations-URL.
* En användare med systemadministratörsbehörighet på IMS-organisationen för varumärkesportalens klient.

[Hämta och installera AEM 6.4](#aemquickstart)

[Hämta och installera det senaste AEM Service Pack](#servicepack)

### Hämta och installera AEM 6.4 {#aemquickstart}

Vi rekommenderar att du AEM 6.4 för att konfigurera en AEM författarinstans. Om du inte har AEM igång kan du hämta det från följande platser:

* Om du redan är AEM kan du hämta AEM 6.4 från [Adobe licenswebbplats](http://licensing.adobe.com).

* Om du är Adobe partner ska du använda [Adobe Partner Training Program](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=82357Q) att begära AEM 6.4.

När du har laddat ned AEM finns instruktioner om hur du konfigurerar en AEM författarinstans i [driftsätta och underhålla](https://helpx.adobe.com/experience-manager/6-4/sites/deploying/using/deploy.html#defaultlocalinstall).

### Hämta och installera AEM senaste Service Pack {#servicepack}

Detaljerade instruktioner finns i

* [AEM 6.4 Service Pack versionsinformation](https://helpx.adobe.com/experience-manager/6-4/release-notes/sp-release-notes.html)

**Kontakta kundsupport** om du inte kan hitta det senaste AEM eller Service Pack.

## Skapa en konfiguration {#configure-new-integration-64}

Utför följande steg i den listade sekvensen om du konfigurerar AEM Assets med Brand Portal för första gången:

1. [Hämta ett offentligt certifikat](#public-certificate)
1. [Skapa [!DNL Adobe I/O] integration](#createnewintegration)
1. [Skapa en konfiguration för IMS-kontot](#create-ims-account-configuration)
1. [Konfigurera molntjänsten](#configure-the-cloud-service)
1. [Testa konfigurationen](#test-integration)

>[!NOTE]
>
>En instans av en AEM Assets-författare får endast konfigureras med en Brand Portal-klient.

### Skapa IMS-konfigurationen {#create-ims-configuration}

IMS-konfigurationen autentiserar varumärkesportalens klient med författarinstansen för AEM Assets.

IMS-konfigurationen har två steg:

* [Hämta ett offentligt certifikat](#public-certificate)
* [Skapa en konfiguration för IMS-kontot](#create-ims-account-configuration)

### Hämta ett offentligt certifikat {#public-certificate}

Med ett offentligt certifikat kan du autentisera din profil på [!DNL Adobe I/O].

1. Logga in på din AEM Assets-författarinstans Standardwebbadress: http:// localhost:4502/aem/start.html
1. Gå till **[!UICONTROL Security]** >> **[!UICONTROL Adobe IMS Configurations]** från panelen **Tools** ![Tools](assets/tools.png).

   ![Användargränssnittet för konfiguration av Adobe IMS-kontot](assets/ims-config1.png)

1. Sidan Adobe IMS-konfigurationer öppnas.

   Klicka på **[!UICONTROL Create]**.

   Sidan **[!UICONTROL Adobe IMS Technical Account Configuration]** öppnas.

1. Fliken **Certifikat** öppnas som standard.

   Välj **[!UICONTROL Adobe Brand Portal]** i **Molnlösning**,

1. Markera kryssrutan **[!UICONTROL Create new certificate]** och ange ett **alias** för certifikatet. Aliaset används som namn på dialogrutan.

1. Klicka på **[!UICONTROL Create certificate]**. En dialogruta visas. Klicka på **[!UICONTROL OK]** för att generera det offentliga certifikatet.

   ![Skapa ett certifikat](assets/ims-config2.png)

1. Klicka på **[!UICONTROL Download Public Key]** och spara certifikatfilen *AEM-Adobe-IMS.crt* på datorn. Certifikatfilen används för [skapa [!DNL Adobe I/O] integration](#createnewintegration).

   ![Hämta certifikatet](assets/ims-config3.png)

1. Klicka på **[!UICONTROL Next]**.

   Du skapar Adobe IMS-kontot på fliken **Konto**, men för det behöver du integreringsinformationen. Håll den här sidan öppen tills vidare.

   Öppna en ny flik och [Skapa [!DNL Adobe I/O] integration](#createnewintegration) för att få integreringsinformation för IMS-kontokonfigurationer.

### Skapa [!DNL Adobe I/O] integration {#createnewintegration}

[!DNL Adobe I/O] integreringen genererar API-nyckel, klienthemlighet och nyttolast (JWT) som krävs för att konfigurera IMS-kontokonfigurationer.

1. Logga in på [!DNL Adobe I/O] Konsol med systemadministratörsbehörighet för IMS-organisationen för Brand Portal-klienten.

   Standard-URL: [https://console.adobe.io/](https://console.adobe.io/)

1. Klicka på **[!UICONTROL Create Integration]**.

1. Markera **[!UICONTROL Access an API]** och klicka på **[!UICONTROL Continue]**.

   ![Skapa en ny integrering](assets/create-new-integration1.png)

1. Sidan Skapa en ny integrering öppnas.

   Välj din organisation i listrutan.

   Välj **[!UICONTROL AEM Brand Portal]** och klicka på **[!UICONTROL Continue]** i **[!UICONTROL Experience Cloud]**.

   Kontrollera att du har valt rätt organisation i listrutan ovanför alternativet **[!UICONTROL Adobe Services]** om alternativet Varumärkesportal är inaktiverat. Kontakta administratören om du inte känner till din organisation.

   ![Skapa en integrering](assets/create-new-integration2.png)

1. Ange ett namn och en beskrivning för integrationen. Klicka på **[!UICONTROL Select a File from your computer]** och överför filen `AEM-Adobe-IMS.crt` som laddades ner under [Hämta ett offentligt certifikat](#public-certificate) .

1. Välj organisationens profil.

   Du kan också markera standardprofilen **[!UICONTROL Assets Brand Portal]** och klicka på **[!UICONTROL Create Integration]**. Integreringen skapas.

1. Klicka på **[!UICONTROL Continue to integration details]** för att visa integreringsinformationen.

   Kopiera **[!UICONTROL API Key]**

   Klicka på **[!UICONTROL Retrieve Client Secret]** och kopiera nyckeln för klienthemligheten.

   ![API-nyckel, klienthemlighet och nyttolastinformation för en integrering](assets/create-new-integration3.png)

1. Gå till fliken **[!UICONTROL JWT]** och kopiera **[!UICONTROL JWT payload]**.

   API-nyckeln, nyckeln för klienthemligheten och informationen för JWT-nyttolasten används för att skapa en IMS-kontokonfiguration.

### Skapa en konfiguration för IMS-kontot {#create-ims-account-configuration}

Kontrollera att du har utfört följande steg:

* [Hämta ett offentligt certifikat](#public-certificate)
* [Skapa [!DNL Adobe I/O] integration](#createnewintegration)

**Så här skapar du en IMS-kontokonfiguration:**

1. Öppna sidan IMS-konfiguration och fliken **[!UICONTROL Accounts]**. Du lämnade den här sidan öppen i slutet av avsnittet [Hämta ett offentligt certifikat ](#public-certificate).

1. Ange en **[!UICONTROL Title]** för IMS-kontot.

   Ange URL:en [https://ims-na1.adobelogin.com/](https://ims-na1.adobelogin.com/) i **[!UICONTROL Authorization Server]**.

   Klistra in API-nyckeln, klienthemligheten och JWT-nyttolasten som du har kopierat i slutet av [Skapa [!DNL Adobe I/O] integration](#createnewintegration).

   Klicka på **[!UICONTROL Create]**.

   Integreringen skapas.

   ![Konfiguration av ett IMS-konto](assets/create-new-integration6.png)

1. Markera IMS-konfigurationen och klicka på **[!UICONTROL Check Health]**. En dialogruta visas.

   Klicka på **[!UICONTROL Check]**. Meddelandet *Token har hämtats* visas när en anslutning har skapats.

   ![](assets/create-new-integration5.png)

>[!CAUTION]
>
>Du får bara ha en IMS-konfiguration. Skapa inte flera IMS-konfigurationer.
>
>Kontrollera att IMS-konfigurationen klarar hälsokontrollen. Om konfigurationen inte godkänns i hälsokontrollen är den ogiltig. Du måste ta bort den och skapa en ny, giltig konfiguration.

### Konfigurera molntjänsten {#configure-the-cloud-service}

Gör så här för att skapa molntjänstkonfigurationen för varumärkesportalen:

1. Logga in på din AEM Assets-författarinstans

   Standard-URL: http:// localhost:4502/aem/start.html
1. Gå till **[!UICONTROL Cloud Services >> AEM Brand Portal]** från panelen **Tools** ![Tools](assets/tools.png).

   Sidan Konfigurationer för varumärkesportalen öppnas.

1. Klicka på **[!UICONTROL Create]**.

1. Ange en **[!UICONTROL Title]** för konfigurationen.

   Välj den IMS-konfiguration som du har skapat i steget [Skapa en konfiguration för IMS-kontot](#create-ims-account-configuration).

   Ange varumärkesportalens klientorganisations-URL i **[!UICONTROL Service URL]**.

   ![](assets/create-cloud-service.png)

1. Klicka på **[!UICONTROL Save and Close]**. Molnkonfigurationen har skapats. Din AEM Assets-författarinstans är nu integrerad med Brand Portal-klienten.

### Testa konfigurationen {#test-integration}

1. Logga in på din AEM Assets-författarinstans

   Standard-URL: http:// localhost:4502/aem/start.html

1. Gå till **[!UICONTROL Deployment >> Replication]** från panelen **Tools** ![Tools](assets/tools.png).

   ![](assets/test-integration1.png)

1. Replikeringssidan öppnas.

   Klicka på **[!UICONTROL Agents on author]**.

   ![](assets/test-integration2.png)

1. Fyra replikeringsagenter skapas för varje klientorganisation.

   Leta reda på replikeringsagenterna för din Brand Portal-klient.

   Klicka på replikeringsagentens URL.

   ![](assets/test-integration3.png)


   >[!NOTE]
   >
   >Replikeringsagenterna arbetar parallellt och delar jobbdistributionen jämnt, vilket ökar publiceringshastigheten fyra gånger den ursprungliga hastigheten. När molntjänsten har konfigurerats krävs ingen ytterligare konfiguration för att aktivera de replikeringsagenter som aktiveras som standard för att aktivera parallell publicering av flera resurser.

1. Kontrollera anslutningen mellan AEM Assets författare och Brand Portal genom att klicka **[!UICONTROL Test Connection]**.

   ![](assets/test-integration4.png)

1. Titta på testresultatens nedre del för att kontrollera att replikeringen lyckades.

   ![](assets/test-integration5.png)


1. Verifiera testresultaten för alla fyra replikeringsagenterna en i en.

   >[!NOTE]
   >
   >Undvik att inaktivera någon av replikeringsagenterna eftersom det kan göra att replikeringen av vissa resurser misslyckas.
   >
   >Se till att alla fyra replikeringsagenterna är konfigurerade för att undvika timeout-fel. Se [felsöka problem vid parallell publicering till Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/publish/troubleshoot-parallel-publishing.html#connection-timeout).

Brand Portal har konfigurerats med din AEM Assets-författarinstans. Du kan nu:

* [Publicera resurser från AEM Assets till varumärkesportalen](../assets/brand-portal-publish-assets.md)
* [Publicera mappar från AEM Assets till varumärkesportalen](../assets/brand-portal-publish-folder.md)
* [Publicera samlingar från AEM Assets till varumärkesportalen](../assets/brand-portal-publish-collection.md)
* [Konfigurera resurskälla](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/asset-sourcing-in-brand-portal/brand-portal-asset-sourcing.html) gör det möjligt för Brand Portal-användare att bidra med och publicera material till AEM Assets.

## Uppgraderingskonfiguration {#upgrade-integration-64}

Utför följande steg i den listade sekvensen för att uppgradera befintliga konfigurationer:

1. [Verifiera jobb som körs](#verify-jobs)
1. [Ta bort befintliga konfigurationer](#delete-existing-configuration)
1. [Skapa en konfiguration](#configure-new-integration-64)

### Verifiera jobb som körs {#verify-jobs}

Kontrollera att inget publiceringsjobb körs på din AEM Assets-författarinstans innan du gör några ändringar. För detta kan du verifiera alla fyra replikeringsagenterna och se till att kön är idealisk/tom.

1. Logga in på din AEM Assets-författarinstans

   Standard-URL: http:// localhost:4502/aem/start.html

1. Gå till **[!UICONTROL Deployment >> Replication]** från panelen **Tools** ![Tools](assets/tools.png).

1. Replikeringssidan öppnas.

   Klicka på **[!UICONTROL Agents on author]**.

   ![](assets/test-integration2.png)

1. Leta reda på replikeringsagenterna för din Brand Portal-klient.

   Se till att **Kön är inaktiv** för alla replikeringsagenter är inget publiceringsjobb aktivt.

   ![](assets/test-integration3.png)

### Ta bort befintliga konfigurationer {#delete-existing-configuration}

Du måste köra följande checklista när du tar bort den befintliga konfigurationen.

* Ta bort alla fyra replikeringsagenter
* Ta bort molntjänst
* Ta bort MAC-användare

Så här tar du bort den befintliga konfigurationen:

1. Logga in på din AEM Assets-författarinstans och öppna CRX Lite som administratör.

   Standard-URL: http:// localhost:4502/crx/de/index.jsp

1. Navigera till `/etc/replications/agents.author` och ta bort alla fyra replikeringsagenterna för din Brand Portal-klient.

   ![](assets/delete-replication-agent.png)

1. Navigera till `/etc/cloudservices/mediaportal` och ta bort **Konfigurering av Cloud Service**.

   ![](assets/delete-cloud-service.png)

1. Navigera till `/home/users/mac` och ta bort **Mac-användare** av er Brand Portal-klient.

   ![](assets/delete-mac-user.png)


Nu kan du [skapa konfiguration](#configure-new-integration-64) på din AEM 6.4-författarinstans på [!DNL Adobe I/O].



<!--
   Comment Type: draft

   <li> </li>
   -->

<!--
   Comment Type: draft

   <li>Step text</li>
   -->

När replikeringen är klar kan du publicera resurser, mappar och samlingar till Brand Portal. Mer information finns i:

* [Publicera resurser på varumärkesportalen](brand-portal-publish-assets.md)
* [Publicera resurser och mappar i Brand Portal](brand-portal-publish-folder.md)
* [Publicera samlingar i Brand Portal](brand-portal-publish-collection.md)
