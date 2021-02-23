---
title: Dela AEM Assets-mappar med Creative Cloud
description: Konfiguration och bästa praxis som gör att användare av Adobe Experience Manager Assets kan utbyta resursmappar med Adobe Creative Cloud-användare.
contentOwner: AG
translation-type: tm+mt
source-git-commit: e64f5b0e1333d511eaf450072756a95399e838d0
workflow-type: tm+mt
source-wordcount: '1061'
ht-degree: 0%

---


# AEM till Creative Cloud-mappen som delar metodtips {#aem-to-creative-cloud-folder-sharing-best-practices}

>[!CAUTION]
>
>Mappdelningsfunktionen AEM till Creative Cloud är föråldrad. Adobe rekommenderar starkt att du använder nyare funktioner som [Adobe Asset Link](https://helpx.adobe.com/enterprise/admin-guide.html/enterprise/using/adobe-asset-link.ug.html) eller [AEM datorprogram](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html). Läs mer i [Bästa praxis för integrering av AEM och Creative Cloud](/help/assets/aem-cc-integration-best-practices.md).

Adobe Experience Manager (AEM) kan konfigureras så att användare i AEM Assets kan dela mappar med Creative Cloud-användare, så att de är tillgängliga som delade mappar i Creative Cloud Assets-tjänsten. Funktionen kan användas för utbyte av filer mellan kreativa team och AEM Assets-användare, särskilt när de kreativa användarna inte har tillgång till AEM Assets-instansen (de finns inte i företagsnätverket).

Den här typen av integrering kan användas i båda fallen, särskilt när du arbetar med användare som inte har direkt åtkomst till AEM Assets:

* Dela en uppsättning specifika resurser från AEM Assets med användare av Creative Cloud Files (t.ex. en översikt och en uppsättning godkända resurser för designarbete för en ny marknadsföringsaktivitet)
* Tar emot nya filer från Creative Cloud-användare.

>[!NOTE]
>
>Innan du läser det här dokumentet kan du läsa igenom den övergripande [AEM och bästa praxis för integrering med Creative Cloud](aem-cc-integration-best-practices.md) för en översikt över ämnet på högre nivå.

## Översikt {#overview}

AEM till mappdelning mellan Creative Cloud är beroende av att mappar och filer delas på serversidan mellan AEM Assets- och Creative Cloud-konton. Kreatörer som använder datorprogrammet Creative Cloud på sina datorer kan dessutom göra de delade mapparna tillgängliga direkt på sina diskar med hjälp av Adobe CreativeSync teknik.

I följande diagram visas en översikt över integreringen.

![chlimage_1-406](assets/chlimage_1-406.png)

Integreringen innehåller följande element:

* **AEM Assets-** servrar som används i företagsnätverket (hanterade tjänster eller lokalt): Mappdelning initieras här.
* **Adobe Marketing Cloud Assets core service**: Fungerar som mellanhand mellan AEM och Creative Cloud. Administratören för det företag som använder integreringen måste upprätta en förtroenderelation mellan Marketing Cloud-organisationen och AEM Assets-instansen. De [definierar också en lista över medarbetare på Creative Cloud](https://experienceleague.adobe.com/docs/core-services/interface/assets/t-admin-add-cc-user.html?lang=en#assets) som AEM Assets-användare kan dela mappar för att öka säkerheten.
* **Creative Cloud Assets web services**  (storage and Creative Cloud Files web UI): Det är här specifika Creative Cloud-användare, som har en AEM Assets-mapp delad, kan acceptera inbjudan och se mappen i sitt Creative Cloud-kontoarkiv.
* **Creative Cloud-datorprogram**: (Valfritt) Möjliggör direkt åtkomst till delade mappar/filer från den kreativa användarens skrivbord via synkronisering med Creative Cloud Assets-lagring.

## Egenskaper och begränsningar {#characteristics-and-limitations}

* **Envägsspridning av ändringar:** Filändringar sprids endast i en riktning - från systemet (AEM eller Creative Cloud Assets), där resursen ursprungligen skapades (överfördes). Integreringen ger ingen helautomatiserad tvåvägssynkronisering mellan de två systemen.

* **Versionshantering:**

   * AEM skapar bara versioner av en resurs vid uppdateringar om filen har sitt ursprung i AEM och uppdateras där.
   * Creative Cloud Assets har en egen [versionsfunktion](https://helpx.adobe.com/creative-cloud/help/versioning-faq.html) som är inriktad på uppdateringar för pågående arbete (lagrar i princip uppdateringar i upp till 10 dagar)

* **Utrymmesbegränsningar:** Storlekar och volymer av filer som utbyts begränsas av  [Creative Cloud Assets-](https://helpx.adobe.com/creative-cloud/kb/file-storage-quota.html) kvoten för kreativa användare (beror på prenumerationsnivå) och en begränsning på 5 GB. Utrymmet begränsas dessutom av den tillgångskvot som organisationen har i Adobe Marketing Cloud Assets bastjänst.

* **Utrymmeskrav:** Filerna i delade mappar måste också lagras fysiskt i AEM och sedan i Creative Cloud, med en cachelagrad kopia i huvudtjänsten Marketing Cloud Assets.
* **Nätverk och bandbredd:** Filerna i delade mappar och alla uppdateringar måste transporteras över nätverket mellan systemen. Du bör se till att endast relevanta filer och uppdateringar delas.
* **Mapptyp**: Det går inte att dela en resursmapp av typen  `sling:OrderedFolder`. Om du vill dela en mapp ska du inte markera alternativet Ordnad när du skapar den i AEM Assets.

## God praxis {#best-practices}

De bästa sätten att utnyttja delning av AEM till Creative Cloud är:

* **Volymeffekter:** Mappdelning mellan AEM och Creative Cloud bör användas för att dela ett mindre antal filer, t.ex. relevanta för en viss kampanj eller aktivitet. Om du vill dela större uppsättningar resurser, som alla godkända resurser i organisationen, använder du andra distributionsmetoder (till exempel AEM Assets Brand Portal) eller AEM datorprogram.
* **Undvik delning av djupa hierarkier:** Delningen fungerar rekursivt och tillåter inte selektiv delning. Normalt bör endast mappar utan undermappar, eller med en mycket kort hierarki, som 1 undermappsnivå, användas för delning.
* **Separata mappar för envägsdelning:** Separata mappar bör användas för att dela det slutliga materialet från AEM Assets till Creative Cloud-filer och för att dela det kreativa materialet tillbaka från Creative Cloud-filer till AEM Assets. Tillsammans med en bra namnkonvention för de här mapparna skapar det en lättbegriplig arbetsmiljö för användare av både AEM Assets och Creative Cloud.
* **Undvik PIA i den delade mappen:** Delad mapp ska inte användas för Pågående arbete - använd en separat mapp i Filer i Creative Cloud för att utföra arbete som kräver många ändringar av filen.
* **Starta nytt arbete utanför den delade mappen:** Nya designer (kreativa filer) ska startas i den separata Pågående arbete-mappen i Creative Cloud-filer, och när de är klara att delas med AEM Assets-användare bör de flyttas eller sparas i den delade mappen.
* **Förenkla delningsstrukturen:** För en mer hanterbar driftsättning kan du tänka på att förenkla delningsstrukturen. I stället för att dela med alla kreativa användare bör AEM Assets-mappar endast delas med grupprepresentanter, som en creative director eller teammanager. Chefen på den kreativa sidan skulle få det slutliga materialet, besluta om arbetstilldelning och sedan låta designers arbeta i sina egna Creative Cloud-konton på PIA-resurser. De kan använda samarbetsfunktionerna i Creative Cloud för att koordinera arbetet och slutligen välja och placera resurser som är redo att delas tillbaka till AEM Assets i deras kreativa färdiga delade mapp.

I följande diagram visas ett exempel på hur du skapar nya designer baserat på befintliga slutliga resurser från AEM Assets.

![chlimage_1-407](assets/chlimage_1-407.png)
