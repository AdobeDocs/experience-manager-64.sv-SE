---
title: Skapa en exempelsida
seo-title: Create a Sample Page
description: Skapa en exempelwebbplats
seo-description: Create a Sample community site
uuid: 04a8f027-b7d8-493a-a9bd-5c4a6715d754
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
content-type: reference
topic-tags: developing
discoiquuid: a03145f7-6697-4797-b73e-6f8d241ce469
exl-id: 00ac29fb-cc8f-4dd9-a261-839a4bf664c2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 3%

---

# Skapa en exempelsida {#create-a-sample-page}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Från och med AEM 6.1 Communities är det enklaste sättet att skapa en exempelsida att skapa en enkel communitywebbplats som består av en sidfunktion.

Detta inkluderar en parsykomponent så att du kan [aktivera komponenter för utveckling](basics.md#accessing-communities-components).

Ett annat alternativ för att utforska exempelkomponenter är att använda funktionerna i [Community Components Guide](components-guide.md).

## Skapa en communitywebbplats {#create-a-community-site}

Det här liknar mycket att skapa en ny webbplats som beskrivs i [Komma igång med AEM Communities](getting-started.md).

Den största skillnaden är att den här självstudiekursen kommer att skapa en ny mall för en community-webbplats som bara innehåller [Sidfunktion](functions.md#page-function) för att skapa en enkel communitysajt som är fri från andra funktioner (andra än förkabelfunktioner som är grundläggande för alla communitysajter).

### Skapa ny platsmall {#create-new-site-template}

Skapa en enkel [mall för communitywebbplats](sites.md).

Från global navigering i en författarinstans väljer du **[!UICONTROL Tools > Communities > Site Templates]**.

![chlimage_1-82](assets/chlimage_1-82.png)

* Välj `Create button`
* GRUNDLÄGGANDE INFORMATION

   * `Name`: Enkelsidig mall
   * `Description`: En mall som består av en enda sidfunktion.
   * välj `Enabled`

![chlimage_1-83](assets/chlimage_1-83.png)

* STRUKTUR

   * Dra en `Page` funktionen till Template Builder
   * Ange information om konfigurationsfunktionen

      * `Title`: En sida
      * `URL`: page

![chlimage_1-84](assets/chlimage_1-84.png)

* Välj **`Save`** för konfigurationen
* Välj **`Save`** för webbplatsmallen

### Skapa ny community-webbplats {#create-new-community-site}

Skapa nu en ny communitywebbplats som bygger på den enkla webbplatsmallen.

När du har skapat webbplatsmallen väljer du från global navigering **[!UICONTROL Communities > Sites]**.

![chlimage_1-85](assets/chlimage_1-85.png)

* Välj **`Create`** icon

* Steg `1 - Site Template`

   * `Title`: Enkel communitywebbplats
   * `Description`: En communitywebbplats som består av en enda sida för experiment.
   * `Community Site Root: (leave blank)`
   * `Community Site Base Language: English`
   * `Name`: exempel

      * url = http://localhost:4502/content/sites/sample
   * `Template`: välj `Single Page Template`


![chlimage_1-86](assets/chlimage_1-86.png)

* Välj `Next`
* Steg `2 - Design`

   * Välj en design

* Välj `Next`
* Välj `Next`

   (Acceptera alla standardinställningar)

* Välj `Create`

![chlimage_1-87](assets/chlimage_1-87.png)

## Publicera webbplatsen {#publish-the-site}

![chlimage_1-88](assets/chlimage_1-88.png)

Från [community sites console](sites-console.md), väljer du publiceringsikonen för att publicera webbplatsen, som standard http://localhost:4503.

## Öppna webbplatsen på författaren i redigeringsläge {#open-the-site-on-author-in-edit-mode}

![chlimage_1-89](assets/chlimage_1-89.png)

Välj ikonen Öppna plats om du vill visa webbplatsen i redigeringsläge.

URL:en blir [http://localhost:4502/editor.html/content/sites/sample/en.html](http://localhost:4502/editor.html/content/sites/sample/en.html)

![chlimage_1-90](assets/chlimage_1-90.png)

På den enkla startsidan är det möjligt att se vad som är förkopplat via communityfunktionerna och -mallarna, och att leka med att lägga till och konfigurera communitykomponenter.

## Visa webbplats vid publicering {#view-site-on-publish}

Öppna sidan på sidan när du har publicerat sidan [publiceringsinstans](http://localhost:4503/content/sites/sample/en.html) för att experimentera med funktionerna som anonym besökare, inloggad medlem eller administratör. Administrationslänken som visas i författarmiljön visas inte i publiceringsmiljön om inte en administratör loggar in.
