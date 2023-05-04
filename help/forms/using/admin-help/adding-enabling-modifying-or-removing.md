---
title: Lägga till, aktivera, ändra eller ta bort slutpunkter
seo-title: Adding, enabling, modifying, or removing endpoints
description: Lär dig hur du lägger till, aktiverar, ändrar och tar bort slutpunkter.
seo-description: Learn how to add, enable, modify and remove endpoints.
uuid: c53f225b-3d55-42f6-8982-0cd7dde0c4f5
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_endpoints
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 7d0d4f96-fc72-4e2b-a2cc-5741b0a30f74
exl-id: 8aed1439-aa39-4f75-909b-6a7ad7840a08
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 0%

---

# Lägga till, aktivera, ändra eller ta bort slutpunkter {#adding-enabling-modifying-or-removing-endpoints}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Lägga till en slutpunkt i en tjänst {#add-an-endpoint-to-a-service}

Slutpunkter kan bara läggas till i tjänster. En slutpunkt får inte finnas ensam. den måste vara associerad med en tjänst.

>[!NOTE]
>
>Du bör använda unika namn när du lägger till slutpunkter.

1. I administrationskonsolen klickar du på Tjänster > Program och tjänster > Tjänsthantering.
1. Klicka på den tjänst du vill konfigurera på sidan Tjänsthantering.
1. Välj den typ av slutpunkt som ska läggas till i listan på fliken Slutpunkter och klicka sedan på Lägg till.
1. Beroende på slutpunktstypen konfigurerar du ytterligare slutpunktsinställningar.

[Slutpunktsinställningar för bevakad mapp](/help/forms/using/admin-help/configuring-watched-folder-endpoints.md#watched-folder-endpoint-settings)

[Inställningar för e-postslutpunkt](/help/forms/using/admin-help/configuring-email-endpoints.md#email-endpoint-settings)

[Konfigurera slutpunkter för Aktivitetshanteraren](/help/forms/using/admin-help/configuring-task-manager-endpoints.md#configuring-task-manager-endpoints)

[Tar bort slutpunktsinställningar](/help/forms/using/admin-help/configuring-remoting-endpoints.md#remoting-endpoint-settings)

1. Klicka på Lägg till.

## Aktivera eller inaktivera en slutpunkt {#enable-or-disable-an-endpoint}

Som standard aktiveras nya slutpunkter automatiskt. Men om du har inaktiverat en slutpunkt måste du aktivera den för att den ska fungera.

Om du har problem med tjänster kan du inaktivera de associerade slutpunkterna för att felsöka problemet bättre. Du kan även inaktivera slutpunkter under regelbundet systemunderhåll eller när du uppgraderar en tjänst.

1. I administrationskonsolen klickar du på Tjänster > Program och tjänster > Endpoint Management.
1. Markera kryssrutan för slutpunkten på sidan Slutpunktshantering för att aktivera eller inaktivera och klicka på Aktivera eller Inaktivera.

## Ändra en slutpunkt {#modify-an-endpoint}

>[!NOTE]
>
>De ändringar du gör i en slutpunktskonfiguration med administrationskonsolen återspeglas inte i programdesigntidskopiorna. Om du distribuerar om ett program kommer alla ändringar som du har gjort i slutpunkterna med administrationskonsolen att gå förlorade.

1. I administrationskonsolen klickar du på Tjänster > Program och tjänster > Endpoint Management.
1. Klicka på slutpunkten som du vill ändra på sidan Slutpunktshantering.
1. Ändra slutpunktens namn, beskrivning och inställningar på sidan Uppdatera slutpunkt.

   >[!NOTE]
   >
   >Ta inte med ett &lt;-tecken i namnet eller beskrivningen eftersom det kortar av namnet eller beskrivningen som visas i Arbetsyta.

1. Klicka på Uppdatera om du vill spara ändringarna.

Du kan även utföra den här uppgiften från sidan Tjänsthantering genom att markera en tjänst och sedan klicka på fliken Slutpunkter.

## Ta bort en slutpunkt {#remove-an-endpoint}

1. I administrationskonsolen klickar du på Tjänster > Program och tjänster > Endpoint Management.
1. Markera kryssrutan för slutpunkten som ska tas bort på sidan Slutpunktshantering och klicka på Ta bort. Slutpunkten visas inte längre.
