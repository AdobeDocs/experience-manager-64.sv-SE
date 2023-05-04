---
title: Provar Responsiv layout i We.Retail
seo-title: Trying out Responsive Layout in We.Retail
description: Provar Responsiv layout i We.Retail
seo-description: null
uuid: d9613655-f54e-458f-9175-d07bb868f58b
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: best-practices
discoiquuid: 2d374e88-ea09-43d5-986c-5d77b0705b93
exl-id: ccb792f7-e837-4790-818f-e2c446328e71
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '283'
ht-degree: 1%

---

# Provar Responsiv layout i We.Retail{#trying-out-responsive-layout-in-we-retail}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Alla webbsidor använder komponenten Layoutbehållare för att implementera responsiv design. Layoutbehållaren har ett styckesystem som gör att du kan placera komponenter i ett responsivt rutnät. Rutnätet kan ändra layouten beroende på enhetens/fönstrets storlek och format. Komponenten används tillsammans med **Layout** i sidredigeraren, där du kan skapa och redigera din responsiva layout beroende på enhet.

## Prova {#trying-it-out}

1. Redigera sidan Arktisk surfning i sektionen Erfarenheter i den överordnad språkgrenen.

   http://localhost:4502/editor.html/content/we-retail/language-masters/en/experience/arctic-surfing-in-lofoten.html

1. Växla till **Förhandsgranska** för att se sidan som den skulle återges för en besökare på webbplatsen. Bläddra nedåt till artikelns innehåll *Aloha-sprit i Norge*.

   ![chlimage_1-178](assets/chlimage_1-178.png)

1. Ändra storlek på webbläsarfönstret och se hur layouten anpassas dynamiskt efter storleksändringen.

   ![chlimage_1-179](assets/chlimage_1-179.png)

1. Växla till layoutläge. Emulatorverktygsfältet visas automatiskt så att du kan planera layouten per målenhet.

   Om du markerar en komponent visas flytande och dolda alternativ på redigeringsmenyn tillsammans med storlekshandtag för komponenten.

   ![chlimage_1-180](assets/chlimage_1-180.png)

1. När du tar och drar i storlekshandtaget för komponenten visas automatiskt layoutstödrastret så att du lättare kan ändra storlek.

   ![chlimage_1-181](assets/chlimage_1-181.png)

## Ytterligare information {#further-information}

Mer information finns i redigeringsdokumentet [Responsiv layout](/help/sites-authoring/responsive-layout.md) eller administratörsdokumentet [Konfigurera layoutbehållare och layoutläge](/help/sites-administering/configuring-responsive-layout.md) för fullständig teknisk information.
