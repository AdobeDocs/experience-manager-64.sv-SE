---
title: SRP - Community Content Storage
seo-title: SRP - Community Content Storage
description: Från och med AEM Communities 6.1 lagras användargenererat innehåll (UGC) i en enda gemensam butik som tillhandahålls av en leverantör av lagringsresurser (SRP)
seo-description: Från och med AEM Communities 6.1 lagras användargenererat innehåll (UGC) i en enda gemensam butik som tillhandahålls av en leverantör av lagringsresurser (SRP)
uuid: 651af1d7-70e8-4b56-8c01-871cb397678e
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: e975e026-e815-4445-be3e-b1237ed3f6b2
translation-type: tm+mt
source-git-commit: 8f169bb9b015ae94b9160d3ebbbd1abf85610465

---


# SRP - Community Content Storage {#srp-community-content-storage}

## Introduktion {#introduction}

Från och med AEM Communities 6.1 lagras användargenererat innehåll (UGC) i en enda gemensam butik som tillhandahålls av en leverantör av lagringsresurser (SRP). Det finns flera SRP-alternativ att välja mellan, till exempel ASRP, MSRP och JSRP.

Till skillnad från tidigare versioner finns det ingen omvänd/framåtriktad replikering av UGC mellan AEM-instanser. I stället gör SRP att UGC är direkt tillgängligt för att skapa, läsa, uppdatera och ta bort (CRUD) åtgärder från alla författare- och publiceringsinstanser, med undantag för JSRP.

Nedan följer [egenskaperna för varje SRP-alternativ](#characteristics-of-srp-options), som är viktig information för beslutsprocessen när man väljer lämplig SRP och [underliggande driftsättning](topologies.md).

Mer information om användningen av SRP för UGC finns i Översikt över [lagringsresursprovidern](srp.md).

>[!NOTE]
>
>SRP gäller endast för communityinnehåll. Det påverkar inte var webbplatsinnehållet lagras ([nodarkiv](../../help/sites-deploying/data-store-config.md)) och påverkar inte den säkra hanteringen av användarregistrering, användarprofiler och användargrupper mellan AEM-instanser (se även [Hantera användardata](#managing-user-data)).

>[!CAUTION]
>
>Från och med AEM 6.1 replikeras [aldrig](#ugc-never-replicated)UGC.
>
>När distributionen inte innehåller någon gemensam butik, t.ex. [JSRP](topologies.md#jsrp) -standardtopologi, visas bara UGC i den AEM-publicerings- eller författarinstans där den angavs. Endast om topologin innehåller ett publiceringskluster visas UGC:n på alla publiceringsinstanser.

## Egenskaper för SRP-alternativ {#characteristics-of-srp-options}

[ASRP - Adobe Storage Resource Provider](asrp.md)\
Med det här alternativet lagras användargenererat innehåll på fjärrbasis i en molntjänst som hanteras av Adobe. Det krävs ytterligare en licens och att man samarbetar med en kontorepresentant för att tillhandahålla kontot för den specifika licensen.

* Kräver en tillhörande molntjänst som tillhandahålls och stöds av Adobe för att lagra communityinnehåll
* Kräver val av datacenter i en specifik geografi (USA, EMEA, APAC)
* Kräver all programmatisk åtkomst till UGC via SRP API
* Lämplig för TjärMK-publiceringsservergrupp
* Passar när det inte finns någon avsikt att investera i lokal lagring

>[!NOTE]
>
>Det finns en gräns för att överföra bilagor till inlägg (eller kommentarer) i ASRP, som är 50 MB.

[MSRP - lagringsresursprovider för MongoDB](msrp.md)\
Med det här alternativet sparas UGC direkt i en lokal MongoDB-instans.

* Kräver en lokal, licensierad installation av MongoDB för att lagra communityinnehåll
* Kräver en lokal installation av Apache Solr
* Kräver all programmatisk åtkomst till UGC via SRP API
* Lämplig för en befintlig StjärtMK-publiceringsgrupp
* Passar för ett MongoMK- eller RdbMK-kluster
* Passar när stora volymer av communityinnehåll förväntas

[DSRP - Resursprovider för relativ databaslagring](dsrp.md)\
Med det här alternativet sparas UGC direkt i en lokal MySQL-databasinstans.

* Kräver en lokal installation av MySQL för att lagra communityinnehåll
* Kräver en lokal installation av Apache Solr
* Kräver all programmatisk åtkomst till UGC via SRP API
* Lämplig för en befintlig StjärtMK-publiceringsgrupp
* Passar för ett MongoMK- eller RdbMK-kluster
* Passar när stora volymer av communityinnehåll förväntas

[JSRP - JCR-lagringsresursprovider](jsrp.md)\
Det finns ingen gemensam lagringsplats med standardalternativet. UGC:n sparas bara i samma JCR-databas som den AEM-instans där den angavs.

* Lagrar communityinnehåll i JCR-databasen för AEM-författaren eller publiceringsinstansen som det publicerades i
* Kräver all programmatisk åtkomst till UGC via SRP API
* Kräver ett publiceringskluster om mer än en publiceringsinstans har distribuerats (det finns ingen replikeringsmekanism bland publiceringsinstanser i en tarMK-servergrupp)
* Moderering utförs endast i publiceringsmiljön (det finns ingen omvänd/framåtriktad replikeringsmekanism mellan författaren och publiceringen)
* I allmänhet bäst för utveckling, demonstrationer och utbildning

## Konfigurerar SRP {#configuring-srp}

Ange standardlagringsalternativet, baserat på den underliggande distributionen, via konsolen [för](srp-config.md)lagringskonfiguration.

Konfigurationsinformation om varje alternativ finns i:

* [ASRP - Adobe Storage Resource Provider](asrp.md)
* [MSRP - lagringsresursprovider för MongoDB](msrp.md)
* [DSRP - Resursprovider för relativ databaslagring](dsrp.md)
* [JSRP - JCR-lagringsresursprovider](jsrp.md)

Om inget lagringsalternativ är aktivt, aktiveras JSRP som standard.

## Additional Information {#additional-information}

### UGC har aldrig replikerats {#ugc-never-replicated}

I redigeringsmiljön skapar en författare sidinnehåll och replikerar det till publiceringsmiljön. När en sida innehåller en interaktiv AEM Communities-funktion, till exempel kommentarer, granskningar, forum, blogg eller QnA, resulterar interaktionen mellan medlemmar (inloggade besökare) på en publiceringsinstans i användargenererat innehåll (UGC) som läggs in i publiceringsmiljön.

Tidigare replikerades det här communityinnehållet bakåt till författarinstanser och från författare replikerat till publiceringsinstanser. Det var problematiskt att upprätthålla konsekvensen mellan AEM-instanser med omvänd och framåtriktad replikering.

Från och med AEM Communities 6.1 har behovet av att replikera UGC eliminerats genom att använda delad lagring för UGC, vilket beskrivs ovan.

När platsinnehållet replikeras replikeras aldrig UGC.

### Hantera användardata {#managing-user-data}

Det är också av intresse för communityn som [*användare *,* användargrupper *och* användarprofiler *](users.md). Dessa användarrelaterade data, som skapas och uppdateras i publiceringsmiljön, måste göras tillgängliga för andra publiceringsinstanser när topologin är en[publiceringsgrupp](../../help/sites-deploying/recommended-deploys.md#tarmk-farm).

Från och med AEM Communities 6.1 synkroniseras användarrelaterade data med Sling-distribution i stället för replikering. Mer information finns i [Användarsynkronisering](sync.md).

### Uppgradera till AEM Communities 6.2 {#upgrading-to-aem-communities}

Vid uppgradering till AEM Communities 6.3, om befintlig UGC måste behållas, bör åtgärder vidtas beroende på om AEM 5.6.1- eller AEM 6.0-communityn använde Adobe On-Demand-lagring eller lokal lagring av UGC.

Mer information finns i [Uppgradera till AEM Communities 6.3](upgrade.md).
