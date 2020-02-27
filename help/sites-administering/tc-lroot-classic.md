---
title: Skapa en språkrot med det klassiska användargränssnittet
seo-title: Skapa en språkrot med det klassiska användargränssnittet
description: Lär dig hur du skapar en språkrot med det klassiska användargränssnittet.
seo-description: Lär dig hur du skapar en språkrot med det klassiska användargränssnittet.
uuid: d44a51a0-1507-4838-851c-cacff48ad825
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: site-features
content-type: reference
discoiquuid: 237b8cc6-158e-4c51-970d-4c9cc74f6496
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Skapa en språkrot med det klassiska användargränssnittet{#creating-a-language-root-using-the-classic-ui}

I följande procedur används det klassiska användargränssnittet för att skapa en språkrot för en plats. Mer information finns i [Skapa en språkrot](/help/sites-administering/tc-prep.md#creating-a-language-root).

1. I webbplatskonsolen väljer du webbplatsens rotsida i webbplatsträdet. ([http://localhost:4502/siteadmin#](http://localhost:4502/siteadmin#))
1. Lägg till en ny underordnad sida som representerar webbplatsens språkversion:

   1. Klicka på Ny > Ny sida.
   1. Ange titel och namn i dialogrutan. Namnet måste ha formatet `<language-code>` eller `<language-code>_<country-code>`t.ex. en_US, en_us, en_GB, en_gb.

      * Den språkkod som stöds är en kod med två bokstäver och gemener som definieras av ISO-639-1
      * Den landskod som stöds är gemen eller versal, tvåbokstavskod enligt ISO 3166
   1. Markera mallen och klicka på Skapa.
   ![newpagefr](assets/newpagefr.png)

1. I webbplatskonsolen väljer du webbplatsens rotsida i webbplatsträdet.
1. Välj Språkkopia på Verktyg-menyn.

   ![toolslanguagecopy](assets/toolslanguagecopy.png)

   I dialogrutan Språkkopia visas en matris med tillgängliga språkversioner och webbsidor. Ett x i en språkkolumn betyder att sidan är tillgänglig på det språket.

   ![språkDialogrutan](assets/languagecopydialog.png)

1. Om du vill kopiera en befintlig sida eller ett befintligt sidträd till en språkversion, markerar du cellen för sidan i språkkolumnen. Klicka på pilen och välj den typ av kopia som ska skapas.

   I följande exempel kopieras sidan för utrustning/solglasögon/irian till den franska språkversionen.

   ![språkopydilogdropdown](assets/languagecopydilogdropdown.png)

   | Typ av språkkopia | Beskrivning |
   |---|---|
   | autom. | Använder beteendet från överordnade sidor |
   | ignorera | Skapar inte en kopia av den här sidan och dess underordnade sidor |
   | `<language>+` (t.ex. franska+) | Kopierar sidan och alla underordnade sidor från det språket |
   | `<language>` (t.ex. franska) | Kopierar endast sidan från det språket |

1. Stäng dialogrutan genom att klicka på OK.
1. Klicka på Ja i nästa dialogruta för att bekräfta kopian.

