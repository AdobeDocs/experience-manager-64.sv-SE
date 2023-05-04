---
title: AEM Brackets Extension
seo-title: AEM Brackets Extension
description: AEM Brackets Extension
seo-description: null
uuid: 2f0dfa42-eb34-44ae-90eb-b5f321c03b79
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: development-tools
content-type: reference
discoiquuid: 8231a30a-dcb7-4156-bb45-c5a23e5b56ef
exl-id: 5924d38b-243e-4a81-85b6-9ff89ae4c811
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '960'
ht-degree: 0%

---

# AEM Brackets Extension{#aem-brackets-extension}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Tillägget AEM Brackets ger ett smidigt arbetsflöde för att redigera AEM komponenter och klientbibliotek och utnyttjar kraften i [Hakparenteser](https://brackets.io/) kodredigeraren som ger åtkomst från kodredigeraren till Photoshop-filer och -lager. Den enkla synkronisering som tillägget ger (ingen Maven eller filvalv krävs) ökar utvecklarens effektivitet och hjälper även gränssnittsutvecklare med begränsade AEM att delta i projekt. Det här tillägget har även stöd för [HTML-mallspråk (HTL)](https://helpx.adobe.com/experience-manager/htl/user-guide.html), vilket minskar komplexiteten i JSP och gör komponentutvecklingen enklare och säkrare.

![chlimage_1-53](assets/chlimage_1-53.png)

### Funktioner {#features}

De viktigaste funktionerna i AEM Brackets Extension är:

* Automatisk synkronisering av ändrade filer till AEM.
* Manuell dubbelriktad synkronisering av filer och mappar.
* Fullständig innehållspaketsynkronisering av projektet.
* HTML-kodkomplettering för uttryck och `data-sly-*` blockprogramsatser.

Brackets innehåller dessutom många användbara funktioner för AEM teckensnittsutvecklare:

* Photoshop filstöd för att extrahera information från en PSD-fil, som lager, mått, färger, teckensnitt, texter m.m.
* Kodtips från PSD för att enkelt återanvända den extraherade informationen i koden.
* Stöd för CSS-preprocessorer, som LESS och SCSS.
* Och hundratals tillägg som täcker mer specifika behov.

## Installation {#installation}

### Hakparenteser {#brackets}

AEM Brackets Extension stöder Brackets version 1.0 eller senare.

Hämta den senaste Brackets-versionen från [hakparenteser.io](https://brackets.io/).

### Tillägget {#the-extension}

Så här installerar du tillägget:

1. Öppna hakparenteser. På menyn **Fil**, markera **Extension Manager...**
1. Retur **AEM** i sökfältet och leta efter **AEM Brackets Extension**.

   ![chlimage_1-54](assets/chlimage_1-54.png)

1. Klicka **Installera**.
1. Stäng dialogrutan och Extension Manager när installationen är klar.

## Komma igång {#getting-started}

### Innehållspaketprojektet {#the-content-package-project}

När tillägget har installerats kan du börja utveckla AEM komponenter genom att öppna en innehållspaketmapp från filsystemet med hakparenteser.

Projektet måste innehålla minst följande:

1. a `jcr_root` mapp (t.ex. `myproject/jcr_root`)

1. a `filter.xml` fil (t.ex. `myproject/META-INF/vault/filter.xml`). för mer information om strukturen i `filter.xml` se filen [Filterdefinition för arbetsyta](https://jackrabbit.apache.org/filevault/filter.html).

I hakparenteser **Fil** meny, välja **Öppna mapp...** och välj `jcr_root` eller den överordnade projektmappen.

>[!NOTE]
>
>Om du inte har ett eget projekt med ett innehållspaket kan du testa [HTL TodoMVC-exempel](https://github.com/Adobe-Marketing-Cloud/aem-sightly-sample-todomvc). På GitHub klickar du på **Ladda ned ZIP**, extrahera filerna lokalt och enligt instruktionerna ovan öppnar du `jcr_root` i Brackets. Följ sedan stegen nedan för att konfigurera **Projektinställningar** och slutligen överföra hela paketet till din AEM genom att göra en **Exportera innehållspaket** enligt instruktionerna längre ned i avsnittet Fullständig synkronisering av innehållspaket.
>
>Efter dessa steg bör du kunna komma åt `/content/todo.html` URL-adressen till din AEM-utvecklingsinstans och du kan börja göra ändringar i koden i hakparenteser och se hur ändringarna synkroniserades direkt till AEM-servern när du har gjort en uppdatering i webbläsaren.

### Projektinställningar {#project-settings}

Om du vill synkronisera ditt innehåll till och från en AEM utvecklingsinstans måste du definiera dina projektinställningar. Detta kan du göra genom att gå till **AEM** meny och välja **Projektinställningar...**

![chlimage_1-55](assets/chlimage_1-55.png)

Med projektinställningarna kan du definiera:

1. Server-URL (t.ex. `http://localhost:4502`)
1. Om servrar som inte har ett giltigt HTTPS-certifikat ska tolereras (håll inte markerat om det inte krävs)
1. Användarnamnet som används för att synkronisera innehåll (t.ex. `admin`)
1. Användarens lösenord (t.ex. `admin`)

## Synkroniserar innehåll {#synchronizing-content}

Tillägget AEM Brackets ger följande typer av innehållssynkronisering för filer och mappar som tillåts av filtreringsreglerna som definieras i `filter.xml`:

### Automatisk synkronisering av ändrade filer {#automated-synchronization-of-changed-files}

Detta synkroniserar endast ändringar från hakparenteser till AEM, men inte tvärtom.

### Manuell dubbelriktad synkronisering {#manual-bidirectional-synchronization}

Öppna snabbmenyn i projektutforskaren genom att högerklicka på en fil eller mapp och på **Exportera till server** eller **Importera från server** finns.

![chlimage_1-56](assets/chlimage_1-56.png)

>[!NOTE]
>
>Om den markerade posten ligger utanför `jcr_root` mapp, **Exportera till server** och **Importera från server** sammanhangsbaserade menyposter är inaktiverade.

### Fullständig synkronisering av innehållspaket {#full-content-package-synchronization}

I **AEM** -menyn, **Exportera innehållspaket** eller **Importera innehållspaket** kan du synkronisera hela projektet med servern.

![chlimage_1-57](assets/chlimage_1-57.png)

### Synkroniseringsstatus {#synchronization-status}

I AEM Brackets Extension finns en meddelandeikon i verktygsfältet till höger om Brackets-fönstret, som anger status för den senaste synkroniseringen:

* grön - alla filer har synkroniserats
* blue - en synkroniseringsåtgärd pågår
* gult - vissa av filerna synkroniserades inte
* röd - ingen av filerna synkroniserades

Om du klickar på meddelandeikonen öppnas dialogrutan Synkroniseringsstatus med en lista över all status för varje synkroniserad fil.

![chlimage_1-58](assets/chlimage_1-58.png)

>[!NOTE]
>
>Endast innehåll som markerats som inkluderat av filtreringsreglerna från `filter.xml` synkroniseras, oavsett vilken synkroniseringsmetod som används.
>
>Dessutom `.vltignore` filer kan användas för att utesluta innehåll från synkronisering till och från databasen.

## Redigera HTML-kod {#editing-htl-code}

AEM Brackets Extension innehåller även vissa funktioner för automatisk komplettering som underlättar skrivandet av HTML-attribut och -uttryck.

### Automatisk komplettering av attribut {#attribute-auto-completion}

1. I ett HTML-attribut skriver du `sly`. Attributet fylls i automatiskt till `data-sly-`.
1. Markera HTL-attributet i listrutan.

### Automatisk komplettering av uttryck {#expression-auto-completion}

Inom ett uttryck `${}`, vanliga variabelnamn slutförs automatiskt.

## Mer information {#more-information}

AEM Brackets Extension är ett öppen källkodsprojekt som hanteras av GitHub av [Adobe Marketing Cloud](https://github.com/Adobe-Marketing-Cloud) organisation, under Apache License, version 2.0:

* Koddatabas: [https://github.com/Adobe-Marketing-Cloud/aem-sightly-brackets-extension](https://github.com/Adobe-Marketing-Cloud/aem-sightly-brackets-extension)
* Apache License, version 2.0: [https://www.apache.org/licenses/LICENSE-2.0.html](https://www.apache.org/licenses/LICENSE-2.0.html)

Kodredigeraren Brackets är även ett öppen källkodsprojekt som hanteras av GitHub av [Adobe Systems Incorporated](https://github.com/adobe) organisation:

* Koddatabas: [https://github.com/adobe/brackets](https://github.com/adobe/brackets)

Du kan bidra!
