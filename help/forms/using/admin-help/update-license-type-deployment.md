---
title: Uppdatera licenstypen för distributionen
seo-title: Update the license type for the deployment
description: Uppdatera licenstypen för distributionen genom att använda sidan Ändra licens i administrationskonsolen.
seo-description: Update the license type for the deployment by using the Change License page in administration console.
uuid: 0152635e-2c00-4944-b9b6-64b368589a91
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/get_started_with_administering_aem_forms_on_jee
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e4f31377-ccc9-4986-a3bf-ef2e83d12448
exl-id: 07671470-59dd-4290-be9a-465fcd89ac2d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 0%

---

# Uppdatera licenstypen för distributionen {#update-the-license-type-for-the-deployment}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Som en del av installationsprocessen för AEM formulär använde du Configuration Manager för att konfigurera och distribuera de AEM formulärmodulerna som du behöver. Som standard är dessa moduler konfigurerade med en 60-dagars utvärderingslicens. Använd sidan Ändra licens i administrationskonsolen för att ändra licenstypen för distributionen. De moduler som är distribuerade visas på sidan Ändra licens.

På sidan Ändra licens visas information om din licens:

* Den aktuella licenstypen
* Datum och tid då licensen senast uppdaterades
* Vem utförde den senaste uppdateringen?
* Licensens aktuella status
* Det datum då AEM formulär installerades
* Det datum då den aktuella licensen upphör att gälla

>[!NOTE]
>
>Licensändringen gäller alla distribuerade moduler. Innan du ändrar licenstypen ska du ta bort distributionen av moduler som inte är licensierade. Välj inte typen av produktionslicens om listan med distribuerade moduler innehåller andra moduler än de som du har köpt från Adobe.

## Uppdatera licenstypen {#update-the-license-type}

1. Klicka på Licensiering i administrationskonsolen.
1. Läs licensavtalet för AEM, välj Jag accepterar om du godkänner villkoren i avtalet och klicka sedan på Nästa.
1. Välj en licenstyp på sidan Ändra licens:

   * **EVAL:** 60-dagars utvärderingslicens
   * **DEV:** Permanent utvecklingslicens
   * **NFR:** 2-årig utvärderingslicens
   * **IDEV:** 1-årsprenumeration på Adobe Developer
   * **Produktion:** Permanent licens

1. Välj Ja, licensändringen är giltig för alla distribuerade moduler.
1. Klicka på Bekräfta licensändring. Ett meddelande om att licensen har uppdaterats visas.
