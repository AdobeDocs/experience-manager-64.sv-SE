---
title: Initiera en ny process med befintliga processdata på arbetsytan i AEM Forms
seo-title: Initiating a new process with existing process data in AEM Forms workspace
description: Se hur du kan initiera en ny process med befintliga processdata i AEM Forms arbetsyta.
seo-description: See how you can initiate a new process with existing process data in AEM Forms workspace.
uuid: 57a7f414-c9f2-4acc-890a-e29e1adff084
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-workspace
discoiquuid: 4d55a100-1876-41f0-a06f-7a009c934f3d
exl-id: d7bdbd22-97b0-45cd-8e72-43ca3d0d1215
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 0%

---

# Initiera en ny process med befintliga processdata på arbetsytan i AEM Forms {#initiating-a-new-process-with-existing-process-data-in-aem-forms-workspace}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan initiera en ny process med data från en befintlig processdata. Behovet av att initiera en ny process från befintliga processdata uppstår när vi måste använda samma formulär ofta med få innehållsändringar som t.ex. för formulär som inte har betalats. Den här funktionen sparar tid och arbete åt användarna, särskilt när processen har långa formulär att fylla i.

Så här startar du en ny process från befintliga processdata:-

1. Gör något av följande:

   * Klicka på den processinstans vars data du vill använda i Spärra/knip. Klicka på den aktivitetsrad som motsvarar startpunkten i vyn Processhistorik i den högra rutan.
   * I Spärra/knip väljer du en sökmall som visar en lista med processinstanser. Markera instansen vars data du vill använda.
   * I **[!UICONTROL To-Do]** väljer du uppgiften. Klicka på **[!UICONTROL History]** och välj den åtgärd som initierade processinstansen.

   ![start3](assets/start3.png) ![start1](assets/start1.png)

1. Klicka på **[!UICONTROL Start]**. Ett adaptivt formulär för den nya processinstansen visas med förfyllda data.

1. Uppdatera data efter behov och klicka på antingen **[!UICONTROL Complete]** eller en lämplig knapp i formuläret.
