---
title: Helt grundläggande
seo-title: Tally Essentials
description: Översikt över klassen Tally
seo-description: Tally class overview
uuid: c369c6a1-9ced-4b5c-af43-8c03236eaa52
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 9941ba90-3d40-4c90-bca8-5db49603cbfa
exl-id: f04ec253-08b8-4ee2-9873-4a51549daeba
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '341'
ht-degree: 0%

---

# Helt grundläggande {#tally-essentials}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Tally är en abstrakt klass som tillhandahåller en standardmetod för att samla in feedback från medlemmar om hur de värdesätter specifika produkter och tjänster. Anonym feedback stöds inte. Besökaren måste registrera sig och logga in för att kunna delta och logga in för att kunna ändra sin feedback. Kravet på inloggning underlättar moderering och ökar värdet på feedback genom att förhindra flera inlägg.

Du kan skapa en anpassad tally-komponent genom att utöka den abstrakta tally-klassen.

[Länka](essentials-liking.md) är ett genomförande av tally som är en enkel form av att uttrycka en positiv åsikt.

[Omröstning](essentials-voting.md) är ett genomförande av tally som är en enkel form av ett positivt eller negativt yttrande.

[Klassificering](rating-basics.md) är en implementering av tally som använder ett stjärnsystem för att uttrycka olika åsikter, från positiva till negativa.

Från och med AEM 6.1 *omröstning* -komponenten är inte längre tillgänglig.

[Recensioner](reviews-basics.md) är en SCF-komponent som är en hybrid av [kommentarer](essentials-comments.md) och [värdering](rating-basics.md).

## Grundläggande för klientsidan {#essentials-for-client-side}

* [Anpassningar på klientsidan](client-customize.md)

## Grundläggande för serversidan {#essentials-for-server-side}

* [Tally API:er](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/api/package-summary.html)

* [Slutpunkter](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/endpoints/package-summary.html)

* [Anpassningar på serversidan](server-customize.md)

### Åtkomst till bokförda tallier (UGC) {#accessing-posted-tallies-ugc}

UGC bör modereras med någon av standardmetoderna för moderering.\
Se [Modererar användargenererat innehåll](moderate-ugc.md).

Från och med AEM 6.1 Communities används [gemensam lagringsplats](working-with-srp.md) för UGC omfattar programmatisk åtkomst till UGC oavsett vilket lagringsalternativ som valts (till exempel ASRP, MSRP eller JSRP).

**Platsen och formatet för användargenererat innehåll i databasen kan ändras utan förvarning**.

Se:

* [Översikt över lagringsresursprovider](srp.md) - introduktion och databasanvändning - översikt
* [SRP och UGC Essentials](srp-and-ugc.md) - SRP-verktygsmetoder och exempel
* [Åtkomst till UGC med SRP](accessing-ugc-with-srp.md) - riktlinjer för kodning
* [Omfaktorisering för SocialUtils](socialutils.md) - mappning av borttagna verktygsmetoder till aktuella SRP-verktygsmetoder
