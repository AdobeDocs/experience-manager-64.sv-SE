---
title: Begär analysskript
seo-title: Request Analysis Script
description: Analysskriptet för begäran görs för att underlätta analysen av access.log-filerna som skapar en läsbar rapport för senare bearbetning
seo-description: The request analysis script is made to ease the analysis of the access.log files producing a readable report for later processing
uuid: 24eff3c6-5748-46f3-a30c-4a3a6427ce1d
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: testing
content-type: reference
discoiquuid: 1b5e0ccf-4157-45e3-8caf-1d6739d7d9d2
exl-id: 8582bbca-c11a-4880-88ba-da22e0301dba
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 0%

---

# Begär analysskript{#request-analysis-script}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Hämta {#download}

Skriptet är gjort för att underlätta analysen av `access.log` filer som skapar en läsbar rapport för senare bearbetning.

[Hämta fil](assets/analyse-access.sh)

## Beskrivning {#description}

Skriptet är gjort för att underlätta analysen av `access.log` filer som skapar en läsbar rapport för senare bearbetning.

Det genererar det totala antalet förfrågningar, GET kontra POST, Begär distribution över tid med mera.

Utdata är i Markdown-syntax och därför blir det enklare att konvertera det till PDF med verktyg som pandoc eller att visa det i en webbläsare med plugin-program som Markdown Viewer.

Den kan analysera en anpassad sökväg som finns på kommandoraden.

Utgå från kommentaren i filen som talar om hur den ska köras:

Analysera CQ `access.log` extrapolera olika uppgifter och producera ett markeringsresultat på `stdout`.

## Användning {#usage}

`./analyse-access.sh access.log.2013-&ast;`

du kan ange ytterligare anpassade sökvägar att analysera på kommandoraden

`/analyse-access.sh access.log.2013-&ast; /my/custom/path/1 /my/custom/path/2`

du kan spara utdata med en enkel rörledning

`./analyse-access.sh access.log.2013-&ast; | tee yr2013.md`
