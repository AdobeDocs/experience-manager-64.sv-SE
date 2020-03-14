---
title: Versionsinformation om AEM 6.4 Service Pack
seo-title: Versionsinformation om AEM 6.4 Service Pack
description: Versionsinformation om Adobe Experience Manager 6.4 Service Packs.
seo-description: Versionsinformation om Adobe Experience Manager 6.4 Service Packs.
uuid: 49a710a8-7cd5-47de-9a96-7af7f3c00dfc
contentOwner: dekalra
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
discoiquuid: 93067308-e275-490f-8d78-ae79e046059c
translation-type: tm+mt
source-git-commit: 6684e78caf43b49660de3c1a90e2cccd9a204420

---


# Versionsinformation om AEM 6.4 Service Pack {#aem-service-pack-release-notes}

## Versionsinformation {#release-information}

| Produkter | **Adobe Experience Manager (AEM) 6.4** |
|---|---|
| Version | 6.4.8.0 |
| Typ | Service Pack-version |
| Date | 5 mars 2020 |
| Hämta URL | AEM 6.4.8.0 i [PackageShare](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/servicepack/AEM-6.4.8.0), [Software Distribution(Beta)](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/servicepack/aem-service-pkg-6.4.8.zip) |

## Vad ingår i AEM 6.4.8.0 {#what-s-included-in-aem}

AEM 6.4.8.0 är en viktig uppdatering som innehåller nya funktioner, viktiga förbättringar som kunderna efterfrågat och prestanda, stabilitet, säkerhetsförbättringar som släppts sedan den allmänna tillgängligheten av AEM 6.4 i **april 2018.**

Det är också kumulativt, vilket innebär att 6.4.8.0 innehåller alla AEM 6.4-servicepaket som släppts före det.

Några viktiga höjdpunkter i den här Service Pack-versionen är:

* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.20.

* Funktionen för radbrytning stöds för japanska webbplatser i WCM-RTE.

* Ordbrytning och radbrytningar stöds för japanska webbplatser.

* Stöd har lagts till för att använda BUNSETSU-metoden för att bryta japanska språkmeningar och rader vid lämpliga positioner.

* CCR-gränssnittet för korrespondenshantering har nu stöd för decimalvärden för tyska.

* Integrering av formulärdatamodeller med SOAP-webbtjänsten har nu stöd för urvalsgrupper eller attribut för element.

* AEM Assets har nu konfigurerats med en varumärkesportal via Adobe I/O.

## Ändringslista {#list-of-changes}

### Sites {#sites}

* När en URL för en AEM Sites-sida innehåller ett kolon eller en procentsymbol slutar den underliggande webbläsaren att svara och CPU-cyklerna uppvisar en spik (NPR-32368, NPR-31917).
* När en AEM Sites-sida öppnas för redigering och en komponent kopieras, är inklistringsåtgärden inte tillgänglig för vissa platshållare (NPR-32328).
* Begäran om aktiveringsarbetsflöde innehåller inte refererade resurser (NPR-32304).
* Om antalet poster är fler än 80 visas bara de första 80 posterna när du skapar en utkast. I utkast visas tomma rader för resten av posterna (NPR-32058).
* Användare kan spara ett innehållsfragment utan att lämna någon information i de obligatoriska fälten (NPR-31988).
* Automatisk navigering fungerar inte för sökvägar som konfigurerats i en Core Experience Fragment-komponent (NPR-31921).
* När du ändrar typen av tabellcell i RTF-redigeraren (Rich Text Editor) inträffar följande fel:
   `Error: No common ancestor found, cannot continue` (NPR-31916).
* När innehåll flyttas inom samma mapp är alternativet för sidflyttning inaktiverat (NPR-31841).
* Lagt till stöd för att dela upp japanska språkmeningar med BUNSETSU-metoden och radbrytningar vid rätt position (NPR-31836).
* När du redigerar en hyperlänk i RTF-redigeraren sparas inte den markerade banan (NPR-31659).
* När du tar bort en flerfältskomponent och ångrar borttagningen återställs komponenten men data återställs inte (NPR-31617).

### Assets {#assets}

* En mapp utan namn skapas i SPS (Scene7 Publishing System) när en resurs flyttas från en mapp till en annan i Experience Manager med Dynamic Media Scene7-konfiguration (NPR-32440).

* Assets detail page of PDF files does not show action buttons in Experience Manager running on Dynamic Media Scene7 mode (NPR-32316).

* Resurs- och videoåtergivningar kan inte tas bort (NPR-32213).

* Kalenderikonen för den schemalagda aktiveringen visas inte i statuskolumnen (i Klassiskt användargränssnitt för DAM-tillgångslista) för resurser vars aktivering är schemalagd för ett senare datum och en senare tid (NPR-32198).

* Relationen mellan tillgångar skrivs över när tillgångar är kopplade till mer än en tillgång med hjälp av Annan (NPR-32196).

* Knappen Spara importerar inte fjärruppsättningen när användaren inte har gjort några ändringar i Set Editor i Dynamic Media Client (NPR-32178).

* Inläggning av PSD-resurser orsakar CPU-spik och Experience Manager Author-instans som inte svarar (NPR-32165).

* Ett minnesfel uppstod när en stor ZIP-fil överfördes i Experience Manager DAM (NPR-32155).

* Versionshistorik-URL:er visas under fältet Refererat av på egenskapssidan för resurser (NPR-31889).

* Avpublicering från varumärkesportalen på sidan Hantera publikation misslyckas för undermappar till en publicerad mapp (NPR-31835).

* Dynamic Media-videokodningar kan inte överföras när Scene7 Cloud Configuration placeras i en privat mapp `/conf` i stället för `/conf/global` (NPR-31779).

* Bild visas inte på tidslinjen när anteckningar har lagts till i Experience Manager som körs i körläge för Dynamic Media Scene7 (NPR-31754).

* ZIP-filen som hämtas från DAM kan inte öppnas med WinZip (NPR-31745).

### Integreringar {#integrations-6480}

* De nedrullningsbara menyerna **Company** och **Reporting** Suite döljs när du väljer **Rapporteringskälla** när du konfigurerar Adobe Analytics i Experience Managers molntjänster (NPR-31729).

* Adobe Campaign-egenskaper rensas inte bort när en språkkopia av ett nyhetsbrev som är länkat till en Adobe Campaign skapas, medan rensning sker när ett nyhetsbrev som är länkat till en Adobe Campaign kopieras eller klistras in (NPR-32540).

### Sling {#sling-6480}

* Icke-deterministisk skuggning av resursuppföljning fungerar inte (CQ-4286466).

### Projekt {#projects-6480}

* Knappen Skapa är inte synlig för användaren även om användaren har behörighet att skapa projekt i undermappen (NPR-31831).

* Funktionen för att växla mellan kortvyn, listvyn och kalendervyn fungerar inte när du har valt kalendervyn i projekt (NPR-31829).

### Översättning {#translation-6480}

* När ett översättningsprojekt skapas för flera språk genereras projektet endast för vissa språk i stället för för alla, och ett fel (resurslösaren är redan stängd) visas i loggen (NPR-32212).

### WCM-MSM {#wcm-msm-6480}

* Behörighetsproblem leder till att fel visas när sidor flyttas i en plan (NPR-32610).

### WCM-sidredigerare {#wcm-page-editor-6480}

* Webbläsaren slutar svara när en komponent läggs till på en sida med ett specifikt URL-format (NPR-32368, NPR-31917).

### WCM-Admin-gränssnitt {#wcm-admin-ui-6480}

* Det ingår inte några refererade resurser i begäran om aktiveringsarbetsflöde (NPR-32304).

### Communities {#communities}

* Det går inte att uppdatera gruppminiatyrbilden för grupper (NPR-32603).

### Varumärkesportal {#brand-portal}

* Avpublicera metadatamatchemat i AEM Resurser fyller i ett felmeddelande även om schemat tas bort vid backend (CQ-4286871).

### Foundation UI {#foundations-ui-6480}

* Ogiltiga tecken visas i den URL som har lagts till i en Button-komponent (NPR-32684).

### Formulär {#forms}

>[!NOTE]
>
>AEM Service Pack innehåller inte korrigeringar för AEM Forms. De levereras med ett separat Forms-tilläggspaket. Dessutom släpps ett kumulativt installationsprogram med korrigeringar för AEM Forms på JEE. Mer information finns i [Installera AEM Forms-tilläggspaket](#install-aem-forms-add-on-package) och [Installera AEM Forms JEE-installationsprogrammet](#install-aem-forms-jee-installer).

* Designer: Om taggningsalternativet är aktiverat försvinner delformulärsramen i den genererade PDF-utdatafilen (NPR-32546, NPR-32322).

* Designer: Om det finns sammanfogade celler i en tabell misslyckas hjälpmedelstestet för PDF-utdatafilen som konverterats från ett XDP-formulär med hjälp av utdatatjänsten (NPR-32079).

* Dokumentsäkerhet: En skyddad PDF-fil kan inte öppnas offline med alternativet DisableGlobalOfflineSynchronizationData inställt på True (NPR-32080).

* Dokumentsäkerhet: Problem vid öppning av en skyddad PDF-fil efter uppgradering från ES4 till AEM 6.3 (NPR-32170).

* Dokumenttjänster: Ett felmeddelande visas när du försöker konvertera en PDF-fil till ett PDF/A-dokument med konverteringsmetoden toPDFA (NPR-32663).

* Dokumenttjänster: Ett undantag visas när tjänsten Reader Extensions används i en PDF-fil (NPR-32639).

* Dokumenttjänster: Ett felmeddelande visas när XDP-filer samlas in och konverteras till PDF-filer (NPR-31821).

* Analyserna ger inga lämpliga resultat när det gäller att skicka in eller överge formulär på en webbplatssida (NPR-31359).

### Programfixar och funktionspaket som ingår i tidigare servicepaket {#hotfixes-and-feature-packs-included-in-previous-service-packs}

#### AEM 6.4.7.0 {#experience-manager-6470}

AEM 6.4.7.0 är en viktig uppdatering som omfattar prestanda, stabilitet, säkerhet och viktiga kundkorrigeringar och förbättringar som släppts sedan den allmänna tillgängligheten av AEM 6.4 i **april 2018.**

Det är också kumulativt, vilket innebär att 6.4.7.0 innehåller alla tidigare AEM 6.4-servicepaket.

Några av de viktigaste nyheterna i AEM 6.4.7.0 är:

* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.17.
* Stöd har lagts till för att ange en version av en Sites-sida när den togs bort.
* Ny kolumn för skapat datum, som är sorterbar, har lagts till i **DAM-listvyn** och i resurssökningsresultat i **listvyn** (NPR-31311).
* Resurssortering baserat på **namnkolumnen** är tillåtet i **listvyn** .
* Tidsgränsen för batchstorlek och arbetsflödessteg för återbearbetning och batchöverföring kan nu konfigureras från gränssnittet i Dynamic Media.
* Minnet `pdfBrochure` har angetts till false i molnkonfigurationen Scene 7 för att spara minne i IPS.

##### Assets {#assets-6470}

**Produktförbättringar**

* Den exportversion av API-paket `package com.day.cq.dam.handler.standard.msoffice` som stöds av `dam-handler` bundle uppgraderas till 6.0.0 (CQ-4279059).
Om du använder paketet `com.day.cq.dam.handler.standard.msoffice` i din anpassade implementering bör du kompilera ditt `dam-handler` paket med den senaste uber burken.

**Korrigeringar**

* Metadata för vissa PDF-dokument uppdateras inte och sparas i PDF-filen när titeln ändras (NPR-31575).

* Resurser med plustecken i filnamnet kan inte tas bort (NPR-30588).

* DAM-mappegenskaper visar inte tillagda användare eller grupper (skapade med LDAP-synkronisering) i stängda användargrupper (NPR-30555).

* Specialtecken i ämnesraden i e-postmallar visas inte korrekt (NPR-30547).

* Resursnamn ändras till gemener när resurser flyttas från en mapp till en annan i AEM som körs i körläget Dynamic Media Scene 7 (NPR-31631).

* Namn på bilduppsättningen ändras till gemener i Scen 7 när bilduppsättning (eller mediaset) skapas och namnges med lämplig namnkonvention i DAM (NPR-31576).

* Arbetsflödet för Dynamic Media Encode Video misslyckas med att generera miniatyrbilder för videon som migreras från Scene 7 till Dynamic Media - körningsläget Scene 7 (NPR-31523).

* Ett internt serverfel uppstod när ett filter användes för att söka efter uppsättningar, i AEM som körs på dynamiska media - Scene 7-körningsläge (NPR-31388).

* Ett fel uppstod när en fjärrbilduppsättning redigerades för bilden som finns i mappen som heter same som namnet på Scene 7-företaget (NPR-31347).

* Resurser som innehåller referenser publiceras inte (DM) (NPR-31179).

* Det värde för förfallotid (klientcache-tid till live) som konfigurerats för Dynamic Media Hybrid-läge replikeras inte till Dynamic Media Delivery Environment (NPR-31126).

* Överföringar från AEM Dynamic Media - Scene 7-miljön till Scene 7 tar för lång tid att slutföra (NPR-30926).

* När du har skapat en sida med komponenten Dynamic Media när du publicerar samma, från en författarinstans som körs på Dynamic Media - Scene 7, uppmanas användaren att publicera konfigurationen mscene7 (NPR-30880).

* Värdet för parametern &quot;asset&quot; i visningsprogrammets inbäddningskod ändras inte när du ändrar värdena i fälten &quot;Title after move&quot; och &quot;Name after move&quot; i Dynamic Media - Scene 7 (NPR-30745).

* Touch UI-sökning (utförd via Omnissearch)-resultatsidan rullar automatiskt upp och förlorar användarens rullningsposition (NPR-31306).

* DAM-händelserensning tar bort den senaste (maxSavedActivities) händelseinformationen och lagrar data som skapats tidigare (NPR-30870).

* Resurstiteln och namnändringen bevaras inte efter flyttningsåtgärden till en målmapp som utlöser oändlig rullning när den väljs (NPR-30647).

* Samlingar tas bort från vyn när du tillämpar något filter i AEM Resurser som du kommer åt från Adobe Asset Link (CQ-4280534).

* Tidsgränsen för batchstorlek och arbetsflödessteg för återbearbetning och batchöverföring går inte att konfigurera från användargränssnittet, och måste anges i CRXDE och arbetsflödet måste synkroniseras två gånger (CQ-4281254).

* Namnet på arbetsflödessteget för batchöverföring och enkelt överföringssteg är detsamma i Scene 7, vilket leder till förvirring (CQ-4281176).

* Arbetsflödet för ombearbetning i Scene 7 fastnar om en resurs saknar metadatanod (CQ-4281170).

* BatchUpload-steget i arbetsflödet för ombearbetning fungerar inte för mappen med videomaterialet (CQ-4280630).

* PDF-alternativ som skickas till DM har extractKeywords inställt på true som standard (CQ-4280101).

* Ett null-punktsundantag har observerats vid körning av arbetsflödet för ombearbetning av Scene 7 i en mapp som innehåller icke-DM-resurser (CQ-4279555).

* Namnändring av resurser i AEM kan inte synkroniseras med scen 7 när det redan finns en resurs med ett dubblettnamn i scen 7 (CQ-4276763).

* Zip-filen som skickas med e-post för hämtning av resurser kan inte packas upp när en användare med läsbehörighet försöker öppna den (CQ-4277925).

* Arbetsflödet för PPT-återgivning kan inte generera återgivningar av de överförda PPT-filerna eftersom AEM 6.4 inte kan uppdatera till com.adobe.granite.poi version 2.0.28 (CQ-4279059).

* PDF-filer är inte indexerade och innehållet i dem är inte sökbart (CQ-4278916).

##### Sites {#sites-6470}

* När starter befordras med endast Befordra ändrade sidor och Befordra starter med ändrade sidor görs, visas endast de ändrade sidorna som befordrade. När listan som ska befordras är korrekt visas de icke-ändrade sidorna fortfarande längst ned i listan (NPR-31314).

* När en AEM Sites-sida flyttas till en annan plats, uppdateras inte egenskaperna för den nya platsen (NPR-31265).

* Om antalet poster är fler än 40 visas bara de första 40 posterna för en ny utkast. I utkast visas tomma rader för resten av posterna (NPR-31182).

* När antalet LiveCopy är stort tar det lång tid att återge förhandsgranskningen i LiveCopy (NPR-30945).

* Stöd för att ange en version av en sida har lagts till när den togs bort. Om versionshantering är inaktiverat för den borttagna sidan kan AEM Sites inte återställa sådana sidor (NPR-30891).

* När en användare lägger till japanska eller koreanska tecken i egenskapen description på en meny visas förvrängda tecken för japansk och koreansk text på menyn (NPR-31331).

* När en användare fokuserar på fält med vänster stödlinje och använder ett kortkommando för att klistra in innehåll, klistras innehållet i sidredigerarens urklipp in i stället för innehållet som kopieras från de vänstra fältspåren (NPR-31169).

* När en användare redigerar ett innehållsfragment återställs den redan borttagna varianten av innehållsfragmentet (NPR-31178).

* Frågan för modell för innehållsfragment är ineffektiv. Det är mycket långsamt om instansen har många sidor och resulterar i ett fel (NPR-30666).

* När du sparar innehållsfragmentmodellen ställs tiden i fältet för datum och tid in på 00:00 (NPR-30540).

##### Integreringar {#integrations-6470}

* När du konfigurerar Adobe Launch visas ett snedstreck (/) i biblioteks-URL:en (NPR-30700).

* Prestandan för ContextHub försämras efter publicering (NPR-30884).

##### Sling {#sling-6470}

* Uppdatera webbkonsolens säkerhetsprovider bundle-version till 1.2.4 för att ta bort beroendet av start-api från webbkonsolesecurityprovider (NPR-30885).

##### Platform {#platform-6470}

* Uppdateringar i buffertstorlekskonfigurationen för Jetty-baserad HTTP-tjänst sparas inte (NPR-30925).

* QueryBuilder har nu stöd för orderby fn:name() i XPath-frågor (NPR-31322).

* Uppdaterat Sling-distribuerad händelseadministratör till version 1.1.4 som förbättrar kvaliteten på loggar i en klustrad miljö (NPR-29256).

##### Foundation UI {#foundation-6470}

* Om du bläddrar till slutet av resultatsidan med ett stort antal sökresultat kraschar webbläsaren (NPR-31332).

* När du växlar från kortvyn till listvyn på en sökresultatsida uppstår en fördröjning innan sidan kan rullas (NPR-31280).

##### Oak {#oak-6470}

* MS Office-filer med filtilläggen .docx och .xlsx som innehåller JPEG-bilder kan inte tolkas med Tika-parser (NPR-31693).

##### Livefyre {#livefyre-6470}

* Livefyre-integrering med AEM 6.4-uppgradering ger Null Point-undantag när integreringen görs med DITA-plugin för syntetiska resurser. Integreringen fungerar emellertid när komponenter läggs till manuellt (FYR-11066).

##### Översättning {#translation-6470}

* Sökvägen till målupplevelseavsnittet uppdateras inte när du befordrar en startsida (NPR-30830).

##### Communities {#communities-6470}

* E-postfunktionen fungerar inte korrekt i vissa fall, även när e-postmeddelanden är aktiverat i meddelandeinställningarna, genereras ett undantag i NotificationsActivityStreamProvider (NPR-31521).
* Det går inte att skapa nya medlemmar. En tom skärm visas på skärmen Skapa medlem i AEM-författarinstansen (NPR-30951).
* Användaren kan inte publicera en kommentar på en blogg i Internet Explorer 11 (NPR-30927).
* Administratören för en begränsad grupp kan inte visa gruppkortet, kan inte utföra några Quick Link-åtgärder (Redigera/Publicera/Ta bort grupper) i AEM-författarinstansen (NPR-30810).
* Medlemsgrupper/gruppinformation visas inte när en ny plats skapas i AEM-författarinstansen (NPR-28840).

##### Formulär {#forms-6470}

>[!NOTE]
>
>AEM Service Pack innehåller inte korrigeringar för AEM Forms. De levereras med ett separat Forms-tilläggspaket. Dessutom släpps ett kumulativt installationsprogram med korrigeringar för AEM Forms på JEE. Mer information finns i [Installera AEM Forms-tilläggspaket](#install-aem-forms-add-on-package) och [Installera AEM Forms JEE-installationsprogrammet](#install-aem-forms-jee-installer).

**Formulärtilläggspaket**

**Adaptiva former**

* Strängar innehåller ordlistenyckeln när adaptiva former lokaliseras (NPR-31109).

* Kryssrutorna och listrutorna i Forms klarar inte tillgänglighetskontrollerna (NPR-31282).

**HTML5-formulär**

* När du genererar HTML5-förhandsgranskning av ett XDP-formulär visas ett flimmer när instanser av ett delformulär läggs till (NPR-30907).

**Document Services for OSGi**

* Om du kör flera samtidiga tråd för att samla ihop formulären med metoden com.adobe.fd.assembler.service.AssemblerService.invoke() visas ett felmeddelande (NPR-31164).

* De temporära filer som skapas av Assembler Service tas inte bort automatiskt och kräver AEM-omstart (NPR-30846).

* Om du tillämpar ReaderExtension Rights på PDF-filer visas ett felmeddelande (NPR-30930).

**Arbetsflöde**

* OSGi-arbetsflödet misslyckas på grund av 100 % processoranvändning (NPR-31234).

**Formulär-JEE-installationsprogram**

**Dokumenttjänster**

* Tjänsten Convert PDF kan inte konvertera PDF-dokument till PostScript och visar ett felmeddelande (NPR-31267).

* SOAP-slutpunktskonfigurationen återställs efter att en korrigering har tillämpats för att korrigera HTML-fel i PDF-filer (NPR-31309).

**PDFG-tjänst**

* Det gick inte att överföra den Adobe PDF-inställningsfil som hämtats med administratörsgränssnittet (NPR-31273).

#### AEM 6.4.6.0 {#experience-manager-6460}

AEM 6.4.6.0 är en viktig uppdatering som omfattar prestanda, stabilitet, säkerhet samt viktiga kundkorrigeringar och förbättringar som släppts sedan den allmänna tillgängligheten av AEM 6.4 i **april 2018.**

Det är också kumulativt, vilket innebär att 6.4.6.0 innehåller alla tidigare AEM 6.4-servicepaket.

Några av de viktigaste nyheterna i AEM 6.4.6.0 är:

* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.15.
* Stöd har lagts till för att spåra dynamiska användargränssnittslägen vid spårningshändelser i grund-API:t.
* Ytterligare renderingsstöd för bildens kärnkomponent.

**Assets**

* Resursresurslänken i en mapp med blanksteg och tecken i namnet visar tomma grå kort för vissa resurser. `&` NPR-29934: Programfix för CQ-4270187
* DAM-arbetsflödet kraschar när MP4-resurser skapas för AEM. NPR-30031: Programfix för CQ-4271352
* Adobe Smart Tag-anslutningsproblem via DataPower. NPR-30026: Programfix för CQ-4269457
* Det går inte att hitta PDF-filen med OmniSearch. NPR-30046: Programfix för GRANITE-26290
* Resurssökvägar i URL:er och mappmetadata som genereras av AVS-API:t är inte URL-kodade.  GRANITE-26198: Programfix för CQ-4271814
* Funktionen för att skapa en granskningsuppgift fungerar inte på grund av odefinierad nyttolast. NPR-30469: Programfix CQ-4274263
* Möjligheten att växla från kortvyn till listvyn och vice versa försvinner när du har gjort en OmniSearch på resursväljaren. NPR-29852: Programfix för CQ-4269369
* (Touch UI) Under guiden för att hantera publicering läggs resurser till i replikeringskön när sidorna har lagts till, vilket gör att en del av resurserna visas efter några sekunder. NPR-29985: Programfix för CQ-4270724
* Om du sorterar sökfrågan efter relevans returneras InDesign-dokument tillsammans med InDesign-mallar. Programfix för CQ-4273864
* Om användaren har ett e-post-ID med versaler kan användarna inte checka in de resurser som tidigare har checkats ut. Programfix för CQ-4276575
* Om du konfigurerar Dynamic Media Cloud-tjänster i `DMHybrid` läge skapas flera tomma rapportsviter som skapats i Analytics utan något rapportsvits-ID som lagrats på AEM, vilket resulterar i duplicering av rapportsviten. Programfix för CQ-4276855
* Varningsdialogrutan visas inte när du befordrar på sidan Hanterad tagg. Programfix för CQ-4252851
* Navigeringsknappen fungerar inte när du använder karusellen för att hantera taggar. Programfix för CQ-4275499
* Funktionen för att flytta resurser gruppvis bryts vilket resulterar i att resurser inte flyttas. Programfix för CQ-4272987

**Sites**

* `pageinfo.json` förfrågningar är extremt långsamma och tar för lång tid att ladda. NPR-29709: Programfix för CQ-4269560
* `onTime` eller `offTime` metadataegenskaper som sparats på resurser återkallas inte om AEM-servern startas om. NPR-30413: Programfix för CQ-4272784
* På grund av ett felaktigt beteende för klassen ConfigPostProcessor tas cq bort när den överordnade sidan avbryts: LiveRelationship-blandningstyp från den underordnade sidan. NPR-30536, NPR-30510: Programfix för CQ-4254113
* XSS (Cross-site scripting) på sidan för redigering i Start-arbetsflödet på sidan för Campaign. NPR-29747: Programfix för CQ-4271067
* (Klassiskt användargränssnitt) Workflow lock-scenen inaktiverar arbetsflödesfliken tills låset släpps. NPR-30356: Programfix för CQ-4237557
* (IE11) När du klistrar in HTML-innehåll i en RTF-redigeringskomponent med defaultPasteMode = plaintext klistras HTML in med formateringen, vilket innebär att defaultPasteMode inte har någon effekt. NPR-30045: Programfix för GRANITE-26094
* (Klassiskt användargränssnitt) När sidan Webbplatsadministratör läses in på nytt inaktiveras alla nedrullningsbara alternativ på menyn Nytt. NPR-29980: Programfix för CQ-4272044
* Det går inte att lägga till format i texten eller redigera befintliga format som har skapats i innehållet. NPR-29712: Programfix för CQ-4266249
* (Klassiskt användargränssnitt) Resurser utan dc: rubrikvärdet visas utan titel i sökvägsdialogrutans webbläsare. NPR-30166: Begäran om backport för CQ-88858
* Cq: avlyssnaren fungerar inte med kapslade komponenter även efter att parsys-komponenten har lagts till. NPR-30422: Programfix för CQ-4274863
* ContextHub-fel under AEM- och Campaign-integrering. NPR-30625: Programfix för CQ-4250790
* Värdet för parametern resourceType request kopieras till värdet för ett HTML-taggattribut som är inkapslat med citattecken. NPR-29832: Programfix för CQ-4255365
* En uppdatering av sidan behövs när komponenterna har kopierats och klistrats in från en sida till en annan. NPR-29982: Programfix för CQ-4256019
* Publicera/avpublicera från ett sidalias stöds inte och bör tas bort. NPR-30062: Programfix för CQ-4271249
* Varningen ResourceResolver som inte stängts i ExperienceFragmentsReplicationListener orsakar stabilitetsproblem över tid och tvingar fram en omstart av AEM-instanser. NPR-30416: Programfix för CQ-4257521
* Om du flyttar Experience Fragments som refereras på mer än 150 sidor ändras inte fragmentPath på de sidor där de refereras. NPR-30556: Programfix för CQ-4274900
* Tolkningsfel vid öppning av ett innehållsfragment som innehåller tecknen USD ($) och inledande klammerparentes ({) efter varandra. Programfix för CQ-4270266
* VersionPreviewServlet fungerar inte i NullPointerException vid försök att visa en version av ett Experience Fragment i tidslinjen. NPR-30074: Programfix för CQ-4271881
* Det går inte att låsa innehållsfragment via incheckningsfunktionen. NPR-29923: Programfix för CQ-4258785

**Replikering**

* JCR-session/Resurslösare läcker under OAuth-implementering vid varje replikering till MAC/Brand Portal. NPR-30000: Programfix för Granite-26196

**Sling**

* Ordningen på underordnade som påverkas med överlappning och föregående ordning orsakar IndexOutOfBoundException. NPR-30408: Programfix för Sling-8296 och Sling-7375
* InactiveBundlesHealthCheck läser konfigurationen MissingPackagesHealthCheck när InactiveBundlesHealthCheck-konfigurationerna har sparats. NPR-30084: Programfix för CQ-4272644

**Handel**

* Det går inte att köra katalogutkast från webbplatskonsolen. NPR-29829: Programfix för CQ-4271461
* Den resurs som används i produkten visar inte någon referens till produkten i avsnittet &quot;Referenser&quot; i resursen och varken resurssökvägen uppdateras om resursen flyttas. NPR-30542: Programfix för CQ-4270247

**Plattform**

* AEM Default Mail Sender kan inte skicka e-post till en SMTP-fjärrserver via TLS v1.2. NPR-30476: Programfix för GRANITE-26605

**Communities**

* Grupper som tagits bort från författaren är inte synkroniserade med alla utgivare. NPR-29987: Programfix för CQ-4268738
* Borttagna användare som tagits bort från fältet Community Administrators är inte synkroniserade med medlemsgruppen. NPR-30389: Programfix för CQ-4274339
* Användare som ingår i administratörsgruppen har inga snabblänkar för gruppen. NPR-30546: Programfix för CQ-4275579
* Om du uppdaterar en ny och befintlig community-grupp skrivs egenskapen över på jcr: innehållsnod och ändrar namnet till den första sidans rubrik. NPR-30109: Programfix för CQ-4273719
* Snabbsökning och sökning via plats och adress fungerar inte när communityn är inställd på att fungera med Data Storage Resource Provider (DSRP). NPR-26737: Programfix för CQ-4258493

**Översättning**

* Automatisk körning av översättning fungerar inte. NPR-30499: Programfix för CQ-4276288
* Användaren kan skapa en språkkopia på innehållssökvägen som är begränsad till skrivskyddad. NPR-29937: Programfix för CQ-4270708
* Översättningsproblem - Endast ett fåtal komponenter översätts med maskinöversättning. NPR-30079: Programfix för CQ-4273764

**Integrering**

* Det anpassade innehållet visas inte korrekt på publiceringsinstansen förrän instansen startas om. NPR-30421: Programfix för CQ-4273706

**Projekt**

* dam: folderThumbnailPaths-värden uppdateras inte och gamla miniatyrbilder visas inte ens när resurserna i mappen har tagits bort. NPR-30424: Programfix för CQ-4273667

**UI-konsoler**

* XSS (Cross-site scripting) på sidegenskaperna Sites på fliken Miniatyrbilder. NPR-30048: Programfix för Granite-26200

**UI-Foundation**

* Stöd har lagts till för att spåra dynamiska användargränssnittslägen vid spårningshändelser i grund-API:t. NPR-30742, GRANITE-26322: Programfix för GRANITE-26036

**Formulär**

>[!NOTE]
>
>AEM Service Pack innehåller inte korrigeringar för AEM Forms. De levereras med ett separat Forms-tilläggspaket. Dessutom släpps ett kumulativt installationsprogram med korrigeringar för AEM Forms på JEE. Mer information finns i [Installera AEM Forms-tilläggspaket](#install-aem-forms-add-on-package) och [Installera AEM Forms JEE-installationsprogrammet](#install-aem-forms-jee-installer).

**Formulärtilläggspaket**

**Adaptiva former**

* Det tar längre tid att hämta en tom css-fil från utgivaren, vilket orsakar prestandaproblem. NPR-30558: Programfix för CQ-4274399
* Formulär som ändras efter publiceringen publiceras inte igen när webbplatsen publiceras. NPR-30411: Programfix för CQ-4236566

**Formulär - serverdelsintegrering**

* Ett fel uppstod när formulärdatamodellen skapades med WSDL (Web Service Definition Language). NPR-30388: Programfix för CQ-4272921

**Formulär - korrespondenshantering**

* Specialtecken som mindre än (&lt;), större än (>) och et-tecken (&amp;) kodas i agentgränssnittet. NPR-30410: Programfix för CQ-4273887
* När ett textfragment som innehåller värden för datamordlistan utlöses, svarar inte agentens användargränssnitt. NPR-30098, NPR-30083: Programfix för CQ-4272204
* CCR-gränssnittet (Create Correspondence UI) misslyckas ibland med felvariabeln (object Object). NPR-29983: Programfix för CQ-4273874
* Inläsning av bokstavsutkast misslyckas med ett undantag när beskrivningen av dokumentfragment innehåller specialtecken som mindre än (&lt;), större än (>) och et-tecken (&amp;) i egenskaper. NPR-29930: Programfix för CQ-4252762

**HTML5-formulär**

* När du använder NonVisual Desktop Access i bläddringsläge för att läsa ett HTML5-formulär, läser webbläsaren Chrome &quot;graphic&quot; före varje Scalable Vector Graphic (SVG) i formulärdesignen. NPR-30450: Programfix för CQ-4274732

**Formulär-JEE-installationsprogram**

**Formulär - Foundation JEE**

* Om du lägger till eller redigerar en webbtjänstanslutning genom att anropa webbtjänster från AEM-formulär, genereras ett fel i Workbench: ClassNotFoundException org.apache.axis.message.SOAPBodyElement. NPR-30116: Programfix för CQ-4273217

**Formulär - dokumenttjänster**

* PDF/A-etiketten saknar fel i Acrobats preflight. NPR-30594: Programfix för CQ-4276032
* Databindningar med ett enda tecken i PDF-filen gör att Reader Extensions misslyckas med felet&quot;java.lang.StringIndexOutOfBoundsException: Strängindexvärdet ligger utanför intervallet: 1 tum. NPR-30128: Programfix för CQ-4273878
* När ett inläsningstest utförs på tjänsten HTML till PDF misslyckas det med ett fel och filtypsinställningarna tas bort från AEM-formulärservern. NPR-30085: Programfix för CQ-4272631
* Om du förenklar en PDF-fil med Adobe Acrobat 9.1 (XFA version 3.0) bevaras inte PDF-formulärens status: Osynliga element i formuläret återställs till ett synligt läge. NPR-29978: Programfix för CQ-4270888

**Formulär - dokumentsäkerhet**

* Det går inte att använda en signatur med tidsstämpel. Fel: ALC-DSC-003-000: com.adobe.idp.dsc.DSCInvocationException: Anropsfel. NPR-30696, NPR-30537: Programfix för CQ-4273778
* Configuration Manager infogar inte japanska strängar för lokaliserade tabellkolumner. NPR-30496: Programfix för CQ-4274868

**PDFG-tjänst**

* Anslutningsfel vid konvertering av Word-dokument till PDF på Windows Server 2016. NPR-30597: Programfix för CQ-4275652
* Undantag nekades för behörighet vid försök att använda backend-tjänsten HTML till PDF via biblioteket &quot;phantomjs&quot;. NPR-30456: Programfix för CQ-4258077
* maxReuseCount för tjänsten HTML till PDF visas inte med JBoss Management Console. NPR-30303, NPR-30135: Programfix för CQ-4273763

#### AEM 6.4.5.0 {#experience-manager-6450}

AEM 6.4.5.0 är en viktig uppdatering som omfattar prestanda, stabilitet, säkerhet samt viktiga kundkorrigeringar och förbättringar som släppts sedan den allmänna tillgängligheten av AEM 6.4 i **april 2018.**

Det är också kumulativt, vilket innebär att 6.4.5.0 innehåller alla tidigare AEM 6.4-servicepaket.

Några av de viktigaste nyheterna i AEM 6.4.5.0 är:

* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.13.
* Tillagd sockettimeout och timeout för anslutning i replikeringsagenter för varumärkesportalen.
* Förbättrade sökfunktioner - Ökade sidnumreringsgränsen för sökresultatet till 100 sidor.
* Inaktiverad `AssetDownloadServlet` OSGi-komponent som standard på AEM-publiceringsinstanser. Mer information finns i [Hämta resurser från AEM](/help/assets/download-assets-from-aem.md).
* Aktiverat stöd för flera Platshanterare för resurser. Mer information finns i [Återanvända resurser med MSM för resurser](/help/assets/reuse-assets-using-msm.md).

**Assets**

* Resurser med en apostrof i filnamnet synkroniseras inte till dynamiska media. NPR-29538: Programfix för CQ-4270592
* DAM DMGGateway-gränssnittet för S3-multipart-stöd har uppdaterats. NPR-29740: Programfix för CQ-4226303
* Dialogrutan för hämtning av resurser visar en felaktig filstorlek när återgivningar hämtas för en video i Dynamic Media. NPR-29642: Programfix för CQ-4246202
* Resurser blir oanvändbara efter Dag CQ DAM Mime Type Service använder text för m3u8. NPR-29276: Programfix för CQ-4264052
* Justering av resursreferens kan inte spara sessionen om någon av de flyttade/namnändrade resurserna ingår i Samling-resurssamlingar. NPR-29143: Programfix för /CQ-4252605
* Det går inte att spåra eller hitta resurser genom att söka i metadatavärdena. NPR-29141: Programfix för CQ-4260215
* När du använder sökfiltret för att spara en smart samling behåller klickåtgärden på panelen inte fokus. NPR-29000:  Programfix för CQ-4240323
* Om du flyttar en mapp kan du skapa en mapp med både stora och små bokstäver. NPR-28945: Programfix för CQ-4265234
* Tomma resultat visas i Omnissearch om samlingsnamnet har utrymme. NPR-29001: Programfix för CQ-4236729
* Om du ändrar namn på en fil med specialtecken som inte stöds, som et-tecken (&amp;), skapas en ogiltig mapp. NPR-29196: Programfix för CQ-4265037
* DAM-extraheringsarkivet för ZIP-filens funktion är bruten. NPR-29187: Programfix för CQ-4254421
* Metadataimport bör tillåta import av metadata utan registrering av namnutrymmen. NPR-29425, NPR-28132: Programfix för CQ-4269445
* Det går inte att spara metadataändringar för resurser vars namn innehåller ett citattecken. NPR-29395: Programfix för CQ-4254305
* Det går inte att flytta en DAM-resurs om filnamnet innehåller blanksteg. NPR-29270: Programfix för CQ-4266403
* Det går inte att hämta ZIP-arkiv som har komprimerats med Deflate64-algoritmen. NPR-29225: Programfix för CQ-4253995
* Miniatyrbilder av resurser visas långsamt när du öppnar en mapp som innehåller resurser med många versioner. NPR-29833: Programfix för CQ-4271629
* Det går inte att ange samlingen som är markerad om Retur-tangenten trycks ned efter att samlingen har valts. NPR-29723: Programfix för CQ-4261607
* XSS-attacker (Cross-site scripting) genom det begränsade varningsfönstret. NPR-29671: Programfix för CQ-4270133
* Det går inte att lägga till relationer till resurser för användare utan borttagningsbehörigheter. NPR-29640: Programfix för CQ-4269196
* När användaren har lagt till en objekttitel på egenskapssidan öppnas egenskapssidan igen när användaren försöker stänga sidan. NPR-29628: Programfix för CQ-4264929
* Om du skapar ett stort antal relationer för en resurs uppstår ett fel. NPR-28779: Programfix för CQ-4250708
* Inmatningen av resurser är långsam i Scene7 Connect-körningsläge. NPR-28658: Programfix för CQ-4263007
* Ett ohanterat TypeError-fel: Det går inte att läsa egenskapen split för undefined som visas när sökresultaten ska visas. NPR-28803: Programfix för CQ-4248371
* Replikeringen från AEM till Brand Portal är låst under lång tid. NPR-28914: Programfix för CQ-4254932
* Att flytta resurser i DAM resulterar inte i en liknande rörelse på Scene7. NPR-28957: Programfix för CQ-4264974
* Metadatauppdateringar skickas inte till IPS om metadatafältet uppdateras i AEM. NPR-28961: Programfix för CQ-4255393
* VersioningTimelineEventProvider ska tillhandahålla rotversionen tillsammans med versionskommentaren. Programfix för GRANITE-26063
* Inmatning av data leder till exekvering av kod på serversidan. Programfix för CQ-4270246
* Aktiverat stöd för flera Platshanterare för resurser. Programfix för CQ-4271453, CQ-4268621, CQ-4257491
* AEM-gränssnittet bör visa ytterligare en post för den aktuella versionen av resursen i tidslinjehistoriken och visa den senaste incheckningskommentaren från Adobe Asset Link. Programfix för CQ-4262864
* Exempelvideon läses inte in när en MixedMediaSet skapas eller redigeras. Programfix för CQ-4244889
* Om du inaktiverar behörigheterna att ta bort innehåll på AEM-sidan förhindrar du användaren att publicera till varumärkesportalen. Programfix för CQ-4270426
* Frågebegränsningsrelaterade problem med tillgångsrapporter efter uppgradering till AEM 6.4.3. NPR-28588: Programfix för CQ-4262022, CQ-4260697
* Nedladdningsfunktionen utnyttjar AEM Assets via en resurshämtningsserver som gör det möjligt för anonyma användare att hämta alla resurser. NPR-27315, programfix för CQ-4254732

**Sites**

* JCR-adresstaggens namn ska fyllas i automatiskt baserat på taggens titel. NPR-28990: Programfix för CQ-4199411
* Knappen Avbryt arv visas inte i vissa av de fält som har lagts till i sidegenskaperna. NPR-29079: Programfix för CQ-4265686
* Åtgärden Förhandsvisa utrullning ska inte försöka återskapa den aktiva kopian eller visa den i listan med rolloutsidor. NPR-29151: Programfix för CQ-4266213
* (Mallredigerare) Formatprincipregression i strukturläge. NPR-28981: Programfix för CQ-4264400
* Kapslade live-kopior visar dubblettposter under utrullning. NPR-29300: Programfix för CQ-4268664
* Det går inte att publicera en Live-kopia av en Live-kopia som innehåller en Design Importer-komponent. Det gick inte att hämta referenser för den valda sidan. NPR-28944: Programfix för CQ-4265014
* När CoralUI används med Multifield lagras fileReferenceParameter på komponentnivå i stället för på multifältnivå. NPR-29536: Programfix för CQ-4266129
* Designreferensen replikeras inte vid publicering efter att arv har avbrutits vid designimporteraren. NPR-29648, NPR-29721: Programfix för CQ-4269270, CQ-4271087
* Sökvägsfältet i RTF-redigeraren öppnas i rotsökvägen oavsett vilken sökväg som har angetts för sökningen. NPR-29483: Programfix för CQ-4268997
* (IE11) Kopiera och klistra in HTML-innehåll i en RTE-komponent med defaultPasteMode = plaintext klistrar inte in innehållet som oformaterad text. NPR-29432, NPR-29171: Programfix för GRANITE-24941
* Stavningskontrollen i RTF-redigeraren fungerar inte längre på andra språk. NPR-29506: Programfix för CQ-4264990
* XSS (Cross-site scripting) på Campaign-sidan. NPR-29614: Programfix för CQ-4269322
* Om du minimerar RTF-redigeraren från helskärmsläge i källredigeringsläge leder det till innehållsförlust. NPR-29574: Programfix för CQ-4260584
* (Klassiskt användargränssnitt) Det går inte alltid att navigera till den sista fliken när det finns ett stort antal taggar. NPR-29544: Programfix för CQ-4264548
* (Klassiskt användargränssnitt) Admin Console-navigeringsmenyn försvinner och sidan läses inte in helt. NPR-29571: Programfix för CQ-4264585
* Felvarning genereras när komponenter läggs till på WCM-sidan när miniatyrbilder är aktiverade på instansen. NPR-29396: Programfix för CQ-4266196
* Ett problem med arv av Style System-noder från den överordnade noden. NPR-29296: Programfix för CQ-4266041
* Sidan som återställs med Timewarp ska referera till rätt bild vid versionshanteringen.  NPR-29431: Programfix för CQ-4262638
* Tom sida med Javascript-fel i redigeraren efter installation av den senaste 6.4.5-versionen av ögonblicksbilden. NPR-29475: Programfix för CQ-4266196
* När du lägger till en komponent i en parsys respekteras inte designkomponentlisteegenskapen och den matchas mot ett annat mallnodnamn med en liknande parsystruktur. NPR-29509: Programfix för CQ-4269044
* cq:dropTarget-zonen täcker hela komponenten i stället för bildens storlek, vilket försvårar målsättningen med inbäddade komponenter. NPR-29738: Programfix för CQ-4268912
* Bildkomponenten anropar inte &quot;afteredit&quot;-avlyssnaren när bildens redigerare på plats används. Programfix NPR-29616 för CQ-4268065
* Ett problem med att konfigurera social publicering på Facebook. NPR-29212: Programfix för CQ-4266630
* När du befordrar starter för ändrade sidor beaktas ändringar i både käll- och startgrenarna. NPR-29308: Programfix för CQ-4266746
* Den återgivna miniatyrbilden för innehållsfragment visar intern kalenderrepresentation för fältet Datum och Tid. NPR-29531: Programfix för CQ-4269362
* Det går inte att lägga till en tagg i flera sidor med befintliga olika taggar. NPR-28729: Programfix för CQ-4262922
* Ikonen för schemalagd aktivering visas inte i webbplatsadministratören. NPR-28725: Programfix för CQ-4263917

**Replikering**

* Känsligt informationsexponeringsproblem i replikeringsagentkomponenten. NPR-29612, NPR-24951: Programfix för GRANITE-25070
* Data som tillhandahålls av användaren kan inte utelämnas vid utdata i cq/replication/components/agent-komponenten, vilket resulterar i en lagrad XSS-säkerhetslucka (Cross-site scripting). Programfix för CQ-4266263

**Experience Fragments**

* Det går inte att exportera Experience Fragments till target när en smart bild används. Programfix för CQ-4269606

**Socialt - Rapportering**

* AEM Community-rapporter visas inte i AEM-författarinstansen. Programfix för CQ-4266294

**Plattform**

* XSS (Cross-site scripting) i pakethanteraren när ett paket installeras. NPR-29734, NPR-29713, NPR-29630: Programfix för GRANITE-26161, GRANITE-
* Flera lagrade och reflekterade XSS (Cross-site scripting) i CRXDE Lite. NPR-29634: Programfix för GRANITE-26049
* Inloggningsfunktionen för paketresurs använder GET-begäran i stället för POST-begäran, vilket gör att lösenordet visas under nätverksfliken. NPR-29631: Programfix för GRANITE-26048

**Felix**

* XSS (Cross-site scripting) observeras i systemkonsolen. Sidan läses in och popup-fönstret visas när musen förs över textfältet. NPR-29853, NPR-29633: Programfix för GRANITE-26188, GRANITE-26050

**Granit**

* Loggningsloggningskonfigurationen för Apache Sling filtrerar inte det inmatade skriptet.  NPR-29775: Programfix för GRANITE-26051

**Communities**

* Grupper som tagits bort av författaren bör tas bort från publiceringsinstanserna. NPR-28933: Programfix för CQ-4264645
* Apphemlighet ska skyddas med ett lösenordsfält, och inte visas i oformaterad text för verktyg för social anslutning. NPR-29728: Programfix för CQ-4270480
* Besökare och medlemmar utan moderatorbehörighet kan se ej godkända/väntande inlägg genom att klistra in URL:en. NPR-29726: Programfix för CQ-4271124, CQ-4271441
* En hög svarstid på upp till 40-50 sekunder observeras vid användarinloggning för Community. NPR-29678: Programfix för CQ-4269444

**Översättning**

* Användare som inte har tillgång till översättningsfunktioner vid navigering bör inte kunna komma åt sina undersidor. NPR-29644: Programfix för CQ-4269979
* Användarbehörigheter som inte stöds som guide tillåter att översättningskopian skapas på en skrivskyddad plats. NPR-29375: Programfix för CQ-4265877

**UI - Foundation**

* Ökade sidnumreringsgränsen för sökresultatet till 100 sidor för kortvyn och 200 för listvyn. NPR-29332: Programfix för GRANITE-24644
* På grund av lat inläsande av taggar visas inget på samlingssidan. NPR-29267: Programfix för GRANITE-24902
* Om du ändrar sidnumreringsgränsen till 100 i stället för 40 utlöses en extra lat inläsning utan en sidnumreringsbegäran. NPR-29246: Programfix för GRANITE-25027
* AEM granite-lösenordsfältet fylls inte i efter kryptering. NPR-29245: Programfix för GRANITE-24908

**Integrering**

* Ett undantagsmeddelande visas när du försöker redigera och spara AEM-startkonfigurationen. NPR-29086: Programfix för CQ-4266153
* BrightEdge-autentiseringsuppgifter misslyckas med anslutningsfel.  NPR-29167: Programfix för CQ-4265872
* Den ärvda kryssrutan som visas på rotnivån i Cloud Service Configs bör tas bort. NPR-27856:  Programfix för CQ-4259676

**Sling**

* HTTP-anslutningens timeout läses inte från konfigurationerna. NPR-29264: Programfix för SLING-7902
* Skrivning av JCR-installationsprogrammet gör att OSGi-konfigurationen använder ett ogiltigt format och blockerar omdistributionen. NPR-29027: Programfix för CQ-4264694

**Projekt**

* Användarna kan inte slutföra projektarbetsflödet. NPR-29621: Programfix för CQ-4258791
* I projektarbetsflödeslistan visas tomma rader utöver 40 arbetsflöden. NPR-28739: Programfix för CQ-4264005
* Om du väljer alternativet för dynamisk återgivning i varumärkesportalen hämtas en tom ZIP-fil. NPR-29420: Programfix för CQ-4268826
* Publicera resurser från AEM Author /content/dam/mac-mappen till Brand Portal fungerar inte. NPR-29820: Programfix för CQ-4271118
* Interpunktion i namnet orsakar problem med publiceringsknappen. NPR-29573: Programfix för CQ-4269317
* Det går inte att skapa en kopia av resursspråket via referenspanelen. Programfix för CQ-4269535

**Arbetsflöde**

* Uppgradera från 6.4.2 till 6.4.4 om du vill ta bort dialogrutans kalenderväljarfält. NPR-29727: Programfix för CQ-4270423

**WCM - Administratörsgränssnitt**

* Knapparna visas inte när du öppnar fliken Behörigheter i Coral2-implementeringen. Programfix för CQ-4269419

**WCM - MSM**

* Om du tar bort en underordnad nod i live-kopian bör liveRelationship frigöras. Programfix för CQ-4270395
* Uppgradera till AEM 6.4.3 så att det tar lång tid att driftsätta Multi-Site Manager. Programfix för CQ-4271410

**Sårbarhet**

* CSRF-skyddsramverket fungerar inte med AEM Foundation-formulär. NPR-28612: Programfix för GRANITE-22231

**WCM - sidredigeraren**

* XSS (Cross-site scripting) speglades när en ogiltig väljare användes. Programfix för CQ-4270397

**Formulär**

De viktigaste nyheterna i AEM 6.4.5.0-formulär är:

**Formulärtilläggspaket**

**Adaptiva former**

* (Touch UI) Alternativet Starta arbetsflöde öppnar inte dialogrutan för konfiguration. NPR-29521: Programfix för CQ-4269050

**Formulär - serverdelsintegrering**

* Aktiverat stöd för ADFS (Active Directory Federation Services) v3.0 för integrering på plats i Microsoft Dynamics. NPR-30003, NPR-29484: Programfix för CQ-4270586
* Tjänsten för förifyllnad misslyckas på grund av en längre handläggningstid från AEM Forms-dataintegreringsmodulen. NPR-28997: Programfix för CQ-4265988
* SOAP-webbtjänstbegäran har fel format i AEM Forms. NPR-29013: Programfix för CQ-4265443
* Inget felmeddelande visas vid testning av SOAP-tjänsten om datumvärdet är felaktigt. Programfix för CQ-4265445

**Formulär - Interaktiv kommunikation och interaktiva formulär - korrespondenshantering**

* CCR-gränssnittet (Create Correspondence UI) hanterar inte ett flyttal.  NPR-29210: Programfix för CQ-4254201
* Verktygstipset för en variabel visas inte i gränssnittet för att skapa korrespondens (CCR UI). NPR-29739: Programfix för CQ-4250533
* Det går inte att kopiera eller klistra in från Omnissearch inom brev. NPR-29808: Programfix för CQ-4270783

**HTML5-formulär**

* När vi lägger till ett blanksteg i texten kan textfältet inte fyllas i till slutet. NPR-28844: Programfix för CQ-4260239

**Formulär-JEE-installationsprogram**

**Formulär - Foundation JEE**

* Webbtjänstkomponenten i AEM Forms Workbench kan inte anropa en webbtjänst, vilket kräver tvåvägs SSL-autentisering. NPR-29485: Programfix för CQ-4246794
* Konfigurationshanteraren för AEM Forms JEE fungerar inte med flera nätverkskort. NPR-29236: Programfix för CQ-4268598
* AEM-startfel från GemFire: java.lang.IllegalStateException: Endast en AdminDistributedSystem-anslutning kan göras samtidigt. NPR-29524: Programfix för CQ-4266295
* NoClassDefFoundError på grund av att jar-versionen inte matchar. NPR-28834: Programfix för NPR-28834

**Formulär - dokumenttjänster**

* Ogiltig PDF/A-fil rapporteras som giltig PDF/A med isPDFA-åtgärd. NPR-29076: Programfix för CQ-4261541
* PDF-filen kan inte konverteras till PDF/A-1b med formulärfältet har ingen utseendeordlista. NPR-29534: Programfix för CQ-4269618
* PDF/A-konvertering från PDF som skapats med utdatatjänsten godkänns inte vid validering med Acrobat DC. NPR-29647: Programfix för CQ-4270448
* Apache POI-paketet misslyckas med ett undantag. NPR-27861, NPR-28048: Programfix för CQ-4245898, CQ-4244778

**Formulär - Designer**

* Stöd för PDF/UA i XFA-formulär (XML Forms Architecture) som genererats med Designer och Output Service. NPR-23022

**Formulär - arbetsflöde**

* Det går inte att skicka från arbetsytan med ett omgivande tecken. NPR-29087: Programfix för CQ-4263172

**Funktionspaket ingår**

**Assets**

* Aktiverat stöd för flera Platshanterare för resurser. Mer information finns i [Återanvända resurser med MSM för resurser](/help/assets/reuse-assets-using-msm.md). NPR-26450: Programfix för CQ-4259922

**OSGI-paket och innehållspaket som ingår**

Följande text innehåller en förteckning över OSGI-paket och innehållspaket som ingår i den gemensamma fiskeripolitiken.

Lista över OSGi-paket som ingår i AEM 6.4.5.0

[Hämta fil](assets/6.4.5.0_bundles.txt)

Lista över innehållspaket som ingår i AEM 6.4.5.0

[Hämta fil](assets/6.4.5.0_OSGI.txt)

#### AEM 6.4.4.0 {#experience-manager-6440}

AEM 6.4.4.0 är en viktig uppdatering som omfattar prestanda, stabilitet, säkerhet och viktiga kundkorrigeringar och förbättringar som släppts sedan den allmänna tillgängligheten av AEM 6.4 i **april 2018.**

Det är också kumulativt, vilket innebär att 6.4.4.0 innehåller alla tidigare AEM 6.4-servicepaket.

Några av de viktigaste nyheterna i AEM 6.4.4.0 är:

* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.11.
* Stöd för cachelagring av tjänstversion har lagts till för att undvika vanliga HTTP-begäranden i tjänstversionen.
* Stöd för borttagning av automatiska taggar har lagts till.
* Oändlig bläddring för katalogguiden har implementerats.
* Stöttad möjlighet att begränsa behörigheter enligt communitysajter.
* Prestandakorrigeringar (cachelagring, asynkron körning, exkluderingslista) för hälsokontroll för Sling Granite-innehåll.
* Knappen Resursväljare har lagts till i dialogrutan för sidminiatyrer.
* En ny egenskap har lagts till som tillåter placering av verktygstipset i fält.
* Förbättrat stöd för ColorPicker i Multifield.
* En kontroll har lagts till för att ignorera tomma värden för talinmatningsmultifält i innehållets libs.
* Aktiverat stöd för Microsoft Translator Text API v3.

**Assets**

* Migrera AVS- och Stock-integrering till AEM 6.4.4.0 NPR-27632
* Om du publicerar en tom resursmapp med undermappar försvinner undermapparna. NPR-27558: Programfix för CQ-4254701
* Tillägg av en enda icke-namngiven sträng\[\]-egenskap orsakar ofullständig XMP-tillbakaskrivning. NPR-26805: Programfix för CQ-4254142
* När du har rastrerat PDF-indata saknas bilder i utdata. NPR-27929: Programfix för CTG-4150481
* Guiden Flytta resurs visar ett felaktigt antal referenssidor för publicerade sidor. NPR-27833: Programfix för CQ-4258014
* AssetPicker söker bara efter den första taggen för att filtrera resultatet när du filtrerar med taggar. NPR-27778: Programfix för CQ-4257705
* PDF-hanteraren AEM OTB fastnar vid bearbetning av PDF-filer med främmande tecken. NPR-28778: Programfix för CQ-4254234
* När en CSV-fil har ett värde som avgränsas med kommatecken i en enda kolumn, kommer AEM CSV-redigeraren inte att kringgå kommatecknet och behandla det som en separat kolumn. NPR-28801: Programfix för CQ-4261694
* Problem med metadataschredigeraren när sökvägsläsaren används för att välja data. NPR-28674: Programfix för CQ-4263005
* För många resurser bearbetas till tjänsten för smart innehåll vilket ger en enorm tid att slutföra den periodiska taggningsprocessen. NPR-28640: Programfix för CQ-4262661, CQ-4262644, CQ-4263234
* Skrivbordsåtgärder fungerar inte för Omnissearch-resultat från `aem/start.html` sidan. NPR-27242: Programfix för CQ-4248176
* Resurs-API tillåter inte överföring av fil > 2 GB vilket orsakar överföringsfel. NPR-27629: Programfix för Granite-23590
* Metadata sparas inte i den hämtade resursen i det första försöket om Dynamic Media är aktiverat för instansen. NPR-28233: Programfix för CQ-4260759
* Tjänstmatcharen är inte stängd i SiteCatalyst-konfigurationen. NPR-28015: Programfix för CQ-4259397
* Att flytta resurser i DAM resulterar inte i en liknande rörelse i Scene7 (p2p-konfiguration). NPR-28313: Programfix för CQ-4261091

**Sites**

* (Klassiskt användargränssnitt) En bråkdel av live-kopior visas i utrullningslistan. NPR-28598, NPR-28574: Programfix för CQ-4263410
* LiveRelationshipManagerImpl genererar undantag när cq:master är tom eller ogiltig. NPR-28590: Programfix för CQ-4263115
* Sidorna tas inte bort på rätt sätt när arbetsflödet &quot;Begär borttagning&quot; är klart. NPR-28668: Programfix för CQ-4263195
* Relationsstatusgränssnittet visar inte korrekta år- eller tidsstämpelvärden för relaterade fält för koral-datumväljare. NPR-28666: Programfix för CQ-4263661
* XSS (Cross-site scripting) i SuggestionHandler för 6.4. NPR-28693: Programfix för CQ-4253821
* Flytta en mapp från webbplatsadmin som slutar på minnet och gör att AEM inte är tillgängligt. NPR-28346: Programfix för CQ-4261398
* MSM LiveCopy-utrullningskonfigurationer förloras efter uppdatering. NPR-28311: Programfix för CQ-4258705
* Det går inte att bläddra igenom fler än 40 ritningskonfigurationer. NPR-27640: Programfix för CQ-4239166
* Användning av SyntheticResource som referens ger ett Null-pekarundantag och blockerar flyttningen av sidorna.  NPR-27576: Programfix för CQ-4258262
* PushOnModify fungerar inte för borttagning på en instans som är uppgraderad till 6.1 till 6.4. NPR-28108: Programfix för CQ-4259833
* (Klassiskt användargränssnitt) Knappen Avbryt arv saknas och komponenten kan redigeras på en live-kopieringssida. NPR-28256: Programfix för CQ-4260161
* OakState0001: Olösta konflikter vid utrullning. NPR-27982: Programfix för CQ-4259548
* När du kopierar/klistrar in en struktur som innehåller SyntheticResource-referenser avslutas processen med felet 500. NPR-27709: Programfix för CQ-4259179
* Det går inte att avsluta pågående arbetsflöden när nyttolaster är aktiverade. NPR-27672: Programfix för CQ-4258520
* Vid utrullning visas duplicerade utrullningsvägar efter uppgradering från 6.1 till 6.4. NPR-27845: Programfix för CQ-4259487
* Integrera dam assetpicker modal i sidminiatyrkomponenten. NPR-28131: Programfix för CQ-108042
* (Klassiskt användargränssnitt) Det går inte att öppna dialogrutor med widgeten Taggar. NPR-28575: Programfix för CQ-4262680
* Filöverföring med flera fält visar inte släppzon. NPR-28676: Programfix för CQ-4263516
* Felet &#39;Ogiltigt värde för rekursionsväljare&#39; uppstod när en komponent skulle migreras från AEM 6.0 till AEM 6.2. NPR-28609: Programfix för CQ-4241258
* RTF-redigeraren i dialogrutan flimrar när en plugin-moduls pover är större än textområdet, vilket blockerar all ytterligare redigering. NPR-27579: Programfix för CQ-4257440
* (Klassiskt användargränssnitt) cq:action editannotate fungerar inte. NPR-28232: Programfix för CQ-4257703
* Om du tar bort taggar från sökpanelen för taggfilterresurser i sidredigeraren uppdateras inte listan korrekt. NPR-27983: Programfix för CQ-4245567
* Om värdena för flerfältsnumret är tomma, kommer klickning på Spara att resultera i ett oändligt laddningsmeddelande utan att något faktiskt slutförs.  NPR-28400, NPR-28393: Programfix för CQ-4244058, CQ-4244349
* Med bara läsbehörighet kan användare/grupper inte markera en XF-fil och har inget alternativ för att visa XF-filen och dess sidegenskaper. NPR-28341: Programfix för CQ-4260412
* JSON-data som tagits emot från Target har ett antal escape-tecken som gör att programsidan bryts. NPR-28318: Programfix för CQ-4252043
* Det går inte att redigera någon komponent efter installation av AEM 6.4.3. NPR-28125: Programfix för CQ-4261216
* Borttagning av alla taggar för ett taggfält bevaras inte för ett strukturerat innehållsfragment. NPR-28133: Programfix för CQ-4247241
* När du redigerar ett innehållsfragment med egenskaperna jcr:lastmodifiedby och jcr:lastmodified uppdateras värdena utan att användaren gör några ändringar. NPR-27847: Programfix för CQ-4257138
* Versionshantering för innehållsfragment jämför skillnader för AEM 6.4. NPR-27764
* Om inga cq:allowedTemplates har definierats för /content/experience-fragments och allowedPaths används i Experience Fragement-mallen genereras ett fel när Experience Fragement flyttas/kopieras. NPR-27487: Programfix för CQ-4257489
* Knappen Skapa visas vid uppdatering för den nya användaren. NPR-27335: Programfix för CQ-4255360
* När du försöker flytta en publicerad sida är antalet referenssidor som visas på den första sidan i guiden Flytta sida felaktigt. NPR-28111: Programfix för CQ-4259663
* (Touch UI) Rail för referenser visar inte inkommande länkar. NPR-28529: Programfix för CQ-4262306
* Det går inte att redigera några komponent- och sidegenskaper efter installation av AEM 6.4.3. NPR-27998: Programfix för CQ-4261216, CQ-4260441
* Migrera kontexthub till jquery 3. NPR-28397: Programfix för GRANITE-19902

**Handel**

* Det går inte att välja katalog om det finns mer än 20 kataloger i en mapp. NPR-27649: Programfix för CQ-4258119
* Vyer för handelsguider och egenskaper bryts eftersom header.reference saknas. Programfix för CQ-4261122

**Campaign - målinriktning**

* com.day.cq.personalization.impl.TeaserResourceEventHandler placeras i en oändlig slinga och orsakar uppdateringar av noder på publiceringsinstanser. Programfix för CQ-4263096

**Replikering**

* Det uppstod ett fel när replikeringsinnehållet com.day.cq.replikation.AccessDeniedException skapades. NPR-28314: Programfix för CQ-4261401
* Sessionsläcka när användaragent-ID är inställt på administratör i replikeringsagenten. NPR-28220: Programfix för CQ-4255517

**DAM - Creative Cloud**

* Stöd för HTTP API för att hitta liknande bilder inifrån AEM Assets. Programfix för CQ-4254091
* Förbättra AVS-API:t så att resultaten av en fråga kan begränsas till medlemmarna i en samling. Programfix för CQ-4258708

**DAM - format**

* När exporten av metadata har startats omdirigeras sidan till en 404-sida. Programfix för CQ-4262447

**DAM - Allmänt**

* (Adobe Stock-integrering) Serverfel visas med ett Oauth-fel i filen error.log. Programfix för CQ-4260406
* Integreringen med Adobe Stock fungerar inte om 6.4.4 tillämpas på 6.4.3. Programfix för CQ-4266009
* Länken till CF-modellen saknas även efter att SP3-korrigeringen har tillämpats. Programfix för CQ-4259029

**Plattform**

* (Klassiskt användargränssnitt) Redigeringsknappen är inte tillgänglig i basrapportkomponenten efter uppgradering till 6.4.2. NPR-28560: Programfix för CQ-4262825
* När du använder en fråga som kombinerar property.operation=like och property.depth, slutar det med ett InvalidQueryException. NPR-28570: Programfix för CQ-4262652
* Internt serverfel när nyligen tillagd språknod tas bort från överlagrad språknod. NPR-28661: Programfix för CQ-4239194
* Null-pekarundantag i stderr.log i sling-oak-1-tråd vid slumpmässiga starter. NPR-28665: Programfix för CQ-4237845

**Felix**

* webconsole.plugins.memoryusage orsakar ett dödläge vid uppdatering. NPR-27895:  Programfix för GRANITE-20715

**Granit**

* Hälsokontrollen för Sling Content Access utför lång verifiering med mycket hög/libs för anpassad resursmatchningssökväg. NPR-28113: Programfix för GRANITE-23529

**Hantering av innehållsfragment**

* Förbättrad användbarhet och paritet med resurser för innehållsfragment. Programfix för CQ-4253883

**Communities**

* Uppgradera sårbara bootstrap till 3.4 och keditor-bibliotek till 4.5.11. NPR-28490: Programfix för CQ-4257511
* Om du avbryter redigeringslägena återställs inte den borttagna bilagan. NPR-27902: Programfix för CQ-4255150
* Dispositionen för lådans räkning bör bara vara synlig för de behöriga medlemmarna. NPR-27900: Programfix för CQ-4251235
* Lägg till rep:cache i Ignorable Nodes på AEM Communities User Sync Listener på publiceringsinstanser. NPR-27842: Programfix för CQ-4247234
* Sökrutan visar ett escape-tecken på gränssnittsnivå. NPR-27838: Programfix för CQ-4259757
* Ett fel genereras när du söker efter specialtecken som (, +,?) i snabbsökning. NPR-28213: Programfix för CQ-4260969
* Skapa en&quot;community-specifik administratörsgrupp&quot; så att användarna kan redigera och skapa den aktuella communitywebbplatsen. NPR-27731
* Lagt till logik för tangentbordshändelser för att öppna video. NPR-27726: Programfix för CQ-4254026
* Aktiverad tangentbordsnavigering för AEM Communities-aktiveringskomponenter vid publicering. NPR-27728: Programfix för CQ-4254028
* Lagt till ariaetikett för list- och kortvyknappar. NPR-27727: Programfix för CQ-4254027
* Hantera sessioner med lösare för öppna resurser i sociala communities. NPR-27721: Programfix för CQ-4258714

**Översättning**

* Stöd för Microsoft Translator Text API v3. NPR-28366: Programfix för CQ-4249755
* jcr:language &amp; cq:language uppdateras inte automatiskt i det översatta språket. NPR-28338: Programfix för CQ-4256046
* Cykliska referenser orsakar StackOverflowError när en språkkopia skapas. NPR-27596: Programfix för CQ-4255621
* Om du klickar på Spara och stäng i ett flerspråkigt översättningsprojekt skapas nya projekt i stället för att nya översättningsjobb skapas i det befintliga projektet. NPR-28219, NPR-28236: Programfix för CQ-4261276, CQ-4260731
* Felsträngen är för lång för att lägga till innehållsfragment med gruppdata på grund av begränsning av antalet tillåtna tecken. NPR-28722: Programfix för CQ-4262362

**Social**

* Kommentarer som skickas till nästa sida markeras med gult varje gång en ny kommentar publiceras. Programfix för CQ-4261359
* Det går inte att ta bort kommentarer i användargenererat innehåll med API. NPR-28075: Programfix för CQ-4261135
* AbstractNotificationOperationService orsakar ClassCastException. Programfix för CQ-4260456
* Ta bort referens till SCORM-molnet (Shareable Content Object Reference Model) i spelaren. Programfix för CQ-4260779

**UI - Foundation**

* Funktionen &quot;Filesystem output cache&quot; som är integrerad i HTML Client Library Manager bryter funktionen &quot;debugClientLibs&quot; för kompilerade skript som LESS-filer. NPR-27249: Programfix för Granite-23313
* Antalet resurser som visas när felsökningsläget aktiveras är alltid 1 och många JS-fel genereras i webbläsarens konsol.  NPR-27575: Programfix för GRANITE-23750
* Spara och stäng sidegenskaperna återgår inte till rätt sida i AEM WAR med Tomcat. NPR-27566: Programfix för GRANITE-23671

**Integrering**

* `com.day.cq.personalization.impl.TeaserResourceEventHandler` går in i en oändlig slinga och orsakar uppdateringar av noder på publiceringsinstanser. NPR-28561: Programfix för CQ-4263096
* Cq:actions beaktas inte för en målkomponent. NPR-27616: Programfix för CQ-4257497
* LiveCopy-arvsannullering fungerar inte korrekt på målbehållare. NPR-28129: Programfix för CQ-4259813
* (Cloud Service Configs) Kryssrutan&quot;inherited from&quot; som visas på rotnivån bör tas bort. NPR-27856:  Programfix för CQ-4259676

**Sling**

* Uppdatering till Sling Models API 1.3.8, Impl 1.4.10. NPR-27636: Programfix för GRANITE-23537

**OAK - Segmentets beständighet**

* SegmentBufferWriter rensas inte efter OnRC. NPR-27464

**Projekt**

* Flerspråksöversättningsprojekt skapar inte flera språkjobb för användare som inte ingår i administratörsgruppen. NPR-28508: Programfix för CQ-4262023
* ProjectTaskListServlet läcker en ResourceResolver när getTaskRenderers anropas när tjänsten startas. NPR-27590: Programfix för CQ-4258011
* Om en katalog har fler underkataloger än sidstorleken, och sidordningen är efter datum eller storlek, går det inte att gå förbi den första sidan med ett fel. NPR-28867: Programfix för CQ-4265039
* Korrigeringar för serveröverskridande skriptning (XSS) i DAM-visningsprogram. NPR-28106:  Programfix för CQ-4253215
* Det går inte att lägga till sidor i översättningsprojekt av projektadministratörer eftersom länken för att lägga till nya sidor i översättningsprojektet inte är synlig. Programfix för CQ-4266334

**Arbetsflöde**

* När vi öppnar dialogrutan för hela arbetsobjektet i arbetsflödesmeddelandet som har ett taggfält läggs en taggegenskap till i det när du klickar på krysset. NPR-28304: Programfix för CQ-4261321
* Knappen Växla användarval i dialogrutan Tilldela om uppgift fungerar inte. NPR-28963: Programfix för CQ-4264206

**Formulär**

De viktigaste nyheterna i AEM 6.4.4.0-formulär är:

* Utökat stöd för att registrera API:er för dokumentsäkerhet för signering och certifiering som transaktioner.

**Formulärtilläggspaket**

**Integrering med Adobe Sign**

* AEM 6.4 Forms Client SDK innehåller inget adobesign-recept-paket. NPR-27735: Programfix för CQ-4259372

**Adaptiva former**

* När ett adaptivt formulär skapas med en tom mall kan kunderna inte underordnade paneler till formulärets rotpanel. NPR-28758: Programfix för CQ-4264157
* När värdet för datumkomponentens årsfält är 9999 misslyckas valideringsskriptet. NPR-28580: Programfix för CQ-4262620
* När ett adaptivt formulär skapas med en tom mall, kan kunderna inte använda underordnade paneler i formulärets rotpanel. NPR-28758: Programfix för CQ-4264157
* Det går inte att ange ett värde mellan fälten för lazy loaded-fragment i ett adaptivt formulär. NPR-27758: Programfix för CQ-4259703
* För adaptiva formulär används inte RTF-redigerare, men biblioteken läses in.  NPR-27759:  Programfix för CQ-4259193
* Omdirigering till URL fungerar inte för adaptiva formulär som är inbäddade på en AEM Sites-sida. NPR-27620: Programfix för CQ-4239287
* Det går inte att ange ett värde mellan fälten för lazy loaded-fragment i ett adaptivt formulär. NPR-28320: Programfix för CQ-4262345
* För adaptiva formulär används inte RTF-redigerare, men biblioteken läses in.  NPR-28001: Programfix för CQ-4259703, CQ-4259193
* Skriptsignatur fungerar inte för AEM Forms-appar som körs på Apple iOS 12.1. NPR-28497: Programfix för CQ-4261765
* Skicka åtgärd med hjälp av&quot;Forms Workflow&quot; Classic-redigeringsproblem i 6.4. Programfix för CQ-4252740
* Fel vid hantering av block och borttagning av tmp-lagring. NPR-28806: Programfix för CQ-426441

**Formulär - korrespondenshantering**

* Agentens användargränssnitt behåller inte bildens ursprungliga storlek. NPR-28800: Programfix för CQ-4259767
* CCR/Agent-gränssnitt: Etiketter för datumfält har flyttats på fliken Data. Programfix för CQ-4255499

**Formulär - transaktionsrapportering**

* Stöd har lagts till för att räkna med digitala signaturer eller certifiera ett dokument som fakturerbara transaktioner. NPR-28495: Programfix för CQ-4260236
* Digitala signaturer har lagts till och certifiera till fakturerbart API. Programfix för CQ-4260236

**Formulärhantering**

Stöd har lagts till för att ersätta användningen av verktygsfältsklientbibliotek med understreck i Forms Managers guide för att starta granskning och flytta resursguiden. NPR-27643: Programfix för CQ-4246536.
Ett paket är fortfarande installerat när du har installerat Forms Management-paketet på gren release/640. Programfix för CQ-4265410Formulär som skickas med bilagor visas inte i arbetsflödet med åtgärden Anropa arbetsflöde för AEM-formulär och aktivera portalsändning har markerats. Programfix för CQ-4263110

**Formulär - serverdelsintegrering**

* Det går inte att testa preprocessor för-/efterbearbetning och anpassad sändning med Client SDK, snabbkorrigering för CQ-4238469

**Formulär-JEE-installationsprogram**

**Formulär - dokumentsäkerhet**

* När du använder uppdateringsprinciptjänsten kan det inte uppstå ett fel i objektet. NPR-28751: Programfix för CQ-4252287
* Signaturbygge misslyckades med en äldre version av Commons-pkg. Programfix för CQ-4265535

**Formulär - Foundation JEE**

* När AEM Forms har infogats på IBM WebSphere misslyckas skapandet av en formulärdatamodell baserad på SOAP. NPR-27923: Programfix för CQ-4251134
* SRT-verktyget i PDF Generator kan inte identifiera den installerade versionen av Adobe Acrobat. NPR-27971

**Formulär - Designer**

* Vissa JPEG-bilder i en XDP-mall återges inte korrekt.  NPR-26702: Programfix för LC-3917457

**Formulär - OBSOLETE**

* Pappersfångsttjänsten kraschar vid bearbetning av TIFF-filer. NPR-28079:  Programfix för CQ-4240649

**Formulär - arbetsflöde**

* HTML5-formulär med standardskickningsprocessen i an.lca fungerar inte med JBoss 7. NPR-28675: Programfix för CQ-4243928
* Det går inte att skicka PDF-formulär i HTML Workspace. NPR-28058: Programfix för CQ-4260373
* Kunddata skrivs ut i informationsloggar med hjälp av arbetsflödet Anropa FDM Service Forms. Programfix för CQ-4260385

**Funktionspaket ingår**

**Sites**

* Versionshantering för innehållsfragment jämför skillnader i AEM 6.4.  NPR-26760: FP för CQ-4248839
* Förbättringar av variationsskillnader för innehållsfragment för AEM 6.4.  NPR-27866: FP för CQ-4248839
* Aktiverad funktion i OSGI-konfiguration **AEM Workflow Retdraw Feature Flag**. Återkallningsåtgärden bör avsluta arbetsflödesinstansen efter att flaggan har angetts. NPR-26451: Programfix för CQ-4259090

**Plattform**

* Förbättrad extrahering av Query Builder-faktor utnyttjar Oak API för 6.4. NPR-26674: FP för CQ-4230337

**OSGI-paket och innehållspaket som ingår**

Följande text innehåller en förteckning över OSGI-paket och innehållspaket som ingår i den gemensamma fiskeripolitiken.

Lista över OSGi-paket som ingår i AEM 6.4.4.0

[Hämta fil](assets/bundles_6_4_4_0.txt)

Lista över innehållspaket som ingår i AEM 6.4.4.0

[Hämta fil](assets/osgi_package_6_440.txt)

#### AEM 6.4.3.0 {#experience-manager-6430}

AEM 6.4.3.0 är en viktig uppdatering som omfattar prestanda, stabilitet, säkerhet och viktiga kundkorrigeringar och förbättringar som släppts sedan den allmänna tillgängligheten av AEM 6.4 i april 2018.

Det är också kumulativt, vilket innebär att 6.4.3.0 innehåller alla tidigare AEM 6.4-servicepaket.

Några av de viktigaste nyheterna i AEM 6.4.3.0 är:

* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.9.
* Stöd har lagts till för egenskapen allowedPaths i adaptiva formulärmallar.
* Förbättrad panelbaserad sökning efter resurser i AEM
* Korrigeringar för XSS (Cross-site scripting) på inloggningssidan.
* Förbättrad gränssnittsinstrumentering.
* Förbättrad FormData-hantering.
* Förbättrad hantering av objektnamngivning inuti ett multifält.
* Förbättrad hantering av platshållarobjekt (kortvyn och listvyn) under markeringen.
* Adobe IMS-autentisering och stöd för Admin Console för hanterade tjänster har lagts till.

**Assets**

* Arbetsflödet för DAM-uppdatering av resurs extraherar inte referenser från INDD-filer om alternativet Dolda ID är aktiverat. NPR-26243; Programfix för CQ-4250933
* Meddelandet om att åtgärden lyckades visas inte när resurser publiceras med Assets Bulk Editor. NPR-26252; Programfix för CQ-4251688.
* När du har tittat på en resurs från ett sökresultat och klickar på knappen Bakåt i webbläsaren visas felmeddelandet&quot;Ogiltig begäran&quot; med felkoden 400. NPR 26578; Programfix för CQ-4253741
* Metadata för resursen visar ett ogiltigt namnområdesfel efter installation av ett Service Pack. NPR-22341; Snabbkorrigering för CQ-4237202
* Alternativet att ändra ordning på mappar och innehållsfragment i listvyn visas inte för de tillämpliga mapparna. NPR-27153; Programfix för CQ-4255873
* Användare kan inte lägga till resurser i en ny samling eftersom det resulterar i ett felmeddelande med en skadad bild i felets popup-dialogruta. NPR-22431; Programfix för CQ-4237086
* Listrutan Cascading stöds inte i dynamiska listrutor. NPR-27043; Programfix för CQ-4252564
* Om användare anger ett icke-standardvärde för Företagets rotmapp i DMS7-molnkonfigurationen fungerar inte visningsförinställningen som förväntat. NPR-26360; Programfix för CQ-4249505
* Resursrapporteringen misslyckas för instanser med ett mycket stort antal resurser. NPR-27278; Programfix för CQ-4256748
* Undermappar ärver inte den överordnade mappens SmartCrop-bildprofil. NPR-27197; Programfix för CQ-4256273
* När integreringen av dynamiska media är aktiverad ändras vissa metadataegenskaper för Assets. Bredd, höjd och platsattribut visas inte. NPR-27203; Programfix för CQ-4256258
* Dynamic Media använder inte den konfigurerade proxyn för vissa typer av resurser. NPR-25211; Programfix för CQ-4244871
* Sidan för metadataredigeraren innehåller ett null-pekarundantag för ogiltig objektparameter. NPR-26169; Programfix för CQ-4241368.
* Om en nedrullningsbar meny har en urvalsregel och en obligatorisk regel har tillämpats på den kan den obligatoriska regeln inte uppfyllas i metadataredigeraren. NPR-27479; Programfix från CQ-4251428

**Sites**

* Användaren kan styra textredigeringsfunktionerna i helskärmsläge i helskärmsläge i , men kan inte styra redigeringsfunktionerna i RTF-redigeringsprogrammet i Edit Dialog med innehållsprinciper. NPR-26750: Programfix för CQ-4241130
* RTF-redigerare blir oanvändbara när de växlar från helskärm till flytande dialogruta. Den flytande vyn innehåller två RTF-redigerare. NPR-25589: Programfix för CQ-4206008
* När returtangenten (Retur-tangenten) trycks ned i ett textfält växlar textredigeraren till helskärmsläge. NPR-26204: Programfix för CQ-4245893
* List-plugin för RTF-redigerare inaktiveras automatiskt och tillåter inte ändringar. NPR-26507: Programfix för CQ-4239387
* När ett specialtecken läggs till i textredigeringsfönstret rullas fönstret uppåt. NPR-26435: Programfix för CQ-4249869
* Client Context segment.js caching vs. frågor som inte cachelagras. NPR-26622: Programfix för CQ-4253486
* När en underordnad regel aktiveras från författarinstansen till publiceringsinstansen slutar publiceringsinstansen att fungera. NPR-26601: Programfix för CQ-4253588
* När RTF-redigeraren kombineras med flera fält visas ett TypeError-undantag: fieldAPI.getName är inte en funktion vid foundation.js-fel inträffar. NPR-27146: Programfix för CQ-4253155
* Salesforce-integrering kan inte använda proxykonfigurationen. NPR-27244: Programfix för CQ-4245300
* När du schemalägger en sida för aktivering med alternativet Hantera publikation för ett senare datum och växlar till listvyn saknas kalenderikonen. NPR-26974: Programfix för CQ-4239206
* Användare kan inte redigera behörigheter för slutna användargrupper i sidegenskaperna. NPR-27138: Programfix för CQ-4256089Det går inte att redigera taggar via taggning. NPR-26957: Programfix för CQ-4254858
* När en tagg som refereras från en strukturerad innehållsfragmentmodell flyttas, uppdateras inte de befintliga referenserna till taggen i ett innehållsfragment. Detta händer i redigeringsskärmen för innehållsfragmentmodellen. NPR-26776: Programfix för CQ-4251805
* När du skapar och befordrar en start med flera sidor skapas flera versioner för varje sida. NPR-26917: Programfix för CQ-4254663
* AEM siteadmin hanterar inte sökvägar som anges i webbläsarens adressfält. NPR-26780: Programfix för CQ-4254097
* När en sida flyttas till en ny plats utan att namnet på den ändras, går sidans versionshistorik förlorad. NPR-26706: Programfix för CQ-4254025
* URL:er i Experience Frment Admin Editor tillåter inte övertäckningar. NPR-26319: Programfix för CQ-4252156
* När en sida skapas med en mall som innehåller ett tomt upplevelsefragment och publiceras går det inte att öppna sidan och ett DefaultSlingScript-fel inträffar. NPR-26305: Programfix för CQ-4252460
* När data används i klasser med samma namn skapas kod som inte är kompatibel. NPR-27282: Programfix för Sling-7581
* Efter installation av uppgradering av SP har webbplatserna en tom konfiguration för utrullning av utkast. NPR-27609: Programfix för CQ-4257078

**DAM - varumärkesportal**

* Taggpredikat publiceras inte när metadata-schemaformulär publiceras på varumärkesportalen. Programfix för CQ-4256218
* När en mapp på tredje nivån publiceras från AEM till varumärkesportalen ändras mappnamnet utan att de överordnade mapparna publiceras. Programfix för CQ-4255423
* Webbläsarpredikatet för sökvägen publiceras från AEM Assets till Brand Portal som förväntat. Den publicerade sökvägen på BP är dock fortfarande /content/dam, som måste uppdateras. Programfix för CQ-4256240

**DAM - Creative Cloud**

* Ikonen&quot;Sök efter Adobe-resurser&quot; saknas i AEM-huvudnavigeringen. Programfix för CQ-4254343

**DAM - DM-klient**

* När videoklipp har importerats till en mapp som är associerad med AVS-videobearbetningsprofilen uppdateras webbläsarfönstret om och om igen. Programfix för CQ-4253563
* YouTube Publish misslyckas när en Ad hoc-tagg som innehåller versaler används. Programfix för CQ-4252477
* När en anteckning skapas i en resurs som PDF startar gränssnittet en oändlig siduppdateringsslinga. NPR-27052: Programfix för CQ-4255396

**DAM - DM-tjänster**

* Dynamic Media använder inte den konfigurerade proxyn för vissa typer av resurser. NPR-10727; Programfix för CQ-4244871

**Plattform**

* Prestandaproblem med org.apache.sling.i18n. NPR-26812: Programfix för SLING-7543
* Det går inte att se nodegenskaperna när XML-indata formateras och distribueras. NPR-26198: Programfix för CQ-4250448
* IndexOutOfBoundsException i ResourceProviderTracker. NPR-26968: Programfix för GRANITE-23310
* JMX-konsolen samlar många administratörssessioner och en ny session öppnas var femte minut. NPR-26958: Programfix för CQ-4251090
* När du har uppgraderat från 6.2 till 6.4 visar loggfilen stackspårning för resurslösaren com.adobe.granite.repository.hc.impl.content.sling.SlingContentHealthCheck. NPR-26176: Programfix för Granite-21734
* När en rensningsagent som är klar att användas för att uppdatera alias konfigureras, misslyckas åtgärden med ett StackOverflowError-undantag. NPR-26373: Programfix för CQ-4242928
* Replikeringen använder utgången OAuth-token tills den misslyckas. NPR-25894
* Begränsad sida (sidan Stängd användargrupp) med sling: alias inte omdirigerar användaren till inloggningssidan. NPR-25715: Programfix för Granite=22263
* Vid publicering av taggar visas ingen aktivitet i användargränssnittet. Programfix för CQ-4255961
* Det går inte att redigera taggar i klassiskt användargränssnitt. Programfix för CQ-4258697
* Uppdaterat org.apache.felix.http.bridge till version 4.0.4. NPR-27038: Backport för Granite - 23334
* Aktivitetsloggar för pakethanteraren ska extraheras i en separat loggfil. NPR-27323: Programfix för Granite-14866
* Paketvalideraren rapporterar inte övertäckningar i CFP. NPR-27119: Programfix för GRANITE-22825

**Projekt**

* AVS-API hanterar inte sidindelning med enbart underordnade underkataloger. NPR-27617: Programfix för CQ-4258639

**OAK**

* Det går inte att logga in på databasen efter installation av AEM 6.4 Service Pack 2. NPR-27171: Programfix för Granite-23317

**Replikering**

* Granskningsloggen är öppen med aktiva sessioner som hela tiden ökar med ~750 varje dag. NPR-27062: Programfix för CQ-4241350

**Communities**

* Formposter och svar läggs till ovanpå den andra sidan och när de uppdateras flyttas inlägget till rätt plats överst på den första sidan. NPR-27342: Programfix för CQ-4247338
* Länkar till alla resurser släpper kontextsökvägen (/aempublish) efter rullning. NPR-26982: Programfix för CQ-4254345
* Tillagda grupper visas inte i listrutan Community Managers, Community Moderators och Privileged Member när en publicerad webbplats redigeras. NPR-27190: Programfix för CQ-4258574
* Endast 10 grupper visas på sidan för aktiveringsresurser, även om sidnumrering är aktiverat för grupplistning. NPR-26934: Programfix för CQ-4252985
* Alternativet att aktivera/inaktivera sökning för schemalagd post i journalkomponenten finns i ConfigMgr, och jobbet SearchScheduledPosts har optimerats. NPR-26923: Programfix för CQ-4250463
* Sök efter nyckelord i adress fungerar inte på komponentsidor i kalendern när AEM-communityn är inställd på att fungera med DSRP. NPR-26737: Programfix för CQ-4258493
* En direkt länk till kommentaren i stället för huvudposten i en kommentars detalj har implementerats för modereringsgränssnitt och aktiveringsresurser. NPR-26704: Programfix för CQ-4251381
* Innehåll som modereras via flerval på modereringskonsolen visas inte på aktivitetsströmmen. NPR-26695: Programfix för CQ-4253244
* Sökningen med Förnamn och Efternamn i fältet Till i Communities Messaging returnerar inte det förväntade resultatet. NPR-26385: Programfix för CQ-4248673
* Ett fel uppstod vid överföring av en annan bifogad fil än bilden (till exempel .pdf) i forum. NPR-27360: Programfix för CQ-4257753
* Det går inte att ta bort eller ta bort funktioner från ett foruminlägg om Författare-Publicera har angetts med MySQL DSRP. NPR-26125; Programfix för CQ-4251520
* Samlingskomponenter (forum, bloggar, kalender, ideation, QnA) har nu en egenskap i komponentdialogrutan för att aktivera/inaktivera Blockera UGC i redigeringsläge för författare för att tillåta/neka UGC-inläsning i WCM-redigeringsläge. NPR-26978: Programfix för CQ-4248161
* Sök taggar fungerar inte för lokaliserade söktermer. NPR-26171: Programfix för CQ-4249926
* Bakåtknappen hoppar över en sida i forumsökningen. NPR-26950: Programfix för CQ-4254804
* AEM-instansen som körs på standardHTTP-porten (80) kan inte nå imsmanifest.xml. NPR-27173: Programfix för CQ-4252211
* Avmarkera kommentar som ett svar på fråga om A fungerar inte om AEM Communities har angetts med DSRP. NPR-26247: Programfix för CQ-4252232
* Det går inte att ringa till Adobe Storage: 414-fel - Long GET URI observeras när användare söker i /content/community-components/en/search.html och väljer författarfält som ett av filtren för söktermen. NPR-26643: Programfix för CQ-4251303
* Listrutevärdet för DataCentreURL i ASRP-konfigurationen ändras från Dallas till Virginia (för VA6). NPR-26936: Programfix för CQ-4254434
* Specialtecken i forumsökningen returnerar fel eller inga resultat. NPR-26930: Programfix för CQ-4247744
* Numret som visas för&quot;Antal resultat&quot; i forumsökningen använder en felaktig avgränsare för engelska och tyska språk. NPR-27050: Programfix för CQ-4248939
* Olästa meddelanden ökar inte efter 21. NPR-26946, NPR-27480: Programfix för CQ-4252829, CQ-4256939
* Sidnumreringen i kommentarsavsnittet i en komponent gör att användarna rullar uppåt för att se sidinnehållet när de når en sida genom sidnumreringen. NPR-27032: Programfix för CQ-4251228
* Community-webbplatsmappen kan inte klickas på miniatyrbilder när du visar från Admin Console på AEM Author-instansen. NPR-26986: Programfix för CQ-4254036
* Med alternativet&quot;Markera alla som lästa&quot; markeras endast de första 10 meddelandena som lästa och andra förblir olästa tills sidan uppdateras. NPR-27037: Programfix för CQ-4254058
* Sidnumrering aktiveras inte för identifiering och listan med ämnen (eller svar) blir längre om den inte läses in igen. NPR-26193: Programfix för CQ-4252104
* Andra användares aktiviteter och borttagna användargränssnittskontrollen visas när du loggar in med moderatorautentiseringsuppgifter och lägger till&quot;#social-tasks&quot; eller&quot;#tabs-2&quot; i slutet av moderatorns profil-URL. Programfix för CQ-4251355
* Det går inte att ta bort alla tilldelade taggar från en bloggartikel. NPR-26851: Programfix för CQ-4253359
* Relationer till UGC tas inte bort när UGC tas bort. NPR-27630: Programfix för CQ-4258706
* Länk till svar fungerar inte när du klickar på svar på forum. NPR-27623: Programfix för CQ-4256138
* Begränsningen för användarabonnemang är begränsad till 1 000. NPR-27614: Programfix för CQ-4254689
* Om du redigerar en plats och redigerar roller i rollinställningarna genereras ett undantagsfel för null-pekare. NPR-27377; Programfix för CQ-4255909

**Översättning**

* Översättningsförhandsgranskning fungerar inte med exempelinnehållet we.retail. NPR-26727: Programfix för CQ-4241179

**UI - Foundation**

* Ett NullPointerException returneras vid försök att hämta konfigurationer efter uppgradering till AEM 6.4. NPR-27310: Programfix för Granite-23573
* Proaktiv backport för korrigeringar av granite.platform.login. NPR-26941
* Proaktiv backport för granite.ui.content fixes. NPR-26294
* Nummerfältskomponenten validerar inte negativa tal i Internet Explorer 11. NPR-26701
* Proaktiv backport för granite.ui.coralui3-korrigeringar. NPR-26662
* Proaktiv backport för granite.ui.coralui3-eon-korrigeringar. NPR-26666
* Proaktiv backport för granite.ui.foundation.components-korrigeringar. NPR-27313
* Proaktiv backport för granite.ui.commons-korrigeringar. NPR-26753
* Proaktiv grundläggande gränssnittssupport. NPR-26248

**Integrering**

* Ändringar i AEM-upplevelser som skapats med målmotorn publiceras inte. NPR-24869: Programfix för CQ-4247832
* Det går inte att skapa flera aktiviteter och upplevelser om deras namn innehåller japanska tecken. NPR-27271: Programfix för CQ-4256857
* Uppdatera start-API-slutpunkt. NPR-26790: Programfix för CQ-4254380
* (Personalization) BrandsRetriever leder hela trädet. NPR-27060: Programfix för CQ-4255790

**WCM - Administratörsgränssnitt**

* Lagt till HTTP-test för publicering/avpublicering av en sida med referenser och ett UI-test för Live Copy. Programfix för CQ-4256894

**WCM - sidredigeraren**

* Verktygsfältet Redigera inaktiveras för komponenter vid den första redigeringen. Programfix för CQ-4253270

**Formulär**

De viktigaste nyheterna i AEM 6.4.3.0-formulär är:

* Aktiverat stöd för en array/lista med objekt med dynamisk entitetsersättning.
* Aktiverade FIPS-kompatibilitet för Reader Extended-arbetsflöde i Digital Signature, Reader Extensions, CryptoProvider och TrustStore.
* Stöd för PDF/UA i XFA-formulär som genererats med Designer eller Output Service.
* Aktiverat stöd för egenskapen allowedPaths i adaptiva formulärmallar.
* JBoss 7.1.4-stöd för AEM Forms 6.4 har lagts till.

**Formulärtilläggspaket**

**Integrering med backend**

* Det går inte att fylla i mappningar av formulärdatamodell som baseras på dynamiska entiteter i SOAP-svar. NPR-26428: Programfix för CQ-4250639
* Värdet för _elementNamespace i formulärdatamodellens ytterligare data, som anges med Test UI, återspeglas inte korrekt i SOAP-begäran. Programfix för CQ-4255373
* En egenskapsbegränsning som kan ha värdet null initieras med ett standardvärde och kan inte synkroniseras med FDM. Programfix för CQ-4253873
* Standardvärdet för egenskapen nullable är inte angivet till True för OData-datakällan. Programfix för CQ-4253870

**Adaptiva former**

* Det gick inte att läsa in webbplatser och formulärredigeraren. NPR-26977; Programfix för CQ-4249170
* Problem när en bifogad fil läggs till i ett anpassat formulär med hjälp av tangentbordet. NPR-25913; Programfix för CQ-4249456

**Formulär - Interaktiv kommunikation**

* Det går inte att flytta en panel som har lagts till med alternativet Lägg till underordnad panel i innehållsträdet i webbkanalen för interaktiv kommunikation och i adaptiva former. Programfix för CQ-4253915
* Tabellnamn visas i stället för namnet på FDM-associationen i avsnittet Datakällor i utskriftskanalen. Programfix för CQ-4253669
* Funktionen isUseXFABullets() är inte inaktiverad i klassen PrintChannelRenderOptions och är tillgänglig i klient-SDK. Programfix för CQ-4246583, CQ-4252700

**Korrespondenshantering**

* Javadocs för 6.4 innehåller inte com.adobe.dbforms.* och motsvarande klasser. Programfix för CQ-4253200
* CCR UI visar ett standardskräppostvärde för datumfältet om det inte finns några indata från testdata-XML. Programfix för CQ-4252041
* Om en bokstav innehåller en listmodul försvinner mellanrummet mellan punkten och texten när du genererar PDF från bokstaven. Programfix för CQ-4250588

**Forms Manager**

* Aktiverat stöd för egenskapen allowedPaths i adaptiva formulärmallar. NPR-26598: Programfix för CQ-4255892

**Formulär - arbetsflöde**

* Om det finns klammerparenteser i uppgiftsnamnet när formulärarbetsflödet körs visas ett undantag i loggarna. Programfix för CQ-4256626
* Det går inte att öppna en sökmall på arbetsytan i AEM Forms. Programfix för CQ-4255651

**Mobilformulär**

* Avslutsmeddelandet visas inte när datumfältet i AEM Forms renderas som HTML i Internet Explorer eller Chrome avslutas. NPR-26483: Programfix för CQ-4239352
* Datum som finns i XML när bearbetningen börjar orsakar ett valideringsfel när användaren försöker lämna formuläret. NPR-26787: Programfix för CQ-4251211

**Formulär-JEE-installationsprogram**

**Tjänsten PDF Generator**

* Det går inte att visa standardrapporter och kompatibilitetsinställningar för PDF-generatorn. NPR-26715: Programfix för CQ-4253384
* den binära filen convertpdf saknas i AIX Forms-tilläggspaketet, vilket orsakar fel när PDFA-tjänsten anropas. Programfix för CQ-4257873

**Dokumenttjänster**

* Lägg till FIPS-kompatibilitet för RE-arbetsflöden i Digital Signature, Reader Extensions, CryptoProvider och TrustStore. NPR-27495: Programfix för CQ-4257572
* Konverteringen misslyckas när tjänsten AssemblerService.toPDFA körs i en slinga. NPR-26354: Programfix för CQ-4248656
* Det går inte att validera PDF-filernas överensstämmelse korrekt baserat på PDF/A-1b-standarder. NPR-26286: Programfix för CQ-4227539
* Slut på minne när du uppgraderar AEM-formulär från 6.1 SP2 CFP5 till CFP13. NPR-26285: Programfix för CQ-4244379
* Det går inte att validera PDF-filernas överensstämmelse korrekt baserat på PDF/A-standarder. NPR-26272: Programfix för CQ-4248823

**Formulär - Foundation JEE**

* JBoss 7.1.4-stöd för AEM Forms 6.4 har lagts till. NPR-27331; Programfix för CQ-4255601

**Inkluderade funktionspaket**

* Aktiverat stöd för en array/lista med objekt med dynamisk entitetsersättning. NPR-26590: Programfix för CQ-4254655

**OSGI-paket och innehållspaket som ingår**

Lista över OSGi-paket som ingår i AEM 6.4.3.0

[Hämta fil](assets/6.4.3.0_bundles.txt)

Lista över innehållspaket som ingår i AEM 6.4.3.0

[Hämta fil](assets/6.4.3.0_OSGI.txt)

#### AEM 6.4.2.0 {#experience-manager-6420}

AEM 6.4.2.0 är en viktig uppdatering som omfattar prestanda, stabilitet, säkerhet och viktiga kundkorrigeringar och förbättringar som släppts sedan den allmänna tillgängligheten av AEM 6.4 i **april 2018.**
Det är också kumulativt, vilket innebär att 6.4.2.0 innehåller alla tidigare AEM 6.4-servicepaket.

Några av de viktigaste nyheterna i AEM 6.4.2.0 är:

* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.7.
* Stöd för HTML Template Language (HTML) Specification 1.4 har lagts till
* Stöd för MongoDB Enterprise 3.6 har lagts till.
* Sidredigeraren Sites har stöd för kontextredigering och komposition med komponenter på klientsidan som byggs in React eller Angular i kombination med <a href="../sites-developing/spa-walkthrough.md">AEM:s SPA Editor JS SDK</a>.
* Förbättringar av innehållsfragment: lade till möjligheten att kommentera i textfält och en jämförelse av versioner sida vid sida.
* Lagt till [integrering med Adobe Stock](/help/assets/aem-assets-adobe-stock.md) så att användarna kan söka efter, förhandsgranska, spara och licensiera Adobe Stock-mediefiler direkt från AEM-användargränssnittet. Mer information finns i [Använda Adobe Stock-mediefiler med AEM Resurser](https://helpx.adobe.com/experience-manager/kt/assets/stock-assets-feature-video-use.md).
* Resurser har fått stöd för dynamisk villkorsstyrd metaschema och möjlighet att ange ett metadataram för resursmappar.
* Lagt till konfiguration i varje komponent för att aktivera/inaktivera funktionen för att skapa/uppdatera mappminiatyrer.
* Förbättrad bildredigering vid sidredigering.
* Regressionskorrigering i Communities för poängsättningshändelse hanteras inte korrekt om det valda svaret tas bort.
* Gränsen för högsta antal sökresultat för ljudet till MAX_INT-10000 har ändrats.
* Transaktionsrensningsjobbet startas bara vid det första anropet till storeTransaction.
* Knappen Markera alla är nu tillgänglig i kortvyn och kolumnvyn.
* Hjälpmedelsförbättringar i CoralUI.
* Förbättrad hantering av Coral.Keys.
* Uppdaterat moment.js till 2.22.2
* Uppdaterad jquery till 1.12.1
* Introducerad komponent för grundarbetsflödesstatus.
* GCC har uppdaterats till den senaste versionen.
* Flytta SAML till ny extern IDP-synkronisering.

**Assets**

* Generering av delresurser för pptx-filen innehåller inga bilder eller miniatyrbilder. NPR-24286: Programfix för CQ-4217986
* migrateAllAssets - Lägg till stöd för gruppbearbetning och förbättra AEM-metoden som lägger till UUID till gamla resurser. NPR-24861: Programfix för CQ-4242863 och CQ-4247874
* Prestandaproblem med generering av miniatyrbilder. NPR-24693: Programfix för CQ-4246960
* (Touch UI) Komponenten för optionspredikat förblir tom när den läggs till på utgivarsidan för resursresurs. NPR-24643: Programfix för CQ-4245295
* (Arbetsflöde) Resurser för smarta taggar bearbetas inte via proxykonfigurationen. NPR-25840: Programfix för CQ-4248202
* (Omnissearch) När du tar bort filtypen:image från sökvillkoren tas inte bildtypen bort. NPR-25232: Programfix för CQ-4248280
* När du försöker flytta en fil till en annan mapp visas inte mappar med apostrof i namnet. NPR-25125: Programfix för CQ-4248660
* Skjutreglage på sidan för underresurser fungerar inte korrekt när språkinställningen är inställd på annat än engelska. NPR-25274: Programfix för CQ-4248489
* Problem med csv-fil för metadataexport när den öppnas på datorer med europeiskt nummerformat. NPR-26009: Programfix för CQ-4250677
* Knappen Skapa är inte tillgänglig för val av resursmapp utan behörigheten Ta bort. NPR-25788: Programfix för CQ-4250140
* (Backport) Förbättrad tillgänglighet: Duplicera-id: id-attributvärdet måste vara unikt, Label: Formulärelement måste ha etiketter och länknamn: Länkarna måste ha urskiljbar text. NPR-24252: Programfix för CQ-4250905, CQ-4250906, CQ-4250907
* Det går inte att överföra en CSV-fil med fält avgränsade med&quot;,&quot; för europeiska länder. NPR-25549: Programfix för CQ-4249931
* (Varumärksportal) Delresurser i en flersidig PDF-fil publiceras inte när en resurs publiceras. NPR-25991: Programfix för CQ-4245162
* Publicera senare funktioner för AEM till varumärkesportalreplikering. NPR-25911: Programfix för CQ-109139
* Publicering och avpublicering av den privata samlingen av icke-adminanvändare resulterar i en NPE-fil. NPR-25906: Programfix för CQ-4250594
* Inaktivera publicering av innehållsfragment och formulärscheman till varumärkesportalen. NPR-24176, NPR-26004: Programfix för CQ-4251592, CQ-4252026
* (Dynamic Media) Uppdaterade DM-visningsprogram till version 5.10.1, som gör det möjligt att kontrollera dubblettnamn på sidan Bildförinställning. Mer information finns i Uppdatera dynamiska mediavisare (5.10.1). NPR-24403: Programfix för CQ-4247554
* Javascript-fel i webbläsarkonsolen i kolumnvyn när du väljer en resurs eller mapp. NPR-25939: Programfix för CQ-4250228
* (Kolumnvy) Det går inte att identifiera uppgifter eftersom nyckelfilen visas som en tom vit post. NPR-25903: Programfix för CQ-4246307

**Sites**

* Frågan om datakälla.jsp i AEM 6.2 skiljer sig från AEM 6.4. NPR-24968: Programfix för CQ-4244235
* (Klassiskt användargränssnitt) Det går inte att lägga till taggar på sidor. NPR-25255, NPR-25612: Programfix för CQ-4249615
* HTML-mallsspecifikation 1.4 har funktioner som stöds av AEM 6.4.2.0 NPR-24585
* Fel arv på lokal komponent efter kopiering av en live-kopieringssida. NPR-25920: Programfix för CQ-4236737, CQ-4248957
* ON/OFF-tid lagras i crx/de men hämtar inte samma i gränssnittskonsolen för sidegenskaper. NPR-25154: Programfix för CQ-4243431
* Stilar Dialogrutans inledande egenskapsvärden bryts. NPR-25648: Programfix för CQ-4250073
* När du definierar en cq:tagName-egenskap i en cq:htmlTag-nod beaktas inte taggnamnet om komponenten inkluderas via JSP. NPR-24154: Programfix för CQ-4244120
* För kapslade parsyskomponenter tillämpas alltid den första (med den minst kapslade sökvägen) som uppfyller designen från flera tillgängliga komponenter. Mer information finns i [Utforma banupplösning](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/page-templates-static.html). NPR-24973: Programfix för CQ-4246276
* När du klistrar in text i en RTE-komponent visas en popup-dialogruta, men den återges inte korrekt. NPR-24895: Programfix för CQ-4245901
* (RTE) Prestandaproblem med obligatorisk fältindikator. NPR-24894: Programfix för CQ-4241895
* (Sidkomponent) Om du lägger till en komponent i Parsys klipps den av från höger och dras ut från enhetens bildrutebredd. NPR-25536: Programfix för CQ-4238224
* I redigeringsprogrammet för oformaterad text skickas data som inte har trimmats och extra blanksteg läggs till. NPR-25312: Programfix för CQ-4249006
* När komponenten öppnas i inbyggt läge visas inte plugin-program som lästs in tidigare den andra gången. NPR-24610: Programfix för CQ-4236850
* När du läser in en XF-fil i redigeringsvyn genom att kopiera/klistra in, läses inte mallvariationen in automatiskt. NPR-24841: Programfix för CQ-4248037
* Fel HTML-struktur i siteadmin/admin bryter IE11. NPR-24686: Programfix för CQ-4246363, CQ-4248402
* (Guiden Hantera publikation) Kalendern för aktiveringsdatum i steget Alternativ öppnas inte efter vissa åtgärder i steget Omfång. NPR-25681: Programfix för CQ-4250205
* Klassiskt användargränssnitt kan inte redigera CUG på grund av borttagning. NPR-25075: Programfix för 4241823
* Alternativet Skapa är inte tillgängligt för att skapa upplevelsefragment. NPR-26053: Programfix för CQ-4249923
* XF-varianten aktiveras därför två gånger och duplicerade ID:n genereras för samma objekt. NPR-24179: Programfix för CQ-4245093
* Foundation-tabellen är sårbar för lagrade korsskriptning mellan webbplatser. NPR-25185: Programfix för CQ-4240760
* Felet &#39;Ogiltigt värde för rekursionsväljare&#39; uppstod när en komponent skulle migreras från AEM 6.2.1.13 till AEM 6.4. NPR-24146

**WCM - sidredigeraren**

* Flera staplade parsyer på grund av långvariga frågor (fler än 6) gör att AEM blir trögt. Programfix för CQ-4240247
* JS-fel när tom cq:tagName läggs till i cq:htmlTag-noden. Programfix för CQ-4251852
* Uppdatera EditableActions baserat på omplaceringen columnClassNames. Programfix för CQ-4250781
* Visa resurs- och modellsökvägar med en enda egenskap och ett enda attribut. Programfix för CQ-4251255
* Återställ ändringar av API:t export.json. Programfix för CQ-4251854
* (Redigerbar SPA) Release-kandidat för 1.0.0. Programfix för CQ-4251991
* Verktygsfältet för redigering inaktiveras för andra komponenter när du redigerar en komponent. Programfix för CQ-4253270

**Integrering**

* Fälten Bibliotek och Hämta URL måste vara redigerbara. NPR-24804: Programfix för CQ-4246864
* Problem med flera DTM-konfigurationer. NPR-24685: Programfix för CQ-4247293
* Stöd för asynkron distribution av värdbaserade klientbibliotek har lagts till. NPR-25716: Programfix för CQ-4245745
* Målkomponenten där motsvarande erbjudande saknas återger hela sidan och i stället för en tom målkomponent läggs en annan fullständig återgivning av sidan till. NPR-25273: Programfix för CQ-4248003
* Målmotorn (mbox.js, at.js) använder inte inbyggda URL:er och URL:er som innehåller kolon som kan misslyckas vid vissa distributioner. NPR-25339: Programfix för CQ-4237854
* (Launch)LibraryDownloadProcess lagrar fel libraryUri-värde. NPR-25330: Programfix för CQ-4250006

**Plattform**

* Indexerar om slinga| NPE vid utförande av BinaryTextExtraction under uppgradering från 6.3 till 6.4. Programfix för Granite - 21677
* Gränsöverskridande åsidosättning av intern markerad sökväg /libs/cq/cloudserviceconfigs/templates/configpage/jcr:content - Problem vid körning av mönsteridentifierare. NPR-25036: Programfix för CQ-4248597
* Loggposter har inte skrivits på grund av NPE i LogEntryImpl. NPR-25627: Programfix för Granite-22383
* Replikering av borttagningshändelsen söker inte efter rättigheter. NPR-25679: Programfix för CQ-4241234
* Stöd för STARTTLS har lagts till i&quot;Day CQ Mail Service.&quot; NPR-25611: Programfix för CQ-4249924
* Proaktiv backport för granite.platform.login korrigeras för att förbättra tillgängligheten. NPR-25176: Programfix för Granite 21746 och Granite-21309
* (AEM 6.4) Ett fel uppstod när paketet skulle återskapas och installeras om. NPR-25173: Programfix för CQ-4247939
* Standardvärdet MERGE_PRESERVE aclHandling har tagits bort. NPR-24593: Programfix för Granite-21889
* Content-Type är inte propogerad och saknas i svaret efter att ContentDispositionFilter har använts två gånger. NPR-24175: Programfix för Sling-7525
* Pakethanterarens status är felaktig efter uppgradering till AEM 6.4-grenen. NPR-24551: Programfix för Granite-21750
* AMS-instans - Felloggningsanalys. Programfix för CQ-4249567

**Dokumentskydd**

* SAML-inloggningen omdirigeras till utloggningssidan med Okta IDP. NPR-25523: Programfix för GRANITE-22364
* IMS-autentisering via externa OAK OAuth-providerkonfigurationer inaktiverar användaren som skapas i AEM. NPR-25301: Programfix för Granite-22363

**MAC - Test- och Target-integrering**

* (Mål) Textkomponentfel vid målanpassning. Programfix för CQ-4233343

**Communities**

* (Filbibliotek) Om du hämtar resurser med blanksteg uppstår formatproblem. NPR-24260: Programfix för CQ-4245159
* Korrigeringar av flera Adobe Social-problem. NPR-24247: Programfix för CQ-4245054, CQ-4245120, CQ-4245296
* Ofullständig rullning för medlemmar och grupper konsolen misslyckas om författaren ska kunna publicera på olika kontextsökvägar. NPR-24437: Programfix för CQ-4246013
* Inlägget återgår inte till det obesvarade läget även om det tas bort från det besvarade läget och poängen inte minskas. NPR-24419: Programfix för CQ-4245797, CQ-4245932
* Händelser som lagts till med hjälp av kalenderfunktioner i communities ger felaktiga värden. NPR-24883: Programfix för CQ-4244056
* (Communities Forum) Problem med sidnumreringsklickning och sidinläsningsbeteende. NPR-24880: Programfix för CQ-4246109
* (Chrome) Tidszonskonverteringar misslyckas för communityhändelser. NPR-24881: Programfix för CQ-4247115
* Det går inte att återge inbäddat objekt i e-postmeddelandet. NPR-24999: Programfix för CQ-4248022
* Automatiseringssekvens ska köras vid UGC-uppdatering förutom när UGC skapas. NPR-25892: Programfix för CQ-4251399
* Modal dialog responsitivity on Groups. NPR-25623: Programfix för CQ-4248805
* Ett undantag genereras när innehåll tas bort. NPR-25869: Programfix för CQ-4248908
* Sidnumrerade länkar till trådar med många inlägg fungerar inte på meddelanden. NPR-25678: Programfix för CQ-4243038
* Tidsvärden i sökresultat visar servertid i stället för klientens tidszon. NPR-25594: Programfix för CQ-4248986
* (Forumkommentarer) Bakåtknappen i webbläsaren fungerar inte som förväntat. NPR-25205: Programfix för CQ-4248573
* (Sökresultat) Bakåtknappen i webbläsaren fungerar inte som förväntat. NPR-25214: Programfix för CQ-4248574
* Null returneras när communitygroupmedlemlist-komponenten läggs över. NPR-25228: Programfix för CQ-4248523
* (Communities Calendar) ClassCastException genereras när händelsen sparas med den nya omslagsbilden. NPR-25167: Programfix för CQ-4248662
* (Communities) Meddelanden trunkeras. NPR-25326
* (AEM Publish) Scorm Resource misslyckas med kontextsökvägen och visar en tom skärm. NPR-26155: Programfix för CQ-4251942
* (MSRP) Den nyligen skapade kalendern sparas delvis och NPE genereras i felloggen. NPR-26071: Programfix för CQ-4250531
* Sidnumreringen Forum/Ämne uppdateras bara när sidan uppdateras. NPR-26070, NPR-25965: Programfix för CQ-4249509
* (Frågor och svar) Det går inte att navigera till föregående sida när en direktlänk till en kommentar öppnas. NPR-26069: Programfix för CQ-4251699
* Överför bild i gruppen Skapa fungerar inte på mobilen. NPR-26172: Programfix för CQ-4251703
* (Meddelanden) När DSRP används visas alltid namnet på meddelandemottagaren som&quot;Okänd&quot;. NPR-26056: Programfix för CQ-4251397
* Statusetiketten för slutförandestatus för aktiveringsSkorm visas tom i användargränssnittet. NPR-26034: Programfix för CQ-4249994
* När du skapar en ny community-grupp skapas en duplicerad community-grupp på ett aktivt/aktivt mongoMK-kluster. NPR-26032: Programfix för CQ-4245884
* (Författare) Det tar för lång tid att läsa in/skapa en grupp i guiden. NPR-26031: Programfix för CQ-4244966
* Parsys försvinner när du lägger till en include-sats i hbs-skriptet. NPR-25908: Programfix för CQ-4250489
* När du aktiverar Tillåt behöriga bör de behöriga medlemmarna endast kunna skapa för användare som är community-medlemmar. NPR-25877: Programfix för CQ-4248450
* Deeplinks blockeras för aktivering. NPR-25966: Programfix för CQ-4251478
* Forumsidbrytningen uppdateras inte dynamiskt när svar tas bort. NPR-25970: Programfix för CQ-4248975, CQ-4252843
* Automatisk rullning och markering fungerar inte med kalender- och filelib-händelser när kommentarer är kapslade. NPR-25958: Programfix för CQ-4251471
* (DSRP) Prestanda för Direct/Deep Link försämras med stora mängder användargenererat innehåll. NPR-25957: Programfix för CQ-4251470
* Det går inte att ändra egenskaperna för Tillåt behöriga medlemmar och Behöriga medlemmar. NPR-26014: Programfix för CQ-4244592
* Markera alla som lästa återställer meddelanderäknarna för alla communitysidor. NPR-25931: Programfix för CQ-4248612
* Redigera IT-program som inte fungerar för DSRP. NPR-25929: Programfix för CQ-4251382
* E-post-IT:er misslyckas på grund av NPE när e-postmallar skapas. NPR-26039: Programfix för CQ-4250962
* Problem med forumtråd vid inbäddning av bilder med mycket hög upplösning. NPR-26037: Programfix för CQ-4244453, CQ-4253099
* Tiden visar växlar när serverns tidszon skiljer sig från användarens tidszon. NPR-26036: Programfix för CQ-4248751
* Om du bifogar en fil två gånger med samma namn till ett foruminlägg uppstår ett serverfel. NPR-24172: Programfix för CQ-4244367
* Prestandakorrigeringar för bakomliggande nätverk - gruppnumrering vid författare och publicering, gruppsökning vid författare, undvikande av serialisering av svar för journal, kalender och idéer samt lazy loading för att hämta gruppmedlemskap (inbjudan/avinbjudan) för varje grupp när grupplistsidan visas. NPR-24538: Programfix för CQ-4246515
* Aktiveringsresurser visas inte på författaren. Programfix för CQ-4252618
* Meddelanden genereras inte för tråd från okända användare. Programfix för CQ-4245132
* Gruppsökning visas inte i den vänstra listen. Programfix för CQ-4252621
* (Författare) Sidindelning fungerar inte för gruppkonsolen. Programfix för CQ-4242786
* Uppgradering av jQuery-gränssnitt. Programfix för CQ-4248894
* Uppgradera till den senaste SCORM 2017.1-versionen. NPR-25675: Programfix för CQ-4240671
* Fälten&quot;Disponera för&quot; är synliga för användare som inte är medlemmar. NPR-25331: Programfix för CQ-4247858
* Posten visas fortfarande i användargränssnittet även efter borttagningen och ger fel i konsolen. NPR-26290: Programfix för CQ-4252803
* (Platsinställningar) Det går att spara ändringar som gjorts i roller. NPR-26274: Programfix för CQ-4252187
* (Säkerhetslucka) Kontoövertagande på grund av felaktig konfiguration av JSON Web Token. NPR-26458: Programfix för CQ-4253314
* Sidindelningen återställs inte när svar tas bort. NPR-26326: Programfix för CQ-4252997
* Bilden som bifogats visas inte i Utkast under redigering. Programfix för CQ-4253360
* Sidan uppdateras inte när den bifogade filen kopplas i relationsdatabasen (DSRP). Programfix för CQ-4253084
* Grupper fungerar inte i Enablement-webbplatsresursen. Programfix för CQ-4252975
* Förutsättningar för utbildningssökvägar sparas inte i Aktivering. Programfix för CQ-4252948

**Arbetsflöde**

* Startgränssnittet för arbetsflöden visar inte tidigare 41 startkonfigurationer och utlöser ett javascript-fel i konsolen. NPR-25028: Programfix för CQ-4247604
* Om du redigerar ett äldre arbetsflöde utan att redigera dess startprogram skapas flera arbetsflöden i ett arbetsflöde som innehåller steget Aktivera sida/resurs. NPR-25870: Programfix för CQ-4250896
* Felaktig länk i arbetsflödets nyttolast om sidan har en metadatanod. NPR-25916: Programfix för CQ-4250733

**Översättning**

* Korrigerat att om du importerar översatta projekt görs två parallella POST-begäranden, vilket ger upphov till fel. NPR-24889: Programfix för CQ-4247638
* Korrigerat att när du skapar översättningsprojekt för flera språk läggs alla sidor för samma språk till i samma jobb. NPR-25091: Programfix för CQ-4246112
* Korrigerade att översättningsjobbet i vissa fall bara listade de 40 översta sidorna. NPR-25974: Programfix för CQ-4248661
* DataPicker-komponenten (Coral2) ändrar inte året. NPR-24466: Programfix för Granite-21893

**UI - Foundation**

* Proaktiv grundläggande gränssnittssupport. NPR-24344, NPR-24345, NPR-25176, NPR-25095, NPR-24332, NPR-25653, NPR-25932, NPR-259 35, NPR-25976
* (Designimporterare) Om du importerar en sida importeras inte js,css. NPR-25203: Programfix för Granite-2236
* Proactive Foundation UI Backports för att förbättra produktens stabilitet. NPR-24334

**MAC - Test- och Target-integrering**

* Den andra sidan av PersonalizationWizard (som startades med Start Targeting) är tom och ger konsolfel. Programfix för CQ-4253277

**Experience Fragments**

* Sammanslagna upplevelsefragment/målintegrering till AEM 6.4.2.0. Programfix för CQ-4248653

**Hantering av innehållsfragment**

* Anteckningar för innehållsfragment och en jämförelse sida vid sida av versioner för innehållsfragment. Programfix för CQ-4247148

**DAM - Allmänt**

* Filtret Utcheckad av fungerar inte korrekt i sökningen. Programfix för CQ-4247070
* När du uppdaterar en resurs blir kopian av resursspråket och dess miniatyrbild tomma. Programfix för CQ-4250641
* Duplicera-id: ID-attributvärdet måste vara unikt. Programfix för CQ-4250905
* Etikett: Formulärelement måste ha etiketter. Programfix för CQ-4250906
* Länknamn: Länkarna måste ha urskiljbar text. Programfix för CQ-4250907
* Migrering av metadatamallar för portmapp, JMX och ServiceUserMapping. Programfix för CQ-4252947
* WebdriverIO-tester körs inte i Version/640-grenen av CQ/dam. Programfix för CQ-4252749
* Länkar till flyttade resurser ändras inte om länken publiceras. Programfix för CQ-4245756

**DAM - visningsprogram**

* Intermittent fel vid inläsning av video med nya visningsprogram 5.10.1. Programfix för CQ-4250562

**DAM-varumärkesportal**

* Det går inte att avpublicera samlingen från varumärkesportalen. Programfix för CQ-4245990
* Det går inte att avpublicera bildförinställningar från varumärkesportalen. Programfix för CQ-4246140
* Delresurser i en flersidig PDF-fil publiceras inte när en resurs publiceras. Programfix för CQ-4245162

**DAM - DMClient**

* När du publicerar en videoresurs på YouTube kommer taggarna som resulterar i YouTube att inkludera taggens fullständiga sökväg. Programfix för CQ-4245549
* (Uppgradering av avanmälan och deltagande) Problem med CSS-omdirigering för visningsprogram. Programfix för CQ-4247854
* Det gick inte att skapa/redigera visningsförinställningen som icke-medlem i gruppen Administratörer. Programfix för CQ-4247618
* (6.4.1.0) Om du lägger till flera videofilmer i flera parsys bryts videospelaren. Programfix för CQ-4248517
* Om du byter namn på och flyttar en resurs i en bilduppsättning blir redigeringen omöjlig. Programfix för CQ-4248434
* När du publicerar stora videoklipp på YouTube genereras timeout-meddelanden. Programfix för CQ-4237831
* (Listvy) Resursväljarens/väljarens användargränssnitt ändras till grått och är inaktiverat för användaren. Programfix för CQ-4237817
* (Lodrät zoomning) CSS läses inte in med ett 404-fel. Programfix för CQ-4236508
* Om du försöker hämta en resurs med ett procenttecken (%) i resursnamnet skapas ett tomt arkiv. Programfix för CQ-4250558
* (Kortvyn) Ingen bearbetningsindikator visas när du använder Kopiera och Klistra in på en videoresurs. Programfix för CQ-4249037
* (Uppgradera från 6.3.2 till 6.4) Förinställningar för uppgradering av bilder visas som &quot;Opublicerade&quot; på sidan Återgivningar, men ger ingen URL-knapp när de väljs. Programfix för CQ-4240406
* Teknisk skuld/mindre förbättringar. Programfix för CQ-4240648
* Resursväljaren (eller Resursväljaren) visar inte alla resurser från de tillgängliga mapparna. Programfix för CQ-4218414
* Bildförinställning utan höjd visar bilder med felaktig storlek. Programfix för CQ-4246546
* (Resurser för flera sidor) Gränssnittet bryts när användaren klickar på anteckningar. Programfix för CQ-4251434
* En uppgradering från 6.3 till 6.4 och senare av Analytics-förinställningen skapas en ny rapportserie och analysförinställning som förlorar användarens äldre rapporteringsdata. Programfix för CQ-4244529
* (Guiden Hantera publikation) Listan med resurser verkar vara tom när du försöker publicera eller avpublicera. Programfix för CQ-4251881
* När du väljer visningsprogram efter att ha visat Set Members (Uppsättningsmedlemmar) kan AVS-videor inte spelas upp. Programfix för CQ-4205308
* Förinställningarna för videobearbetning kan inte ha en ny förinställning för videokodning tillagd och inte heller redigera de befintliga förinställningarna för kodning. Programfix för CQ-4240407
* Bildförinställningar används inte för nedladdade dynamiska återgivningar. Programfix för CQ-4249862
* Knappen Markera alla fungerar inte korrekt på listsidan för visningsförinställningar. Programfix för CQ-4252462
* Videoprofiler: Knappen Markera allt fungerar inte. Programfix för CQ-4253076, CQ-4251447
* SP2-valideringspass - rökpass. Programfix för CQ-4251639

**DAM - DMServices**

* Dynamic Media Renditions kunde inte genereras för EPS-filen. Programfix för CQ-4243688

**Granit**

* Typo i bundle SymbolicName leder till duplicerat paket. Programfix för Granite - 22155
* CUGConfiguration kan inte hämta CugExclude. Programfix för Granite - 21109
* Om du startar om Adobe Granite Workflow Core körs arbetsflödesstegen från mitten igen, vilket skapar onödiga arbetsflöden. NPR-25057: Programfix för Granite-2218
* JcrResourceBundle stöder inte flera basnamn korrekt. NPR-25245: Programfix för Granite-22317
* Vid installation av innehållspaket grupperas åtkomstkontrollistorna efter huvudnamn, vilket bryter behörighetsmodellen. NPR-24583: Programfix för Granite-21591
* Uppdatera Jetty till 9.4.11 för att åtgärda säkerhetsluckor. NPR-25030: Programfix för Granite-22120

**Formulär**

De viktigaste nyheterna i AEM 6.4.2.0-formulär är:

* Lagt till ny egenskap för köer som ska uppdateras utan att webbläsaren uppdateras.
* Funktioner som användaren kan använda samma WSDL-fil för flera tjänster har lagts till.
* Tidsstämpelmönstret som inte stöds togs bort från listrutan för datumväljaren.
* Stöd för underliggande xfaf och pdf i OSGI har lagts till.
* Utökat stöd för att använda [transaktionsrapportfunktionen](https://helpx.adobe.com/experience-manager/6-4/forms/using/transaction-reports-overview.html) vid anläggningsdistributioner.
* Tillagd kod som inte visar underordnade var i villkorsregelredigeraren.

**Formulärtilläggspaket**

**Transaktionsrapportering**

* Uppdatera konfigurationen för transaktionsrapportering med vikten av omvänd replikering konfigurerad på en publiceringsserver. NPR-26050: Programfix för CQ-4246650
* Fördröjd initiering av det periodiska tömningsjobbet. NPR-25968: Programfix för CQ-4245024
* Transaktionsinspelning misslyckas med ett null-pekarundantag. Programfix för CQ-4247302

**Formulär - arbetsflöde**

* (HTML-arbetsyta) När en användare gör anspråk på en uppgift uppdateras antalet köer för den aktuella användaren, men inte för andra användare, såvida inte sidan uppdateras. Problemet har åtgärdats av en ny egenskap. Mer information om hur du konfigurerar den här nya egenskapen för din AEM-instans finns i dess konfigurationsinställningar. NPR-24536: Programfix för CQ-4233665
* Det gick inte att läsa in ett stort formulär i AEM Forms App på 6.4. NPR-24463: Programfix för CQ-4245091
* Problem i appen Mobile Workspace när du försöker visa den delade uppgiften. NPR-25177: Programfix för CQ-4248733
* Inkonsekvent valideringsbeteende mellan webben och APK. NPR-25670: Programfix för CQ-4248178
* När ett anrop till en webbtjänst görs till ett HTML5-formulär som öppnas i klienten misslyckas det och ett felmeddelande returneras. NPR-26048: Programfix för CQ-4244716
* Problem vid anrop till tjänsten i AEM-formulär Windows 6.3. NPR-26468: Programfix för CQ-4252341

**Mobilformulär**

* (Formset) Valideringsfel för SSN- och mobilfält vid förhandsvisning. NPR-24458: Programfix för CQ-4244983
* Data visas inte vid förifyllning av flerradiga fält i HTML-förhandsvisning. NPR-24549: Programfix för CQ-4244212
* Data förloras när skriptet utvärderas i ett flerradsfält. NPR-25333, programfix för CQ-4249610

**Formulär - Interaktiv kommunikation och korrespondenshantering**

* Synkroniseringen misslyckas på konc med grundläggande mall och referera till konc.int. utskriftsmall. NPR-24912
* (CCR) Validerare fungerar inte för fält/variabler. Programfix för CQ-4245047
* Datamodellsobjektsikonen försvinner då och då i verktygsfältet för textredigering. Programfix för CQ-4245122
* Undantagsloggar visas på kopierade konc om originalkonc tas bort. Programfix för CQ-4249378
* I bokstavsåtergivningen utvärderas villkoret inte till true även om data är korrekta. Programfix för CQ-4245944
* Automatiskt genererade komponenter markeras inte när du väljer från innehållsträdet. Programfix för CQ-4246178
* Problem när webbkanalmallsredigeraren öppnas. Programfix för CQ-4248182
* Det går inte att ändra ordningen på resurser som lagts till eftersom upp-/nedpilarna förblir inaktiverade. Programfix för CQ-4252042
* Det gick inte att uppdatera egenskaperna för villkorsmodulen. Programfix för CQ-4247909
* Gränssnittet i dialogrutan Avbryt arv när användaren ändrar ordning på ett objekt i webbkanalen måste förbättras. Programfix för CQ-4241076
* Data i bokstaven som motsvarar bindningar som definieras i XDP fylls inte i med URL för direktbrev. Programfix för CQ-4245833
* (Problem med cache-lagring) Synkroniseringen av webbkanalen återspeglar inte ändringar som gjorts i layoutfragment, textfragment i utskriftskanalen. Programfix för CQ-4251460
* Det går inte att uppdatera egenskaperna för Layoutfragment och DD. Programfix för CQ-4247830
* (CCR) Det går inte att läsa in utkast på nytt på grund av XML-tolkning. Programfix för CQ-4250950
* (IC Editor) Knappen Redigera fragment bör vara mer synlig. Programfix för CQ-4244694
* (XDP) En tom skärm visas när du lägger till ett layoutfragment i det nya delformuläret. Programfix för CQ-4248810
* Testfel för DocumentFragment-master-DeployWithServerSideTests. Programfix för CQ-4245496
* Variabelinstansen för textmodulen har duplicerats i villkorsmodulen. Programfix för CQ-4252128
* PDF-förhandsgransknings-URL:en visar inte transaktionsrapportering vid publicering. Programfix för CQ-4246158
* Konc.int. synkroniseringsrelaterade problem med synkronisering av utskriftskanal till webbkanal. Programfix för CQ-4251505
* EXM: Rensa kod: Ta bort LocalFunctionMapper. Programfix för CQ-4243265
* För att korrigera resurstypen för TableHeader för IC:s webChannel-tabellkomponent. Programfix för CQ-4251821
* (IC Editor) Användbarhetsproblem. Programfix för CQ-4241081
* Delformuläret Utskriftskanal visar inte infogningsfunktioner. Programfix för CQ-4252994
* Synkronisering av ändringar misslyckas efter borttagning av FDM-nod eller variabelplatshållare. Programfix för CQ-4253178
* (Mallredigerare) Den grundläggande mallen visar sidhuvuds-/sidfotens ytterligare dragningsområden och skärmen flimrar när webbkanalen öppnas. Programfix för CQ-4253323
* Autogenererade komponenter markeras inte när de väljs från innehållsträdet. Programfix för CQ-4246178

**Dokumenttjänster**

* (Form Service) OSGI saknar stöd för XFAF. NPR-25181, programfix för CQ-4251313
* Tecknen i rubriken för den sammansatta PDF-filen kommer att bli förvrängda. NPR-25113: Programfix för CQ-4244682

**Adaptiva former**

* Skicka åtgärd som Skicka e-post genererar ett undantag med CC/BC-fält tomma. NPR-25019: Programfix för CQ-4243039
* Det går inte att använda OTB AEM Form-komponenten på grund av ineffektiv fråga. NPR-25065: Programfix för CQ-4247256
* Ta bort sling:orderBefore från dialognoder för guideImageChoiceComponent. Programfix för CQ-4245013
* (Datumväljaren) Redigera mönster stöder inte två typer av tidsstämpelmönster. Programfix för CQ-4237982
* Skicka åtgärd med hjälp av klassiska redigeringsproblem i Forms Workflow. Programfix för CQ-4236981
* (Webbkanal) IC-diagram ska ärva colspan-egenskap från AF-diagram. Programfix för CQ-4252143

**Integrering med backend**

* (SOAP-begäranden) Stora decimaler (fler än sex siffror) representeras i exponentiell notation vilket resulterar i valideringsfel. NPR-25283: Programfix för CQ-4248100
* Felaktig validering av valfria parametrar som definierats i komplexa typer. NPR-25070: Programfix för CQ-4247107
* Funktioner som användaren kan använda samma WSDL-fil för flera tjänster har lagts till. NPR-24604, programfix för CQ-4247756
* FDM blandar parametrarnas ordning i sina SOAP-anrop. NPR-25069, programfix för CQ-4247180
* FDM sammanfogar enheter (i List/Array) i SOAP-begäran. NPR-25284: Programfix för CQ-4248375

**JEE-installationsprogram för formulär**

**PDFG-tjänst**

* Funktionen för att skapa/ändra säkerhetsinställningar fungerar inte. NPR-24769: Programfix för CQ-4246927
* Optimera PDF-filer genom att selektivt frigöra teckensnitt via ett enda API-anrop. NPR-23287

**Dokumenttjänster**

* Utdatatjänsten innehåller inte rätt taggar för hjälpmedelsläsaren. NPR-24438, NPR-24439, NPR-2440, NPR-24441: Programfix för CQ-4243849, CQ-4243845, CQ-4243852, CQ-4243853

**Dokumentsäkerhet**

* Problem med att skapa profiler med dokumentsäkerhet. NPR-25586, NPR-25547: Programfix för CQ-4247086

**Formulär - Foundation JEE**

* Processer som körs som systemkontextkonto regelbundet. NPR-25289, NPR-25313: Programfix för CQ-4249331
* AEM Forms JEE påverkas av APache Struts och Jackson-meddelanden om databindning. NPR-25628: Programfix för CQ-4242891
* Startpunkten för e-post fungerar inte. NPR-25253: Programfix för CQ-4248518

**Funktionspaket ingår**

**Assets**

* Lagt till [integrering med Adobe Stock](/help/assets/aem-assets-adobe-stock.md) så att användarna kan söka efter, förhandsgranska, spara och licensiera Adobe Stock-mediefiler direkt från AEM-användargränssnittet. Mer information finns i [Använda Adobe Stock-mediefiler med AEM-resurser](https://helpx.adobe.com/experience-manager/kt/assets/using/stock-assets-feature-video-use.html. NPR-15779: Programfix för CQ-30857
* Stöd för dynamisk villkorsstyrd metaschema har lagts till. Mer information finns i [Överlappande metadata](/help/assets/cascading-metadata.md). NPR-25189: Programfix för CQ-4237413
* Alternativet &quot;Resurshämtning&quot; har aktiverats för innehållsfragment. Mer information finns i [Resursrapporter](/help/assets/asset-reports.md). NPR-25186: Programfix för CQ-4237410
* Möjlighet att ange ett metadatamatchema för resursmappar. Mer information finns i Schema för [mappmetadata](/help/assets/folder-metadata-schema.md) och i [konfigurationsinställningarna](#configuration-settings-required-for-npr) efter installationen av AEM 6.4.2.0. NPR-21268: Programfix för CQ-4221574

**Sites**

* Tillåt redigering av ett innehållsfragment utan borttagningsbehörigheter. Mer information finns i [Anpassa och utöka innehållsfragment](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/customizing-content-fragments.html#AssetPermissions). NPR-25793: Programfix för CQ-4248750
* Lagt till möjlighet att kommentera innehållsfragment. For more information, see [Variations-Authoring Fragments](https://helpx.adobe.com/experience-manager/6-4/assets/using/content-fragments-variations.html#AnnotatingaContentFragment). NPR-25188: Programfix för CQ-4235336
* Versionshantering: Jämför innehållsfragment sida vid sida. Mer information finns i [Hantera innehållsfragment](https://helpx.adobe.com/experience-manager/6-4/assets/using/content-fragments-managing.html#ComparingFragmentVersions). NPR-25187: Programfix för CQ-4237412
* Förbättringar i bildredigeraren som stöds av AEM 6.4.2.0. Mer information finns i [Bildredigeraren](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html). NPR-24467

**OSGI-paket och innehållspaket som ingår**

Lista över OSGi-paket som ingår i AEM 6.4.2.0

[Hämta fil](assets/6.4.2.0_bundle-list.txt)

Lista över innehållspaket som ingår i AEM 6.4.2.0

[Hämta fil](assets/6_4_2_0content-package-list.txt)

#### AEM 6.4.1.0 {#experience-manager-6410}

AEM 6.4.1.0 är en viktig uppdatering som omfattar prestanda, stabilitet, säkerhet och viktiga kundkorrigeringar och förbättringar som släppts sedan den allmänna tillgängligheten av AEM 6.4 i april 2018.

AEM 6.4.1.0 kan installeras på AEM 6.4 GA. Några av huvudpunkterna i Service Pack är:

* Den inbyggda databasen (Apache Jackrabbit Oak) uppdateras till version 1.8.3.
* Nya förbättrade smarta taggar.
* Korrigeringar i designväljaren, taggväljaren (ändra den virtuella källdatorn och den virtuella måldatorn till auto.)
* Stöd för typeHint har lagts till för att spara värden som sträng.
* Stöd för SMTP över TLS i Mail Service har lagts till.
* Korrigering för proxyhantering för HTTP-vidarebefordrare i DMS7.
* Uppdatera till /etc/clientlibs/social/thirdparty/handlebars/source/handlebars.js version 1.3.
* Korrigeringar i DMHybrid-paket för avanmälan och avanmälan.
* Korrigeringar i smart beskärning.
* Flyttade OTB-konfigurationsvärden till den nya platsen (från /etc till /conf).
* Färgprofiler har lagts till i kundinställningarna på leveransservrar.
* Migrering av inställningar för Image Server från /etc —&amp;gt; /conf.
* Källinnehållsfragment har lagts till för översättning.
* Stöd för ARIA har lagts till i Print och PrintDialog.
* Stöd för ARIA-validering av e-post har lagts till.
* Proaktiv backport för korrigeringar av platform.clientlibs.

**Assets**

* Listrutan Cascading visar tomt när egenskapssidan för resursen öppnas igen. NPR-23042: Programfix för CQ-4238761
* Delade länkar på mylinkshare page och länkar till sidan är inte tillgängliga för icke-admin-användare NPR-23044: Programfix för CQ-4239004
* För att förhindra ett null-pekarundantag i arbetsflödet för DAM-resursuppdatering i 6.4.0. NPR-24134: Programfix för CQ-4244972
* På den publicerade WCM-sidan visas platshållarikoner för hotspot, CSS-filer saknas med 403-fel för OTB-visningsprogram. NPR-23041: Programfix för CQ-4233716
* (Detaljvy) Navigeringsfunktionen Nästa/Bakåt lämnar en DIV-övertäckning i förhandsvisningsområdet för dynamisk återgivning som blockerar åtkomst till visningsprogrammet. NPR-23043: Programfix för CQ-4238499
* CMYK-bildåtergivningen har felaktig mättnad. NPR-23048: Programfix för CQ-4235470
* Extrahering av XMP-metadata av Scene7ListInfoProvider är resurskrävande. NPR-23754
* (dam-delivery) HTTP-vidarebefordraren respekterar inte HTTP-proxyinställningarna. NPR-24002: Programfix för CQ-4244140

**Sites**

* När vi byter namn på sidan när vi flyttar den, går det bra att flytta sidan, men namnbytet fungerar inte. NPR-22923: Programfix för CQ-4235907
* Fel vid publicering av en Live Copy-sida som pekar på en importsida i Adobe Campaigns. NPR-23053: Programfix för CQ-4237164
* Det går inte att flytta/byta namn i det klassiska användargränssnittet. Felmeddelandet&quot;Ett fel uppstod när sidan flyttades&quot; visas och namnet har inte ändrats. NPR-23051: Programfix för CQ-4235907
* När du växlar innehåll från kolumnvyn till listvyn återges en tom sida och ett Null-pekarundantag aktiveras för sidor med OffTime inställt och OnTime som tomt. NPR-22968, NPR-23052: Programfix för CQ-4238940

**Handel**

* Korrigera felande Hobbes-testfall (CQ/Commerce Module). Programfix för CQ-4253494

**Sårbarhet**

* Salesforce-integreringen är sårbar för SSRF (Server Side Request Forgery). NPR-24289: Programfix för CQ-4245277
* SSRF (Server Side Request Forgery) och XSS (Cross-Site Scripting) i ReportingServicesProxyServlet. NPR-24657: Programfix för CQ-4246880
* XSS (Cross-Site Scripting): Reflected in commerce createcatalogwizard.html/content. NPR-24642: Programfix för CQ-4237017
* XSS (Cross-site scripting) i Admin UI Project-länkar. NPR-23272: Programfix för CQ-4241795

**WCM - Foundation Components**

* Om du öppnar designväljaren genereras ett null-pekarundantag. NPR-23047: Programfix för CQ-4238736

**Användargränssnitt**

* (Coral3 Datepicker) Lägg till stöd för typeHint om du vill spara värden som &quot;String&quot;. NPR-23398: Programfix för Granite-21194
* Internationalisering fungerar inte på språknivå. NPR-22967, NPR-23046: Programfix för Granite-2111
* Proaktiv backport för granite.ui.commons-korrigeringar. NPR-23537
* Proaktiv backport för granite.ui.content fixes. NPR-23535
* Proaktiv backport för granite.ui.coralui-korrigeringar. NPR-23538
* Det går inte att ta bort flera användare från gruppen samtidigt. NPR-23846
* (OMEGA) Rapportera&quot;Funktion&quot; endast på engelska. NPR-23989: Programfix för Granite-21231
* (Designimporterare) Om du importerar en sida importeras inte js, css. NPR-25203: Programfix för Granite-2236

**Integrering**

* Resurslösaren är inte stängd i com.day.cq.analytics.sitecatalyst. NPR-22340: Programfix för CQ-4236515
* TargetContentImpl gör att AEM blir trögt under långa frågor. NPR-22359: Programfix för CQ-4236907
* Målmotorn (mbox.js, at.js) använder inte inbyggda URL:er och URL:er som innehåller kolon som kan misslyckas vid vissa distributioner. NPR-22434: Programfix för CQ-4237854
* I målläget kan författare ändra en komponent som ärvts från utkastet utan att avbryta arvet. NPR-22865: Programfix för CQ-4237907
* (Personalisering) Ikonerna deformeras när du växlar till kortvyn. NPR-23373, NPR-23374: Programfix för CQ-4240018, CQ-4240019
* (Personalisering) Målgruppskonsolen visar inte: mapptyper. NPR-23375: Programfix för CQ-4242293
* När en komponent är avsedd för en publiceringsinstans visas flimmer som visar standardupplevelsen före den valda. NPR-23415: Programfix för CQ-4242038
* (Adobe IMS Console) Tjänstkonfigurationen AccessTokenProvider OSGi visas igen efter borttagningen. NPR-23520: Programfix för CQ-4208250
* Konfigurationsreferensreplikeringen misslyckas med den mellanliggande mappstrukturen. NPR-23485: Programfix för CQ-4242751
* (Personalisering) clientlib blockeras av proxyservern. NPR-23521: Programfix för CQ-4240995
* (Adobe IMS Console) Registrerade molnlösningar hämtas inte upp i konfigurationsguiden. NPR-23977: Programfix för CQ-4244549
* Oändlig slinga när målinnehåll läses in på sidor utan HTML-tillägg. NPR-23522: Programfix för CQ-4223600
* Aktiveringen misslyckas för en sida med ärvda konfigurationsreferenser för dynamisk tagghantering. NPR-23485: Programfix för CQ-4242751

**Plattform**

* (Klassiskt användargränssnitt) (Touch-gränssnitt) Taggväljaren visas inte och ett undantag genereras när du försöker bläddra efter taggar via ett taggpredikat i resurssökningsschemat. NPR-23049: Programfix för CQ-4239371
* (Klassiskt användargränssnitt) Komponenter som använder xtype=taggar returnerar null och kan inte väljas i listan över taggar. NPR-23050: Programfix för CQ-4239937
* (Varumärkning) Dialogrutan för deltagande innehåller information om Adobe Marketing Cloud i stället för Adobe Experience Cloud. NPR-23210: Programfix för CQ-4237799
* Filteralternativet gör AEM trögt efter uppgradering från 6.3 till 6.4. NPR-24260: Programfix för CQ-4239847 (för kontroll)
* Proaktiv backport för korrigeringarna granite.omnisearch.core. NPR-23536
* Proaktiv backport för korrigeringar av platform.clientlibs. NPR-23569
* Cloud Service Config-arv brutet när andra sidegenskaper redigeras. NPR-23216: Programfix för CQ-4239782
* Aktiverat STARTTLS-stöd i Day CQ Mail Service. NPR-23941: Programfix för CQ-4240397

**Projekt**

* (Innehållsfragment) Språkkopia för inbäddad resurs skapas inte medan engelsk resurs läggs till i översättning. Programfix för CQ-4243477
* I den nedrullningsbara listan msft config visas config från /libs(6.4 configs) i stället för från /etc(6.3 configs) i äldre läge. Programfix för CQ-4243475
* Befordra och ta bort översättningsstarter automatiskt i översättningsprojekt. Programfix för CQ-4243474
* Innehållsfragment på webbplatser översätts inte. Programfix för CQ-4243482, CQ-4243483, CQ-4245687
* Serverfel vid öppning av översättningsjobbsökfilter. Programfix för CQ-4236813
* Listrutan för autentiseringskonfiguration är tom även om tif finns i /conf/we-retail. Programfix för CQ-4236315
* Öppna projekt-KPI: prestandaförsämringar när fler projekt skapas. NPR-23840: Programfix för CQ-4238392
* Arbetsflödesstartaren kan inte acceptera TypeHint-värdet för String. NPR-23863: Programfix för CQ-4238356

**Communities**

* Säkerhetsluckor i version 1.0 av Handlebars. NPR-23636: Programfix för CQ-4243055
* Det går inte att tillåta flaggade meddelanden gruppvis. NPR-23867: Programfix för CQ-4243962
* Standardvärdet visas inte för sorteringsknappen i forumkomponenten. NPR-23882: Programfix för CQ-4243375
* Problem med meddelandeleverans från communitysajter till grupper. NPR-23935

**Arbetsflöde**

* Day CQ Workflow Email Notification Service utlöser ett e-postmeddelande per Mongo-nod för WorkflowCompleted- och WorkflowAborted-meddelanden. NPR-22515: Programfix för CQ-4238172
* Om du kör arbetsflödet för DAM-uppdateringsresursen genereras ett NullPointerException. NPR-23010: Programfix för Granite-21096
* Arbetsflödesprocessteget visar inte skript från /etc/workflow/scripts. NPR-23263: Programfix för Granite-20775
* Arbetsflödets dynamiska deltagarsteg visar inte skript från /apps/workflow/scripts. NPR-23464: Programfix för Granite-21276
* Det går inte att redigera något arbetsflöde efter att ha redigerat det en gång. NPR-23742: Programfix för CQ-4238526
* (Klassiskt användargränssnitt) När arbetsflödet startas försvinner villkoren och arbetsflödena startar utan några villkor. NPR-23835: Programfix för CQ-4239153
* Projektinkorg: när du växlar till kalendervyn visas huvudinnehållet i inkorgen. NPR-23947: Programfix för CQ-4241236
* Nödvändig att visa nyttolastdetaljer i paketet så att HTML-komponenten kan visa värdet i listvyn. NPR-23948: Programfix för CQ-4240953
* Det går inte att lagra dialogdata i dialogdeltagarsteget. NPR-23965: Programfix för CQ-4234123
* (Touch-gränssnittet) När du sparar en arbetsflödesmodell ändras knappen Synkronisera till Synkroniserad vilket resulterar i ett stavfel. Programfix för CQ-4244843
* Projektinkorg: när du växlar till kalendervyn visas huvudinnehållet i inkorgen. Programfix för CQ-4244436
* Det går inte att välja dialogrutor i steg för dialogdeltagare. Programfix för CQ-4244532
* Proaktiv backport för korrigeringarna granite.omnisearch.core. NPR-23536
* Problem i Mobile Workspace App 6.4 med delad aktivitet. NPR-26383

**WCM - översättning**

* (Referenspanel) Översättningsjobb körs inte när projekt skapas. Programfix för CQ-4245327

**WCM - MSM**

* (MSM) Prestandaförbättring för utrullning. Programfix för CQ-4231488
* (MSM) Tidsgapet i händelseavlyssning mellan händelser som faktiskt inträffar och händelsehantering. Programfix för CQ-4227766

**Skärmar**

* Skärmsidan misslyckas med fel på grund av saknade beroenden för screens-core-pkg:1.4.42. Programfix för CQ-4245918

**Projekt - översättning**

* (Innehållsfragment) Språkkopia för inbäddad resurs skapas inte medan engelsk resurs läggs till i översättning. Programfix för CQ-4243477
* I den nedrullningsbara listan msft config visas config från /libs(6.4 configs) i stället för från /etc(6.3 configs) i äldre läge. Programfix för CQ-4243475
* Befordra och ta bort översättningsstarter automatiskt i översättningsprojekt. Programfix för CQ-4243474
* Innehållsfragment på webbplatser översätts inte. Programfix för CQ-4243482, CQ-4243483, CQ-4245687
* Serverfel vid öppning av översättningsjobbsökfilter. Programfix för CQ-4236813
* Listrutan för autentiseringskonfiguration är tom även om tif finns i /conf/we-retail. Programfix för CQ-4236315

**Hantering av innehållsfragment**

* När du tar bort komponentfyllningsloggar med stackspår. Programfix för CQ-4242315

**DAM - Allmänt**

* När du stänger detaljvyn för en resurs återgår den till en felaktig sökresultatsida. Programfix för CQ-4240960
* (Camera Raw) Bildjusteringsalternativet saknas. Programfix för CQ-4246121
* IndexOutOfBoundsException: OTB-rapport om resursändring. Programfix för CQ-4239744
* Ta bort konfidensgrad från rapport-csv. Programfix för CQ-4241491
* E-postleverans för länkdelning bruten för icke-admin-avsändare. Programfix för CQ-4240357
* Åtgärda IT-fel. Programfix för CQ-4249891

**DAM - varumärkesportal**

* Resursegenskaperna listar endast tre egenskaper på den första fliken, medan alla flikar ser tomma ut. Programfix för CQ-4242503
* Filtyps- och filstorlekspredikat är inte tillgängliga i publicerade sökformulär. Programfix för CQ-4242026
* Sökningen i katalogpredikatet ska filtreras bort eller inte visas i sökfiltren. Programfix för CQ-4241386
* Standardsökning från bör finnas efter avpublicering. Programfix för CQ-4241383, CQ-424113
* Publicera till varumärkesportalgester fungerar inte för bildförinställningar. Programfix för CQ-4241074
* Publicera på varumärkesportalen fungerar inte för samlingar. Programfix för CQ-4241122, CQ-4246558

**DAM - DM-klient**

* Om du uppgraderar till 6.4 tas tidigare skapade videokodningsprofiler bort. Programfix för CQ-4244067
* Attributet Alt-text är brutet i komponenten Dynamic Media. Programfix för CQ-4244081
* (DMS7) Redigering av fjärruppsättningar i AEM skrivs inte över i Scene7. Programfix för CQ-4243430
* Verifiering av 6.4 SP1-versionen på DM Hybrid. Programfix för CQ-4244623
* (DMS7-UA) När du klickar på knappen Bädda in för en publicerad videoresurs verkar ingenting hända. Dialogrutan Bädda in förväntas visas med HTML-kod. Programfix för CQ-4245237
* (DM Hybrid) Kopiera URL för publicerade videomaterial eller blandade mediamängder får &quot;[[object Object]&quot; i URL-dialogrutan. Programfix för CQ-4245236, CQ-4245451
* (DMHybrid) Videons detaljvysida innehåller inte förhandsgranskningen av videobasset och skickar ett felmeddelande till konsolen. Programfix för CQ-4244320
* Automatisk S7-kodning av webbutiksinnehåll. Programfix för CQ-4242253
* Förinställningarna för videobearbetning kan inte ha en ny förinställning för videokodning tillagd och inte heller redigera de befintliga kodningsförinställningarna. Programfix för CQ-4240407
* Förhandsuppgradera bildförinställningar visas som opublicerade på sidan Återgivningar och ger ingen URL. Programfix för CQ-4240406
* (CSS) Resurser visas - men de visningsprogram som används är standard och inte OTB-visningsprogram. Programfix för CQ-4239839
* Inaktiverade rensningssteg låstes manuellt och används av privata korallklasser. Programfix för CQ-4239729
* Bildvisningsprogrammet genererar ett fel och visar inte rätt smart beskärning. Programfix för CQ-4237564
* Äldre förinställning under /etc verkar vara bruten och inte migrerad till platsen under /conf när den sparas. Programfix för CQ-4237416
* Regression i OOB VideoViewer 5.8.x - visningsprogrammet expanderar iframe till höger och bryter därmed sidlayouten. Programfix för CQ-4235465
* (DMS7) Webbadress för återgivning med smart beskärning och knappen för inbäddning är aktiva för bilder som inte har publicerats. Programfix för CQ-4233696
* (DMHybrid) Återställ tidigare beskärnings-/rotationsfunktion. Programfix för CQ-4239489
* När du förhandsgranskar en video i kortvyn växlar uppspelningsknappen inte för att pausa. Programfix för CQ-4238592
* När du utför en Opt-In-uppgradering flyttas/kopieras inte YouTube-konfigurationen från den gamla platsen till den nya. Programfix för CQ-4238590
* DropTwo OTB AVS Video Processing Profiles are listed under Folder properties and only one contains defined encodings. Programfix för CQ-4238096
* (DMS7) Smart beskärning: Detaljvy: URL-knappen heter Kopiera-knapp för återgivningar. Programfix för CQ-4237804
* Visningsförinställningens listsida är tom även efter att du har kört rullningskommandona. Programfix för CQ-4243246
* Inaktiverade rensningssteg låste manuell körning och användning av privata korallklasser. Programfix för CQ-4239729
* Sidan med videorapportdetaljer visar inte videoresurser. Programfix för CQ-4246208

**DAM - DMServices**

* (DMS7) Molnkonfiguration: Det går inte att synkronisera nytt innehåll med Scene7 efter uppdatering till SP1. Programfix för CQ-4244437
* (DMHybrid) Färgprofiler och kataloginställningar registreras inte i ett debug_info=kataloganrop. Programfix för CQ-4242346
* Lägg till färgprofiler i kundinställningarna på leveransservrar. Programfix för CQ-4241818, CQ-4241819
* (DMHybrid) Efter 6.3 &amp;gt; 6.4-uppgraderingen. Kataloginställningarna flyttas till fel nod. Programfix för CQ-4239974, CQ-4239975
* (DMHybrid) Skript för push-visningsförinställningar skapar inte de noder som behövs för att ändra kataloginställningarna. Programfix för CQ-4240076
* När du använder listrutan Format och väljer antingen PNG- eller JPG-format, visas den hämtade filen som övermättad och mörkare än den ursprungliga resursen. Programfix för CQ-4240073
* (DMS7) Ta bort MIME-typmappningen: image_x-eps. Programfix för CQ-4240394
* (DMS7) Överföringsparametrar för blockerad bakgrund skickar inte ipsApiService.log och fungerar därför inte. Programfix för CQ-4240686
* Om du uppgraderar bildbearbetningsprofiler som skapats i en instans av version 6.3 till 6.4 bryts egenskapen Crop-type. Programfix för CQ-4237739
* (Dynamic Media) Det går inte att överföra reguljära resurser utanför mappen SmartCrop. Programfix för CQ-4237670
* Justera profilens reservkod för profilnamnet Adaptive Video Encoding till Adaptive_Video_Encoding. Programfix för CQ-4237666
* EmbedXMP-data anges alltid till&quot;active&quot; för Ptiff-genereringsprocessen. Programfix för CQ-4234498
* CMYK-bildåtergivningen har felaktig mättnad. Programfix för CQ-4235470
* Inställningarna för Image Server replikeras inte till leveransen medan replikeringsloggarna markerar att de lyckades. Programfix för CQ-4239480, CQ-4239046
* (DMS7) Det går inte att skapa uppsättningar med gamla/nya referenser till molnkonfigurationen. Programfix för CQ-4238078
* Scene7-arbetsflödessteget läser bara Scene7 i namnet och beskrivningen, men det förtydligar inte arbetsflödessteget i arbetsflödet för DAM-uppdatering. Programfix för CQ-4237865

**DAM - Smarta taggar**

* Nya förbättrade smarta taggar. NPR-21951

**Formulär**

AEM Forms-korrigeringar levereras via tilläggspaket och andra patch-installerare som medföljer releasen. Mer information finns i AEM Forms Releases.

De viktigaste nyheterna i AEM Forms är:

* AEM Forms har funktioner [](https://helpx.adobe.com/experience-manager/6-4/forms/using/transaction-reports-overview.html) för att spåra och hålla reda på transaktioner som skickade formulär, bearbetade dokument och återgivna dokument i era AEM Forms-installationer. Den ger insikter om produktanvändning och hjälper företagsanvändare att förstå digitala bearbetningsvolymer.
* PDF/UA har stöd för XML-formulär.
* Tillagd allowProxy = true för Clientlib **aemfd.ccm.channel.contentpage**
* Uppdaterad kod som gör avancerad titelsökning som innehåller i stället för lika.
* Uppdatera till en ny version av NPM (Node Package Manager) på datorn för kontinuerlig integrering.

**Formulärtilläggspaket**

**Integrering med backend**

* Ett fel genereras när null anges som ett värde för ett valfritt fält. NPR-24397
* WSDL-anrop misslyckas när elementet har ett annat namnområde än globalt namnutrymme. NPR-24281
* (FDM WSDL) Hämtar DermisException: Undantagslistdata för egenskapstypsmatris. NPR-24265
* (FDM WSDL) Hämtar DermisException: java.lang.Exception: createSOAPParam: Ogiltiga parametrar. NPR-24264
* (FDM Client SDK) Det går inte att utföra testning av förprocessor/efterprocessor och anpassad sändningsåtgärd. Programfix för CQ-4238469
* Korrigeringar för Javadoc-problem i Dermis. Programfix för CQ-4244250
* Förbättrade indata i WSDL (Web Services Description Language). Programfix för CQ-4244133
* Grundläggande autentiseringstestning för WSDL ger olika fel för samma konfiguration i AEM 6.3 och AEM 6.4. Programfix för CQ-4244132
* Begäran om att ta med ValueUtil i klient-sdk och javadocs. Programfix för CQ-4242803
* (FDM Cloud Config) Det går inte att konfigurera SOAP-baserad autentisering från molnkonfigurationen. Programfix för CQ-4238462
* Dermis - Lägg till saknade paket i Javadocs. Programfix för CQ-4242815
* WSDLInvokerParams som ska inkluderas i Forms Add-On-klientens SDK. NPR-23381: Programfix för CQ-4240233

**Adaptiva former**

* Dokumentåtergivning (IC) ska loggas som en transaktion med tjänsten Transaction Recording. Programfix för CQ-4245333
* När UAT5 körs saknas en post i PDF-filen som genererades vid verifieringsfasen. Programfix för CQ-4243184
* Testa om det finns en djup kopia av guideContext. Programfix för CQ-4242924
* Korrekturtypsfält saknas när UAT3 körs på den senaste uppgraderade servern. Programfix för CQ-4243120
* På en uppgraderad server saknar det inskickade formuläret de värden för delstat/provins/region och land som fanns på en server före uppgraderingen. Programfix för CQ-4241444
* (ExpressionEditor) Fel vid navigering till Verifiera scen under formuläröverföring. Programfix för CQ-4241384
* Värden saknas i verifieringsfasen på föruppgraderings- och uppgraderingsservern för det skickade formuläret. Programfix för CQ-4241896
* Knappen Avsluta och spara längst ned på sidan fungerar inte. Programfix för CQ-4240112
* Kontaktnummer saknas i den uppgraderade installationen. Programfix för CQ-4239870
* Under `ACTION TAKEN` avsnittet Tvisttyp på fliken Ytterligare dokument som stöder mitt anspråk har ytterligare fältet Korrekturtyp sparats. Programfix för CQ-4239873
* Fel i getDataAPI påträffades vid verifyPdf-steget. Programfix för CQ-4239865
* Fel i migreringsloggar för författare och publiceringsinstans. Programfix för CQ-4239365
* Fel i migreringsloggar för författare och publiceringsinstans. Programfix för CQ-4239635
* Deserialiseringsfel som &quot;Deserialization not allowed for class sun.util.calendar.ZoneInfo&quot; i felloggarna efter att ett adaptivt formulär har skickats. Programfix för CQ-4240419
* Tillståndsfältet fylls inte i i Mobile-formuläråtergivningen. Programfix för CQ-4240597
* Ta bort referensanvändning av komponenter i mallar från antimönsterlistan. Programfix för CQ-4239217
* Numeriska rutor i HTML5 som flyttal eller decimaltal ger olika valideringsresultat i olika webbläsare. NPR-23528: Programfix för CQ-4244097
* (Bildöverföring) Bilden visas inte i DOR-förhandsvisning. Programfix för CQ-4243178
* JEE-servern genererar ett fel när den försöker skicka det adaptiva formuläret med e-post-PDF och Inkludera bilagor. Programfix för CQ-4239894
* Diagrammet ritas inte vid körning med tabell/panel. Programfix för CQ-4240010
* Det går inte att skicka anpassade formulär och det går inte att ändra antalet transaktioner på grund av att överföringen misslyckades. Programfix för CQ-4246125
* (Bildval) Dokumentet med postalternativ är inte synligt. Programfix för CQ-4236976
* Mallredigerarens användargränssnitt är inte stabilt. Programfix för CQ-4241497
* AF-filer visas inte med fliken Resurser på sidopanelen när de visas med bläddringsalternativet för dialogrutan för AEM-formulärkomponentegenskaper. Programfix för CQ-4236751
* Det arbetsflödes-ID som genereras för formulärkonvertering ska vara tillgängligt i det genererade adaptiva formuläret. Programfix för CQ-4240014
* Det går inte att välja en mall för att skapa en sida på webbplatser med direktuppgradering: LiveCycle till 6.4-server. Programfix för CQ-4241300

**Assembler Service**

* Transaktionsloggning i Assembler Services. Programfix för CQ-4245018, CQ-4245017, CQ-4245016.
* Transaktionen rapporteras inte när PDF/A-konvertering görs med DDX. Programfix för CQ-4246039

**Forms Manager**

* FM:s Knapplista SKAPAS om du vill sortera i bokstavsordning. Programfix för CQ-4242307

**Formulärportal**

* Utkast som har sparats på en föruppgraderingsserver öppnas inte korrekt på en uppgraderad server. Programfix för CQ-4243303
* Versionsuppdatering till 7.1 för adobe-formsmanager-core-module. Programfix för CQ-4245753
* Utkast som har sparats på en föruppgraderingsserver öppnas inte korrekt på en uppgraderad server. Programfix för CQ-4243303
* Scenen med bifogade filer kraschar vid ersättning/tillägg/borttagning av bilagor i nya instanser/samma utkastinstans. Programfix för CQ-4243165
* Antalet utkast som har hämtats från databasfrågor är större än antalet utkast i portalen. Programfix för CQ-4241489
* Formulär som skickas på en föruppgraderingsserver finns inte på en uppgraderad server. Programfix för CQ-4241490
* Formuläret som visas i användargränssnittet på fliken för att skicka in är i ett tillstånd som inte har skickats trots att det har skickats. Programfix för CQ-4241487
* GuideContext ska formas genom att djupt kopiera fälten som guideContext innehåller customPropertyMap som i sig är ett objekt. Programfix för CQ-4240126
* Fel vid försök att spara ett formulär. Programfix för CQ-4240763
* Posten för sparade och inskickade formulär fylls i i crx/de trots att vi har en DB-konfiguration som anges i formulärportalens utkast- och inskickningskonfiguration. Programfix för CQ-4240726
* (Sök och visa) Det avancerade fasta värdet för sökrubrik ska fungera som innehåller i stället för lika. Programfix för CQ-4245499

**Mobilformulär**

* Datumfältet överlappar i mobilformulär. Programfix för CQ-4242256
* Formulärinlämning för mobilformulär ska loggas som en transaktion med transaktionsregistreringstjänsten. Programfix för CQ-4246166
* Formulärinlämning i Formset ska loggas som en transaktion med Transaction Record Service. Programfix för CQ-4246165

**AEM Forms App**

* (Windows App) Det går inte att återge formuläret. Programfix för CQ-4238005

**Arbetsflöde OSGI**

* Transaktionsloggning i Tilldela uppgift för arbetsflöde. Programfix för CQ-424440
* (FDM-steg) Det går inte att använda värden från arbetsflödets metadata när steget Tilldela uppgift infogas mellan processsteget och fdm-steget. Programfix för CQ-4241472
* Delegering av tilldelningsuppgifter fungerar inte i Forms-integrering i OSGI-arbetsflöden. NPR-23709: Programfix för CQ-4243700
* (Arbetsflödesmodellredigerare) Vissa arbetsflödesmodeller kan inte redigeras via ClassicUI WF-modellredigeraren. Programfix för CQ-4241151

**MultiChannel-dokument**

* Datumfältet i mallen överlappar delformuläret i IC-redigeringen. Programfix för CQ-4240110
* Sidhuvudet får inte tas bort eller flyttas upp och ned vid redigering av konc-webbkanaler. Programfix för CQ-4243358
* (IC Editor) Standardrader anges till 1 för tabellkomponenter. Programfix för CQ-4244848
* Målområdet förblir synligt även när innehållet har dragits och släppts på det. Programfix för CQ-4244534
* Webbkanalen känner inte igen tabbar i textdokumentfragment. Programfix för CQ-4244481
* (Utskriftskanal) Dokumentåtergivning (IC) ska loggas som en transaktion med tjänsten Transaction Recording. Programfix för CQ-4245335
* (Webbkanal) Dokumentåtergivning (IC) ska loggas som en transaktion med tjänsten Transaction Recording. Programfix för CQ-4245334
* Dokumentbehållarsökningen eller datamodellträdssökningen måste vara enhetlig med resursfiltersökningen. Programfix för CQ-4242305
* (Dokumentfragment) Egenskapen indentation drar in texten med hur mycket enheter som inte kan tolkas. Programfix för CQ-4241082, CQ-4240643
* (IC Editor) Ikonen Redigera fragment på dokumentfragmentets panel som listas på fliken Resurser är inte så lätt att identifiera och förstå. Programfix för CQ-4241047
* Tillåt anonym åtkomst till IC Anonymous inaccessible client library. Programfix för CQ-4245588
* (Webbkanal) Data tolkas inte i någon av tabellerna i webbförhandsvisningen och visas som tomma. Programfix för CQ-4244476
* Tabellrubriker visas som variabler i webbkanaler vid automatisk generering. Programfix för CQ-4244242
* (IC Editor) Innehållet i ett dokumentfragment som används i en konc bör storleksändras automatiskt så att det passar bredden på målområdet. Programfix för CQ-4244094
* Kanalnamnet som visas i överkanten i mitten måste vara konsekvent för antingen IC-titel för WEB/PRINT. Programfix för CQ-4242498
* Textredigerarens dataobjektpanel ska endast innehålla entiteter på den översta nivån, snabbkorrigering för CQ-4244121
* Standardnamn tilldelas inte när en ny komponent läggs till i redigeraren. Programfix för CQ-4244691
* Lägga till Colspan-konfiguration i alla webbkanalskomponenter. Programfix för CQ-4244946
* Egenskapen för tabellbredd för layoutfragment återställs inte och respekteras inte i Letter- eller Customer Communication Print Channel. Programfix för CQ-4241574

**Korrespondenshantering**

* Bildtexter som tagits bort från bokstavsmallen efter redigering av en textresurs som innehåller platshållare. NPR-24196
* När XDP-filen överförs och används som layout för brevmallar går det inte att förhandsgranska eller redigera mallarna. NPR-24143: Programfix för CQ-4244407
* Tilldelningsmarkering är som standard markerat i listfragment. Programfix för CQ-4240097
* Villkorsredigerare - Flera resultatutvärderingar ska vara aktiverade som standard. Programfix för CQ-4240096
* Bild som tas bort från List visar fortfarande bilden i förhandsvisning. Programfix för CQ-4239909
* Regeln som anges i villkorsmodulen är inställd som &#39;Standard&#39; för alla moduler. Programfix för CQ-4239878
* Det går inte att skapa datamordlistan med felet&quot;Okänt JCR-undantag&quot;. Programfix för CQ-4244122
* Gaps in 6.3 Content JavaDocs. Programfix för CQ-4213586

**Formulär-JEE-installationsprogram**

**Core**

* (HTML-arbetsyta) Spårningsinformation saknas för program med parentessymbol i namnet. NPR-23402

**PDFG-tjänst**

* Transaktionsloggning i PDFG-tjänster. Programfix för CQ-4244951, CQ-4244586
* Reducera PDF-filer genom att selektivt frigöra teckensnitt via ett enda API-anrop. NPR-23287
* Problem med uppdatering av PDFG-konfigurationer vid AEM-uppgradering. Programfix för CQ-4241176
* Transaktionsloggning i PDFUtility Service. Programfix för CQ-4245014

**Processhantering**

* (HTML-arbetsyta) Processstartpunkter sorteras inte i alfanumerisk ordning. Programfix för CQ-4239629
* (HTML-arbetsyta) Förbered dataanrop som kommer upp två gånger när utkastet öppnas första gången. Programfix för CQ-4243280
* (HTML-arbetsyta) Förbered data-processen utlöses när ett formulär stängs. Programfix för CQ-4239456
* Arbetsytan hänger sig när du går mellan två uppgifter. Programfix för CQ-4237125

**Workbench**

* Hantera dataprocessen Förbered för åtgärdsprofil misslyckas när standardkonfigurationen för återgivningsprocessen är inställd på HTML. Programfix för CQ-4244292

**Forms Designer**

* Stöd för PDF/UA i XML-formulär som genererats via Designer och Output Service. NPR-23022
* Textbundna hyperlänkar som definieras i Designer taggas inte och de har ingen alternativ text när de sparas som PDF från Designer. NPR-23023

**Funktionspaket ingår**

**Assets**

* Förbättrade funktioner för smarta taggar. Mer information finns i [Förbättrade smarta taggar](https://helpx.adobe.com/experience-manager/6-4/assets/using/enhanced-smart-tags.html). NPR-21951: Programfix för CQ-4234883
* Referenser till AEM Resurser introducerades i InDesign. Mer information finns i Referenser till [AEM-resurser i InDesign](/help/assets/managing-linked-subassets.md). NPR-23386

**Sites**

* (Sidredigering) Förbättringar i bildredigeraren. Mer information finns i [Bildredigeraren](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/image-editor.html). NPR-24267: Programfix för CQ-4245502

**OSGI-paket och innehållspaket som ingår**

Följande text innehåller en förteckning över OSGI-paket och innehållspaket som ingår i den gemensamma fiskeripolitiken.

Lista över OSGi-paket som ingår i AEM 6.4.1.0

[Hämta fil](assets/6_4_1_0_bundle-list.txt)

Lista över innehållspaket som ingår i AEM 6.4.1.0

[Hämta fil](assets/6_4_1_0_content-package-list.txt)

### Installera 6.4.8.0 {#install}

#### Installationskrav {#setup-requirements}

<!--

>[!NOTE]
>
>For successful installation of AEM 6.4.6.0 on the instance, it is strongly recommended to upgrade the version of com.adobe.granite.oak.s3connector to 1.8.4 for the customers who are on the older version of s3 connector.
>The process of upgrading the com.adobe.granite.oak.s3connector is available at [https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html](https://helpx.adobe.com/in/experience-manager/6-4/sites/deploying/using/data-store-config.html).
>Download the latest version of com.adobe.granite.oak.s3connector from: [https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/](https://repo.adobe.com/nexus/content/groups/public/com/adobe/granite/com.adobe.granite.oak.s3connector/)

-->

>[!CAUTION]
>
>För kunder med funktionspaket installerade på AEM 6.4. Valfria funktionspaket från Adobe är beroende av releaseversionen och Service Pack. Om du har något funktionspaket installerat kontaktar du AEM Customer Care-teamet för att kontrollera om dessa funktionspaket är kompatibla med detta Service Pack för AEM 6.4.

* AEM 6.4.8.0 kräver AEM 6.4. Mer information finns i [uppgraderingsdokumentationen](../sites-deploying/upgrade.md) .
* Nedladdningen av Service Pack finns på Adobe Package Share, som du kommer åt direkt från AEM 6.4-instansen.
* På en distribution med MongoDB och flera instanser installerar du AEM 6.4.8.0 på en av Author-instanserna med hjälp av Package Manager.
* Innan du installerar Service Pack bör du kontrollera att du har en ögonblicksbild eller en ny säkerhetskopia av AEM-instansen.
* Starta om instansen innan du installerar den. Detta behövs bara när instansen fortfarande är i uppdateringsläge (och detta är fallet när instansen precis uppdaterades från en tidigare version), men rekommenderas vanligtvis om instansen kördes under en längre tidsperiod.

>[!NOTE]
>
>Adobe rekommenderar inte att du tar bort eller avinstallerar AEM 6.4.8.0-paketet.

### Installera Service Pack via paketresurs {#install-the-service-pack-via-package-share}

Så här installerar du Service Pack på en befintlig AEM 6.4-instans:

1. Logga in på Package Share within AEM eller direkt från webbläsaren och ladda ned AEM 6.4.8.0-paketet.

   (sök efter&quot;AEM-6.4.8.0&quot;)
1. Installera det hämtade paketet med hjälp av Package Manager.

>[!NOTE]
>
>**Dialogrutan för Package Manager-gränssnittet avslutas ibland på ett felaktigt sätt under installationen av 6.4.8.0**
>
>Därför rekommenderar vi att du väntar på att felloggarna ska stabiliseras innan du får åtkomst till instansen. Användaren måste vänta på specifika loggar som rör avinstallation av uppdateringspaketet innan den kan vara säker på att installationen lyckas. Det händer vanligtvis på Safari, men kan hända i olika webbläsare.

### Automatisk installation {#auto-installation}

Det finns två sätt att automatiskt installera AEM 6.4.8.0 i en instans som körs:

S. Placera paketet i ..*/crx-quickstart/install* -mappen när servern körs. Paketet installeras automatiskt.

B. Använd [HTTP-API:t från Package Manager](https://docs.adobe.com/content/docs/en/crx/2-3/how_to/package_manager.html) - kontrollera att du använder `cmd=install&recursive=true` - så att det kapslade paketet installeras.

>[!NOTE]
>
>AEM 6.4.8.0 stöder inte Bootstrap-installation.

### Validera installation {#validate-install}

1. Produktinformationssidan (*/system/console/ productinfo *) ska nu visa den uppdaterade versionssträngen &quot;Adobe Experience Manager, version 6.4.8.0&quot; under Installerade produkter.
1. Alla OSGI-paket är antingen AKTIVA eller FRAGMENT i OSGI-konsolen (Använd webbkonsolen: /system/console/bundles).
1. OSGI-paketet org.apache.jackrabbit.oak-core finns i version 1.8.17 eller senare (Använd webbkonsol: /system/console/bundles).

Information om den certifierade plattformen för körning med den här versionen av AEM Sites and Assets finns i [Tekniska krav](../sites-deploying/technical-requirements.md).

>[!Note]
>När paketet har installerats visas ett >informativt meddelande som anger att innehållet >package har installerats, t.ex. **&quot;Content Package AEM-6.4-Service-Pack-7 har installerats korrekt.&quot;**

### Uppdatera dynamiska medievyer (5.10.1) {#update-dynamic-media-viewers}

<p id="Dynamic">AEM 6.4.8.0 innehåller en ny version av Dynamic Media Viewer (5.10.1) som gör det möjligt att söka efter dubblettnamn på sidan Bildförinställning. Dynamic Media-kunder rekommenderas att köra följande kommando för att få fram aktuella visningsinställningar från kartongen.

`curl -u admin:admin http://localhost:4502/libs/settings/dam/dm/presets/viewer.pushviewerpresets`

som kopierar nya visningsförinställningar till /conf-platsen.

### Installera tilläggspaket för AEM-formulär {#install-aem-forms-add-on-package}

#### Installera tillägget AEM-formulär {#installaemformsaddon}

>[!NOTE]
>
>Hoppa över om du inte använder AEM Forms. Korrigeringar i AEM Forms levereras via ett separat tilläggspaket.

>[!NOTE]
>
>AEM 6.4.8.0 innehåller en ny version av [AEM Forms-kompatibilitetspaketet](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/cq640/compatpack/AEM-FORMS-6.4.7.0-COMPAT). Om du använder en äldre version av AEM Forms Compatibility Package och uppdaterar till AEM 6.4.8.0 installerar du den senaste versionen av AEM Forms-kompatibilitetspaketet efter installationen av Forms Add-On Package.

1. Kontrollera att du har installerat AEM Service Pack.
1. Ladda ned motsvarande tilläggspaket för formulär i [AEM Forms-versioner](https://helpx.adobe.com/aem-forms/kb/aem-forms-releases.html) för ditt operativsystem.
1. Installera tilläggspaketet för formulär enligt beskrivningen i [Installera tilläggspaket](https://helpx.adobe.com/experience-manager/6-4/forms/using/installing-configuring-aem-forms-osgi.html#InstallAEMFormsaddonpackage)för AEM-formulär.

### Installera JEE-installationsprogrammet för AEM Forms {#install-aem-forms-jee-installer}

>[!NOTE]
>
>Hoppa över om du inte använder AEM Forms på JEE. Korrigeringar i AEM Forms JEE levereras via ett separat installationsprogram.

Information om hur du installerar det kumulativa installationsprogrammet för AEM Forms JEE och konfigurationen efter distributionen finns i [AEM Forms JEE Patch Installer 0015](https://helpx.adobe.com/aem-forms/quick-fixes/6-4/jee-patch-0015.html).

#### Konfigurationsinställningar som krävs för NPR-21268 {#configuration-settings-required-for-npr}

Om du använder klassiskt (gammalt) gränssnitt och har skapat metadatamallar med hjälp av det följer du stegen för att köra JMX-skriptet för att bevara dem -

1. Gå till /system/console/jmx.
1. Klicka på&quot;Migrera metadatamallar&quot;.
1. Klicka på&quot;migrateMetadataTemplatesAtPath&quot; och ange den mappsökväg där du vill att metadatamallarna ska bevaras.

#### Konfigurationsinställningar som krävs för NPR-24536 {#configuration-settings-required-for-npr-1}

Antalet delade köer uppdateras inte som standard för andra användare när en användare gör anspråk på en uppgift. För detta har vi infört en ny fastighet. Följ stegen nedan för att konfigurera den här egenskapen på din AEM-instans:

1. Gå till Admin UI -> Tjänster -> Arbetsyta -> Global administration.
1. Exportera globala inställningar.
1. I den hämtade XML-filen lägger du till taggen &lt;client_tasksPollingInterval>10&lt;/client_tasksPollingInterval> Här är 10 exempelvärdet i sekunder. Du kan ändra den därefter.
1. Spara filen.
1. Gå tillbaka till Admin UI -> Tjänster -> Arbetsyta -> Global administration.
1. Importera XML-filen i avsnittet Importera globala inställningar.
1. Du kan nu logga ut från systemet och logga in igen.
1. Antalet delade köer börjar uppdateras för andra användare på arbetsytan.
1. Om du vill stänga av avsökningen ändrar du värdet till 0 och importerar XML-filen igen.

### Uber Jar {#uber-jar}

Uber Jar för AEM 6.4.8.0 finns i [Adobe Public Maven-databasen](https://repo.adobe.com/nexus/content/groups/public/com/adobe/aem/uber-jar/6.4.8/).

Om du vill använda Uber Jar i ett Maven-projekt kan du läsa artikeln [Så här använder du Uber jar](../sites-developing/ht-projects-maven.md) och inkludera följande beroende i projektstrukturen:

```shell
<dependency>
      <code>com.adobe.aem</groupId>
      <artifactId>uber-jar</artifactId>
      <version>6.4.8</version>
      <classifier>apis</classifier>
      <scope>provided</scope>
</dependency>
```

### Borttagna/inaktuella funktioner {#removed-deprecated-features}

I det här avsnittet listas funktioner som har tagits bort eller tagits bort från AEM 6.4.

| Yta | Funktion | Ersättning | Version |
|---|---|---|---|
| Assets | Hantera taggåtgärd för underresurser | Ingen ersättning | AEM 6.4.2.0 |
| Resurser och integrering med Adobe Creative Cloud | [AEM till Creative Cloud-mappdelning](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/creative-cloud.html) introducerades i AEM 6.2 som ett sätt att ge kreativa användare tillgång till resurser från AEM. En ny funktion i Creative Cloud-programmet, Adobe Asset Link, ger en mycket bättre användarupplevelse och kraftfullare åtkomst till resurser från AEM direkt inifrån Photoshop, InDesign och Illustrator. Adobe kommer inte att göra ytterligare förbättringar av mappdelningsfunktionen. Funktionen ingår i AEM, men vi rekommenderar att man använder ersättningsfunktionen. | Adobe Asset Link eller datorprogram. Mer information finns i [artikeln om integrering](/help/assets/aem-cc-integration-best-practices.md) av AEM Creative Cloud. | AEM 6.4.4.0 |

### Kända fel {#known-issues}

* Följande fel och varningar kan visas under installationen:

   * Fel vid skapande av komponentinstans och Service factory returnerade null på grund av databasomstart:

      * com.day.cq.cq-personalization \[com.day.cq.pesonalization.impl.DefaultProfileProvider(938)\] Det går inte att skapa komponentinstansen eftersom det inte gick att binda referensprofileManager
      * org.apache.sling.Commons.eduler FrameworkEvent ERROR (org.osgi.framework.ServiceException: Servicefabriken returnerade null. (Komponent: com.day.cq.tagging.impl.TagGarbageCollector (1687))
   * `com.adobe.cq.social.cq-social-jcr-provider bundle com.adobe.cq.social.cq-social-jcr-provider:1.3.5 (395)[com.adobe.cq.social.provider.jcr.impl.SpiSocialJcrResourceProviderImpl(2302)]` : Tidsgränsen överskreds i väntan på att reg.ändringen skulle slutföras utan registrering.
   * `com.adobe.granite.maintenance.impl.TaskScheduler` Inga underhållsfönster hittades vid granit/drift/underhåll
   * `com.adobe.cq.com.adobe.cq.ui.commons bundle com.adobe.cq.com.adobe.cq.ui.commons:1.2.28 (204)[com.adobe.cq.ui.wcm.commons.internal.servlets.rte.RTEFilterServletFactory(573)]`: Metoden unbindChange har utlöst ett undantag (java.lang.IllegalStateException: Tjänsten har redan avregistrerats.)
Dessa fel kräver inga åtgärder eftersom de inte påverkar AEM-instansen.


### Lösta problem {#resolved-issues}

**AEM 6.4.4.0**

* Det finns inget fel för resursen när metadata importeras/exporteras. CQ-4253263
* Det går inte att redigera bildkomponenter och sidegenskaper efter att du har använt 6.4.3.0 ovanpå 6.4.2.0. CQ-4260316 &amp; CQ-4260441För att lösa problemet:
   * Gå till Pakethanteraren
   * Installera om paketet &quot;cq-ui-wcm-admin-content-1.0.1004.zip&quot;
   * Kompilera om alla JSP:er `(http://<AEM HOST>:<AEM PORT/system/console/slingjsp)` ELLER Starta om instansen.

### OSGi-paket och innehållspaket som ingår {#osgi-bundles-and-content-packages-included}

Följande textdokument listar de OSGi-paket och innehållspaket som ingår i AEM 6.4.8.0.

Lista över OSGi-paket som ingår i AEM 6.4.8.0

[Hämta fil](assets/6.4.8.0_osgi_bundles.txt)

Lista över innehållspaket som ingår i AEM 6.4.8.0

[Hämta fil](assets/6.4.8.0_content_packages.txt)

### Användbara resurser {#helpful-resources}

* [Versionsinformation om AEM 6.4](../release-notes/release-notes.md)
* [AEM - produktsida](https://www.adobe.com/solutions/web-experience-management.html)
* [AEM 6.4-dokumentation](https://helpx.adobe.com/support/experience-manager/6-4.html)
* Prenumerera på [Adobe Priority-produktuppdateringar](https://www.adobe.com/subscription/priority-product-update.html)

### Begränsade platser {#restricted-sites-new}

Dessa webbplatser är bara tillgängliga för kunder. Om du är kund och behöver åtkomst kontaktar du din kontoansvarige på Adobe.

* [Nedladdning av produkt på licensing.adobe.com](https://licensing.adobe.com/)
* [Kontakta kundsupport](https://daycare.day.com/)
