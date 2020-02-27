---
title: Installerar funktionspaket 18912 för migrering av gruppresurser
seo-title: Installerar funktionspaket 18912 för migrering av gruppresurser
description: Med funktionspaket 18912 kan du antingen importera resurser i grupp via FTP eller migrera resurser från Dynamic Media Classic till Dynamic Media i AEM. Det här tillvalspaketet finns tillgängligt från Adobes support.
seo-description: Med funktionspaket 18912 kan du antingen importera resurser i grupp via FTP eller migrera resurser från Dynamic Media Classic till Dynamic Media i AEM. Det här tillvalspaketet finns tillgängligt från Adobes support.
uuid: 316d77e3-3d61-4cf0-8955-726ee54e268c
contentOwner: rbrough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 6198e613-a867-49a8-b9a5-a05e7889821c
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Installerar funktionspaket 18912 för migrering av gruppresurser {#installing-feature-pack}

Installation av funktionspaket 18912 är _valfritt_.

Med funktionspaket 18912 kan du antingen importera resurser i bulk direkt till Dynamic Media - Scene 7-läge på AEM via FTP eller migrera resurser från Dynamic Media Classic till Dynamic Media - Scene7-läge på AEM. Funktionspaketet finns på [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html).

>[!NOTE]
>
>Du kan använda funktionspaketet för att massmigrera resurser på egen hand från Dynamic Media Classic till Dynamic Media - Scene 7 i AEM eller massmigrera resurser med FTP-funktionen i Dynamic Media Classic, men Adobe rekommenderar *inte* den här metoden på grund av den komplexitet som detta medför.
>
>Det innebär att paket med migreringsfunktioner, som detta, *endast* stöds som en del av ett migreringsprojekt via [Adobe Professional Services](https://www.adobe.com/experience-cloud/consulting-services.html).

Innan du kan installera det här funktionspaketet måste du först skapa en tjänstanvändare och ange den informationen till Adobe.

Se även [Konfigurera dynamiska media - Scene7-läge](https://helpx.adobe.com/experience-manager/6-4/assets/using/config-dms7.html).

**Om du vill installera funktionspaket 18912 för migrering** av gruppresurser

1. I din AEM-instans går du till **[!UICONTROL Verktyg > Dokumentskydd > Användare > Skapa användare]**. Den här tjänstanvändaren måste ha läs-/skrivbehörighet till `/content/dam`.
1. I fälten **[!UICONTROL ID]** och **[!UICONTROL Lösenord]** anger du ett användarnamn och lösenord. till exempel `FTP User`. Det här namnet visas på tidslinjen som den användare som skapade resursen. När en resurs överförs från FTP betraktas en resurs som skapad när den överförs till FTP-servern och överförs till AEM.
1. Kontakta [Adobe Enterprise Support för Experience Manager](https://helpx.adobe.com/contact/enterprise-support.ec.html) för att få tillgång till funktionspaketet 18912 för nedladdning. Du kan behöva följande information när du kontaktar supporten:

   * Serverns IP-adress för din Author-instans, inklusive portnumret (portnumret är som standard 4502).
   * Användarnamn och lösenord för AEM-tjänsten från föregående steg.

1. Adobe Enterprise Support för AEM ger dig FTP-inloggningsuppgifter och tillgång till funktionspaket 18912.

1. Installera funktionspaketet 18912 när du får det.

   Mer information om hur du använder paketdelning och paket i AEM finns i [Arbeta med paket](/help/sites-administering/package-manager.md) .

