---
title: Lagringskonfiguration
seo-title: Storage Configuration
description: Åtkomst till lagringskonsolen
seo-description: How to access the Storage Configuration Console
uuid: 6a5a71d5-6aaa-4635-8852-4dae33c497a9
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 71fac7e9-814a-48b5-b816-9bdcb2a05190
role: Admin
exl-id: 905b6dc5-cf17-4f58-a687-27e2910a0729
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '229'
ht-degree: 0%

---

# Lagringskonfiguration {#storage-configuration}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

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

   * Mer information finns i [välja MSRP](msrp.md#select-msrp)
   * Mer information finns i [välja DSRP](dsrp.md#select-dsrp)
   * Mer information finns i [markera ASRP](asrp.md#select-asrp)

* Välj **[!UICONTROL Submit]**

### Om JCR-lagring {#about-jcr-storage}

Observera att om inget val görs är standarddatabasen AEM JCR.

JCR är *not* en gemensam lagringsplats som delas av författaren och publiceringsmiljöer. Community-innehåll visas bara i den författar- eller publiceringsmiljö där det skapades.

Besök [JCR Store](jsrp.md) för ytterligare information.

>[!NOTE]
>
>Nodens frånvaro `srpc`under `/etc/socialconfig` anger standardvärdet [JCR-butik](jsrp.md).
