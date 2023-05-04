---
title: Sidskillnader
seo-title: Page Diff
description: Med funktionen för sidskillnader kan du enkelt jämföra två sidor sida vid sida med skillnaderna markerade.
seo-description: The page diff feature allows for the convenient side-by-side comparison of two pages with their differences highlighted.
uuid: cf029ed8-606e-4f12-ac8e-5ea9ebd70b1b
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: 5a771d8c-cc56-4979-aeab-b508755a2078
exl-id: 1b1fa592-a145-4abe-a455-df24d551b937
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 1%

---

# Sidskillnader{#page-diff}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

Att skapa innehåll är en repetitiv process. Effektiv redigering kräver att man kan se vad som har ändrats från en iteration till en annan. Om du visar den ena sidversionen och den andra är ineffektiv och felbenägen kan uppstå. En författare vill enkelt kunna jämföra den aktuella sidan sida vid sida med en annan version.

Med funktionen för sidskillnader kan du enkelt jämföra två sidor sida vid sida med skillnaderna markerade.

>[!CAUTION]
>
>Om du kör en version före AEM 6.4.3 måste användaren ha **Ändra/skapa/ta bort** behörighet på noden `/content/versionhistory` för att använda funktionen.
>
>Se [Developing and Page Diff](/help/sites-developing/pagediff.md#operation-details) om du vill ha mer teknisk information om den här funktionen.

## Använd {#use}

Diff:en sida vid sida kan jämföra:

* [Versioner](/help/sites-authoring/working-with-page-versions.md#comparing-a-version-with-current-page) - Tidigare version av en sida med det aktuella läget
* [Live-kopior](/help/sites-administering/msm-livecopy.md#comparing-a-live-copy-page-with-a-blueprint-page) - Live Copy med utkast
* [Startar](/help/sites-authoring/launches-editing.md#comparing-a-launch-page-to-its-source-page) - Starta med källan
* [Språkkopior](/help/sites-administering/tc-manage.md#comparing-language-copies) - En sida före och efter (re-)översättning

Läs respektive avsnitt om hur du påbörjar skillnaderna i dessa sammanhang.

### Presentation av skillnader {#presentation-of-differences}

Oberoende av vilket innehåll som jämförs, förblir presentationen av skillnaderna densamma.

* Det innehåll som valdes när du startade differensen visas till vänster (diff-startpunkten).
* Jämförelseinnehållet visas till höger (vad det markerade innehållet jämförs med).

Om du till exempel jämför versioner visas den aktuella versionen till vänster och den föregående versionen till höger.

Källan för båda sidorna visas tydligt i sidhuvudsfältet högst upp i webbläsarfönstret.

![chlimage_1-355](assets/chlimage_1-355.png)

Skillnaden identifierar ändringar på komponentnivå och HTML. Objekt som har ändrats markeras med olika färger.

**Komponentändringar**

* Ljusgrön - komponent tillagd
* Rosa - komponent borttagen
* Blå - komponenten ändrad
* Blå - komponenten har flyttats

Observera att färgerna Ändrad och Flyttad är desamma.

**Ändringar i HTML**

* Mörkgrön - tillagd HTML
* Röd - HTML har tagits bort

>[!NOTE]
>
>När du jämför språkkopior inaktiveras markering, eftersom i en översättning ändras allt och markering inte har någon fördel.

### Helskärm och avslutande {#fullscreen-and-exiting}

Om du vill fokusera på ett visst innehåll kan du klicka på helskärmsikonen för endera&quot;sidan&quot; av diff:n för att förstora den till hela webbläsarfönstret.

![](do-not-localize/chlimage_1-24.png)

Den markerade sidan fyller hela fönstret, men fältet förblir överst så att du kan växla mellan de två sidorna.

![chlimage_1-356](assets/chlimage_1-356.png)

Du kan också stänga helskärmsläget genom att klicka på ikonen för att avsluta helskärmsläget.

![](do-not-localize/chlimage_1-25.png)

Du kan när som helst stänga diff sida vid sida genom att klicka på stängningsknappen i sidhuvudet.

## Begränsningar {#limitations}

I vissa situationer kan det hända att sidskillnader inte identifierar någon skillnad som förväntat.

* När olika versioner och starter används inte dynamiska komponenter som vägbeskrivningar, menyer, produktlistor eller logotyper (komponenter som är beroende av webbplatsstrukturen för att återge sitt innehåll).
* För versioner återskapar inte diff åtkomstkontrollprincipen och Live copy-relationen.
* Om du ändrar något i en bild, t.ex. attributen alt, title eller src, markeras den i blått som ändrad. I vissa fall har bilden emellertid en Base64-representation av src-attributet och även om båda bilderna ser likadana ut markeras de med diff som olika på grund av de olika src-attributen.
* Skillnaden kan inte identifiera bildrotation.
* Om en sida flyttas kan du inte längre göra några skillnader med versioner som gjorts före flyttningen.

   * Om du får problem med en skillnad ska du kontrollera [Tidslinje](/help/sites-authoring/basic-handling.md#timeline) för att se om sidan har flyttats.

>[!NOTE]
>
>Versioner kan inte jämföras med varandra. Endast den aktuella versionen kan jämföras med andra versioner av sidan. Den aktuella versionen är alltid den version som markeras med ändringar.

>[!NOTE]
>
>Mer information om hur sidskillnader fungerar samt om begränsningar som kan påverka sidskillnader finns i [dokumentation för utvecklare](/help/sites-developing/pagediff.md) av den här funktionen.
