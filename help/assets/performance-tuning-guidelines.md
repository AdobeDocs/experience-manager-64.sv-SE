---
title: Prestandajusteringsguide för resurser
description: Viktiga fokusområden kring AEM-konfiguration, ändringar av maskinvara, programvara och nätverkskomponenter för att ta bort flaskhalsar och optimera prestanda för AEM Assets.
contentOwner: AG
translation-type: tm+mt
source-git-commit: af5f8a24db589ecdbe28d603ab9583f11d29212c

---


# Prestandajusteringsguide för resurser {#assets-performance-tuning-guide}

En AEM-konfiguration (Adobe Experience Manager) innehåller ett antal maskinvaru-, programvaru- och nätverkskomponenter. Beroende på ditt driftsättningsscenario kan du behöva specifika konfigurationsändringar för maskinvara, programvara och nätverkskomponenter för att ta bort flaskhalsar i prestandan.

Genom att identifiera och följa vissa riktlinjer för optimering av maskinvara och programvara kan du dessutom skapa en stabil grund som gör att driftsättningen av AEM Assets kan uppfylla förväntningarna på prestanda, skalbarhet och tillförlitlighet.

Dåliga prestanda i AEM Assets kan påverka användarupplevelsen när det gäller interaktiva prestanda, bearbetning av resurser, nedladdningshastighet och andra områden.

Prestandaoptimering är en grundläggande uppgift som du utför innan du fastställer målvärden för ett projekt.

Här är några viktiga fokusområden där du kan identifiera och åtgärda prestandaproblem innan de påverkar användarna.

## Platform {#platform}

AEM stöds på ett antal plattformar, men Adobe har funnit det bästa stödet för inbyggda verktyg i Linux och Windows, vilket ger optimala prestanda och förenklad implementering. Det bästa är att driftsätta ett 64-bitars operativsystem för att uppfylla de höga minneskraven för en AEM Assets-driftsättning. Precis som för alla AEM-distributioner bör du implementera tarMK där det är möjligt. Även om TonaMK inte kan skalas bortom en enda författarinstans, fungerar det bättre än MongoMK. Du kan lägga till instanser av TjärMK-avlastning för att öka arbetsflödets bearbetningskraft i din AEM Assets-distribution.

### Tillfällig mapp {#temp-folder}

Om du vill förbättra överföringstiden för resurser använder du lagring med höga prestanda för den tillfälliga Java-katalogen. I Linux och Windows kan en RAM-enhet eller SSD användas. I molnbaserade miljöer kan en motsvarande typ av höghastighetslagring användas. I till exempel Amazon EC2 kan en [tillfällig](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/InstanceStorage.html) enhet användas för den tillfälliga mappen.

Om servern har tillräckligt med minne konfigurerar du en RAM-enhet. Kör följande kommandon i Linux för att skapa en 8 GB RAM-enhet:

```
mkfs -q /dev/ram1 800000
 mkdir -p /mnt/aem-tmp
 mount /dev/ram1 /mnt/aem-tmp
 df -H | grep aem-tmp
```

I Windows måste du använda en drivrutin från tredje part för att skapa en RAM-enhet eller bara använda lagring med höga prestanda, som SSD.

När den tillfälliga volymen med höga prestanda är klar anger du JVM-parametern -Djava.io.tmpdir. Du kan till exempel lägga till JVM-parametern nedan till variabeln CQ_JVM_OPTS i skriptet bin/start för AEM:

`-Djava.io.tmpdir=/mnt/aem-tmp`

## Java-konfiguration {#java-configuration}

### Java-version {#java-version}

Eftersom Oracle har slutat släppa uppdateringar för Java 7 från och med april 2015 rekommenderar Adobe att man driftsätter AEM Assets på Java 8. I vissa fall har den visat bättre prestanda.

### JVM-parametrar {#jvm-parameters}

Du bör ange följande JVM-parametrar:

* `-XX:+UseConcMarkSweepGC`
* `-Doak.queryLimitInMemory`=500000
* `-Doak.queryLimitReads`=100000
* `-Dupdate.limit`=250000
* `-Doak.fastQuerySize`=true

## Datalagring och minneskonfiguration {#data-store-and-memory-configuration}

### Konfiguration av fillagring {#file-data-store-configuration}

Du bör separera datalagret från segmentlagret för alla AEM Resurser-användare. Dessutom kan konfigurering av parametrarna `maxCachedBinarySize` och `cacheSizeInMB` hjälpa till att maximera prestandan. Ange `maxCachedBinarySize` den minsta filstorlek som kan sparas i cachen. Ange storleken på den minnescache som ska användas för datalagret i `cacheSizeInMB`. Adobe rekommenderar att du anger det här värdet mellan 2 och 10 procent av den totala stackstorleken. Inläsnings-/prestandatestning kan dock hjälpa till att fastställa den idealiska inställningen.

### Konfigurera maximal storlek för buffrad bildcache {#configure-the-maximum-size-of-the-buffered-image-cache}

När du överför stora mängder resurser till Adobe Experience Manager kan du minska den konfigurerade maxstorleken för buffrat bildcacheminne för att undvika oväntade ökningar i minnesanvändningen och för att förhindra att JVM misslyckas med OutOfMemoryErrors. Tänk dig ett exempel på att du har ett system med en högsta heap (- `Xmx`param) på 5 GB, en Oak BlobCache inställd på 1 GB och dokumentcache inställd på 2 GB. I det här fallet tar den buffrade cachen upp till 1,25 GB och minne, vilket innebär att endast 0,75 GB minne återstår för oväntade toppar.

Konfigurera den buffrade cachestorleken i OSGi-webbkonsolen. Vid `https://host:port/system/console/configMgr/com.day.cq.dam.core.impl.cache.CQBufferedImageCache`anger du egenskapen `cq.dam.image.cache.max.memory` i byte. 1073741824 är till exempel 1 GB (1 024 x 1 024 x 1 024 = 1 GB).

Om du använder en nod för att konfigurera den här egenskapen från AEM 6.1 SP1 måste du ange datatypen Long om du använder en `sling:osgiConfig` nod. Mer information finns i [CQBufferedImageCache förbrukar heap under överföring](https://helpx.adobe.com/experience-manager/kb/cqbufferedimagecache-consumes-heap-during-asset-uploads.html)av resurser.

### Gemensamma datalager {#shared-data-stores}

Implementering av ett S3- eller delat fildatalager kan bidra till att spara diskutrymme och öka nätverkets genomströmning i storskaliga implementeringar. Mer information om fördelar och nackdelar med att använda ett delat datalager finns i [Handbok](assets-sizing-guide.md)för resursstorlek.

### S3-datalager {#s-data-store}

Följande S3 Data Store-konfiguration ( `org.apache.jackrabbit.oak.plugins.blob.datastore.S3DataStore.cfg`) hjälper Adobe att extrahera 12,8 TB binära stora objekt (BLOB) från ett befintligt arkiv till ett S3-datalager på en kunds webbplats:

```
accessKey=<snip>
 secretKey=<snip>
 s3Bucket=<snip>
 s3Region=us-standard
 s3EndPoint=<a href="https://s3.amazonaws.com/">s3.amazonaws.com</a>
 connectionTimeout=120000
 socketTimeout=120000
 maxConnections=80
 writeThreads=60
 concurrentUploadsThreads=30
 asyncUploadLimit=30
 maxErrorRetry=1000
 path=/opt/author/crx-quickstart/repository/datastore
 s3RenameKeys=false
 s3Encryption=SSE_S3
 proactiveCaching=true
 uploadRetries=1000
 migrateFailuresCount=400
```

## Nätverksoptimering {#network-optimization}

Adobe rekommenderar att du aktiverar HTTPS eftersom många företag har brandväggar som förhindrar HTTP-trafik, vilket påverkar överföringar negativt och gör att filer skadas. För stora filöverföringar måste användarna ha kabelanslutna anslutningar till nätverket eftersom ett WiFi-nätverk snabbt blir mättat. Riktlinjer för hur du identifierar flaskhalsar i nätverk finns i [Handbok](assets-sizing-guide.md)för resursstorlek. Information om hur du utvärderar nätverksprestanda genom att analysera nätverkstopologi finns i [Resurser för nätverksaspekter](assets-network-considerations.md).

Din nätverksoptimeringsstrategi är i första hand beroende av hur mycket bandbredd som är tillgänglig och hur stor belastning din AEM-instans har. Gemensamma konfigurationsalternativ, inklusive brandväggar och proxies, kan förbättra nätverkets prestanda. Här följer några viktiga punkter att tänka på:

* Beroende på vilken instanstyp du har (liten, måttlig, stor) kontrollerar du att du har tillräcklig nätverksbandbredd för AEM-instansen. Lämplig bandbreddsallokering är särskilt viktig om AEM ligger på AWS.
* Om din AEM-instans finns på AWS kan du dra nytta av en mångsidig skalningspolicy. Överför instansen om användarna förväntar sig hög belastning. Minska storleken för måttlig/låg belastning.
* HTTPS: De flesta användare har brandväggar som tolkar HTTP-trafik, vilket kan påverka överföringen av filer negativt eller till och med skada filer under överföringen.
* Stora filöverföringar: Se till att användarna har kabelanslutna anslutningar till nätverket (WiFi-anslutningar blir snabbt mättade).

## Arbetsflöden {#workflows}

### Övergående arbetsflöden {#transient-workflows}

Ställ in arbetsflödet DAM Update Asset på Transient när det är möjligt. Inställningen minskar avsevärt de allmänna kostnader som krävs för att bearbeta arbetsflöden, eftersom arbetsflöden i det här fallet inte behöver passera genom de normala spårnings- och arkiveringsprocesserna.

>[!NOTE]
>
>Som standard är arbetsflödet för DAM-uppdatering av tillgångar inställt på Transient i AEM 6.3. I så fall kan du hoppa över följande procedur.

1. Öppna `http://localhost:4502/miscadmin` den AEM-instans som du vill konfigurera.

1. Expandera **[!UICONTROL Verktyg]** > **[!UICONTROL Arbetsflöde]** > **[!UICONTROL Modeller]** > **[!UICONTROL dam]** i navigeringsträdet.
1. Dubbelklicka på **[!UICONTROL DAM Update Asset]**.
1. Gå till fliken **[!UICONTROL Sida]** i den flytande verktygspanelen och klicka sedan på **[!UICONTROL Sidegenskaper]**.
1. Välj **[!UICONTROL Övergående arbetsflöde]** och klicka på **[!UICONTROL OK]**.

   >[!NOTE]
   >
   >Vissa funktioner har inte stöd för tillfälliga arbetsflöden. Om din AEM Assets-distribution kräver dessa funktioner ska du inte konfigurera tillfälliga arbetsflöden.

   Om det inte går att använda tillfälliga arbetsflöden kör du regelbundet arbetsflödesrensning för att ta bort arkiverade arbetsflöden för DAM Update Asset för att säkerställa att systemprestanda inte försämras.

   Vanligtvis bör du köra rensningsarbetsflöden varje vecka. I resurskrävande scenarier, till exempel vid omfattande tillgångsinhämtning, kan du dock köra det oftare.

   Om du vill konfigurera rensning av arbetsflöden lägger du till en ny Adobe Granite Workflow Renge-konfiguration via OSGi-konsolen. Konfigurera och schemalägg arbetsflödet som en del av veckounderhållsperioden.

   Om tömningen är för lång så tar det för lång tid. Därför bör du se till att rensningsjobben är fullständiga för att undvika situationer där rensningsarbetsflödena misslyckas på grund av det stora antalet arbetsflöden.

   När du har kört flera icke-tillfälliga arbetsflöden (som skapar arbetsflödesinstansnoder) kan du köra [ACS AEM Commons Workflow Remover](https://adobe-consulting-services.github.io/acs-aem-commons/features/workflow-remover.html) på ad hoc-basis. Det tar bort överflödiga, slutförda arbetsflödesinstanser direkt i stället för att vänta på att schemaläggaren för rensning av arbetsflödet i Adobe Granite ska köras.

### Maximalt antal parallella jobb {#maximum-parallel-jobs}

Som standard kör AEM ett maximalt antal parallella jobb som motsvarar antalet processorer på servern. Problemet med den här inställningen är att under perioder med hög belastning används alla processorer av arbetsflödena för DAM Update Asset, vilket gör att användargränssnittet tar längre tid och förhindrar att AEM kör andra processer som skyddar serverns prestanda och stabilitet. Det är en god vana att ange det här värdet till hälften av de processorer som är tillgängliga på servern genom att utföra följande steg:

1. På AEM Author går du till [http://localhost:4502/system/console/slingevent](http://localhost:4702/system/console/slingevent).
1. Klicka på Redigera i varje arbetsflödeskö som är relevant för implementeringen, till exempel Bevilja tillfällig arbetsflödeskö.
1. Ändra värdet för Maximalt antal parallella jobb och klicka på Spara.

Att ställa in en kö på hälften av de tillgängliga processorerna är en användbar lösning att börja med. Du kan dock behöva öka eller minska det här antalet för att få maximal genomströmning och justera det efter miljö. Det finns separata köer för tillfälliga och icke-tillfälliga arbetsflöden samt andra processer, till exempel externa arbetsflöden. Om flera köer är inställda på 50 % av processorerna aktiva samtidigt kan systemet snabbt bli överbelastat. De köer som används ofta varierar mycket mellan olika implementeringar. Därför kan du behöva konfigurera dem noggrant för maximal effektivitet utan att ge avkall på serverstabiliteten.

### Avlastning {#offloading}

För stora arbetsflöden eller arbetsflöden som är resurskrävande, till exempel videotranskodning, kan du avlasta arbetsflöden för DAM Update Asset till en andra författarinstans. Problemet med avlastning är ofta att eventuell inläsning som sparas genom avlastning av arbetsflödesbearbetningen motverkas av kostnaden för att replikera innehållet fram och tillbaka mellan instanser.

Från och med AEM 6.2 och med ett funktionspaket för AEM 6.1 kan du utföra avlastning med binär replikering. I den här modellen delar författarinstanserna ett vanligt datalager och skickar bara metadata fram och tillbaka genom framåtreplikering. Detta fungerar bra med ett delat fildatalager, men det kan uppstå problem med ett S3-datalager. Eftersom bakgrundstrådar kan orsaka fördröjning är det möjligt att en resurs inte har skrivits till datalagret innan avlastningsjobbet startar.

### DAM-uppdateringskonfiguration {#dam-update-asset-configuration}

Arbetsflödet för DAM-uppdatering av resurser innehåller en komplett serie steg som är konfigurerade för uppgifter, till exempel Scene7 PTIFF-generering och InDesign Server-integrering. De flesta användare behöver dock inte utföra flera av dessa steg. Adobe rekommenderar att du skapar en anpassad kopia av arbetsflödesmodellen DAM Update Asset och tar bort alla onödiga steg. I det här fallet ska du uppdatera startarna för DAM Update Asset så att de pekar på den nya modellen.

>[!NOTE]
>
>Om du kör arbetsflödet DAM Update Asset kraftigt kan du öka storleken på filens datalager. Resultaten från ett experiment som Adobe har utfört har visat att datalagrets storlek kan öka med ungefär 400 GB om ca 500 arbetsflöden utförs inom 8 timmar.
>
>Det är en tillfällig ökning och datalagret återställs till den ursprungliga storleken när du har kört skräpinsamlingsaktiviteten för datalagret.
>
>Vanligtvis körs skräpinsamlingsaktiviteten för datalager varje vecka tillsammans med andra schemalagda underhållsaktiviteter.
>
>Om du har begränsat diskutrymme och kör arbetsflöden för DAM-uppdatering av resurser intensivt bör du överväga att schemalägga skräpinsamlingen oftare.

#### Generering av rendering vid körning {#runtime-rendition-generation}

Kunderna använder bilder av olika storlek och format på sin webbplats eller för att distribuera dem till affärspartners. Eftersom varje återgivning ökar utrymmet för resursen i databasen rekommenderar Adobe att du använder funktionen noggrant. Om du vill minska mängden resurser som behövs för att bearbeta och lagra bilder kan du generera dessa bilder vid körning i stället för som återgivningar vid importen.

Många webbplatskunder implementerar en bildservett som ändrar storlek på och beskär bilder när de begärs, vilket medför ytterligare belastning på publiceringsinstansen. Så länge dessa bilder kan cachas kan utmaningen dock mildras.

Ett annat sätt är att använda Scene7-teknik för att helt och hållet överlåta bildbearbetning. Dessutom kan ni driftsätta varumärkesportalen som inte bara tar över ansvaret för att skapa renderingar från AEM-infrastrukturen, utan även hela publiceringsnivån.

#### ImageMagick {#imagemagick}

Om du anpassar arbetsflödet DAM Update Asset för att generera återgivningar med ImageMagick rekommenderar Adobe att du ändrar filen policy.xml på */etc/ImageMagick/*. Som standard använder ImageMagick hela det tillgängliga diskutrymmet på operativsystemsvolymen och det tillgängliga minnet. Gör följande konfigurationsändringar i avsnittet `policymap` policy.xml för att begränsa dessa resurser.

```xml
<policymap>
  <!-- <policy domain="system" name="precision" value="6"/> -->
  <policy domain="resource" name="temporary-path" value="/ephemeral0/imagemagick_tmp"/>
  <policy domain="resource" name="memory" value="1000MiB"/>
  <policy domain="resource" name="map" value="1000MiB"/>
  <!-- <policy domain="resource" name="area" value="1gb"/> -->
  <policy domain="resource" name="disk" value="10000MiB"/>
  <!-- <policy domain="resource" name="file" value="768"/> -->
  <policy domain="resource" name="thread" value="1"/>
  <policy domain="resource" name="throttle" value="50"/>
  <!-- <policy domain="resource" name="time" value="3600"/> -->
</policymap>
```

Dessutom anger du sökvägen till ImageMagick:s temporära mapp i filen *configure.xml* (eller genom att ange systemvariabeln `MAGIC_TEMPORARY_PATH`) till en diskpartition som har tillräckligt med utrymme och IOPS.

>[!CAUTION]
>
>En felaktig konfiguration kan göra servern instabil om ImageMagick använder allt tillgängligt diskutrymme. De principändringar som krävs för att bearbeta stora filer med ImageMagick kan påverka AEM-prestanda. Mer information finns i [Installera och konfigurera ImageMagick](best-practices-for-imagemagick.md).

>[!NOTE]
>
>ImageMagick `policy.xml` - och `configure.xml` -filerna finns under `/usr/lib64/ImageMagick-*/config/` i stället för `/etc/ImageMagick/`. Mer information om [konfigurationsfilernas placering finns i dokumentationen](https://www.imagemagick.org/script/resources.php) till ImageMagick.

Om du använder AEM på Adobes hanterade tjänster (AMS) kan du kontakta Adobes kundtjänst om du tänker bearbeta många stora PSD- eller PSB-filer. Det går inte att bearbeta PSB-filer med hög upplösning som är större än 3 000 × 2 3 000 pixlar i Experience Manager.

<!-- 

#### Sub-asset generation and page extraction {#sub-asset-generation-and-page-extraction}

During asset uploads, AEM's workflow creates a separate asset for each page in PDF and Office documents. Each of these pages is an asset by itself, which consumes additional disk space, requires versioning and additional workflow processing. If you do not require separate pages, disable Sub Asset Generation and Page Extraction.

To disable Sub Asset generation, do the following:

1. Open the **[!UICONTROL Workflow Console]** tool by going to */libs/cq/workflow/content/console.html*

1. Select the **[!UICONTROL Models]** tab
1. Double click the **[!UICONTROL DAM Update Asset]** workflow model
1. Delete **[!UICONTROL Process Sub Asset]** step from **[!UICONTROL DAM Update Asset]** workflow model.

1. Click on **[!UICONTROL Save]**

To disable Page Extraction:

1. Open the **[!UICONTROL Workflow Console]** tool by going to */libs/cq/workflow/content/console.html*

1. Select the **[!UICONTROL Launchers]** tab
1. Select a launcher that launches **[!UICONTROL DAM Parse Word Documents]** workflow model 
1. Click **[!UICONTROL Edit]**
1. Select **[!UICONTROL Disable]**
1. Click **[!UICONTROL OK]**
1. Repeat steps 3-6 for other launcher items that use **DAM Parse Word Documents **workflow model 

-->

<!--
# Sub-asset generation and page extraction {#sub-asset-generation-and-page-extraction}

During asset uploads, AEM's workflow creates a separate asset for each page in PDF and Office documents. Each of these pages is an asset by itself, which consumes additional disk space, requires versioning and additional workflow processing. If you do not require separate pages, disable Sub Asset Generation and Page Extraction.

To disable Sub Asset generation, do the following:

1. Open the **[!UICONTROL Workflow Console]** tool by going to */libs/cq/workflow/content/console.html*

1. Select the **[!UICONTROL Models]** tab
1. Double click the **[!UICONTROL DAM Update Asset]** workflow model
1. Delete **[!UICONTROL Process Sub Asset]** step from **[!UICONTROL DAM Update Asset]** workflow model.

1. Click on **[!UICONTROL Save]**

To disable Page Extraction:

1. Open the **[!UICONTROL Workflow Console]** tool by going to */libs/cq/workflow/content/console.html*

1. Select the **[!UICONTROL Launchers]** tab
1. Select a launcher that launches **[!UICONTROL DAM Parse Word Documents]** workflow model.
1. Click **[!UICONTROL Edit]**
1. Select **[!UICONTROL Disable]**
1. Click **[!UICONTROL OK]**
1. Repeat steps 3-6 for other launcher items that use **DAM Parse Word Documents** workflow model.
-->

### XMP-tillbakaskrivning {#xmp-writeback}

XMP-tillbakaskrivning uppdaterar originalresursen när metadata ändras i AEM, vilket ger följande resultat:

* Själva tillgången ändras
* En version av resursen skapas
* DAM Update Asset körs mot resursen

De listade resultaten kräver stora resurser. Därför rekommenderar Adobe att du [inaktiverar XMP-återställning](https://helpx.adobe.com/experience-manager/kb/disable-xmp-writeback.html)om det inte behövs.

Om du importerar en stor mängd metadata kan det leda till resurskrävande XMP-återskrivningsaktivitet om körningsarbetsflödesflaggan är markerad. Planera en sådan import under begränsad serveranvändning så att prestanda för andra användare inte påverkas.

## Replikering {#replication}

När du replikerar resurser till ett stort antal publiceringsinstanser, till exempel i en webbplatsimplementering, rekommenderar Adobe att du använder kedjereplikering. I det här fallet replikeras författarinstansen till en enda publiceringsinstans som i sin tur replikeras till de andra publiceringsinstanserna och frigör författarinstansen.

### Konfigurera kedjereplikering {#configure-chain-replication}

1. Välj vilken publiceringsinstans du vill använda för att länka replikeringarna till
1. På den publiceringsinstansen lägger du till replikeringsagenter som pekar på andra publiceringsinstanser
1. På var och en av dessa replikeringsagenter aktiverar du **[!UICONTROL Vid mottagande]** på fliken **[!UICONTROL Utlösare]** .

>[!NOTE]
>
>Adobe rekommenderar inte att resurser aktiveras automatiskt. Om det behövs rekommenderar Adobe att du gör detta som det sista steget i ett arbetsflöde, vanligtvis DAM Update Asset.

## Sökindex {#search-indexes}

Se till att du implementerar de senaste Service Pack-uppdateringarna och prestandarelaterade snabbkorrigeringar eftersom de ofta innehåller uppdateringar av systemindex. Se tips [för prestandajustering| 6.x](https://helpx.adobe.com/experience-manager/kb/performance-tuning-tips.html) för vissa indexoptimeringar som kan tillämpas, beroende på vilken version av AEM du har.

Skapa anpassade index för frågor som du kör ofta. Mer information finns i [metod för att analysera långsamma frågor](https://aemfaq.blogspot.com/2014/08/oak-query-log-file-analyzer-tool.html) och [skapa anpassade index](/help/sites-deploying/queries-and-indexing.md). Mer information om de effektivaste strategierna för frågor och index finns i [Bästa metoder för frågor och indexering](/help/sites-deploying/best-practices-for-queries-and-indexing.md).

### Lucene-indexkonfigurationer {#lucene-index-configurations}

Vissa optimeringar kan göras för Oak-indexkonfigurationer som kan förbättra prestanda för AEM Assets:

Uppdatera LuceneIndexProvider-konfigurationen:

1. Gå till /system/console/configMgrorg.apache.jackrabbit.oak.plugins.index.lucene.LuceneIndexProviderService
1. Aktivera indexfilerna **** CopyOnRead, CopyOnWrite och Prefetch i versioner före AEM 6.2. Dessa värden är aktiverade som standard i AEM 6.2 och senare versioner.

Uppdatera indexkonfigurationer för att förbättra omindexeringstiden:

1. Öppna CRXDe /crx/de/index.jsp och logga in som administrativ användare
1. Bläddra till /oak:index/lucene
1. Lägg till en String[] -egenskap med namnet **[!UICONTROL excludePaths]** med värdena &quot;/var&quot;, &quot;/etc/workflow/instances&quot; och &quot;/etc/replication&quot;
1. Bläddra till /oak:index/damAssetLucene
1. Lägg till en String[] -egenskap med namnet **[!UICONTROL includedPaths]** med värdet &quot;/content/dam&quot;
1. Spara

(Endast AEM6.1 och 6.2) Uppdatera indexet ntBaseLucene för att förbättra prestanda vid borttagning och flyttning av resurser:

1. Bläddra till */läs:index/ntBaseLucene/indexRules/nt:base/properties*
1. Lägg till två nt:ostrukturerade noder **[!UICONTROL slingResource]** och **[!UICONTROL damResolvedPath]** under */oak:index/ntBaseLucene/indexRules/nt:base/properties*
1. Ange egenskaperna nedan på noderna (där ordnade egenskaper och propertyIndex-egenskaper är av typen *Boolean*:

   slingResource

   name=&quot;sling:resource&quot;

   ordered=false

   propertyIndex= true

   type=&quot;String&quot;

   damResolvedPath

   name=&quot;dam:resolvedPath&quot;

   ordered=false

   propertyIndex=true

   type=&quot;String&quot;

1. På noden /oak:index/ntBaseLucene anger du egenskapen `reindex=true`
1. Klicka på **[!UICONTROL Spara alla]**
1. Övervaka error.log för att se när indexeringen är klar:

   Omindexering har slutförts för index: [/ek:index/ntBaseLucene]

1. Du kan också se att indexeringen har slutförts genom att uppdatera noden /oak:index/ntBaseLucene i CRXDe eftersom egenskapen reindex skulle återgå till false
1. När indexeringen är klar går du tillbaka till CRXDe och anger att **[!UICONTROL type]** -egenskapen ska vara inaktiverad för dessa två index

   * */oak:index/slingResource*
   * */oak:index/damResolvedPath*

1. Klicka på **[!UICONTROL Spara alla]**

Inaktivera Lucene-textextrahering:

Om användarna inte behöver kunna söka i innehållet i resurser, till exempel genom att söka i texten i PDF-dokument, kan du förbättra indexprestanda genom att inaktivera den här funktionen.

1. Gå till AEM-pakethanteraren /crx/packmgr/index.jsp
1. Överför och installera paketet nedan

[Hämta fil](assets/disable_indexingbinarytextextraction-10.zip)

### Gissa totalt {#guess-total}

När du skapar frågor som genererar stora resultatuppsättningar bör du använda parametern för att undvika att använda mycket minne när du kör dem. `guessTotal`

## Known issues {#known-issues}

### Stora filer {#large-files}

Det finns två viktiga kända fel som rör stora filer i AEM. När filer når större storlekar än 2 GB kan synkronisering med vänteläge i kallt läge hamna i en situation där minnet är slut. I vissa fall förhindras att standby-synkronisering körs. I andra fall kraschar den primära instansen. Detta scenario gäller alla filer i AEM som är större än 2 GB, inklusive innehållspaket.

På samma sätt kan det ta lite tid innan filen är helt beständig från cachen till filsystemet om filstorleken når 2 GB när ett delat S3-datalager används. Detta innebär att om du använder en binär replikering utan binärfiler kan det hända att binära data inte har befunnits beständiga innan replikeringen slutförs. Denna situation kan leda till problem, särskilt om det är viktigt att data är tillgängliga, till exempel i avlastningsscenarier.

## Prestandatestning {#performance-testing}

För varje AEM-driftsättning måste ni skapa ett system för prestandatestning som snabbt kan identifiera och lösa flaskhalsar. Här är några nyckelområden att fokusera på.

### Nätverkstestning {#network-testing}

Utför följande uppgifter för alla problem med nätverkets prestanda från kunden:

* Testa nätverksprestanda inifrån kundens nätverk
* Testa nätverksprestanda inifrån Adobe. För AMS-kunder kan du arbeta med din CSE för att testa inifrån Adobe-nätverket.
* Testa nätverksprestanda från en annan åtkomstpunkt
* Genom att använda ett prestandatest för nätverk
* Testa mot dispatchern

### AEM-instanstestning {#aem-instance-testing}

För att minimera latens och uppnå hög genomströmning genom effektiv processoranvändning och lastdelning ska du regelbundet övervaka AEM-instansens prestanda. Särskilt gäller följande:

* Kör inläsningstester mot AEM-instansen
* Övervaka uppladdningsprestanda och gränssnittsvarstider

## Prestandakontrolllista för AEM Resurser {#aem-assets-performance-checklist}

* Gör det möjligt för HTTPS att kringgå alla HTTP-trafiksniffare på företag.
* Använd en kabelanslutning för överföring av stora resurser.
* Ange optimala JVM-parametrar.
* Konfigurera ett datalager i filsystemet eller ett S3 DataStore.
* Inaktivera generering av underresurser. Om det är aktiverat skapar AEM:s arbetsflöde en separat resurs för varje sida i en flersidig resurs. Var och en av dessa sidor är en enskild resurs som förbrukar mer diskutrymme, kräver versionshantering och ytterligare arbetsflödesbearbetning. Om du inte behöver separata sidor inaktiverar du generering av delresurser och sidextrahering.
* Möjliggör tillfälliga arbetsflöden.
* Justera Granite-arbetsflödesköerna för att begränsa antalet samtidiga jobb.
* Konfigurera ImageMagick för att begränsa resursförbrukningen.
* Ta bort onödiga steg från arbetsflödet för DAM Update Asset.
* Konfigurera arbetsflöde och versionsrensning.
* Optimera Lucene-indexkonfigurationen.
* Optimera index med de senaste servicepaketen och snabbkorrigeringarna. Kontakta Adobe Support för eventuella ytterligare indexoptimeringar.
* Används `guessTotal` för att optimera frågeprestanda.
* Om du konfigurerar AEM för att identifiera filtyper från filernas innehåll (genom att konfigurera [!UICONTROL Day CQ DAM Mime Type Service] i [!UICONTROL AEM Web Console]) överför du många filer samtidigt under icke-toppade tider eftersom åtgärden är resurskrävande.
