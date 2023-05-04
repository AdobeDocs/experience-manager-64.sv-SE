---
title: Bakåtkompatibilitet i AEM 6.4
seo-title: Backward Compatibility in AEM 6.4
description: Lär dig hur du kan göra dina program och konfigurationer kompatibla med AEM 6.4
seo-description: Learn how to keep your apps and configurations compatible with AEM 6.4
uuid: 2fa8525e-7f3b-4096-ac85-01c2c76bc9ac
contentOwner: sarchiz
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: upgrading
content-type: reference
discoiquuid: 5e76fe09-4d37-4c8c-8baf-97e75689bd26
feature: Upgrading
exl-id: 5798100a-e03a-43f8-9189-ae51c06e192b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 0%

---

# Bakåtkompatibilitet i AEM 6.4{#backward-compatibility-in-aem}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

>[!NOTE]
>
>En lista över innehåll- och konfigurationsändringar som inte omfattas av kompatibilitetspaketet finns på [Omstrukturering av lager i AEM 6.4](/help/sites-deploying/repository-restructuring.md).

I AEM 6.4 har alla funktioner utvecklats med bakåtkompatibilitet i åtanke.

I de flesta fall behöver inte kunder som kör AEM 6.3 ändra koden eller anpassningarna när de gör uppgraderingen. För AEM 6.1- och 6.2-kunder finns det inga ytterligare brytningsförändringar än vad man skulle få vid en uppgradering till 6.3.

Undantag där funktioner inte kan hållas bakåtkompatibla kan göras genom att man installerar ett kompatibilitetspaket för 6.3 (se hur du installerar nedan för mer information om var du ska hämta). Kompatibilitetspaketet återställer kompatibilitet för program som är kompatibla med AEM 6.3.

Med Kompatibilitetspaketet kan du köra AEM i kompatibilitetsläge och skjuta upp anpassad utveckling mot nya AEM funktioner:

>[!NOTE]
>
>Observera att kompatibilitetspaketet bara är en tillfällig lösning för att skjuta upp den utveckling som krävs för att vara AEM 6.4-kompatibel. Det rekommenderas bara som ett sista alternativ om du inte kan hantera kompatibilitetsproblem direkt efter uppgraderingen. Vi rekommenderar att du växlar till inbyggt läge och avinstallerar kompatibilitetspaketet när du har valt att fortsätta med 6.4-baserad anpassad utveckling och att du har tillgång till alla 6.4-funktioner.

![screen_shot_2018-04-05at43339pm](assets/screen_shot_2018-04-05at43339pm.png)

Kompatibilitetspaketet har två lägen: **Routning aktiverad** och **Routning inaktiverad**.

Detta gör att AEM 6.4 kan köras i tre lägen:

**Ursprungligt läge:**

Det inbyggda läget är till för kunder som vill använda alla nya funktioner i AEM 6.4 och är redo att göra en del av utvecklingen för att få anpassningarna att fungera med alla nya funktioner.

Det innebär att du kan behöva göra ändringar i programmet omedelbart efter uppgraderingen.

**Kompatibilitetsläge: Kompatibilitetspaket installerat med routning aktiverat**

Kompatibilitetsläget är avsett för kunder som har anpassat gränssnitt som inte är bakåtkompatibla. Detta gör att AEM kan köras i kompatibilitetsläge och skjuta upp den anpassade utvecklingen mot nya AEM funktioner som inte är kompatibla med en del av din anpassade kod.

**Äldre läge: Kompatibilitetspaket installerat med routning inaktiverat**

Äldre läge är för kunder som har anpassade gränssnitt som baseras på äldre eller inaktuell kod från AEM som har flyttats ut i kompatibilitetspaketet.

![image2018-2-12_23-58-37](assets/image2018-2-12_23-58-37.png)

## Konfigurera {#how-to-set-up}

Kompatibilitetspaketet AEM 6.3 kan installeras som ett paket med hjälp av pakethanteraren. Du kan ladda ned [AEM 6.3-kompatibilitetspaket från programvarudistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/compatpack/aem-compat-cq64-to-cq63) webbplats.

När Kompatibilitetspaketet har installerats kan routningen aktiveras eller inaktiveras med en växel i OSGI-konfigurationen enligt nedan:

![screen_shot_2017-11-27at122421pm](assets/screen_shot_2017-11-27at122421pm.png)

När Kompatibilitetspaketet har installerats och konfigurerats används funktionerna baserat på det kompatibilitetsläge som har valts.
