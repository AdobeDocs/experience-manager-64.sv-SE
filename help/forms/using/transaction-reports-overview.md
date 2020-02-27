---
title: Översikt över transaktionsrapporter
seo-title: Översikt över transaktionsrapporter
description: Räkna med alla inskickade blanketter, interaktiv kommunikation, dokument som konverterats till ett format till ett annat, med mera
seo-description: Räkna med alla inskickade blanketter, interaktiv kommunikation, dokument som konverterats till ett format till ett annat, med mera
uuid: b40220e6-88c8-4507-b228-6c57d9b54422
contentOwner: khsingh
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-manager
discoiquuid: 1fb11e02-d8f1-41a0-8e23-cb890b4e2244
translation-type: tm+mt
source-git-commit: 0797eeae57ac5a9676c6d308eaf2aaffab999d18

---


# Översikt över transaktionsrapporter {#transaction-reports-overview}

Räkna med alla inskickade blanketter, interaktiv kommunikation, dokument som konverterats till ett format till ett annat, med mera

## Introduktion {#introduction}

Med transaktionsrapporter i AEM Forms kan du räkna med alla transaktioner som har utförts sedan ett visst datum vid distributionen av AEM Forms. Målet är att tillhandahålla information om produktanvändning och hjälpa företagsintressenter att förstå sina digitala bearbetningsvolymer. Exempel på en transaktion är:

* Skicka in ett anpassningsbart formulär, ett HTML5-formulär eller en formuläruppsättning
* Återgivning av en utskrift eller webbversion av en interaktiv kommunikation
* Konvertering av ett dokument från ett filformat till ett annat

Mer information om vad som betraktas som en transaktion finns i [Fakturerbara API:er](/help/forms/using/transaction-reports-billable-apis.md).

Transaktionsregistrering är inaktiverat som standard. Du kan [aktivera transaktionsregistrering](/help/forms/using/viewing-and-understanding-transaction-reports.md#setting-up-transaction-reports) från AEM Web Console. Du kan visa transaktionsrapporter om författare, bearbetning eller publicering. Visa transaktionsrapporter om författare eller bearbetningsinstanser för en sammanställd summa av alla transaktioner. Visa transaktionsrapporter på publiceringsinstanserna för att se antalet transaktioner som bara äger rum på den publiceringsinstans som rapporten körs från.

Skapa inte innehåll (Skapa adaptiva formulär, interaktiv kommunikation, teman och andra redigeringsaktiviteter) eller bearbeta dokument (Använd arbetsflöden, dokumenttjänster och andra bearbetningsaktiviteter) i samma AEM-instans. Behåll transaktionsinspelningen inaktiverad för AEM Forms-servrar som används för att skapa innehåll. Låt transaktionsregistrering vara aktiverat för AEM Forms-servrar som används för att bearbeta dokument.

![sample-transaction-report-author-1](assets/sample-transaction-report-author-1.png)

En transaktion finns kvar i bufferten under en angiven period (Tömningstid för buffert + Omvänd replikeringstid). Som standard tar det ca 90 sekunder för antalet transaktioner att återspeglas i transaktionsrapporten.

Åtgärder som att skicka ett PDF-formulär, använda agentgränssnittet för att förhandsgranska interaktiv kommunikation eller använda icke-standardiserade metoder för att skicka formulär räknas inte som transaktioner. AEM Forms tillhandahåller ett API för att registrera sådana transaktioner. Anropa API:t från dina anpassade implementeringar för att registrera en transaktion.

## Topologi som stöds {#supported-topology}

Transaktionsrapporter är bara tillgängliga på AEM Forms i OSGi-miljö. Det stöder författarpublicering, författarbearbetning-publicering och endast bearbetningstopologier. Exempel på topologier finns i [Arkitektur och distributionstopologier för AEM Forms](/help/forms/using/transaction-reports-overview.md).

Transaktionsantalet replikeras baklänges från publiceringsinstanser till författare eller bearbetningsinstanser. En indikativ topologi för författarpublicering visas nedan:

![simple-author-publish-topology](assets/simple-author-publish-topology.png)

>[!NOTE]
>
>Transaktionsrapporter för AEM Forms stöder inte topologier som bara innehåller publiceringsinstanser.

### Riktlinjer för att använda transaktionsrapporter {#guidelines-for-using-transaction-reports}

* Inaktivera transaktionsrapporter för alla författarinstanser som rapporter om författarinstanser inkluderar transaktioner som registrerats under redigeringsaktiviteter.
* Aktivera alternativet **Visa transaktioner från publicering endast** på författarinstansen om du vill visa kumulativa transaktioner från alla publiceringsinstanser. Du kan också visa transaktionsrapporter för varje publiceringsinstans för faktiska transaktioner endast för den aktuella publiceringsinstansen.
* Använd inte författarinstanser för att köra arbetsflöden och bearbeta dokument.
* Innan du använder transaktionsrapportering måste du se till att omvänd replikering är aktiverat för alla publiceringsinstanser om du har en tologi med publiceringsservrar.
* Transaktionsdata återreplikeras från en publiceringsinstans till endast motsvarande författare eller bearbetningsinstans. Författaren eller bearbetningsinstansen kan inte replikera data till en annan instans. Om du till exempel har en topologi för redigeringsbearbetning/publicering, replikeras aggregerade transaktionsdata bara till bearbetningsinstansen.

## Relaterade artiklar {#related-articles}

* [Visa och förstå transaktionsrapporter](/help/forms/using/viewing-and-understanding-transaction-reports.md)
* [Fakturerbara API:er för transaktionsrapporter](/help/forms/using/transaction-reports-billable-apis.md)
* [Registrera en transaktion för anpassade implementeringar](/help/forms/using/record-transaction-custom-implementation.md)

