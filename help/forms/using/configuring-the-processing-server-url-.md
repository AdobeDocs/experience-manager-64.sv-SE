---
title: Konfigurera AEM DS-inställningar
seo-title: Konfigurera AEM DS-inställningar
description: Du måste ange URL:en för bearbetningsservern innan du skickar ett formulär.
seo-description: Du måste ange URL:en för bearbetningsservern innan du skickar ett formulär.
uuid: 2b415c99-275b-4b67-bb8e-35329514ecbb
contentOwner: amgoyal
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: fbb9044a-a737-45f6-8062-0ef5424a92f8
role: Administratör
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '232'
ht-degree: 0%

---


# Konfigurerar AEM DS-inställningar {#configuring-aem-ds-settings}

I den här artikeln beskrivs hur du konfigurerar **AEM DS Settings Service**. Den här inställningen kan användas i flera scenarier, till exempel:

* I korrespondenshantering

   * För konfigurering av AEM Forms Workflow
   * När du använder formulärportalen för att spara utkast/inskickning på fjärrbasis

* I adaptiva formulär för fall när adaptiv form skickas från publiceringsinstansen

Så här konfigurerar du **[!UICONTROL AEM DS Settings]**:

1. Öppna Configuration Manager på publiceringsinstansen med URL:en:

   *http://localhost:port/system/console/configMgr*.

   ![aem_web_configuration_console](assets/aem_web_configuration_console.png)

1. I fönstret **[!UICONTROL Adobe Experience Manager Web Console Configuration]** letar du reda på och klickar på alternativet **[!UICONTROL AEM DS Settings]**.

   ![ds_settings](assets/ds_settings.png)

1. Fönstret **[!UICONTROL AEM DS Settings Service]** visar de vanliga konfigurationsinställningarna för AEM DS-komponenter.

   ![ds_settings_1](assets/ds_settings_1.png)

1. Lägg till följande information i respektive fält:

   **[!UICONTROL Processing Server URL]**: Bearbetningsservern är den server där Forms- eller AEM-arbetsflödet måste aktiveras. Detta kan vara samma som URL:en för den AEM författarinstansen eller den andra server-URL:en (d.v.s. http:// localhost:port/).

   **[!UICONTROL Processing Server User Name]**: Användarnamn för arbetsflöde  [baserat på den server-URL som används]

   **[!UICONTROL Processing Server Password]**: Lösenord för arbetsflödesanvändare

   >[!NOTE]
   >
   >* När du använder arbetsflödena Forms eller AEM måste du konfigurera tjänsten DS-inställningar innan du skickar något från publiceringsservern. I annat fall ska inlämningen av formuläret misslyckas.

