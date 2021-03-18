---
title: Utforma hjälpmedelsförberedda HTML5-formulär
seo-title: Utforma hjälpmedelsförberedda HTML5-formulär
description: HTML5-formulär använder hjälpmedelsstandarden ARIA HTML5. Dessa formulär har stöd för fliknavigering och är certifierade att vara kompatibla med vanliga skärmläsare.
seo-description: HTML5-formulär använder hjälpmedelsstandarden ARIA HTML5. Dessa formulär har stöd för fliknavigering och är certifierade att vara kompatibla med vanliga skärmläsare.
uuid: b7757079-5f06-4818-8488-11d67cbe3522
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: ccc59dd5-c0cf-415a-b71a-5bc0cf452ede
feature: Mobile Forms
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 0%

---


# Utforma hjälpmedelsförberedda HTML5-formulär {#designing-accessible-html-forms}

HTML5-formulär använder hjälpmedelsstandarden ARIA HTML5 för att generera hjälpmedelsförberedda HTML-formulär. De här formulären har stöd för tabbnavigering (utom Mozilla FireFox) och är certifierade som kompatibla med vanliga skärmläsare. Om du vill generera ett HTML5-formulär med bra hjälpmedelsfunktioner utformar du XFA-formulärmallen baserat på några [grundläggande riktlinjer för design](/help/forms/using/best-practices-for-html5-forms.md). Riktlinjerna för designen omfattar konfiguration av rätt tabbordning och tillhandahållande av innehållet i Tala text för varje formulärkontroll. AEM Forms Designer stöder inställningen av dessa formulärkontrollsattribut för att generera ett tillgängligt PDF- och HTML5-formulär.

*Obs!Fliknavigering omfattar inte skyddade fält, t.ex. beräkningsfält som visar summan av värden. För att skärmläsaren ska kunna läsa värdet för ett skyddat fält placerar du ett tomt skrivskyddat fält ovanpå eller bredvid det skyddade fältet. Tilldela det skyddade fältets värde till det nya skrivskyddade fältet. Skärmläsaren eller fliknavigeringen kan välja det här skrivskyddade fältet och tala ut det som värdet för det skyddade fältet.*

AEM Forms Designer innehåller ett antal alternativ för att tala text som kan skickas till skärmläsare. För varje objekt i ett formulär kan användaren ange en av flera inställningar för skärmläsartexten:

* Anpassad uppläsningstext, som kan ställas in med paletten Tillgänglighet. Författare kan kommentera namnen på knappar och fält samt deras syfte.
* Verktygstips som du kan ange på paletten Tillgänglighet.
* Bildtexter för fält i formuläret.
* Namn på objekt, enligt alternativen Namn på fliken Bindning.

![hjälpmedel](assets/accessibility.png)

Om det finns flera alternativ som funktionsbeskrivning, Reader-text och bildtext på en formulärkontroll använder Reader på skärmen endast en av dessa egenskaper. Standardordningen är Reader, funktionsbeskrivning, bildtext och namn för anpassad skärm. Du kan åsidosätta standardordningen med alternativet Skärmprioritet **Reader** på paletten Tillgänglighet.
