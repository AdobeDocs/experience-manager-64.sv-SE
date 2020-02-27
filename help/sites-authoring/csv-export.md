---
title: Exportera till CSV
seo-title: Exportera till CSV
description: Exportera information om sidorna till en CSV-fil på det lokala systemet
seo-description: Exportera information om sidorna till en CSV-fil på det lokala systemet
uuid: aa03adac-bbfb-4566-a153-25fe6f6843dd
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: d4473758-674a-42d6-923a-b536f7f9c1f7
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Exportera till CSV{#export-to-csv}

**Med Skapa CSV-export** kan du exportera information om dina sidor till en CSV-fil på ditt lokala system.

* Den hämtade filen kallas `export.csv`
* Innehållet beror på de egenskaper du väljer.
* Du kan definiera banan tillsammans med exportens djup.

>[!NOTE]
>
>Hämtningsfunktionen och standarddestinationen för webbläsaren används.

Med guiden Skapa CSV-export kan du välja:

* Egenskaper att exportera

   * Metadata

      * Ändrad
      * Publicerad
   * Analyser

      * Sidvyer
      * Unika besökare
      * Tid på sidan


* Djup

   * Överordnad sökväg
   * Endast direktunderordnade
   * Ytterligare nivåer av barn
   * Nivåer

Den resulterande `export.csv` filen kan öppnas i Excel eller något annat kompatibelt program.

![chlimage_1-58](assets/chlimage_1-58.png)

Alternativet Skapa **CSV-export** är tillgängligt när du bläddrar i **webbplatskonsolen** (i listvyn): det är ett alternativ i listrutan **Skapa** :

![screen_shot_2018-03-21at154719](assets/screen_shot_2018-03-21at154719.png)

Så här skapar du en CSV-export:

1. Öppna konsolen **Platser** och navigera till önskad plats om det behövs.
1. I verktygsfältet väljer du **Skapa** och sedan **CSV-export** för att öppna guiden:

   ![screen_shot_2018-03-21at154758](assets/screen_shot_2018-03-21at154758.png)

1. Välj de egenskaper som ska exporteras.
1. Välj **Skapa**.

