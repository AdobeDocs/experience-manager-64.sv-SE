---
title: Skärmläsare för HTML5-formulär
seo-title: Screen readers for HTML5 forms
description: Visar de skärmläsare som stöds i HTML5-formulär.
seo-description: Lists the screen readers supported with HTML5 forms.
uuid: 035354e2-957f-4eb6-bc16-4ca96ec7ac74
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 53c57180-7004-4534-9146-603f7770a6fe
feature: Mobile Forms
exl-id: c27eb771-d390-4534-8e67-f1277550e760
source-git-commit: e608249c3f95f44fdc14b100910fa11ffff5ee32
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 0%

---

# Skärmläsare för HTML5-formulär {#screen-readers-for-html-forms}

HTML5-formulärkomponenter återger XFA-formulärmallen till ett HTML5-format. Alla standardwebbläsare som stöder HTML5 kan återge dessa formulär. För att ge stöd för liknande datainhämtning i olika PDF- och HTML5-formulär behålls layouten för PDF forms i HTML5-formulär.

HTML5-formulär använder HTML-standardkonstruktioner som tillåter vanliga hjälpmedelsverktyg för HTML att användas med dessa formulär. Om ett formulär är utformat enligt bästa praxis för hjälpmedelsförberedda formulär fungerar det med alla skärmläsare som stöds. Dessutom är sådana formulär aktiverade för tangentbordsnavigering.

## Tillgänglighetsstandarder {#accessibility-standards}

HTML5-formulär uppfyller kraven i avsnitt 508 för tillgänglighet med kända undantag. Mer information finns i [VPAT för HTML5-formulär](http://wwwimages.adobe.com/content/dam/acom/en/accessibility/compliance/pdfs/livecycle-mobile-forms-es4-section-508-vpat.pdf).

## Certifierade skärmläsare för HTML5-formulär {#certified-screen-readers-for-html-forms}

* JAWS 14.0 i Microsoft Windows
* VoiceOver på Mac OS X och iPad

### JAWS {#jaws}

Alla standardtangenttryckningar och kortkommandon fungerar för HTML5-formulär. Mer information om JAWS finns på [https://www.freedomscientific.com/jaws-hq.asp](https://www.freedomscientific.com/jaws-hq.asp).

### VoiceOver {#voiceover}

HTML5-formulär har stöd för alla standardtangenttryckningar och -gester för Voice over. Mer information om hur du konfigurerar och använder VoiceOver finns i [https://www.apple.com/accessibility/voiceover/](https://www.apple.com/accessibility/voiceover/).

## Kända fel {#known-issues}

* **(Endast i Utforskaren 9)** I HTML5-formulär läses sidorna in vid behov (dynamiskt). Sidinläsning on demand orsakar problem med skärmläsarnas funktion. När skärmläsarens fokus är på det sista fältet på sidan och användaren trycker på fliken, återgår skärmläsaren fokus till det första fältet på formulärets första sida i stället för att fokusera på det första fältet på nästa sida.
* **(Endast internt Explorer 9)** Datumväljarkontrollen i HTML5-formulär är inte helt tillgänglig med tangentbordet. Om du trycker på upp-/nedtangenterna flera gånger i datumväljaren stängs datumväljaren och fokus flyttas till nästa/sista fält.

* VoiceOver kan inte identifiera piltangenter på datumwidgeten på iPad safari.
