---
title: Utforma formulärmallar för HTML5-formulär
seo-title: Utforma formulärmallar för HTML5-formulär
description: 'AEM Forms erbjuder återgivning av XFA-formulärmallar till HTML5-format. Formulärdesigners kan utforma formulärmallar med Designer och använda HTML5-återgivningsfunktionen. '
seo-description: 'AEM Forms erbjuder återgivning av XFA-formulärmallar till HTML5-format. Formulärdesigners kan utforma formulärmallar med Designer och använda HTML5-återgivningsfunktionen. '
uuid: 41a00ec5-d7f9-4717-a961-00d20d8e7b2a
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: e135fa01-fede-4285-b4dd-2d23acbb4d26
translation-type: tm+mt
source-git-commit: f13d358a6508da5813186ed61f959f7a84e6c19f

---


# Utforma formulärmallar för HTML5-formulär {#designing-form-templates-for-html-forms}

HTML5-formulärkomponenten i AEM erbjuder återgivning av XFA-formulärmallar till HTML5-format. Formulärdesigners kan utforma formulärmallar med [Forms Designer](https://www.adobe.com/go/learn_aemforms_designer_63) och använda HTML5-återgivningsfunktionen. Dessa formulärmallar, tillsammans med deras resurser, kan finnas i AEM-databasen, filsystemet eller visas via http. Men om du tänker hantera dina formulär med Forms Manager bör mallarna och resurserna finnas i AEM-databasen.

Även om HTML5-formulär i stor utsträckning matchar beteendet i PDF-formulären finns det vissa funktioner i båda formaten som inte kan användas i det andra formatet. Hur streckkoder tillämpas på ett PDF-formulär i Adobe Reader varierar till exempel från ett mobilformulär eller hur ett formulär signeras digitalt varierar också mellan formaten. Mer information om sådana variationer finns i [Funktionsdifferentiering mellan HTML5-formulär och PDF-formulär](/help/forms/using/feature-differentiation-html5-forms-pdf-forms.md).

Vanliga XFA-funktioner finns i följande metodtips och riktlinjer för att utforma ett formulär som fungerar i båda formaten.

## Funktioner i AEM Forms Designer för HTML5-formulär {#capabilities-in-aem-forms-designer-for-html-forms}

### Förhandsgranska HTML {#preview-html}

Fliken Förhandsgranska HTML läggs till i designläget för formulärdesigners för att förhandsgranska formulär i HTML5-format under designprocessen. Mer information om hur du aktiverar och konfigurerar den här funktionen i AEM Forms Designer finns i [Förhandsgranska HTML](/help/forms/using/preview-xdp-forms-html.md).

### Klottra signaturer {#scribble-signature}

Huvudmålet för HTML5-formulär är pekenheter. Därför har en ny kontroll för signering i klotter lagts till i AEM Forms Designer. Du kan klicka på eller dra och släppa kontrollen för signering av skript på formulärmallen och konfigurera den. Det återges som ett klottrigt fält i HTML5-rendering och kan användas för att klottra signaturer på enheter med pekskärm. På stationära datorer kan den användas som ett klotterfält med hjälp av muskontroll. Mer information om hur du använder den här funktionen finns i [XFA-skriptfält](/help/forms/using/scribble-signature.md).

![4](assets/4.png)
