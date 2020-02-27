---
title: Åtkomst till UGC med SRP
seo-title: Åtkomst till UGC med SRP
description: När en webbplats är konfigurerad att använda ASRP eller MSRP lagras inte den faktiska UGC:n i AEM:s nodbutik (JCR)
seo-description: När en webbplats är konfigurerad att använda ASRP eller MSRP lagras inte den faktiska UGC:n i AEM:s nodbutik (JCR)
uuid: 5f9f8c9b-4c6a-45b0-96ff-14934380eba7
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: ee786a5c-b985-4d78-9063-6c79ae5e13e6
translation-type: tm+mt
source-git-commit: 565604feff7fa365a1c6b52b62a0b0eb681bb192

---


# Åtkomst till UGC med SRP {#accessing-ugc-with-srp}

## Om SRP {#about-srp}

Alla AEM Communities-komponenter och -funktioner bygger på ramverket för [sociala komponenter (SCF)](scf.md), som anropar SocialResourceProvider-API:t för att komma åt allt användargenererat innehåll (UGC).

Innan en communityplats skapas måste [lagringsresursprovidern (SRP)](working-with-srp.md) konfigureras för att välja en implementering som överensstämmer med den underliggande [topologin](topologies.md). SRP-implementeringarna baseras på tre lagringsalternativ:

1. [ASRP](asrp.md) - Adobe on demand-lagring
2. [MSRP](msrp.md) - MongoDB
3. [JSRP](jsrp.md) - JCR

## Om UGC-lagring {#about-ugc-storage}

Det som är viktigt att veta om lagring av UGC är att när en webbplats har konfigurerats att använda ASRP eller MSRP lagras inte den faktiska UGC:n i AEM:s [nodbutik](../../help/sites-deploying/data-store-config.md) (JCR).

Även om det kan finnas noder i JCR som skuggar UGC för att ge användbara metadata, ska dessa noder inte blandas ihop med själva UGC.

Se Översikt över [lagringsresursprovidern.](srp.md)

## Bästa praxis {#best-practice}

När du utvecklar anpassade komponenter bör utvecklare vara noga med att koda oberoende av den topologi som valts för tillfället, vilket ger flexibilitet att gå över till en ny topologi i framtiden.

### Anta att JCR inte är tillgängligt {#assume-jcr-not-available}

Metoder som är specifika för JCR bör undvikas.

Metoder som ska användas:

* Sling API (Sling Resource)
   * Anta inte att det finns JCR-noder

* OSGi Events
   * Anta inte att det finns JCR-händelser

* [Verktyg för sociala resurser](socialutils.md#socialresourceutilities-package)
* [SCF-verktyg](socialutils.md#scfutilities-package)

Metoder som ska undvikas:

* Nod-API
* JCR-händelser
* Starta arbetsflöden (som använder JCR-händelser)

### Använd söksamlingar {#use-search-collections}

Olika SRP kan ha olika inbyggda frågespråk. Vi rekommenderar att du använder metoder från [com.adobe.cq.social.ugc.api](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/ugc/api/package-summary.html) -paketet för att anropa rätt frågespråk.

Mer information finns i [Söka i Grundläggande](search-implementation.md).

## Resurser {#resources}

* [Community Content Storage](working-with-srp.md) - diskuterar tillgängliga SRP-alternativ för en gemensam lagringsplats för användargenererat innehåll
* [Översikt över](srp.md) lagringsresursprovidern - introduktion och databasanvändning - översikt
* [SRP och UGC Essentials](srp-and-ugc.md) - SRP-verktygsmetoder och -exempel
* [Search Essentials](search-implementation.md) - Essentials information for searching UGC
* [Omfaktorisering för SocialUtils](socialutils.md) - mappning av utgått verktygsmetoder till aktuella SRP-verktygsmetoder
