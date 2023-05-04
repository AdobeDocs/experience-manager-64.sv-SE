---
title: Utforma formulärmallar för HTML5-formulär
seo-title: Designing form templates for HTML5 forms
description: AEM Forms erbjuder återgivning av XFA-formulärmall till HTML5-format. Formulärdesigners kan utforma formulärmallar med Designer och använda HTML5-renderingsfunktionen.
seo-description: AEM Forms offers rendering XFA form template to HTML5 format. Form designers can design form templates using Designer and use the HTML5 rendition capability.
uuid: 41a00ec5-d7f9-4717-a961-00d20d8e7b2a
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: e135fa01-fede-4285-b4dd-2d23acbb4d26
feature: Mobile Forms
exl-id: 248e56c7-51b7-41d3-8bc9-a5d737bf178b
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '379'
ht-degree: 0%

---

# Utforma formulärmallar för HTML5-formulär {#designing-form-templates-for-html-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

HTML5-formulärkomponenten i AEM erbjuder återgivning av XFA-formulärmallen till HTML5-formatet. Blankettmallarna kan utformas med [Forms Designer](https://www.adobe.com/go/learn_aemforms_designer_63) och använda HTML5-renderingsfunktionen. Dessa formulärmallar, tillsammans med deras resurser, kan ligga i AEM, filsystem eller visas via http. Men om du tänker hantera dina formulär med Forms Manager bör mallarna och resurserna finnas i AEM.

Även om HTML5-formulär i stor utsträckning överensstämmer med PDF forms beteende finns det vissa funktioner i båda formaten som inte kan användas i det andra formatet. Hur streckkoder tillämpas på ett PDF-formulär i Adobe Reader varierar till exempel från ett mobilformulär eller hur ett formulär signeras digitalt varierar också mellan formaten. Mer information om sådana variationer finns i [Skillnaden mellan HTML5-formulär och PDF forms](/help/forms/using/feature-differentiation-html5-forms-pdf-forms.md).

Vanliga XFA-funktioner finns i följande metodtips och riktlinjer för att utforma ett formulär som fungerar i båda formaten.

## Funktioner i AEM Forms Designer för HTML5 Forms {#capabilities-in-aem-forms-designer-for-html-forms}

### Förhandsgranska HTML {#preview-html}

Fliken Förhandsgranska HTML har lagts till i designläget så att formulärdesigners kan förhandsgranska formulär i HTML 5-format under designprocessen. Mer information om hur du aktiverar och konfigurerar den här funktionen i AEM Forms Designer finns i [Förhandsgranska HTML](/help/forms/using/preview-xdp-forms-html.md).

### Klottra signaturer {#scribble-signature}

Det främsta målet för HTML5-formulär är pekenheter. Därför har en ny kontroll för signering i klotter lagts till i AEM Forms Designer. Du kan klicka på eller dra och släppa kontrollen för signering av skript på formulärmallen och konfigurera den. Det återges som ett klottrigt fält i HTML5-renderingen och kan användas för att klottra signaturer på pekenheter. På stationära datorer kan den användas som ett klotterfält med hjälp av muskontroll. Mer information om hur du använder den här funktionen finns i [XFA-skriptfält](/help/forms/using/scribble-signature.md).

![4](assets/4.png)
