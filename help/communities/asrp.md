---
title: ASRP - Adobe lagringsresursleverantör
seo-title: ASRP - Adobe Storage Resource Provider
description: Konfigurera AEM Communities för att använda en relationsdatabas som gemensam lagringsplats
seo-description: Set up AEM Communities to use a relational database as its common store
uuid: 29826b44-633d-4586-8553-cd87ebe269a2
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 86349e4d-29ff-4baa-9fcd-c0ab1f0753e9
role: Admin
exl-id: 136c0913-c8b8-451d-bb28-3c3285c172a1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---

# ASRP - Adobe lagringsresursleverantör {#asrp-adobe-storage-resource-provider}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Om ASRP {#about-asrp}

När AEM Communities har konfigurerats att använda ASRP som gemensam lagringsplats är användargenererat innehåll (UGC) tillgängligt från alla författare- och publiceringsinstanser utan behov av synkronisering eller replikering.

Se även [Egenskaper för SRP-alternativ](working-with-srp.md#characteristics-of-srp-options) och [Rekommenderade topologier](topologies.md).

## Krav {#requirements}

Ytterligare en licens krävs för ASRP.

Kontakta din kontorepresentant för att konfigurera din AEM Communities-webbplats så att den använder ASRP för UGC:

* URL till datacenter (adress till ASRP-slutpunkten)
* Konsumentnyckel
* Hemlig nyckel
* Rapportsvitens ID:n

Konsumentnycklarna och de hemliga nycklarna delas över alla rapporteringsprogram för ett företag. Det finns en rapportsvit per innehavare.

## Konfiguration {#configuration}

### Välj ASRP {#select-asrp}

The [Konsol för lagringskonfiguration](srp-config.md) gör det möjligt att välja standardlagringskonfiguration, som identifierar vilken implementering av SRP som ska användas.

**On author**:

* Från global navigering: **[!UICONTROL Tools > Communities > Storage Configuration]**

![chlimage_1-310](assets/chlimage_1-310.png)

* Välj **[!UICONTROL Adobe Storage Resource Provider (ASRP)]**
* Följande information kommer från provisioneringsprocessen

   * **[!UICONTROL Data Center URL]**

      Dra ned för att välja det produktionsdatacenter som din kontorepresentant har identifierat

   * **[!UICONTROL Default Report Suite]**

      Ange namnet på standardrapportsviten

   * **[!UICONTROL Consumer Key]**

      Ange konsumentnyckeln

   * **[!UICONTROL Secret]**

      Ange den hemliga nyckeln

* Välj **[!UICONTROL Submit]**

Förbered publiceringsinstanserna:

* [Replikera krypteringsnyckeln](#replicate-the-crypto-key)
* [Replikera konfigurationen](#publishing-the-configuration)

Testa anslutningen när konfigurationen har skickats:

* Välj **[!UICONTROL Test Config]**
för varje författare och publiceringsinstans testar du anslutningen till datacentret från konsolen Lagringskonfiguration

* Kontrollera slutligen att webbplatsens URL:er för profildata kan dirigeras från datacentret av [externalisera länkar](#externalize-links).

### Replikera krypteringsnyckeln {#replicate-the-crypto-key}

Konsumentnyckeln och hemlig nyckel är krypterade. För att nycklarna ska kunna krypteras eller dekrypteras på rätt sätt måste den primära krypteringsnyckeln för Granite vara vara densamma för alla AEM.

Följ instruktionerna på [Replikera krypteringsnyckeln](deploy-communities.md#replicate-the-crypto-key).

### Gör länkar externt {#externalize-links}

Korrigera profil- och profilbildslänkar genom att kontrollera att [Konfigurera länkfunktionen](../../help/sites-developing/externalizer.md).

Var noga med att ange att domänerna ska vara URL:er som är routningsbara från URL:en för datacenter (ASRP-slutpunkt).

### Tidssynkronisering {#time-synchronization}

För att autentiseringen med ASRP-slutpunkten ska lyckas måste datorerna som kör ditt värdbaserade AEM Communities vara tidssynkroniserade, till exempel med [NTP (Network Time Protocol)](https://www.ntp.org/).

### Publicera konfigurationen {#publishing-the-configuration}

ASRP måste identifieras som det gemensamma arkivet för alla författar- och publiceringsinstanser.

Så här gör du den identiska konfigurationen tillgänglig i publiceringsmiljön:

* **On author**:

   * Navigera från huvudmenyn till **[!UICONTROL Tools > Operations > Replication]**
   * Välj **[!UICONTROL Activate Tree]**
   * **[!UICONTROL Start Path]**:

      * Bläddra till `/etc/socialconfig/srpc/`
   * Avmarkera **[!UICONTROL Only Modified]**
   * Välj **[!UICONTROL Activate]**


## Uppgradera från AEM 6.0 {#upgrading-from-aem}

>[!CAUTION]
>
>Om du aktiverar ASRP på en publicerad communitywebbplats lagras eventuell UGC i [JCR](jsrp.md) kommer inte längre att synas eftersom det inte finns någon synkronisering av data mellan lokal lagring och molnlagring.

**`AEM Communities Extension`** introducerades tidigare i AEM 6.0 sociala communities som en molntjänst. Från och med AEM 6.1 Communities behövs ingen molnkonfiguration. Välj bara ASRP från [lagringskonfigurationskonsol](srp-config.md).

På grund av den nya lagringsstrukturen är det nödvändigt att följa [uppgradera](upgrade.md#adobe-cloud-storage) Instruktioner när du uppgraderar från sociala communityn till Communities.

## Hantera användardata {#managing-user-data}

För information om *användare*, *användarprofiler* och *användargrupper*, som ofta används i publiceringsmiljön, besök

* [Användarsynkronisering](sync.md)
* [Hantera användare och användargrupper](users.md)

## Felsökning {#troubleshooting}

### UGC försvinner efter uppgradering {#ugc-disappears-after-upgrade}

Om du uppgraderar från en befintlig AEM 6.0 social community ska du följa [uppgraderingsinstruktioner](upgrade.md#adobe-cloud-storage), annars kommer UGC att *visas* att bli vilse.

### Autentiseringsfel {#authentication-errors}

Om du får autentiseringsfel mot datacenter-URL:en, och AEM error.log innehåller meddelanden om inaktuella tidsstämplar, kontrollerar du att tidssynkronisering pågår.

Vi rekommenderar att du använder ett verktyg som [NTP (Network Time Protocol)](https://www.ntp.org/) för att synkronisera alla AEM författare och publiceringsservrar.

### Nytt innehåll visas inte i sökningar {#new-content-does-not-appear-in-searches}

Adobe molnlagringsinfrastruktur använder *slutlig konsekvens* för att uppnå sina mål för skalning och prestanda. Därför är nytt innehåll inte tillgängligt direkt och det kan ta några sekunder innan det visas i sökresultaten.

Medan intervallet som påverkar den slutliga konsekvensen övervakas bör du kontakta din kontorepresentant om det tar längre tid än några sekunder innan nytt innehåll visas i sökningar.

### UGC är inte synlig i ASRP {#ugc-not-visible-in-asrp}

Kontrollera att ASRP har konfigurerats som standardprovider genom att kontrollera konfigurationen av lagringsalternativet. Som standard är lagringsresursprovidern JSRP, inte ASRP.

Gå till konsolen för lagringskonfiguration eller kontrollera den AEM databasen för alla författare och publiceringsinstanser:

* I JCR, om [/etc/socialconfig](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/)

   * Innehåller inte [srpc](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc) nod, det betyder att lagringsprovidern är JSRP
   * Om srpc-noden finns och innehåller nod [defaultconfiguration](http://localhost:4502/crx/de/index.jsp#/etc/socialconfig/srpc/defaultconfiguration)ska standardkonfigurationens egenskaper definiera ASRP som standardprovider
