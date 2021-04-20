---
title: Konfigurera AEM Forms för att skicka formulärdata till en JEE-process från AEM Forms
seo-title: Konfigurera AEM Forms för att skicka formulärdata till en JEE-process från AEM Forms
description: Med AEM Forms kan ni integrera adaptiva formulär med AEM Forms i JEE-processer för bearbetning av formulärdata.
seo-description: Med AEM Forms kan ni integrera adaptiva formulär med AEM Forms i JEE-processer för bearbetning av formulärdata.
uuid: ee7ea442-d604-4520-9af5-ad40ec4927a1
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: 03619a67-d1ea-4b80-b1a6-0c65a9e9212f
role: Administrator
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 0%

---


# Konfigurera AEM Forms för att skicka formulärdata till en AEM Forms på en JEE-process {#configuring-aem-forms-to-submit-form-data-to-an-aem-forms-on-jee-process}

Med adaptiva formulär kan data skickas till en AEM Forms om JEE-process för vidare bearbetning. Med den kan du aktivera en AEM Forms on JEE-process med data som är tillgängliga från det skickade formuläret. Utför följande steg för att göra det möjligt för din AEM Forms-instans att skicka ett adaptivt formulär till AEM Forms i JEE-processen:

## Konfigurera din AEM Forms-server {#configure-your-aem-forms-server}

Utför följande steg för att göra det möjligt för AEM formulärserver att skicka data till en AEM Forms på en JEE-server:

1. Gå till AEM webbkonfigurationskonsol på https://[*värd*]:[*port*]/system/console/configMgr.

1. Leta reda på och klicka på **SDK-komponenten för klienten i Adobe**.
1. Klicka för att redigera konfigurationsserverns URL, användarnamn och lösenord för AEM Forms på JEE-servern.
1. Granska inställningarna och klicka på **Spara**.

![SDK-konfiguration för Adobe-klient](assets/clientsdkconfiguration.jpg)

## Mappa data med processfält {#map-data-with-process-fields}

När din AEM Forms har konfigurerats mappar du data-XML och bilagor från det skickade formuläret till fälten i AEM Forms om JEE-processen. Så här gör du:

1. I webbkonfigurationskonsolen klickar du för att redigera LiveCycle Process Locator och Invoker **-konfigurationen för guiden.**
1. Ange följande parametrar:

   * **Namn på XML-parametern**  data(obligatorisk): Ange XML-egenskapsfilen för den AEM Forms on JEE-process som ska bearbeta skickade data. Standardvärdet är **dataxml**.
   * **Namn på parametern**  för bifogade filer (valfritt): Ange listan med dokumentobjekt som AEM Forms on JEE-processen behöver bearbeta. Standardvärdet är **fileAttachmentsList**.

1. Granska inställningarna och klicka på **Spara**.

![Guide LiveCycle Process Locator och Invoker](assets/test3.jpg)

När åtgärden Skicka till Forms Workflow har konfigurerats listas de AEM Forms på JEE-serverprocesser som innehåller den angivna XML-parametern.
