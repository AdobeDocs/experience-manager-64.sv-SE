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
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f

---


# Utforma hjälpmedelsförberedda HTML5-formulär {#designing-accessible-html-forms}

HTML5-formulär använder hjälpmedelsstandarden ARIA HTML5 för att generera hjälpmedelsförberedda HTML-formulär. De här formulären har stöd för tabbnavigering (utom Mozilla FireFox) och är certifierade som kompatibla med vanliga skärmläsare. Om du vill generera ett HTML5-formulär med bra hjälpmedelsfunktioner utformar du XFA-formulärmallen baserat på några [grundläggande riktlinjer](/help/forms/using/best-practices-for-html5-forms.md)för design. Riktlinjerna för designen omfattar konfiguration av rätt tabbordning och tillhandahållande av innehållet i Tala text för varje formulärkontroll. AEM Forms Designer stöder inställningen av dessa formulärkontrollsattribut för att generera ett tillgängligt PDF- och HTML5-formulär.

*Obs!Fliknavigering omfattar inte skyddade fält, t.ex. beräkningsfält som visar summan av värden. För att skärmläsaren ska kunna läsa värdet för ett skyddat fält placerar du ett tomt skrivskyddat fält ovanpå eller bredvid det skyddade fältet. Tilldela det skyddade fältets värde till det nya skrivskyddade fältet. Skärmläsaren eller fliknavigeringen kan välja det här skrivskyddade fältet och tala ut det som värdet för det skyddade fältet.*

AEM Forms Designer innehåller ett antal alternativ för att tala text som kan skickas till skärmläsare. För varje objekt i ett formulär kan användaren ange en av flera inställningar för skärmläsartexten:

* Anpassad uppläsningstext, som kan ställas in med paletten Tillgänglighet. Författare kan kommentera namnen på knappar och fält samt deras syfte.
* Verktygstips som du kan ange på paletten Tillgänglighet.
* Bildtexter för fält i formuläret.
* Namn på objekt, enligt alternativen Namn på fliken Bindning.

![hjälpmedel](assets/accessibility.png)

När det finns flera alternativ som verktygstips, Skärmläsartext och Bildtext på en formulärkontroll använder skärmläsaren bara en av dessa egenskaper. Standardordningen är Anpassad uppläsningstext, funktionsbeskrivning, bildtext och namn. You can override the default order using the Screen Reader **Precedence** option in the Accessibility palette.
