---
title: Skapa en SCF-sandlåda
seo-title: Create An SCF Sandbox
description: Den här självstudiekursen är främst avsedd för utvecklare som inte är AEM och som är intresserade av att använda SCF-komponenter.  Här går vi igenom hur man skapar en SCF-sandlådeplats
seo-description: This tutorial is primarily for developers, new to AEM, who are interested in using SCF components.  It walks through the creation of An SCF Sandbox site
uuid: ee52e670-e1e6-4bcd-9548-c963142e6704
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: e1b5c25d-cbdd-421c-b81a-feb6039610a3
exl-id: f8cd2866-6e4d-47e6-b9aa-c2190b0b1b7b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '529'
ht-degree: 0%

---

# Skapa en SCF-sandlåda {#create-an-scf-sandbox}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).


Från och med AEM 6.1 Communities är det enklaste sättet att snabbt skapa en sandlåda att skapa en community-webbplats. Se [Komma igång med AEM Communities](getting-started.md).

Ett annat användbart verktyg för utvecklare är [Community Components Guide](components-guide.md), som gör det möjligt att utforska och snabbt skapa prototyper för communitykomponenter och -funktioner.

Att skapa en webbplats kan vara användbart för att förstå strukturen hos en AEM webbplats som kan innehålla funktioner för användargrupper, samtidigt som det kan finnas enkla sidor där du kan utforska arbetet med [ramverk för sociala komponenter (SCF)](scf.md).

Den här självstudiekursen är främst avsedd för utvecklare som inte är AEM och som är intresserade av att använda SCF-komponenter. Här går vi igenom hur du skapar en SCF-sandlådeplats, ungefär som självstudiekursen för [Skapa en komplett webbplats](../../help/sites-developing/website.md) som fokuserar på webbplatsstrukturer som navigering, logotyp, sökning, verktygsfält och lista underordnade sidor.

Utvecklingen sker i en författarinstans, medan det är bäst att experimentera med webbplatsen i en publiceringsinstans.

Stegen i den här självstudiekursen är:

* [Konfigurera webbplatsstruktur](setup-website.md)
* [Ursprungligt sandlådeprogram](initial-app.md)
* [Ursprungligt sandlådeinnehåll](initial-content.md)
* [Utveckla sandlådeprogram](develop-app.md)
* [Lägg till klienter](add-clientlibs.md)
* [Utveckla innehåll i sandlådan](develop-content.md)

>[!CAUTION]
>
>I den här självstudiekursen skapas ingen community-webbplats med de funktioner som skapas med [Konsolen Webbplatser i Communities](sites-console.md). I den här självstudiekursen beskrivs till exempel inte hur du konfigurerar inloggning, självregistrering, [social inloggning](social-login.md), meddelanden, profiler och så vidare.
>
>Om du föredrar en enkel community-webbplats följer du [Skapa en exempelsida](create-sample-page.md) självstudiekurs.

## Förutsättningar {#prerequisites}

I den här självstudiekursen förutsätts att du har en AEM författare och en AEM publiceringsinstans installerad som har [senaste versionen](deploy-communities.md#latest-releases) av Communities.

Nedan följer några praktiska länkar för utvecklare som är nya för den AEM plattformen:

* [Komma igång](../../help/sites-deploying/deploy.md#getting-started) - För distribution AEM instanser

   * [Grunderna](../../help/sites-developing/the-basics.md) - För utvecklare av webbplatser och funktioner
   * [Steg 1 för författare](../../help/sites-authoring/first-steps.md) - För redigering av sidinnehåll

## Använda CRXDE Lite Development Environment {#using-crxde-lite-development-environment}

AEM utvecklare tillbringar mycket tid i [CRXDE Lite](../../help/sites-developing/developing-with-crxde-lite.md) utvecklingsmiljö på en författarinstans. CRXDE Lite ger mindre begränsad åtkomst till CRX-databasen. Klassiska användargränssnittsverktyg och pekaktiverade användargränssnittskonsoler ger mer strukturerad åtkomst till specifika delar av CRX-databasen.

När du har loggat in med administratörsbehörighet finns det olika sätt att få åtkomst till CRXDE Lite:

1. Välj navigering från global navigering **[!UICONTROL Tools > CRXDE Lite]**.

   ![chlimage_1-350](assets/chlimage_1-350.png)

2. Från [välkomstsida för klassiskt användargränssnitt](http://localhost:4502/welcome.html), rulla nedåt och klicka **[!UICONTROL CRXDE Lite]** i den högra panelen.

   ![chlimage_1-351](assets/chlimage_1-351.png)

3. Bläddra direkt till `CRXDE Lite`: `<server>:<port>/crx/de`

   På en lokal författarinstans: ` [http://localhost:4502/crx/de](http://localhost:4502/crx/de)`

Om du vill arbeta med CRXDE Lite måste du logga in med utvecklar- eller administratörsbehörighet. För standardinstansen av localhost kan du logga in med

* `username: admin`
* `password: admin`


**Var medveten** att inloggningen kommer att timeout och du måste logga in igen med jämna mellanrum med listrutan till höger i verktygsfältet CRXDe Lite.

Om du inte är inloggad kan du inte navigera i JCR-databasen eller utföra några redigerings-/sparåtgärder.

***När du är osäker, logga in igen!***

![chlimage_1-352](assets/chlimage_1-352.png)
