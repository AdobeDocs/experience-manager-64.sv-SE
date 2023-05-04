---
title: Namnkonventioner
seo-title: Naming Conventions
description: Bindestreck i Java-paketnamn
seo-description: Hyphens in Java Package Name
uuid: 48086e6c-c35b-4ffc-b216-d01feca7bf9a
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 5271feb9-70c6-4c82-8ac7-34a63d80e3aa
exl-id: f5a63642-9f2c-436f-bd40-4459545a0ddf
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Namnkonventioner {#naming-conventions}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Bindestreck i Java-paketnamn {#hyphens-in-java-package-name}

När du skapar en plats för en Java-klass måste du vara medveten om att paketnamnet måste matcha databasmappens namn med eventuella bindestreck i sökvägen som escape-konverterats.

När du använder bindestreck i namn på databasobjekt rekommenderas AEM utveckling, men bindestreck är ogiltiga i Java-paketnamn.

Den underliggande CRX-plattformen måste kunna skilja mellan det faktiska understrecket &#39;_&#39; och ett bindestreck &#39;-&#39;. I JCR måste därför bindestrecket ersättas med dess unicode-värde (u002d) och escape-konverteras med understrecket &#39;_&#39;.

Om databassökvägen till exempel är **/apps/my-example/component/info/Info.java**, ska paketnamnet vara `java package apps.my_002dexample.component.info;`

Observera att ett understreck måste undantas på liknande sätt, så att `_` blir `_005f`.
