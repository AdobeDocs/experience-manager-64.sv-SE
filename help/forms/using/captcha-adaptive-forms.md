---
title: Använda CAPTCHA i anpassningsbara formulär
seo-title: Using CAPTCHA in adaptive forms
description: Lär dig hur du konfigurerar AEM CAPTCHA- eller Google reCAPTCHA-tjänsten i adaptiva formulär.
seo-description: Learn how to configure AEM CAPTCHA or Google reCAPTCHA service in adaptive forms.
uuid: 8bcb0dd7-b43c-4a36-8f6b-7875b68f9ba1
contentOwner: vishgupt
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author, adaptive_forms
discoiquuid: 32369b0b-5abf-487d-ae6b-972c254eb7e2
feature: Adaptive Forms
exl-id: 1129004b-5e8b-42fd-98ed-f203edde93b9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '662'
ht-degree: 0%

---

# Använda CAPTCHA i anpassningsbara formulär {#using-captcha-in-adaptive-forms}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

CAPTCHA (Completely Automated Public Turing test to tell Computers and Humans Apart) är ett program som ofta används vid onlinetransaktioner för att skilja mellan människor och automatiserade program eller organ. Det utgör en utmaning och utvärderar användarens svar för att avgöra om det är en människa eller en robot som interagerar med webbplatsen. Det förhindrar användaren att fortsätta om testet misslyckas och gör onlinetransaktionerna säkra genom att förhindra att skräppost eller skadliga syften publiceras.

AEM Forms stöder CAPTCHA i adaptiva former. Du kan använda tjänsten reCAPTCHA från Google för att implementera CAPTCHA.

>[!NOTE]
>
>AEM Forms har endast stöd för reCaptcha v2. Andra versioner stöds inte.
>
>CAPTCHA i adaptiva formulär stöds inte i offlineläge i AEM Forms-appen.

## Konfigurera ReCAPTCHA-tjänsten av Google {#google-recaptcha}

Formulärförfattare kan använda tjänsten reCAPTCHA från Google för att implementera CAPTCHA i anpassningsbara formulär. Den har avancerade CAPTCHA-funktioner för att skydda er webbplats. Mer information om hur reCAPTCHA fungerar finns i [Google reCAPTCHA](https://developers.google.com/recaptcha/).

![recaptcha](assets/recaptcha.png)

Så här implementerar du tjänsten reCAPTCHA i AEM Forms:

1. Hämta [API-nyckelpar för reCAPTCHA](https://www.google.com/recaptcha/admin) från Google. Den innehåller en webbplatsnyckel och hemlighet.
1. Skapa konfigurationsbehållare för molntjänster.

   1. Gå till **[!UICONTROL Tools > General > Configuration Browser]**.
      * Se [Configuration Browser-dokumentation](/help/sites-administering/configurations.md) för mer information.
   1. Gör följande för att aktivera den globala mappen för molnkonfigurationer eller hoppa över det här steget för att skapa och konfigurera en annan mapp för molntjänstkonfigurationer.

      1. I konfigurationsläsaren väljer du **[!UICONTROL global]** mapp och tryck **[!UICONTROL Properties]**.
      1. Aktivera i dialogrutan Konfigurationsegenskaper **[!UICONTROL Cloud Configurations]**.
      1. Tryck **[!UICONTROL Save & Close]** för att spara konfigurationen och stänga dialogrutan.
   1. Tryck på **[!UICONTROL Create]**.
   1. I dialogrutan Skapa konfiguration anger du en rubrik för mappen och aktiverar **[!UICONTROL Cloud Configurations]**.
   1. Tryck **[!UICONTROL Create]** för att skapa en mapp som är aktiverad för molntjänstkonfigurationer.


1. Konfigurera molntjänsten för reCAPTCHA.

   1. Gå till AEM ![verktyg](assets/tools.png) >  **Cloud Services**.
   1. Tryck på **[!UICONTROL reCAPTCHA]**. Sidan Konfigurationer öppnas. Välj den konfigurationsbehållare som skapades i föregående steg och tryck på **[!UICONTROL Create]**.
   1. Ange namn, platsnyckel och hemlig nyckel för reCAPTCHA-tjänsten och tryck på **[!UICONTROL Create]** för att skapa molntjänstkonfigurationen.
   1. I dialogrutan Redigera komponent anger du platsen och de hemliga nycklarna som fås i steg 1. Tryck **[!UICONTROL Save Settings]** och sedan trycka **[!UICONTROL OK]** för att slutföra konfigurationen.

   När reCAPTCHA-tjänsten har konfigurerats är den tillgänglig för användning i adaptiva formulär. Mer information finns i [Använda CAPTCHA i anpassningsbara formulär](#using-captcha).

## Använd CAPTCHA i anpassningsbara formulär {#using-captcha}

Så här använder du CAPTCHA i adaptiva former:

1. Öppna ett anpassat formulär i redigeringsläge.

   >[!NOTE]
   >
   >Kontrollera att den konfigurationsbehållare som valts när du skapar det adaptiva formuläret innehåller molntjänsten reCAPTCHA. Du kan också redigera adaptiva formuläregenskaper för att ändra konfigurationsbehållaren som är kopplad till formuläret.

1. Dra från komponentwebbläsaren och släpp **[!UICONTROL Captcha]** på den adaptiva formen.

   >[!NOTE]
   >
   >Det går inte att använda mer än en Captcha-komponent i ett adaptivt formulär. Du bör inte heller använda CAPTCHA i en panel som är markerad för lazy loading eller i ett fragment.

   >[!NOTE]
   >
   >Captcha är tidskänsligt och upphör om ungefär en minut. Därför rekommenderar vi att du placerar Captcha-komponenten precis före Skicka-knappen i den anpassade formen.

1. Välj den Captcha-komponent som du har lagt till och tryck på ![cmppr](assets/cmppr.png) om du vill redigera dess egenskaper.
1. Ange en titel för CAPTCHA-widgeten. Standardvärdet är **Captcha**. Välj **[!UICONTROL Hide title]** om du inte vill att rubriken ska visas.
1. Från **[!UICONTROL Captcha service]** nedrullningsbar meny, välja **[!UICONTROL reCaptcha]** för att aktivera tjänsten reCAPTCHA om du har konfigurerat den enligt beskrivningen i [Tjänsten ReCAPTCHA från Google](#google-recaptcha). Välj en konfiguration i listrutan Inställningar. Välj också storleken som **[!UICONTROL Normal]** eller **[!UICONTROL Compact]** för widgeten reCAPTCHA.

   >[!NOTE]
   >
   >Markera inte **[!UICONTROL Default]** från listrutan Captcha-tjänst eftersom AEM CAPTCHA-tjänsten är föråldrad.

1. Spara egenskaperna.

Tjänsten reCAPTCHA är aktiverad i det adaptiva formuläret. Du kan förhandsgranska formuläret och se hur CAPTCHA fungerar.
