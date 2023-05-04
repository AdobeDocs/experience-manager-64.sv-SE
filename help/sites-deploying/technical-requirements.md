---
title: Tekniska krav
seo-title: Technical Requirements
description: En lista över de klient- och serverplattformar som stöds för AEM.
seo-description: A list of the supported client and server platforms for AEM.
uuid: d5bdcd41-3585-41f7-860d-8068a2931a72
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: platform
discoiquuid: 4d3c4650-3e2a-43b1-ad2d-8d0ae2254ca9
exl-id: 21c10b39-ca37-4085-86f8-063c30a180ed
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '3294'
ht-degree: 0%

---

# Tekniska krav{#technical-requirements}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe stöder Adobe Experience Manager (AEM) på plattformarna enligt följande information i det här dokumentet.

Kontakta plattformsleverantören direkt om du har frågor som är specifikt relaterade till själva plattformen.

>[!NOTE]
>
>Beroende på vilken plattform du installerar AEM på kan det finnas olika uppsättningar krav för användarhantering.

## Förutsättningar {#prerequisites}

Lägsta krav för installation av Adobe Experience Manager:

* Installerad Java Platform, Standard Edition JDK eller annat som stöds [Java Virtual Machines](#java-virtual-machines)
* Experience Manager QuickStart-fil (fristående JAR eller WAR för webbapplikationsdistribution)

### Krav för minsta storlek {#minimum-sizing-requirements}

Lägsta krav för att köra Adobe Experience Manager:

* 5 GB ledigt diskutrymme i installationskatalogen
* 2 GB minne

>[!NOTE]
>
>* Användningsexempel för digitala resurser kräver mer basminne. Se [Driftsättning och underhåll](/help/sites-deploying/deploy.md#default-local-install) för mer information.
>* [AEM Forms tilläggspaket](/help/forms/using/installing-configuring-aem-forms-osgi.md) kräver 15 GB temporärt utrymme.
>


Se [Riktlinjer för maskinvarans storlek](/help/managing/hardware-sizing-guidelines.md) för ytterligare information.

### Supportnivåer {#support-levels}

I det här dokumentet visas vilka klient- och serverplattformar som stöds för Adobe Experience Manager. Adobe har flera supportnivåer, både för rekommenderade konfigurationer och andra konfigurationer.

### Konfigurationer som stöds {#supported-configurations}

Adobe rekommenderar dessa konfigurationer och ger full support som en del av standardavtalet för programunderhåll.

<table> 
 <tbody> 
  <tr> 
   <td>Supportnivå</td> 
   <td>Beskrivning<br /> </td> 
  </tr> 
  <tr> 
   <td><strong>S: Stöds</strong></td> 
   <td>Adobe ger fullständigt stöd och underhåll för den här konfigurationen. Den här konfigurationen omfattas av Adobe kvalitetssäkringsprocess.</td> 
  </tr> 
  <tr> 
   <td><strong>R: Begränsat stöd</strong></td> 
   <td>För att våra kunder ska lyckas erbjuder Adobe full support inom ett begränsat supportprogram, vilket kräver att specifika villkor uppfylls. Support på R-nivå kräver en formell kundförfrågan och en bekräftelse från Adobe. Kontakta Adobe kundtjänst om du vill ha mer information.</td> 
  </tr> 
 </tbody> 
</table>

### Konfigurationer som inte stöds {#unsupported-configurations}

| Supportnivå | Beskrivning |
|---|---|
| **Z: Stöds inte** | Konfigurationen stöds inte. Adobe har inga programsatser om huruvida konfigurationen fungerar eller inte. |

## Plattformar som stöds {#supported-platforms}

### Java Virtual Machines {#java-virtual-machines}

Programmet kräver att en Java Virtual Machine körs, vilket tillhandahålls av JDK-distributionen (Java Development Kit).

Adobe Experience Manager arbetar med följande versioner av Java Virtual Machines:

>[!CAUTION]
>
>Vi rekommenderar att du följer säkerhetsbulletinerna från Java-leverantören för att säkerställa säkerheten i produktionsmiljöer och installerar de senaste Java-uppdateringarna.

<table> 
 <tbody> 
  <tr> 
   <td>Plattform</td> 
   <td>Supportnivå<br /> </td> 
  </tr> 
  <tr> 
   <td>Oracle Java SE 11 JDK [1]</td> 
   <td>Z: Stöds inte </td> 
  </tr> 
  <tr> 
   <td>Oracle Java SE 10 JDK [1]</td> 
   <td>Z: Stöds inte </td> 
  </tr> 
  <tr> 
   <td>Oracle Java SE 9 JDK [1]</td> 
   <td>Z: Stöds inte</td> 
  </tr> 
  <tr> 
   <td><strong>Oracle Java SE 8 JDK - 64 bitar</strong></td> 
   <td>S: Stöds [3]<br /> </td> 
  </tr> 
  <tr> 
   <td>IBM J9 VM - build 2.9, JRE 1.8.0 [2]</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>IBM J9 VM - build 2.8, JRE 1.8.0 [2]</td> 
   <td>S: Stöds</td> 
  </tr> 
 </tbody> 
</table>

1. Oraclet har flyttat till en LTS-modell (Long Term Support) för Oracle Java SE-produkter. Java 9 och 10 är icke-LTS-versioner som Oracle (se [Oracle Java SE - supportöversikt](https://www.oracle.com/technetwork/java/eol-135779.html)). Adobe tillhandahåller endast stöd för LTS-versioner av Java för AEM i produktionen.

1. IBM JRE stöds endast i kombination med WebSphere Application Server.
1. Stöd för och distribution av Oraclet Java SE JDK, inklusive alla underhållsuppdateringar av LTS-releaser efter slutet av de offentliga uppdateringarna, kommer att stödjas av Adobe direkt för alla AEM som använder Oraclet Java SE. Se [Stöd för Oracle Java i Adobe Experience Manager Q&amp;A](assets/adobe-oracle-java-license-agreement.pdf) för mer information.

### Lagring och beständighet {#storage-persistence}

Det finns olika alternativ för att distribuera Adobe Experience Manager-databasen. Se följande lista för de tekniker och lagringsalternativ som stöds.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Plattform</strong></td> 
   <td><strong>Beskrivning</strong></td> 
   <td><strong>Supportnivå</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Filsystem med TAR-filer [1]</strong></td> 
   <td>Databas</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td><strong>Filsystem med datastore [1]</strong></td> 
   <td>Binärfiler</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Lagra binärfiler i TAR-filer i filsystemet [1]</td> 
   <td>Binärfiler</td> 
   <td>Z: Stöds inte för produktion</td> 
  </tr> 
  <tr> 
   <td>Amazon S3</td> 
   <td>Binärfiler</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Microsoft Azure Blob Storage</td> 
   <td>Binärfiler</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>MongoDB Enterprise 3.6 [5, 6]</td> 
   <td>Databas</td> 
   <td>S: Stöds med begränsningar</td> 
  </tr> 
  <tr> 
   <td>MongoDB Enterprise 3.4 [2, 3, 6]</td> 
   <td>Databas</td> 
   <td>S: Stöds med begränsningar</td> 
  </tr> 
  <tr> 
   <td>MySQL 5.7</td> 
   <td>Forms-databas</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>IBM DB2 11.1<br /> </td> 
   <td>Forms-databas</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>IBM DB2 10.5</td> 
   <td>Databas och databas för Forms</td> 
   <td>R: Begränsat stöd (4)</td> 
  </tr> 
  <tr> 
   <td>Oracle Database 12c (12.1.x)</td> 
   <td>Databas och databas för Forms</td> 
   <td>R: Begränsat stöd</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2017</td> 
   <td>Forms-databas</td> 
   <td>Z: Stöds inte (4)</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2016</td> 
   <td>Forms-databas</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Microsoft SQL Server 2014</td> 
   <td>Forms-databas</td> 
   <td>R: Begränsat stöd (4)</td> 
  </tr> 
  <tr> 
   <td><strong>Apache Lucene (inbyggt i Quickstart)</strong></td> 
   <td>Söktjänst</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Apache Solr</td> 
   <td>Söktjänst</td> 
   <td>S: Stöds</td> 
  </tr> 
 </tbody> 
</table>

1. &#39;Filsystem&#39; inkluderar blocklagring som är POSIX-kompatibel. Detta inkluderar nätverkslagringsteknik. Tänk på att filsystemets prestanda kan variera och påverka den övergripande prestandan. Vi rekommenderar att du läser in AEM i kombination med nätverks-/fjärrfilsystemet.
1. MongoDB-delning stöds inte i AEM.
1. MongoDB-lagringsmotorn WiredTiger stöds endast.
1. Stöds inte för AEM Forms.
1. MongoDB Enterprise 3.6 stöds från och med AEM version 6.4.2.0.
1. Stödet för MongoDB 3.4 har nått slutet av livscykeln (EOL), medan MongoDB 3.6 förväntas nå EOL den 30 april 2021. Observera att Adobe endast kommer att ge support för AEM produktrelaterade frågor under framtidens gång.

>[!NOTE]
>
>Se [Distribuera webbgrupper](/help/communities/deploy-communities.md) om du vill ha mer information om AEM Communities.

>[!NOTE]
>
>MongoDB är en tredjepartsprogramvara och ingår inte i AEM licenspaket. Mer information finns i [MongoDB-licenspolicy](https://www.mongodb.org/about/licensing/) sida.
>
>För att få ut så mycket som möjligt av er AEM med MongoDB rekommenderar Adobe att ni licensierar MongoDB Enterprise-versionen för att få tillgång till professionell support. Se [Rekommenderade distributioner](/help/sites-deploying/recommended-deploys.md#prerequisites-and-recommendations-when-deploying-aem-with-mongomk) för mer information.
>
>Licensen innehåller en standarduppsättning av repliker, som består av en primär och två sekundära instanser som kan användas för antingen författaren eller publiceringsdistributionerna.
>
>Om du vill köra både författaren och publicera på MongoDB måste du köpa två separata licenser.
>
>Adobe kundtjänst kommer att hjälpa dig med kvalificeringsproblem i samband med användningen av MongoDB med AEM.
>
>Mer information finns i [MongoDB för Adobe Experience Manager](https://www.mongodb.com/lp/contact/mongodb-adobe-experience-manager).

>[!NOTE]
>
>De relationsdatabaser som stöds ovan är tredjepartsprogram och ingår inte i AEM licenspaket.
>
>För att kunna köra AEM 6.4 med en relationsdatabas som stöds krävs ett separat supportavtal med en databasleverantör. Adobe kundtjänst kommer att hjälpa dig med kvalificeringsproblem i samband med användning av relationsdatabaser med AEM 6.4.
>
>**Observera att de flesta relationsdatabaser för närvarande stöds i Level-R på AEM 6.4, som innehåller stödkriterier och ett supportprogram enligt beskrivningen ovan.**

### Servletmotorer/programservrar {#servlet-engines-application-servers}

Adobe Experience Manager kan köras antingen som en fristående server (snabbstart-JAR-filen) eller som ett webbprogram på en tredjepartsprogramserver (WAR-filen).

Den lägsta servlet API-version som krävs är Servlet 3.1, men under Servlet 4.0.

| Plattform | Supportnivå |
|---|---|
| **Quickstart inbyggd servermotor (Jetty 9.3)** | S: Stöds |
| Oracle WebLogic Server 12.2 (12cR2) | S: Stöds |
| IBM WebSphere Application Server Continuous Delivery (LibertyProfile) med Web Profile 7.0 och IBM JRE 1.8 | S: Stöds |
| IBM WebSphere Application Server 9.0 | S: Stöds |
| Apache Tomcat 8.5.x | S: Stöds |
| JBoss EAP 7.1.0 med JBoss Application Server | S: Stöds (1) |
| JBoss EAP 7.0.0 med JBoss Application Server | S: Stöds |

1. Stöds inte för AEM Forms.

### Operativsystem för servrar {#server-operating-systems}

Adobe Experience Manager fungerar med följande serverplattformar:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Plattform</strong></td> 
   <td><strong>Supportnivå</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Linux, baserat på Red Hat-distribution</strong></td> 
   <td>S: Stöds (1)</td> 
  </tr> 
  <tr> 
   <td>Linux baserat på Debian-distribution inkl. Ubuntu</td> 
   <td>S: Stöds (4)</td> 
  </tr> 
  <tr> 
   <td>Linux, baserat på SUSE-distribution</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Microsoft Windows Server 2016</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Microsoft Windows Server 2012 R2</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Oracle Solaris 11</td> 
   <td>S: Stöds med begränsningar (3,5,7)<br /> R: Begränsad support för nya kontrakt</td> 
  </tr> 
  <tr> 
   <td>IBM AIX 7.2</td> 
   <td>S: Stöds med begränsningar (2,5,7)<br /> R: Begränsad support för nya kontrakt</td> 
  </tr> 
 </tbody> 
</table>

1. Linux Kernel 2.6, 3.x och 4.x innehåller derivat från Red Hat-distributionen, inklusive Red Hat Enterprise Linux, CentOS, Oracle Linux och Amazon Linux. AEM Forms tilläggsfunktioner stöds endast i CentOS 7 och Red Hat Enterprise Linux 7.
1. AEM Assets: Se avsnittet [Stöd för XMP metadata-återskrivning](#requirements-for-aem-assets-xmp-metadata-write-back)
1. AEM Assets: Dynamic Media Imaging stöds inte. Dynamic Media Video stöds.
1. AEM Forms stöds bara på Ubuntu 16.04 LTS.
1. AEM Assets: Inget stöd för [Omvandling av råfiler](/help/assets/camera-raw.md)
1. AEM Forms: Inget stöd för produktionsmiljön
1. AEM Assets: Inget stöd för [förbättrad PDF rastrering](/help/assets/aem-pdf-rasterizer.md)
1. AEM Forms: Stöds inte

### Virtuella miljöer och molnmiljöer {#virtual-cloud-computing-environments}

Adobe Experience Manager stöds i en virtuell dator i molnmiljöer som Microsoft Azure och Amazon Web Services (AWS), i enlighet med de tekniska krav som anges på den här sidan och i enlighet med Adobe standardsupportvillkoren.

Adobe rekommenderar att du använder Adobes hanterade tjänster för att distribuera AEM på Azure eller AWS. Adobes hanterade tjänster ger experterna erfarenhet och kunskaper av att driftsätta och AEM i dessa molndatormiljöer. Ta en titt på [ytterligare dokumentation om Adobe Managed Services](https://www.adobe.com/marketing-cloud/enterprise-content-management/managed-services-cloud-platform.html?aemClk=t).

I alla andra fall där AEM distribueras på Azure eller AWS, eller i någon annan molndatormiljö, kommer support från Adobe att finnas i den virtuella datormiljön i enlighet med de tekniska specifikationer som anges på den här sidan. Alla rapporterade problem som rör AEM som körs i någon av dessa molnmiljöer måste kunna reproduceras oberoende av alla molntjänster som är specifika för molndatormiljön, såvida inte molntjänsten specifikt stöds som en del av de tekniska krav som anges på den här sidan, till exempel Azure Blob Storage eller AWS S3.

För rekommendationer om hur du distribuerar AEM på Azure eller AWS, utanför Adobe Managed Services, rekommenderar vi att du arbetar direkt med molnleverantören eller Adobe-partners som stöder distributionen av AEM i den molnmiljö du väljer. Den valda molnleverantören eller partnern ansvarar för storleksspecifikationerna, designen och implementeringen av arkitekturen, för att uppfylla dina specifika krav på prestanda, belastning, skalbarhet och säkerhet.

### Dispatcher Platforms (webbservrar) {#dispatcher-platforms-web-servers}

Dispatcher är komponenten för cachelagring och belastningsutjämning. [Ladda ned den senaste Dispatcher-versionen](https://helpx.adobe.com/experience-manager/dispatcher/release-notes.html). Experience Manager 6.4 kräver Dispatcher version 4.3.1 eller senare.

Följande webbservrar kan användas med Dispatcher version 4.3.1:

| Plattform | Supportnivå |
|---|---|
| **Apache httpd 2.4.x** (se även 1,2 nedan) | S: Stöds |
| Microsoft IIS 10 (Internet Information Server) | S: Stöds |
| Microsoft IIS 8.5 (Internet Information Server) | S: Stöds |

1. Webbservrar som byggts utifrån Apache httpd-källkoden har samma supportnivå som den version av httpd som den baseras på. Om du är osäker ber du Adobe att få bekräfta supportnivån för respektive serverprodukt. Följande fall:

   1. HTTP-servern byggdes med enbart officiella källdistributioner av Apache, eller
   1. HTTP-servern levererades som en del av det operativsystem där den körs. Exempel: IBM HTTP Server, Oracle HTTP Server

1. Dispatcher är inte tillgänglig för Apache 2.4.x för Windows.

## Klientplattformar som stöds {#supported-client-platforms}

### Webbläsare som stöds för redigeringsgränssnittet {#supported-browsers-for-authoring-user-interface}

Adobe Experience Manager användargränssnitt fungerar med följande klientplattformar. Alla webbläsare testas med standarduppsättningen med plugin-program och tillägg.

Det AEM användargränssnittet är optimerat för större skärmar (vanligen bärbara och stationära datorer) och surfplattor (t.ex. Apple iPad eller Microsoft Surface). Telefonformfaktorn stöds inte.

>[!NOTE]
>
>**Stöd för webbläsare med snabb lansering:**
>
>Uppdateringar för Mozilla Firefox, Google Chrome och Microsoft Edge var sjätte månad. Adobe tillhandahåller uppdateringar för Adobe Experience Manager för att upprätthålla den supportnivå som anges nedan för kommande versioner av dessa webbläsare.

<table> 
 <tbody> 
  <tr> 
   <td><strong>Webbläsare</strong></td> 
   <td><strong>Stöd för användargränssnitt<br /> </strong></td> 
   <td><strong>Stöd för Classic UI</strong></td> 
  </tr> 
  <tr> 
   <td><strong>Google Chrome (Evergreen)</strong></td> 
   <td>S: Stöds</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Microsoft Edge (Evergreen)</td> 
   <td>S: Stöds</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Microsoft Internet Explorer 11</td> 
   <td>S: Stöds</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Mozilla Firefox (Evergreen)</td> 
   <td>S: Stöds</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Mozilla Firefox last ESR [1]</td> 
   <td>S: Stöds</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Apple Safari 12.x på macOS</td> 
   <td>S: Stöds</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Apple Safari 11.x på macOS</td> 
   <td>S: Stöds</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Apple Safari 10.x på macOS</td> 
   <td>S: Stöds</td> 
   <td>S: Stöds</td> 
  </tr> 
  <tr> 
   <td>Apple Safari på iOS 12.x</td> 
   <td>S: Stöds [2]</td> 
   <td>Z: Stöds inte</td> 
  </tr> 
  <tr> 
   <td>Apple Safari på iOS 11.x</td> 
   <td>S: Stöds [2]</td> 
   <td>Z: Stöds inte</td> 
  </tr> 
  <tr> 
   <td>Apple Safari på iOS 10.3</td> 
   <td>S: Stöds [2]</td> 
   <td>Z: Stöds inte</td> 
  </tr> 
 </tbody> 
</table>

1. Extended Support Release för Firefox [Läs mer om detta på mozilla.org](https://www.mozilla.org/en-US/firefox/organizations/faq/)
1. stöd för Apple iPad

### Webbläsare som stöds för webbplatser {#supported-browsers-for-websites}

I allmänhet beror webbläsarstöd för webbplatser som återges av AEM Sites på implementeringen av AEM sidmallar, design och komponentutdata, och är därför styrande för den part som implementerar dessa delar.

### WebDAV-klienter {#webdav-clients}

**Microsoft Windows 7+**

Om du vill ansluta med Microsoft Windows 7+ till en AEM som inte är säker med SSL måste grundläggande autentisering över oskyddat nätverk aktiveras i Windows. Detta kräver en ändring i Windows-registret för WebClient:

1. Leta reda på registerundernyckeln:

   * HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Services\WebClient\Parameters

1. Lägg till registerposten BasicAuthLevel till den här undernyckeln med värdet 2 eller mer.

Se [Microsoft Support KB 841215](https://support.microsoft.com/default.aspx/kb/841215).

Mer information om hur du kan förbättra WebDav-klientens svar i Windows finns i [Microsoft Support KB 2445570](https://support.microsoft.com/kb/2445570)

## Information om ytterligare plattformar {#additional-platform-notes}

I det här avsnittet finns specialanteckningar och mer detaljerad information om hur du kör Adobe Experience Manager och dess tillägg.

### IPv4 och IPv6 {#ipv-and-ipv}

Alla element i Adobe Experience Manager (Instance, Dispatcher) kan installeras i både IPv4- och IPv6-nätverk.

Åtgärden är smidig eftersom ingen speciell konfiguration krävs. Du kan bara ange en IP-adress i det format som passar nätverkstypen om det behövs.

Det innebär att när en IP-adress måste anges kan du välja (efter behov) bland:

* en IPv6-adress

   till exempel `https://[ab12::34c5:6d7:8e90:1234]:4502`

* en IPv4-adress

   till exempel `https://123.1.1.4:4502`

* ett servernamn

   till exempel `https://www.yourserver.com:4502`

* standardfallet för `localhost` tolkas för både IPv4- och IPv6-nätverksinstallationer

   till exempel `http://localhost:4502`

### Krav för AEM Dynamic Media Add-on {#requirements-for-aem-dynamic-media-add-on}

AEM Dynamic Media är inaktiverat som standard. Se [Aktivera Dynamic Media](/help/assets/config-dynamic.md#enabling-dynamic-media).

När Dynamic Media är aktiverat gäller följande ytterligare systemkrav:
>[!NOTE]
>
>Följande systemkrav gäller **_endast_** om du använder Dynamic Media - hybridläge, Dynamic Media - Hybridläget har en inbäddad bildserver, som bara är certifierad på vissa operativsystem.
>
>För Dynamic Media-kunder som kör Dynamic Media - Scene7-läge (dvs. **dynamicmedia_scene7** runmode), det finns inga ytterligare systemkrav, endast samma systemkrav som AEM. Dynamic Media - Scene7-lägesarkitekturen använder den molnbaserade bildtjänsten, inte den tjänst som är inbäddad i AEM.

#### Maskinvara {#hardware}

Följande maskinvarukrav gäller för både Linux och Windows:

* Intel Xeon- eller AMD Opteron-processor med minst 4 kärnor
* Minst 16 GB RAM

#### Linux {#linux}

För att kunna använda Dynamic Media i Linux krävs följande krav:

* RedHat Enterprise 7 eller CentOS 7 och senare med de senaste korrigeringsfilerna
* 64-bitars operativsystem
* Växling inaktiverad (rekommenderas)
* SELinux är inaktiverat (se anm. nedan)

>[!NOTE]
>
>Om språkområdet är inställt så att LC_CTYPE inte är lika med en_US.UTF-8 kommer det att förhindra att dynamiska medier fungerar. Om du vill se vilket värde det har skriver du &quot;locale&quot; i kommandotolken. Om det inte är det anger du LC_CTYPE-miljövariabeln till den tomma strängen genom att skriva &quot;export LC_CTYPE=&quot; innan du kör AEM.

>[!NOTE]
>
>**Inaktiverar SELinux:** Image Serving fungerar inte med SELinux aktiverat. Det här alternativet är aktiverat som standard. Du kan åtgärda problemet genom att redigera **/etc/selinux/config** och ändra SELinux-värdet från:
>
>`SELINUX=enforcing` till  `SELINUX=disabled`

>[!NOTE]
>
>**NUMA-arkitektur:** System med processorer med AMD64 och Intel EM64T är vanligtvis konfigurerade som icke-enhetliga minnesarkitekturplattformar (NUMA), vilket innebär att kärnan konstruerar flera minnesnoder vid start i stället för att konstruera en enda minnesnod.
>
>Konstruktionen för flera noder kan resultera i minnesöverbelastning på en eller flera av noderna innan andra noder töms. När minnesöverbelastning inträffar kan kärnan bestämma sig för att avsluta processer (till exempel Image Server eller Platform Server) trots att det finns tillgängligt minne.
>
>Därför rekommenderar Adobe att du stänger av NUMA med **numa=off** startalternativ för att undvika att kärnan tar kål på dessa processer.

>[!NOTE]
>
>**Värdnamnet för servern måste kunna matchas:** Kontrollera att serverns värdnamn kan matchas till en IP-adress. Om det inte är möjligt lägger du till det fullständiga, kvalificerade värdnamnet och IP-adressen i **/etc/värdar**:
>
>`<ip address> <fully qualified hostname>`

#### Windows {#windows}

* Microsoft Windows Server 2016
* Växla utrymme motsvarande minst dubbelt så mycket fysiskt minne (RAM)

Om du vill använda Dynamic Media i Windows måste du installera Microsoft Visual Studio 2010, 2013 och 2015 för x64 och x86.

x64

* Den återdistribuerbara Microsoft Visual Studio 2010 finns på [https://www.microsoft.com/en-us/download/details.aspx?id=13523](https://www.microsoft.com/en-us/download/details.aspx?id=13523)
* Microsoft Visual Studio 2013 redistributable finns på [https://www.microsoft.com/en-us/download/details.aspx?id=40784](https://www.microsoft.com/en-us/download/details.aspx?id=40784)
* Microsoft Visual Studio 2015 redistributable finns på [https://www.microsoft.com/en-us/download/details.aspx?id=48145](https://www.microsoft.com/en-us/download/details.aspx?id=48145)

x86

* Den återdistribuerbara Microsoft Visual Studio 2010 finns på [https://www.microsoft.com/en-in/download/details.aspx?id=5555](https://www.microsoft.com/en-in/download/details.aspx?id=5555)
* Microsoft Visual Studio 2013 redistributable finns på [https://www.microsoft.com/en-in/download/details.aspx?id=40769](https://www.microsoft.com/en-in/download/details.aspx?id=40769)
* Microsoft Visual Studio 2015 redistributable finns på [https://www.microsoft.com/en-us/download/details.aspx?id=52685](https://www.microsoft.com/en-us/download/details.aspx?id=52685)

#### macOS {#macos}

* 10.9.x och senare
* Stöds endast i demos- och testversioner

### Krav för AEM Forms PDF Generator {#requirements-for-aem-forms-pdf-generator}

<table> 
 <tbody> 
  <tr> 
   <th><p><strong>Produkt</strong></p> </th> 
   <th><p><strong>Format som stöds för konvertering till PDF</strong></p> </th> 
  </tr> 
  <tr> 
   <td><p><a href="https://helpx.adobe.com/acrobat/release-note/release-notes-acrobat-reader.html">Klassiskt Acrobat 2017-spår</a></p> </td> 
   <td><p>XPS, bildformat (BMP, GIF, JPEG, JPG, TIF, TIFF, PNG, JPX, JP2, J2K, J2C, JPC), HTML, HTM, DWG, DXF och DWF</p> </td> 
  </tr> 
  <tr> 
   <td>Microsoft® Project 2016</td> 
   <td>MPP</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Publisher 2016</td> 
   <td>PUB</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office Visio 2016</td> 
   <td>VSD</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office 2016</td> 
   <td>DOC, DOCX, XLS, XLSX, PPT, PPTX, RTF och TXT</td> 
  </tr> 
  <tr> 
   <td>Microsoft® Office 2013</td> 
   <td>DOC, DOCX, XLS, XLSX, PPT, PPTX, RTF och TXT</td> 
  </tr> 
  <tr> 
   <td>Corel WordPerfect X7</td> 
   <td>WP, WPD<br /> </td> 
  </tr> 
  <tr> 
   <td>OpenOffice 4.1.2</td> 
   <td>ODT, ODP, ODS, ODG, ODF, SXW, SXI, SXC, SXD, XLS, XLSX, DOC, DOCX, PPT, PPTX, bildformat (BMP, GIF, JPEG, JPG, TIF, TIFF, PNG, JPF, JPX, JP2, J2K, J2C, JPC), HTML, HTM, RTF och TXT</td> 
  </tr> 
  <tr> 
   <td><p>OpenOffice 3.4</p> </td> 
   <td><p>ODT, ODP, ODS, ODG, ODF, SXW, SXI, SXC, SXD, XLS, XLSX, DOC, DOCX, PPT, PPTX, bildformat (BMP, GIF, JPEG, JPG, TIF, TIFF, PNG, JPF, JPX, JP2, J2K, J2C, JPC), HTML, HTM, RTF och TXT</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>PDF Generator stöder endast engelska, franska, tyska och japanska versioner av de operativsystem och program som stöds.
>
>Dessutom:
>
>* PDF Generator kräver [Acrobat 2017 Classic track version 17.011.30078 eller senare](https://helpx.adobe.com/acrobat/release-note/release-notes-acrobat-reader.html) för att utföra konverteringen.
>* AEM Forms stöder endast 32-bitarsversioner av de program som stöds.
>* Funktionerna OCR PDF (sökbar PDF), Optimize PDF och Export PDF stöds endast i Microsoft Windows.
>* Tjänsten HTML2PDF används inte i AIX.
>* PDF Generator-konverteringar för OpenOffice stöds bara i Windows, Linux och Solaris.
>* Funktionerna OCR PDF, Optimize PDF och Export PDF stöds endast i Windows.
>* En version av Acrobat medföljer AEM Forms för att aktivera PDF Generator-funktionaliteten. Programmeringsversionen ska endast användas med AEM Forms under AEM Forms-licensens löptid, för användning med AEM Forms PDF Generator. Mer information finns i AEM Forms produktbeskrivning för din distribution ([Lokal](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-on-premise.html) eller [Managed Services](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-managed-services.html))&quot;
>


### Krav för AEM Forms Designer {#requirements-for-aem-forms-designer}

* Microsoft® Windows® 2012 Server R2, Microsoft® Windows® 2016 Server, Microsoft® Windows® 2019 Server, Microsoft® Windows® 10
* 1 GHz eller snabbare processor med stöd för PAE, NX och SSE2.
* 1 GB RAM för 32-bitars eller 2 GB RAM för 64-bitars operativsystem
* 16 GB diskutrymme för 32-bitars eller 20 GB diskutrymme för 64-bitars operativsystem
* Grafikminne - 128 MB GPU (256 MB rekommenderas)
* 2,35 GB ledigt hårddiskutrymme
* Bildskärmsupplösning på 1 024 x 768 pixlar eller högre
* Maskinvaruacceleration för video (valfritt)
* Acrobat Pro DC, Acrobat Standard DC eller Adobe Acrobat Reader DC
* Administrativ behörighet för att installera Designer

### Krav för AEM Assets XMP metadata write-back {#requirements-for-aem-assets-xmp-metadata-write-back}

XMP stöds och är aktiverat för följande plattformar och filformat:

**Operativsystem**

* Linux (32-bitars, behöver stöd för 32-bitarsprogram på 64-bitarssystem). Anvisningar om hur du installerar 32-bitars klientbibliotek finns i [Aktivera XMP och återskrivning på 64-bitars RedHat Linux](https://helpx.adobe.com/experience-manager/kb/enable-xmp-write-back-64-bit-redhat.html).

* Windows Server
* Oracle Solaris
* Mac OS X (64-bitars)

**Filformat**

* JPEG
* PNG
* TIFF
* PDF
* INDD
* AI
* EPS

### Krav för AEM Screens Player {#requirements-for-aem-screens-player}

AEM Screens Player version 3.3.x har stöd för följande operativsystem:

* Microsoft Windows 10 Enterprise LTSB
* Google Chome OS 62+
* Google Android 5.1.1 med uppdaterad Android System WebView version 5.2+
* Apple iOS 10.3+
* Apple macOS 10.12+
