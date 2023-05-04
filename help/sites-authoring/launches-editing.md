---
title: Redigera Launches
seo-title: Editing Launches
description: När du har skapat en startsida för sidan (eller en uppsättning sidor) kan du redigera innehållet i startkopian av sidorna.
seo-description: After creating a launch for your page (or set of pages) you can edit the content in the launch copy of the page(s).
uuid: 851bcbbe-1dff-457f-a3bc-468ace9b4ac4
contentOwner: AEM Docs
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: a28539fc-c1dd-43bf-a47b-5f158c5611a7
legacypath: /content/docs/en/aem/6-0/author/site-page-features/launches
exl-id: 9f208b13-08eb-4305-b712-379e9b9b041e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '525'
ht-degree: 19%

---

# Redigera Launches{#editing-launches}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Redigera startsidor {#editing-launch-pages}

När en startsida har skapats för en sida (eller en uppsättning sidor) kan du redigera innehållet i startkopian av sidorna.

1. Öppna [Starta från referenser (platskonsolen)](/help/sites-authoring/launches.md#launches-in-references-sites-console) för att visa tillgängliga åtgärder.
1. Välj **Gå till sidan** för att öppna sidan för redigering.

### Redigera startsidor som är beroende av en Live-kopia {#editing-launch-pages-subject-to-a-live-copy}

Om din lansering baseras på en [live copy](/help/sites-administering/msm.md) då kommer du att:

* se låssymboler (små hänglås) när du redigerar en komponent (innehåll och/eller egenskaper).
* se **Live Copy** tabba in **Sidegenskaper**

En live-kopia används för att synkronisera innehåll *från* källgrenen *till* startgrenen (för att hålla startsidan uppdaterad med ändringarna i källan).

Du kan göra ändringar på samma sätt som du kan redigera en vanlig Live-kopia; till exempel:

* Om du klickar på ett stängt hänglås bryts synkroniseringen och du kan göra nya uppdateringar av innehållet när du startar programmet. När du har låst upp (öppet hänglås) skrivs inte ändringarna över av ändringar som gjorts på samma plats i källgrenen.
* **Gör uppehåll i** (och **återuppta**) arv för en viss sida.

Se [Ändra innehåll i Live Copy](/help/sites-administering/msm-livecopy.md#changing-live-copy-content) för ytterligare information.

## Jämföra en startsida med dess källsida {#comparing-a-launch-page-to-its-source-page}

Om du vill spåra de ändringar du har gjort kan du visa startsidan i **Referenser** och jämföra startsidan med dess källsida:

1. I **Webbplatser** konsol, [navigera till startsidan och markera den](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).
1. Öppna **[Referenser](/help/sites-authoring/basic-handling.md#references)** panel och markera **Startar**.
1. Välj en specifik start och sedan **Jämför med källa**:

   ![chlimage_1-96](assets/chlimage_1-96.png)

1. De två sidorna (start och källa) öppnas sida vid sida.

   Mer information om hur du använder funktionen finns i [Sidskillnader](/help/sites-authoring/page-diff.md).

## Ändra använda källsidor {#changing-the-source-pages-used}

Du kan när som helst lägga till eller ta bort sidor till/från intervallet med källsidor för en start:

1. Öppna och välj programstart från:

   * den [Startar konsolen](/help/sites-authoring/launches.md#the-launches-console):

      * Välj **Redigera**.
   * [Referenser (platskonsolen)](/help/sites-authoring/launches.md#launches-in-references-sites-console) för att visa tillgängliga åtgärder:

      * Välj **Redigera start**.

   Källsidorna visas.

1. Gör önskade ändringar och bekräfta sedan med **Spara**.

   >[!NOTE]
   >
   >Om du vill lägga till sidor i en programstart måste de ligga under en gemensam språkrot. dvs. inom en enda plats.

## Redigera en startkonfiguration {#editing-a-launch-configuration}

Du kan när som helst redigera egenskaperna för en start:

1. Öppna och välj programstart från:

   * den [Startar konsolen](/help/sites-authoring/launches.md#the-launches-console):

      * Välj **Egenskaper**.
   * [Referenser (platskonsolen)](/help/sites-authoring/launches.md#launches-in-references-sites-console) för att visa tillgängliga åtgärder:

      * Välj **Redigera egenskaper**.

   Detaljerna visas.

1. Gör önskade ändringar och bekräfta sedan med **Spara**.

   Avsnittet [Startsidor och händelseordning](/help/sites-authoring/launches.md#launches-the-order-of-events) innehåller information om syftet med och interaktionen mellan fälten **Startdatum** och **Produktionsklar**.

## Identifiera startstatus för en sida {#discovering-the-launch-status-of-a-page}

Statusen visas när du väljer en viss start på fliken Inställningar (se [Startar i referenser (platskonsolen)](/help/sites-authoring/launches.md#launches-in-references-sites-console)).

![chlimage_1-97](assets/chlimage_1-97.png)
