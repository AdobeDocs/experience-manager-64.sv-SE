---
title: Konfigurera inställningar för säker administration för AEM Forms på JEE
seo-title: Configuring Secure Administration Settings for AEM Forms on JEE
description: Lär dig hur du administrerar användarkonton och tjänster som, trots att de krävs i en privat utvecklingsmiljö, inte krävs i en produktionsmiljö i AEM Forms på JEE.
seo-description: Learn how to administer user accounts and services that, although required in a private development environment, are not required in a production environment of AEM Forms on JEE.
uuid: 04e45d06-f57d-406c-8228-15f483199430
content-type: reference
topic-tags: Security
products: SG_EXPERIENCEMANAGER/6.4
discoiquuid: d211d8b0-e75f-49c3-808d-5d0e26ad3a6b
role: Admin
exl-id: 980d420c-a768-4634-9b8c-3f1d7327285d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 0%

---

# Konfigurera inställningar för säker administration för AEM Forms på JEE {#configuring-secure-administration-settings-for-aem-forms-on-jee}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Lär dig hur du administrerar användarkonton och tjänster som, trots att de krävs i en privat utvecklingsmiljö, inte krävs i en produktionsmiljö i AEM Forms på JEE.

I allmänhet använder inte utvecklare produktionsmiljön för att bygga och testa applikationer. Därför måste du administrera användarkonton och tjänster som, trots att de krävs i en privat utvecklingsmiljö, inte krävs i en produktionsmiljö.

I den här artikeln beskrivs metoder för att minska den totala attackytan med hjälp av administrationsalternativ som finns i AEM Forms på JEE.

## Inaktiverar icke nödvändig fjärråtkomst till tjänster {#disabling-non-essential-remote-access-to-services}

När AEM Forms har installerats och konfigurerats på JEE är många tjänster tillgängliga för fjärranrop via SOAP och Enterprise JavaBeans™ (EJB). Termen fjärranrop avser i det här fallet alla anropare som har nätverksåtkomst till SOAP-, EJB- eller AMF-portarna (Action Message Format) för programservern.

Även om AEM Forms på JEE-tjänster kräver att giltiga autentiseringsuppgifter skickas för en auktoriserad anropare, bör du endast tillåta fjärråtkomst till de tjänster som du behöver för att kunna fjärråtkomst. För att uppnå begränsad tillgänglighet bör du minska uppsättningen fjärranslutna tjänster till minsta möjliga för ett fungerande system och sedan aktivera fjärranrop för de ytterligare tjänster du behöver.

AEM Forms på JEE-tjänster behöver alltid minst SOAP-åtkomst. Dessa tjänster krävs vanligtvis för Workbench, men omfattar även tjänster som anropas av Workspace-webbprogrammet.

Gör så här med webbsidan Program och tjänster i administrationskonsolen:

1. Logga in på administrationskonsolen genom att skriva följande URL i en webbläsare:

   ```as3
            https://[host name]:[port]/adminui
   ```

1. Klicka **Tjänster > Program och tjänster > Inställningar**.
1. Ställ in inställningarna så att upp till 200 tjänster och slutpunkter visas på samma sida.
1. Klicka **Tjänster** > **Program och tjänster** > **Hantering av slutpunkter**.
1. Välj **EJB** från **Provider** lista och klicka sedan på **Filter**.
1. Om du vill inaktivera alla EJB-slutpunkter markerar du kryssrutan bredvid var och en av dem i listan och klickar på **Inaktivera**.
1. Klicka **Nästa** och upprepa föregående steg för alla EJB-slutpunkter. Kontrollera att EJB finns med i leverantörskolumnen innan du inaktiverar slutpunkterna.
1. Välj **SOAP** från **Provider** lista och klicka sedan på **Filter**.
1. Om du vill ta bort SOAP-slutpunkter markerar du kryssrutan bredvid var och en av dem i listan och klickar på **Ta bort**. Ta inte bort följande slutpunkter:

   * AuthenticationManagerService
   * DirectoryManagerService
   * JobManager
   * event_management_service
   * event_configuration_service
   * ProcessManager
   * TemplateManager
   * RepositoryService
   * TaskManagerService
   * TaskQueueManager
   * TaskManagerQueryService
   * WorkspaceSingleSignOn
   * ApplicationManager

1. Klicka **Nästa** och upprepa föregående steg för SOAP-slutpunkter som inte finns i ovanstående lista. Kontrollera att SOAP finns med i leverantörskolumnen innan du tar bort slutpunkterna.

## Inaktiverar onödvändig anonym åtkomst till tjänster {#disabling-non-essential-anonymous-access-to-services}

Vissa formulärservertjänster tillåter oautentiserade (anonyma) anrop för vissa åtgärder. Det innebär att en eller flera åtgärder som exponeras av tjänsten kan anropas som en autentiserad användare eller som ingen autentiserad användare alls.

1. Logga in på administrationskonsolen genom att skriva följande URL i en webbläsare:

   ```as3
            https://[host name]:[port]/adminui
   ```

1. Klicka **Tjänster > Program och tjänster > Tjänsthantering**.
1. Klicka på namnet på den tjänst som du vill inaktivera (till exempel AuthenticationManagerService).
1. Klicka på **Fliken Säkerhet**, avmarkera **Anonym åtkomst tillåten** och klicka **Spara**.
1. Slutför steg 3 och 4 för följande tjänster:

   * AuthenticationManagerService
   * EJB
   * E-post
   * JobManager
   * WatchedFolder
   * UsermanagerUtilService
   * Remoting
   * RepositoryProviderService
   * EMCDocumentumRepositoryProvider
   * IBMFilenetRepositoryProvider
   * FormAugmenter
   * TaskManagerService
   * TaskManagerKoppling
   * TaskManagerQueryService
   * TaskQueueManager
   * AktivitetSlutpunktshanterare
   * UserService
   * WorkspaceSearchTemplateService
   * WorkspacePropertyService
   * OutputService
   * FormsService

   Om du tänker visa någon av dessa tjänster för fjärranrop bör du även inaktivera anonym åtkomst för dessa tjänster. Annars kan anropare med nätverksåtkomst till den här tjänsten anropa tjänsten utan att skicka giltiga autentiseringsuppgifter.

   Anonym åtkomst bör inaktiveras för alla tjänster som inte behövs. Många interna tjänster kräver att anonym autentisering är aktiverat eftersom de måste anropas av en potentiell användare i systemet utan att vara förauktoriserade.

## Ändra standardtimeout för global {#changing-the-default-global-time-out}

Slutanvändare kan autentisera till AEM Forms via Workbench, AEM Forms webbprogram eller anpassade program som anropar AEM Forms servertjänster. En global timeout-inställning används för att ange hur lång tid dessa användare kan interagera med AEM Forms (med en SAML-baserad försäkran) innan de tvingas autentisera igen. Standardinställningen är två timmar. I en produktionsmiljö måste tiden minskas till det minsta antal minuter som tillåts.

### Minimera tidsgränsen för omautentisering {#minimize-reauthentication-time-limit}

1. Logga in på administrationskonsolen genom att skriva följande URL i en webbläsare:

   ```as3
            https://[host name]:[port]/adminui
   ```

1. Klicka **Inställningar > Användarhantering > Konfiguration > Importera och exportera konfigurationsfiler**.
1. Klicka **Exportera** för att skapa en config.xml-fil med de befintliga AEM Forms-inställningarna.
1. Öppna XML-filen i en redigerare och leta reda på följande post:

   `<entry key=”assertionValidityInMinutes” value=”120”/>`

1. Ändra värdet till ett tal som är större än 5 (i minuter) och spara filen.
1. Gå till sidan Importera och exportera konfigurationsfiler i administrationskonsolen.
1. Ange sökvägen till den ändrade filen config.xml eller klicka på Bläddra för att navigera till den.
1. Klicka **Importera** för att ladda upp den ändrade filen config.xml och sedan klicka på **OK**.
