---
title: Genomgång av referenswebbplatser för självbetjäning för medarbetare
seo-title: Självbetjäning för medarbetare
description: AEM Forms referenswebbplats visar hur man kan utnyttja AEM Forms funktioner för att genomföra personalrekrytering och självbetjäningsarbetsflöden.
seo-description: AEM Forms referenswebbplats visar hur man kan utnyttja AEM Forms funktioner för att genomföra personalrekrytering och självbetjäningsarbetsflöden.
uuid: ecc98e0d-c964-44dc-b219-9ebe92632d22
topic-tags: introduction
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d2695f71-5126-477c-ae6b-a964fb55728b
translation-type: tm+mt
source-git-commit: 8cbfa421443e62c0483756e9d5812bc987a9f91d
workflow-type: tm+mt
source-wordcount: '1626'
ht-degree: 0%

---


# Genomgång av referenswebbplats för medarbetares självbetjäning {#employee-self-service-reference-site-walkthrough}

## Förutsättning {#prerequisite}

Konfigurera referenswebbplatserna enligt beskrivningen i [Konfigurera och konfigurera AEM Forms referenswebbplatser](/help/forms/using/setup-reference-sites.md).

## Översikt {#overview}

Självbetjäningssystem för anställda, som i allmänhet finns på företagets intranät, ger personalen tillgång till en mängd information och tjänster som de kan få från sina skrivbord. Det ger medarbetarna möjlighet och fullständig kontroll att utföra åtgärder som att få tillgång till deras anställningsinformation, ansöka om ledighet och lämna in utgiftsrapporter. Å andra sidan bidrar det till att förbättra effektiviteten i processerna och minska kostnaderna samtidigt som medarbetarna hålls informerade och engagerade.

Självbetjäning för medarbetare visar hur man kan utnyttja AEM Forms för att införa självbetjäningssystemet för medarbetare i organisationen.

>[!NOTE]
>
>Självbetjäningsexempel för anställda finns både på referenswebbplatserna We.Finance och We.Gov. De exempel, bilder och beskrivningar som används i genomgången använder referenswebbplatsen We.Finance. Du kan dock köra de här användningsexemplen och granska artefakter med hjälp av We.Gov också. Om du vill göra det måste du ersätta **we-Finance** med **we-gov** i de angivna URL:erna.

## Genomgång av enkäter om intressekonflikter {#conflict-of-interest-questionnaire-walkthrough}

Organisationer ber då och då sina anställda att skicka in frågeformulär om intressekonflikter som identifierar externa aktiviteter eller personliga relationer hos deras anställda som kan komma i konflikt med deras organisation.

Övervakningsavdelningen på Sarah har bett medarbetarna att lämna in frågeformuläret Conflict of Interest.

### Sarah skickar frågeformuläret för intressekonflikter {#sarah-submits-the-conflict-of-interest-questionnaire}

Sarah går till sin organisations portal, loggar in och klickar på Medarbetare för att komma åt personalens instrumentpanel. Hon hittar ett frågeformulär om intressekonflikter på kontrollpanelen för medarbetare och klickar på **[!UICONTROL Apply]**.

![we-Finance-](assets/we-finance-home.png)
**homeFigure:** *Organisationsportal*

![employee-](assets/employee-dashboard.png)
**dashboardFigure:** *Personalkontrollpanel*

Sarah navigerar i formuläret med knappen Nästa och läser igenom avsnitten Introduktion och Definition. Hon svarar på frågorna i avsnittet Frågor. Slutligen skriver hon under och skickar in frågeformuläret.

Organisationsportalen och enkäten är responsiva och mobilvänliga. Följande arbetsflöde visar hur Sarah navigerar genom och skickar in enkäten på sin mobila enhet.

![conflict-form-on-mobile](assets/conflict-form-on-mobile.png)

**Så här fungerar det**

Organisationsportalen och personalkontrollpanelen är AEM Sites-sidor. På kontrollpanelen visas flera alternativ för självbetjäning, till exempel frågeformuläret Konflikt. Knappen Använd är länkad till ett anpassat formulär.

Det anpassningsbara formuläret använder regler för att visa/dölja information baserat på svaret som ges på fliken Frågor. Formuläret använder dessutom komponenten Klottra för signering på fliken Deklaration. Granska det adaptiva formuläret på `https://[authorHost]:[authorPort]/editor.html/content/forms/af/we-finance/employee/self-service/conflict-of-interest.html`.

**Se det själv**

Gå till `https://[publishHost]:[publishPort]/content/we-finance/global/en/self-service-forms.html` och logga in med `srose/srose` som användarnamn/lösenord för Sarah. Klicka på **[!UICONTROL Employee]** för att öppna instrumentpanelen och klicka sedan på **[!UICONTROL Apply]** i frågeformuläret Konflikt. Granska och skicka in enkäten.

### Gloria granskar och godkänner enkäten om intressekonflikter {#gloria-reviews-and-approves-the-conflict-of-interest-questionnaire-submission}

Det frågeformulär om intressekonflikter som Sarah har lämnat in tilldelas Gloria Rios för granskning. Gloria arbetar som efterlevnadsansvarig i organisationen. Gloria loggar in på sin AEM Inbox och granskar de uppgifter hon tilldelats. Hon godkänner frågeformuläret som lämnats in av Sarah och fullföljer uppgiften.

![conflict-](assets/conflict-inbox.png)
**inboxFigure:** *Glorias inkorg*

![conflict-](assets/conflict-approved.png)
**approvedFigure:** *Öppna uppgift*

**Så här fungerar det**

Skicka-åtgärden i frågan om intressekonflikter utlöser ett arbetsflöde som skapar en uppgift i Glorias inkorg för godkännande. Granska Formens Workflow på `https://[authorHost]:[authorPort]/editor.html/conf/global/settings/workflow/models/we-finance/employee/self-service/we-finance-employee-conflict-of-interest.html`

![employee-self-service-reference-site](assets/employee-self-service-reference-site.png)

**Se det själv**

Gå till `https://[publishHost]:[publishPort]/content/we-finance/global/en/login.html?resource=/aem/inbox.html` och logga in med `grios/password` som användarnamn/lösenord för Gloria Rios. Öppna uppgiften som har skapats för enkäten om intressekonflikter och godkänn den.

## Genomgång av applikationer med företagskort {#corporate-card-application-walkthrough}

Sarah reser mycket i jobbet och kräver ett kreditkort för att kunna betala sina räkningar i farten. Hon ansöker om ett företagskort via sin organisations personalportal.

### Sarah skickar in Corporate Card-applikationen {#sarah-submits-the-corporate-card-application}

Sarah går till sin organisations portal, loggar in och klickar på **[!UICONTROL Employee]** för att komma åt medarbetarinstrumentpanelen. Hon hittar ett Corporate Card-program på personalinstrumentpanelen och klickar på **[!UICONTROL Apply]**.

![we-Finance-home-1](assets/we-finance-home-1.png)
**Figure:** *Organisationsportal*

![employee-dashboard-1](assets/employee-dashboard-1.png)
**Figure:** *Employee Dashboard*

Hon klickar **[!UICONTROL Apply]** på Corporate Card. Ett enkelsidigt program öppnas. Hon fyller i alla uppgifter och klickar på **[!UICONTROL Apply]** för att skicka in ansökan.

![kort-formulär](assets/card-form.png)

**Så här fungerar det**

Organisationsportalen och personalkontrollpanelen är AEM Sites-sidor. På kontrollpanelen visas flera alternativ för självbetjäning, till exempel företagskortsprogrammet. Knappen Använd i programmet är länkad till ett anpassat formulär.

Den adaptiva formen för företagstillämpningar är en enkel, ensidig, responsiv adaptiv form. Den använder grundläggande adaptiva formulärkomponenter som text, telefon, numerisk ruta och nummernummerlista. Gå igenom det anpassade formuläret på:\
`https://[authorHost]:[authorPort]/editor.html/content/forms/af/we-finance/employee/self-service/corporate-card.html`.

**Se det själv**

Gå till `https://[publishHost]:[publishPort]/content/we-finance/global/en/self-service-forms.html` och logga in med `srose/srose` som användarnamn/lösenord för Sarah. Klicka på **[!UICONTROL Employee]** för att komma åt kontrollpanelen och klicka sedan på **[!UICONTROL Apply]** på Corporate Card-programmet. Fyll i uppgifterna och skicka in ansökan.

### Gloria granskar och godkänner ansökan {#gloria-reviews-and-approves-the-corporate-card-application}

Den ansökan om företagskort som Sarah har skickat in tilldelas Gloria Rios för granskning. Gloria loggar in på sin AEM Inbox och granskar de uppgifter hon tilldelats. Hon godkänner Sarah ansökan och slutför uppgiften.

![corporate-card-](assets/corporate-card-inbox.png)
**inboxFigure:** *Glorias inkorg*

![corporate-card-](assets/corporate-card-approved.png)
**approvedFigure:** *Open task*

**Så här fungerar det**

Arbetsflödet för att skicka in med Corporate Card-programmet aktiverar ett Forms-arbetsflöde som skapar en uppgift i Glorias inkorg för godkännande. Granska Formens Workflow på `https://[authorHost]:[authorPort]/editor.html/conf/global/settings/workflow/models/we-finance/employee/self-service/we-finance-employee-corporate-card.html`

![corporate-card-workflow-model](assets/corporate-card-workflow-model.png)

**Se det själv**

Gå till `https://[publishHost]:[publishPort]/content/we-finance/global/en/login.html?resource=/aem/inbox.html` och logga in med `grios/password` som användarnamn/lösenord för Gloria Rios. Öppna uppgiften som skapats för Corporate Card-programmet och godkänn den.

## Genomgång av inskickning av utgiftsrapport {#expense-report-submission-walkthrough}

När Sarah går på affärsresor måste hon skicka in utgiftsrapporter för godkännande. Med självbetjäningsalternativet i sin organisation kan hon skicka in utgiftsrapporten online.

### Sarah skickar programmet för utgiftsrapporten {#sarah-submits-the-expense-report-application}

Sarah går till sin organisations portal, loggar in och klickar på **[!UICONTROL Employee]** för att komma åt medarbetarinstrumentpanelen. Hon hittar programmet för utgiftsrapport på kontrollpanelen för medarbetare och klickar på **[!UICONTROL Apply]**.

![we-Finance-home-2](assets/we-finance-home-2.png)
**Figure:** *Organisationsportal*

![employee-dashboard-2](assets/employee-dashboard-2.png)
**Figure:** *Employee Dashboard*

Hon klickar på **[!UICONTROL Apply]** i programmet Utgiftsrapport. Ett programformulär öppnas med två flikar - Rapportnamn och Rapportdetaljer. Med ikonen **+** på fliken Rapportinformation kan hon lägga till fler än utgifter i en rapport.

Organisationsportalen och tillämpningarna är responsiva och mobilvänliga. Följande arbetsflöde visar hur Sarah navigerar genom och skickar utgiftsrapporten på sin mobila enhet.

![omkostnadsredovisning på mobilen](assets/expense-report-on-mobile.png)

**Så här fungerar det**

Organisationsportalen och personalkontrollpanelen är AEM Sites-sidor. På kontrollpanelen visas flera alternativ för självbetjäning, till exempel programmet Utgiftsrapport. Knappen Använd är länkad till ett anpassat formulär.

Flikarna Rapportnamn och Rapportdetaljer i det adaptiva formuläret är panelkomponenter. Panelen Rapportdetaljer innehåller panelen Utgift. Det är en upprepningsbar panel som gör att du kan lägga till flera utgifter i rapporten. Granska det adaptiva formuläret och dess konfigurationer på `https://[authorHost]:[authorPort]/editor.html/content/forms/af/we-finance/employee/expense-report.html`.

**Se det själv**

Gå till `https://[publishHost]:[publishPort]/content/we-finance/global/en/self-service-forms.html` och logga in med `srose/srose` som användarnamn/lösenord för Sarah. Klicka på **[!UICONTROL Employee]** för att öppna kontrollpanelen och klicka sedan på **[!UICONTROL Apply]** i programmet Utgiftsrapport. Fyll i uppgifterna och skicka in ansökan.

### Gloria granskar och godkänner utgiftsrapporten {#gloria-reviews-and-approves-the-expense-report}

Utgiftsrapporten från Sarah har tilldelats Gloria Rios för granskning. Gloria loggar in på sin AEM Inbox och granskar de uppgifter hon tilldelats. Hon godkänner Sarah ansökan och slutför uppgiften.

![utgiftsrapport-](assets/expense-report-inbox.png)
**inboxBild:** *Glorias inkorg*

![utgiftsrapport-](assets/expense-report-approved.png)
**godkändBild:** *Öppna uppgift*

**Så här fungerar det**

Arbetsflödet för att skicka in i programmet Utgiftsrapport utlöser ett Forms-arbetsflöde som skapar en uppgift i Glorias inkorg för godkännande. Granska Formens Workflow på `https://[authorHost]:[authorPort]/editor.html/conf/global/settings/workflow/models/we-finance/employee/self-service/we-finance-employee-expense-report-workflow.html`

![corporate-card-cost-report-workflow-model](assets/corporate-card-expense-report-workflow-model.png)

**Se det själv**

Gå till `https://[publishHost]:[publishPort]/content/we-finance/global/en/login.html?resource=/aem/inbox.html` och logga in med `grios/password` som användarnamn/lösenord för Gloria Rios. Öppna uppgiften som skapats för programmet Utgiftsrapport och godkänn den.

## Lämna programgenomgången {#leave-application-walkthrough}

Sarah planerar en familjesemester nästa månad och vill ansöka om en veckas ledighet från jobbet.

### Sarah skickar ledighetsansökan {#sarah-submits-the-leave-application}

Sarah går till sin organisations portal, loggar in och klickar på **[!UICONTROL Employee]** för att komma åt medarbetarinstrumentpanelen. Hon hittar programmet på kontrollpanelen för medarbetare och klickar på **[!UICONTROL Apply]**.

![we-Finance-home-3](assets/we-finance-home-3.png)
**Figure:** *Organisationsportal*

![employee-dashboard-3](assets/employee-dashboard-3.png)
**Figure:** *Employee Dashboard*

Lämna program öppnas med Sarah namn och anställnings-ID förifyllt i formuläret. Det visar också hennes ledighetsbalans och historia. Hon fyller i ledighetsinformationen och lämnar in ansökan om godkännande.

Organisationsportalen och tillämpningarna är responsiva och mobilvänliga. Följande arbetsflöde visar hur Sarah navigerar genom och skickar programmet på sin mobila enhet.

![leave-form-on-mobile](assets/leave-form-on-mobile.png)

**Så här fungerar det**

Organisationsportalen och personalkontrollpanelen är AEM Sites-sidor. På kontrollpanelen visas flera självbetjäningsalternativ, till exempel programmet Lämna. Knappen Använd är länkad till ett anpassat formulär.

Det anpassningsbara formuläret för ledighetsansökan baseras på datamodellen Employee Leaves. I avsnittet Lämna saldo fylls tabellen för återstående saldo i med tjänsten `getLeavesOf` Form Data Model. I start- och slutdatumfälten används regler för att validera att datumvärdena är lika med eller efter det aktuella datumet. Ledighetens varaktighet beräknas med funktionen `calcBusinessDays`.

Du kan granska det adaptiva formuläret och formulärdatamodellen på följande platser:

`https://[authorHost]:[authorPort]/editor.html/content/forms/af/we-finance/employee/self-service/leave-application.html`

`https://[authorHost]:[authorPort]/aem/fdm/editor.html/content/dam/formsanddocuments-fdm/db`

**Se det själv**

Gå till `https://[publishHost]:[publishPort]/content/we-finance/global/en/self-service-forms.html` och logga in med `srose/srose` som användarnamn/lösenord för Sarah. Klicka på **[!UICONTROL Employee]** för att öppna instrumentpanelen och klicka sedan på **[!UICONTROL Apply]** på Lämna program. Fyll i uppgifterna och skicka in ansökan.

### Gloria granskar och godkänner ledighetsansökan {#gloria-reviews-and-approves-the-leave-application}

Den ledighetsansökan som Sarah har lämnat in tilldelas Gloria Rios för granskning. Gloria loggar in på sin AEM Inbox och granskar de uppgifter hon tilldelats. Hon godkänner Sarah ansökan och slutför uppgiften.

![left-](assets/leave-inbox.png)
**inboxFigure:** *Glorias inkorg*

![lämna-](assets/leave-approved.png)
**godkändBild:** *Öppna uppgift*

**Så här fungerar det**

Arbetsflödet för att skicka iväg programmet utlöser ett Forms-arbetsflöde som skapar en uppgift i Glorias inkorg för godkännande. Granska Formens Workflow på `https://[authorHost]:[authorPort]/editor.html/conf/global/settings/workflow/models/we-finance/employee/self-service/we-finance-employee-leave-application.html`

![corporate-card-leave-application-workflow-model](assets/corporate-card-leave-application-workflow-model.png)

**Se det själv**

Gå till `https://[publishHost]:[publishPort]/content/we-finance/global/en/login.html?resource=/aem/inbox.html` och logga in med `grios/password` som användarnamn/lösenord för Gloria Rios. Öppna uppgiften som skapats för att lämna programmet och godkänn den.
