---
title: Arbeta med sidversioner
seo-title: Working with Page Versions
description: Skapa, jämföra och återställa versioner av en sida
seo-description: Create, compare, and restore versions of a page
uuid: b0328431-c2cf-48f4-b358-261238338241
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: fa331c03-5587-452d-ab96-ac2926ae0da3
exl-id: 2df7c08f-db17-4666-ba39-e81cc2e656d7
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1111'
ht-degree: 6%

---

# Arbeta med sidversioner{#working-with-page-versions}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Versionshantering skapar en ögonblicksbild av en sida vid en viss tidpunkt. Med versionshantering kan du utföra följande åtgärder:

* Skapa en version av en sida.
* Återställ en sida till en tidigare version för att ångra en ändring som du har gjort på en sida, till exempel.
* Jämför den aktuella versionen av en sida med en tidigare version med skillnader i markerad text och bild.

## Skapa en ny version {#creating-a-new-version}

Du kan skapa en version av resursen från:

* den [Tidslinjespår](#creating-a-new-version-timeline)
* den [Skapa](#creating-a-new-version-create-with-a-selected-resource) alternativ (när en resurs har valts)

### Skapa en ny version - Tidslinje {#creating-a-new-version-timeline}

1. Navigera till sidan som du vill skapa en version för.
1. Markera sidan i [markeringsläge](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).
1. Öppna **Tidslinje** kolumn.
1. Klicka/tryck på pilen vid kommentarfältet för att visa alternativen:

   ![screen_shot_2018-03-21at155035](assets/screen_shot_2018-03-21at155035.png)

1. Välj **Spara som version**.
1. Ange **Etikett** och **Kommentar** vid behov.

   ![chlimage_1-398](assets/chlimage_1-398.png)

1. Bekräfta den nya versionen med **Skapa**.

   Informationen i tidslinjen uppdateras för att ange den nya versionen.

### Skapa en ny version - Skapa med en markerad resurs {#creating-a-new-version-create-with-a-selected-resource}

1. Navigera till sidan som du vill skapa en version för.
1. Markera sidan i [markeringsläge](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).
1. Välj **Skapa** i verktygsfältet.
1. Dialogrutan öppnas. Du kan ange en **Etikett** och **Kommentar** vid behov:

   ![screen_shot_2012-02-15at105050am](assets/screen_shot_2012-02-15at105050am.png)

1. Bekräfta den nya versionen med **Skapa**.

   Tidslinjen öppnas och informationen uppdateras för att ange den nya versionen.

## Återställa till en sidversion {#reverting-to-a-page-version}

När en version har skapats kan du vid behov återgå till den versionen.

>[!NOTE]
>
>När du återställer en sida blir den skapade versionen en del av en ny gren.
>
>Så här illustrerar du:
>
>* Skapa versioner av valfri sida.
>* De inledande etiketterna och versionsnodnamnen är 1.0, 1.1, 1.2 och så vidare.
>* Återställa den första versionen. dvs. 1.0.
>* Skapa nya versioner igen.
>* De genererade etiketterna och nodnamnen blir nu 1.0.0, 1.0.1, 1.0.2 osv.
>


Så här återgår du till en tidigare version:

1. Navigera till sidan som du vill återställa till en tidigare version.
1. Markera sidan i [markeringsläge](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).
1. Öppna kolumnen **Tidslinje** och välj antingen **Visa alla** eller **Versioner**. Sidversionerna för den valda sidan visas.
1. Välj den version som du vill återställa till. Möjliga alternativ visas:

   ![screen_shot_2018-03-21at155246](assets/screen_shot_2018-03-21at155246.png)

1. Välj **Återgå till den här versionen**. Den valda versionen återställs och informationen på tidslinjen uppdateras.

## Förhandsgranska en version {#previewing-a-version}

Du kan förhandsgranska en viss version:

1. Navigera till den sida som du vill jämföra.
1. Markera sidan i [markeringsläge](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).
1. Öppna kolumnen **Tidslinje** och välj antingen **Visa alla** eller **Versioner**.
1. Sidversionerna visas. Markera den version som du vill förhandsgranska:

   ![screen_shot_2018-03-21at155330](assets/screen_shot_2018-03-21at155330.png)

1. Välj **Förhandsgranska**. Sidan visas på en ny flik.

   >[!CAUTION]
   >
   >Om en sida har flyttats kan du inte längre förhandsgranska versioner som gjorts före flyttningen.
   >
   >Om du får problem med en förhandsgranskning bör du kontrollera [Tidslinje](/help/sites-authoring/basic-handling.md#timeline) för att se om sidan har flyttats.

## Jämföra en version med den aktuella sidan {#comparing-a-version-with-current-page}

Så här jämför du en tidigare version med den aktuella sidan:

1. Navigera till den sida som du vill jämföra.
1. Markera sidan i [markeringsläge](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources).
1. Öppna kolumnen **Tidslinje** och välj antingen **Visa alla** eller **Versioner**.
1. Sidversionerna visas. Välj den version du vill jämföra:

   ![screen_shot_2018-03-21at155330](assets/screen_shot_2018-03-21at155330.png)

1. Välj **Jämför med aktuell**. The [sidskillnader](/help/sites-authoring/page-diff.md) öppnar och visar skillnaderna.

## Timewarp {#timewarp}

Timewarp är en funktion som simulerar *publicerad* en sidas status vid en viss tidpunkt tidigare.

Syftet är att du ska kunna spåra den publicerade webbplatsen vid den valda tidpunkten. Sidversionerna används för att avgöra publiceringsmiljöns tillstånd.

Så här gör du:

* Systemet söker efter den sidversion som var aktiv vid den valda tidpunkten.
* Detta innebär att den visade versionen skapades/aktiverades *före* den tidpunkt som valts i Timewarp.
* När du navigerar till en sida som har tagits bort återges även den, så länge som de gamla versionerna av sidan fortfarande är tillgängliga i databasen.
* Om ingen publicerad version hittas återgår Timewarp till sidans aktuella status i redigeringsmiljön (detta för att förhindra ett fel/404-sida, vilket skulle förhindra bläddring).

### Använda Timewarp {#using-timewarp}

Timewarp är en [läge](/help/sites-authoring/author-environment-tools.md#page-modes) för sidredigeraren. Du startar det genom att helt enkelt växla det på samma sätt som andra lägen.

1. Starta redigeraren för sidan där du vill starta Timewarp och välj sedan **Timewarp** i lägesmarkeringen.

   ![screen_shot_2018-03-21at155416](assets/screen_shot_2018-03-21at155416.png)

1. Ange ett måldatum och en måltid i dialogrutan och klicka eller tryck på **Ange datum**. Om du inte väljer någon tid används den aktuella tiden som standard.

   ![screen_shot_2018-03-21at155513](assets/screen_shot_2018-03-21at155513.png)

1. Sidan visas baserat på det angivna datumet. Timewarp-läget indikeras via det blå statusfältet högst upp i fönstret. Använd länkarna i statusfältet för att välja ett nytt måldatum eller avsluta Timewarp-läget.

   ![screen_shot_2018-03-21at155544](assets/screen_shot_2018-03-21at155544.png)

### Begränsningar för tidsförvrängning

Med Timewarp kan du göra ett bra försök att återskapa en sida vid en viss tidpunkt. På grund av komplexiteten i den kontinuerliga redigeringen av innehåll i AEM är detta dock inte alltid möjligt. Dessa begränsningar bör beaktas när du använder Timewarp.

* **Timewarp fungerar baserat på publicerade sidor** - Timewarp fungerar bara helt om du tidigare har publicerat sidan. I annat fall visas den aktuella sidan i författarmiljön.
* **Timewarp använder sidversioner** - Om du navigerar till en sida som har tagits bort/tagits bort från databasen kommer den att återges korrekt om det fortfarande finns äldre versioner av sidan i databasen.
* **Borttagna versioner påverkar Timewarp** - Om versioner tas bort från databasen kan inte Timewarp visa rätt vy.
* **Timewarp är skrivskyddat** - Du kan inte redigera den gamla versionen av sidan. Det är bara tillgängligt för visning. Om du vill återställa den äldre versionen måste du göra det manuellt med hjälp av Återställ.
* **Timewarp baseras bara på sidinnehåll** - Om element (som kod, css, resurser/bilder osv.) för återgivning av webbplatsen har ändrats, skiljer sig vyn från den ursprungliga, eftersom objekten inte versionsindelas i databasen.

>[!CAUTION]
>
>Timewarp är ett verktyg som hjälper författare att förstå och skapa sitt innehåll. Den är inte avsedd som en revisionslogg eller för juridiska ändamål.
