---
title: Versionsinformation om AEM 6.4 Cumulative Fix Pack
description: Versionsinformation om Adobe Experience Manager 6.4 Cumulative Fix Packs.
contentOwner: AK
mini-toc-levels: 1
translation-type: tm+mt
source-git-commit: b1deed95174e271bbd91814ef4aa6d4fa578cc45
workflow-type: tm+mt
source-wordcount: '2144'
ht-degree: 0%

---


# Versionsinformation om AEM 6.4 Cumulative Fix Pack {#aem-cumulative-fix-pack-release-notes}

## Versionsinformation {#release-information}

| Produkter | **Adobe Experience Manager (AEM) 6.4** |
|---|---|
| Version | 6.4.8.1 |
| Typ | Kumulativt korrigeringspaket |
| Date | 4 juni 2020 |
| Förutsättning | [AEM 6.4 Service Pack 8 (6.4.8.0)](sp-release-notes.md) |
| Hämta URL | AEM 6.4.8.1 på [paketresurs](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/cumulativefixpack/AEM-CFP-6.4.8.1), [programdistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fcq640%2Fcumulativefixpack%2Faem-6.4.8-cfp-1.0.zip) |

## Vad ingår i AEM 6.4.8.1 {#what-s-included-in-aem}

AEM Cumulative Fix Pack 6.4.8.1 är en viktig uppdatering som innehåller flera interna korrigeringar och kundkorrigeringar sedan den allmänna tillgängligheten av AEM 6.4 Service Pack 8 (6.4.8.0) i mars 2020.

AEM Cumulative Fix Pack 6.4.8.1 är beroende av AEM 6.4 Service Pack 8. Du måste därför installera AEM Cumulative Fix Pack 6.4.8.1-paketet när du har installerat AEM 6.4 Service Pack 8.

Några av de viktigaste nyheterna i AEM 6.4.8.1 är:

* Borttagen Paketdelningsintegrering med Adobe Experience Manager.
* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.21.

Mer information om bestruket finpapper och andra typer av releaser finns i [AEM Update Release Vehicle Definitions](../sites-deploying/update-release-vehicle-definitions.md)

## Ändringslista {#list-of-changes}

Adobe Experience Manager 6.4.8.1 innehåller korrigeringar av följande problem.

### Sites {#sites-6481}

* När namnet på en lokal komponent i en LiveCopy är identiskt med namnet på en komponent i utkastet och komponenten rullas ut från utkast, läggs termen _msm_move inte till i namnet på den lokala komponenten (NPR-33207).
* Parametrarna som läggs till i den ursprungliga begäran ingår inte i omdirigerings-URL:en (NPR-33174).
* När alternativet Coral.Select anger emptyOption=true eller innehåller ett standardobjekt med värdet = &quot;&quot;, kommer filen dropdownshowhide.js att stöta på ett fel: Uncaught TypeError: component.getValue är inte en funktion (NPR-33163).
* När en komponent innehåller en annan komponent som en dataunderordnad resurs ersätts platshållaren för den överordnade behållarkomponenten med platshållaren för de inre komponenterna (NPR-33119).
* När du baserar ett innehållsfragment på ett schema och det innehåller ett obligatoriskt textområde eller ett sökvägsfält, kan innehållsfragmentet inte sparas (NPR-33007)
* När du skapar en anpassad komponent med hjälp av fragmentkomponenten för körklar upplevelse och använder den på AEM Sites-sidor, visar inte AEM referenser (användning) för den anpassade komponenten (NPR-32852).
* När en AEM Sites-sida är en del av en stor innehållsuppsättning med flera live-kopior går det inte att läsa in förhandsgranskningen av sidversionshistoriken (NPR-32772).
* När du befordrar en programstart läggs&quot;cq:LiveRelationship&quot;-blandningen till i alla komponenter som läggs till vid programstarten. Det påverkar alla starter oavsett om en start skapas med eller utan att alternativet - Inherit source page live data - (NPR-32664) väljs.
* När sidnumreringen startar läses inte Experience Fragments Picker in alla objekt (NPR-32605).
* Det går inte att skapa en start för en AEM Sites-sida. Startskapande resulterar i ett fel (NPR-32544).
* Hantera publikation innehåller inte refererade resurser i begäran om aktiveringsarbetsflöde (NPR-32463).
* Hälsokontrollen för utskickaren visar `Invalid cookie header` ett varningsmeddelande i loggfilerna (NPR-33630).

### Assets {#assets-6481}

* Antalet resurser ändras inte enligt ändringen i urvalet i listvyn (NPR-33285).

* Knappen Nästa aktiveras inte när du väljer överordnad nod (där en underordnad mapp visas) och sedan väljer underordnad mapp (NPR-33284).

* Touchgränssnittet återges inte (med fel) för användare som inte har läsåtkomst i databasroten när DMS7- eller hybridläget är aktiverat (NPR-33175).

* De GB18030-tecken som finns i mapp- och resursnamn ändras till tomma i de hämtade zip-filerna (NPR-33150).

* En extra mapp skapas vid smart beskärning av en resurs som finns i en överordnad mapp med ett punkttecken i namnet (NPR-32755). `.`

* Lazy-inläsning aktiveras inte och högst 100 resurser visas när du väljer att granska uppgifter från meddelandeinkorgen (NPR-32749).

* Länksidan till delningssamlingen har brutits på grund av ändringar i koralinformationen (NPR-32510).

* Resursbearbetning när massöverföring fastnar (CQ-4293916).

### Platform {#platform-6481}

* Filtret anropas inte om [!DNL Sling] mappningsposten skapas under `sling:match` `/etc/maps` (NPR-33308).
* Alla rensningsagenter aktiveras när en sida inaktiveras (NPR-32941).
* När du använder API:t för att miniera ett JavaScript-bibliotek visas ett felmeddelande i loggfilen som anger att JavaScript-koden inte är kompatibel med strikt läge. `ScriptProcessor` API:t innehåller inget alternativ för att aktivera eller inaktivera strikt läge. (NPR-32746).
* När en SQL-fråga körs längre, till exempel 7 timmar, slutar AEM svara (NPR-33043).

### Användargränssnitt {#ui-6481}

* När du söker efter eller bläddrar i en bana med hjälp av en markeringsdialogruta visas allt innehåll i den valda JCR-noden i stället för att bara visa bilderna (NPR-32712).

### Översättningsprojekt {#tranlation-6481}

* Ett `NullPointerException` fel visas i loggarna när ett översättningsjobb körs (NPR-3220).

### Communities {#communities-6481}

* Författare som har skapat en ny grupp omdirigeras inte till avsnittet [!UICONTROL Community Group] i [!DNL Internet Explorer] 11 (NPR-33202).
* Ett fel inträffar vid åtkomst till [!UICONTROL Activity Stream] sidan (NPR-33152).
* När du redigerar en [!DNL Communities] grupp och ändrar miniatyrbilden uppdateras inte gruppens miniatyrbild (NPR-32603).
* När du skapar en version av meddelanden och prenumerationer på användargenererat innehåll (UGC) lagras ett felaktigt ID för källsidan (CQ-4289703).

### Arbetsflöde {#workflow-6481}

* Vissa komponenter visas inte i den dialogruta som öppnas när en användare slutför ett arbetsflöde som innehåller en [!UICONTROL Dialog Participant step] (NPR-32989).

* Alternativet [!UICONTROL Timeline] i den vänstra listen tar längre tid att ladda än förväntat (NPR-32850).

### Formulär {#forms-6481}

>[!NOTE]
>
>AEM Cumulative Fix Pack innehåller inte korrigeringar för AEM Forms. De levereras med ett separat Forms-tilläggspaket. Dessutom släpps ett kumulativt installationsprogram med korrigeringar för AEM Forms på JEE. Mer information finns i [Installera AEM Forms-tilläggspaket](#install-aem-forms-add-on-package) och [Installera AEM Forms JEE-installationsprogrammet](#install-aem-forms-jee-installer).

* Korrespondenshantering: När en användare klistrar in innehåll från ett [!DNL Word] dokument behåller textdokumentfragmentet inte formatering (NPR-33213).
* Adaptiva former: En ny rad i en sträng i en ordlista med adaptiva formulär lägger till `&#xa;` tecken i ordlistan (NPR-33265).
* Adaptiva former: Användaren kan inte spara ett anpassat formulär med mer än en bifogad fil (NPR-33214).
* Adaptiva former: `AddInstance` och `RemoveInstance` metoder för klassen Instance Manager lägger inte till dynamiskt antal instanser för lazy load-fragment på [!DNL Internet Explorer 11] (NPR-33201).
* Adaptiva former: Analyser som är aktiverade på ett adaptivt formulär som är inbäddat på en [!DNL Sites] sida registrerar inte data för händelserna Submit och Abandon (NPR-31359).
* Adaptiva former: När en användare klistrar in innehållet från ett [!DNL Word] dokument i ett adaptivt formulär och skickar det innehåller det skickade adaptiva formuläret unicode-tecken. Dessutom misslyckas konverteringen av PDF till PDF/A på grund av Unicode-tecken (NPR-33348).
* BackendIntegration: Begäranden från formulärdatamodellen misslyckas eftersom uppdateringstoken förfaller på grund av ett inaktivt tillstånd (NPR-33168).
* Dokumenttjänster: Konvertering av PDF-tjänst kan inte konvertera PDF-dokument till PostScript på grund av att Gibson-jars saknas [!DNL WebLogic] på [!DNL Linux] servern (NPR-33515, CQ-4292239).
* Dokumenttjänster: När en användare konverterar en textfil till en PDF-fil återges inte japanska tecken korrekt (NPR-33239).

## Installera 6.4.8.1 {#install}

### Installationskrav {#setup-requirements}

<!--

>[!NOTE]
>
>For successful installation of AEM 6.4.6.0 on the instance, it is strongly recommended to upgrade the version of com.adobe.granite.oak.s3connector to 1.8.4 for the customers who are on the older version of s3 connector.
>The process of upgrading the com.adobe.granite.oak.s3connector is available at [https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html](https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html).
>Download the latest version of com.adobe.granite.oak.s3connector from: [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/)

-->

>[!CAUTION]
>
>För kunder med funktionspaket installerade på AEM 6.4. Valfria funktionspaket från Adobe är beroende av releaseversion och servicepaket. Om du har något funktionspaket installerat kontaktar du AEM Customer Care-teamet för att kontrollera om dessa funktionspaket är kompatibla med detta kumulativa korrigeringspaket för AEM 6.4.

* AEM 6.4.8.1 kräver AEM 6.4.8.0. Mer information finns i [uppgraderingsdokumentationen](../sites-deploying/upgrade.md) .
* På en distribution med MongoDB och flera instanser installerar du AEM 6.4.8.1 på en av Author-instanserna med hjälp av Package Manager.
* Innan du installerar det kumulativa korrigeringspaketet måste du se till att du har en ögonblicksbild eller en ny säkerhetskopia av AEM-instansen.
* Starta om instansen innan du installerar den. Detta behövs bara när instansen fortfarande är i uppdateringsläge (och detta är fallet när instansen precis uppdaterades från en tidigare version), men rekommenderas vanligtvis om instansen kördes under en längre tidsperiod.

>[!NOTE]
>
>Adobe rekommenderar inte att du tar bort eller avinstallerar AEM 6.4.8.1-paketet.

### Installera det ackumulerade korrigeringspaketet {#install-cumulative-fix-pack}

Så här installerar du Cumulative Fix Pack på en befintlig AEM 6.4.8.0-instans:

1. Klicka på länken [Paketresurs](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/cumulativefixpack/AEM-CFP-6.4.8.1) eller [Programdistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/cumulativefixpack/aem-6.4.8-cfp-1.0.zip) för att hämta paketet.

1. Öppna [Pakethanteraren](http://localhost:4502/crx/packmgr/index.jsp) och klicka på **Överför paket** för att överföra paketet.

1. Markera paketnamnet och klicka på **Installera**.

>[!NOTE]
>
>**Dialogrutan för Package Manager-gränssnittet avslutas ibland på ett felaktigt sätt under installationen av 6.4.8.1**
>
>Därför rekommenderar vi att du väntar på att felloggarna ska stabiliseras innan du får åtkomst till instansen. Användaren måste vänta på specifika loggar för avinstallation av uppdateringspaketet innan den kan vara säker på att installationen lyckas. Det händer vanligtvis på Safari, men kan hända i olika webbläsare.

### Automatisk installation {#auto-installation}

Det finns två sätt att automatiskt installera AEM 6.4.8.1 i en instans som körs:

S. Placera paketet i ..*/crx-quickstart/install* -mappen när servern körs. Paketet installeras automatiskt.

B. Använd [HTTP-API:t från Package Manager](https://docs.adobe.com/content/docs/en/crx/2-3/how_to/package_manager.html) - kontrollera att du använder `cmd=install&recursive=true` - så att det kapslade paketet installeras.

>[!NOTE]
>
>AEM 6.4.8.1 stöder inte Bootstrap-installation.

### Validera installation {#validate-install}

1. Produktinformationssidan (*/system/console/ productinfo *) ska nu visa den uppdaterade versionssträngen &quot;Adobe Experience Manager, version 6.4.8.1&quot; under Installerade produkter.
1. Alla OSGI-paket är antingen AKTIVA eller FRAGMENT i OSGI-konsolen (Använd webbkonsolen: /system/console/bundles).
1. OSGI-paketet org.apache.jackrabbit.oak-core finns i version 1.8.17 eller senare (Använd webbkonsol: /system/console/bundles).

Information om den certifierade plattformen för körning med den här versionen av AEM Sites and Assets finns i [Tekniska krav](../sites-deploying/technical-requirements.md).

>[!Note]
>När paketet har installerats visas ett >informativt meddelande som anger att innehållet >package har installerats, t.ex. **&quot;Content Package AEM-6.4-Service-Pack-7 har installerats korrekt.&quot;**

### Uppdatera dynamiska medievyer (5.10.1) {#update-dynamic-media-viewers}

<p id="Dynamic">AEM 6.4.8.1 innehåller en ny version av Dynamic Media Viewer (5.10.1) som gör det möjligt att kontrollera dubblettnamn på sidan Bildförinställning. Dynamic Media-kunder rekommenderas att köra följande kommando för att få fram aktuella visningsinställningar från kartongen.

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

som kopierar nya visningsförinställningar till /conf-platsen.

### Installera tilläggspaket för AEM-formulär {#install-aem-forms-add-on-package}

>[!NOTE]
>
>Hoppa över om du inte använder AEM Forms. Korrigeringar i AEM Forms levereras via ett separat tilläggspaket.

1. Kontrollera att du har installerat AEM Cumulative Fix Pack.
1. Ladda ned motsvarande tilläggspaket för formulär i [AEM Forms-versioner](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) för ditt operativsystem.
1. Installera tilläggspaketet för formulär enligt beskrivningen i [Installera tilläggspaket](https://helpx.adobe.com/experience-manager/6-4/forms/using/installing-configuring-aem-forms-osgi.html#InstallAEMFormsaddonpackage)för AEM-formulär.

### Installera JEE-installationsprogrammet för AEM Forms {#install-aem-forms-jee-installer}

>[!NOTE]
>
>Hoppa över om du inte använder AEM Forms på JEE. Korrigeringar i AEM Forms JEE levereras via ett separat installationsprogram.

Information om hur du installerar det kumulativa installationsprogrammet för AEM Forms JEE och konfigurationen efter distributionen finns i [AEM Forms JEE Patch Installer 0016](https://helpx.adobe.com/aem-forms/quick-fixes/6-4/jee-patch-0016.html).

### Uber Jar {#uber-jar}

Uber Jar för AEM 6.4.8.1 finns i [Adobe Public Maven-databasen](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aem/uber-jar/6.4.8.1/).

Om du vill använda Uber Jar i ett Maven-projekt kan du läsa artikeln [Så här använder du Uber jar](../sites-developing/ht-projects-maven.md) och inkludera följande beroende i projektstrukturen:

```shell
<dependency>
      <groupId>com.adobe.aem</groupId>
      <artifactId>uber-jar</artifactId>
      <version>6.4.8.1</version>
      <classifier>apis</classifier>
      <scope>provided</scope>
</dependency>
```

## Borttagna/inaktuella funktioner {#removed-deprecated-features}

I det här avsnittet listas funktioner som har tagits bort eller tagits bort från AEM 6.4.

| Yta | Funktion | Ersättning | Version |
|---|---|---|---|
| Assets | Hantera taggåtgärd för underresurser | Ingen ersättning | AEM 6.4.2.0 |
| Resurser och integrering med Adobe Creative Cloud | [AEM till Creative Cloud-mappdelning](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/creative-cloud.html) introducerades i AEM 6.2 som ett sätt att ge kreativa användare tillgång till resurser från AEM. En ny funktion i Creative Cloud-programmet, Adobe Asset Link, ger en mycket bättre användarupplevelse och kraftfullare åtkomst till resurser från AEM direkt inifrån Photoshop, InDesign och Illustrator. Adobe kommer inte att göra ytterligare förbättringar av mappdelningsfunktionen. Funktionen ingår i AEM, men vi rekommenderar att man använder ersättningsfunktionen. | Adobe Asset Link eller datorprogram. Mer information finns i [artikeln om integrering](/help/assets/aem-cc-integration-best-practices.md) av AEM Creative Cloud. | AEM 6.4.4.0 |

## Kända fel {#known-issues}

* När du installerar AEM 6.4.8.1 orsakar uppdateringen av [!DNL Chrome] version 83 ett problem när du skapar paket. Lös problemet genom att använda andra tillgängliga webbläsare, som [!DNL Internet Explorer] och [!DNL Firefox]eller andra installationsalternativ för AEM-standardpaket. Problemet åtgärdas efter installation av AEM 6.4.8.1.

* Det går inte att skicka ett e-postmeddelande till SMTP-fjärrservern med hjälp av AEM-standardavsändaren eftersom den bara tillåter kommunikation med TLS v1.2. Ta bort paketet `javax.mail:mail:1.5.0-b01` från `system/console` och uppdatera paketen för att lösa problemet.

Information om kända fel i AEM 6.4.8.0 Service Pack finns i [AEM 6.4.8.0 Service Pack Release Notes](sp-release-notes.md).

## OSGi-paket och innehållspaket som ingår {#osgi-bundles-and-content-packages-included}

Följande textdokument innehåller en lista över de OSGi-paket och innehållspaket som ingår i AEM 6.4.8.1.

Lista över OSGi-paket som ingår i AEM 6.4.8.1

[Hämta fil](assets/6.4.8.1_osgi_bundles.txt)

Lista över innehållspaket som ingår i AEM 6.4.8.1

[Hämta fil](assets/6.4.8.1_content_packages.txt)

## Användbara resurser {#helpful-resources}

* [Versionsinformation om AEM 6.4](../release-notes/release-notes.md)
* [AEM - produktsida](https://www.adobe.com/solutions/web-experience-management.html)
* [AEM 6.4-dokumentation](https://helpx.adobe.com/support/experience-manager/6-4.html)
* Prenumerera på [Adobe Priority-produktuppdateringar](https://www.adobe.com/subscription/priority-product-update.html)

## Begränsade platser {#restricted-sites-new}

Dessa webbplatser är bara tillgängliga för kunder. Om du är kund och behöver åtkomst kontaktar du din kontoansvarige på Adobe.

* [Nedladdning av produkt på licensing.adobe.com](https://licensing.adobe.com/)
* [Kontakta kundsupport](https://docs.adobe.com/content/help/en/customer-one/using/home.html)
