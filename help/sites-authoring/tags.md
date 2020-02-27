---
title: Använda taggar
seo-title: Använda taggar
description: Taggar är ett snabbt och enkelt sätt att klassificera innehåll på en webbplats
seo-description: Taggar är ett snabbt och enkelt sätt att klassificera innehåll på en webbplats
uuid: a91f8724-fc35-4f40-b21c-bee90429765b
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: site-features
discoiquuid: d0b0e47b-e68d-407d-9d06-deca2039dede
translation-type: tm+mt
source-git-commit: 8326ee711558a390f79fc185fc37bbbb3097e309

---


# Använda taggar {#using-tags}

Taggar är ett snabbt och enkelt sätt att klassificera innehåll på en webbplats. Taggar kan ses som nyckelord eller etiketter som kan bifogas till en sida, en resurs eller annat innehåll för att göra det möjligt att söka efter innehållet och relaterat innehåll.

* Se [Administrera taggar](/help/sites-administering/tags.md) för information om hur du skapar och hanterar taggar samt om vilka innehållstaggar som har tillämpats.
* Mer information om taggningsramverket samt om hur du inkluderar och utökar taggar i anpassade program finns i [Tagga för utvecklare](/help/sites-developing/tags.md) .

## Tio skäl att använda märkord {#ten-reasons-to-use-tagging}

1. Ordna innehåll: taggning gör livet enklare för skribenterna eftersom de snabbt kan ordna innehållet med mindre ansträngning.

1. Ordna taggar: När taggar organiserar innehåll organiserar hierarkiska taxonomier/namnutrymmen taggar.

1. Djupt sorterade taggar: med möjlighet att skapa taggar och undertaggar blir det möjligt att uttrycka hela taxonomiska system, som omfattar termer, undertermer och deras relationer. Detta gör att en andra (eller tredje) innehållshierarki kan skapas parallellt med den officiella.

1. Kontrollerad taggning: taggningen kan styras genom att behörigheter tillämpas på taggar och/eller namnutrymmen för att styra hur taggar skapas och används.

1. Flexibel taggning: Taggar har många namn och ansikten: taggar, taxonomitermer, kategorier, etiketter och mycket annat. De är flexibla i sin innehållsmodell och i hur de kan användas. om du t.ex. anger målgrafik, kategoriserar och klassificerar innehåll eller skapar en sekundär innehållshierarki.

1. Förbättrad sökning: standardsökkomponenten i AEM omfattar i stort sett skapade taggar och använda taggar som du kan använda filter på för att begränsa resultaten till de som är relevanta.

1. SEO-aktivering: taggar som används som sidegenskaper visas automatiskt i de metataggar på sidan som gör den synlig för sökmotorer.

1. Enkel sofistikering: -taggar kan skapas från ett ord och med en knapptryckning. Därefter kan en titel, beskrivning och ett obegränsat antal etiketter läggas till för att ge taggen mer semantik.

1. Styckesammans konsekvens: taggningssystemet är en kärnkomponent i AEM och används av alla AEM-funktioner för att kategorisera innehåll. Programmeringsgränssnittet för taggning är även tillgängligt för utvecklare som skapar taggningsaktiverade program med tillgång till samma taxonomier.

1. Kombinerar struktur och flexibilitet: AEM är idealiskt för att arbeta med strukturerad information på grund av inkapsling av sidor och sökvägar. Det är lika kraftfullt när du arbetar med ostrukturerad information på grund av den inbyggda textsökningen. Taggning kombinerar styrkan hos både strukturen och flexibiliteten.

När du utformar innehållsstrukturen för en plats och metadatarammet för resurser bör du tänka på att taggningen är enkel och tillgänglig.

## Tillämpar taggar {#applying-tags}

I redigeringsmiljön kan författare lägga till taggar genom att gå till sidegenskaperna och ange en eller flera taggar i fältet **Taggar/nyckelord** .

Om du vill använda [fördefinierade taggar](/help/sites-administering/tags.md)använder du fältet **Taggar** och fönstret **Markera taggar** i fönstret **Sidegenskaper** . Fliken **Standardtaggar** är standardnamnutrymmet, vilket innebär att det inte finns något `namespace-string:` prefix till taxonomin.

![chlimage_1-92](assets/chlimage_1-92.png)

### Publiceringstaggar {#publishing-tags}

Precis som med sidor kan du göra följande med taggar och namnutrymmen:

**Aktivera**

* Aktivera enskilda taggar.

   Precis som för sidor måste nyligen skapade taggar aktiveras innan de blir tillgängliga i publiceringsmiljön.

>[!NOTE]
>
>När du aktiverar en sida öppnas en dialogruta automatiskt där du kan aktivera oaktiverade taggar som hör till sidan.

**Inaktivera**

* Inaktivera de markerade taggarna.

## Tagga moln {#tag-clouds}

Taggmoln visar ett moln med taggar, antingen för den aktuella sidan, för hela webbplatsen eller för de mest använda. Tagga moln är ett sätt att markera problem som är (har varit) av intresse för användaren. Storleken på texten som används för att visa taggen varierar beroende på hur den används.

Komponenten [Tag Cloud](/help/sites-authoring/default-components-foundation.md#tag-cloud) (allmän komponentgrupp) används för att lägga till ett taggmoln på en sida.

## Söka på taggar {#searching-on-tags}

Du kan söka efter taggar både i författarmiljön och i publiceringsmiljön.

### Använda sökkomponenten {#using-search-component}

Om du lägger till en [sökkomponent](/help/sites-authoring/default-components-foundation.md#search) på en sida får du en sökfunktion som innehåller taggar och kan användas i både författarmiljön och publiceringsmiljön.

![chlimage_1-93](assets/chlimage_1-93.png)

