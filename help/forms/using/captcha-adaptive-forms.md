---
title: Använda CAPTCHA i anpassningsbara formulär
seo-title: Använda CAPTCHA i anpassningsbara formulär
description: Lär dig hur du konfigurerar AEM CAPTCHA- eller Google reCAPTCHA-tjänsten i adaptiva formulär.
seo-description: Lär dig hur du konfigurerar AEM CAPTCHA- eller Google reCAPTCHA-tjänsten i adaptiva formulär.
uuid: 8bcb0dd7-b43c-4a36-8f6b-7875b68f9ba1
contentOwner: vishgupt
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 32369b0b-5abf-487d-ae6b-972c254eb7e2
translation-type: tm+mt
source-git-commit: 4dbb6af1c0a76aabc003749d7fa76f8c6e41e726
workflow-type: tm+mt
source-wordcount: '636'
ht-degree: 0%

---


# Använda CAPTCHA i anpassningsbara formulär {#using-captcha-in-adaptive-forms}

CAPTCHA (Completely Automated Public Turing test to tell Computers and Humans Apart) är ett program som ofta används vid onlinetransaktioner för att skilja mellan människor och automatiserade program eller organ. Det utgör en utmaning och utvärderar användarens svar för att avgöra om det är en människa eller en robot som interagerar med webbplatsen. Det förhindrar användaren att fortsätta om testet misslyckas och gör onlinetransaktionerna säkra genom att förhindra att skräppost eller skadliga syften publiceras.

AEM Forms stöder CAPTCHA i adaptiva former. Du kan använda tjänsten reCAPTCHA av Google för att implementera CAPTCHA.

>[!NOTE]
>
>AEM Forms har endast stöd för reCaptcha v2. Andra versioner stöds inte.
>
>CAPTCHA i adaptiva formulär stöds inte i offlineläge i appen AEM Forms.

## Konfigurera ReCAPTCHA-tjänsten av Google {#google-recaptcha}

Formulärförfattare kan använda tjänsten reCAPTCHA av Google för att implementera CAPTCHA i anpassningsbara formulär. Den har avancerade CAPTCHA-funktioner för att skydda er webbplats. Mer information om hur reCAPTCHA fungerar finns i [Google reCAPTCHA](https://developers.google.com/recaptcha/).

![recaptcha](assets/recaptcha.png)

Så här implementerar du tjänsten reCAPTCHA i AEM Forms:

1. Hämta [reCAPTCHA API-nyckelpar](https://www.google.com/recaptcha/admin) från Google. Den innehåller en webbplatsnyckel och hemlighet.
1. Skapa konfigurationsbehållare för molntjänster.

   1. Gå till **[!UICONTROL Tools > General > Configuration Browser]**.
   1. Gör följande för att aktivera den globala mappen för molnkonfigurationer eller hoppa över det här steget för att skapa och konfigurera en annan mapp för molntjänstkonfigurationer.

      1. Markera mappen i Configuration Browser och tryck på **[!UICONTROL global]** den **[!UICONTROL Properties]**.
      1. Aktivera **[!UICONTROL Cloud Configurations]** i dialogrutan Konfigurationsegenskaper.
      1. Tryck för **[!UICONTROL Save & Close]** att spara konfigurationen och stänga dialogrutan.
   1. Tryck på **[!UICONTROL Create]** i Configuration Browser.
   1. I dialogrutan Skapa konfiguration anger du en rubrik för mappen och aktiverar **[!UICONTROL Cloud Configurations]**.
   1. Tryck för **[!UICONTROL Create]** att skapa mappen som är aktiverad för molntjänstkonfigurationer.


1. Konfigurera molntjänsten för reCAPTCHA.

   1. Gå till ![verktyg](assets/tools.png) > **Cloud Service** i din AEM-författarinstans.
   1. Tryck på **[!UICONTROL reCAPTCHA]**. Sidan Konfigurationer öppnas. Välj den konfigurationsbehållare som skapades i föregående steg och tryck sedan på **[!UICONTROL Create]**.
   1. Ange Namn, Webbplatsnyckel och Hemlig nyckel för reCAPTCHA-tjänsten och tryck för **[!UICONTROL Create]** att skapa molntjänstkonfigurationen.
   1. I dialogrutan Redigera komponent anger du platsen och de hemliga nycklarna som fås i steg 1. Tryck **[!UICONTROL Save Settings]** och tryck sedan på **[!UICONTROL OK]** för att slutföra konfigurationen.
   När reCAPTCHA-tjänsten har konfigurerats är den tillgänglig för användning i adaptiva formulär. Mer information finns i [Använda CAPTCHA i adaptiva formulär](#using-captcha).

## Använd CAPTCHA i anpassningsbara formulär {#using-captcha}

Så här använder du CAPTCHA i adaptiva former:

1. Öppna ett anpassat formulär i redigeringsläge.

   >[!NOTE]
   >
   >Kontrollera att den konfigurationsbehållare som valts när du skapar det adaptiva formuläret innehåller molntjänsten reCAPTCHA. Du kan också redigera adaptiva formuläregenskaper för att ändra konfigurationsbehållaren som är kopplad till formuläret.

1. Dra komponenten från komponentwebbläsaren till det adaptiva formuläret och släpp den **[!UICONTROL Captcha]** .

   >[!NOTE]
   >
   >Det går inte att använda mer än en Captcha-komponent i ett adaptivt formulär. Du bör inte heller använda CAPTCHA i en panel som är markerad för lazy loading eller i ett fragment.

   >[!NOTE]
   >
   >Captcha är tidskänsligt och upphör om ungefär en minut. Därför rekommenderar vi att du placerar Captcha-komponenten precis före Skicka-knappen i den anpassade formen.

1. Markera den Captcha-komponent som du har lagt till och tryck på ![cmpr](assets/cmppr.png) för att redigera dess egenskaper.
1. Ange en titel för CAPTCHA-widgeten. The default value is **Captcha**. Välj **[!UICONTROL Hide title]** om du inte vill att rubriken ska visas.
1. I listrutan väljer du **[!UICONTROL Captcha service]** att aktivera tjänsten reCAPTCHA om du har konfigurerat den enligt beskrivningen i **[!UICONTROL reCaptcha]** tjänsten ReCAPTCHA från Google [](#google-recaptcha). Välj en konfiguration i listrutan Inställningar. Du kan även välja storlek som **[!UICONTROL Normal]** eller **[!UICONTROL Compact]** för widgeten reCAPTCHA.

   >[!NOTE]
   >
   >Välj inte **[!UICONTROL Default]** i listrutan Captcha-tjänst eftersom standardtjänsten AEM CAPTCHA är inaktuell.

1. Spara egenskaperna.

Tjänsten reCAPTCHA är aktiverad i det adaptiva formuläret. Du kan förhandsgranska formuläret och se hur CAPTCHA fungerar.
