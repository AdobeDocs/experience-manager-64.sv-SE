---
title: Snabbguide till framtagning av sidor
seo-title: Snabbguide till framtagning av sidor
description: En snabb guide på hög nivå till de viktigaste funktionerna vid framtagning av sidinnehåll
seo-description: En snabb guide på hög nivå till de viktigaste funktionerna vid framtagning av sidinnehåll
uuid: 35442d98-caf9-4cdb-8e68-4fc611e66290
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 163a4887-7c33-4305-8c48-882630f2caa1
translation-type: tm+mt
source-git-commit: a87e078e1a8f49dc899ce9b160d789cb254338e2
workflow-type: tm+mt
source-wordcount: '1555'
ht-degree: 4%

---


# Quick Guide to Authoring Pages{#quick-guide-to-authoring-pages}

Dessa procedurer är avsedda som en snabbguide (på hög nivå) till de viktigaste åtgärderna vid framtagning av sidinnehåll i AEM.

De ska:

* Är inte avsedda som omfattande täckning.
* Ange länkar till den detaljerade dokumentationen.

Mer information om redigering med AEM finns i:

* [Steg 1 för författare](/help/sites-authoring/first-steps.md)
* [Arbeta med författarmiljön](/help/sites-authoring/author-environment-tools.md)

## Några snabba tips {#a-few-quick-hints}

Innan du ger en översikt över specifika detaljer finns det en liten samling allmänna tips och tips som du bör tänka på, särskilt om du är van vid att skapa [klassiskt gränssnitt](/help/sites-classic-ui-authoring/classicui.md).

### Webbplatskonsol {#sites-console}

* **Skapa**

   * Den här knappen är tillgänglig i många konsoler - de alternativ som visas är sammanhangsberoende så att de kan variera beroende på scenario.

* Ändra ordning på sidor i en mapp

   * Detta kan du göra i [listvyn](/help/sites-authoring/basic-handling.md#list-view). Ändringarna används och visas i andra vyer.

* Ändra användargränssnittet

   * Detta kan göras från olika platser. Se [Välja användargränssnitt](/help/sites-authoring/select-ui.md).

### Sidredigering {#page-authoring}

* Navigera i länkar

   * ***Länkar är inte tillgängliga för navigering*** när du är i **redigeringsläge** . Om du vill navigera med länkar måste du [förhandsgranska sidan](/help/sites-authoring/editing-content.md#previewing-pages) med hjälp av:

      * [Förhandsgranskningsläge](/help/sites-authoring/editing-content.md#preview-mode)
      * [Visa som publicerad](/help/sites-authoring/editing-content.md#view-as-published)

* Arbetsflöden och versioner har inte längre startats/skapats från sidredigeraren. detta görs nu från [tidslinjen](/help/sites-authoring/basic-handling.md#timeline) (nås från konsolen).

>[!NOTE]
>
>Det finns ett antal kortkommandon som kan underlätta redigeringen.
>
>* [Kortkommandon vid sidredigering](/help/sites-authoring/page-authoring-keyboard-shortcuts.md)
>* [Kortkommandon för konsoler](/help/sites-authoring/keyboard-shortcuts.md)


## Hitta din sida {#finding-your-page}

1. Öppna konsolen **Platser** (med alternativet **Platser** i [Global navigering](/help/sites-authoring/basic-handling.md#global-navigation) - detta aktiveras (listruta) när du väljer länken Adobe Experience Manager (överst till vänster).

1. Navigera nedåt i trädet genom att trycka/klicka på lämplig sida. Hur sidresurserna visas beror på vilken vy du använder - [kort, lista eller kolumn](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources):

   ![screen_shot_2018-03-21at160214](assets/screen_shot_2018-03-21at160214.png)

1. Navigera uppåt i trädet med [den synliga sökvägen i sidhuvudet](/help/sites-authoring/basic-handling.md#the-header), som gör att du kan gå tillbaka till den valda platsen:

   ![chlimage_1-95](assets/chlimage_1-95.png)

### Skapa en ny sida {#creating-a-new-page}

1. [Navigera till den plats](#finding-your-page) där du vill skapa den nya sidan.
1. Använd ikonen **Skapa** och välj sedan **Sida** i listan:

   ![screen_shot_2018-03-21at160324](assets/screen_shot_2018-03-21at160324.png)

1. Då öppnas guiden som vägleder dig genom att samla in den information som behövs när du [skapar den nya sidan](/help/sites-authoring/managing-pages.md#creating-a-new-page). Följ instruktionerna på skärmen.

## Välja sida för ytterligare åtgärd {#selecting-your-page-for-further-action}

Du kan markera en sida så att du kan utföra en åtgärd på den. När du väljer en sida uppdateras verktygsfältet automatiskt så att de åtgärder som är relevanta för resursen visas.

Hur du väljer en sida beror på vilken vy du använder i konsolen:

1. Kortvy:

   * Ange markeringsläget genom [att välja önskad resurs](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources) med:

      * Mobil enhet: tryck och håll
      * Skrivbord: snabbåtgärden [](/help/sites-authoring/basic-handling.md#quick-actions) - kryssikon:

         ![screen_shot_2018-03-21at160503](assets/screen_shot_2018-03-21at160503.png)

      * Kortet kommer att förses med en bock som visar att sidan har valts.
   >[!NOTE]
   >
   >I markeringsläget ändras ikonen **Markera** (en bock) till ikonen **Avmarkera** (ett kryss).

1. Listvy:

   * Tryck/klicka på miniatyrbilden för resursen - miniatyrbilden kommer att överlappas med en bock för att visa att den har markerats.

1. Kolumnvy:

   * Tryck/klicka på miniatyrbilden för resursen - miniatyrbilden kommer att överlappas med en bock för att visa att den har markerats.

## Snabbåtgärder (endast kortvyn/skrivbordet) {#quick-actions-card-view-desktop-only}

1. [Navigera till sidan](#finding-your-page) som du vill vidta åtgärder på.
1. Håll muspekaren över kortet som representerar den resurs du behöver. snabbåtgärderna visas:

   ![screen_shot_2018-03-21at160503-1](assets/screen_shot_2018-03-21at160503-1.png)

## Redigera sidinnehåll {#editing-your-page-content}

1. [Navigera till sidan](#finding-your-page) som du vill redigera.
1. [Öppna sidan för redigering](/help/sites-authoring/managing-pages.md#opening-a-page-for-editing) med ikonen Redigera (penna):

   ![screen_shot_2018-03-21at160607](assets/screen_shot_2018-03-21at160607.png)

   Du kommer åt detta från antingen:

   * [Snabbåtgärder (endast kortvyn/skrivbordet)](#quick-actions-card-view-desktop-only) för lämplig resurs.
   * Verktygsfältet när [sidan har markerats](#selecting-your-page-for-further-action).

1. När redigeraren öppnas kan du:

   * [Lägg till en ny komponent på sidan](/help/sites-authoring/editing-content.md#inserting-a-component) genom att:

      * öppna sidopanelen
      * välja fliken Komponenter ( [komponentwebbläsaren](/help/sites-authoring/author-environment-tools.md#components-browser))
      * dra den nödvändiga komponenten till sidan.
      Sidpanelen kan öppnas (och stängas) med:

      ![](do-not-localize/screen_shot_2018-03-21at160738.png)

   * [Redigera innehållet i en befintlig komponent](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) på sidan:

      * Öppna komponentens verktygsfält genom att trycka eller klicka. Öppna dialogrutan med ikonen **Redigera** (penna).
      * Öppna komponentens direktredigerare genom att trycka och hålla ned eller dubbelklicka. De tillgängliga åtgärderna visas (för vissa komponenter är detta ett begränsat urval).
      * Om du vill visa alla tillgängliga åtgärder går du till helskärmsläge med:
      ![](do-not-localize/screen_shot_2018-03-21at160706.png)

   * [Konfigurera egenskaperna för en befintlig komponent](/help/sites-authoring/editing-content.md#component-edit-dialog)

      * Öppna komponentens verktygsfält genom att trycka eller klicka. Använd ikonen **Konfigurera** (skiftnyckel) för att öppna dialogrutan.
   * [Flytta en komponent](/help/sites-authoring/editing-content.md#moving-a-component) :

      * Dra den önskade komponenten till dess nya plats.
      * Öppna komponentens verktygsfält genom att trycka eller klicka. Använd ikonerna **Klipp** ut och **Klistra in** där det behövs.
   * [Kopiera (och klistra in)](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) en komponent:

      * Öppna komponentens verktygsfält genom att trycka eller klicka. Använd ikonerna **Kopiera** och sedan **Klistra in** efter behov.
      >[!NOTE]
      >
      >Du kan **klistra in** komponenter på samma sida eller på en annan sida. Om du klistrar in på en annan sida som redan var öppen före klipp ut/kopiera-åtgärden, måste sidan uppdateras.

   * [Ta bort](/help/sites-authoring/editing-content.md#edit-configure-copy-cut-delete-paste) en komponent:

      * Öppna komponentens verktygsfält med tryck eller klicka och använd sedan ikonen **Ta bort** .
   * [Lägg till anteckningar](/help/sites-authoring/annotations.md#annotations) på sidan:

      * Välj **anteckningsläget** (pratbubblarikonen). Lägg till anteckningar med ikonen **Lägg till anteckning** (plus). Avsluta anteckningsläget med X överst till höger.
      ![](do-not-localize/screen_shot_2018-03-21at160813.png)

   * [Förhandsgranska en sida](/help/sites-authoring/editing-content.md#preview-mode) (för att se hur den kommer att se ut i publiceringsmiljön)

      * Välj **Förhandsgranska** i verktygsfältet.
   * Återgå till redigeringsläget (eller välj ett annat läge) med **listrutan Redigera** .
   >[!NOTE]
   >
   >Om du vill navigera med hjälp av länkar i innehållet måste du använda [förhandsgranskningsläget](/help/sites-authoring/editing-content.md#preview-mode).

## Redigera sidegenskaperna {#editing-the-page-properties}

Det finns två (huvudsakliga) metoder för [redigering av sidegenskaper](/help/sites-authoring/editing-page-properties.md):

* Från **webbplatskonsolen** :

   1. [Navigera till sidan](#finding-your-page) som du vill publicera.
   1. Välj ikonen **Egenskaper** på något av följande sätt:

      * [Snabbåtgärder (endast kortvyn/skrivbordet)](#quick-actions-card-view-desktop-only) för lämplig resurs.
      * Verktygsfältet när [sidan har markerats](#selecting-your-page-for-further-action).
   ![screen_shot_2018-03-21at160850](assets/screen_shot_2018-03-21at160850.png)

* Sidegenskaperna visas. Du kan göra nödvändiga uppdateringar och sedan använda Spara för att behålla dessa

   * När du [redigerar sidan](#editing-your-page-content):

      1. Öppna menyn **Sidinformation** .
      1. Select **Open Properties** to open the dialog for editing the properties.

         ![screen_shot_2018-03-21at160920](assets/screen_shot_2018-03-21at160920.png)

## Publicera din sida (eller avpublicera) {#publishing-your-page-or-unpublishing}

Det finns två huvudmetoder för att [publicera sidan](/help/sites-authoring/publishing-pages.md) (och även för att avpublicera):

* Från **webbplatskonsolen** :

   1. [Navigera till sidan](#finding-your-page) som du vill publicera.
   1. Välj ikonen **Snabbpublicering** på något av följande sätt:

      * [Snabbåtgärder (endast kortvyn/skrivbordet)](#quick-actions-card-view-desktop-only) för lämplig resurs.
      * Verktygsfältet när [sidan har valts](#selecting-your-page-for-further-action) (ger även åtkomst till [Publicera senare](/help/sites-authoring/publishing-pages.md#manage-publication)).
   ![screen_shot_2018-03-21at160957](assets/screen_shot_2018-03-21at160957.png)

* När du [redigerar sidan](#editing-your-page-content):

   1. Öppna menyn **Sidinformation** .
   1. Välj **Publicera sida**.
   ![screen_shot_2018-03-21at161026](assets/screen_shot_2018-03-21at161026.png)

* Du kan bara avpublicera en sida från konsolen via alternativet **Hantera publikation**, som bara är tillgängligt i verktygsfältet (inte via snabbåtgärderna).

   Alternativet **Avpublicera sida** är fortfarande tillgängligt via menyn **Sidinformation** i redigeraren.

   ![screen_shot_2018-03-21at161059](assets/screen_shot_2018-03-21at161059.png)

   Mer information finns i [Publicera sidor](/help/sites-authoring/publishing-pages.md#unpublishing-pages) .

## Flytta, kopiera och klistra in eller ta bort sidan {#move-copy-and-paste-or-delete-your-page}

1. [Navigera till sidan](#finding-your-page) som du vill flytta, kopiera och klistra in eller ta bort.
1. Välj ikonen för kopiera (och sedan klistra in), flytta eller ta bort efter behov på något av följande sätt:

   * [Snabbåtgärder (endast kortvyn/skrivbordet)](#quick-actions-card-view-desktop-only) för den begärda resursen.
   * Verktygsfältet när [sidan har markerats](#selecting-your-page-for-further-action).

   * Kopiera:

      * Du måste sedan navigera till den nya platsen och klistra in.
   * Flytta:

      * Guiden öppnas och samlar in den information som behövs för att flytta sidan. Följ instruktionerna på skärmen.
   * Ta bort:

      * Du ombeds bekräfta åtgärden.
   >[!NOTE]
   >
   >Borttagning är inte tillgängligt som snabbåtgärd.

## Låser sidan (låser upp) {#locking-your-page-then-unlocking}

[När du låser en sida](/help/sites-authoring/editing-content.md#locking-a-page) kan andra författare inte arbeta med den. Ikonen/knappen Lås (och Lås upp) finns:

* Verktygsfältet när [sidan har markerats](#selecting-your-page-for-further-action).
* Listrutan [Sidinformation](#editing-the-page-properties) när du redigerar en sida.
* Sidans verktygsfält när du redigerar en sida (när sidan är låst)

Låsikonen ser till exempel ut så här:

![screen_shot_2018-03-21at161124](assets/screen_shot_2018-03-21at161124.png)

## Åtkomst till sidreferenser {#accessing-page-references}

[Snabb åtkomst till referenser](/help/sites-authoring/author-environment-tools.md#references) till/från en sida finns i Reference Rail.

1. Välj **Referenser** med verktygsfältsikonen (antingen före eller efter [att du har valt sidan](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161210](assets/screen_shot_2018-03-21at161210.png)

   En lista över referenstyper visas:

   ![screen_shot_2018-03-21at161315](assets/screen_shot_2018-03-21at161315.png)

1. Tryck/klicka på den typ av referens som krävs för att visa mer information och (när det är lämpligt) vidta ytterligare åtgärder.

## Skapa en version av din sida {#creating-a-version-of-your-page}

1. Om du vill öppna tidslinjen väljer du **[Tidslinje](/help/sites-authoring/basic-handling.md#timeline)**med verktygsfältsikonen (antingen före eller efter[att du har valt sidan](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161355](assets/screen_shot_2018-03-21at161355.png)

1. Tryck/klicka på uppilen längst ned till höger i kolumnen Tidslinje för att visa extra knappar, inklusive **Spara som version**.

   ![screen_shot_2018-03-21at161507](assets/screen_shot_2018-03-21at161507.png)

1. Välj **Spara som version** och sedan **Skapa**.

## Återställa/jämföra en version av sidan {#restoring-comparing-a-version-of-your-page}

Samma grundläggande funktion används när du återställer och/eller jämför versioner av sidan:

1. Välj **[Tidslinje](/help/sites-authoring/basic-handling.md#timeline)**med verktygsfältsikonen (antingen före eller efter[sidmarkering](#selecting-your-page-for-further-action)):

   ![screen_shot_2018-03-21at161355-1](assets/screen_shot_2018-03-21at161355-1.png)

   Om en version av sidan redan har sparats visas den i tidslinjen.

1. Tryck/klicka på den version som du vill återställa - då visas ytterligare åtgärdsknappar:

   * **Återgå till den här versionen**

      * Versionen återställs.
   * **Visa skillnader**

      * Sidan öppnas med skillnader (mellan de två versionerna) markerade.


