---
title: Distribuera AEM Forms-app
seo-title: Distribute AEM Forms app
description: Använd MDM (Mobile Device Management) för storskalig driftsättning av appar på mobila enheter.
seo-description: Use Mobile Device Management (MDM) for the large-scale deployment of apps on mobile devices.
uuid: 8a2ce42b-5e9b-42c1-a945-c069f6152f6e
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 5756cb52-dd47-4277-981c-fd0af9a20638
exl-id: c1bf0a0e-70f7-41dd-8b1a-c114d89a265b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 0%

---

# Distribuera AEM Forms-app {#distribute-aem-forms-app}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

MDM (Mobile Device Management) möjliggör storskalig driftsättning av appar på mobila enheter.

>[!NOTE]
>
>Distributionen gäller endast för iOS- och Android-enheter.

## De viktigaste funktionerna i MDM-lösningar: {#main-features-generally-provided-by-mdm-solutions}

* Aktivera enhetsregistrering i företagsmiljön
* Tillåt konfiguration och uppdatering av enhetsinställningar
* Säkerställ regelefterlevnaden.
* Säker mobil åtkomst till företagsresurser

En MDM-lösning tillsammans med hantering av mobilappar gör att du kan hantera interna, offentliga och köpta appar på företagets mobila enheter.

MDM-administratören kan överföra både ipa- och apk-filer till MDM-servern och styra vilka användare som kan komma åt ipa- eller apk-filerna. Administratören kan också styra profilinställningarna för respektive program.

## Profilinställningar som påverkar AEM Forms-appen {#profile-settings-affecting-the-aem-forms-app-br}

Följande profilinställningar på enheten påverkar hur AEM Forms-appen fungerar på din enhet:

* **Tillåt användning av kamera** i **Enhetsfunktioner** section

Om du inaktiverar **Tillåt användning av kamera**, kamerans funktion i [Fotografanteckning](/help/forms/using/add-attachments.md) fungerar inte. Du måste aktivera det här alternativet om du vill använda kameran i appen.

* **Kräv lösenord på enheten** i avsnittet Lösenordspolicyer

Aktivera **kryptering av programdata** rekommenderar vi att du aktiverar **lösenord** på din enhet. Om lösenordet inte har angetts på enheten krypteras inte programdata som lagras på enheten.
