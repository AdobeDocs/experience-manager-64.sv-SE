---
title: AEM datorprogram för AEM Forms
seo-title: AEM desktop app for AEM Forms
description: AEM kan du mappa Adobe Experience Manager (AEM) Assets-databasen och AEM Forms binära filer till en nätverkskatalog på datorn. Läs mer om de resurser som stöds AEM skrivbordsappen och hur du aktiverar AEM Forms för AEM.
seo-description: AEM desktop app lets you map the Adobe Experience Manager (AEM) Assets repository and AEM Forms binary files to a network directory on your system. Learn more about the assets supported in AEM desktop app and how to enable AEM Forms for AEM desktop app.
uuid: 99e0f2fb-8623-45bb-8e2e-5c5d6f482366
contentOwner: khsingh
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: manage
discoiquuid: c30332b6-e012-442d-8e84-28832c116c7b
noindex: true
role: Admin
exl-id: 26cd0851-cadf-4a8f-b3bf-59f77671f584
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '479'
ht-degree: 0%

---

# AEM datorprogram för AEM Forms {#aem-desktop-app-for-aem-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM kan du mappa Adobe Experience Manager (AEM) Assets-databasen och AEM Forms binära filer till en nätverkskatalog på datorn. Du kan visa synkroniserade resurser och binära filer i en filutforskare och använda olika program för att redigera filerna efter behov. Förutom att visa filerna kan du även skapa, överföra och ta bort de binära filerna. Du kan också öppna, redigera och spara filer direkt från programmet. Du kan till exempel öppna och redigera en XDP-fil direkt i Designer. De ändringar du gör av resurserna lokalt återspeglas i AEM Assets-databasen och AEM Forms användargränssnitt.

Du kan hämta programmet från en AEM. Mer information om hur du hämtar programmet finns i [Versionsinformation för AEM](https://helpx.adobe.com/experience-manager/desktop-app/release-notes.html).

## AEM Forms-resurser som stöds AEM datorprogrammet {#aem-forms-assets-supported-in-aem-desktop-app}

Du kan använda appen för att synkronisera binära AEM Forms-filer av följande typ: Formulärmallar (.xdp), PDF-formulär (.pdf), Dokument (.pdf), Bilder, XML-schema (.xsd) och formatmallar (.xfs). I programmet visas alla andra filer (filer som inte stöds) som 0-byte-filer. Om du listar filer som inte stöds som 0-byte-filer ser du till att användaren är medveten om att det finns andra resurser på AEM Forms-servern.

>[!NOTE]
>
>Ett filnamn får bara innehålla alfanumeriska tecken, bindestreck eller understreck.

## Aktivera AEM Forms för AEM {#enable-aem-forms-for-aem-desktop-app}

AEM använder WebDAV-protokoll i Microsoft Windows och SMB1 i Mac OS X för att ansluta till en AEM Forms-server. AEM Forms-servern är inte aktiverad att synkronisera binära filer och andra resurser med en WebDAV- eller SMB-klient. Så här aktiverar du AEM Forms för AEM datorprogram:

1. Logga in på AEM Forms som administratör.
1. Klicka på i författarinstansen ![adobeexperienceManager](assets/adobeexperiencemanager.png) **[!UICONTROL Adobe Experience Manager > Tools]** ![hammare](assets/hammer.png) **[!UICONTROL > Deployment > Operations > Web Console]**. Webbkonsolen öppnas i ett nytt fönster.
1. I webbkonsolfönstret letar du upp och öppnar **[!UICONTROL FormsManager AddOn Configuration]** alternativ.
1. Avmarkera alternativet **[!UICONTROL Asynchronously Sync Resources]** och klicka **[!UICONTROL Save]**.
1. Starta om AEM Forms-servern. Efter omstarten är AEM Forms-servern aktiverad för att acceptera och dela innehåll med AEM skrivbordsapp.
1. Öppna appen och anslut till AEM Forms-servern.

   När anslutningen lyckades fyller programmet i `content/dam` och `content/dam/formsanddocuments` mappar. Förutom att flytta filer från mapparna ovan till lokala mappar kan du använda appen för att flytta innehåll mellan automatiskt ifyllda mappar.
