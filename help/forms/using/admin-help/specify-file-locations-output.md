---
title: Ange filplatser för utdata
seo-title: Specify file locations for Output
description: Lär dig hur du anger filplatser för utdata.
seo-description: Learn how to specify file locations for Output.
uuid: 3287274f-85b5-4811-8abb-d347a9b80947
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 460bbb31-8187-469c-8102-b310093b6c03
exl-id: 5b8f04dd-6781-4126-8bb2-5d8b7a2f19c8
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '350'
ht-degree: 0%

---

# Ange filplatser för utdata {#specify-file-locations-for-output}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan ange var utdata ska söka efter vissa typer av filer som krävs.

1. Klicka på Tjänster > Utdata i administrationskonsolen.
1. Ange lämpliga alternativ under Platser.
1. Klicka på Spara.

## Platsinställningar {#locations-settings}

**Innehållsrot-URI:** URI eller absolut plats för databasen som formulär hämtas från. Detta värde kombineras med parametern sForm, som anges via API:t, för att skapa den absoluta sökvägen till det formulär som hämtas. Det här värdet kan referera till en katalog eller en webbplats som är tillgänglig via HTTP.

Standardvärdet är en tom sträng.

**XCI-konfigurationsfil:** Den relativa eller absoluta platsen för XCI-konfigurationsfilen som Output-tjänsten använder för återgivning. För ett relativt värde antas XCI-filen finnas i den distribuerbara EAR-filen för AEM formulär.

Standardvärdet är `com/adobe/formServer/PA/pa_output.xci`.

**Cacheplats:** Anger platsen för cacheminnet för utdatadisken. När du ändrar den här inställningen återställs all befintlig cacheinformation från den aktuella platsen och en ny cache skapas på den nya platsen. Välj något av följande alternativ:

**Standardplats:** Det här är standardvalet. När det här alternativet är markerat skapas cachen på en plats som är beroende av den programserver som du använder:

* **JBoss:** `[JBoss Home]\server\[install type]\svcdata\Output\Cache`
* **WebLogic:** `[WebLogic Home]\user_projects\domains\[aem-forms domain Name]\adobe\[forms server name]\Output\Cache`
* **WebSphere:** `[IBM Home]\WebSphere\AppServer\installedApps\adobe\server1\Output\Cache`

**Tillfällig katalog för LC:** Cachen skapas i en underkatalog till den AEM formulärkatalogen temporp, som anges i administrationskonsolen under Inställningar > Systeminställningar > Konfigurationer > Plats för tillfällig katalog. Underkatalogen heter `adobeoutput_[servername]`.

>[!NOTE]
>
>Om du använder ett tillfälligt rensningsverktyg bör du vara medveten om att funktionen inte påverkas om du tar bort de här katalogerna, men att prestandan kan påverkas avsevärt under en kort tid, tills den nya cachen skapas. Du kan undvika det här problemet genom att inte ta bort de här katalogerna samtidigt som du rensar den tillfälliga katalogen för AEM formulär.
