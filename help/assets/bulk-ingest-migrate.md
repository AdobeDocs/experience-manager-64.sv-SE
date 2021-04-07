---
title: Installerar funktionspaket 18912 för migrering av gruppresurser
seo-title: Installerar funktionspaket 18912 för migrering av gruppresurser
description: Med funktionspaketet 18912 kan du antingen importera resurser gruppvis via FTP eller migrera resurser från Dynamic Media Classic till Dynamic Media i AEM. Detta tillvalspaket finns tillgängligt från Adobe support.
seo-description: Med funktionspaketet 18912 kan du antingen importera resurser gruppvis via FTP eller migrera resurser från Dynamic Media Classic till Dynamic Media i AEM. Detta tillvalspaket finns tillgängligt från Adobe support.
uuid: 316d77e3-3d61-4cf0-8955-726ee54e268c
contentOwner: rbrough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 6198e613-a867-49a8-b9a5-a05e7889821c
exl-id: f9bb59f6-39a5-4804-8abe-12783d4162c9
feature: Konfiguration
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---

# Installerar funktionspaket 18912 för migrering av gruppresurser {#installing-feature-pack}

Installationen av funktionspaket 18912 är _valfri_.

Med funktionspaketet 18912 kan du antingen importera resurser i grupp direkt till Dynamic Media - Scene 7-läge AEM via FTP, eller migrera resurser från Dynamic Media Classic till Dynamic Media - Scene7-läge på AEM. Funktionspaketet är tillgängligt från [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html).

>[!NOTE]
>
>Du kan använda funktionspaketet för att massmigrera resurser på egen hand från Dynamic Media Classic till Dynamic Media - Scen 7 i AEM eller massmigrera resurser med FTP-funktionen i Dynamic Media Classic, men Adobe rekommenderar inte *den här metoden på grund av komplexiteten.*
>
>Det innebär att paket med flyttningsfunktioner, som detta, endast *stöds* som en del av ett migreringsprojekt via [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html).

Innan du kan installera det här funktionspaketet måste du först skapa en tjänstanvändare och ange den informationen till Adobe.

Se även [Konfigurera Dynamic Media - Scene7-läge](https://helpx.adobe.com/experience-manager/6-4/assets/using/config-dms7.html).

**Om du vill installera funktionspaket 18912 för migrering** av gruppresurser

1. Navigera till **[!UICONTROL Tools > Security > Users > Create User]** i AEM. Den här tjänstanvändaren måste ha läs-/skrivbehörighet till `/content/dam`.
1. I fälten **[!UICONTROL ID]** och **[!UICONTROL Password]** anger du ett användarnamn och lösenord; till exempel `FTP User`. Det här namnet visas på tidslinjen som den användare som skapade resursen. När en resurs överförs från FTP betraktas en resurs som skapad när den överförs till FTP-servern och skickas till AEM.
1. Kontakta [Adobe Enterprise Support för Experience Manager](https://helpx.adobe.com/se/contact/enterprise-support.ec.html) för att få tillgång till funktionspaket 18912 för hämtning. Du kan behöva följande information när du kontaktar supporten:

   * Serverns IP-adress för din Author-instans, inklusive portnumret (portnumret är som standard 4502).
   * AEM användarnamn och lösenord från föregående steg.

1. Adobe Enterprise Support för AEM ger dig FTP-inloggningsuppgifter och tillgång till funktionspaket 18912.

1. Installera funktionspaketet 18912 när du får det.

   Mer information om hur du använder programdistribution och paket i AEM finns i [Arbeta med paket](/help/sites-administering/package-manager.md).
