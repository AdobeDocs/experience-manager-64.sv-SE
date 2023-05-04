---
title: Distribuera webbgrupper
seo-title: Deploying Communities
description: Så här distribuerar du AEM Communities
seo-description: How to deploy AEM Communities
uuid: 1f7faf1a-a339-4eaa-b728-b9110cb350a8
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: deploying
discoiquuid: d0249609-2a9c-4d3b-92ee-dbc5fbdeaac6
exl-id: 0b7496f0-0b3c-4d12-a659-d95744157f14
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2192'
ht-degree: 1%

---

# Distribuera webbgrupper {#deploying-communities}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Förutsättningar {#prerequisites}

* [AEM 6.4 Platform](../../help/sites-deploying/deploy.md)

* AEM Communities-licens

* Ytterligare licenser för:

   * [Funktioner i Adobe Analytics for Communities](analytics.md)
   * [MongoDB för MSRP](msrp.md)
   * [Adobe Cloud för ASRP](asrp.md)

## Checklista för installation {#installation-checklist}

**För [AEM](../../help/sites-deploying/deploy.md#what-is-aem)**

* Installera den senaste [AEM 6.4 - uppdateringar](#aem-updates)

* Om du inte använder standardportarna (4502, 4503) [konfigurera replikeringsagenter](#replication-agents-on-author)
* [replikera krypteringsnyckeln](#replicate-the-crypto-key)
* Om det finns stöd för globalisering, [konfigurera automatisk översättning](../../help/sites-administering/translation.md)

   (exempelinställningar tillhandahålls för utveckling)

**För [Funktioner i Communities](overview.md)**

* Om en [publicera servergrupp](../../help/sites-deploying/recommended-deploys.md#tarmk-farm), [identifiera den primära utgivaren](#primary-publisher)

* [Aktivera tunneltjänsten](#tunnel-service-on-author)
* [Aktivera social inloggning](social-login.md#adobe-granite-oauth-authentication-handler)
* [Konfigurera Adobe Analytics](analytics.md)
* Konfigurera en [standardtjänst för e-post](email.md)
* Identifiera valet för [delad UGC-lagring](working-with-srp.md) (**SRP**)

   * Om MongoDB SRP [(MSRP)](msrp.md)

      * [Installera och konfigurera MongoDB](msrp.md#mongodb-configuration)
      * [Konfigurera Solr](solr.md)
      * [Välj MSRP](srp-config.md)
   * Om relationsdatabas SRP [(DSRP)](dsrp.md)

      * [Installera JDBC-drivrutinen för MySQL](#jdbc-driver-for-mysql)
      * [Installera och konfigurera MySQL för DSRP](dsrp-mysql.md)
      * [Konfigurera Solr](solr.md)
      * [Välj DSRP](srp-config.md)
   * Om Adobe SRP [(ASRP)](asrp.md)

      * Arbeta med din kontorepresentant för etablering
      * [Välj ASRP](srp-config.md)
   * Om JCR SRP [(JSRP)](jsrp.md)

      * Inte ett delat UGC-arkiv:

         * UGC replikeras aldrig
         * UGC är bara synligt på AEM instans eller kluster där det angavs
      * Standard är JSRP

   För **[aktiveringsfunktion](overview.md#enablement-community)**

   * [Installera och konfigurera FFmpeg](ffmpeg.md)
   * [Installera JDBC-drivrutinen för MySQL](#jdbc-driver-for-mysql)
   * [Installera AEM Communities SCORM-Engine](#scorm-package)
   * [Installera och konfigurera MySQL för aktivering](mysql.md)






## Senaste releaser {#latest-releases}

AEM 6.4 Communities GA innehåller Communities-paketet. Mer information om uppdateringar av AEM 6.4 [Communities](/help/release-notes/release-notes.md#experience-manager-communities), se [AEM 6.4 Versionsinformation](/help/release-notes/release-notes.md#release-information).

### AEM 6.4 - uppdateringar {#aem-updates}

Från och med AEM 6.3 levereras uppdateringar av Communities som en del av AEM Cumulative Fix Packs och Service Packs.

För de senaste uppdateringarna av AEM 6.4 bör du kontrollera [Adobe Experience Manager 6.4 Cumulative Fix Packs and Service Pack](https://helpx.adobe.com/experience-manager/aem-releases-updates.html).

### Versionshistorik {#version-history}

Liksom AEM 6.4 och senare är AEM Communities funktioner och snabbkorrigeringar en del av AEM Communities kumulativa korrigeringspaket och servicepaket. Det finns därför inga separata funktionspaket.

### JDBC-drivrutin för MySQL {#jdbc-driver-for-mysql}

Två Communities-funktioner använder en MySQL-databas:

* För [aktivering](enablement.md): spela in SCORM-aktiviteter
* För [DSRP](dsrp.md): lagra användargenererat innehåll (UGC)

MySQL-kopplingen måste hämtas och installeras separat.

Nödvändiga steg är:

1. Hämta ZIP-arkivet från [https://dev.mysql.com/downloads/connector/j/](https://dev.mysql.com/downloads/connector/j/)

   * Versionen måste vara >= 5.1.38

1. Extract mysql-connector-java-&lt;version>-bin.jar (bundle) från arkivet

1. Använd webbkonsolen för att installera och starta paketet:

   * Till exempel http://localhost:4502/system/console/bundles
   * Välj **`Install/Update`**
   * Bläddra.. för att välja det paket som extraherats från det hämtade ZIP-arkivet
   * Kontrollera att *Oracle Corporations JDBC-drivrutin för MySQLcom.mysql.jdbc* är aktivt och starta det om inte (eller kontrollera loggarna)

1. Om du installerar på en befintlig distribution efter att JDBC har konfigurerats, binder du om JDBC till den nya anslutningen genom att spara om JDBC-konfigurationen från webbkonsolen:

   * Till exempel http://localhost:4502/system/console/configMgr
   * Sök `Day Commons JDBC Connections Pool` konfiguration
   * Markera för att öppna
   * Välj `Save`

1. Upprepa steg 3 och 4 för alla författare- och publiceringsinstanser

Mer information om hur du installerar paket finns på [Webbkonsol](/help/sites-deploying/web-console.md#bundles) sida.

#### Exempel: Installerat MySQL Connector-paket {#example-installed-mysql-connector-bundle}

![chlimage_1-410](assets/chlimage_1-410.png)

### SCORM-paket {#scorm-package}

SCORM (Shareable Content Object Reference Model) är en samling standarder och specifikationer för e-utbildning. SCORM definierar också hur innehåll kan paketeras i en överförbar ZIP-fil.

AEM Communities SCORM-motorn krävs för [aktivering](overview.md#enablement-community) -funktion. SCORM-paket som stöds i AEM Communities 6.4 är:

* **[cq -social- scorm -package, version 1.2.11](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-pkg)**. Det här SCORM-paketet stöds av alla versioner av AEM 6.4 Communities.

* **[cq -social-scorm -package, version 2.2.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg)** inkluderar [SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/) motor. SCORM-paketet stöds AEM 6.4.2.x Communities och senare.

För en ny installation av SCORM-motorn innehåller paketet [SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/) (som [  cq -social-scorm -package, version 2.2.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg)) ska användas. så att du kan spela upp utbildningsresurser som stöds av SCORM 2017.

<!--This section used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

### Så här installerar du ett SCORM-paket för första gången

1. Installera **[cq-social-scorm-package, version 2.2.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg).**
1. Hämta **`/libs/social/config/scorm/database_scormengine_data.sql`** från cq-instans och kör den på mysql-server för att skapa ett uppgraderat scormEngineDB-schema.
1. Lägg till `/content/communities/scorm/RecordResults` i egenskapen Exkluderade sökvägar i CSRF-filter från `https://<hostname>;:<port>/system/console/configMgr` på förlag.

Befintliga SCORM-installationer kan uppgraderas till [**cq-social-scorm-package, version 2.2.2**](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg) som använder [SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/)), om det redigerade kursinnehållet kräver SCORM 2017.1.

>[!NOTE]
>
>Uppgradering till SCORM 2017.1-paketet kräver migrering av den befintliga databasen (vilket förklaras ytterligare).

<!--This section used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

### Så här uppgraderar du en version av din SCORM-motor

1. Ta en säkerhetskopia av ScormEngineDB-schemat.
1. Installera **[cq-social-scorm-package, version 2.2.2](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fsocial%2Fscorm%2Fcq-social-scorm-2017-pkg).**
1. Hämta paketet från `/libs/social/config/scorm/ScormEngine.zip` och extrahera samma.
1. Gå till **Installationsprogram** mapp för den extraherade katalogen.
1. Uppdatera `SystemDatabaseConnectionString` med `scorm db connection url` i fil **[!UICONTROL EngineInstall.xml]**.
1. Kör verktyget för uppgradering av mysql-schema i installationsmappen med kommandot:

   `java -Dlogback.configurationFile=logback.xml -cp "lib/*" RusticiSoftware.ScormContentPlayer.Logic.Upgrade.ConsoleApp EngineInstall.xml`
1. Bildskärm `engine_upgrade.log` fil för alla typer av fel och schemauppgraderingsstatus.
1. Lägg till `/content/communities/scorm/RecordResults` in **[!UICONTROL Excluded Paths]** egenskap i CSRF-filter från `https://<hostname>:<port>/system/console/configMgr` på förlag.

### SCORM-loggning {#scorm-logging}

Alla aktiveringsaktiviteter loggas utförligt på systemkonsolen, som de är installerade.

Loggnivån kan vid behov ställas in på WARN för `RusticiSoftware.*` paket.

Information om hur du arbetar med loggar finns i [Arbeta med granskningsposter och loggfiler](../../help/sites-deploying/monitoring-and-maintaining.md#working-with-audit-records-and-log-files).

### AEM avancerad MLS {#aem-advanced-mls}

För att SRP-samlingen (MSRP eller DSRP) ska ha stöd för avancerad flerspråkig sökning (MLS) krävs nya Solr-plugin-program förutom ett anpassat schema och en Solr-konfiguration. Alla nödvändiga objekt paketeras i en nedladdningsbar zip-fil.

Den avancerade MLS-nedladdningen (kallas även &quot;phasetwo&quot;) är tillgänglig från Adobe-databasen:

* AEM-SOLR-MLS-phasetwo

   Information om hur du hämtar det avancerade MLS-paketet finns i [AEM avancerad MLS](deploy-communities.md#aem-advanced-mls) i distributionsavsnittet i dokumentationen.

   * Version 1.2.40, 6 april 2016
   * Ladda ned AEM-SOLR-MLS-phasetwo-1.2.40.zip

Mer information och installationsinformation finns på [Solr-konfiguration](solr.md) för SRP.

### Om länkar att paketera resurs {#about-links-to-package-share}

**Paket synliga i Adobe AEM Cloud**

Länkarna till paketen på den här sidan kräver ingen instans av AEM som körs eftersom de ska paketera delning på `adobeaemcloud.com`. Paketen kan visas, men `Install`är till för att installera paketen på en värdplats i Adobe. Om du tänker installera på en lokal AEM väljer du `Install`resulterar i ett fel.

**Installera på lokal AEM**

Installera de paket som visas i `adobeaemcloud.com` på en lokal AEM måste paketet först hämtas till en lokal disk:

* Välj **[!UICONTROL Assets]** tab
* Välj **[!UICONTROL download to disk]**

Använd pakethanteraren i den lokala AEM-instansen (till exempel [http://localhost:4502/crx/packmgr/](http://localhost:4502/crx/packmgr/)) för att överföra till den lokala AEM.

Du kan också komma åt paketet med hjälp av paketresursen från den lokala AEM-instansen (till exempel [http://localhost:4502/crx/packageshare/](http://localhost:4502/crx/packageshare/)), `Download`kommer att hämtas till den lokala AEM instansens paketdatabas.

När du är i den lokala AEM-instansens paketdatabas använder du pakethanteraren för att installera paketet.

Mer information finns på [Så här arbetar du med paket](../../help/sites-administering/package-manager.md#package-share).

## Rekommenderade distributioner {#recommended-deployments}

I AEM Communities används en gemensam butik för att lagra användargenererat innehåll (UGC) och kallas ofta för [lagringsresursprovider](working-with-srp.md). Rekommenderade distributionscenter när de väljer ett SRP-alternativ för den gemensamma butiken.

Den gemensamma lagringsplatsen har stöd för moderering och analys av användargenererat innehåll i publiceringsmiljön samtidigt som behovet av [replikering](sync.md) av UGC.

* [Community Content Store](working-with-srp.md): diskuterar SRP-lagringsalternativ för AEM communities

* [Rekommenderade topologier](topologies.md): diskuterar topologi som ska användas beroende på användningsfall och val av SRP

## Uppgraderar {#upgrading}

När du uppgraderar till AEM 6.4-plattformen från tidigare versioner av AEM är det viktigt att du läser Uppgradera till AEM 6.4.

Förutom att uppgradera plattformen kan du läsa [Uppgradera till AEM Communities 6.4](upgrade.md) om du vill veta mer om förändringar i communities.

## Konfigurationer {#configurations}

### Primär utgivare {#primary-publisher}

När den valda distributionen är en [publicera servergrupp](topologies.md#tarmk-publish-farm)måste en AEM publiceringsinstans identifieras som **`primary publisher`** för aktiviteter som inte ska förekomma i alla instanser, t.ex. funktioner som är beroende av **meddelanden** eller **Adobe Analytics**.

Som standard är `AEM Communities Publisher Configuration` OSGi-konfigurationen är konfigurerad med **`Primary Publisher`** kryssrutan är markerad så att alla publiceringsinstanser i en publiceringsgrupp identifierar sig själva som primär.

Det är därför nödvändigt att **redigera konfigurationen för alla sekundära publiceringsinstanser** för att avmarkera **`Primary Publisher`** kryssrutan.

![chlimage_1-411](assets/chlimage_1-411.png)

För alla andra (sekundära) publiceringsinstanser i en publiceringsgrupp:

* Logga in med administratörsbehörighet
* Öppna [webbkonsol](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel: [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Leta reda på `AEM Communities Publisher Configuration`
* Markera redigeringsikonen
* Avmarkera **[!UICONTROL Primary Publisher]** box
* Välj **[!UICONTROL Save]**

### Replikeringsagenter på författare {#replication-agents-on-author}

Replikering används för webbplatsinnehåll som skapas i publiceringsmiljön, t.ex. communitygrupper, samt för att hantera medlemmar och medlemsgrupper från författarmiljön med hjälp av [tunneltjänst](#tunnel-service-on-author).

För den primära utgivaren måste du se till att [Konfiguration för replikeringsagent](../../help/sites-deploying/replication.md) identifierar publiceringsservern och den behöriga användaren korrekt. Den standardauktoriserade användaren, `admin,` har redan rätt behörigheter (är medlem i `Communities Administrators`).

För att andra användare ska ha rätt behörigheter måste de läggas till som medlem i `administrators` användargrupp (även medlem av `Communities Administrators`).

Det finns två replikeringsagenter i författarmiljön som kräver att transportkonfigurationen är korrekt konfigurerad.

* Åtkomst till replikeringskonsolen på författaren

   * Från global navigering: **[!UICONTROL Tools > Deployment > Replication > Agents on author]**

* Följ samma procedur för båda agenterna:

   * **Standardagent (publicera)**
   * **Agenten för omvänd replikering (publicera omvänd)**

      1. Välj agent
      1. Välj **[!UICONTROL edit]**
      1. Välj **[!UICONTROL Transport]** tab
      1. If not port `4503`, redigera **[!UICONTROL URI]** för att ange rätt port
      1. Om ingen användare `admin`, redigera **[!UICONTROL User]** och **[!UICONTROL Password]** för att ange en medlem i `administrators` användargrupp

I följande bilder visas resultatet av att porten ändrats från 4503 till 6103 med:

#### Standardagent (publicera) {#default-agent-publish}

![chlimage_1-412](assets/chlimage_1-412.png)

#### Agenten för omvänd replikering (publicera omvänd) {#reverse-replication-agent-publish-reverse}

![chlimage_1-413](assets/chlimage_1-413.png)

### Tunneltjänst på författare {#tunnel-service-on-author}

När du använder redigeringsmiljön för att [skapa webbplatser](sites-console.md), [ändra webbplatsegenskaper](sites-console.md#modifying-site-properties) eller [hantera communitymedlemmar](members.md)måste du ha åtkomst till medlemmar (användare) som är registrerade i publiceringsmiljön, inte till användare som är registrerade hos författaren.

Tunneltjänsten ger denna åtkomst med replikeringsagenten på författaren.

Så här aktiverar du tunneltjänsten:

* På **författare**
* Logga in med administratörsbehörighet
* Om utgivaren inte är localhost:4503 eller transportanvändaren inte är `admin`,

   Sedan [konfigurera replikeringsagenten](#replication-agents-on-author)

* Öppna [Webbkonsol](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel: [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)

* Leta reda på `AEM Communities Publish Tunnel Service`
* Markera redigeringsikonen
* Kontrollera **[!UICONTROL enable]** box
* Välj **[!UICONTROL Save]**

![chlimage_1-414](assets/chlimage_1-414.png)

### Replikera krypteringsnyckeln {#replicate-the-crypto-key}

Det finns två funktioner i AEM Communities som kräver att alla AEM serverinstanser använder samma krypteringsnycklar. Dessa är [Analyser](analytics.md) och [ASRP](asrp.md).

Från och med AEM 6.3 lagras nyckelmaterialet i filsystemet och inte längre i databasen.

Om du vill kopiera nyckelmaterialet från författaren till alla andra instanser måste du:

* Få åtkomst till AEM, vanligtvis en författarinstans som innehåller det nyckelmaterial som ska kopieras

   * Leta reda på `com.adobe.granite.crypto.file` i det lokala filsystemet

      Till exempel,

      * `<author-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21`
      * The `bundle.info` filen identifierar paketet
   * Navigera till datamappen

      Till exempel,

      * `<author-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21/data`
   * Kopiera hmac- och primär nodfiler



* För varje AEM

   * Navigera till datamappen

      Till exempel,

      * `<publish-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21/data`
   * Klistra in de två tidigare kopierade filerna
   * Det är nödvändigt att [uppdatera Granite Crypto-paketet](#refresh-the-granite-crypto-bundle) om AEM körs


>[!CAUTION]
>
>Om en annan säkerhetsfunktion redan har konfigurerats som baseras på krypteringsnycklarna kan konfigurationen skadas om du replikerar krypteringsnycklarna. För assistans: [kontakta kundtjänst](https://helpx.adobe.com/marketing-cloud/contact-support.html).

#### Databasreplikering {#repository-replication}

Du kan behålla nyckelmaterialet som lagras i databasen, vilket var fallet i AEM 6.2 och tidigare, genom att ange följande systemegenskap vid första starten av varje AEM (som skapar den ursprungliga databasen):

* `-Dcom.adobe.granite.crypto.file.disable=true`

>[!NOTE]
>
>Det är viktigt att kontrollera att [replikeringsagent vid författare](#replication-agents-on-author) är korrekt konfigurerad.

Med nyckelmaterialet som lagras i databasen replikeras krypteringsnyckeln från författaren till andra instanser på följande sätt:

Använda [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* bläddra till [https://&lt;server>:&lt;port>/crx/de](http://localhost:4502/crx/de)
* välj `/etc/key`
* open `Replication` tab
* välj `Replicate`

* [uppdatera Granite Crypto-paketet](#refresh-the-granite-crypto-bundle)

![chlimage_1-415](assets/chlimage_1-415.png)

#### Uppdatera Granite Crypto Bundle {#refresh-the-granite-crypto-bundle}

* I varje publiceringsinstans kan du öppna [Webbkonsol](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel: [https://&lt;server>:&lt;port>/system/console/bundles](http://localhost:4503/system/console/bundles)

* Sök `Adobe Granite Crypto Support` bundle (com.adobe.granite.crypto)
* Välj **[!UICONTROL Refresh]**

![chlimage_1-416](assets/chlimage_1-416.png)

* Efter ett ögonblick **Lyckades** visas:

   `Operation completed successfully.`

### Apache HTTP-server {#apache-http-server}

Om du använder Apache HTTP-servern måste du använda rätt servernamn för alla relevanta poster.

Var särskilt försiktig med att använda rätt servernamn, inte `localhost`, i `RedirectMatch`.

#### httpd.conf-exempel {#httpd-conf-sample}

```shell
<IfModule alias_module>
     # XAMPP does not have a favicon; this prevents any 404 errors which may arise.
     Redirect 404 /favicon.ico
     <Location /favicon.ico>
         ErrorDocument 404 "No favicon"
     </Location>

    # Return from "Sign Out" generates response header directing you to "/", generating a 404 error
    # The RedirectMatch resolves it correctly when modified for the target Community Site:
    RedirectMatch ^/$ https://[server name]/content/sites/engage/en.html
 ...
 </IfModule>
```

### Dispatcher {#dispatcher}

Om du använder en Dispatcher läser du:

* AEM [Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher.html) dokumentation
* [Installerar Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher-install.html)
* [Konfigurera Dispatcher för Communities](dispatcher.md)
* [Kända fel](troubleshooting.md#dispatcher-refetch-fails)

## Dokumentation för relaterade communities {#related-communities-documentation}

* Besök [Administrera webbgruppsplatser](administer-landing.md) om du vill veta mer om hur du skapar en community-webbplats, konfigurerar mallar för communitysajter, modererar communityinnehåll, hanterar medlemmar och konfigurerar meddelanden.

* Besök [Utveckla webbgrupper](communities.md) om du vill veta mer om ramverket för sociala komponenter (SCF) och hur du anpassar komponenter och funktioner i Communities.

* Besök [Komponenter i redigeringsgrupper](author-communities.md) om du vill lära dig hur du redigerar med och konfigurerar Communities-komponenter.
