---
title: Hantera formulärprogram och uppgifter i AEM Inbox
seo-title: Hantera formulärprogram och uppgifter i AEM Inbox
description: Med AEM Inbox kan du starta formulärcentrerade arbetsflöden genom att skicka program och hantera uppgifter.
seo-description: Med AEM Inbox kan du starta formulärcentrerade arbetsflöden genom att skicka program och hantera uppgifter.
uuid: 5173558a-542a-4130-8bb6-5ac555ecc507
contentOwner: vishgupt
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: publish
discoiquuid: c1515c58-7d9a-4a36-9390-f6d6b980b801
translation-type: tm+mt
source-git-commit: 4dbb6af1c0a76aabc003749d7fa76f8c6e41e726
workflow-type: tm+mt
source-wordcount: '923'
ht-degree: 0%

---


# Hantera formulärprogram och uppgifter i AEM Inbox {#manage-forms-applications-and-tasks-in-aem-inbox}

Ett av många sätt att starta eller utlösa ett formulärcentrerat arbetsflöde är genom program i AEM Inbox. Du måste skapa ett arbetsflödesprogram för att kunna göra ett formulärarbetsflöde tillgängligt som program i Inkorgen. Mer information om arbetsflödesprogram och andra sätt att starta formulärarbetsflöden finns i [Starta ett formulärorienterat arbetsflöde i OSGi](/help/forms/using/aem-forms-workflow.md#launch).

Dessutom konsoliderar AEM Inbox meddelanden och uppgifter från olika AEM-komponenter, inklusive formulärarbetsflöden. När ett formulärarbetsflöde som innehåller ett tilldelningssteg aktiveras, visas det associerade programmet som en uppgift i den tilldelades inkorg. Om den som tilldelats är en grupp visas uppgiften i Inkorgen för alla gruppmedlemmar tills en enskild person gör anspråk på eller delegerar uppgiften.

Användargränssnittet i Inkorgen innehåller lista- och kalendervyer för att visa uppgifter. Du kan också konfigurera visningsinställningarna. Du kan filtrera uppgifter baserat på olika parametrar. Mer information om visning och filter finns i [Inkorgen](/help/sites-authoring/inbox.md).

Sammanfattningsvis kan du i Inkorgen skapa ett nytt program och hantera tilldelade uppgifter.

>[!NOTE]
>
>Du måste vara medlem i gruppen med arbetsflödesanvändare för att kunna använda AEM Inbox.

## Skapa program {#create-application}

1. Gå till AEM Inbox på `https://[server]:[port]/aem/inbox`.
1. Tryck på i Inkorgen **[!UICONTROL Create > Application]**. Sidan Välj program visas.
1. Markera ett program och klicka på **[!UICONTROL Create]**. Det adaptiva formulär som är associerat med programmet öppnas. Fyll i formulären och tryck **[!UICONTROL Submit]**. Det startar det associerade arbetsflödet och skapar en uppgift i den tilldelades inkorg.

## Hantera uppgifter {#manage-tasks}

När ett formulärarbetsflöde utlöses och du är tilldelad eller en del av den tilldelade gruppen, visas en uppgift i Inkorgen. Du kan visa uppgiftsinformation och utföra tillgängliga åtgärder för uppgiften inifrån Inkorgen.

### Anspråk eller delegera uppgifter {#claim-or-delegate-tasks}

Uppgifter som tilldelas en grupp visas i Inkorgen för alla gruppmedlemmar. Alla gruppmedlemmar kan göra anspråk på den uppgiften eller delegera den till en annan gruppmedlem. Så här gör du:

1. Tryck för att markera aktivitetens miniatyrbild. Alternativ för att öppna eller delegera uppgiften visas högst upp.

   ![välj uppgift](assets/select-task.png)

1. Gör något av följande:

   * Tryck på **[!UICONTROL Delegate]** om du vill delegera uppgiften. Dialogrutan Delegera objekt öppnas. Välj en användare, lägg till en kommentar och tryck på **[!UICONTROL OK]**.
   ![delegera](assets/delegate.png)

   * Tryck för att göra anspråk på uppgiften **[!UICONTROL Open]**. Dialogrutan Tilldela till mig själv öppnas. Tryck **[!UICONTROL Proceed]** för att göra anspråk på uppgiften. Uppgiften visas med dig som tilldelad i din inkorg.
   ![krav](assets/claim.png)

### Visa information och utför åtgärder på uppgifter {#view-details-and-perform-actions-on-tasks}

När du öppnar en uppgift kan du visa uppgiftsinformation och utföra tillgängliga åtgärder. Vilka åtgärder som är tillgängliga för en uppgift definieras i steget Tilldela i det associerade formulärarbetsflödet.

1. Tryck för att markera aktivitetens miniatyrbild. Alternativ för att öppna eller delegera den valda uppgiften visas högst upp.
1. Tryck för **[!UICONTROL Open]** att visa aktivitetsinformation och vidta åtgärder. Den detaljerade uppgiftsvyn öppnas. I den här vyn kan du visa aktivitetsinformation och vidta åtgärder för uppgiften.

   >[!NOTE]
   >
   >Om en uppgift har tilldelats en grupp måste du göra anspråk på den för att den ska kunna öppnas i detaljerad vy.

![aktivitetsinformation](assets/task-details.png)

Den detaljerade uppgiftsvyn innehåller följande avsnitt:

* Uppgiftsinformation
* Formulär
* Information om arbetsflöde
* Verktygsfältet Åtgärder

#### Uppgiftsinformation {#task-details}

I avsnittet Uppgiftsinformation visas information om uppgiften. Vilken information som visas beror på konfigurationsinställningarna för steget [](/help/sites-developing/workflows-step-ref.md) Tilldela i arbetsflödet. I exemplet ovan visas beskrivning, status, startdatum och arbetsflöde som används för uppgiften. Det gör det även möjligt att bifoga en fil till uppgiften.

#### Form {#form}

Fliken Formulär i området för huvudinnehållet visar eventuella bifogade formulär och fältnivåbilagor.

#### Information om arbetsflöde {#workflow-details}

Fliken Arbetsflödesinformation överst visar förloppet för uppgiften genom olika steg i arbetsflödet. Här visas slutförda, aktuella och väntande faser för uppgiften. Stegen för ett arbetsflöde definieras i steget [](/help/sites-developing/workflows-step-ref.md) Tilldela uppgift i det associerade arbetsflödet.

Fliken visar också aktivitetshistorik för varje slutförd fas i arbetsflödet. Om du vill ha mer information om scenen trycker du **[!UICONTROL View Details]** på en färdig fas. Här visas kommentarer, formulär och uppgiftsbilagor, status, start- och slutdatum och så vidare om uppgiften.

![arbetsflödesinformation](assets/workflow-details.png)

#### Verktygsfältet Åtgärder {#actions-toolbar}

Verktygsfältet Åtgärder visar alla tillgängliga alternativ för uppgiften. Medan Spara, Återställ och Delegera är standardåtgärder konfigureras andra tillgängliga åtgärder i [tilldelningssteget](/help/sites-developing/workflows-step-ref.md). I exemplet ovan har Godkänn och Avvisa konfigurerats i arbetsflödet.

När du utför en åtgärd fortsätter den i arbetsflödet.

### Visa slutförda uppgifter {#view-completed-tasks}

AEM Inbox visar endast aktiva uppgifter. Slutförda uppgifter visas inte i listan. Du kan emellertid använda inkorgsfilter för att filtrera uppgifter baserat på flera parametrar, t.ex. uppgiftstyp, status, start- och slutdatum. Så här visar du slutförda uppgifter:

1. I AEM Inbox trycker du på ![växlingspanel1](assets/toggle-side-panel1.png) för att öppna filterväljaren.
1. Tryck på **[!UICONTROL Task Status]** dragspelspanelen och välj **[!UICONTROL Complete]**. Alla slutförda uppgifter visas.

   ![filter-1](assets/filter-1.png)

1. Tryck för att markera en uppgift och klicka på **[!UICONTROL Open]**.

Uppgiften öppnas och visar dokumentet eller det adaptiva formulär som är kopplat till uppgiften. För anpassningsbara formulär visas det skrivskyddade adaptiva formuläret eller dess PDF-dokument med poster som konfigurerats på fliken Formulär/Dokument i [arbetsflödessteget](/help/sites-developing/workflows-step-ref.md)Tilldela uppgift.

I avsnittet med aktivitetsinformation visas information om till exempel åtgärd, aktivitetsstatus, startdatum och slutdatum.

![slutförd uppgift](assets/completed-task.png)

På fliken **[!UICONTROL Workflow Details]** visas varje steg i arbetsflödet. Tryck **[!UICONTROL View details]** för att få detaljerad information.

![complete-task-workflow](assets/completed-task-workflow.png)

