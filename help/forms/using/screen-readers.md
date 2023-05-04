---
title: Skärmläsare för HTML5-formulär
seo-title: Screen readers for HTML5 forms
description: Visar en lista över skärmläsare som kan användas med HTML5-formulär.
seo-description: Lists the screen readers supported with HTML5 forms.
uuid: 035354e2-957f-4eb6-bc16-4ca96ec7ac74
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: 53c57180-7004-4534-9146-603f7770a6fe
feature: Mobile Forms
exl-id: c27eb771-d390-4534-8e67-f1277550e760
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '373'
ht-degree: 0%

---

# Skärmläsare för HTML5-formulär {#screen-readers-for-html-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Formulärkomponenter i HTML5 återger XFA-formulärmallen till HTML5-format. Alla standardwebbläsare som stöder HTML5 kan återge dessa formulär. För att ge stöd för liknande datainhämtning i PDF och HTML 5 behålls layouten för PDF forms i HTML5-formulär.

HTML5-formulär använder HTML som standard och gör det möjligt att använda vanliga hjälpmedelsverktyg för HTML för dessa formulär. Om ett formulär är utformat enligt bästa praxis för hjälpmedelsförberedda formulär fungerar det med alla skärmläsare som stöds. Dessutom är sådana formulär aktiverade för tangentbordsnavigering.

## Tillgänglighetsstandarder {#accessibility-standards}

HTML5-formulär uppfyller kraven i avsnitt 508 för tillgänglighet med kända undantag. Se [VPAT för HTML5-formulär](https://www.adobe.com/content/dam/cc1/en/accessibility/compliance/pdfs/adobe-livecycle-es4-section-508-vpat-portfolio.pdf) för mer information.

## Certifierade skärmläsare för HTML5-formulär {#certified-screen-readers-for-html-forms}

* JAWS 14.0 i Microsoft Windows
* VoiceOver på Mac OS X och iPad

### JAWS {#jaws}

Alla standardtangenttryckningar och kortkommandon fungerar för HTML5-formulär. Mer information om JAWS finns på [https://www.freedomscientific.com/jaws-hq.asp](https://www.freedomscientific.com/products/software/jaws/).

### VoiceOver {#voiceover}

HTML5-formulär har stöd för alla standardtangenttryckningar och -gester i Voice over. Mer information om hur du konfigurerar och använder VoiceOver finns i [https://www.apple.com/accessibility/voiceover/](https://www.apple.com/accessibility/voiceover/).

## Kända fel {#known-issues}

* **(Endast Internet Explorer 9)** I HTML5-formulär läses sidorna in vid behov (dynamiskt). Sidinläsning on demand orsakar problem med skärmläsarnas funktion. När skärmläsarens fokus är på det sista fältet på sidan och användaren trycker på fliken, återgår skärmläsaren fokus till det första fältet på formulärets första sida i stället för att fokusera på det första fältet på nästa sida.
* **(Endast Internet Explorer 9)** Datumväljarkontrollen i HTML5-formulär är inte helt tillgänglig med tangentbordet. Om du trycker på upp-/nedtangenterna flera gånger i datumväljaren stängs datumväljaren och fokus flyttas till nästa/sista fält.

* VoiceOver kan inte identifiera piltangenter på datumwidgeten i iPad Safari.
