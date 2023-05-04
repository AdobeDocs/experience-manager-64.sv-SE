---
title: Så här arbetar du med paket
seo-title: How to Work With Packages
description: Lär dig grunderna i hur du arbetar med paket i AEM.
seo-description: Learn the basics of working with packages in AEM.
uuid: e9eb4f88-9df6-4019-92e0-2aafcffe1aab
contentOwner: Chiradeep Majumdar
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: content
content-type: reference
discoiquuid: 8e568c59-5455-422f-94a6-baf6d2aae070
exl-id: eebc10fa-1d49-4797-a9e6-b6615bfe0173
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '4057'
ht-degree: 0%

---

# Så här arbetar du med paket{#how-to-work-with-packages}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med paket kan du importera och exportera databasinnehåll. Du kan till exempel använda paket för att installera nya funktioner, överföra innehåll mellan instanser och säkerhetskopiera databasinnehåll.

Paket kan öppnas och/eller underhållas från följande sidor:

* [Pakethanteraren](#package-manager)som du använder för att hantera paketen i den lokala AEM instansen.

* [Paketresurs](#package-share), en centraliserad server som innehåller både offentligt tillgängliga paket och sådana som är privata för ditt företag. De publika paketen kan innehålla snabbkorrigeringar, nya funktioner, dokumentation m.m.

Du kan överföra paket mellan Package Manager, Package Share och ditt filsystem.

## Vad är paket? {#what-are-packages}

Ett paket är en zip-fil som innehåller databasinnehåll i form av en filsystemserialisering (kallas vault-serialisering). Detta ger en lättanvänd och redigerbar representation av filer och mappar.

Paket innehåller innehåll, både sidinnehåll och projektrelaterat innehåll, som väljs med filter.

Ett paket innehåller även vaultmetainformation, inklusive filterdefinitioner och importkonfigurationsinformation. Ytterligare innehållsegenskaper (som inte används för paketextrahering) kan inkluderas i paketet, till exempel en beskrivning, en visuell bild eller en ikon. dessa egenskaper är avsedda för innehållspaketkonsumenten och endast för informationsändamål.

>[!NOTE]
>
>Paket representerar den aktuella versionen av innehållet när paketet skapas. De innehåller inga tidigare versioner av det innehåll som AEM sparar i databasen.

Du kan utföra följande åtgärder på eller med paket:

* Skapa nya paket; definiera paketinställningar och filter efter behov
* Förhandsgranska paketinnehåll (före bygge)
* Skapa paket
* Visa paketinformation
* Visa paketinnehåll (efter bygget)
* Ändra definitionen för befintliga paket
* Återskapa befintliga paket
* Radbryt paket
* Hämta paket från AEM till filsystemet
* Överför paket från filsystemet till den lokala AEM
* Validera paketinnehåll före installation
* Utför en torr installation
* Installera paket (AEM installerar inte paket automatiskt efter överföring)
* Ta bort paket
* Hämta paket, till exempel snabbkorrigeringar, från paketdelningsbiblioteket
* Överför paket till den företagsinterna sektionen i biblioteket Paketresurs

## Paketinformation {#package-information}

En paketdefinition består av olika typer av information:

* [Paketinställningar](#package-settings)
* [Paketfilter](#package-filters)
* [Paketskärmbilder](#package-screenshots)
* [Paketikoner](#package-icons)

### Paketinställningar {#package-settings}

Du kan redigera olika paketinställningar för att definiera aspekter som paketbeskrivning, relaterade fel, beroenden och providerinformation.

The **Paketinställningar** är tillgänglig via **Redigera** knapp när [skapa](#creating-a-new-package) eller [redigera](#viewing-and-editing-package-information) ett paket och innehåller tre flikar för konfiguration. När du har gjort ändringarna klickar du **OK** för att spara dessa.

![packagenredigera](assets/packagesedit.png)

| **Fält** | **Beskrivning** |
|---|---|
| Namn | Paketets namn. |
| Grupp | Namnet på gruppen som paketet ska läggas till i, för att organisera paket. Skriv namnet på en ny grupp eller markera en befintlig grupp. |
| Version | Text som ska användas för den anpassade versionen. |
| Beskrivning | En kort beskrivning av paketet. HTML kan användas för formatering. |
| Miniatyrbild | Ikonen som visas med paketlistan. Klicka på Bläddra för att välja en lokal fil. |

![chlimage_1-344](assets/chlimage_1-344.png)

<table> 
 <tbody> 
  <tr> 
   <th><strong>Fält</strong></th> 
   <th><strong>Beskrivning</strong></th> 
   <th><strong>Format/exempel</strong></th> 
  </tr> 
  <tr> 
   <td>Namn</td> 
   <td>Namnet på providern.</td> 
   <td><em>AEM Geometrixx<br /> </em></td> 
  </tr> 
  <tr> 
   <td>URL</td> 
   <td>URL för providern.</td> 
   <td><em>https://www.aem-geometrixx.com</em></td> 
  </tr> 
  <tr> 
   <td>Länk</td> 
   <td>Paketspecifik länk till en providersida.</td> 
   <td><em>https://www.aem-geometrixx.com/mypackage.html</em></td> 
  </tr> 
  <tr> 
   <td>Kräver<br /> </td> 
   <td> 
    <ul> 
     <li>Administratör: Välj när paketet bara kan installeras av ett konto med administratörsbehörighet.</li> 
     <li>Starta om: Välj när servern måste startas om efter att paketet har installerats.</li> 
    </ul> </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td>AC-hantering</td> 
   <td><p>Ange hur åtkomstkontrollsinformationen som definieras i paketet ska hanteras när paketet importeras:</p> 
    <ul> 
     <li><strong>Ignorera</strong></li> 
     <li><strong>Skriv över</strong></li> 
     <li><strong>Sammanfoga</strong></li> 
     <li><strong>Rensa</strong></li> 
     <li><strong>MergePreserve</strong></li> 
    </ul> <p>Standardvärdet är <strong>Ignorera</strong>.</p> </td> 
   <td> 
    <ul> 
     <li><strong>Ignorera</strong> - bevara åtkomstkontrollistor i databasen</li> 
     <li><strong>Skriv över</strong> - skriv över åtkomstkontrollistor i databasen</li> 
     <li><strong>Sammanfoga</strong> - sammanfoga båda uppsättningar åtkomstkontrollistor</li> 
     <li><strong>Rensa</strong> - rensa åtkomstkontrollistor</li> 
     <li><strong>MergePreserve</strong> - lägg in åtkomstkontroll i innehållet med den som medföljer paketet genom att lägga till åtkomstkontrollposter för objekt som inte finns i innehållet</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

![paketerberoenden](assets/packagesdependencies.png)

| **Fält** | **Beskrivning** | **Format/exempel** |
|---|---|---|
| Testad med | Det produktnamn och den version som det här paketet har eller är kompatibelt med. | *AEM6* |
| Åtgärdade fel | Ett textfält där du kan visa information om fel som har åtgärdats i det här paketet. Visa varje fel på en separat rad. | bug-nr summary |
| Beroende på | Visar beroendeinformation som måste respekteras när andra paket är nödvändiga för att det aktuella paketet ska kunna köras som förväntat. Det här fältet är viktigt när du använder snabbkorrigeringar. | groupId:name:version |
| Ersätter | En lista över borttagna paket som det här paketet ersätter. Innan du installerar kontrollerar du att det här paketet innehåller allt nödvändigt innehåll från de föråldrade paketen, så att inget innehåll skrivs över. | groupId:name:version |

### Paketfilter {#package-filters}

Filter identifierar databasnoderna som ska inkluderas i paketet. A **Filterdefinition** anger följande information:

* The **Rotsökväg** av innehållet som ska inkluderas.
* **Regler** som innehåller eller exkluderar specifika noder under rotsökvägen.

Filter kan innehålla noll eller flera regler. När inga regler har definierats innehåller paketet allt innehåll under rotsökvägen.

Du kan definiera en eller flera filterdefinitioner för ett paket. Använd mer än ett filter för att inkludera innehåll från flera rotsökvägar.

![chlimage_1-345](assets/chlimage_1-345.png)

Följande tabell beskriver dessa regler och innehåller exempel:

<table> 
 <tbody> 
  <tr> 
   <th> Regeltyp</th> 
   <th>Beskrivning </th> 
   <th>Exempel </th> 
  </tr> 
  <tr> 
   <td> include</td> 
   <td>Du kan definiera en sökväg eller använda ett reguljärt uttryck för att ange alla noder som du vill ta med.<br /> <br /> Om du tar med en katalog kommer: 
    <ul> 
     <li>ta med katalogen <i>och</i> alla filer och mappar i den katalogen (dvs. hela underträdet)</li> 
     <li><strong>not</strong> ta med andra filer eller mappar från den angivna rotsökvägen</li> 
    </ul> </td> 
   <td>/libs/sling/install(/.*)? </td> 
  </tr> 
  <tr> 
   <td> exclude</td> 
   <td>Du kan ange en sökväg eller använda ett reguljärt uttryck för att ange alla noder som du vill utesluta.<br /> <br /> Om du exkluderar en katalog exkluderas den katalogen <i>och</i> alla filer och mappar i den katalogen (dvs. hela underträdet).<br /> </td> 
   <td>/libs/wcm/foundation/components(/.*)?</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Ett paket kan innehålla flera filterdefinitioner, så att noder från olika platser enkelt kan kombineras till ett paket.

Paketfilter definieras oftast först [skapa paketet](#creating-a-new-package), men de kan redigeras vid ett senare tillfälle (efter vilket paketet ska återskapas).

### Paketskärmbilder {#package-screenshots}

Du kan bifoga skärmbilder till ditt paket för att få en visuell representation av hur innehållet ser ut; genom att t.ex. tillhandahålla skärmbilder av nya funktioner.

### Paketikoner {#package-icons}

Du kan även bifoga en ikon till paketet för att få en snabb visuell representation av vad paketet innehåller. Detta visas sedan i paketlistan och kan hjälpa dig att enkelt identifiera paketet eller paketklassen.

Eftersom ett paket kan innehålla en ikon används följande konventioner för officiella paket:

>[!NOTE]
>
>Undvik förvirring genom att använda en beskrivande ikon för paketet och använd inte någon av de officiella ikonerna.

Officiellt snabbkorrigeringspaket:

![](do-not-localize/chlimage_1-28.png)

AEM eller tilläggspaket:

Officiella funktionspaket:

![](do-not-localize/chlimage_1-29.png)

## Pakethanteraren {#package-manager}

Pakethanteraren hanterar paketen i din lokala AEM. Efter att du har [har tilldelats nödvändiga behörigheter](#permissions-needed-for-using-the-package-manager) du kan använda pakethanteraren för olika åtgärder, bland annat för att konfigurera, bygga, hämta och installera dina paket. Nyckelelementen som ska konfigureras är:

* [Paketinställningar](#package-settings)
* [Paketfilter](#package-filters)

### Behörigheter som krävs för att använda Pakethanteraren {#permissions-needed-for-using-the-package-manager}

Om du vill ge användarna rätt att skapa, ändra, överföra och installera paket måste du ge dem rätt behörighet på följande platser:

* **/etc/paket** (fullständiga rättigheter exklusive radering)
* noden som innehåller paketets innehåll

Se [Ange behörigheter](/help/sites-administering/security.md) för instruktioner om hur du ändrar behörigheter.

### Skapa ett nytt paket {#creating-a-new-package}

Så här skapar du en ny paketdefinition:

1. På AEM välkomstskärm klickar du på **Paket** (eller från **verktyg** dubbelklicka på konsolen **Paket**).

1. Välj sedan **Pakethanteraren**.
1. Klicka **Skapa paket**.

   >[!NOTE]
   >
   >Om din instans har många paket kan det finnas en mappstruktur på plats, så du kan navigera till den önskade målmappen innan du skapar det nya paketet.

1. I dialogrutan:

   ![paketernyhet](assets/packagesnew.png)

   Ange följande:

   * **Gruppnamn**

      Målgruppens (eller mappens) namn. Grupper är avsedda att användas för att hjälpa dig att ordna dina paket.

      En mapp skapas för gruppen om den inte redan finns. Om du lämnar gruppnamnet tomt skapas paketet i huvudpaketlistan (Hem > Paket).

   * **Paketnamn**

      Namnet på det nya paketet. Välj ett beskrivande namn som hjälper dig (och andra) att enkelt identifiera innehållet i paketet.

   * **Version**

      Ett textfält där du kan ange en version. Detta läggs till paketnamnet för att bilda zip-filens namn.
   Klicka **OK** för att skapa paketet.

1. AEM listar det nya paketet i lämplig gruppmapp.

   ![packagesitem](assets/packagesitem.png)

   Klicka på ikonen eller paketnamnet som du vill öppna.

   ![packagesiklickad](assets/packagesitemclicked.png)

   >[!NOTE]
   >
   >Du kan vid behov gå tillbaka till den här sidan senare.

1. Klicka **Redigera** för att redigera [paketinställningar](#package-settings).

   Här kan du lägga till information och/eller definiera vissa inställningar. dessa innehåller till exempel en beskrivning, [icon](#package-icons), relaterade buggar och lägg till providerinformation.

   Klicka **OK** när du är klar med redigeringen av inställningarna.

1. Lägg till **[Skärmbilder](#package-screenshots)** till paketet efter behov. En instans är tillgänglig när paketet skapas. Lägg till fler om det behövs genom att använda **Package Screenshot** från sidosparken.

   Lägg till den faktiska bilden genom att dubbelklicka på bildkomponenten i **Skärmbilder** område, lägga till en bild och klicka **OK**.

1. Definiera **[Paketfilter](#package-filters)** genom att dra instanser av **Filterdefinition** från sidosparken och dubbelklicka sedan för att öppna för redigering:

   ![paketerfilter](assets/packagesfilter.png)

   Ange:

   * **Rotsökväg**
Det innehåll som ska förpackas. kan vara roten i ett underträd.
   * **Regler**
Reglerna är frivilliga. för enkla paketdefinitioner är det inte nödvändigt att ange inkluderings- eller exkluderingsregler.

      Om det behövs kan du definiera antingen [**Inkludera** eller **Exkludera** regler](#package-filters) för att exakt definiera paketets innehåll.

      Lägg till regler med **+** symbol, ta bort regler med **-** symbol. Reglerna tillämpas i den ordning de har, så att de kan placeras efter behov med **Upp** och **Ned** knappar.
   Klicka sedan på **OK** för att spara filtret.

   >[!NOTE]
   >
   >Du kan använda så många filterdefinitioner du behöver, men du måste se till att de inte hamnar i konflikt. Använd **Förhandsgranska** för att bekräfta vad innehållet i förpackningen ska vara.

1. För att bekräfta vad paketet innehåller kan du använda **Förhandsgranska**. Detta utför en torr körning av byggprocessen och visar allt som kommer att läggas till i paketet när det byggs.
1. Nu kan du [Bygge](#building-a-package) ditt paket.

   >[!NOTE]
   >
   >Det är inte obligatoriskt att bygga paketet just nu, det kan göras vid en senare tidpunkt.

### Bygga ett paket {#building-a-package}

Ett paket skapas ofta samtidigt som du [skapa paketdefinitionen](#creating-a-new-package), men du kan gå tillbaka vid ett senare tillfälle för att antingen skapa eller återskapa paketet. Detta kan vara användbart om innehållet i databasen har ändrats.

>[!NOTE]
>
>Innan du skapar paketet kan det vara användbart att förhandsgranska innehållet i paketet. Klicka för att göra detta **Förhandsgranska**.

1. Öppna paketdefinitionen från **Pakethanteraren** (klicka på paketikonen eller -namnet).

1. Klicka **Bygge**. En dialogruta där du uppmanas bekräfta att du vill skapa paketet.

   >[!NOTE]
   >
   >Detta är särskilt viktigt när du återskapar ett paket eftersom paketinnehållet skrivs över.

1. Klicka **OK**. AEM skapar paketet med allt innehåll som läggs till i paketet. När AEM är klar visas en bekräftelse på att paketet har skapats och (när du stänger dialogrutan) information om paketlistan uppdateras.

### Rewrapping a Package {#rewrapping-a-package}

När ett paket har byggts kan det vid behov rewrappas.

När du packar om ändras paketinformationen - *utan* ändra paketinnehållet. Paketinformationen är miniatyrbilden, beskrivningen osv., med andra ord allt du kan redigera med **Paketinställningar** dialogruta (för att öppna den här klickningen **Redigera**).

Ett viktigt användningsområde för ombrytning är när du förbereder ett paket för paketresursen. Du kan till exempel ha ett befintligt paket och bestämma dig för att dela det med andra. För det vill du lägga till en miniatyrbild och lägga till en beskrivning. I stället för att återskapa hela paketet med alla dess funktioner (vilket kan ta en stund och innebär att paketet inte längre är identiskt med originalpaketet) kan du kapsla in det och bara lägga till miniatyrbilden och beskrivningen.

1. Öppna paketdefinitionen från **Pakethanteraren** (klicka på paketikonen eller -namnet).

1. Klicka **Redigera** och uppdatera **[Paketinställningar](#package-settings)** efter behov. Klicka **OK** att spara.

1. Klicka **Radbryt** visas en dialogruta där du uppmanas bekräfta åtgärden.

### Visa och redigera paketinformation {#viewing-and-editing-package-information}

Så här visar eller redigerar du information om en paketdefinition:

1. Gå till det paket du vill visa i Pakethanteraren.
1. Klicka på paketikonen för det paket som du vill visa. Paketsidan med information om paketdefinitionen öppnas:

   ![packagesiklickad-1](assets/packagesitemclicked-1.png)

   >[!NOTE]
   >
   >Du kan även redigera och utföra vissa åtgärder på paketet från den här sidan.
   >
   >Vilka knappar som är tillgängliga beror på om paketet redan har skapats eller inte.

1. Om paketet redan har byggts klickar du **Innehåll**&#x200B;öppnas ett fönster där allt innehåll i paketet visas:

### Innehåll och testinstallation för visning av paket {#viewing-package-contents-and-testing-installation}

När ett paket har skapats kan du visa innehållet:

1. Gå till det paket du vill visa i Pakethanteraren.
1. Klicka på paketikonen för det paket som du vill visa. Detta öppnar paketsidan med information om paketdefinitionen.

1. Om du vill visa innehållet klickar du **Innehåll**&#x200B;öppnas ett fönster där allt innehåll i paketet visas:

   ![packningar](assets/packgescontents.png)

1. Om du vill göra en torr installation klickar du **Testinstallation**. När du har bekräftat åtgärden öppnas ett fönster där resultatet visas som om installationen utfördes:

   ![paketestestinstallera](assets/packagestestinstall.png)

### Hämtar paket till filsystemet {#downloading-packages-to-your-file-system}

I det här avsnittet beskrivs hur du hämtar ett paket från AEM till filsystemet med hjälp av **Pakethanteraren**.

>[!NOTE]
>
>Se [Paketresurs](#package-share) om du vill ha information om hur du hämtar snabbkorrigeringar, funktionspaket och paket från den offentliga delen och företagets interna del av paketdelningen.
>
>Från paketresurs kan du:
>
>* hämta paket från [Paketera Dela direkt i den lokala AEM instansen](#downloading-and-installing-packages-from-package-share).\
   >  När du laddar ned paketet importeras det till din databas. Därefter kan du omedelbart installera det på din lokala instans med **Pakethanteraren**. Dessa paket innehåller snabbkorrigeringar och andra delade paket.
>
>* hämta paket från [Paketera Dela till filsystemet](#downloading-packages-to-your-file-system-from-package-share).
>


1. På AEM välkomstskärm klickar du på **Paket** väljer **Pakethanteraren**.
1. Navigera till paketet som du vill hämta.

   ![paketerladda ned](assets/packagesdownload.png)

1. Klicka på länken som utgörs av zip-filens namn (understruken) för paketet som du vill hämta; till exempel `export-for-offline.zip`.

   AEM hämtar paketet till datorn (med en standarddialogruta för hämtning av webbläsare).

### Överför paket från filsystemet {#uploading-packages-from-your-file-system}

Med en paketöverföring kan du överföra ett paket från filsystemet till AEM Package Manager.

>[!NOTE]
>
>Se [Överför paket till företagets interna paketresurs](#uploading-a-package) om du vill överföra ett paket till företagets privata område i paketresursen.

Så här överför du ett paket:

1. Navigera till **Pakethanteraren**. Till den gruppmapp som du vill att paketet ska överföras till.

   ![paketerupload, knapp](assets/packagesuploadbutton.png)

1. Klicka **Överför paket**.

   ![paketeruploaddialog](assets/packagesuploaddialog.png)

   * **Fil**

      Du kan antingen skriva filnamnet direkt eller använda **Bläddra..** för att välja det paket som krävs från det lokala filsystemet (efter markeringen klickar du på **OK**).

   * **Tvinga överföring**

      Om det redan finns ett paket med det här namnet kan du klicka på det här om du vill framtvinga en överföring (och skriva över det befintliga paketet).
   Klicka **OK** så att det nya paketet överförs och visas i pakethanterarlistan.

   >[!NOTE]
   >
   >Om du vill göra innehållet tillgängligt för AEM ska du se till att [installera paketet](#installing-packages).

### Verifierar paket {#validating-packages}

Innan du installerar ett paket kanske du vill verifiera dess innehåll. Eftersom paket kan ändra överlagrade filer under `/apps` och/eller lägga till, ändra och ta bort åtkomstkontrollistor, är det ofta användbart att validera dessa ändringar innan du installerar.

#### Valideringsalternativ {#validation-options}

Valideringsmekanismen kan kontrollera följande egenskaper hos paketet:

* OSGi-paketimporter
* Övertäckningar
* ACL

Dessa alternativ beskrivs nedan.

* **Validera OSGi-paketimporter**

   **Vad är markerat**

   Den här valideringen undersöker paketet för alla JAR-filer (OSGi-paket) och extraherar deras `manifest.xml` (som innehåller de versionshanteringsberoenden som OSGi-paketet är beroende av) och verifierar den AEM instansen exporterar dessa beroenden med rätt versioner.

   **Hur det rapporteras**

   Alla versionshanteringsberoenden som inte kan uppfyllas av den AEM instansen visas i **Aktivitetslogg** för Package Manager.

   **Fellägen**

   Om beroenden inte uppfylls startar inte OSGi-paketen med dessa beroenden. Detta resulterar i en trasig programdistribution eftersom allt som förlitar sig på det OSGi-paket som inte startats i sin tur inte fungerar som det ska.

   **Felupplösning**

   För att åtgärda fel på grund av att OSGi-paketen inte är nöjd måste beroendeversionen i paketet med otillfredsställande importer justeras.

* **Validera övertäckningar**

   **Vad är markerat**

   Valideringen avgör om det paket som installeras innehåller en fil som redan finns i AEM.

   Med en befintlig övertäckning vid `/apps/sling/servlet/errorhandler/404.jsp`, ett paket som innehåller `/libs/sling/servlet/errorhandler/404.jsp`så att den befintliga filen ändras på `/libs/sling/servlet/errorhandler/404.jsp`.

   **Hur det rapporteras**

   Alla sådana övertäckningar beskrivs i **Aktivitetslogg** för Package Manager.

   **Fellägen**

   Ett feltillstånd innebär att paketet försöker distribuera en fil som redan är överlagrad, vilket innebär att ändringarna i paketet åsidosätts (och därmed&quot;döljs&quot;) av övertäckningen och inte börjar gälla.

   **Felupplösning**

   För att lösa det här problemet måste du ha kvar övertäckningsfilens innehåll i `/apps` måste granska ändringarna i den överlagrade filen i `/libs` och lägg in de ändringar som behövs i övertäckningen ( `/apps`) och distribuera om den överlagrade filen.

   >[!NOTE]
   >
   >Observera att valideringsfunktionen inte kan stämma av om det överlagda innehållet har integrerats korrekt i överläggsfilen. Valideringen fortsätter därför att rapportera om konflikter även efter att nödvändiga ändringar har gjorts.

* **Validera åtkomstkontrollistor**

   **Vad är markerat**

   Valideringen kontrollerar vilka behörigheter som läggs till, hur de hanteras (sammanfoga/ersätt) och om de aktuella behörigheterna påverkas.

   **Hur det rapporteras**

   Behörigheterna beskrivs i **Aktivitetslogg** för Package Manager.

   **Fellägen**

   Inga explicita fel kan anges. Valideringen anger bara om nya ACL-behörigheter kommer att läggas till eller påverkas av att paketet installeras.

   **Felupplösning**

   Med hjälp av den information som valideringen ger kan de påverkade noderna granskas i CRXDE och åtkomstkontrollistorna kan justeras i paketet efter behov.

   >[!CAUTION]
   >
   >Som god praxis rekommenderas att paket inte påverkar AEM-tillhandahållna åtkomstkontrollistor eftersom detta kan leda till oväntade produktbeteenden.

#### Utför validering {#performing-validation}

Paketvalidering kan göras på två olika sätt:

* Via pakethanterarens gränssnitt
* Via HTTP-POST-begäran, till exempel med cURL

>[!NOTE]
>
>Validering ska alltid ske efter att paketet har överförts, men innan det installeras.

**Paketvalidering via Pakethanteraren**

1. Öppna packningshanteraren på `https://<server>:<port>/crx/packmgr`
1. Markera paketet i listan och välj sedan **Mer** rullgardinsmeny från rubriken och sedan **Validera** i listrutan.

   >[!NOTE]
   >
   >Detta bör göras efter att du har överfört innehållspaketet, men innan du installerar paketet.

1. I den modala dialogrutan som visas använder du kryssrutorna för att välja valideringstyp(er) och börja valideringen genom att klicka **Validera**. Du kan även klicka **Avbryt**.

1. De valda valideringarna körs sedan. Resultaten visas i aktivitetsloggen för Package Manager.

**Paketvalidering via HTTP-POST-begäran**

Begäran om POST har följande format.

```
https://<host>:<port>/crx/packmgr/service.jsp?cmd=validate&type=osgiPackageImports,overlays,acls
```

>[!NOTE]
>
>The `type` parametern kan vara en kommaseparerad osorterad lista som består av:
>
>* `osgiPackageImports`
>* `overlays`
>* `acls`
>
>Värdet för `type` standardvärdet är `osgiPackageImports` om det inte godkänns.

Följande är ett exempel på hur du använder cURL för att köra en paketvalidering.

1. Om du använder cURL kör du en programsats som liknar följande:

   ```shell
   curl -v -X POST --user admin:admin -F file=@/Users/SomeGuy/Desktop/core.wcm.components.all-1.1.0.zip 'http://localhost:4502/crx/packmgr/service.jsp?cmd=validate&type=osgiPackageImports,overlays,acls'
   ```

1. Den begärda valideringen körs och svaret skickas tillbaka som ett JSON-objekt.

>[!NOTE]
>
>Svaret på en begäran om validering av HTTP-POST är ett JSON-objekt med valideringsresultatet.

### Installerar paket {#installing-packages}

När du har överfört ett paket måste du installera innehållet. Om paketinnehållet ska vara installerat och fungera måste det vara både:

* läses in i AEM (antingen [överförda från ditt filsystem](#uploading-packages-from-your-file-system) eller [hämtat från paketresurs](#downloading-and-installing-packages-from-package-share))

* installerat

>[!CAUTION]
>
>Om du installerar ett paket kan befintligt innehåll skrivas över eller tas bort. Överför bara ett paket om du är säker på att det inte tar bort eller skriver över innehåll som du behöver.
>
>Om du vill se innehållet i ett paket, eller hur det påverkar det, kan du:
>
>* Gör en testinstallation av paketet utan att ändra något av innehållet:\
   >  Öppna paketet (klicka på paketikonen eller paketnamnet) och klicka på **Testa installationen**.
>
>* Se en lista med paketets innehåll:\
   >  Öppna paketet och klicka på **Innehåll**.
>


>[!NOTE]
>
>Omedelbart innan du installerar ditt paket skapas ett ögonblicksbildspaket med det innehåll som ska skrivas över.
>
>Den här ögonblicksbilden installeras om/när du avinstallerar paketet.

>[!CAUTION]
>
>Om du installerar digitala resurser måste du:
>
>* Inaktivera först WorkflowLauncher.\
   >  Använd menyalternativet Komponenter i OSGi-konsolen för att inaktivera `com.day.cq.workflow.launcher.impl.WorkflowLauncherImpl`.
>
>* När installationen är klar återaktiverar du WorkflowLauncher.
>
>Genom att inaktivera WorkflowLauncher säkerställer du att Assets-importimeringsramverket inte (oavsiktligt) manipulerar resurserna vid installationen.

1. Gå till det paket du vill installera i Pakethanteraren.

   An **Installera** visas på sidan om paket som ännu inte har installerats.

   >[!NOTE]
   >
   >Du kan även öppna paketet genom att klicka på dess ikon för att öppna **Installera** där.

1. Klicka **Installera** för att starta installationen. En dialogruta begär bekräftelse och visar alla ändringar som görs. När du är klar klickar du **Stäng** i dialogrutan.

   Ordet **Installerad** visas bredvid paketet när det har installerats.

### Filsystembaserad överföring och installation {#file-system-based-upload-and-installation}

Det finns ett annat sätt att överföra och installera paket till din instans. I filsystemet har du en `crx-quicksart` och `license.properties` -fil. Du måste skapa en mapp med namnet `install` under `crx-quickstart`. Du kommer då att få något sådant: `<aem_home>/crx-quickstart/install`

I den här installationsmappen kan du lägga till dina paket direkt. De laddas automatiskt upp och installeras på din instans. När du är klar kan du se paketen i Package Manager.

Om instansen körs lägger du till ett paket i `install` -mappen startar direkt vid överföringen och installationen på instansen. Om din instans inte körs, kommer paketen du placerar i `install` -mappen installeras vid start i alfabetisk ordning.

>[!NOTE]
>
>Du kan också göra detta innan du ens startar instansen för första gången. För att göra det måste du skapa `crx-quickstart` skapa mappen manuellt `install` och placera paketen där. När du sedan startar instansen första gången installeras paketen i alfabetisk ordning.

### Avinstallerar paket {#uninstalling-packages}

AEM kan du avinstallera paket. Den här åtgärden återställer innehållet i databasen som påverkas av ögonblicksbilden som skapades omedelbart före paketinstallationen.

>[!NOTE]
>
>Vid installationen skapas ett ögonblicksbildspaket med det innehåll som ska skrivas över.
>
>Paketet installeras om när du avinstallerar paketet.

1. Gå till det paket som du vill avinstallera i Pakethanteraren.
1. Klicka på paketikonen för det paket som du vill avinstallera.
1. Klicka **Avinstallera** om du vill ta bort innehållet i det här paketet från databasen. En dialogruta begär bekräftelse och visar alla ändringar som görs. När du är klar klickar du **Stäng** i dialogrutan.

### Ta bort paket {#deleting-packages}

Så här tar du bort ett paket från pakethanterarlistan:

>[!NOTE]
>
>De installerade filerna/noderna från paketet är **not** borttagen.

1. I **verktyg** konsol, expandera **Paket** för att visa ditt paket i den högra rutan.

1. Klicka på det paket som du vill ta bort så att det är markerat och sedan antingen:

   * Klicka **Ta bort** i verktygsfältmenyn.
   * Högerklicka och välj **Ta bort**.

   ![paket:ta bort](assets/packagesdelete.png)

1. AEM ber om en bekräftelse på att du vill ta bort paketet. Klicka **OK** för att bekräfta borttagningen.

>[!CAUTION]
>
>Om det här paketet redan har installerats *installerat* innehållet **not** tas bort.

### Replikerar paket {#replicating-packages}

Replikera innehållet i ett paket för att installera det på publiceringsinstansen:

1. I **Pakethanteraren** navigera till det paket som du vill replikera.

1. Klicka på ikonen eller på namnet på det paket som du vill replikera för att expandera det.
1. I **Mer** nedrullningsbar meny i verktygsfältet väljer **Replikera**.

## Paketdelning {#package-share}

Paketresursen var en centraliserad server som är allmänt tillgänglig för delning av innehållspaket.

Den har ersatts med [Programvarudistribution.](#software-distribution)

## Programvarudistribution {#software-distribution}

[Programvarudistribution](https://downloads.experiencecloud.adobe.com) är det nya användargränssnittet som förenklar sökning och hämtning av AEM.

Mer information finns i [Dokumentation om programvarudistribution.](https://experienceleague.adobe.com/docs/experience-cloud/software-distribution/home.html)

>[!CAUTION]
>
>AEM pakethanterare kan för närvarande inte användas med programvarudistribution. Du hämtar dina paket till den lokala hårddisken.
