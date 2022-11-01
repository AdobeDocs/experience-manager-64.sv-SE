---
title: Installera och konfigurera datainhämtningsfunktioner
seo-title: Install and configure data capture capabilities
description: Installera och konfigurera adaptiva formulär, PDF forms och HTML5 Forms. Konfigurera Adobe Analytics och Adobe Target för adaptiva formulär för att analysera användningen av formulär och målanvändare utifrån deras profil.
seo-description: Install and configure adaptive forms, PDF Forms, and HTML5 Forms. Configure Adobe Analytics and Adobe Target for adaptive forms to analyze usage of forms and target users based on their profile.
uuid: ce253b5a-eeb2-47d2-a6c9-e6f59384159a
contentOwner: khsingh
topic-tags: installing
discoiquuid: 1bb8360c-5543-484e-9712-590822211298
role: Admin
exl-id: 45b0fb99-9f7f-47e6-a4de-4db321867f8f
source-git-commit: f8b19b6723d333e76fed111b9fde376b3bb13a1d
workflow-type: tm+mt
source-wordcount: '1759'
ht-degree: 0%

---

# Installera och konfigurera datainhämtningsfunktioner {#install-and-configure-data-capture-capabilities}

Installera och konfigurera adaptiva formulär, PDF forms och HTML5 Forms. Konfigurera Adobe Analytics och Adobe Target för adaptiva formulär för att analysera användningen av formulär och målanvändare utifrån deras profil.

## Introduktion {#introduction}

AEM Forms tillhandahåller en uppsättning formulär för att hämta data från slutanvändaren: adaptiva formulär, HTML5 Forms och PDF forms. Det innehåller även verktyg för att lista alla tillgängliga formulär på en webbsida, analysera formuläranvändningen och för att identifiera målanvändare utifrån deras profil. Dessa funktioner ingår i AEM Forms tilläggspaket. Tilläggspaketet distribueras på en Author- eller Publish-instans av AEM.

**Adaptiva former:** Dessa formulär ändrar utseende baserat på enhetens skärmstorlek, är engagerande och interaktiva till sin natur. Adaptiv Forms kan även integreras med Adobe Analytics, Acrobat Sign och Adobe Target. Ni kunde leverera personaliserade formulär och processorienterade upplevelser till användarna baserat på deras demografi och andra funktioner. Man kan också integrera adaptiva blanketter med Acrobat Sign.

**PDF forms** är lämpliga för pixelperfekt utskrift och digital informationsinhämtning i ett PDF-dokument. I den digitala avataren kan du använda Adobe Acrobat eller Acrobat Reader för att fylla i dessa formulär. Du kan lägga upp dessa formulär på din webbplats eller använda formulärportalen för att lista dem på en AEM webbplats. Du kan även skicka dessa formulär till andra som bilagor. De här formulären passar bäst för skrivbordsmiljöer.

**HTML5 Forms** är en webbläsarvänlig version av PDF forms. HTML5 Forms passar för miljöer som inte stöder plugin-program för PDF. HTML5 Forms möjliggör återgivning av XFA-baserade formulär på mobila enheter och webbläsare på stationära datorer där XFA-baserad PDF inte stöds. Dessa formulär passar bäst för surfplattor och datorer.

AEM Forms är en kraftfull plattform i företagsklass och datainhämtning (adaptiva formulär, PDF forms och HTML5 Forms) är bara en av AEM Forms funktioner. En fullständig lista över funktioner finns på [Introduktion till AEM Forms](/help/forms/using/introduction-aem-forms.md).

## Distributionstopologi {#deployment-topology}

AEM Forms tilläggspaket är ett program som distribueras till AEM. Du behöver bara minst en AEM Author- och AEM Publish-instans för att kunna köra AEM Forms datainhämtningsfunktioner. Följande topologi rekommenderas för att köra AEM Forms AEM Forms datainsamlingsfunktioner. Mer information om topologin finns i [Arkitektur och driftsättningstopologier för AEM Forms](/help/forms/using/aem-forms-architecture-deployment.md).

![rekommenderad topologi](assets/recommended-topology.png)

## Systemkrav {#system-requirements}

Innan du börjar installera och konfigurera datainhämtningsfunktionen i AEM Forms måste du se till att:

* Maskinvaru- och programvaruinfrastruktur finns på plats. En detaljerad lista över maskin- och programvara som stöds finns på [tekniska krav](/help/sites-deploying/technical-requirements.md).

* Installationssökvägen för AEM-instansen innehåller inte blanksteg.
* En AEM körs. I AEM är &quot;instance&quot; en kopia av AEM som körs på en server i författar- eller publiceringsläge. Du behöver minst två [AEM (en författare och en publicering)](/help/sites-deploying/deploy.md) för att köra AEM Forms datainhämtningsfunktioner:

   * **Upphovsman**: En AEM som används för att skapa, överföra och redigera innehåll och för att administrera webbplatsen. När innehållet är klart att publiceras replikeras det till publiceringsinstansen.
   * **Publicera**: En AEM som skickar det publicerade innehållet till allmänheten via Internet eller ett internt nätverk.

* Minneskraven uppfylls. AEM Forms tilläggspaket kräver:

   * 15 GB temporärt utrymme för Microsoft Windows-baserade installationer.
   * 6 GB temporärt utrymme för UNIX-baserade installationer.

* Replikering och omvänd replikering har angetts för författaren och publiceringsinstanserna. Mer information finns i [Replikering](/help/sites-deploying/replication.md).
* Extra krav för UNIX-baserade system: Om du använder det UNIX-baserade operativsystemet installerar du följande paket från installationsmediet för respektive operativsystem.

<table> 
 <tbody> 
  <tr> 
   <td>exponat</td> 
   <td>libxcb</td> 
   <td>freetype</td> 
   <td>libXau</td> 
  </tr> 
  <tr> 
   <td>libSM</td> 
   <td>zlib</td> 
   <td>libICE</td> 
   <td>libuuid</td> 
  </tr> 
  <tr> 
   <td>glibc</td> 
   <td>libXext</td> 
   <td><p>nss-softokn-free-bl</p> </td> 
   <td>fontconfig</td> 
  </tr> 
  <tr> 
   <td>libX11</td> 
   <td>libXrender</td> 
   <td>libXrandr</td> 
   <td>libXinerama</td> 
  </tr> 
 </tbody> 
</table>

## Installera AEM Forms tilläggspaket {#install-aem-forms-add-on-package}

AEM Forms tilläggspaket är ett program som distribueras till AEM. Paketet innehåller AEM Forms datainhämtning och andra funktioner. Så här installerar du tilläggspaketet:

1. Öppna [Programvarudistribution](https://experience.adobe.com/downloads). Du behöver en Adobe ID för att logga in på Software Distribution.
1. Tryck **[!UICONTROL Adobe Experience Manager]** finns i rubrikmenyn.
1. I **[!UICONTROL Filters]** avsnitt:
   1. Välj **[!UICONTROL Forms]** från **[!UICONTROL Solution]** nedrullningsbar lista.
   2. Välj version och typ för paketet. Du kan också använda **[!UICONTROL Search Downloads]** för att filtrera resultaten.
1. Tryck på det paketnamn som gäller för operativsystemet och välj **[!UICONTROL Accept EULA Terms]** och trycka **[!UICONTROL Download]**.
1. Öppna [Pakethanteraren](https://docs.adobe.com/content/help/en/experience-manager-65/administering/contentmanagement/package-manager.html)  och klicka **[!UICONTROL Upload Package]** för att överföra paketet.
1. Markera paketet och klicka på **[!UICONTROL Install]**.

   Du kan även hämta paketet via länken direkt i [AEM Forms](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) artikel.

1. När paketet har installerats uppmanas du att starta om AEM. **Starta inte om servern omedelbart.** Innan du stoppar AEM Forms-servern väntar du tills meddelandena ServiceEvent REGISTERED och ServiceEvent UNREGISTERED inte visas i [AEM-installationskatalog]/crx-quickstart/logs/error.log och loggen är stabil.
1. Upprepa steg 1-7 för alla författare- och publiceringsinstanser.

## Konfiguration efter installation {#post-installation-configurations}

AEM Forms har några obligatoriska och valfria konfigurationer. De obligatoriska konfigurationerna är bland annat att konfigurera BouncyCastle-bibliotek och serialiseringsagent. De valfria konfigurationerna är bland annat att konfigurera dispatcher, Forms-portalen, Acrobat Sign, Adobe Analytics och Adobe Target.

### Obligatoriska efterinstallationskonfigurationer {#mandatory-post-installation-configurations}

#### Konfigurera RSA- och BouncyCastle-bibliotek  {#configure-rsa-and-bouncycastle-libraries}

Utför följande steg på alla författare- och publiceringsinstanser för att starta delegeringen av biblioteken:

1. Stoppa den underliggande AEM.
1. Öppna [AEM installationskatalog]\crx-quickstart\conf\sling.properties fil för redigering.

   Om du använt [AEM installationskatalog]\crx-quickstart\bin\start.bat här startar du AEM och redigerar sedan sling.properties som finns på [AEM_root]\crx-quickstart\.

1. Lägg till följande egenskaper i filen sling.properties:

   ```
   sling.bootdelegation.class.com.rsa.jsafe.provider.JsafeJCE=com.rsa.*
   sling.bootdelegation.class.org.bouncycastle.jce.provider.BouncyCastleProvider=org.bouncycastle.*
   ```

1. (Endast AIX) Lägg till följande egenskaper i filen sling.properties:

   ```
   sling.bootdelegation.xerces=org.apache.xerces.*
   ```

1. Spara och stäng filen och starta AEM.
1. Upprepa steg 1-4 för alla författarinstanser och publiceringsinstanser.

#### Konfigurera serialiseringsagenten {#configure-the-serialization-agent}

Utför följande steg på alla Author- och Publish-instanser för att lägga till paketet i tillåtelselista:

1. Öppna AEM Configuration Manager i ett webbläsarfönster. Standardwebbadressen är `https://[server]:[port]/system/console/configMgr`.
1. Söka och öppna **[!UICONTROL Deserialization Firewall Configuration]**.
1. Lägg till **[!UICONTROL sun.util.calendar]** till **[!UICONTROL allowlist]** fält. Klicka på **[!UICONTROL Save]**.
1. Upprepa steg 1-3 för alla författarinstanser och publiceringsinstanser.

### Ytterligare konfigurationer efter installation {#optional-post-installation-configurations}

#### Konfigurera Dispatcher {#configure-dispatcher}

Dispatcher är ett verktyg för cachelagring och lastbalansering för AEM. AEM Dispatcher skyddar också AEM från attacker. Du kan öka säkerheten för AEM genom att använda Dispatcher tillsammans med en webbserver i företagsklass. Om du använder [Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher-configuration.html)och sedan utföra följande konfigurationer för AEM Forms:

1. Konfigurera åtkomst för AEM Forms:

   Öppna filen dispatcher.any för redigering. Navigera till filteravsnittet och lägg till följande filter i filteravsnittet:

   `/0025 { /type "allow" /glob "* /bin/xfaforms/submitaction*" } # to enable AEM Forms submission`

   Spara och stäng filen. Mer information om filter finns i [Dispatcher-dokumentation](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher-configuration.html).

1. Konfigurera tjänsten för refererarfilter:

   Logga in som administratör i konfigurationshanteraren för Apache Felix. Konfigurationshanterarens standardwebbadress är `https://[server]:[port_number]/system/console/configMgr`. I **[!UICONTROL Configurations]** väljer du **[!UICONTROL Apache Sling Referrer Filter]** alternativ. I fältet Tillåt värdar anger du avsändarens värdnamn för att tillåta det som referent och klickar på **[!UICONTROL Save]**. Formatet på posten är `https://[server]:[port]`.

#### Konfigurera cache {#configure-cache}

Cachelagring är en mekanism som förkortar dataåtkomsttider, minskar fördröjningen och förbättrar in-/utdatahastigheter (I/O). Cacheminnet för adaptiva formulär lagrar endast HTML-innehåll och JSON-struktur i ett adaptivt formulär utan att några förfyllda data sparas. Det minskar tiden som krävs för att återge ett anpassat formulär.

* När du använder cacheminnet för anpassade formulär använder du [AEM Dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/using/dispatcher-configuration.html) för att cachelagra klientbibliotek (CSS och JavaScript) för ett adaptivt formulär.
* När du utvecklar anpassade komponenter bör du se till att cachen för anpassade formulär är inaktiverad på servern som används för utveckling.

Utför följande steg för att konfigurera cachen för adaptiva formulär:

1. Gå till konfigurationshanteraren AEM webbkonsolen på `https://[server]:[port]/system/console/configMgr`.
1. Klicka **[!UICONTROL Adaptive Form and Interactive Communication Web Channel Configuration]** om du vill redigera dess konfigurationsvärden. I dialogrutan Redigera konfigurationsvärden anger du det maximala antalet formulär eller dokument som en instans av AEM Forms-servern kan cachelagra i **[!UICONTROL Number of Adaptive Forms]** fält. Standardvärdet är 100. Klicka på **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Om du vill inaktivera cachen anger du värdet i fältet Antal adaptiva Forms till **0**. Cacheminnet återställs och alla formulär och dokument tas bort från cacheminnet när du inaktiverar eller ändrar cachekonfigurationen.

#### Konfigurera SSL-kommunikation för formulärdatamodell {#configure-ssl-communcation-for-form-data-model}

Du kan aktivera SSL-kommunikation för formulärdatamodellen. Om du vill aktivera SSL-kommunikation för formulärdatamodellen ska du lägga till certifikat i Java Trust Store för alla instanser innan du startar en AEM Forms-instans. Du kan köra följande kommando för att lägga till certifikaten: &quot;

`keytool -import -alias <alias-name> -file <pathTo .cer certificate file> -keystore <<pathToJRE>\lib\security\cacerts>`

#### Konfigurera Acrobat Sign {#configure-adobe-sign}

Acrobat Sign möjliggör e-signaturarbetsflöden för anpassningsbara formulär. E-signaturer förbättrar arbetsflödena för att bearbeta dokument inom juridik, försäljning, löneadministration, personaladministration och många andra områden.

I ett typiskt Acrobat Sign-scenario och ett scenario med adaptiva formulär fyller en användare i ett adaptivt formulär som kan användas för en tjänst. Till exempel kan en kreditkortsansökan och en medborgare få förmåner. När en användare fyller i, skickar och signerar ansökningsformuläret skickas formuläret till tjänsteleverantören för ytterligare åtgärder. Tjänsteleverantören granskar programmet och använder Acrobat Sign för att markera det som godkänt. För att möjliggöra liknande arbetsflöden för elektroniska signaturer kan du integrera Acrobat Sign med AEM Forms.

Om du vill använda Acrobat Sign med AEM Forms [Integrera Acrobat Sign med AEM Forms](/help/forms/using/adobe-sign-integration-adaptive-forms.md).

#### Konfigurera Adobe Analytics {#configure-adobe-analytics}

AEM Forms kan integreras med Adobe Analytics så att ni kan samla in och spåra prestandamått för era publicerade formulär och dokument. Syftet med att analysera dessa värden är att fatta välgrundade beslut baserat på uppgifter om de ändringar som krävs för att göra formulär eller dokument mer användbara.

Information om hur du använder Adobe Analytics med AEM Forms finns i [Konfigurera analyser och rapporter](/help/forms/using/configure-analytics-forms-documents.md).

#### Integrera Adobe Target {#integrate-adobe-target}

Kunderna överger troligtvis ett formulär om upplevelsen inte är engagerande. Även om det är frustrerande för kunderna kan det också öka supportvolymen och kostnaderna för organisationen. Det är både viktigt och utmanande att identifiera och tillhandahålla rätt kundupplevelse som ökar konverteringsgraden. AEM innehåller nyckeln till detta problem.

AEM kan integreras med Adobe Target, en Adobe Marketing Cloud-lösning, för att leverera personaliserade och engagerande kundupplevelser i flera digitala kanaler. Om du vill använda Adobe Target för att A/B-testa adaptiva formulär, [Integrera Adobe Target med AEM Forms](/help/forms/using/ab-testing-adaptive-forms.md#setupandintegratetargetinaemforms).

## Nästa steg {#next-steps}

Du har konfigurerat en miljö för att använda AEM Forms datainhämtningsfunktioner. Nästa steg mot att använda funktionen är:

* [Skapa ditt första anpassningsbara formulär](/help/forms/using/create-your-first-adaptive-form.md)
* [Skapa ditt första PDF-formulär](https://helpx.adobe.com/content/dam/help/en/experience-manager/6-4/forms/pdf/designer-quickstart.pdf)
* [Introduktion till HTML5 Forms](/help/forms/using/introduction.md)
