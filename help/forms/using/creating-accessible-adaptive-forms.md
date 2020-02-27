---
title: Skapa hjälpmedelsförberedda adaptiva formulär
seo-title: Skapa hjälpmedelsförberedda adaptiva formulär
description: Med AEM Forms får du verktyg och verktyg för att skapa hjälpmedelsförberedda formulär som uppfyller alla tillgänglighetsstandarder.
seo-description: Med AEM Forms får du verktyg och verktyg för att skapa hjälpmedelsförberedda formulär som uppfyller alla tillgänglighetsstandarder.
uuid: eceb3282-0b90-4e0a-8b89-137d27029747
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 96d9ad52-074b-4084-b818-abce79282776
translation-type: tm+mt
source-git-commit: 7e58d1d861f832d073fb178868804995ee8d855b

---


# Skapa hjälpmedelsförberedda adaptiva formulär {#creating-accessible-adaptive-forms}

## Introduktion {#introduction}

Ett hjälpmedelsanpassat formulär är ett formulär som alla kan använda, inklusive användare med särskilda behov. Adobe Experience Manager (AEM) innehåller ett antal funktioner som gör det enklare att använda adaptiva formulär för användare med olika funktioner. Lösningen hjälper också formulärförfattare att skapa tillgängliga adaptiva formulär.

Att bygga in tillgänglighet i anpassningsbara formulär ger inte bara en så bred publik som möjligt, utan det är också ett krav när det gäller att leverera dokument i områden där det krävs överensstämmelse med tillgänglighetsstandarder. AEM Forms hjälper formulärutvecklare att följa tillgänglighetsstandarderna.

När du skapar ett anpassat formulär bör du tänka på följande när du skapar hjälpmedelsförberedda formulär:

* Ange korrekta etiketter för formulärkontroller
* Ange textmotsvarigheter för bilder
* Ange tillräcklig färgkontrast
* Kontrollera att formulärkontrollerna är tangentbordstillgängliga

##  Ange korrekta etiketter för formulärkontroller {#provide-proper-labels-for-form-controls}

Etiketten eller titeln för en komponent identifierar vad formulärkomponenten representerar. Texten &quot;Förnamn&quot; anger till exempel att användaren måste ange sitt förnamn i ett textfält. För att skärmläsare ska kunna komma åt etiketten är den programmatiskt kopplad till en formulärkomponent. Formulärkontrollen kan även konfigureras med ytterligare hjälpmedelsinformation.

Etiketten som upplevs av skärmläsare behöver inte nödvändigtvis vara samma som den visuella bildtexten. I vissa fall kanske du vill ange kontrollens syfte mer specifikt. För varje fältobjekt i ett formulär kan hjälpmedelsalternativen användas för att ange vad skärmläsaren ska meddela för att identifiera det specifika formulärfältet.

Så här använder du alternativet Hjälpmedel:

1. Markera en komponent och tryck på ![cmpr](assets/cmppr.png).
1. Klicka på **Tillgänglighet** i sidlisten för att välja det önskade hjälpmedelsalternativet.

### Tillgänglighetsalternativ i formulärkomponenter {#accessibility-options-in-form-components}

![Tillgänglighetsalternativ i formulärkomponenter](assets/accessibility-options.png)

**Författare av anpassade textformulär** tillhandahåller innehållet i hjälpmedelsalternativet Anpassad text. Den här anpassade texten används i hjälpmedelstekniken, till exempel skärmläsare. Att använda inställningen Titel är det bästa alternativet i de flesta scenarier. Du bör endast skapa anpassad uppläsningstext när du inte kan använda titeln eller en kort beskrivning.

**Kort beskrivning** För de flesta komponenter visas den korta beskrivningen vid körning när användaren placerar pekaren över komponenten. Du kan ange det här alternativet i fältet för kort beskrivning under alternativet för hjälpinnehåll.

**Titel** Använd det här alternativet om du vill att AEM Forms ska använda den visuella etikett som är kopplad till formulärfältet som skärmläsartext.

**Namn** Du kan ange ett värde i fältet Namn på fliken Bindning. Namnet får inte innehålla blanksteg.

**Om du väljer Ingen** och inte väljer Ingen får formulärobjektet inget namn i det publicerade formuläret. Ingen rekommenderas inte för formulärkontroller.

>[!NOTE]
>
>Alternativknapp och kryssruta kan bara ha två alternativ för tillgänglighet: Anpassad text och Titel.

>[!NOTE]
>
>För XFA-baserade adaptiva formulär ärvs hjälpmedelsalternativet från de hjälpmedelsalternativ som angetts i XDP. Verktygstips från XDP mappas till Short Description och Caption mappas till Title. De andra alternativen fungerar som de är.

##  Ange textmotsvarigheter för bilder {#provide-text-equivalents-for-images}

Bilder kan förbättra förståelsen för vissa användare. För användare som använder skärmläsare minskar dock bilderna formulärets tillgänglighet. Om du väljer att använda bilder anger du textbeskrivningar för alla bilder.

Kontrollera att texten beskriver objektet och dess syfte i formuläret. En skärmläsare läser upp den här alternativa texten när en bild påträffas. En bild måste alltid ha en alternativ text angiven.

Markera en bildkomponent och tryck på ![cmpr](assets/cmppr.png). Ange alternativ text för en bild under Egenskaper i sidlisten.

![Alternativ text för en bild](assets/image-properties.png)

##  Ange tillräcklig färgkontrast {#provide-sufficient-color-contrast}

Hjälpmedelsdesignen inbegriper att överväga ytterligare riktlinjer för färganvändning. Formulärförfattare kan använda färger för att förbättra formulärens utseende genom att markera olika formulärkomponenter. En felaktig användning av färg kan dock göra ett formulär svårt eller omöjligt att läsa av personer med olika funktioner.

Användare med nedsatt syn förlitar sig på hög kontrast mellan text och bakgrunden för att läsa digitalt innehåll. Utan tillräcklig kontrast kan ett formulär bli svårt, för att inte säga omöjligt, att läsa för vissa användare.

Vi rekommenderar att du använder standardfärgerna för teckensnitt och bakgrund - innehåll i svart färg mot en vit bakgrund. Om du ändrar standardfärgerna väljer du antingen en mörk förgrundsfärg på en ljus bakgrundsfärg, eller tvärtom.

Mer information om hur du ändrar färgkontrast och tema för anpassade former finns i [Skapa anpassade teman för anpassade formulär](/help/forms/using/creating-custom-adaptive-form-themes.md).

##  Kontrollera att formulärkontrollerna är tangentbordstillgängliga {#ensure-that-form-controls-are-keyboard-accessible}

Ett hjälpmedelsanpassat formulär kan fyllas i helt med bara tangentbordet eller en motsvarande indataenhet. Användare med nedsatt rörelseförmåga eller nedsatt syn har kanske inget annat val än att använda tangentbordet och många användare som kan använda en mus föredrar tangentbordsinmatning. Genom att använda de olika indatametoderna kan du inte bara skapa hjälpmedelsförberedda formulär, du kan också skapa formulär som bättre passar alla användares önskemål.

Följande kortkommandon finns i AEM Forms.

| Åtgärd | Kortkommando |
|---|---|
| Flytta markören framåt genom ett formulär | Tabb |
| Flytta markören bakåt genom ett formulär | Skift+Tabb |
| Flytta till nästa panel | Alt + högerpil |
| Flytta till föregående panel | Alt + vänsterpil |
| Återställ ifyllda data i ett formulär | Alt+R |
| Skicka ett formulär | Alt+S | configuring-watch-folder-endpoints.md |