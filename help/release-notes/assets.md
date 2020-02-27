---
title: Versionsinformation om AEM Resurser
seo-title: AEM Assets
description: Versionsinformation om Adobe Experience Manager 6.4 Assets.
seo-description: Versionsinformation om Adobe Experience Manager 6.4 Assets.
uuid: f5e7608d-f906-4a35-b442-899703de3587
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 397b3267-1437-4263-963c-9d68ccc928ab
translation-type: tm+mt
source-git-commit: 2411f1aa2853a161603d15917102d5cf1a8139b6

---


# Versionsinformation om AEM Resurser {#aem-assets-release-notes}

Viktiga funktioner, högdagrar och förbättringar som gjorts i AEM 6.4 Assets beskrivs i versionsinformationen. Följ länkarna för detaljerad information.

## Adobe Asset Link {#adobe-asset-link}

Adobe Asset Link i Creative Cloud for enterprise effektiviserar samarbetet mellan kreatörer och marknadsförare vid skapandet av innehåll. Det är en ny inbyggd funktion i Creative Cloud for enterprise som ger en anslutning till AEM Assets direkt från Adobe Photoshop, Adobe Illustrator eller Adobe InDesign - utan att lämna dessa verktyg.

Mer information om funktioner, förutsättningar och hur du får tillgång till dem finns på sidan [Adobe Asset Link](https://helpx.adobe.com/enterprise/using/adobe-asset-link.html) .

## Förbättrade smarta taggar (från Adobe Sensei) {#enhanced-smart-tags-powered-by-adobe-sensei}

Med AEM 6.4 introduceras artificiell intelligensbaserad Förbättrade smarta taggar utöver smarta taggar som startades i AEM 6.3.

* Smart Content Service lär sig kundens affärsklonomi och använder den för att automatiskt tagga digitala resurser med kundrelevanta taggar utöver generiska taggar. Det förbättrar upptäckten av tillgångar avsevärt och minskar time to market.
* Adobe Sensei driver Smart Content Service, som gör det möjligt att utbilda bildigenkänningsalgoritmen i företagets taxonomi. Den här innehållsintelligensen används sedan för att tillämpa relevanta taggar på liknande resurser.

Om du vill använda AEM Resurser Förbättrade smarta taggar installerar du det [senaste Service Pack-versionen av AEM 6.4](https://helpx.adobe.com/experience-manager/aem-releases-updates.html).

## Smart Translation Search (med Adobe Sensei som bas) {#smart-translation-search-powered-by-adobe-sensei}

I AEM 6.4 introduceras funktionen Smart Translation Search som stöder flerspråkiga sökscenarier. Kunder med globalt spridda team på flera olika språk har nu tillgång till sökning på olika språk utan att behöva använda kostsamma och tidsödande arbetsflöden för översättning.

* Sökfrågan översätts utan manuell åtgärd.
* Smarta taggar genereras på engelska och maskinöversätts till andra språk.
* Flerspråkig sökning utförs med öppen källkodsbiblioteket Apache Joshua som stöder mer än 50 språk.

## Användarupplevelse {#user-experience}

AEM 6.4 ger avsevärda förbättringar vad gäller bläddring, sökning, flersidiga resurser och administrationsverktyg. Information nedan:

Förbättrad bläddring

* Ny innehållsträd för att snabbt navigera i en resurshierarki. I kombination med listvyn återställs interaktionsmodellen för klassiskt användargränssnitt så att resurshierarkier kan bläddras.
* Nya kortkommandon, till exempel m för att flytta resurser, p för att öppna egenskapssidan, Ctrl + C för att kopiera åtgärder och många andra.
* Förbättrad rullning, lat inläsningsgränssnitt i kort- och listvyn för att bläddra bland ett stort antal resurser.
* Förbättrad kortvy med stöd för kort i olika storlekar baserat på visningsinställningar.
* Förbättrad upplevelse av tillgångsinformation med möjlighet att visa, navigera till&quot;föregående&quot; eller&quot;nästa&quot; resurs tillsammans med antal resurser, aktuell resurs.

Förbättrade sökfunktioner

* Ny knapp för att söka tillbaka med möjlighet att navigera till ett sökobjekt och återgå till samma position i sökresultaten utan att köra sökfrågan igen.
* Antal nya sökresultat om du vill visa antalet sökresultat.
* Förbättrat filtypssökfilter med möjlighet att filtrera sökresultat baserat på finkorniga MIME-typer som JPG, PNG och PSD, jämfört med tidigare bild-, dokument- och multimediealternativ.
* Förbättrade sökfilter med exakta tidsstämplar istället för tidigare funktioner med skjutreglage.

Förbättringar av flersidiga resurser

* Förbättrad surfupplevelse av resurser på flera sidor med minskat antal klick.
* Förbättrade kommentarer och anteckningar har stöd för alla sammanställda på tillgångsnivå i stället för på sidnivå.

Förbättringar av administrationsverktyg

* Förbättrad egenskapsväljare i administrationsverktygen för metadata, sökning och rapporter med Type ahead-funktioner och bläddringsfunktioner som förenklar administratörsupplevelsen.

Kataloger

* Förbättrad användarupplevelse, anpassning till mallgränssnittet. Mer information finns i [Katalogproducent](../sites-administering/catalog-producer.md).

## Metadata {#metadata}

AEM 6.4 har flera avancerade metadatahanteringsfunktioner för att hantera metadata i stor skala och upprätthålla metadataintegriteten med hjälp av regler och valideringar. Här är de viktigaste funktionerna:

* Ny exportfunktion för massmetadata som exporterar (alla, selektiva) metadata för ett stort antal resurser i CSV-format för redigering, delning och integrering med tredje part.
* Ny funktion för import av massmetadata för att importera CSV-filer för att lägga till nya metadata och uppdatera befintliga metadata för flera resurser på en gång. Den här åtgärden är asynkron och hindrar inte systemprestanda. När det är klart meddelas användaren via AEM:s meddelandesystem.
* Nya Cascading- och Contextual Metadata-verktyg med Metadata Schema Tool. Nu är det möjligt att definiera kedjor av beroenden och värdemappningar mellan fält. Du kan också definiera i vilket sammanhang metadataformulärfält ska visas/döljas. På så sätt kan du bara visa relevanta fält när som helst beroende på värden i andra fält.

## Rapporter {#reports}

AEM 6.4 ger betydande förbättringar i tillgångsrapporteringen:

* Nytt skalbart ramverk (för stora databaser) på företagsnivå som använder Sling-jobb för asynkron bearbetning av rapportbegäranden. Du kan schemalägga rapporter vid ett visst datum och en viss tidpunkt. Du kan också lägga till anpassade kolumner i en rapport.
* Nya OTB-rapporter som oftast efterfrågas av kunder som t.ex. Diskanvändning, Filer, Länkresurser, Publicera på varumärkesportal och Utbildning i smarta taggar.
* Nytt gränssnitt för att skapa och hantera rapporter med finkorniga alternativ, möjlighet att komma åt arkiverade rapporter, se status för rapportkörning (lyckades, misslyckades, köades osv.).

## Varumärkesportal {#brand-portal}

* **6.3 Platform Upgrade**: Varumärkesportalen har uppgraderats från AEM 6.0 till AEM 6.3 med nya funktioner och prestandaförbättringar.
* **Parallell publicering**: Upp till replikeringar kan ske mellan AEM Assets och Brand Portal (tidigare 1), vilket avsevärt förbättrar publiceringsprestanda
* **Publicering** av schema- och sökfasett: Möjlighet att publicera metadatamatcheman och anpassade sökaspekter på varumärkesportalen, vilket eliminerar behovet av dubbelarbete.
* **Publicera** flera taggar: Möjlighet att publicera taxonomi (tillsammans med hierarki) till varumärkesportalen, vilket eliminerar behovet av dubbelarbete.
* **Självregistrering eller Begär åtkomst**: Arbetsflöde för oregistrerade användare på varumärkesportalen.
* **Underhållsmeddelande** i appen (på skärmen): Meddelanden visas i god tid för att undvika störningar i verksamheten.
* **Förbättrade** rapporter: Tre OOTB-rapporter finns: ladda ned, publicera och dela länkar.
* **DRM-baserade begränsningar**: När en licensierad mediefil har gått ut är den inte längre tillgänglig för hämtning från varumärkesportalen.

## AEM-skrivbordsapp {#aem-desktop-app}

AEM-datorprogrammet uppdateras till version 1.8, som är kompatibel med AEM 6.4. En fullständig lista över ändringar för AEM-datorprogrammet finns i ett dedikerat dokument med versionsinformation [för](https://helpx.adobe.com/experience-manager/desktop-app/release-notes.html) AEM-skrivbordsappen.\
Här är en lista över höjdpunkter på AEM-skrivbordsappen sedan AEM 6.3 släpptes:

* Möjlighet att överföra hierarkiska mappar i bakgrunden.
* Gränssnitt för att övervaka överföringar av resurser i bakgrunden.
* Förbättrad cachelagring, inklusive ett gränssnitt för att hantera cachelagringsparametrar.
* Bredare stöd för AEM-autentiseringskonfigurationer (SAML/SSO) och nätverksproxy.
* Supportabilitet: enkel åtkomst till loggar från användargränssnittet.
* Förbättrad stabilitet och korrigeringar för kundproblem.

Följande dokumentation är tillgänglig för enklare åtkomst till dokumentation och bästa praxis:

* [Användarhandbok](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html)som riktar sig till slutanvändare som arbetar med programmet
* [Best practices guide](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app-best-practices.html), riktad till slutanvändare och administratörer
* [Installationshandbok](https://helpx.adobe.com/experience-manager/desktop-app/install-configure-aem-desktop-app.html), som riktar sig till administratörer som konfigurerar AEM- och AEM-skrivbordsappen för att fungera tillsammans

## Nivåindelad lagring {#tiered-storage}

AEM 6.4 innehåller en uppsättning funktioner som stöder olika nivåindelade lagringsinställningar och som implementerar livscykelregler. Lagringsalternativen har också stöd för (men är inte begränsade) offentliga moln - AWS eller Azure.

* Möjlighet för användare att välja och senare ändra lagringsklass när de vill och definiera regler för lagring av resurser från en klass till en annan eller hantera livscykeln för deras resurser.
* Möjlighet för användare att sänka sina lagringskostnader genom att välja en annan AWS eller Azure.

En översikt över vilka plattformar som stöds finns i dokumentationen om [tekniska krav](../sites-deploying/technical-requirements.md).

## Stängd användargrupp {#closed-user-group}

* I AEM 6.4 kan du använda Stängd användargrupp eller CUG för att begränsa mappåtkomst vid publiceringsinstans. Det är ett alternativ för att lägga till objekt via mappegenskapssidan på mappnivå och det används för alla mappar och undermappar/resurser i mappen.
* Om en CUG är konfigurerad och auktorisering aktiverad för en mapp omdirigeras användarna i publiceringsläge till en inloggningssida när de försöker komma åt mappen. Därför kan behöriga användare komma åt mappen och dess resurser först efter att inloggningen är slutförd. Därför begränsar CUG läsåtkomsten till ett visst träd i innehållsdatabasen för alla utom valda objekt.

## Dynamic Media-tillägg {#dynamic-media-add-on}

Dynamic Media i 6.4 har stöd för ett nytt läge - där huvudresursen överförs och hanteras med webbgränssnittet för AEM Assets, och dynamiska återgivningar och andra dynamiska mediefunktioner hanteras i bakgrunden av Dynamic Media-molntjänsten.

I det här läget (som introducerades i [AEM 6.3 Feature Packs 14410 och 18912](https://helpx.adobe.com/experience-manager/6-3/release-notes/dynamic-media-featurepack-14410.html)) drar användarna nytta av komplett resurshantering och dynamiska mediefunktioner med det moderna AEM Assets-webbgränssnittet och utnyttjar fortfarande leveranstjänster som är bakåtkompatibla med Dynamic Media Classic (Scene7), inklusive leverans-URL:er, som oförändrad.

Dessutom innehåller AEM 6.4 nya funktioner som drivs av Adobe Sensei, förbättringar för nya medier som VR och 3D, Dynamic Media-visningsprogram och stöd för Experience Fragments i Interactive Images och Carousel Banners.

### Smart Crop (från Adobe Sensei) {#smart-crop-powered-by-adobe-sensei}

* Smart Crop ger automatiskt icke-förstörande beskärning av bilder för att bevara intressepunkten för responsiv design. Du kan förhandsgranska beskurna förslag och manuellt justera dem om det behövs.
* Den här funktionen möjliggör även automatisk generering av färgrutor för produktbilder. Automatiserad generering av färgrutor gör det enklare att automatiskt lägga till färgrutor, mönsterrutor eller båda i produktbilderna.

Mer information finns i dokumentationen för [bildprofiler](../assets/image-profiles.md) .

Läs även [Lägga till dynamiska medieresurser till siddokumentationen](../assets/adding-dynamic-media-assets-to-pages.md) om du vill veta mer om hur du använder SmartCrop med komponenten Dynamic Media.

### Smart bildbehandling {#smart-imaging}

* Smart bildbehandling utnyttjar varje användares unika visningsegenskaper för att automatiskt leverera bilder som är optimerade för sin upplevelse, vilket ger bättre prestanda och engagemang.
* Bilder konverteras automatiskt till olika format baserat på webbläsarfunktioner.
* Bildkvalitetsinställningarna bestäms i webbläsaren och används. Den här intelligensen gör att bildinläsningsprestanda är acceptabla för begränsad bandbredd och långsamma anslutningshastigheter.

Mer information finns i dokumentationen för [Smart](../assets/imaging-faq.md) Imaging.

### Förbättringar av nya medier och visningsprogram {#emerging-media-amp-viewer-enhancements}

* Nya visningsprogram stöds, vilket ger användaren bättre och mer engagerande upplevelser.
* Panoramavisningsprogrammet hjälper till att engagera användaren och ger möjlighet att bättre uppleva rumsscener, egenskaper, platser och landskap. Mer information finns i dokumentationen för [panoramabilder](../assets/panoramic-images.md) .

* VR Viewer ger en engagerande upplevelse av egenskaper, platser och landskap.
* Vertical Image Viewer optimerad för produktbilder.
* Förbättrade hjälpmedelsfunktioner för tangentbord.

### 3D och integrering med Dimension CC {#d-and-integration-with-dimension-cc}

Integrering med [Adobe Dimension CC](https://www.adobe.com/products/dimension.html) för smidigare 3D-arbetsflöde har införts. Mer information finns i [Arbeta med 3D-resurser](../assets/assets-3d.md) .