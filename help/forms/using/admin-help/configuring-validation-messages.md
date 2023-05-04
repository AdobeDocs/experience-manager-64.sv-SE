---
title: Konfigurera valideringsmeddelanden
seo-title: Configuring validation messages
description: Lär dig hur du anger hur valideringsmeddelanden ska visas och deras plats i förhållande till formuläret som returneras i webbläsaren.
seo-description: Learn how to specify how validation messages are displayed and their location relative to the form returned in the web browser.
uuid: f6bff4fa-f90f-4135-ae40-7ab3d3613122
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_forms
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 5f2f8129-e45e-4f3f-ae30-c09330d0e152
exl-id: 2016ac85-12a1-42cb-bc03-fced94947010
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '386'
ht-degree: 0%

---

# Konfigurera valideringsmeddelanden {#configuring-validation-messages}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

För formulär som återges som HTML visas formulärvalideringsfel som inträffar för användaren. Du kan anpassa hur valideringsmeddelanden visas. Beroende på var valideringsmeddelandena visas kan du även styra platsen för meddelandet i formuläret och storleken på ramkanten.

## Ange hur valideringsmeddelanden ska visas {#specify-how-validation-messages-are-displayed}

1. Klicka på Tjänster > Formulär i administrationskonsolen.
1. Välj något av följande alternativ i rapportlistan under Valideringsutdata:

   **Meddelanderuta:** Om du vill visa valideringsmeddelanden i en separat dialogruta.

   **Ram:** Om du vill visa valideringsmeddelanden i en bildruta i samma fönster.

   **Ingen bildruta:** Om du vill visa valideringsmeddelanden i samma fönster. Det här värdet är standardvärdet.

   **Via API (med data):** Returnera valideringsmeddelandena via API (med data). Valideringsmeddelandena visas inte på skärmen.

   **Via API (med formulär):** Returnera valideringsmeddelandena via API (med formuläret). Valideringsmeddelandena visas inte på skärmen.

   **Ingen:** Visa inte valideringsmeddelanden.

1. Klicka på Spara.

## Ange platsen för valideringsmeddelanden i förhållande till formuläret som returneras i webbläsaren {#specify-the-location-of-validation-messages-relative-to-the-form-returned-in-the-web-browser}

Om Rapportering är inställt på Bildruta eller Ingen bildruta kan du ange plats för valideringsmeddelanden.

1. Välj något av följande alternativ i listan Position under Valideringsutdata:

   **Vänster:** Om du vill visa valideringsmeddelanden till vänster i webbläsaren.

   **Höger:** Om du vill visa valideringsmeddelanden till höger i webbläsaren.

   **Överkant**: Om du vill visa valideringsmeddelanden högst upp i webbläsaren. Det här värdet är standardvärdet.

   **Nederkant**: Om du vill visa valideringsmeddelanden längst ned i webbläsaren.

1. Klicka på Spara.

## Ange ramens kantlinjestorlek {#specify-the-frame-border-size}

När du har valt Rapportering som Bildruta kan du ange ramens kantstorlek.

1. Under Valideringsutdata skriver du ramkantens storlek i pixlar i rutan Kantstorlek.

   Kantstorleken måste vara lika med eller större än 0. Standardvärdet är 1.

1. Klicka på Spara.
