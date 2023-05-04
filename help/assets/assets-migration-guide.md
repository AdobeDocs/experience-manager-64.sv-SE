---
title: Migrera resurser till Adobe Experience Manager Assets i grupp
description: Så här lägger du in resurser i AEM, använder metadata, genererar renderingar och aktiverar dem för att publicera instanser.
contentOwner: AG
feature: Migration,Renditions,Asset Management
role: Architect,Admin
exl-id: 31da9f3d-460a-4b71-9ba0-7487f1b159cb
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1808'
ht-degree: 8%

---

# Guide för resursmigrering {#assets-migration-guide}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När du migrerar resurser till AEM finns det flera steg att tänka på. Extrahering av resurser och metadata från det aktuella hemmet ligger utanför det här dokumentets räckvidd eftersom det varierar mycket mellan implementeringar. I det här dokumentet beskrivs hur du hämtar dessa resurser till AEM, använder deras metadata, skapar återgivningar och aktiverar eller publicerar resurserna.

## Förutsättningar {#prerequisites}

Granska och implementera vägledningen i [Prestandajusteringstips för resurser](performance-tuning-guidelines.md). Många steg, till exempel konfigurera maximalt antal samtidiga jobb, förbättrar serverns stabilitet och prestanda vid inläsning. Andra steg, som konfiguration av fillagring, är svåra att utföra efter att systemet har lästs in med resurser.

>[!NOTE]
>
>Följande verktyg för resursmigrering ingår inte i Adobe Experience Manager. Adobe kundsupport stöder inte dessa verktyg.
>
>* ACS [!DNL Experience Manager] Tools Tag Maker
>* ACS [!DNL Experience Manager] Verktyg CSV-importerare för resurser
>* ACS Commons - massarbetsflödeshanterare
>* Snabbåtgärdshanteraren för ACS-kommandon
>* Syntetiskt arbetsflöde
>
>Programvaran är öppen källkod och täcks av [Apache v2-licensen](https://adobe-consulting-services.github.io/pages/license.html). Om du vill ställa en fråga eller rapportera ett problem går du till [ [!DNL Experience Manager] GitHub Issues for ACS Tools](https://github.com/Adobe-Consulting-Services/acs-aem-commons/issues) eller [ [!DNL Experience Manager] ACS Commons](https://github.com/Adobe-Consulting-Services/acs-aem-tools/issues).

## Migrera till [!DNL Experience Manager] {#migrate-to-aem}

Migrera resurser till [!DNL Experience Manager] kräver flera steg och bör visas som en process i flera steg. Flyttningsfaserna är följande:

1. Inaktivera arbetsflöden.
1. Läs in taggar.
1. Ingest assets.
1. Bearbeta återgivningar.
1. Aktivera resurser.
1. Aktivera arbetsflöden.

![chlimage_1-223](assets/chlimage_1-223.png)

### Inaktivera arbetsflöden {#disable-workflows}

Inaktivera startfunktionerna för `DAM Update Asset` arbetsflöde. Det är bäst att importera alla resurser till systemet och sedan köra arbetsflödena gruppvis. Om du redan är aktiv under migreringen kan du schemalägga dessa aktiviteter att köras utanför kontorstid.

### Läs in taggar {#load-tags}

Du kanske redan har en tagg-taxonomi på plats som du tillämpar på dina bilder. Verktyg som CSV-resursimporteraren och metadataprofilfunktionerna kan hjälpa dig att automatisera användningen av taggar i resurser. Lägg till taggarna i Experience Manager före detta. The [ACS [!DNL Experience Manager] Tools Tag Maker](https://adobe-consulting-services.github.io/acs-aem-tools/features/tag-maker/index.html) kan du fylla i taggar med hjälp av ett Microsoft Excel-kalkylblad som läses in i systemet.

### Ingående resurser {#ingest-assets}

Prestanda och stabilitet är viktiga frågor när du ska hämta in resurser i systemet. När du läser in mycket data i Experience Manager måste du se till att systemet fungerar bra. Detta minimerade den tid som krävs för att lägga till data och hjälper till att undvika att överbelasta systemet. Detta förhindrar att systemet kraschar, särskilt i system som redan är i produktion.

Det finns två sätt att läsa in resurser i systemet: en push-baserad metod med HTTP eller en pull-baserad metod med JCR-API:erna.

#### Tryck igenom HTTP {#push-through-http}

Adobe Managed Services-team använder ett verktyg som heter Glutton för att läsa in data i kundmiljöer. Glutton är ett litet Java-program som läser in alla resurser från en katalog till en annan katalog på en [!DNL Experience Manager] -instans. I stället för Glutton kan du också använda verktyg som Perl-skript för att publicera resurserna i databasen.

Det finns två nackdelar med att använda metoden att gå igenom https:

1. Överför resurserna via HTTP till servern. Detta kräver en hel del extraarbete och är tidskrävande, vilket gör att det tar längre tid att utföra migreringen.
1. Om du har taggar och anpassade metadata som måste användas för resurserna, kräver den här metoden en andra anpassad process som du måste köra för att använda dessa metadata för resurserna när de har importerats.

Det andra sättet att importera resurser är att hämta resurser från det lokala filsystemet. Om du inte kan få en extern enhet eller nätverksresurs monterad på servern för att utföra en pull-baserad metod är det bästa alternativet att publicera resurserna via HTTP.

#### Dra från det lokala filsystemet {#pull-from-the-local-file-system}

The [ACS [!DNL Experience Manager] Verktyg CSV-importerare för resurser](https://adobe-consulting-services.github.io/acs-aem-tools/features/csv-asset-importer/index.html) hämtar resurser från filsystemet och metadata för resurser från en CSV-fil för resursimporten. The [!DNL Experience Manager] Resurshanterarens API används för att importera resurserna till systemet och tillämpa de konfigurerade metadataegenskaperna. Resurser monteras helst på servern via en nätverksfilmontering eller via en extern enhet.

När resurser inte överförs via ett nätverk förbättras prestandan avsevärt. Den här metoden är vanligtvis den mest effektiva metoden för att läsa in resurser i databasen. Dessutom kan du importera alla resurser och metadata i ett enda steg eftersom verktyget har stöd för metadatahämtning. Du behöver inte utföra något annat steg för att använda metadata, till exempel använda ett separat verktyg.

### Bearbeta återgivningar {#process-renditions}

När du har läst in resurserna i systemet måste du bearbeta dem via arbetsflödet DAM Update Asset för att extrahera metadata och generera renderingar. Innan du utför det här steget måste du duplicera och ändra arbetsflödet för DAM-uppdatering av resurser efter dina behov. Vissa steg i standardarbetsflödet är kanske inte nödvändiga för dig, till exempel Dynamic Media Classic PTIFF-generering eller serverintegrering med InDesign.

När du har konfigurerat arbetsflödet efter dina behov kan du utföra det på två sätt:

1. Det enklaste sättet är [ACS Commons massarbetsflödeshanterare](https://adobe-consulting-services.github.io/acs-aem-commons/features/bulk-workflow-manager.html). Med det här verktyget kan du köra en fråga och bearbeta resultatet av frågan via ett arbetsflöde. Det finns även alternativ för att ange gruppstorlekar.
1. Du kan använda [ACS Commons Fast Action Manager](https://adobe-consulting-services.github.io/acs-aem-commons/features/fast-action-manager.html) tillsammans med [syntetiska arbetsflöden](https://adobe-consulting-services.github.io/acs-aem-commons/features/synthetic-workflow.html). Även om det här tillvägagångssättet är mycket mer involverat kan du ta bort overheadkostnaderna för [!DNL Experience Manager] arbetsflödesmotor samtidigt som serverresurser optimeras. Dessutom förbättrar Fast Action Manager resultatet ytterligare genom att övervaka serverresurser dynamiskt och begränsa belastningen på systemet. Exempel på skript finns på funktionssidan för ACS Commons.

### Aktivera resurser {#activate-assets}

För distributioner som har en publiceringsnivå måste du aktivera resurserna i publiceringsgruppen. Adobe rekommenderar att du kör mer än en publiceringsinstans, men det är mest effektivt att replikera alla resurser till en publiceringsinstans och sedan klona den instansen. När du aktiverar ett stort antal resurser kan du behöva ingripa efter att ha aktiverat ett träd. Därför: När aktiveringar utlöses läggs objekt till i kön för delningsuppgifter/händelser. När storleken på den här kön börjar bli över cirka 40 000 objekt tar det dramatiskt lång tid att bearbeta. När storleken på den här kön överstiger 100 000 objekt börjar systemstabiliteten försämras.

Du kan använda [Snabb Action Manager](https://adobe-consulting-services.github.io/acs-aem-commons/features/fast-action-manager.html) för att hantera resursreplikering. Detta fungerar utan att använda Sling-köerna, vilket sänker overheadkostnaderna samtidigt som arbetsbelastningen begränsas för att förhindra att servern blir överbelastad. Ett exempel på hur du använder FAM för att hantera replikering visas på funktionens dokumentationssida.

Andra alternativ för att hämta resurser till publiceringsgruppen är bland annat att använda [vlt-rcp](https://jackrabbit.apache.org/filevault/rcp.html) eller [oak-run](https://github.com/apache/jackrabbit-oak/tree/trunk/oak-run), som ingår i Jackrabbit. Ett annat alternativ är att använda ett verktyg som bygger på öppen källkod för [!DNL Experience Manager] infrastruktur anropad [Grabbit](https://github.com/TWCable/grabbit), som sägs ha snabbare prestanda än Valt.

För någon av dessa metoder är caveat att resurserna i författarinstansen inte visas som aktiverade. Om du vill hantera flaggning av dessa resurser med rätt aktiveringsstatus måste du också köra ett skript som markerar resurserna som aktiverade.

>[!NOTE]
>
>Adobe stöder inte Grabbit.

### Klona publicering {#clone-publish}

När resurserna har aktiverats kan du klona publiceringsinstansen och skapa så många kopior som behövs för distributionen. Det är ganska enkelt att klona en server, men det finns några viktiga steg att komma ihåg. Så här klonar du publiceringen:

1. Säkerhetskopiera källinstansen och datalagret.
1. Återställ säkerhetskopian av instansen och datalagret till målplatsen. Följande steg hänvisar alla till den nya instansen.
1. Utför en filsystemsökning under `crx-quickstart/launchpad/felix` for `sling.id`. Ta bort den här filen.
1. Under rotsökvägen för datalagret letar du upp och tar bort alla `repository-XXX` filer.
1. Redigera `crx-quickstart/install/org.apache.jackrabbit.oak.plugins.blob.datastore.FileDataStore.config` och `crx-quickstart/launchpad/config/org/apache/jackrabbit/oak/plugins/blob/datastore/FileDataStore.config` för att peka på platsen för datalagret i den nya miljön.
1. Starta miljön.
1. Uppdatera konfigurationen för alla replikeringsagenter på författaren/författarna så att de pekar på rätt publiceringsinstanser eller push-agenter för dispatcher på den nya instansen för att peka på rätt dispatchers för den nya miljön.

### Aktivera arbetsflöden {#enable-workflows}

När migreringen är klar bör startarna för DAM Update Asset-arbetsflödena återaktiveras för att stödja generering av återgivningar och metadataextrahering för den dagliga systemanvändningen.

## Migrera resurser över [!DNL Experience Manager] distributioner {#migrate-between-aem-instances}

Även om det inte är nästan lika vanligt, behöver du ibland migrera stora mängder data från en [!DNL Experience Manager] instans till annan. till exempel när du utför en [!DNL Experience Manager] uppgradera, uppgradera din maskinvara eller migrera till ett nytt datacenter, till exempel med en AMS-migrering.

I det här fallet är dina resurser redan ifyllda med metadata och återgivningar har redan genererats. Du kan helt enkelt fokusera på att flytta resurser från en instans till en annan. Vid migrering mellan [!DNL Experience Manager] -instanser utför du följande steg:

1. Inaktivera arbetsflöden: Eftersom du migrerar återgivningar tillsammans med våra resurser, vill du inaktivera arbetsflödesstarterna för DAM Update Asset.

1. Migrera taggar: Eftersom du redan har taggar inlästa i källan [!DNL Experience Manager] du kan till exempel skapa dem i ett innehållspaket och installera paketet på målinstansen.

1. Migrera resurser: Det finns två verktyg som rekommenderas för att flytta resurser från en [!DNL Experience Manager] till en annan instans:

   * **Fjärrkopia av valv**, eller `vlt rcp`kan du använda VLT i ett nätverk. Du kan ange en käll- och målkatalog och hämta alla databasdata från en instans och läsa in dem i en annan. Vlt rcp finns dokumenterad på [https://jackrabbit.apache.org/filevault/rcp.html](https://jackrabbit.apache.org/filevault/rcp.html)
   * **Grabbit** är ett verktyg för innehållssynkronisering med öppen källkod som utvecklats av Time Warner Cable för deras [!DNL Experience Manager] implementering. Eftersom den använder kontinuerliga dataströmmar har den en lägre fördröjning jämfört med vlt rcp och kräver en hastighetsförbättring på två till tio gånger snabbare än vlt rcp. Grabbit har även stöd för synkronisering av deltainnehåll, vilket gör att det kan synkronisera ändringar efter att en första migreringspass har slutförts.

1. Aktivera resurser: Följ instruktionerna för [aktivera resurser](#activate-assets) dokumenteras för den inledande migreringen till AEM.

1. Klonpublicering: Precis som med en ny migrering är det effektivare att läsa in en publiceringsinstans och klona den än att aktivera innehållet på båda noderna. Se [Klonar publicering.](#clone-publish)

1. Aktivera arbetsflöden: När du är klar med migreringen kan du aktivera startfunktionerna för arbetsflödena för DAM Update Asset för att stödja generering av återgivningar och extrahering av metadata för den dagliga systemanvändningen.
