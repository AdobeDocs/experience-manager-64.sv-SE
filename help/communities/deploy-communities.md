---
title: Distribuera webbgrupper
seo-title: Distribuera webbgrupper
description: Så här distribuerar du AEM Communities
seo-description: Så här distribuerar du AEM Communities
uuid: 1f7faf1a-a339-4eaa-b728-b9110cb350a8
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: deploying
discoiquuid: d0249609-2a9c-4d3b-92ee-dbc5fbdeaac6
translation-type: tm+mt
source-git-commit: 8c66f2b0053882bd1c998d8e01dbb0573881bc87

---


# Distribuera webbgrupper {#deploying-communities}

## Förutsättningar {#prerequisites}

* [AEM 6.4 Platform](../../help/sites-deploying/deploy.md)

* AEM Communities-licens

* Ytterligare licenser för:

   * [Funktioner i Adobe Analytics for Communities](analytics.md)
   * [MongoDB för MSRP](msrp.md)
   * [Adobe Cloud för ASRP](asrp.md)

## Checklista för installation {#installation-checklist}

**För[AEM-plattformen](../../help/sites-deploying/deploy.md#what-is-aem)**

* Installera de senaste [AEM 6.4-uppdateringarna](#aem-updates)

* Om du inte använder standardportarna (4502, 4503) [konfigurerar du replikeringsagenter](#replication-agents-on-author)
* [replikera krypteringsnyckeln](#replicate-the-crypto-key)
* Om det finns stöd för globalisering kan du [konfigurera automatisk översättning](../../help/sites-administering/translation.md)

   (exempelinställningar tillhandahålls för utveckling)

**För[communityfunktionen](overview.md)**

* Om du distribuerar en [publiceringsgrupp](../../help/sites-deploying/recommended-deploys.md#tarmk-farm)[identifierar du den primära utgivaren](#primary-publisher)

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
         * UGC är bara synligt på AEM-instansen eller klustret där det angavs
      * Standard är JSRP
   För **[aktiveringsfunktionen](overview.md#enablement-community)**

   * [Installera och konfigurera FFmpeg](ffmpeg.md)
   * [Installera JDBC-drivrutinen för MySQL](#jdbc-driver-for-mysql)
   * [Installera AEM Communities SCORM-Engine](#scorm-package)
   * [Installera och konfigurera MySQL för aktivering](mysql.md)






## Senaste releaser {#latest-releases}

AEM 6.4 Communities GA levereras med Communities-paket. Om du vill veta mer om uppdateringar av AEM 6.4- [communityn](/help/release-notes/release-notes.md#experience-manager-communities)kan du läsa [AEM 6.4 Release Notes](/help/release-notes/release-notes.md#release-information).

### AEM 6.4 - uppdateringar {#aem-updates}

Från och med AEM 6.3 levereras uppdateringar av Communities som en del av AEM Cumulative Fix Packs och Service Packs.

För de senaste uppdateringarna av AEM 6.4, se till att kontrollera [Adobe Experience Manager 6.4 Cumulative Fix Packs och Service Packs](https://helpx.adobe.com/experience-manager/aem-releases-updates.html).

### Versionshistorik {#version-history}

Precis som med AEM 6.4 och senare är AEM Communities-funktioner och snabbkorrigeringar en del av AEM Communities kumulativa korrigeringspaket och servicepaket. Det finns därför inga separata funktionspaket.

### JDBC-drivrutin för MySQL {#jdbc-driver-for-mysql}

Två Communities-funktioner använder en MySQL-databas:

* För [aktivering](enablement.md): spela in SCORM-aktiviteter
* För [DSRP](dsrp.md): lagra användargenererat innehåll (UGC)

MySQL-kopplingen måste hämtas och installeras separat.

Nödvändiga steg är:

1. Hämta ZIP-arkivet från [https://dev.mysql.com/downloads/connector/j/](https://dev.mysql.com/downloads/connector/j/)

   * Versionen måste vara >= 5.1.38

1. Extrahera mysql-connector-java-&lt;version>-bin.jar (bundle) från arkivet

1. Använd webbkonsolen för att installera och starta paketet:

   * Till exempel http://localhost:4502/system/console/bundles
   * Välj **`Install/Update`**
   * Bläddra.. för att välja det paket som extraherats från det hämtade ZIP-arkivet
   * Kontrollera att *Oracle Corporations JDBC-drivrutin för MySQLcom.mysql.jdbc* är aktiv och starta den om inte (eller kontrollera loggarna)

1. Om du installerar på en befintlig distribution efter att JDBC har konfigurerats, binder du om JDBC till den nya anslutningen genom att spara om JDBC-konfigurationen från webbkonsolen:

   * Till exempel http://localhost:4502/system/console/configMgr
   * Hitta `Day Commons JDBC Connections Pool` konfigurationen
   * Markera för att öppna
   * Välj `Save`

1. Upprepa steg 3 och 4 för alla författare- och publiceringsinstanser

Mer information om hur du installerar paket finns på [webbkonsolsidan](../../help/sites-deploying/configuring-web-console.md#bundles) .

#### Exempel: Installerat MySQL Connector-paket {#example-installed-mysql-connector-bundle}

![chlimage_1-410](assets/chlimage_1-410.png)

### SCORM-paket {#scorm-package}

SCORM (Shareable Content Object Reference Model) är en samling standarder och specifikationer för e-utbildning. SCORM definierar också hur innehåll kan paketeras i en överförbar ZIP-fil.

AEM Communities SCORM-motorn krävs för [aktiveringsfunktionen](overview.md#enablement-community) . SCORM-paket som stöds på AEM Communities 6.4-versionen är:

* **[cq -social- scorm -package, version 1.2.11](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/social/scorm/cq-social-scorm-pkg)**. SCORM-paketet stöds av alla AEM 6.4 Communities-versioner.

* **[cq -social- scorm -package, version 2.2.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/social/scorm/cq-social-scorm-2017-pkg)**includes[SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/)engine. SCORM-paketet stöds från och med AEM 6.4.2.x Communities.

För en ny installation av SCORM-motorn bör paketet som innehåller [SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/) (som är [ cq -social- scorm -package, version 2.2.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/social/scorm/cq-social-scorm-2017-pkg)) användas. så att du kan spela upp utbildningsresurser som stöds av SCORM 2017.

<!--This section used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

### Så här installerar du ett SCORM-paket för första gången

1. Installera **[cq-social-scorm-paketet, version 2.2.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/social/scorm/cq-social-scorm-2017-pkg).**
1. Hämta **`/libs/social/config/scorm/database_scormengine_data.sql`** från cq-instansen och kör den på mysql-servern för att skapa ett uppgraderat scormEngineDB-schema.
1. Lägg till `/content/communities/scorm/RecordResults` i egenskapen Undantagna sökvägar i CSRF-filter från `https://<hostname>;:<port>/system/console/configMgr` utgivare.

Befintliga SCORM-installationer kan uppgraderas till [**cq-social-scorm-package, version 2.2.2 **](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/social/scorm/cq-social-scorm-2017-pkg)(som använder[SCORM 2017.1](https://rusticisoftware.com/blog/scorm-engine-2017-released/)) om det redigerade kursinnehållet kräver SCORM 2017.1.

>[!NOTE]
>
>Uppgradering till SCORM 2017.1-paketet kräver migrering av den befintliga databasen (vilket förklaras ytterligare).

<!--This section used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

### Så här uppgraderar du en version av din SCORM-motor

1. Ta en säkerhetskopia av ScormEngineDB-schemat.
1. Installera **[cq-social-scorm-paketet, version 2.2.2](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/social/scorm/cq-social-scorm-2017-pkg).**
1. Hämta paketet från `/libs/social/config/scorm/ScormEngine.zip` och extrahera det.
1. Gå till mappen **Installer** i den extraherade katalogen.
1. Uppdatera `SystemDatabaseConnectionString` med din `scorm db connection url` i file **[!UICONTROL EngineInstall.xml]**.
1. Kör verktyget för uppgradering av mysql-schema i installationsmappen med kommandot:

   `java -Dlogback.configurationFile=logback.xml -cp "lib/*" RusticiSoftware.ScormContentPlayer.Logic.Upgrade.ConsoleApp EngineInstall.xml`
1. Övervaka `engine_upgrade.log` filen för alla typer av fel och schemauppgraderingsstatus.
1. Lägg till `/content/communities/scorm/RecordResults` i egenskapen **[!UICONTROL Uteslutna sökvägar]** i CSRF-filter från `https://<hostname>:<port>/system/console/configMgr` utgivare.

### SCORM-loggning {#scorm-logging}

Alla aktiveringsaktiviteter loggas utförligt på systemkonsolen, som de är installerade.

Om du vill kan du ställa in loggnivån på WARN för `RusticiSoftware.*` paketet.

Mer information om hur du arbetar med loggar finns i [Arbeta med granskningsposter och loggfiler](../../help/sites-deploying/monitoring-and-maintaining.md#working-with-audit-records-and-log-files).

### AEM Advanced MLS {#aem-advanced-mls}

För att SRP-samlingen (MSRP eller DSRP) ska ha stöd för avancerad flerspråkig sökning (MLS) krävs nya Solr-plugin-program förutom ett anpassat schema och en Solr-konfiguration. Alla nödvändiga objekt paketeras i en nedladdningsbar zip-fil.

Den avancerade MLS-nedladdningen (kallas även &quot;phasetwo&quot;) finns tillgänglig från Adobe-databasen:

* [AEM-SOLR-MLS-phasetwo](https://repo.adobe.com/nexus/content/repositories/releases/com/adobe/tat/AEM-SOLR-MLS-phasetwo/1.2.40/)

   * Version 1.2.40, 6 april 2016
   * Ladda ned AEM-SOLR-MLS-phasetwo-1.2.40.zip

Mer information och installationsinformation finns på [Solr Configuration](solr.md) for SRP.

### Om länkar att paketera resurs {#about-links-to-package-share}

**Synliga paket i Adobe AEM Cloud**

Länkarna till paketen på den här sidan kräver ingen instans av AEM som körs eftersom de ska paketera delning på `adobeaemcloud.com`. Paketen kan visas, men `Install`knappen används för att installera paketen på en Adobe-värdplats. Om du tänker installera på en lokal AEM-instans `Install`uppstår ett fel om du väljer det.

**Installera på lokal AEM-instans**

Om du vill installera de paket som visas i `adobeaemcloud.com` en lokal AEM-instans måste paketet först hämtas till en lokal disk:

* Välj fliken **[!UICONTROL Resurser]**
* Välj **[!UICONTROL Hämta till disk]**

På den lokala AEM-instansen använder du pakethanteraren (till exempel [http://localhost:4502/crx/packmgr/](http://localhost:4502/crx/packmgr/)) för att överföra till den lokala AEM-paketdatabasen.

Om du använder paketet med hjälp av paketresursen från den lokala AEM-instansen (till exempel [http://localhost:4502/crx/packageshare/](http://localhost:4502/crx/packageshare/)) hämtas `Download`knappen till den lokala AEM-instansens paketdatabas.

När du är i den lokala AEM-instansens paketdatabas använder du pakethanteraren för att installera paketet.

Mer information finns i [Arbeta med paket](../../help/sites-administering/package-manager.md#package-share).

## Rekommenderade distributioner {#recommended-deployments}

I AEM Communities används en gemensam butik för att lagra användargenererat innehåll (UGC) och kallas ofta [lagringsresursleverantör (SRP)](working-with-srp.md). Rekommenderade distributionscenter när de väljer ett SRP-alternativ för den gemensamma butiken.

Den gemensamma lagringsplatsen stöder moderering av och analys av UGC i publiceringsmiljön samtidigt som behovet av [replikering](sync.md) av UGC elimineras.

* [Community Content Store](working-with-srp.md): diskuterar SRP-lagringsalternativ för AEM-communities

* [Rekommenderade topologier](topologies.md): diskuterar topologi som ska användas beroende på användningsfall och val av SRP

## Uppgraderar {#upgrading}

När du uppgraderar till AEM 6.4-plattformen från tidigare versioner av AEM är det viktigt att du läser Uppgradera till AEM 6.4.

Förutom att uppgradera plattformen kan du läsa [Uppgradera till AEM Communities 6.4](upgrade.md) för att få information om communityförändringar.

## Konfigurationer {#configurations}

### Primär utgivare {#primary-publisher}

När den valda distributionen är en [publiceringsgrupp](topologies.md#tarmk-publish-farm)måste en AEM-publiceringsinstans identifieras som **`primary publisher`** för aktiviteter som inte ska förekomma i alla instanser, till exempel funktioner som kräver **meddelanden** eller **Adobe Analytics**.

Som standard är `AEM Communities Publisher Configuration` OSGi-konfigurationen konfigurerad med kryssrutan **`Primary Publisher`** markerad, så att alla publiceringsinstanser i en publiceringsgrupp identifierar sig själva som primär.

Det är därför nödvändigt att **redigera konfigurationen för alla sekundära publiceringsinstanser** för att avmarkera **`Primary Publisher`** kryssrutan.

![chlimage_1-411](assets/chlimage_1-411.png)

För alla andra (sekundära) publiceringsinstanser i en publiceringsgrupp:

* Logga in med administratörsbehörighet
* Åtkomst till [webbkonsolen](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Leta reda på `AEM Communities Publisher Configuration`
* Markera redigeringsikonen
* Avmarkera rutan **[!UICONTROL Primär utgivare]**
* Välj **[!UICONTROL Spara]**

### Replikeringsagenter på författare {#replication-agents-on-author}

Replikering används för webbplatsinnehåll som skapas i publiceringsmiljön, t.ex. communitygrupper, samt för att hantera medlemmar och medlemsgrupper från författarmiljön med hjälp av [tunneltjänsten](#tunnel-service-on-author).

För den primära utgivaren måste du se till att [replikeringsagentkonfigurationen](../../help/sites-deploying/replication.md) identifierar publiceringsservern och den behöriga användaren korrekt. Den auktoriserade standardanvändaren har `admin,` redan rätt behörigheter (är medlem i `Communities Administrators`).

För att en annan användare ska ha rätt behörigheter måste de läggas till som medlem i `administrators` användargruppen (även som medlem i `Communities Administrators`).

Det finns två replikeringsagenter i författarmiljön som kräver att transportkonfigurationen är korrekt konfigurerad.

* Åtkomst till replikeringskonsolen på författaren

   * Från global navigering: **[!UICONTROL Verktyg > Distribution > Replikering > Agenter på författare]**

* Följ samma procedur för båda agenterna:

   * **Standardagent (publicera)**
   * **Agenten för omvänd replikering (publicera omvänd)**

      1. Välj agent
      1. Markera **[!UICONTROL redigering]**
      1. Välj fliken **[!UICONTROL Transport]**
      1. Om porten inte `4503`finns kan du redigera **[!UICONTROL URI]** för att ange rätt port
      1. Om användaren inte `admin`gör det redigerar du **[!UICONTROL Användare]** och **[!UICONTROL lösenord]** för att ange en medlem i `administrators` användargruppen

I följande bilder visas resultatet av en ändring av porten från 4503 till 6103 med:

#### Standardagent (publicera) {#default-agent-publish}

![chlimage_1-412](assets/chlimage_1-412.png)

#### Agenten för omvänd replikering (publicera omvänd) {#reverse-replication-agent-publish-reverse}

![chlimage_1-413](assets/chlimage_1-413.png)

### Tunneltjänst på författare {#tunnel-service-on-author}

När du använder författarmiljön för att [skapa webbplatser](sites-console.md), [ändra webbplatsegenskaper](sites-console.md#modifying-site-properties) eller [hantera communitymedlemmar](members.md)måste du ha tillgång till medlemmar (användare) som är registrerade i publiceringsmiljön, inte användare som är registrerade på författaren.

Tunneltjänsten ger denna åtkomst med replikeringsagenten på författaren.

Så här aktiverar du tunneltjänsten:

* On **author**
* Logga in med administratörsbehörighet
* Om utgivaren inte är localhost:4503 eller om transportanvändaren inte är `admin`det,

   Konfigurera sedan [replikeringsagenten](#replication-agents-on-author)

* Åtkomst till [webbkonsolen](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel [http://localhost:4502/system/console/configMgr](http://localhost:4502/system/console/configMgr)

* Leta reda på `AEM Communities Publish Tunnel Service`
* Markera redigeringsikonen
* Markera **[!UICONTROL aktiveringsrutan]**
* Välj **[!UICONTROL Spara]**

![chlimage_1-414](assets/chlimage_1-414.png)

### Replikera krypteringsnyckeln {#replicate-the-crypto-key}

Det finns två funktioner i AEM Communities som kräver att alla AEM-serverinstanser använder samma krypteringsnycklar. Dessa är [Analytics](analytics.md) och [ASRP](asrp.md).

Från och med AEM 6.3 lagras nyckelmaterialet i filsystemet och inte längre i databasen.

Om du vill kopiera nyckelmaterialet från författaren till alla andra instanser måste du:

* Få åtkomst till AEM-instansen, vanligtvis en författarinstans, som innehåller det nyckelmaterial som ska kopieras

   * Hitta paketet i det lokala filsystemet `com.adobe.granite.crypto.file`

      Exempel:

      * `<author-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21`
      * Filen identifierar `bundle.info` paketet
   * Navigera till datamappen

      Exempel:

      * `<author-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21/data`
   * Kopiera hmac- och mallfilerna



* För varje AEM-målinstans

   * Navigera till datamappen

      Exempel:

      * `<publish-aem-install-dir>/crx-quickstart/launchpad/felix/bundle21/data`
   * Klistra in de två tidigare kopierade filerna
   * Du måste [uppdatera Granite-krypteringspaketet](#refresh-the-granite-crypto-bundle) om AEM-målinstansen körs


>[!CAUTION]
>
>Om en annan säkerhetsfunktion redan har konfigurerats som baseras på krypteringsnycklarna kan konfigurationen skadas om du replikerar krypteringsnycklarna. Om du behöver hjälp [kontaktar du kundtjänst](https://helpx.adobe.com/marketing-cloud/contact-support.html).

#### Databasreplikering {#repository-replication}

Att ha nyckelmaterialet lagrat i databasen, som var fallet i AEM 6.2 och tidigare, kan bevaras genom att ange följande systemegenskap vid första starten av varje AEM-instans (som skapar den ursprungliga databasen):

* `-Dcom.adobe.granite.crypto.file.disable=true`

>[!NOTE]
>
>Det är viktigt att kontrollera att [replikeringsagenten på författaren](#replication-agents-on-author) är korrekt konfigurerad.

Med nyckelmaterialet som lagras i databasen replikeras krypteringsnyckeln från författaren till andra instanser på följande sätt:

Använda [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* gå till [https://&lt;server>:&lt;port>/crx/de](http://localhost:4502/crx/de)
* select `/etc/key`
* öppna `Replication` flik
* select `Replicate`

* [uppdatera Granite Crypto-paketet](#refresh-the-granite-crypto-bundle)

![chlimage_1-415](assets/chlimage_1-415.png)

#### Uppdatera Granite Crypto Bundle {#refresh-the-granite-crypto-bundle}

* Gå till [webbkonsolen för varje publiceringsinstans](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel [https://&lt;server>:&lt;port>/system/console/bundles](http://localhost:4503/system/console/bundles)

* Hitta `Adobe Granite Crypto Support` paketet (com.adobe.granite.crypto)
* Välj **[!UICONTROL Uppdatera]**

![chlimage_1-416](assets/chlimage_1-416.png)

* Efter en stund visas dialogrutan **Slutfört** :

   `Operation completed successfully.`

### Apache HTTP-server {#apache-http-server}

Om du använder Apache HTTP-servern måste du använda rätt servernamn för alla relevanta poster.

Var särskilt försiktig med att använda rätt servernamn, inte `localhost`i `RedirectMatch`.

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

* AEM&#39;s [Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher.html) documentation
* [Installerar Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher-install.html)
* [Konfigurera Dispatcher för Communities](dispatcher.md)
* [Kända fel](troubleshooting.md#dispatcher-refetch-fails)

## Dokumentation för relaterade communities {#related-communities-documentation}

* Besök [Administrera communitysajter](administer-landing.md) om du vill veta mer om hur du skapar en community-webbplats, konfigurerar mallar för communitysajter, modererar communityinnehåll, hanterar medlemmar och konfigurerar meddelanden.

* Besök [Utvecklingsgrupper](communities.md) om du vill veta mer om ramverket för sociala komponenter (SCF) och hur du anpassar komponenter och funktioner i Communities.

* Besök [Authoring Communities Components](author-communities.md) om du vill veta mer om hur du skapar med och konfigurerar Communities-komponenter.

