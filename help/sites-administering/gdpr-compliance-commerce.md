---
title: AEM Commerce - GDPR-beredskap
seo-title: AEM Commerce - GDPR Readiness
description: "AEM Commerce - GDPR-beredskap"
seo-description: null
uuid: 7ca26587-8cce-4c75-8629-e0e5cfb8166c
contentOwner: carlino
discoiquuid: c637964a-dfcb-41fe-9c92-934620fe2cb3
feature: Commerce Integration Framework
exl-id: c5002812-cbc6-4b3e-85be-3446630b4e8a
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 0%

---

# AEM Commerce - GDPR-beredskap{#aem-commerce-gdpr-readiness}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!IMPORTANT]
>
>GDPR används som exempel i avsnitten nedan, men de ingående detaljerna är tillämpliga på alla dataskydds- och sekretessbestämmelser. såsom GDPR, CCPA osv.

Europeiska unionens allmänna dataskyddsförordning om integritetsskydd får verkan från och med maj 2018. Mer information finns i [GDPR-sidan på Adobe Privacy Center](https://www.adobe.com/privacy/general-data-protection-regulation.html).

>[!NOTE]
>
>Se [AEM GDPR-beredskap](/help/managing/data-protection-and-privacy.md) för mer information.

![screen_shot_2018-03-22at11606](assets/screen_shot_2018-03-22at111606.jpg)

I våra färdiga Commerce-integreringar är AEM upplevelselagret, konsumera tjänster och skicka tillbaka data till kundens handelsplattform som körs i headlessläge.

För vissa e-handelsplattformar lagrar vi profilinformation ( `/home/users`) och e-handelstoken (för inloggning på e-handelsplattformen) i AEM. Läs mer om dessa användningsområden [Hantera GDPR-begäranden för AEM](/help/sites-administering/handling-gdpr-requests-for-aem-platform.md).

![screen_shot_2018-03-22at11621](assets/screen_shot_2018-03-22at111621.jpg)

## Hantera GDPR-förfrågningar för AEM {#handling-gdpr-requests-for-aem-commerce}

För integreringen av Salesforce Commerce Cloud lagrar AEM Commerce ingen GDPR-relevant information. Du bör vidarebefordra din begäran till [Salesforce Cloud](https://documentation.demandware.com/).

För hybris- och IBM WebSphere-integreringar finns det vissa data i AEM. Du bör använda [AEM GDPR-instruktioner](/help/sites-administering/handling-gdpr-requests-for-aem-platform.md) och fundera över följande frågor:

1. **Var lagras/används mina data?** Cachelagrad användarprofilinformation som namn, användaridentifierare för e-handel, token, lösenord, adressdata o.s.v. visas från AEM.
1. **Med vem delar jag de täckta GDPR-uppgifterna?** Alla uppdateringar av GDPR-relevanta data i AEM Commerce lagras inte (utom relevant profilinformation, som nämns ovan) utan läggs tillbaka i koden för e-handelsplattformen.
1. **Så här tar du bort mina användardata**? Ta bort användarprofilen i AEM och anropa användarborttagningen på handelsplattformen.

>[!NOTE]
>
>Ta en titt på [hybris wiki](https://wiki.hybris.com/) eller [Websphere Commerce-dokumentation](https://www-01.ibm.com/support/docview.wss?uid=swg27036450) vid behov.
