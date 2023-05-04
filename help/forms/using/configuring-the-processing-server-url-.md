---
title: Konfigurera AEM DS-inställningar
seo-title: Configuring AEM DS settings
description: Du måste ange URL:en för bearbetningsservern innan du skickar ett formulär.
seo-description: You need to specify the processing server URL before you submit a form.
uuid: 2b415c99-275b-4b67-bb8e-35329514ecbb
contentOwner: amgoyal
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: fbb9044a-a737-45f6-8062-0ef5424a92f8
role: Admin
exl-id: f60beaae-4082-4165-8a37-9d9c94e360b2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 0%

---

# Konfigurera AEM DS-inställningar {#configuring-aem-ds-settings}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

I den här artikeln beskrivs hur du konfigurerar **Tjänsten AEM DS-inställningar**. Den här inställningen kan användas i flera scenarier, till exempel:

* I korrespondenshantering

   * För konfigurering av AEM Forms Workflow
   * När du använder formulärportalen för att spara utkast/inskickning på fjärrbasis

* I adaptiva formulär för fall när adaptiv form skickas från publiceringsinstansen

Följ de här stegen för att konfigurera **[!UICONTROL AEM DS Settings]**:

1. Öppna Configuration Manager på publiceringsinstansen med URL:en:

   *http://localhost:port/system/console/configMgr*.

   ![aem_web_configuration_console](assets/aem_web_configuration_console.png)

1. I **[!UICONTROL Adobe Experience Manager Web Console Configuration]** fönster, leta upp och klicka på **[!UICONTROL AEM DS Settings]** alternativ.

   ![ds_settings](assets/ds_settings.png)

1. The **[!UICONTROL AEM DS Settings Service]** I visas de vanliga konfigurationsinställningarna för AEM DS-komponenter.

   ![ds_settings_1](assets/ds_settings_1.png)

1. Lägg till följande information i respektive fält:

   **[!UICONTROL Processing Server URL]**: Bearbetningsservern är den server där Forms- eller AEM-arbetsflödet måste aktiveras. Detta kan vara samma som URL:en för den AEM författarinstansen eller den andra server-URL:en (d.v.s. http:// localhost:port/).

   **[!UICONTROL Processing Server User Name]**: Användarnamn för arbetsflödesanvändare [baserat på den server-URL som används]

   **[!UICONTROL Processing Server Password]**: Lösenord för arbetsflödesanvändare

   >[!NOTE]
   >
   >* När du använder arbetsflödena Forms eller AEM måste du konfigurera tjänsten DS-inställningar innan du skickar något från publiceringsservern. I annat fall ska inlämningen av formuläret misslyckas.

