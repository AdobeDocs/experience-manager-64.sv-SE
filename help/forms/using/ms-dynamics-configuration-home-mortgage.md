---
title: Konfigurera Microsoft Dynamics 365 för arbetsflödet för inteckning i hemmet på referenswebbplatsen för We.Finance
seo-title: Configure Microsoft Dynamics 365 for the home mortgage workflow of the We.Finance reference site
description: Lär dig hur du kan utnyttja Microsoft® Dynamics 365-tjänsterna med hjälp av adaptiva formulär för heminteckningsarbetsflödet på webbplatsen Web.Finance Reference
seo-description: Learn how to leverage the Microsoft® Dynamics 365 services through adaptive forms for the home mortgage workflow of the We.Finance Reference site
uuid: a0656d90-84c7-46d1-9a16-dadcc19ff9ef
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: develop, Configuration
discoiquuid: 6b31397a-fb06-4043-9368-59fb4fce8afa
exl-id: 7e1f417e-6a6b-4ef2-a453-866331fe3e96
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '485'
ht-degree: 0%

---

# Konfigurera Microsoft Dynamics 365 för arbetsflödet för inteckning i hemmet på referenswebbplatsen för We.Finance {#configure-microsoft-dynamics-for-the-home-mortgage-workflow-of-the-we-finance-reference-site}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Lär dig hur du kan utnyttja Microsoft® Dynamics 365-tjänsterna med hjälp av adaptiva formulär för heminteckningsarbetsflödet på webbplatsen Web.Finance Reference

## Översikt {#overview}

Microsoft® Dynamics 365 är en CRM- och ERP-programvara (Customer Relationship Management) som innehåller företagslösningar för att skapa och hantera kundkonton, kontakter, leads, möjligheter och ärenden.

AEM Forms tillhandahåller en molntjänst för integrering av Dynamics 365 med [Forms dataintegrering](/help/forms/using/data-integration.md) -modul. Scenariot [Programgenomgång av Home Mortgage med Microsoft® Dynamics](/help/forms/using/finance-reference-site-walkthrough.md#home-mortgage-application-walkthrough-with-microsoft-dynamics) visar hur en kund använder referenswebbplatsen We.Finance för att ansöka om ett lån när webbplatsen använder Microsoft® Dynamics för Forms dataintegrering. Innan du kan använda genomgången av Home Mortgage-programmet med Microsoft® Dynamics-scenariot måste du konfigurera Microsoft® Dynamics 365 så att det används med referenswebbplatsen We.Finance.

## Förutsättningar {#prerequisites}

Innan du börjar konfigurera och konfigurera Dynamics 365 måste du se till att du har:

* [Konfigurera AEM Forms referenswebbplatser](/help/forms/using/setup-reference-sites.md).

* AEM 6.3 Forms Service Pack 1 och senare
* Microsoft® Dynamics 365-konto
* Registrerat program för tjänsten Dynamics 365 med Microsoft® Azure Active Directory
* Klient-ID och klienthemlighet för det registrerade programmet

## Länka inteckningsberäkningen till webbplatsens startsida {#link-the-home-mortgage-calculator-with-your-site-home-page}

1. Gå till följande sida på författarinstansen:

   https://[server]:[port]/editor.html/content/we-finance/global/en/loan-landing-page.html

1. Bläddra nedåt till Hemmedarbetarkalkylatorn.
1. Markera den högra kolumnens panel (räknare) och tryck för att visa snabbmenyn. Tryck på Konfigurera på snabbmenyn. Dialogrutan Redigera AEM Forms-behållare visas.

   ![kalkylatorconfigurepanel](assets/calculatorconfigurepanel.png)

1. I dialogrutan Redigera AEM Forms-behållare bläddrar du till resurssökvägen och väljer en beräkning av bolån på följande väg och trycker **Bekräfta**:

   formsanddocuments/We.Finance/MS Dynamics/

   ![selectassetpath](assets/selectassetpath.png)

1. Tryck **Klar**.
1. Publicera den redigerade sidan.

   >[!NOTE]
   >
   >Bindningen av beräkningsfälten med FDM är förkonfigurerad via referenspaketet för We.Finance. Om du vill visa bindningen kan du öppna formuläret i redigeringsläget och se de binda referenserna för fältet.

1. Om du vill skapa en anpassad enhet för lagring av ansökningspost för bostadslåneprogram importerar du AEMFormsFSIRefsite_1_0.zip-lösningspaketet till din Microsoft® Dynamics-instans:

   1. Hämta paketet från:

      `https://[server]:[port]/content/aemforms-refsite-collaterals/we-finance/home-mortgage/ms-dynamics/AEMFormsFSIRefsite_1_0.zip`

   1. Importera lösningspaketet till instansen av Microsoft® Dynamics. I din Microsoft® Dynamics-instans går du till **Inställningar** > **Lösningar** och sedan trycka **Importera**.

1. Om du vill ställa in kontaktinformation för användare som används i refsite importerar du Sarah Rose Contact.CSV-paketet till din Microsoft® Dynamics-instans:

   1. Hämta paketet från:

      `https://[server]:[port]/content/aemforms-refsite-collaterals/we-finance/home-mortgage/ms-dynamics/Sarah%20Rose%20Contact.csv`

   1. Importera paketet till din Microsoft® Dynamics-instans. I din Microsoft® Dynamics-instans går du till **Försäljning** > **Kontakter** och sedan trycka **Importera data**.
