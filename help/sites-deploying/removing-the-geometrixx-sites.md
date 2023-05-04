---
title: Ta bort Geometrixx
seo-title: Removing the Geometrixx Sites
description: Lär dig hur du tar bort exempelinnehållet i Geometrixx.
seo-description: Learn how to remove the sample Geometrixx content.
uuid: 07d20837-3375-4e64-bb07-3e4d10452335
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
discoiquuid: 56761a36-ce21-46e1-856f-75a7e94acae9
exl-id: 495031fb-b559-4071-abc4-93d238ce136d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '168'
ht-degree: 0%

---

# Ta bort Geometrixx{#removing-the-geometrixx-sites}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM innehåller ett antal exempelwebbplatser för Geometrixx. Du kan ta bort det här exempelinnehållet via **Pakethanteraren**.

De enskilda geometrixx-relaterade paketen är:

* `cq-geometrixx-outdoors-ugc-pkg-*<version>*.zip`
* `cq-geometrixx-pkg-*<version>*.zip`
* `cq-content-mac-*<version>*.zip`
* `cq-geometrixx-login-pkg-*<version>*.zip`
* `cq-geometrixx-users-pkg-*<version>*.zip`
* `cq-geometrixx-workflow-pkg-*<version>*.zip`
* `cq-geometrixx-outdoors-pkg-*<version>*.zip`
* `cq-geometrixx-commons-pkg-*<version>*.zip`
* `cq-geometrixx-media-pkg-*<version>*.zip`

Om du vill ta bort ett enskilt paket klickar du på **Avinstallera** på det paketet.

Det finns också ett superpaket:

* `cq-geometrixx-all-pkg-5.6.12.zip`

Detta paket innehåller alla ovanstående individuella paket. Om du vill ta bort allt geometrixrelaterat innehåll samtidigt klickar du på **Avinstallera** på det här paketet. Superpaketet försätts i det avinstallerade läget och alla enskilda paket försvinner från pakethanterarvyn.

Du har nu en tom AEM utan några demonstrationssajter.

>[!NOTE]
>
>När du uppgraderar installeras geometrixx-webbplatser om automatiskt. Du kan behöva ta bort geometrixx-webbplatser efter uppgraderingen om du inte vill ha dessa exempel.
