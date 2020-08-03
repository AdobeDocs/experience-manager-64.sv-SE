---
title: Versionsinformation för tjänsten Smart Content
seo-title: Versionsinformation för tjänsten Smart Content
description: Översikt över tjänsten Smart Content Service och kända problem med tjänsten.
seo-description: Översikt över tjänsten Smart Content Service och kända problem med tjänsten.
uuid: 5f474b36-3451-48ea-8669-b2d793638b06
content-type: reference
products: SG_EXPERIENCEMANAGER
discoiquuid: 9f88c773-ddeb-4c66-ac07-7d3aa196c51b
translation-type: tm+mt
source-git-commit: f8ba597c62379ba413309303c2ad066ab7afce1e
workflow-type: tm+mt
source-wordcount: '526'
ht-degree: 1%

---


# Versionsinformation för tjänsten Smart Content {#smart-content-service-release-notes}

Översikt över tjänsten Smart Content Service och kända problem med tjänsten.

Organisationer kräver att deras digitala resurser taggas baserat på den taxonomi som anställda, partners och kunder använder för att referera till och söka efter digitala resurser. Jämfört med generiska taggar är det enklare att identifiera och hämta resurser som är taggade baserat på företagstaxonomi genom taggbaserade sökningar.

Tjänsten Smart Content Service använder er företagsklonomi av AEM Assets för att automatiskt tagga digitala resurser, vilket ser till att de mest relevanta resurserna visas i sökningar.

Du måste utbilda Smart Content Service i en välstrukturerad uppsättning AEM resurser och taggar för att känna igen din företagstaxonomi. När tjänsten har tränats kan den använda dessa taggar på en liknande uppsättning resurser.

Tjänsten Smart Content Service drivs av Adobe Sensei-plattformen som gör det möjligt att utbilda bildigenkänningsalgoritmen i företagets taxonomi. Den här innehållsintelligensen används sedan för att tillämpa relevanta taggar på liknande resurser.

## Viktiga förbättringar {#key-improvements}

Tjänsten Smart Content innehåller följande viktiga förbättringar:

* Algoritmoptimering för att ytterligare förbättra modellprecision, återkallningsvärden
* Stöd för att återställa modellutbildning för alla taggar på innehavarnivå
* Stöd för förbättrade namnutrymmen för smarta taggar för att undvika konflikter
* Ny ersättningspolicy för modell för att undvika försämring på grund av omskolning
* Klientvis övervakning för användning av tjänsten
* Åtgärdar problem med klustring och anslutning, vilket ökar tillförlitligheten i tjänsten

## Åtgärdade problem {#fixed-issues}

Följande problem har åtgärdats i den här versionen:

* Arbetsprocesserna för taggning och utbildning avslutas om det inte går att ansluta till MySQL-servern. CQ-4242886

* Precisionsjusteringar har inte beräknats korrekt. CQ-4241797

* Felaktig PR-beräkning för modellen. CQ-4241381

* Utbildningsarbetsflödet saknar exempelresurser när de bearbetas från kö CQ-4240901

* Förbättrad precisionsåterkallning. CQ-4239895

* Modellersättningsprincip. CQ-4239886

* Bilder på mäns skjorta är taggade med kofttaggen. CQ-4239650

* Utbildningsexempel saknas vid driftsättning på scenen. CQ-4239483

* Utbildningen ska valideras på en uppsättning resurser som lämnats in för utbildning. CQ-4238834

* Det går inte att skapa modeller för negativ matning även om det finns minimala positiva/negativa för en tagg. CQ-4240741

* Felaktiga poster för negativt födoämne i loggar för utbildare. CQ-4240738

* Problem med förstagångsutbildning om taggar som lämnats in för utbildning är slumpmässiga negativ av varandra. CQ-4240118

* Improvisionera loggar för att övervaka användningen av tjänsten per klientorganisation. CQ-4239781

## Språk {#languages}

Tjänsten för smart innehåll är tillgänglig för följande språk:

* Engelska
* Tyska
* Franska
* Spanska
* Italienska
* Portugisiska
* Japanska
* Förenklad kinesiska
* Koreanska

## Länkar {#links}

* [Adobe Experience Manager produktsida på adobe.com](https://www.adobe.com/marketing-cloud/experience-manager.html)
* [Förbättrad dokumentation för smarta taggar](/help/assets/enhanced-smart-tags.md)

## Produktåtkomst och support (begränsade platser) {#product-access-and-support-restricted-sites}

Dessa webbplatser är bara tillgängliga för kunder. Om du är kund och behöver åtkomst kontaktar du din kontoansvarige på Adobe.

* [Produktåtkomst](https://login.marketing.adobe.com)
* [Nedladdning av produkt på licensing.adobe.com](https://licensing.adobe.com/).
* Produktuppdateringar, patchar och paket för ytterligare funktionalitet vid [programvarudistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html).
* [Kundsupport via Admin Console](https://adminconsole.adobe.com/). Mer information finns i [nya Adobe Customer Support Experience](https://docs.adobe.com/content/help/en/customer-one/using/home.html).
