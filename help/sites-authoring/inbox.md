---
title: Din inkorg
seo-title: Your Inbox
description: Hantera dina uppgifter med inkorgen
seo-description: Managing your tasks with the inbox
uuid: ddd48019-ce69-4a47-be2b-5b66ae2fe3c8
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: 8b607b55-2412-469f-856b-0a3dea4b0efb
exl-id: 9037f21c-5392-4322-af0d-7e220c810954
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '924'
ht-degree: 9%

---

# Din inkorg{#your-inbox}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan få meddelanden från olika AEM, inklusive arbetsflöden och projekt. om:

* Uppgifter:

   * dessa kan också skapas vid olika punkter i AEM, t.ex. under **Projekt**,
   * kan vara produkten av ett arbetsflöde **Skapa uppgift** eller **Skapa projektuppgift** steg.

* Arbetsflöden:

   * Arbetsobjekt som representerar åtgärder som du måste utföra på sidinnehåll.

      * det här är produkten av arbetsflöde **Deltagare** steg
   * felobjekt, så att administratörer kan försöka utföra det misslyckade steget igen.


Du får dessa meddelanden i din egen Inkorg där du kan visa dem och vidta åtgärder.

>[!NOTE]
>
>AEM levereras förinläst med administrativa uppgifter som tilldelats administratörsanvändargruppen. Se [Administrativa arbetsmoment som inte går att köra](#out-of-the-box-administrative-tasks) för mer information.

>[!NOTE]
>
>Mer information om objekttyperna finns även i:
>
>* [Projekt](/help/sites-authoring/touch-ui-managing-projects.md)
>* [Projekt - arbeta med uppgifter](/help/sites-authoring/task-content.md)
>* [Arbetsflöden](/help/sites-authoring/workflows.md)
>* [Forms](/help/forms/home.md)
>


## Inkorgen i sidhuvudet {#inbox-in-the-header}

Från någon av konsolerna visas det aktuella antalet objekt i din inkorg i sidhuvudet. Indikatorn kan också öppnas för att ge snabb åtkomst till sidan/sidorna som kräver åtgärder eller åtkomst till inkorgen:

![wf-80](assets/wf-80.png)

>[!NOTE]
>
>Vissa åtgärder visas också i [kortvy över lämplig resurs](/help/sites-authoring/basic-handling.md#card-view).

## Administrativa arbetsmoment som inte går att köra  {#out-of-the-box-administrative-tasks}

Färdiga AEM levereras förinläst med fyra uppgifter tilldelade till administratörsanvändargruppen.

* [Konfigurera analys och målgruppsanpassning](/help/sites-administering/opt-in.md)
* [Använd AEM checklista](/help/sites-administering/security-checklist.md)
* Aktivera insamling av aggregerad användningsstatistik
* [Konfigurera HTTPS](/help/sites-administering/ssl-by-default.md)

## Öppna Inkorgen {#opening-the-inbox}

Så här öppnar du AEM inkorg:

1. Klicka/tryck på indikatorn i verktygsfältet.

1. Välj **Visa alla**. **AEM -inkorgen** öppnas. I inkorgen visas objekt från arbetsflöden, projekt och uppgifter.
1. Standardvyn är [Listvy](#inbox-list-view), men du kan även växla till [Kalendervy](#inbox-calendar-view). Detta görs med vyväljaren (verktygsfält, överst till höger).

   För båda vyerna kan du även definiera [Visa inställningar](#inbox-view-settings); vilka alternativ som är tillgängliga beror på den aktuella vyn.

   ![wf-79](assets/wf-79.png)

>[!NOTE]
>
>Inkorgen fungerar som en konsol, och du kan använda [Global navigering](/help/sites-authoring/basic-handling.md#global-navigation) eller [Sök](/help/sites-authoring/search.md) för att navigera till en annan plats när du är klar.

### Inkorg - listvy {#inbox-list-view}

I den här vyn visas alla objekt tillsammans med viktig relevant information:

![wf-82](assets/wf-82.png)

### Inkorg - kalendervy {#inbox-calendar-view}

I den här vyn visas objekt efter deras placering i kalendern och den exakta vyn som du har valt:

![wf-93](assets/wf-93.png)

Du kan:

* välja en specifik vy, **Tidslinje**, **Kolumn**, **Lista**

* ange vilka uppgifter som ska visas enligt **Schema**; **Alla**, **Planerad**, **Pågår**, **Förfaller snart**, **Förfallodatum**

* detaljgranska för mer detaljerad information om ett objekt
* markera ett datumintervall som vyn ska fokuseras i:

![wf-91](assets/wf-91.png)

### Inkorg - Visa inställningar {#inbox-view-settings}

För båda vyerna (List och Calendar) kan du definiera inställningar:

* **Kalendervy**

   För **Kalendervy** du kan konfigurera:

   * **Gruppera efter**
   * **Schema** eller **Ingen**
   * **Kortstorlek**

   ![wf-92](assets/wf-92.png)

* **Listvy**

   För **Listvy** du kan konfigurera sorteringsmekanismen:

   * **Sortera efter**
   * **Sorteringsordning**

   ![wf-83](assets/wf-83.png)

## Vidta åtgärder för ett objekt {#taking-action-on-an-item}

1. Om du vill utföra en åtgärd för ett objekt markerar du miniatyrbilden för det aktuella objektet. Ikoner för de åtgärder som är tillämpliga på det objektet visas i verktygsfältet:

   ![wf-84](assets/wf-84.png)

   Åtgärderna är lämpliga för objektet och omfattar:

   * **Slutförd** Åtgärd. till exempel en uppgift eller ett arbetsflödesobjekt.
   * **Tilldela igen**/**Delegera** ett objekt.
   * **Öppna** en post, Beroende på objekttypen kan den här åtgärden:

      * visa objektegenskaperna
      * öppna en lämplig kontrollpanel eller guide för ytterligare åtgärder
      * öppna relaterad dokumentation
   * **Stega bakåt** till ett föregående steg.
   * Visa nyttolasten för ett arbetsflöde.
   * Skapa ett projekt från objektet.

   >[!NOTE]
   >
   >Mer information finns i:
   >
   >* Arbetsflödesobjekt - [Delta i arbetsflöden](/help/sites-authoring/workflows-participating.md)


1. Beroende på vilket objekt som valts kommer en åtgärd att startas; till exempel:

   * en dialogruta som är lämplig för åtgärden öppnas.
   * en åtgärdsguide startas.
   * en dokumentationssida öppnas.

   Till exempel: **Tilldela igen** öppnar en dialogruta:

   ![wf-85](assets/wf-85.png)

   Beroende på om en dialogruta, guide, dokumentationssida har öppnats kan du:

   * Bekräfta lämpliga åtgärder. t.ex. Tilldela igen.
   * Avbryt åtgärden.
   * Bakpil: Om en åtgärdsguide eller dokumentationssida till exempel har öppnats kan du gå tillbaka till Inkorgen.


## Skapa en uppgift {#creating-a-task}

I inkorgen kan du skapa uppgifter:

1. Välj **Skapa** sedan **Uppgift**.
1. Fyll i de nödvändiga fälten i **Grundläggande** och **Avancerat** tabbar; endast **Titel** är obligatoriskt, alla andra är valfria:

   * **Grundläggande**:

      * **Titel**
      * **Projekt**
      * **Tilldelad**
      * **Innehåll**; liknar Nyttolast är detta en referens från aktiviteten till en plats i databasen
      * **Beskrivning**
      * **Aktivitetsprioritet**
      * **Startdatum**
      * **Förfallodatum**

   ![wf-86](assets/wf-86.png)

   * **Avancerat**

      * **Namn**: detta kommer att användas för att skapa URL:en, om det är tomt kommer det att baseras på **Titel**.

   ![wf-87](assets/wf-87.png)

1. Välj **Skicka**.

## Skapa ett projekt {#creating-a-project}

För vissa uppgifter kan du skapa en [Projekt](/help/sites-authoring/projects.md) baserat på den uppgiften:

1. Välj lämplig åtgärd genom att trycka/klicka på miniatyrbilden.

   >[!NOTE]
   >
   >Endast uppgifter som skapats med **Skapa** alternativ för **Inkorg** kan användas för att skapa ett projekt.
   >
   >Arbetsobjekt (från ett arbetsflöde) kan inte användas för att skapa ett projekt.

1. Välj **Skapa projekt** i verktygsfältet för att öppna guiden.
1. Välj lämplig mall och sedan **Nästa**.
1. Ange de nödvändiga egenskaperna:

   * **Grundläggande**

      * **Titel**
      * **Beskrivning**
      * **Startdatum**
      * **Förfallodatum**
      * **Användare** och roll
   * **Avancerat**

      * **Namn**
   >[!NOTE]
   >
   >Se [Skapa ett projekt](/help/sites-authoring/touch-ui-managing-projects.md#creating-a-project) för fullständig information.

1. Välj **Skapa** för att bekräfta åtgärden.

## Filtrera objekt i AEM {#filtering-items-in-the-aem-inbox}

Du kan filtrera objekten i listan:

1. Öppna **AEM**.

1. Öppna filterväljaren:

   ![wf-88](assets/wf-88.png)

1. Du kan filtrera de listade objekten enligt ett antal kriterier, varav många kan förfinas; till exempel:

   ![wf-89](assets/wf-89.png)

   >[!NOTE]
   >
   >Med [Visa inställningar](#inbox-view-settings) Du kan också konfigurera sorteringsordningen när du använder [Listvy](#inbox-list-view).
