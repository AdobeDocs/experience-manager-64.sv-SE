---
title: Genomgång av referenswebbplatsen för förnyelse av autoförsäkring
seo-title: Genomgång av referenswebbplatsen för förnyelse av autoförsäkring
description: 'null'
seo-description: 'null'
uuid: 18676ab4-9f8d-4014-b751-2a722fd152da
contentOwner: dekalra
topic-tags: introduction
discoiquuid: a960d489-f5a3-436a-b028-54292648c7be
translation-type: tm+mt
source-git-commit: 4466161992d877b17d43fe73e3298dd6252733c0
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---


# Genomgång av referenswebbplatsen för förnyelse av autoförsäkring {#we-finance-auto-insurance-renewal-reference-site-walkthrough}

## Krav {#pre-requisites}

Konfigurera referensplatsen enligt beskrivningen i [Konfigurera och konfigurera AEM 6.4 Forms Reference Site](/help/forms/using/setup-reference-sites.md).

## Scenario för referenswebbplats för ekonomi  {#we-finance-reference-site-scenario}

Webbplatsen We.Finance är en sajt för finansiella tjänster som är utformad för att hjälpa dig att lära dig interaktiva kommunikationsfunktioner i AEM Forms.

Läs mer om genomgången av Web.Finance Auto Insurance-exempel som visar hur AEM formulär och dess integrering med Microsoft Dynamics hjälper till att personalisera kundupplevelsen i ett finansföretag. Den interaktiva genomgången är utformad för att underlätta implementering av komplexa digitala transaktioner och kundkommunikation i ett finansföretag.

**Resan börjar med följande exempel:**

Sarah Rose är en befintlig We.Finance-kund och har köpt en bilförsäkring. Nu är det dags att förnya sin försäkring. Gloria Rios, försäkringsagent, We.Finance skickar en påminnelse till Sarah om förnyelsen av sin policy. Sarah följer instruktionerna i e-postmeddelandet och slutför processen.

## Genomgång av självförsäkringsprogram {#auto-insurance-application-walkthrough}

Scenariot för automatisk försäkring för Web.Finance är en visuell berättarröst för användaren och baseras på två personligheter:

* Sarah Rose, en We.Finance-kund
* Gloria Rios, försäkringsagent, We.Finance

### Gloria skickar ett meddelande om förnyelse av försäkringsavtal från We.Finance {#gloria-sends-an-insurance-policy-renewal-communication-from-we-finance}

Gloria loggar in AEM instansen, klickar på **Förnyelse av försäkring** och klickar sedan på **Open Agent-gränssnittet.** Klicket fyller i försäkringsdokumentet med information om Sarah Rose. Gloria klickar på&#x200B;**Skicka** och ett meddelande visas på skärmen&quot;Inskickning initierad&quot; och sedan på några sekunder&quot;Inskickad klar&quot;.

Sarah får ett mejl med rubriken&quot;Din förnyelse av autoförsäkring&quot;.

![agent_ui_email](assets/agent_ui_email.png)

#### Se det själv {#see-it-yourself}

Gå till **Adobe Experience Manager** > **Forms** > **Forms &amp; Documents** > **We.Finance** > **Auto Insurance**. Välj **den interaktiva kommunikationen Förnyelse** av automatisk försäkring och klicka på **Öppna agentgränssnitt**. Den interaktiva kommunikationen öppnas i agentgränssnittet. Ange en giltig e-postadress för att ta emot e-postmeddelandet med det bifogade principdokumentet och klicka på Skicka.

Du kan öppna och granska den interaktiva kommunikationen om förnyelse av autoförsäkring direkt från `https://[authorHost]: authorPort]/aem/formdetails.html/content/dam/formsanddocuments/we-finance/autoinsurance/auto-insurance-renewal.`

### Sarah får ett meddelande om förnyelse av försäkringsavtal från We.Finance och bestämmer sig för att förnya {#sarah-receives-an-insurance-policy-renewal-communication-from-we-finance-and-decides-to-renew}

Sarah får ett mejl med en bilaga från We.Finance som påminner henne om att hennes policy för autoförsäkring håller på att löpa ut. Den bifogade filen är den utskrivna versionen av det automatiska försäkringsbrevet.

Sarah klickar på **Förnya nu** och dirigeras till webbversionen av sitt autofyrbrev. Utöver det här brevet hittar Sarah antalet dagar kvar innan hennes policy upphör att gälla. Sidan ger Sarah en grundläggande översikt över sin försäkringsinformation, t.ex. försäkringsnummer, förfallobelopp och annan information som rabatterbjudanden och förmånsersättningar. Sarah klickar igen på **Förnya nu** längst ned i policyn.

![ref1](assets/ref1.png)

#### Så här fungerar det {#how-it-works}

Utdata för webb och utskrift av autofyrningsbrevet skapas med hjälp av flerkanalsfunktionerna i Interactive Communications.

Knappen Förnya nu i e-postmeddelandet är länkad till programmet Förnya automatiskt, som är en interaktiv kommunikation i en publiceringsinstans.

#### Se det själv {#see-it-yourself-1}

Du måste ha fått ett e-postmeddelande med en bifogad PDF. PDF-filen är en utskriftsversion av ditt autofonkbrev. Klicka på **Förnya nu** för att gå till webbversionen av profilen. Kontrollera din personliga information och policyinformation och klicka på **Förnya nu** , som tar dig till en annan interaktiv kommunikation.

Knappen **Förnya nu** i e-postmeddelandet dirigerar Sarah till webbversionen av policyn. Du kan gå till följande URL:

`https://[authorServer]:[authorPort]/content/document.html?schema=fdm&documentId=/content/forms/af/we-finance/autoinsurance/auto-insurance-renewal/channels/web.html&customerId=1`

Du kan kontrollera den detaljerade sammanfattningen av din automatiska försäkringsförnyelse och klicka på **Förnya nu** längst ned på sidan.

### Sarah kommer till betalningssidan {#sarah-reaches-the-payment-page}

Vi.Finance tar Sarah till betalningssidan. Sarah omkontrollerar sitt principnummer och utgångsdatum med sina register. Till höger på sidan kontrollerar hon betalningsöversikten för förnyelsen med 10 % premiumrabatt på det totala beloppet.

#### Så här fungerar det {#how-it-works-1}

Knappen Förnya nu dirigerar Sarah till betalningssidan. Betalningssidan är ett anpassningsbart formulär.

#### Se det själv {#see-it-yourself-2}

Klicka på **Förnya nu** för att nå betalningssidan. Fyll i kreditkortsinformationen och klicka på **Gör betalning.**

Du kan nå betalningssidan i utvecklingsinstansen på

`https://[authorServer]:[authorPort]/content/document.html?documentId=/content/forms/af/we-finance/credit-card/ccbillpayment.html&schema=fdm&customerId=1`

### Sarah gör betalningen och slutför processen {#sarah-makes-the-payment-and-completes-the-process}

Sarah fyller i sin kreditkortsinformation och klickar på **Gör betalning**.

#### Så här fungerar det {#how-it-works-2}

När Sarah fyller i kreditkortsinformationen och klickar på Submit (Skicka) bearbetas hennes kreditkortsbetalning och ett tackmeddelande som konfigurerats i det adaptiva formuläret visas på skärmen.

#### Se det själv {#see-it-yourself-3}

Du kan visa bekräftelsemeddelandet efter att du klickat på Gör betalning vid

`https://[authorServer]:[authorPort]/content/forms/af/we-finance/credit-card/ccbillpayment/jcr:content/guideContainer.guideThankYouPage.html?owner=admin&status=Submitted`
