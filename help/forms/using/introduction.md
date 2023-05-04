---
title: Introduktion till HTML5-formulär
seo-title: Introduction to HTML5 forms
description: HTML5-formulär är en ny funktion i Adobe Experience Manager 6.0 (AEM 6.0) som erbjuder återgivning av XFA-formulärmallar i HTML5-format.
seo-description: HTML5 forms is a new capability in Adobe Experience Manager 6.0 (AEM 6.0) software that offers rendering of XFA form templates in HTML5 format.
uuid: a68f1ca1-32dd-48f9-9359-8f09abd1c3de
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: hTML5_forms
discoiquuid: b8cd2656-8bc2-4bd7-a3d6-dc76b0a2d429
feature: Mobile Forms
exl-id: c69b5ae6-c5c5-46df-8290-3e41470cd09e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Introduktion till HTML5-formulär {#introduction-to-html-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

HTML5-formulär är en ny funktion i Adobe Experience Manager 6.0 (AEM 6.0) som erbjuder återgivning av XFA-formulärmallar i HTML5-format. Denna funktion gör det möjligt att återge formulär på mobila enheter och webbläsare på datorer där XFA-baserad PDF inte stöds. HTML5-formulär har inte bara stöd för XFA-formulärmallarnas befintliga funktioner, utan även nya funktioner, som klottersignaturer, för mobila enheter.

HTML5-formulär genererar dokument som baseras på HTML 5-standardkonstruktioner. Du kan visa HTML5-formulär i alla moderna webbläsare som stöder HTML5. Inga ytterligare webbläsarplugin-program behöver installeras för webbläsarna. Mer information om vilka webbläsare som stöds finns i [Klientplattformar som stöds](https://adobe.com/go/learn_aemforms_supportedplatforms_63).

![](do-not-localize/mobile_form_on_an_ipad_date_14.png)

## Viktiga funktioner i HTML5-formulär {#key-capabilities-of-html-forms-br}

* Återger befintliga XFA-formulär i HTML5 som stöds i alla kompatibla webbläsare.
* Använder XFA:s standardfunktioner för blankettkonstruktion för att skapa blanketter för mobila enheter.
* Använder dynamiska XFA-funktioner i HTML5-format.
* Använder mycket exakt SVG-textlayout (SVG 1.1) för att matcha PDF-textlayouten.
* Tillhandahåller stöd för JavaScript och FormCalc.
* Sammanställer fragment dynamiskt till interaktiva formulär baserat på datadrivna händelser eller användarindata.
* Ger stöd för anpassad CSS som matchar formulärens utseende enligt företagets standarder.
* Möjliggör anpassade widgetar för datainhämtning.
* Ger stöd för integrering med webbprogram.

### Flerkanalspublicering {#multichannel-publishing}

Formulärutvecklare kan använda en XFA-mall för att återge formulär i PDF och HTML 5-format. Den här funktionen är bra i scenarier där du har en stor uppsättning XFA-formulär som kräver minimala ändringar för att kunna anpassa dig till HTML5-formulärdesignen. Du kan återge befintliga XFA-formulär till HTML5 för att ange olika enheter där XFA-baserad PDF ännu inte stöds.

## Hantera HTML5-formulär {#manage-html-forms}

AEM har också en enhetlig vy för att lista och hantera alla formulärmallar med AEM Forms användargränssnitt. Du kan aktivera, inaktivera, publicera och förhandsgranska formulär. Mer information finns i [Introduktion till hantering av formulär](/help/forms/using/introduction-managing-forms.md).

### Forms-anpassning {#forms-customization}

HTML5-formulär återger formulärmallar med HTML 5-standardkonstruktioner. Detta gör det enkelt att anpassa och utöka formulär i HTML5-format med hjälp av webbtekniker, främst CSS och JavaScript. Du kan enkelt anpassa utseendet på befintliga widgetar, skapa egna widgetar eller använda anpassade format i formulär. Mer information om hur du skapar anpassade widgetar och anpassar befintliga widgetar finns i [Plug in anpassade widgetar med HTML5-formulär](/help/forms/using/custom-widgets.md).
