---
title: Lagringskonfiguration
seo-title: Lagringskonfiguration
description: Åtkomst till lagringskonsolen
seo-description: Åtkomst till lagringskonsolen
uuid: 6a5a71d5-6aaa-4635-8852-4dae33c497a9
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 71fac7e9-814a-48b5-b816-9bdcb2a05190
translation-type: tm+mt
source-git-commit: 5e30bf76fd3304ed268c45cc8862a9c51c5d30f1
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---


# Lagringskonfiguration {#storage-configuration}

Lagringskonfiguration är ett sätt att identifiera det lagringsutrymme som valts för communityinnehåll, som också kallas användargenererat innehåll (UGC).

Den här inställningen informerar AEM Communities-koden om vilken implementering av lagringsresursprovidern som ska användas vid åtkomst till UGC och måste återspegla den topologi som fastställdes när AEM distribuerades.

En diskussion om lagringsalternativ och driftsättningstopologier finns på

* [Community Content Store](working-with-srp.md)
* [Rekommenderade topologier](topologies.md)

## Konsol för lagringskonfiguration {#storage-configuration-console}

![chlimage_1-188](assets/chlimage_1-188.png)

För att nå lagringskonsolen i redigeringsmiljön

* Från global navigering: **[!UICONTROL Tools > Communities > Storage Configuration]**

Så här väljer du ett annat lagringsalternativ än standard-JCR:

* välj ett alternativ
* Konfigurera korrekt

   * Se information om [val av MSRP](msrp.md#select-msrp)
   * Se information om [val av DSRP](dsrp.md#select-dsrp)
   * Se information om [val av ASRP](asrp.md#select-asrp)

* Välj **[!UICONTROL Submit]**

### Om JCR-lagring {#about-jcr-storage}

Observera att om inget val görs är standarddatabasen AEM JCR.

JCR är *inte* en gemensam lagringsplats som delas av författar- och publiceringsmiljöerna. Community-innehåll visas bara i den författar- eller publiceringsmiljö där det skapades.

Mer information finns i [JCR Store](jsrp.md).

>[!NOTE]
>
>Om noden `srpc`saknas under `/etc/socialconfig` indikerar standardlagret för [JCR](jsrp.md).

