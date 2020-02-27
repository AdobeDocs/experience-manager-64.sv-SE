---
title: Definiera testfall
seo-title: Definiera testfall
description: Dina testfall ska baseras på användningsfall och detaljerade kravspecifikationer
seo-description: Dina testfall ska baseras på användningsfall och detaljerade kravspecifikationer
uuid: 82dff825-da58-49a2-bf35-f5bb905e523d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 87a1f27a-765e-4882-9c06-5909e1610e1d
translation-type: tm+mt
source-git-commit: 0edddfde1e66ec487139f98e9ffafee885e61dfd

---


# Definiera testfall{#defining-your-test-cases}

Dina testfall ska baseras på följande:

**Användningsexempel**

* Dessa definierar den funktionalitet som krävs för interaktionen mellan Actors (roller som initierar vissa åtgärder) och systemet.
* Användningsärenden ska definieras av kunden.

**Detaljerad kravspecifikation**

* Alla funktions- och prestandakrav bör testas.

Provningarna bör tydligt definiera

* Förutsättningar. dessa kan omfatta specifika system, konfigurationer eller provningsupplevelser.
* Steg som skall följas. på en lämplig detaljnivå.
* Förväntade resultat.
* Tydliga kriterier för godkännande eller fel.

Möjligheten att automatisera testfall är uppenbart attraktiv eftersom den kan eliminera repetitiva uppgifter.

## Manuella eller automatiserade tester {#manual-versus-automated-tests}

Automatisering av testfall är dock en betydande investering, så vissa aspekter bör beaktas:

* Kräv tid, arbete och erfarenhet för att konfigurera och konfigurera.
* Om webbläsarbaserade uppdateringar är installerade finns det en ökad risk för problem. behöver ytterligare tid för att korrigera.
* Det är bara praktiskt för stora projekt.
* Bra när flera releaser genereras antingen för testning eller i den långsiktiga releaseplanen.

## Testa specifika aspekter {#testing-specific-aspects}

Vid testning av AEM är några specifika detaljer av särskilt intresse:

Skapa och publicera miljöer

Även om det ingår i [miljöer](/help/sites-developing/the-basics.md#environments) är det värt att betona en avgörande faktor för AEM när det gäller testning.

Du måste tänka på AEM som två program:

* i **redigeringsmiljönDen här instansen** tillåter författare att ange och publicera innehåll.
Detta har en liten(er), förutsägbar uppsättning användare, för vilka specifika funktioner och prestanda är avgörande.
* i **publiceringsmiljön** Den här instansen presenterar webbplatsen i dess publicerade form så att besökarna kan komma åt den.
Detta har vanligtvis en större uppsättning användare, där trafikvolymen inte alltid är helt förutsägbar. Prestanda är fortfarande avgörande - vid svar på förfrågningar. Cachelagring och lastbalansering måste också beaktas.

Även om de är samma programvara:

* har olika syften
* har olika krav på funktionalitet och prestanda
* har konfigurerats på ett annat sätt
* justeras separat
* ska var och en ha sin egen uppsättning godkännandetester

Med andra ord måste de testas separat och med olika testfall.

**Personanpassning**

Vid testning av personalisering ska varje enskilt användningsfall upprepas med flera användarkonton för att bevisa beteendet.

Cachelagring måste också kontrolleras för korrekt beteende.

**Dispatcher**

I de flesta projekt installeras Dispatcher för cachelagring och belastningsutjämning.

Testningen är svår (cachelagring sker på olika nivåer och på olika platser) och måste göras i svarta lådor. Viktiga aspekter att testa för är:

* **Noggrannhet**. se till att webbplatsbesökaren kan se innehållsuppdateringar.
* **Kontinuitet**. se till att webbplatsen fortfarande är tillgänglig när en server stängs av.
* **Klusterkluster** används för att tillhandahålla:
   * **Redundans** Om en server misslyckas tar andra servrar i klustret över bearbetningen.
   * **Prestandabelastningsbalansering med fullständig failover ökar prestanda för ett kluster.**

När det används för ett kundprojekt måste klustret testas för att bekräfta att konfigurationen fungerar korrekt.

## Testar program från tredje part {#testing-third-party-software}

Alla tredjepartsprogram som interagerar med AEM beskrivs i Detaljerade kravspecifikationer.

Alla provningar som krävs (beroende på det definierade omfånget) ska analyseras och rena provningar utföras.
