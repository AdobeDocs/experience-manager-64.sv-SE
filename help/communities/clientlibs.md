---
title: Clientlibs for Communities Components
seo-title: Clientlibs for Communities Components
description: Klientbibliotek för Communities
seo-description: Klientbibliotek för Communities
uuid: 0a62f629-e6af-4269-862e-0595824c329f
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 7d423dff-8710-4f43-ad55-8863169946e2
translation-type: tm+mt
source-git-commit: 59d40b5bddc42a4ac057ef600243f396aefc926b

---


# Clientlibs for Communities Components {#clientlibs-for-communities-components}

## Introduktion {#introduction}

I det här avsnittet av dokumentationen beskrivs hur du lägger till klientbibliotek (klientbibliotek) på en sida för webbgruppskomponenter.

Grundläggande information finns på

* [Använda bibliotek](../../help/sites-developing/clientlibs.md) på klientsidan som innehåller användarinformation och felsökningsverktyg
* [Clientlibs for SCF](client-customize.md#clientlibs) som ger användbar information när du anpassar SCF-komponenter
* [Blogg: AEM Client Libraries förklaras av exempel](https://blogs.adobe.com/experiencedelivers/experience-management/clientlibs-explained-example/)

## Varför Clientlibs krävs {#why-clientlibs-are-required}

Clientlibs krävs för att en komponent ska fungera korrekt (JavaScript) och formatera (CSS).

När det finns en [communityfunktion](functions.md) för en funktion kommer alla nödvändiga komponenter och konfigurationer, inklusive de nödvändiga klientlibs, att finnas på communitywebbplatsen. Det är bara om ytterligare komponenter ska vara tillgängliga för författare som måste läggas till ytterligare klientlib.

När de nödvändiga klientlibs saknas kan det leda till javascript-fel och ett oväntat utseende om du [lägger till en webbgruppskomponent på en sida](author-communities.md) .

### Exempel: Monterade granskningar utan Clientlibs {#example-placed-reviews-without-clientlibs}

![chlimage_1-244](assets/chlimage_1-244.png)

### Exempel: Monterade granskningar med Clientlibs {#example-placed-reviews-with-clientlibs}

![chlimage_1-245](assets/chlimage_1-245.png)

## Identifiera nödvändiga klienter {#identifying-required-clientlibs}

Den viktigaste funktionsinformationen för utvecklare identifierar de nödvändiga klientlibs.

Om du bläddrar till [Community Components Guide](components-guide.md) från en AEM-instans får du dessutom tillgång till en lista med de clientlib-kategorier som krävs för en komponent.

Till exempel, högst upp på sidan [](http://localhost:4502/content/community-components/en/reviews.html) Recensioner, visas de klickbara listerna

* cq.ckeditor
* cq.social.hbs.reviews

![chlimage_1-246](assets/chlimage_1-246.png)

## Lägga till nödvändiga klienter {#adding-required-clientlibs}

När du vill lägga till en webbgruppskomponent på en sida måste du lägga till de nödvändiga klientlibs för komponenten om det inte redan finns.

Använd [CRXDE|Lite](#using-crxde-lite) för att ändra en befintlig klientlibslista för en communitywebbplatssida.

Så här lägger du till en klientlib för en community-webbplats med [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md):

* Gå till [https://&lt;server>:&lt;port>/crx/de](http://localhost:4502/crx/de)
* Leta reda på `clientlibslist` noden för sidan där du vill lägga till komponenten

   * `/content/sites/sample/en/page/jcr:content/clientlibslist`

* Med `clientlibslist` nod markerad

   * Leta reda på[] egenskapen String `scg:requiredClientLibs`
   * Markera dess innehåll `Value` för att komma åt dialogrutan String-array

      * Bläddra nedåt om det behövs
      * Välj `+` att ange ett nytt klientbibliotek

         * Upprepa för att lägga till fler klientbibliotek
      * Välj **[!UICONTROL OK]**
   * Välj **[!UICONTROL Spara alla]**



>[!NOTE]
>
>Om webbplatsen inte är en communitywebbplats måste förekomsten eller platsen för klientbiblioteken som används för webbplatsen identifieras.

I exemplet [Komma igång med AEM Communities](getting-started.md) , där `site-name` är *engagerande*, visas klienten så här om du lägger till granskningskomponenten:

![chlimage_1-247](assets/chlimage_1-247.png)

