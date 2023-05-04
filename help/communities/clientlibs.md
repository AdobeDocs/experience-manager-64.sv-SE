---
title: Clientlibs for Communities Components
seo-title: Clientlibs for Communities Components
description: Klientbibliotek för Communities
seo-description: Client-side libraries for Communities
uuid: 0a62f629-e6af-4269-862e-0595824c329f
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 7d423dff-8710-4f43-ad55-8863169946e2
exl-id: 9b4ed16f-3c7c-478a-a897-9b4be086988b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '415'
ht-degree: 1%

---

# Clientlibs for Communities Components {#clientlibs-for-communities-components}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

I det här avsnittet av dokumentationen beskrivs hur du lägger till klientbibliotek (klientbibliotek) på en sida för webbgruppskomponenter.

Grundläggande information finns på

* [Använda bibliotek på klientsidan](../../help/sites-developing/clientlibs.md) som innehåller användningsinformation och felsökningsverktyg
* [Clientlibs for SCF](client-customize.md#clientlibs) som ger användbar information när du anpassar SCF-komponenter

## Varför Clientlibs krävs {#why-clientlibs-are-required}

Clientlibs krävs för att en komponent ska fungera korrekt (JavaScript) och formatera (CSS).

När det finns en [communityfunktion](functions.md) för en funktion kommer alla nödvändiga komponenter och konfigurationer, inklusive nödvändiga klienter, att finnas på communitywebbplatsen. Det är bara om ytterligare komponenter ska vara tillgängliga för författare som måste läggas till ytterligare klientlib.

När de nödvändiga klientlibs saknas, [lägga till en webbgruppskomponent på en sida](author-communities.md) kan resultera i javascript-fel och ett oväntat utseende.

### Exempel: Monterade granskningar utan Clientlibs {#example-placed-reviews-without-clientlibs}

![chlimage_1-244](assets/chlimage_1-244.png)

### Exempel: Monterade granskningar med Clientlibs {#example-placed-reviews-with-clientlibs}

![chlimage_1-245](assets/chlimage_1-245.png)

## Identifiera nödvändiga klienter {#identifying-required-clientlibs}

Den viktigaste funktionsinformationen för utvecklare identifierar de nödvändiga klientlibs.

Från en AEM förekomst bläddrar du dessutom till [Community Components Guide](components-guide.md) ger åtkomst till en lista över de klientlibkategorier som krävs för en komponent.

Till exempel längst upp på [Granskningssida](http://localhost:4502/content/community-components/en/reviews.html) de nödvändiga listorna är

* cq.ckeditor
* cq.social.hbs.reviews

![chlimage_1-246](assets/chlimage_1-246.png)

## Lägga till nödvändiga klienter {#adding-required-clientlibs}

När du vill lägga till en webbgruppskomponent på en sida måste du lägga till de nödvändiga klientlibs för komponenten om det inte redan finns.

Använd [CRXDE|Lite](#using-crxde-lite) om du vill ändra en befintlig klientlistorlista för en communitywebbplats.

Så här lägger du till en klientlib för en community-webbplats med [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Bläddra till [https://&lt;server>:&lt;port>/crx/de](http://localhost:4502/crx/de)
* Leta reda på `clientlibslist` nod för den sida där du vill lägga till komponenten

   * `/content/sites/sample/en/page/jcr:content/clientlibslist`

* Med `clientlibslist` markerad nod

   * Leta reda på strängen[] property `scg:requiredClientLibs`
   * Välj `Value` för att komma åt dialogrutan String-array

      * Bläddra nedåt om det behövs
      * Välj `+` för att ange ett nytt klientbibliotek

         * Upprepa för att lägga till fler klientbibliotek
      * Välj **[!UICONTROL OK]**
   * Välj **[!UICONTROL Save All]**



>[!NOTE]
>
>Om webbplatsen inte är en communitywebbplats måste förekomsten eller platsen för klientbiblioteken som används för webbplatsen identifieras.

Använda [Komma igång med AEM Communities](getting-started.md) exempel, där `site-name` är *engagera*, är det så här klienten visas om du lägger till granskningskomponenten:

![chlimage_1-247](assets/chlimage_1-247.png)
