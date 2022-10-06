---
title: Utvecklarläge
seo-title: Developer Mode
description: I utvecklarläget öppnas en sidopanel med flera flikar som ger utvecklaren information om den aktuella sidan
seo-description: Developer mode opens a side panel with several tabs that provide a developer with infomation about the current page
uuid: 2ff0d85e-fe49-4506-b6d6-74cc060d7ea1
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: components
content-type: reference
discoiquuid: efbe46a3-c37f-4b67-8b3a-188cfc75118b
exl-id: 733eddf1-48f9-45c2-a1b4-138cf32b4b59
source-git-commit: 51358642a2fa8f59f3f5e3996b0c37269632c4cb
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 1%

---

# Utvecklarläge{#developer-mode}

När du redigerar sidor i AEM [lägen](/help/sites-authoring/author-environment-tools.md#page-modes) är tillgängliga, inklusive läget Utvecklare. Då öppnas en sidopanel med flera flikar som ger utvecklaren information om den aktuella sidan. De tre flikarna är:

* **[Komponenter](#components)** för att visa information om struktur och prestanda.
* **[Test](#tests)** för att köra tester och analysera resultaten.
* **[Fel](#errors)** för att se om det finns några problem.

Detta hjälper en utvecklare att:

* Upptäck: vilka sidor som är sammansatta av.
* Felsök: vad som händer var och när, vilket i sin tur hjälper till att lösa problem.
* Test: fungerar programmet som förväntat.

>[!CAUTION]
>
>Utvecklarläge:
>
>* Är bara tillgängligt i det beröringsaktiverade användargränssnittet (vid redigering av sidor).
>* Är inte tillgängligt på mobila enheter eller små fönster på skrivbordet (på grund av utrymmesbegränsningar).
   >   * Detta inträffar när bredden är mindre än 1024px.
>* Är endast tillgänglig för användare som är medlemmar i `administrators` grupp.


>[!CAUTION]
>
>Utvecklarläget är bara tillgängligt på en standardförfattarinstans som inte använder körläget nosampling content.
>
>Om det behövs kan det konfigureras för användning:
>
>* på en författarinstans med nosamplsinnehållets körningsläge
>* en publiceringsinstans
>
>Det bör inaktiveras igen efter användning.

>[!NOTE]
>
>Se
>
>* Kunskapsbasartikel, [Felsökning AEM TouchUI-problem](https://helpx.adobe.com/experience-manager/kb/troubleshooting-aem-touchui-issues.html)för fler tips och verktyg.
>* AEM Gems-session om [AEM 6.0 Developer Mode](https://experienceleague.adobe.com/docs/experience-manager-gems-events/gems/gems2014/aem-developer-mode.html).


## Öppnar utvecklarläge {#opening-developer-mode}

Utvecklarläget implementeras som en sidopanel i sidredigeraren. Om du vill öppna panelen väljer du **Utvecklare** från lägesväljaren i verktygsfältet i sidredigeraren:

![chlimage_1-229](assets/chlimage_1-229.png)

Panelen är uppdelad i två flikar:

* **[Komponenter](/help/sites-developing/developer-mode.md#components)** - Detta visar ett komponentträd, som liknar [innehållsträd](/help/sites-authoring/author-environment-tools.md#content-tree) för författare

* **[Fel](/help/sites-developing/developer-mode.md#errors)** - När problem uppstår visas information för varje komponent.

### Komponenter {#components}

![chlimage_1-230](assets/chlimage_1-230.png)

Detta visar ett komponentträd som:

* Visar kedjan med komponenter och mallar som återges på sidan (SLY, JSP osv.). Trädet kan expanderas för att visa kontext i hierarkin.
* Visar den datortid på serversidan som krävs för att återge komponenten.
* Gör att du kan expandera trädet och välja specifika komponenter i trädet. Markeringen ger åtkomst till komponentinformation. t.ex.

   * Databassökväg
   * Länkar till skript (används i CRXDE Lite)

* De valda komponenterna (i innehållsflödet, vilket anges med en blå ram) markeras i innehållsträdet (och tvärtom).

Detta kan hjälpa till att:

* Fastställ och jämför återgivningstiden per komponent.
* Se och förstå hierarkin.
* Förstå och förbättra sidinläsningstiden genom att hitta långsamma komponenter.

Varje komponentpost kan visa (till exempel:

![chlimage_1-231](assets/chlimage_1-231.png)

* **Visa detaljer**: en länk till en lista som visar

   * alla komponentskript som används för att återge komponenten.
   * databasens innehållssökväg för den här specifika komponenten.

   ![chlimage_1-232](assets/chlimage_1-232.png)

* **Redigera skript**: en länk som:

   * öppnar komponentskriptet i CRXDE Lite.

* När du expanderar en komponentpost (pilhuvud) kan du även visa:

   * Hierarkin i den markerade komponenten.
   * Återgivningstider för den markerade komponenten separat, alla enskilda kapslade komponenter i den och den kombinerade summan.

   ![chlimage_1-233](assets/chlimage_1-233.png)

>[!CAUTION]
>
>Vissa länkar pekar på skript under `/libs`. Dessa är dock bara till för referens **får inte** redigera vad som helst under `/libs`, eftersom alla ändringar du gör kan gå förlorade. Detta beror på att den här grenen kan ändras när du uppgraderar eller installerar en programfix/funktionspaket. Alla ändringar du behöver ska göras under `/apps`, se [Övertäckningar och åsidosättningar](/help/sites-developing/overlays.md).

### Fel {#errors}

![chlimage_1-234](assets/chlimage_1-234.png)

Förhoppningsvis **Fel** tabben kommer alltid att vara tom (som ovan), men när problem uppstår visas följande information för varje komponent:

* En varning om komponenten skriver en post i felloggen, tillsammans med information om felet och direktlänkar till rätt kod i CRXDE Lite.
* En varning om komponenten öppnar en administratörssession.

I en situation där en odefinierad metod anropas visas det resulterande felet i **Fel** tab:

![chlimage_1-235](assets/chlimage_1-235.png)

Komponentposten i trädet på fliken Komponenter markeras också med en indikator när ett fel inträffar.

### Test {#tests}

>[!CAUTION]
>
>I AEM 6.2 återimplementerades testfunktionerna i utvecklarläget som ett fristående verktygsprogram.
>
>Mer information finns i [Testa användargränssnittet](/help/sites-developing/hobbes.md).
