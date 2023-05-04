---
title: Dokumentfragment
seo-title: Document Fragments
description: Med dokumentfragment som text, listor, villkor och layoutfragment i Correspondence Management kan du skapa statiska, dynamiska och repeterbara komponenter i kundens korrespondens.
seo-description: Document Fragments, such as Text, lists, conditions, and layout fragments, in Correspondence Management let you form the static, dynamic, and repeatable components of customer correspondence.
uuid: 053a17e5-69a5-463d-af4f-46a86534158f
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: correspondence-management
discoiquuid: 1f48548c-4222-454d-ad16-53da37170de2
feature: Correspondence Management
exl-id: 54159851-bae1-4efd-8c8f-3a855776ecc4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---

# Dokumentfragment {#document-fragments}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Dokumentfragment är återanvändbara delar/komponenter i en korrespondens som du kan använda för att skapa interaktiv kommunikation/brev. Dokumentfragmenten är av följande typer:

* **Text**: En textresurs är en del av innehållet som består av ett eller flera textstycken. Ett stycke kan vara statiskt eller dynamiskt.

   * [Texter i interaktiv kommunikation](/help/forms/using/texts-interactive-communications.md)

* **Villkor**: Med villkor kan du definiera vilket innehåll som ska inkluderas när korrespondensen skapas, baserat på angivna data. Villkoret beskrivs i termer av kontrollvariabler. En kontrollvariabel kan antingen vara ett dataordlisteelement eller en platshållare.

   * [Villkor i interaktiv kommunikation](/help/forms/using/conditions-interactive-communications.md)

* **Lista:** List är en grupp dokumentfragment, inklusive text, listor, villkor och bilder. Ordningen på listelementen kan vara fast eller redigerbar. När du skapar en bokstav kan du använda några eller alla listelement för att återanvända ett mönster med element.
* **Layoutfragment**: Ett layoutfragment är en layout som kan användas i en eller flera bokstäver. Ett layoutfragment används för att skapa repeterbara mönster, särskilt dynamiska tabeller. Layouten kan innehålla typiska formulärfält som &quot;Adress&quot; och &quot;Referensnummer&quot;. Den innehåller också tomma delformulär som anger målområden. Layouterna (XDP) skapas i Designer och överförs sedan till AEM Forms.
