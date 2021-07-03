---
title: Bästa praxis för integrering av AEM och Creative Cloud
description: Bästa tillvägagångssätt för att integrera en AEM driftsättning med Adobe Creative Cloud för att effektivisera arbetsflöden för överföring av resurser och uppnå maximal effektivitet
contentOwner: AG
feature: Samarbete,Adobe Asset Link,Skrivbordsapp
role: User,Admin
exl-id: cb9bea05-3359-4fb4-b935-59e522a5f387
source-git-commit: 5d96c09ef764b02e08dcdf480da1ee18f4d9a30c
workflow-type: tm+mt
source-wordcount: '3576'
ht-degree: 15%

---

# Bästa praxis för integrering av AEM och Creative Cloud {#aem-and-creative-cloud-integration-best-practices}

<!-- TBD: Reconcile with 6.5 article that's ahead of this article now in terms of content streamlining and structuring.
-->

Adobe Experience Manager Assets är en DAM-lösning (Digital Asset Management) som kan integreras med Adobe Creative Cloud för att hjälpa DAM-användare att samarbeta med kreativa team och effektivisera samarbetet när innehåll skapas.

Adobe Creative Cloud förser kreativa team med ett ekosystem av lösningar och tjänster som hjälper dem att skapa digitala resurser. Det omfattar dator- och mobilapplikationer, molntjänster som lagring med datorsynkronisering eller webbupplevelse, liksom marknadsplatser som Adobe Stock.

Läs vidare för att ta reda på vilka integreringar som du ska välja mellan stationär dator och företagsspecifik DAM baserat på ditt användningsfall och vilka metoder som är associerade med de sammankopplade arbetsflödena.

>[!NOTE]
>
>Delning av AEM till Creative Cloud-mappar är föråldrat och beskrivs inte längre i den här guiden. Adobe rekommenderar att du använder nyare funktioner som [Adobe Asset Link](https://helpx.adobe.com/enterprise/using/adobe-asset-link.html) eller [AEM datorprogram](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/introduction.html) för att ge kreativa användare åtkomst till resurser som hanteras i AEM.

## Samarbete mellan kreatörer, marknadsförare och DAM-användare {#collaboration-needs-of-creatives-marketers-and-dam-users}

| Krav | Använd skiftläge | Involverade ytor |
|---|---|---|
| Förenkla för kreatörer på datorn | Effektivisera åtkomsten till mediefiler från en DAM (AEM Assets) för kreatörer, eller mer allmänt för användare på datorer som arbetar med program för att skapa egna mediefiler. De behöver ett enkelt och enkelt sätt att upptäcka, använda (öppna), redigera och spara ändringar i AEM samt överföra nya filer. | Skrivbordet Win eller Mac. Creative Cloud-appar |
| Tillhandahåll högklassiga färdiga resurser från Adobe Stock | Marknadsförarna hjälper till att snabba upp processen för att skapa innehåll genom att hjälpa till med materialanskaffning och identifiering. Kreatörer använder det godkända materialet direkt inifrån sina kreativa verktyg. | AEM Assets Adobe Stock Marketplace metadatafält |
| Distribuera och dela resurser efter organisationer | Interna avdelningar/lokala kontor och externa partners, distributörer och byråer använder det godkända material som delas av huvudorganisationen. Organisationen vill säkert och smidigt dela de skapade resurserna för vidare återanvändning. | Brand Portal, Resursdelningskommentarer |

## Adobe för samarbete {#adobe-offerings-to-support-the-collaboration-need}

| Värdeförslag för berörda personer | Adobe | Involverade ytor |
|---|---|---|
| Creative users upptäcker resurser från AEM, öppnar och använder dem, redigerar och överför ändringar till AEM samt överför nya filer till AEM, utan att lämna Creative Cloud-programmen. | [Adobe Asset Link](https://helpx.adobe.com/enterprise/using/adobe-asset-link.html) | Photoshop, Illustrator och InDesign |
| Affärsanvändare förenklar öppning och användning av resurser, redigering och överföring av ändringar i AEM samt överföring av nya filer till AEM från skrivbordsmiljön. De använder en allmän integrering för att öppna alla resurstyper i det inbyggda skrivbordsprogrammet, inklusive andra typer än Adobe. | [AEM](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html) | AEM datorprogram på Win och Mac |
| Marknadsförare och affärsanvändare upptäcker, förhandsgranskar, licensierar och sparar samt hanterar Adobe Stock-resurser inifrån AEM. Licensierade och sparade mediefiler innehåller utvalda Adobe Stock-metadata för bättre styrning. | [Integrering med Experience Manager och Adobe Stock](aem-assets-adobe-stock.md) | AEM webbgränssnitt |

Den här artikeln fokuserar främst på de två första aspekterna av samarbetsbehovet. Distribution och anskaffning av resurser i stor skala omnämns kortfattat som ett användningsexempel. Överväg Adobes varumärkesportal eller Assets Share Commons för sådana behov. Alternativa lösningar som [Brand Portal](https://helpx.adobe.com/se/experience-manager/brand-portal/user-guide.html), lösningar som kan byggas baserat på [Resursdelningskomponenter](https://adobe-marketing-cloud.github.io/asset-share-commons/), [Länkdelning](/help/assets/link-sharing.md), med [Experience Manager Assets](/help/assets/managing-assets-touch-ui.md), bör granskas utifrån specifika krav.

![Creative Cloud-anslutningar för AEM: Bestäm vilka funktioner som ska användas](assets/creative-connections-aem.png)

<!-- 
## Terms and definitions {#terms-and-definitions}

The terms used in this document may have a different meaning in other contexts. In particular, the following terms pertaining to the digital asset lifecycle are used when referring to workflows between a creative professional's desktop and DAM:

* **Work-in-progress or creative work-in-progress (WIP):** A phase in asset lifecycle where an asset undergoes multiple changes and is typically not yet ready to be shared with broader teams.
* **Creative-ready assets:** Assets that are ready to be shared with a broader team, or have been  selected / approved  by the creative team for sharing with marketing or LOB teams.
* **Asset approvals:** The approval process that runs for assets already uploaded to DAM, which typically includes brand approvals, legal approvals, and so on.
* **Final asset:** An asset that has gone through all  approvals/metadata  tagging and is ready to be used by the broader team. Such an asset is stored in DAM and made available to all (or all interested) users. It can be used in marketing channels or by creative teams to create designs.
* **Minor asset  update/change:** A quick and small change to a digital asset. It is often made in response to a retouching or minor editing request, asset review, or approval (for example, reposition, change text size, adjust saturation/brightness, color, and so on).
* **Major asset  update/change:** A change to a digital asset that requires considerable work, and sometimes must be done over a longer period of time. It typically includes multiple changes. The asset must be saved multiple times while being updated. Major asset updates typically cause the asset to enter a WIP stage.
* **DAM:** Digital asset management. In this document, it is synonymous with AEM Experience Manager Assets, unless specifically mentioned otherwise.
* **Creative user:** A creative professional, who creates digital assets using Creative Cloud apps and services. In some cases, a creative user may be a member of a creative team who may use Creative Cloud, but does not create digital assets (like a creative director or creative team manager).
* **DAM user:** A typical user of a DAM system. Depending on the organization, a DAM user can be a marketing or a non-marketing user, for example a Line-of-Business (LOB) user, librarian, sales person, and so on.
-->

### Mappning av användningsfall

| Använd skiftläge | AEM | Mappdelning | Andra lösningar |
|---|---|---|---|
| Dela ett mindre antal (1) DAM-resurser med den kreativa användaren | ✔ ✔ | ✔ |  |
| Dela fler (2) DAM-resurser med den kreativa användaren | ✔ ✔ | ✘ | [Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/home.html) <br> [Resursresurs](assets-finder-editor.md) |
| Dela DAM-resurser med användare som har åtkomst till DAM | ✔ ✔ | ✔ | [Länkdelning](link-sharing.md) |
| Dela DAM-resurser med användare som inte har åtkomst till DAM | ✘ | ✔ ✔ | [Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/home.html) <br> [Resursresurs](assets-finder-editor.md) |
| Spara mindre antal/volym resurser till DAM | ✔ ✔ | ✔ | [Överföring av webbgränssnitt](managing-assets-touch-ui.md) |
| Spara fler resurser på DAM (3) | ✔ ✔ | ✘ | [Webbgränssnitt, ](managing-assets-touch-ui.md) <br> UploadAnpassat skript/verktyg |
| Migrera ett stort antal resurser till DAM | ✘ | ✘ | [Migreringshandbok](assets-migration-guide.md) |
| Öppna en resurs på skrivbordet snabbt | ✔ ✔ | ✘ |  |
| Öppna och ändra resurser snabbt på datorn | ✔ ✔ | ✘ |  |

Förklaring till symbolerna:

* ✔ ✔: bästa lösning
* ✔: godtagbar lösning
* ✘: ska inte användas för användningsfallet

Ytterligare kommentarer:

* (1) Mindre antal resurser: till exempel en liten uppsättning resurser som är kopplade till ett projekt eller en kampanj
* (2) Större antal tillgångar: till exempel alla godkända tillgångar i organisationen
* (3) Använd AEM för överföring av skrivbordsapp

För att stödja användningsexemplen på resursfördelning bör andra lösningar beaktas:

* [Varumärkesportaler ](https://helpx.adobe.com/experience-manager/brand-portal/user-guide.html) för ett konfigurerbart SaaS-tillägg i AEM Assets för publicering av resurser.
* Anpassade lösningar skapas baserat på kodbasen [Resursdelningskommandon](https://adobe-marketing-cloud.github.io/asset-share-commons/).
* AEM [länkresurs](/help/assets/link-sharing.md) för att dela resurser ad hoc med hjälp av länkar.
* [AEM Assets webbgränssnitt ](/help/assets/managing-assets-touch-ui.md) med områden för externa parter som skyddas av AEM Access Control-inställningar och nödvändiga IT-/nätverkskonfigurationsjusteringar, vilket ger dessa externa användare tillgång till AEM.

## Viktiga begrepp och användningsområden {#key-concepts-and-use-cases}

### Ordlista med vanliga termer {#glossary-of-common-terms}

* **Pågående arbeten eller pågående designarbeten (WIP):** En fas i en resurs livscykel där den genomgår flera ändringar och oftast inte är redo att delas med större team.
* **Designresurser:** Resurser som är klara att delas med ett större team eller som har valts ut/godkänts av designteamet för att delas med marknadsförings- eller affärsområdesteam.
* **Godkännanden av resurser:** Godkännandeprocessen som körs för resurser som redan har överförts till DAM, som vanligtvis omfattar varumärkesgodkännanden, juridiska godkännanden och så vidare.
* **Slutlig resurs:** En resurs som har genomgått alla godkännanden och all metadatataggning och är klar att användas av teamet. En sådan resurs lagras i DAM och är tillgänglig för alla (intresserade) användare. Den kan användas i marknadsföringskanaler eller av designteam för att skapa material.
* **Mindre uppdatering/ändring av resurs:** En snabb och liten ändring av en digital resurs. Ändringarna är ofta retuscheringar, smärre redigeringar, resursgranskningar eller godkännanden (t.ex. omplacering, ändring av textstorlek, justering av mättnad/intensitet eller färg).
* **Större uppdatering/ändring av resurs:** En arbetskrävande ändring av en digital resurs, som ibland tar lång tid att genomföra. Den omfattar vanligtvis flera ändringar. Resursen måste sparas flera gånger medan den uppdateras. Större resursuppdateringar medför oftast att resursen får statusen pågående arbete.
* **DAM:** Digitalt resurshanteringssystem. I det här dokumentet är det synonymt med AEM Experience Manager Assets, om inget annat anges.
* **Designanvändare:** En kreatör som skapar digitalt material med Creative Cloud-program och -tjänster. I vissa fall är designanvändaren medlem i ett designteam och kan använda Creative Cloud, men skapar inte digitala resurser (som en designchef eller designteamschef).
* **DAM-användare:** En typisk användare av ett DAM-system. Beroende på organisationen kan en DAM-användare vara en marknadsföringsanvändare eller en icke-marknadsföringsanvändare, till exempel en affärsområdesanvändare, bibliotekarie eller säljare.

### Att tänka på när du använder AEM och Creative Cloud {#considerations-when-using-aem-and-creative-cloud-integration}

* Se [god praxis för skrivbordsprogram](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/troubleshoot.html?lang=en#best-practices-to-prevent-troubles)
* Se [Adobe Stock-integrering](aem-assets-adobe-stock.md)
* Se [Länk till Adobe-resurs](https://helpx.adobe.com/enterprise/using/adobe-asset-link.html)

Detta är en kort sammanfattning av bästa praxis för integrering mellan Experience Manager och Creative Cloud. Läs resten av det här dokumentet för att få en mer detaljerad förståelse för dessa.

* **För designanvändare som arbetar i Photoshop, InDesign eller Illustrator:** Adobe Asset Link ger den bästa användarupplevelsen, inklusive ren hantering av pågående arbeten för resurser som checkats ut från AEM
* **För att förenkla tillgången till resurser från skrivbordet för alla generiska filformat eller program:** använd datorversionen av AEM
* **Förstå varför och när resurser ska lagras i DAM:** Uppdateringar som ska göras tillgängliga för hela teamet i organisationen
* **Tänk på mängden resurser som delas:** Om ni använder mediedistribution kan styrning och säkerhet vara de viktigaste aspekterna. Överväg att använda verktyg som är byggda för att göra detta i stor skala, som varumärkesportalen.
* **Förstå resursers livscykel:** Ta reda på hur resurser hanteras i organisationen av olika team
* **Var försiktig med ofta sparade resurser:** Adobe Asset Link tar hand om det med PS, AI och ID. För andra program bör du inte utföra pågående arbete i mappade/delade mappar om du behöver alla ändringar i DAM

### Tillgång till Adobe Stock-material från AEM Assets {#access-to-adobe-stock-assets-from-aem-assets}

[AEM och Adobe Stock ](/help/assets/aem-assets-adobe-stock.md) integration ger AEM möjlighet att söka, förhandsgranska, licensiera och spara resurser från Adobe Stock i AEM. Licensierade och sparade Adobe Stock-resurser har valt Stock-metadata som kan användas för att söka efter dem med extra filter.

Några viktiga punkter om den här integreringen:

* När resurser från Adobe Stock sparas i AEM blir de ett vanligt AEM Assets med binärfiler sparade i AEM. Vissa metadata som är relaterade till Adobe Stock sparas för resursen i AEM, annars ser det ut som för andra filer. Om till exempel smarta taggar är aktiva läggs taggarna till i de här resurserna när de sparas.
* Resursen som sparas till AEM är en kopia, inte en länk tillbaka till Adobe Stock.

**Arbeta med resurser som sparats från Adobe Stock till AEM i Creative Cloud**. Den här integreringen är oberoende av Adobe Asset Link, men Adobe Asset Link känner igen dessa resurser som sparats från Stock på det sättet och visar ytterligare metadata och Stock-ikoner för dessa resurser i gränssnittet för tillägget Adobe Asset Link i Photoshop, Illustrator eller InDesign. Filerna är tillgängliga för att bläddra, öppna och så vidare, eftersom de är vanliga AEM resurser när de sparas i AEM.
Creative-användare som arbetar i Creative Cloud-program med tillägget Adobe Asset Link kan, förutom att ha tillgång till redan licensierade mediefiler från Adobe Stock till AEM, även använda Creative Cloud Libraries-panelen för att söka efter, förhandsgranska och licensiera Adobe Stock-mediefiler.
Resurser från Adobe Stock som licensierats och sparats i AEM blir tillgängliga för de större team som har tillgång till AEM Assets-distributionen, medan kreatörer som licensierar mediefiler från Adobe Stock via Creative Cloud Libraries endast gör dem tillgängliga för sig själva som standard på sitt Creative Cloud-konto.

<!-- 
TBD: A condensed version of the below content is better placed in the Adobe DAM article.
-->

## Lagra resurser i ett resurshanteringssystem {#about-storing-assets-in-a-dam}

För att skapa ett effektivt arbetsflöde mellan kreatörer och marknadsförare/branschspecifika team (LOB) och välja de bästa supportfunktionerna är det viktigt att förstå när och varför resurser lagras i DAM.

### Varför resurser lagras i DAM {#why-assets-are-stored-in-dam}

Genom att lagra resurser i DAM blir de enkelt tillgängliga och sökbara. Det ser till att resurserna kan utnyttjas av många användare i organisationen eller ekosystemet, bland annat partners, kunder och så vidare.

De flesta organisationer väljer att endast lagra resurser som är relevanta för marknadsförings-/LOB-processerna längre fram i kedjan (publicera till kanaler som webbkanaler via AEM Sites eller andra kanaler som tillhandahålls av Adobe Experience Cloud, Advertising Cloud och mäts av Analytics Cloud, som tillhandahåller till användare/partners osv.). Dessutom lagrar organisationer resurser som kan bli föremål för en gransknings-/godkännandeprocess i DAM. På så sätt lagrar DAM de flesta resurser som har stora chanser att utnyttjas och undviker att lagra inaktiva resurser.

Lagring av resurser är också beroende av tekniska aspekter och resursutnyttjande. DAM tillhandahåller ytterligare tjänster runt lagrade resurser, inklusive extrahering av metadata, versionshantering, generering av förhandsgranskning/omkodning, hantering av referenser och tillägg av åtkomstkontrollsinformation. Dessa tjänster kräver extra tid och infrastrukturresurser.

Det är ofta inte önskvärt att lagra alla resurser och uppdateringar. Om till exempel uppdateringar av specifika resurser har dålig kvalitet och förbrukar för mycket resurser, kanske resurserna inte lagras i DAM.

### När resurser lagras i DAM {#when-assets-are-stored-in-dam}

Kreativa team (och organisationer) är vanligtvis inte intresserade av att lagra resurser i varje skede av resursens livscykel. De undviker till exempel att lagra resurser i följande fall:

* Resurser som ännu inte färdigställts eller som är föremål för experimenterande
* Resurser som inte godkänns i granskningsprocessen
* Jämfört med den aktuella resursen har teamet bättre kandidater att representera sitt arbete för externa team

Vanligtvis lagras följande klassresurser i DAM:

* Tillgångar som har nått en viss löptid och anses vara klara att delas
* Resurser som har valts ut i förväg av det kreativa teamet
* Specifika resursformat som kan användas eller begäras av marknadsföring, beroende på ett specifikt kontrakt eller avtal (t.ex. JPG-filer som konverterats från RAW-filer, TIFF-filer/bilder från PSD-original)

### När uppdateringar av resurser lagras i DAM {#when-updates-to-assets-are-stored-in-dam}

I regel ska endast uppdateringar av resurser som är relevanta för den bredare uppsättningen DAM-användare lagras i DAM. Det ser till att användare (marknadsföringsfunktioner och liknande funktioner) bara ser relevanta versioner på tidslinjen för DAM-resurser.

Vanligtvis ändras relaterade till viktiga milstolpar i resursens livscykel. Till exempel bör det ursprungliga kreativa materialet eller en officiell uppdatering som baseras på begäran/granskning som tillhandahålls av det kreativa teamet lagras och versionsindelas i DAM.

Det kreativa teamets uppdatering för granskning av marknadsföringsteamet efter en begäran om ändring av befintligt material i DAM är ett exempel på en relevant uppdatering. Den ska lagras och versionshanteras i DAM för vidare referens eller för att återgå till den tidigare versionen.

Nedan följer exempel på uppdateringar som vanligtvis inte är relevanta:

* Tidiga versioner av mediefiler som överförts innan de är klara för marknadsföringsgranskning
* Vanliga kreativa ändringar av resursen i den pågående arbetsfasen innan det kreativa teamet bestämmer att resursen är klar

### Användaråtkomst till DAM {#user-access-to-dam}

AEM Assets stöder två typer av användare baserat på deras åtkomst till AEM Assets-distributionen. Vanligtvis har användare i företagsnätverket (brandväggen) direktåtkomst till DAM. Andra användare utanför företagsnätverket skulle inte ha direktåtkomst. Användartypen avgör vilka integreringar som kan användas ur teknisk synpunkt.

#### Kreativa användare med direkt åtkomst till DAM {#creative-users-with-direct-access-to-dam}

Vanligtvis har interna kreativa team, byråer/kreatörer som är anställda i det interna nätverket tillgång till DAM-instansen, inklusive AEM.

I sådana fall kan AEM datorprogram ge enkel åtkomst till det slutliga/godkända materialet och du kan spara kreativa resurser på DAM.

#### Kreativa användare utan åtkomst till DAM {#creative-users-without-access-to-dam}

Externa byråer och frilansare som inte har direkt åtkomst till DAM-instansen kan behöva åtkomst till godkända resurser eller lägga till sina nya designer i DAM.

I så fall kan du utnyttja integrationen mellan AEM och Creative Cloud för att förbättra arbetsflödet. Förutsättningen är att de kreativa användarna har ett Adobe ID-konto och ett Creative Cloud-konto med lagringstjänst.

Använd följande strategier för att ge tillgång till slutliga/godkända mediefiler:

* Så här ger du åtkomst till ett stort antal resurser: Använd [AEM Assets Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/home.html?lang=en) eller kundens implementering av [Resursresurs](assets-finder-editor.md) i AEM publiceringsinfrastruktur

* Så här ger du åtkomst till några resurser: AEM kan användas tillsammans med AEM Assets Brand Portal eller Resursresurs. Observera att det finns vissa begränsningar för den här integreringen som beskrivs mer ingående i den här artikeln.

### Användningsexempel {#use-cases}

Följande exempel beskriver olika typer av arbetsflöden mellan DAM och designerns skrivbord.

#### Skapa ny design med resurser från DAM {#creating-new-designs-using-assets-from-dam}

I följande diagram visas livscykeln för digitala resurser. Det visar hur kreativa användare och DAM-användare (marknadsförare, LOB-användare) utnyttjar befintliga resurser och använder dem för att skapa fler resurser och skicka dem för godkännande.

![chlimage_1-301](assets/chlimage_1-301.png)

Resursens livscykel omfattar följande steg:

1. Dela godkänt material till den kreativa datorn: Slutliga resurser från DAM blir tillgängliga för den kreativa användaren (på datorn)
1. Skapa en ny design (kreativt digitalt material): En ny fil lagras i området Pågående arbete.
1. Använd (placera) godkända resurser i en ny design: Den kreativa användaren skapar en ny resurs med befintliga godkända resurser i Creative Cloud-appar
1. Uppdateringar av pågående arbete sparas ofta: Den kreativa användaren itererar snabbt och sparar filen ofta. I det här skedet kan den kreativa användaren samarbeta med andra, men de ofta sparade uppdateringarna är vanligtvis inte av intresse för DAM-användare.
1. Resursen når sin status som klar för kreativitet och sparas i mappen Creative Ready
1. Resursuppdatering: En resursuppdatering eller en ny fil är tillgänglig för användarna i DAM
1. Resursen används i produktionen: Detta är en DAM-process som, beroende på organisationen, kan omfatta taggning, godkännanden och ändring av åtkomstkontroll. I det här skedet betraktas tillgången som slutgiltig och kan användas av bredare team som utnyttjar DAM. Den kan också användas av kreativa användare för att skapa andra resurser.

Här följer några allmänna rekommendationer om hur du hanterar resurser genom den här processen:

* Använd ett dedikerat lagringsutrymme/system, till exempel Adobe Creative Cloud Assets-synkroniserad mapp, för WIP-filerna: Vanliga uppdateringar som inte är relevanta för DAM-användare hanteras bäst av ett dedikerat system, inte från AEM Assets. WIP-resurser kan synkroniseras till en lokal disk med Adobe Creative Cloud-datorprogram, sparas på en lokal lagringsplats och så vidare.
* Använd separata mappar/resurser för slutliga resurser och resurser som överförs till DAM: För tydlighetens skull bör de slutliga resurserna ha en egen mappad/delad mapp (&quot;Final&quot; example above) och de resurser som ska överföras tillbaka till DAM ska ha en egen (&quot;Creative Ready&quot;)

#### Ändra befintliga resurser som hanteras i DAM {#changing-existing-assets-managed-in-dam}

I vissa fall kan resurser i DAM kräva ändringar. Exempel:

* Begär ändringar av resurser från granskning och godkännande i AEM Assets
* Viktiga uppdateringar av befintliga sluttillgångar
* Snabbredigering av en befintlig fil (särskilt innan den godkänts)

I sådana fall är AEM datorprogram det enklaste sättet att utföra dessa åtgärder.

![chlimage_1-302](assets/chlimage_1-302.png)

Här är händelseflödet som visas i diagrammet:

<!-- TBD for formatting. 
This article will get fixed automatically when 6.5 content is ported to it.
And 6.5 content will be ported after updating it for AEM desktop app 2.0 best practices.
And it will be updated for DA2.0 best practices after 6.5 repo is available for writers to edit content in.
-->

* **1:** Dela resursen från DAM till skrivbordet eller öppna den direkt på skrivbordet i det program du föredrar (t.ex. Adobe Photoshop). Du bör checka ut om du vill låsa filen.
* **2:** Mindre uppdatering: Redigera filen och spara ändringarna.
* Alternativt flöde till steg 2

   * **A:** Huvuduppdatering: Om filen kräver en omfattande uppsättning ändringar bör den sparas regelbundet och kopieras till en Pågående arbete-mapp/ett Pågående arbete-område.
   * **B:** Arbetet med filen fortsätter i Pågående arbete-mapparna. De sparade ändringarna synkroniseras inte till versionen i DAM
   * **C:** När uppdateringarna är klara kopieras filen tillbaka eller sparas i den mappade mappen

* **3:** Resursuppdateringar återspeglas i DAM. Checka in resursen för att låsa upp den.
* **4:** Resursen används i produktionen.

Här följer några allmänna rekommendationer om hur du hanterar resurser under den här processen:

* Undvik att spara en fil som du har öppnat direkt från en nätverksresurs som har mappats av AEM skrivbordsappen, såvida inte ändringarna du har gjort i filen är små.
* Kopiera filen till en separat Pågående arbete-mapp om du vill göra ytterligare ändringar i den, spara regelbundet eller samarbeta med det kreativa teamet.

#### Massöverföring till DAM {#bulk-upload-to-dam}

Du kan behöva överföra ett större antal filer till DAM samtidigt i vissa scenarier, till exempel:

* Överföra resultat från foton eller större projekt
* Överföra material från reklambyråer
* Överför markerade resurser från en större uppsättning om markeringen görs utanför DAM

Observera att den här beskrivningen avser att överföra filer operativt (t.ex. varje vecka, eller med varje fotografering osv.), som en normal del av datoranvändarens arbetsflöde. Stora resursmigreringar beskrivs inte här.

Du kan utnyttja följande funktioner om du vill överföra resurser i grupp:

* Om du vill överföra stora/hierarkiska mappar använder du AEM skrivbordsapp, som innehåller funktionen [Mappöverföring](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html#bulkupload). Du kan också överföra hierarkiska mappstrukturer. Resurserna överförs i bakgrunden och är därför inte knutna till en webbläsarsession
* Om du vill överföra några filer från en enda mapp drar du dem direkt från skrivbordet till webbgränssnittet eller använder alternativet Skapa i AEM Assets webbgränssnitt.

>[!NOTE]
>
>Beroende på vilka affärskrav du har kan du även använda en anpassad överförare.

#### Hantera digitala resurser direkt från skrivbordet {#managing-digital-assets-directly-from-desktop}

Om du använder Network File Shares för att hantera digitala resurser kan du se att bara den nätverksresurs som mappas av AEM datorprogram används som ett praktiskt alternativ. När du övergår från filresurser i nätverk bör du komma ihåg att AEM Web UI innehåller en mängd funktioner för hantering av digitala resurser som går mycket längre än vad som är möjligt på en nätverksresurs (sökning, samlingar, metadata, samarbete, förhandsvisningar osv.) och AEM datorprogrammet erbjuder en praktisk länk för att ansluta DAM-databasen på serversidan med datorarbetet.

Undvik att använda AEM datorprogram för att hantera resurser direkt i AEM Assets nätverksresurs. Undvik till exempel att använda AEM datorprogram för att flytta/kopiera flera filer. Använd i stället AEM Assets webbgränssnitt för att dra mappar från Finder/Utforskaren till nätverksresursen eller använd funktionen AEM Assets mappöverföring.

#### Resursmigrering {#asset-migration}

Information om hur du planerar och kör resursmigreringar från ett befintligt system till ett nytt system eller migrering av stora volymer resurser som lagras på servrar finns i [migreringshandboken](/help/assets/assets-migration-guide.md). AEM datorprogram och integreringar från AEM till Creative Cloud stöder inte sådana migreringar. På grund av de stora volymer resurser som ska importeras och ytterligare krav på metadatamappning, omvandling och förtäring bör migreringar hanteras med olika verktyg och metoder.

>[!MORELIKETHIS]
>
>* [Adobe Asset Link](https://helpx.adobe.com/in/enterprise/admin-guide.html/in/enterprise/using/adobe-asset-link.ug.html)
>* [Bästa praxis för AEM](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/archive/best-practices-for-v1.html)
>* [AEM Brand Portal](https://experienceleague.adobe.com/docs/experience-manager-brand-portal/using/introduction/brand-portal.html)
>* [Integrering med AEM och Adobe Stock](aem-assets-adobe-stock.md)

