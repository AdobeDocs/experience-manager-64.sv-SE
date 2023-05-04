---
title: Konfigurerar fjärrslutpunkter
seo-title: Configuring Remoting endpoints
description: Lär dig hur du konfigurerar fjärrslutpunkter.
seo-description: Learn how to configure remoting endpoints.
uuid: 4d4f9274-dcae-4b9f-975a-575376c2f89c
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_endpoints
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: aab9d622-d76b-4100-9ca6-e5b86f543381
exl-id: d8e31f99-0558-4634-ae35-f4a09f34ad6d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---

# Konfigurerar fjärrslutpunkter {#configuring-remoting-endpoints}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

En fjärrslutpunkt gör att ett program som skapats med Flex kan anropa tjänsten med hjälp av (borttaget för AEM formulär) AEM form Remoting. En fjärrslutpunkt skapas automatiskt för varje aktiverad tjänst. Ett Flex-mål som har samma namn som slutpunkten skapas, och Flex-klienter kan skapa fjärrobjekt som pekar på det här målet för att anropa åtgärder på den aktuella tjänsten.

## Tar bort slutpunktsinställningar {#remoting-endpoint-settings}

**Autentiseringsmetod för Flex-klient:** Bestämmer vilken typ av svar som servern skickar tillbaka till klienten när den anropade tjänsten är säkerhetsaktiverad, den anropade åtgärden inte stöder anonyma anrop och klienten skickar antingen inga eller ogiltiga autentiseringsuppgifter.
