---
title: Exportera till CSV
seo-title: Export to CSV
description: Exportera information om sidorna till en CSV-fil på det lokala systemet
seo-description: Export information about your pages to a CSV file on your local system
uuid: aa03adac-bbfb-4566-a153-25fe6f6843dd
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: d4473758-674a-42d6-923a-b536f7f9c1f7
exl-id: 52eb9c2f-ce29-4622-8726-802ac40246d4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 12%

---

# Exportera till CSV{#export-to-csv}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

**Skapa CSV-export** Med kan du exportera information om sidorna till en CSV-fil på det lokala systemet.

* Den hämtade filen kallas `export.csv`
* Innehållet beror på de egenskaper du väljer.
* Du kan definiera banan tillsammans med exportens djup.

>[!NOTE]
>
>Hämtningsfunktionen och standarddestinationen för webbläsaren används.

I guiden Skapa CSV-export kan du välja:

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

Resultatet `export.csv` kan öppnas i Excel eller något annat kompatibelt program.

![chlimage_1-58](assets/chlimage_1-58.png)

Skapa **CSV-export** är tillgängligt när du bläddrar bland **Webbplatser** konsol (i listvyn): det är ett alternativ i **Skapa** nedrullningsbar meny:

![screen_shot_2018-03-21at154719](assets/screen_shot_2018-03-21at154719.png)

Så här skapar du en CSV-export:

1. Öppna konsolen **Sites** och navigera till önskad plats om det behövs.
1. Välj **Skapa** sedan **CSV-export** för att öppna guiden:

   ![screen_shot_2018-03-21at154758](assets/screen_shot_2018-03-21at154758.png)

1. Välj de egenskaper som ska exporteras.
1. Välj **Skapa**.
