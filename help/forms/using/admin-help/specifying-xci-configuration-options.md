---
title: Ange XCI-konfigurationsalternativ
seo-title: Specifying XCI configuration options
description: Lär dig hur du anger XCI-konfigurationsalternativ.
seo-description: Learn how to specify XCI configuration options.
uuid: 5d3c10c1-4a93-4336-b311-20faaf835b9f
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 162c9fda-f4d4-4ad5-a9ab-7554828e821c
exl-id: 7a13b13f-3eee-4fc0-8957-bd42f43119e9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 0%

---

# Ange XCI-konfigurationsalternativ {#specifying-xci-configuration-options}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med Forms kan du ange en anpassad XCI-fil som ska användas för återgivning. (Se [Konfigurera platser för Forms](/help/forms/using/admin-help/configuring-locations-forms.md#configuring-locations-for-forms).) Som standard åsidosätter Forms några av de alternativ som anges i XCI-filen, bland annat följande:

* `config/present/xdp/packets`
* `config/present/pdf/creator`
* `config/present/pdf/producer`
* `config/present/pdf/compression/compressObjectStream`

Du kan välja alternativ som avbryter åsidosättningen för alternativen ovan. I så fall använder Forms värdena som anges i den anpassade XCI-filen.

1. Klicka på Tjänster > Forms i administrationskonsolen.
1. Markera eller avmarkera kryssrutan Använd XCI-standardalternativ för system. När det här alternativet är markerat använder Forms standardvärden för inställningarna för paket, skapare, producent och compressObjectStream. När det här alternativet är avmarkerat används de värden som anges i den anpassade XCI-filen i Forms.
1. Klicka på Spara.
