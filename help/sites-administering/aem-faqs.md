---
title: Vanliga frågor om AEM
seo-title: Vanliga frågor om AEM 6.4
description: Använd de här vanliga frågorna för att förstå, konfigurera och felsöka vanliga arbetsflöden och problem i AEM.
seo-description: Använd de här vanliga frågorna för att förstå, konfigurera och felsöka vanliga arbetsflöden och problem i AEM.
uuid: af197bcc-2c61-4c64-b781-f24d83c27c82
contentOwner: jsyal
discoiquuid: c66b65af-443f-4fc2-b775-9f4e3c60285a
translation-type: tm+mt
source-git-commit: f5b45b2c8bfcf9d82ddc08b05b5fff22937fa9fd

---


# Vanliga frågor om AEM{#aem-faqs}

Följ den här sidan för att få svar på några problem med AEM-felsökning och konfiguration.

## Sites {#sites}

### Hur konfigurerar jag binär distribution? {#how-do-i-configure-binary-less-distribution}

Binär distribution stöds för distributioner via ett delat datalager och innefattar agenter som utnyttjar exporteraren för det vaultbaserade distributionspaketet (standard-PID: `org.apache.sling.distribution.serialization.impl.vlt.VaultDistributionPackageBuilderFactory`) package builder.

När det binära läget är aktiverat innehåller de distribuerade innehållspaketen referenser till binära filer i stället för till de faktiska binära filerna.

### Hur aktiverar jag binär distribution? {#how-do-i-enable-binary-less-distribution}

Om du vill aktivera binär distribution distribuerar du med ett delat blobarkiv.\
Kontrollera `useBinaryReferences` egenskapen i OSGI-konfigurationen med det fabriks-PID ( `org.apache.sling.distribution.serialization.impl.vlt.VaultDistributionPackageBuilderFactory`*)*som din agent använder.

### Hur kan jag anpassa felmeddelandena när jag navigerar i sidhierarkin i AEM-webbplatskonsolen? {#how-can-i-customize-the-error-messages-while-navigating-page-hierarchy-in-aem-sites-console}

Kontrollera nätverkspanelen (i Chrome-webbläsaren) där en personlig konfiguration (JS inte har miniatyrbildats).

Visa kolumnen för att ta reda på vilken som initierade en begäran `Initiator` . Den innehåller filerna och radnumren som AJAX-anropen görs från. Senare kan du spåra felhanteringsfunktionen och ändra felmeddelandet efter dina behov.

### Hur aktiverar man behörigheter när man skapar en språkkopia för innehållsförfattare i AEM? {#how-to-enable-permissions-while-creating-language-copy-for-content-authors-in-aem}

Innehållsförfattare måste ha behörighet på `/content/projects` plats för att kunna skapa en språkkopieringsfunktion.

Om man också behöver hantera projekt av författare är lösningen att lägga till författaren i `project-administrators` gruppen.

### Hur ändrar du format när du skapar en språkkopia för ett projekt? {#how-to-change-the-format-while-creating-language-copy-for-a-project}

Skapa en språkrot och en språkkopia i roten innan du skapar ett översättningsprojekt.

Exempel:\
Skapa en språkrot på `/content/geometrixx` med namnet som `fr_LU` (och titeln som franska (Luxemburg)). Skapa sedan en språkkopia av sidan på referenspanelen och navigera till `Create structure only` alternativet i `Create & Translate`. Skapa slutligen ett översättningsprojekt och lägg sedan till språkkopian i översättningsjobbet.

Mer information finns i de andra resurserna nedan:

* [Förbereda innehåll för översättning](/help/sites-administering/tc-prep.md)
* [Hantera översättningsprojekt](/help/sites-administering/tc-manage.md)

### Hur granskar man AEM-funktioner som inloggningsförsök och ACL eller behörighetsändringar? {#how-to-audit-aem-capabilities-such-as-login-attempts-and-acl-or-permission-changes}

AEM har introducerat möjligheten att logga administrativa ändringar för bättre felsökning och granskning. Som standard loggas informationen i `error.log` filen. För att underlätta övervakningen rekommenderar vi att de dirigeras om till en separat loggfil.\
Mer information om hur du omdirigerar utdata till en separat loggfil finns i [Granska användarhanteringsåtgärder i AEM](/help/sites-administering/audit-user-management-operations.md).

### Hur aktiverar jag SSL som standard? {#how-to-enable-ssl-by-default}

Adobe Experience Manager (AEM) 6.4 levereras med SSL-guiden och har ett användargränssnitt för att konfigurera Jetty och Granite Jetty SSL-stöd.

Information om hur du aktiverar SSL finns i [SSL som standard](/help/sites-administering/ssl-by-default.md).

### Vilken är den rekommenderade arkitekturen när man använder AEM:s Content Services från en mobilapp, ideally React Native? {#what-is-the-recommended-architecture-when-using-aem-s-content-services-from-a-mobile-app-ideally-react-native}

Content Services är baserat på Sling Models och AEM-utvecklarna måste tillhandahålla en Sling Model pojo för varje komponent som exporteras.

Mer information om hur du använder AEM-innehållstjänster från ett React-program finns i [Självstudiekursen Kom igång med AEM Content Services](https://helpx.adobe.com/experience-manager/kt/sites/using/content-services-tutorial-use.html) .

Om utvecklarna vill exportera ett träd med komponenter kan de också implementera `ComponentExporter` - och `ContainerExporter` gränssnitten samt använda `ModelFactory` för att iterera över de underordnade komponenterna och returnera sin modellbeteckning. Se resurserna nedan:

[1] [Adobe-Marketing-Cloud/aem-core-wcm-components](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/blob/master/bundles/core/src/main/java/com/adobe/cq/wcm/core/components/internal/models/v1/PageImpl.java#L245)

[2] [Apache Sling:Sling Models](https://sling.apache.org/documentation/bundles/models.html)

### Hur inaktiverar man popup-fönstret för AEM 6.4-undersökningen? {#how-to-disable-aem-survey-pop-up}

Du kan välja att samla in användningsstatistik med hjälp av Touch-gränssnittet eller webbkonsolen. Mer information finns i [Välja in i aggregerad användningsstatistik](/help/sites-deploying/opt-in-aggregated-usage-statistics.md).

### Finns det någon bra resurs som sätter fokus på de viktigaste funktionerna för uppgradering till AEM 6.4? {#is-there-a-good-resource-that-highlights-the-key-features-for-upgrading-to-aem}

Se [Förstå anledningar att uppgradera AEM](https://helpx.adobe.com/experience-manager/kt/platform-repository/using/upgrade-aem-article-understand.html) som beskriver en högnivåuppdelning av nyckelfunktioner för kunder som funderar på att uppgradera till den senaste versionen av Adobe Experience Manager.

### Hur konfigurerar jag en AEM-instans så att den använder PorterStem-filtret? {#how-to-configure-an-aem-instance-to-use-the-porterstem-filter}

Filtret PorterStem använder algoritmen för Porter Stemming för engelska. Resultatet liknar att använda Snowball Porter-temmer med argumentet *language=&quot;English&quot;* . Men den här stammen kodas direkt i Java och baseras inte på Snowball. Den godkänner inte en lista med skyddade ord och passar bara för engelsk text.

Oak visar en uppsättning lucene-provides analyzer-konfigurationselement som kan användas i AEM. Mer information om hur du använder filter finns i **Apache Oak Analyzers** i [Simple search Implementation Guide](https://helpx.adobe.com/experience-manager/kt/sites/using/search-tutorial-develop.html).

### Hur omindexerar man helt? {#how-to-perform-a-full-re-indexing}

Omindexering bör alltid ske med vederbörlig hänsyn tagen till hur den påverkar AEM:s totala prestanda och utföras under perioder med låg aktivitet eller underhållsperioder.

Läs [Bästa praxis för frågor och indexering](/help/sites-deploying/best-practices-for-queries-and-indexing.md) om du vill veta varför du indexerar om.

### Stöder vi minifierade JS-libs i Design Importer? {#do-we-support-minified-js-libs-in-design-importer}

Du måste ändra standardegenskapen för JS-processorn för HTML-bibliotekshanteraren i Adobe Granite till ***min:gcc***. För att kunna importera designpaketet rekommenderar vi att du inkluderar förminifierade bibliotek från tredje part i våra bibliotek på klientsidan.

## Assets {#assets}

### Varför upprepas arbetsflödet Resurser när MP4-filer överförs (till exempel med metoden dra och släpp)? {#why-the-assets-workflow-repeats-itself-while-uploading-mp-files-for-example-using-drag-and-drop-method}

Om användaren inte har borttagningsbehörighet under objektnoden när de överför filmfilerna misslyckas borttagningssegmentnoderna och överföringen startas om.

### Hur många digitala resurser kan användas med AEM 6.4 i taget? {#what-is-the-maximum-number-of-digital-assets-that-can-be-operated-with-aem-at-a-time}

Med Adobe Experience Manager (AEM) 6.4 kan du överföra upp till 2 GB resurser i taget.

Mer information om maximalt antal resurser som kan användas med AEM 6.4 finns i [Handbok](/help/assets/assets-sizing-guide.md)för resursstorlek.

### Vilka är standardinställningarna för OTB-konfigurationer när du skapar en språkkopia? {#what-are-the-default-settings-for-ootb-configurations-while-creating-language-copy}

När du skapar språkkopior med hjälp av det klassiska användargränssnittet flyttas resurser inte under den nya språkhierarkin utan används från språkinställningen.

När du skapar en språkkopia med Touch-gränssnittet (**Referenser** -> **Uppdatera språkkopia**) skapas en ny DAM-mapp under det nya språket och resurser refereras därifrån.

Det här är standardinställningen för OTB-konfigurationer. Du kan ställa in **Översätt sidresurser** = **Översätt** inte i översättningskonfigurationer.\
För AEM 6.4, **Verktyg** > **Molntjänster** > **Översättningsmolntjänster**.

### Hur inaktiverar man en AEM-komponent som ger exponentiell tillväxt för AEM SegmentStore (AEM 6.3.1.1)? {#how-to-disable-an-aem-component-causing-exponential-growth-for-the-aem-segmentstore-aem}

Du kan inaktivera OSGi Component Disabler. Information om hur du använder den här tjänsten finns i [OSGi Component Disabler](https://adobe-consulting-services.github.io/acs-aem-commons/features/osgi-disablers/component-disabler/index.html).

Som en tillfällig lösning kan du även inaktivera komponenten manuellt antingen via gränssnittet eller via ett `curl` kommando (exempel nedan) efter varje AEM-omstart.

`curl -u admin:$(pass CQ_Admin) 'http://localhost:4502/system/console/components/com.day.cq.analytics.sitecatalyst.impl.importer.ReportImporter' --data 'action=disable'`

### Hur konfigurerar man tillgångsinsikter med AEM 6.4-instansen? {#how-to-configure-asset-insights-with-aem-instance}

Information om hur du konfigurerar och konfigurerar tillgångsinsikter för Experience Manager som distribueras via Adobe Activation (DTM) finns i [Konfigurera tillgångsinsikter med AEM Assets](https://helpx.adobe.com/experience-manager/kt/assets/using/asset-insights-tutorial-setup.html).

### Hur anpassar man administrationskonsoler? {#how-to-customize-admin-consoles}

AEM innehåller olika mekanismer som gör att du kan anpassa konsolerna och sidredigeringsfunktionerna i din redigeringsinstans.
Mer information om hur du skapar en anpassad konsol och anpassar en standardvy för en konsol finns i [Anpassa konsoler](/help/sites-developing/customizing-consoles-touch.md).

### Vad är skillnaden mellan CoralUI 2- och CoralUI 3-baserade komponenter? {#what-is-the-difference-between-coralui-and-coralui-based-components}

En ny uppsättning Sling-komponenter för Granite UI Foundation har skapats för Coral3 och finns under [/libs/granite/ui/components/coral/Foundation.](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/coral/foundation/server.html) Det finns en uppsättning för CoralUI 2-baserade komponenter och en uppsättning för CoralUI 3-baserade komponenter. Den nya uppsättningen kommer inte bara att vara en kopiera-klistra in av den gamla uppsättningen, utan kommer att rensas (till exempel strömlinjeformning, borttagning av borttagen funktion). Därför rekommenderar vi att en sida endast använder CoralUI 3-baserad eller CoralUI 2-baserad uppsättning.

Mer information finns i [Migreringshandboken till CoralUI 3-baserad](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/granite-ui/api/jcr_root/libs/granite/ui/components/legacy/coral2/migration.html).

### Hur anpassar man sökkomponenten i AEM Assets? {#how-to-customize-the-search-component-in-aem-assets}

Mer information om sökökning/rankning och ytterligare implementeringsinformation finns i Implementeringsguiden för [enkel sökning.](https://helpx.adobe.com/experience-manager/kt/sites/using/search-tutorial-develop.html)

Den enkla sökimplementeringen är material från 2017 Summit lab AEM Search Demystified.

### Om en kund endast köper Sites-licenser i AEM, har de fortfarande tillgång till Assets? {#if-a-customer-buys-only-sites-license-in-aem-do-they-still-have-access-to-assets}

Nej, kunden kan inte komma åt Assets (eller något annat än Sites). Även om alla Adobe Experience Manager On-Local (AEM) finns med i JAR-rapporten har kunden bara tillgång till de komponenter i JAR som de har licens för i sitt avtal. Om de vill utforska andra komponenter kan de antingen använda utvärderingsprogrammet för AEM i upp till 45 dagar eller signera en försäljningsorder på $0 som ger dem behörighet att utvärdera (ingen användning av produktionen) namngivna komponenter som Assets.

Läs mer om AEM On-Premise och Adobes hanterade tjänster här:

* [Lokal programvara för Adobe Experience Manager](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-on-premise.html)

* [Adobe Experience Manager Managed Services](https://helpx.adobe.com/legal/product-descriptions/adobe-experience-manager-managed-services.html)

### Hur kan en kund utöka standardegenskaperna för en sida eller en resurs? {#how-to-extend-default-properties-page-or-asset}

Mer information om hur du utökar standardegenskaperna för en sida eller en resurs finns i resurserna nedan:

* [Metadata-scheman i resurser](/help/assets/metadata-schemas.md)
* [Anpassa vyer av Sidegenskaper](/help/sites-developing/page-properties-views.md)
