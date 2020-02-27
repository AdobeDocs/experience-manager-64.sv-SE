---
title: Versionsinformation för AEM Sites
seo-title: AEM Sites
description: Versionsinformation om webbplatser i Adobe Experience Manager 6.4.
seo-description: Versionsinformation om webbplatser i Adobe Experience Manager 6.4.
uuid: 593928ec-5d1a-4a88-bd73-897421c5984a
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 40225441-7cfe-4395-ac71-60504b42e764
translation-type: tm+mt
source-git-commit: 901a923b6ab2b6bee1738d2b8f1928571c8019cb

---


# Versionsinformation för AEM Sites {#aem-sites-release-notes}

## Sites {#sites}

Se följande för förbättringar av AEM Sites 6.4:

### Webbplatsadministration {#site-administration}

* Ny innehållsträd för att snabbt navigera i en platshierarki. I kombination med listvyn återställs interaktionsmodellen för klassiskt användargränssnitt så att du kan bläddra på en plats.
* Förbättrad bläddring i kort- och listvyn för stora mappar.
* Förbättrad interaktion med sökresultaten - knappen Bakåt återställer det tidigare sökresultatet.
* Ytterligare kortkommandon, för de vanligaste åtgärderna, som att öppna en viss räl, redigera, flytta och ta bort sidor eller för att öppna egenskaper.
* Möjlighet att inaktivera kortkommandon (aktivera/inaktivera i Inställningar).
* Sluta visa tidsstämplar i alla användargränssnittsrelativa efter 7 dagar (ange som standard i Inställningar).

###  Page Editor {#page-editor}

* Uppdaterad enhetslista för responsiv förgranskning av webbplatser, nu med Apple iPhone 8, 8 Plus och X samt Samsung S7
* Flyttade standardplats för malldesigninformation bort från /etc/design för att stödja webbplatsspecifika inställningar i /conf. Kunder som uppgraderar från tidigare AEM-versioner kan fortsätta använda /etc/design.

### Utveckling av komponenter och mallar {#component-amp-template-development}

* Project Archetype 13+, se [Github för versionsinformation](https://github.com/Adobe-Marketing-Cloud/aem-project-archetype/releases).
* HTML version 1.3.1, se [Github för versionsinformation](https://github.com/Adobe-Marketing-Cloud/htl-spec/releases/tag/1.3.1).
* Core Components 2.0.4+, se [Github för versionsinformation](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/releases).
* Formatsystem

   * Lagt till ett helt nytt koncept för att tilldela CSS-klasser till komponenter och tillåta användare i sidredigeraren att välja bland en delmängd av format via användargränssnittet
   * Lagt till möjlighet att definiera det HTML-elementnamn som återges runt komponenten, t.ex. &lt;main>, &lt;exclude>

* Stödrastersystem för layoutbehållare, se [Github](https://github.com/Adobe-Marketing-Cloud/aem-responsivegrid).
* Mallredigerare och profiler

   * Profiler har nu stöd för Style System-konfigurationer per komponent, per behållare och mall.
   * Förbättrat stöd för att definiera layout i mallar för redigerbara komponenter

* Referenswebbplats Vi.Retail 3.0, se [Github för versionsinformation](https://github.com/Adobe-Marketing-Cloud/aem-sample-we-retail/releases).

>[!CAUTION]
>
>AEM inkluderar version 1.12.4 av jQuery-biblioteket för att ge maximal kompatibilitet med befintlig anpassad kod. Adobe har gjort ändringar för att åtgärda kända säkerhetsproblem.

### Content Fragments &amp; Editor {#content-fragments-amp-editor}

* Strukturerade innehållsmodeller som grund för innehållsfragment

   * Modellredigeringsgränssnitt
   * Förkonfigurerade dataelement för innehållsfragmentmodeller (enkelradstext, flerradstext, tal, boolesk, datum&amp;tid, uppräkning, innehållsreferens, taggar)

* Förbättrad användbarhet för AEM Content Fragment-redigeraren

   * Översikt över alla element
   * Helskärmsredigering för enstaka element
   * Förbättrade funktioner för textredigering (punktlistor, numrerade listor, indrag, hyperlänkar, tabeller, sök&amp;ersätt, stavningskontroll)

* Förbättrade utdataalternativ för AEM Content Fragments har lagts till

   * Ny komponent för innehållsfragment, som en del av kärnkomponenter. [Se kod på GitHub.](https://github.com/Adobe-Marketing-Cloud/aem-core-wcm-components/tree/master/extension/contentfragment/content/src/content/jcr_root/apps/core/wcm/extension/components/contentfragment/v1/contentfragment)
   * Content Services-stöd med JSON-utdata via Sling Model Exporter

### Experience Fragments {#experience-fragments}

* Introducerade Experience Fragment Building Blocks, för att underlätta återanvändning av innehåll mellan Experience Fragments-variationer genom att gruppera komponenter och göra det enkelt att referera i varianter.
* Lagt till möjlighet att lägga till Experience Fragments i översättningsprojekt via referensspåret
* Förbättra möjligheterna att starta arbetsflöden med Experience Fragments via tidslinjen
* Referensspåret visar nu var en Experience Fragment används i AEM
* Konfiguration av mallplatser tillåter nu författare att på global nivå eller mappnivå definiera vilka Experience Fragment-mallar som får användas
* Fasetterad sökning har nu stöd för avancerad filtrering, som publicerade/ej publicerade, som exporteras till sociala medier och Adobe Target
* Inloggning för enstaka sociala medier har lagts till när Experience Fragments exporteras till Pinterest eller Facebook
* Integrerade AEM Experience Fragments med Adobe Target. Synkronisering av Experience Fragments till Target skapar erbjudanden i Adobe Target som kan användas med Target Visual Experience Composer för att bädda in den i alla Target-aktiverade upplevelser.

### Översättning {#translation}

* Förbättrad användbarhet för AEM Translation-projekt:

   * Stöd för flera målspråk i ett projekt
   * Möjlighet att automatiskt befordra och ta bort översättningsstarter
   * Möjlighet att schemalägga återkommande körningar av översättningsprojekt (varje dag, varje vecka, varje månad, varje år)
   * Förbättrade översättningsprojektrutor med mer detaljerad statusinformation

* Introducerad uppdatering av omvänt översättningsminne, för att uppdatera översättningsminnet i ett översättningssystem från tredje part efter lokala innehållsredigeringar i AEM
* Översättningsarbetsflöden har nu stöd för grupperade språkrötter
* Lagt till möjlighet att tilldela godtyckliga namn till språkrötter, och använd JCR-egenskapen för mappning till ISO-kod
* Uppdateringar av smart översättning känner nu igen nya sidor som lagts till i en huvudgren för språk
* Introducerad översättningsstatusrapportering i listvyn Platsadministratörer

### Hantering av flera webbplatser (MSM) {#multi-site-management-msm}

* Förbättrad MSM-skalbarhet genom att använda ett Oak-baserat index jämfört med i minnet (LiveCopyIndex)

### Launches {#launches}

* Förbättrade prestanda för starter som innehåller stora platsträd och om många starter är aktiva
* Förbättrad automarknadsföring och publicering av startsidor med flera rotsidor.
* Ett problem som gjorde att den responsiva enhetsförhandsvisningen inte fungerade med sidor som redigerades i samband med en start har åtgärdats.

### Målinriktning och simulering av innehåll {#content-targeting-simulation}

* Stödmappar för att ordna segment baserat på plats/sammanhang (CQ-94620)
* Flyttade standardplats för segment till /conf för att ha plats-/kontextspecifika segmentlistor.

### AEM &amp; Adobe Target {#aem-amp-adobe-target-nbsp}

* Integrerade AEM Experience Fragments med Adobe Target. Synkronisering av Experience Fragments till Target skapar erbjudanden i Adobe Target som kan användas med Target Visual Experience Composer för att bädda in den i alla Target-aktiverade upplevelser.
* Adobe Target mbox.js version 63 ingår nu. Adobe rekommenderar att du byter implementering till at.js.
* at.js version 1.2.2 ingår nu. Adobe rekommenderar att du använder antingen Dynamic Tag Management (DTM) eller [Adobe Experience Platform Launch](https://www.adobe.com/enterprise/cloud-platform/launch.html) för att distribuera at.js till webbplatsen.

### AEM och Adobe Analytics {#aem-amp-adobe-analytics}

* s_code.js H.27.5 ingår nu. Adobe rekommenderar att du byter implementering till AppMeasurement.js
* AppMeasurement.js 1.8.0 ingår nu. Adobe rekommenderar att du använder antingen Dynamic Tag Management (DTM) eller [Adobe Experience Platform Launch](https://www.adobe.com/enterprise/cloud-platform/launch.html) för att etablera AppMeasurement.js på webbplatsen.

## Webbgrupper, tillägg {#communities-add-on}

Se sidan [Versionsinformation för webbgrupper](/help/release-notes/communities-release-notes.md)

## Skärmar, tillägg {#screens-add-on}

* Stöd för Screens Players har lagts till för att ansluta till AEM-publiceringsservrar för kommando-, kontroll- och kanalnedladdning (istället för direkt till AEM-författaren).
* Lagt till möjlighet att gruppera kanaltilldelningar i scheman
* Kanaltilldelningar har nu start- och slutdatum
* Device Dashboard visar nu spelarens skal och firmware-version
* Enhetsinstrumentpanelens lista visar anslutningsstatus för spelaren
* Google Chrome OS-stöd för AEM Screens Player har lagts till
* Microsoft Windows 10 har lagts till för AEM Screens Player

