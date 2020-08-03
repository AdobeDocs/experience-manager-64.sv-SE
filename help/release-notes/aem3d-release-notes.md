---
title: AEM 3D versionsinformation
seo-title: AEM 3D versionsinformation
description: Versionsinformation om 3D-innehåll i Adobe Experience Manager Assets.
seo-description: Versionsinformation om 3D-innehåll i Adobe Experience Manager Assets.
uuid: 6675951f-86f0-4ec5-97e4-d247f6faf913
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4
content-type: reference
topic-tags: 3D
discoiquuid: 9789d031-fb7e-415a-a9c3-8b8fde978238
translation-type: tm+mt
source-git-commit: f8ba597c62379ba413309303c2ad066ab7afce1e
workflow-type: tm+mt
source-wordcount: '1933'
ht-degree: 0%

---


# AEM 3D versionsinformation {#aem-d-release-notes}

AEM-6.4-DynamicMedia-3D version 3.1.0 (10 oktober 2018)

Det AEM 3D-funktionspaketet har stöd för 3D-innehåll i AEM Assets. Den innehåller funktioner för att överföra, hantera, förhandsgranska och återge 3D-resurser. Stöd för visning och återgivning är optimerat för enskilda objekt (i stället för komplexa scener med flera objekt).

AEM 3D stöder resurstyperna Adobe Dimension (Dn) och glTF. Implementeringen för dessa tillgångstyper skiljer sig avsevärt från implementeringen för traditionella 3D-typer som beskrivs i den här dokumentationen. Se [Arbeta med Adobe Dimension-resurser](/help/assets/working-dimension-assets.md).

Det ingår även serverintegration med Autodesk® Maya® (endast Windows). När du installerar och konfigurerar Maya på samma server som AEM aktiverar du stöd för filformaten Maya, inklusive högklassig rendering med den fristående pluginmodulen NVIDIA® mental ray® för Maya. Installation och konfigurering av 3ds Max på servern ger stöd för det inbyggda .max-filformatet.

Se [Integrera med Autodesk Maya](/help/assets/integrate-maya-with-3d.md).

Se även [Installera och konfigurera AEM 3D-resurser](/help/assets/install-config-3d.md) och [Avancerade konfigurationsinställningar](/help/assets/advanced-config-3d.md).

Se även [Arbeta med 3D-resurser](/help/assets/assets-3d.md).

## Systemkrav {#system-requirements}

**Förutsättningar**

* AEM 6.4.2 (AEM 6.4 med Service Pack 2)
* Autodesk® FBX® SDK 2016.1.2

**Operativsystem som stöds**

* Microsoft Windows 2012 Server eller senare
* Apple OS X El Capitan 10.6 eller senare
* RedHat Enterprise Linux 7.3

**Webbläsare som stöds för AEM Assets**

* Google Chrome 53 eller senare (rekommenderas).
* Apple Safari 9.1 eller senare.
* Firefox 48 eller senare.
* Microsoft Edge 25.10586 eller senare.

Andra webbläsare kanske inte har stöd för interaktiv visning av 3D-innehåll i AEM. Endast Google Chrome har stöd för skuggning i förhandsvisning.

**Maskinvarukrav och rekommendationer**

* CPU - 3D-bearbetning och -rendering är mycket krävande på datorns processor. Därför rekommenderas en modern server med minst åtta processorkärnor.
* Minne - Minst 32 GB rekommenderas.
* Masslagring - SSD-lagring med hög bandbredd rekommenderas.

   Vid överföring konverteras 3D-resurser till ett eget format för snabb, interaktiv visning. Beroende på vilken typ av 3D-resurs det är nödvändigt med lagringsutrymme på 2-3x storleken på den överförda 3D-resursen.

Se även [Arbeta med 3D-resurser](/help/assets/assets-3d.md).

## Installera och konfigurera AEM 3D {#installing-and-configuring-aem-d}

Se [Installera och konfigurera AEM 3D](/help/assets/install-config-3d.md).

Se även [Integrera AEM 3D med Autodesk Maya](/help/assets/integrate-maya-with-3d.md) och [Integrera AEM 3D med Autodesk 3ds Max](/help/assets/integrating-aem-3d-with-autodesk-3ds-max.md).

## 3D-filformat som stöds {#supported-d-file-formats}

| Format | Beskrivning | Plattformar | Anteckningar |
|--- |--- |--- |--- |
| DN | Adobe Dimension | Alla | Kräver åtkomst till en molnbaserad konverteringstjänst. |
| GLTZ | Zipped gITF | Alla |  |
| GLB | Binary gITF | Alla | Hämta endast (GLB-återgivningar skapas för DN-resurser). |
| OBJ | Wavefront OBJ 3D | Alla |  |
| FBX | Autodesk FBX (Kaydara Filmbox) | Alla | Autodesk FBX SDK måste vara installerat på Författarnoden. |
| MA, MB | Autodesk Maya | Endast Windows | Autodesk Maya krävs på Författarnoden för att aktivera dessa filformat. Se [Integrera AEM 3D med Autodesk Maya](/help/assets/integrate-maya-with-3d.md). |
| JT | Siemens PLM Open CAD | Endast Windows | Autodesk Maya krävs på Författarnoden för att aktivera dessa filformat. Se [Integrera AEM 3D med Autodesk Maya](/help/assets/integrate-maya-with-3d.md). |
| * | Ytterligare 3D-indataformat som stöds av Autodesk Maya kan aktiveras. Se [Aktivera ytterligare format som stöds av Maya](/help/assets/integrate-maya-with-3d.md#enabling-additional-formats-supported-by-maya). | Endast Windows | Autodesk Maya krävs på Författarnoden för att aktivera dessa filformat. Se [Integrera AEM 3D med Autodesk Maya](/help/assets/integrate-maya-with-3d.md). |
| MAX | Autodesk 3ds max | Endast Windows | Autodesk 3ds Max krävs på författarnoden för att aktivera det här filformatet. Se [Integrera AEM 3D med Autodesk 3ds Max](/help/assets/integrating-aem-3d-with-autodesk-3ds-max.md). |

## Förbättringar och nya funktioner {#enhancements-and-new-features}

Version 3.0

* Stöd för Autodesk 3ds Max inbyggt filformat.
* Olika ändringar och felkorrigeringar för att förbättra stabilitet, kvalitet och användarupplevelse.
* Konfigurationsinställningar har flyttats till `/libs/settings/dam/v3d/`

Version 3.1

* Begränsat stöd för Adobe Dimension filformat (.dn).
* Ett nytt 3D-visningsprogram för glTF-resurser.
* Ett nytt gränssnitt till en molnbaserad, Adobe-hanterad konverteringstjänst som finns i Amazon AWS. Inledningsvis konverteras endast den här tjänsten från Dn till glTF-format.

## Begränsningar och kända fel {#restrictions-and-known-issues}

### Adobe Dimension support {#adobe-dimension-support}

* Den här versionen av AEM3D har begränsat stöd för .dn-filer som skapas med Adobe Dimension.
* Under överföringsprocessen använder AEM en molnbaserad konverteringstjänst på Adobe för att skapa en glTF-rendering från den ursprungliga .dn-filen. Du måste ha tillgång till konverteringstjänsten och välja Amazon AWS-slutpunkter.
* Det finns ett nytt glTF-visningsprogram som har stöd för visning av Dn-resurser i AEM Assets och på platser/skärmar. Stöd för scener i visningsprogrammet är inte tillgängligt än.
* Dn-modeller kan bädda in IBL-ljus och bakgrunder som visas, om sådana finns. Visningsprogrammet kan också använda standardljus, eller en standardbakgrundsfärg, eller båda.
* Det finns ännu ingen högkvalitativ återgivning för Dn-resurser.
* Beroenden som texturscheman är inbäddade i Dn-resurser och kan inte hanteras explicit i AEM.

### Kompatibilitet {#compatibility}

* **Körning som Windows-tjänst stöds inte (endast Windows)** . Detta kan fungera men har inte testats.
* **Dynamic Media** ( `dynamicmedia-scene7` läge) - Kompatibiliteten för AEM3D med den nya Dynamic Media-lösningen som släpptes med AEM 6.4 har ännu inte verifierats fullständigt. Om Dynamic Media och AEM3D distribueras tillsammans rekommenderar vi att du bara placerar 3D-resurser och deras beroenden i ett område i AEM Assets databas som inte är tilldelat Dynamic Media. Den här rekommendationen är särskilt viktig för 32-bitars TIFF-filer som krävs för 3D-scener men som inte stöds av Dynamic Media.

### Allmänt {#general}

* **Genvägen** Lös beroenden - Den här genvägen är tillgänglig i kortvyn för 3D-resurser. Resurskort i kortvyn visar bannern Olösta beroenden. Kortkommandot öppnar fliken **Grundläggande egenskaper** i stället för fliken **Beroenden** . Tillfällig lösning: navigera manuellt till fliken Beroenden.

* **Scenväljaren är inte tillgänglig** - 3D-resurser som innehåller ljus taggas automatiskt av AEM som 3D-faser. Det finns ingen lägesväljare tillgänglig för faser i detaljvyn. Om du vill markera en 3D-resurs som ett 3D-objekt går du till **Grundläggande egenskaper**, ändrar **Resursklass** till **3D-objekt** och klickar sedan på **Spara**.

* **Hämta 3D-resurser med beroenden och renderingar** - När du hämtar 3D-resurser från AEM med både **Beroenden** och **renderingar** markerade, innehåller hämtningen inte bara renderingar av den primära 3D-resursen, utan även renderingar av alla beroenden.

* **Autodesk 3ds Max-integrering** - Rendering med 3ds Max stöds inte just nu.

### Filtypsbegränsningar {#file-type-restrictions}

* **Matematiska (.ma) filer** - Matematiska filer använder samma filsuffix som ursprungliga Maya-filer. När funktionspaketet är installerat och filformatet Maya.ma är aktiverat, misslyckas AEM3D:s försök att importera matematiska filer som Maya-filer. Sådana resurser visar en felbanderoll i kortvyn.

* **Targa-bildfiler** (.tga) - Äldre 3D-modellfiler kan innehålla referenser till TGA-filer. Det här formatet stöds inte av AEM. Adobe rekommenderar att du konverterar sådana filer till ett annat format innan du överför 3D-resurserna till AEM.
* **HDR-bilder** - HDR-bilder används för faser med bildbaserat ljus (IBL). För närvarande stöds endast 32-bitars TIFF-bilder för detta ändamål.
* **32-bitars TIFF-bilder** - 32-bitars TIFF-bilder används för faser med bildbaserad belysning. AEM har inte stöd för att skapa återgivningar för dessa resurser, vilket resulterar i tomma miniatyrbilder, och förhandsgranskning är inte möjlig. Tillgången fungerar fortfarande korrekt när den används i ett IBL-steg.
* **Autodesk 3ds Max-filer** (.max) - Om Autodesk 3ds Max är installerat och konfigurerat på Author-noderna har AEM stöd för att hantera och konvertera .max-filer. Det går för närvarande inte att använda .max-filer som steg.

### Automatisk beroendeupplösning {#automatic-dependency-resolution}

* **Olösta filberoenden efter överföring** - När 3D-resurser och deras beroenden överförs med samma överföring är det möjligt att vissa beroenden inte löses automatiskt. Det här problemet uppstår troligare om de beroende filerna är stora. Åtgärda problemet genom att gå till sidan **Egenskaper/beroenden** för resursen som visar olösta beroenden efter överföringen. De tidigare ej lösta beroendena ska nu visas. Klicka på **Spara** för att slutföra resursen. Om du vill förhindra det här problemet i framtiden kan du överföra alla beroenden i en separat transaktion innan du överför 3D-objekten.

* **Skiftlägeskänslighet** - Automatisk beroendeupplösning försöker matcha filnamn på ett skiftlägeskänsligt sätt. Om t.ex. det ursprungliga beroendet i 3D-resursen är `image.jpg`, tolkas beroendet som en resurs med namnet `Image.jpg`, `image.JPG`eller någon annan skiftlägesvariation.

### 3D-faser {#d-stages}

* **Miniatyrbilder för scener** - De automatiskt genererade miniatyrbilderna för scener kanske inte representerar scenen korrekt.
* **Scengeometri för icke-IBL-stadier** - Renderingen för förfina snabbt återger inte geometri från faser med icke-IBL-ljus, inklusive bakgrunder och markplan. Den här geometrin visas fortfarande på ett rimligt sätt i resursvyn Detalj (3D-förhandsvisning).

* **FBX-faser med IBL-ljus** - Du kan överföra FBX-faser med IBL-ljus. FBX-formatet har dock inga bestämmelser för överföring av IBL-bildnamnet. Filberoendeupplösningen misslyckas därför. IBL-bilden måste tilldelas manuellt till scenen efter överföringen. Du kan tilldela samma 32-bitars TIFF-bild till de tre beroenden som är **Diffusera foton** för ljusmiljö, **Reflexion Environment Image** och **Background Environment Image**, eller så kan olika bilder tilldelas.

* **Bakgrundsbild av IBL-stadier** - För vissa IBL-scener kan bakgrundsbilden ha dålig kvalitet, till exempel för ljus eller för suddig. För att maximera den visuella kvaliteten på bildbakgrunden i IBL-stadier rekommenderar Adobe att du förbereder en separat 8-bitars JPEG-bild med hög upplösning och bifogar den till IBL-scenen som **bakgrundsmiljöbild**.

* **Svart bild vid återgivning med Maya i ett IBL-stadium** - Detta problem beror troligen på att Maya inte hittar IBL-bildberoendet eftersom den ursprungliga IBL-bilden som scenen refererar till har ersatts med en bild med ett annat namn. För att undvika detta bör du se till att minst ett av de tre beroenden som Maya IBL-scenen refererar till har samma namn som den ursprungliga IBL-filreferensen i Maya-filen.
* **Omvänd bakgrundsbild för IBL-scenen** - Bilderna för IBL-stadier har avsiktligt vridits vågrätt för att matcha beteendet hos den NVIDIA-renderare för mental ray som tillhandahålls av Autodesk Maya. Tillfällig lösning: Vänd bilderna som används för IBL-stadier i Photoshop innan du överför dem.
* **Intensitet i IBL-stadier** - Den automatiska analysen av IBL-bilden kan resultera i att motivet är för mörkt eller för ljust. Om du vill justera ljusstyrkan för IBL-stadier går du till **Grundläggande egenskaper** och justerar det **ljusa** värdet för **Miljöbelysning** efter behov.

### AEM Sites 3D-komponent {#aem-sites-d-component}

* **En 3D-komponent per sida** - För närvarande tillåts bara en instans av 3D-komponenten på varje webbsida. Om mer än en 3D-komponent läggs till på samma sida fungerar ingen av 3D-komponenterna korrekt.
* **3D-vyn saknas när du förhandsgranskar i platser** - När du använder **Förhandsgranska** i platser måste sidan läsas in på nytt i webbläsaren för att 3D-visningsprogrammet ska kunna initieras fullständigt. Detta är inte något problem när du visar webbsidan direkt (d.v.s. när den `edit.html` tas bort från sökvägen) på antingen författarnoden eller publiceringsnoden.

* **Helskärmsläge är inte tillgängligt på iOS-enheter** - Helskärmsknappen är inte tillgänglig på iOS-enheter, oavsett vilken webbläsare som används.

### Publicera 3D-innehåll {#publishing-d-content}

* **Konfiguration** av 3D-komponent - Du måste installera 3D-funktionspaketet på alla aktiva publiceringsnoder och varje nod måste konfigureras med **CRXDE Lite** till samma konfigurationsalternativ på `/libs/settings/dam/v3D/WebGLSites`.

* **Texturer, bakgrund eller ljus saknas efter publicering** - **Publiceringsfunktionen** i AEM Sites publicerar automatiskt sidans primära beroenden, inklusive 3D-modellen och 3D-scenen som 3D-komponenten refererar till. 3D-faser och 3D-modeller är vanligtvis beroende av sekundära resurser för IBL-bilder och texturkartor, som publiceras inte automatiskt av publiceringsfunktionen i Sites. Tillfällig lösning: publicera alla 3D-resurser från Assets innan du publicerar webbsidan från Sites. Detta garanterar att alla beroenden för 3D-resurser är tillgängliga på publiceringsnoderna.
