---
title: Resursmallar
description: Lär dig mer om tillgångsmallar i AEM Assets och hur du använder tillgångsmallar för att skapa marknadsföringsmaterial.
uuid: 7ba87c1d-70cd-4b89-86f3-971b93885f1e
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 340b62f7-2405-4d2d-846d-2c444d6cc77b
feature: Asset Management,Developer Tools
role: Business Practitioner
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '1577'
ht-degree: 1%

---


# Resursmallar {#asset-templates}

Resursmallar är en speciell typ av resurser som gör det enkelt att snabbt återanvända visuellt avancerat innehåll för digitala medier och trycksaker. En resursmall består av två delar, avsnittet med fasta meddelanden och det redigerbara avsnittet.

Avsnittet med fasta meddelanden kan innehålla eget innehåll, t.ex. varumärkeslogotyp och copyrightinformation som har inaktiverats för redigering. Det redigerbara avsnittet kan innehålla visuellt och textbaserat innehåll i fält som kan redigeras för att anpassa meddelanden.

Flexibiliteten att göra begränsade redigeringar samtidigt som globala signaturer skyddas gör att materialmallar är idealiska byggstenar för snabb innehållsanpassning och distribution som innehållsartefakter för olika funktioner. Återanvändning av innehåll minskar kostnaderna för att hantera tryckta och digitala kanaler och leverera en helhetsbild och enhetliga upplevelser i alla dessa kanaler.

Som marknadsförare kan ni lagra och hantera mallar i AEM Assets och använda en enda basmall för att enkelt skapa flera personaliserade utskriftsupplevelser. Ni kan skapa olika typer av marknadsföringsmaterial, som broschyrer, flygblad, vykort, visitkort och så vidare, för att på ett enkelt sätt förmedla ert marknadsföringsbudskap till kunderna. Du kan också montera flersidiga utskrifter från befintliga eller nya utskrifter. Framför allt kan ni enkelt leverera både digitala och tryckta upplevelser samtidigt för att skapa en enhetlig, integrerad upplevelse för användarna.

Resursmallar är mestadels InDesign-filer, men kompetensen i InDesign är inte något hinder för att skapa stellära artefakter. Du behöver inte mappa fälten i din InDesign-mall till de produktfält som du annars behöver när du skapar kataloger. Du kan redigera mallarna i WYSIWYG-läge direkt i webbgränssnittet. För att InDesign ska kunna bearbeta dina redigeringsändringar måste du först konfigurera AEM Assets så att det integreras med InDesign-servern.

Möjligheten att redigera InDesign-mallar från webbgränssnittet bidrar till ett bättre samarbete mellan kreatörer och marknadsförare, samtidigt som time to market för lokala marknadsföringssatsningar minskar.

Du kan göra följande med resursmallar:

* Ändra redigerbara mallfält från webbgränssnittet
* Styr den grundläggande formateringen av text, t.ex. teckenstorlek, stil och typ på taggnivå
* Ändra bilder i mallen med hjälp av innehållsväljaren
* Förhandsgranska malländringar
* Sammanfoga flera mallfiler för att skapa en flersidig artefakt

När du väljer en mall för materialet skapar AEM Assets en kopia av mallen som du kan redigera. Den ursprungliga mallen bevaras, vilket säkerställer att den globala signaturen förblir intakt och kan återanvändas för att stärka varumärkets enhetlighet.

Du kan exportera den uppdaterade filen i den överordnade mappen i följande format:

* INDD
* PDF
* JPG

Du kan även hämta utdata i dessa format till ditt lokala system.

## Skapa en säkerhet {#creating-a-collateral}

Tänk dig ett scenario där du vill skapa digital tryckbar information som broschyrer, flygblad och annonser för en kommande kampanj och dela med butiker globalt. Genom att skapa material som bygger på en mall kan ni leverera en enhetlig kundupplevelse över alla kanaler. Designers kan skapa kampanjmallar (en eller flera sidor) med hjälp av en kreativ lösning som InDesign och överföra mallarna till AEM Assets åt dig. Innan du skapar en säkerhet måste du ha en eller flera INDD-mallar överförda till och tillgängliga i Experience Manager i förväg.

1. Klicka på eller tryck på AEM logotyp och sedan på/på **[!UICONTROL Assets]** på navigeringssidan.
1. Välj **[!UICONTROL Templates]** bland alternativen.

   ![chlimage_1-306](assets/chlimage_1-306.png)

1. Klicka/tryck på **[!UICONTROL Create]** och välj sedan den information du vill skapa på menyn. Välj till exempel **[!UICONTROL Brochure]**.

   ![chlimage_1-307](assets/chlimage_1-307.png)

1. ha en eller flera INDD-mallar överförda till och tillgängliga i Experience Manager i förväg. Välj en mall för din broschyr och klicka/tryck på **[!UICONTROL Next]**.

   ![chlimage_1-308](assets/chlimage_1-308.png)

1. Ange ett namn och en valfri beskrivning för broschyren.

   ![chlimage_1-309](assets/chlimage_1-309.png)

1. (Valfritt) Klicka/tryck på ikonen **[!UICONTROL Tags]** bredvid fältet **[!UICONTROL Tags]** och välj en eller flera taggar för broschyren. Klicka/tryck på **[!UICONTROL Confirm]** för att bekräfta ditt val.

   ![chlimage_1-310](assets/chlimage_1-310.png)

1. Klicka på **[!UICONTROL Create]**. En dialogruta bekräftar att en ny broschyr har skapats. Klicka/tryck på **[!UICONTROL Open]** för att öppna broschyren i redigeringsläge.

   ![chlimage_1-311](assets/chlimage_1-311.png)

   Du kan också stänga dialogrutan och navigera till mappen på mallsidan som du började med för att visa den broschyr du skapade. Typen av säkerhet visas på miniatyrbilden i kortvyn. I det här fallet visas t.ex. Broschyr på miniatyrbilden.

   ![chlimage_1-312](assets/chlimage_1-312.png)

## Redigera en säkerhet {#editing-a-collateral}

Du kan redigera en sammanställning direkt när du har skapat den. Du kan även öppna den från mallsidan eller resurssidan.

1. Gör något av följande om du vill öppna materialet för redigering:

   * Öppna den säkerhet (broschyr i det här fallet) som du skapade i steg 7 av [Skapa en säkerhet](asset-templates.md#creating-a-collateral).
   * Navigera från sidan Mallar till en mapp där du har skapat materialet och klicka/tryck på snabbåtgärden Redigera på miniatyrbilden av ett material.
   * Klicka på/tryck på ikonen Redigera i verktygsfältet på resurssidan för den aktuella resursen.
   * Markera den önskade delen och klicka/tryck på ikonen Redigera i verktygsfältet.

   ![chlimage_1-313](assets/chlimage_1-313.png)

   Resurssökaren och textredigeraren visas till vänster på sidan. Textredigeraren är öppen som standard.

   Du kan använda textredigeraren för att ändra texten som ska visas i textfältet. Du kan ändra teckenstorlek, stil, färg och typ på taggnivå.

   Med hjälp av objektsökaren kan du söka efter eller söka efter bilder i AEM Assets och ersätta de redigerbara bilderna i mallen med de bilder du väljer.

   ![chlimage_1-314](assets/chlimage_1-314.png)

   De redigerbara visas till höger. För att ett fält ska kunna redigeras i AEM Assets måste motsvarande fält i mallen taggas i InDesign. Med andra ord bör de göras redigerbara i InDesign.

   ![chlimage_1-315](assets/chlimage_1-315.png)

   >[!NOTE]
   >
   >Se till att din AEM är integrerad med en InDesign-server så att AEM Assets kan extrahera data från InDesign-mallen och göra den tillgänglig för redigering. Mer information finns i [Integrera AEM Assets med InDesign Server](indesign.md).

1. Om du vill ändra texten i ett redigerbart fält klickar/trycker du på textfältet i listan med redigerbara fält och redigerar texten i fältet.

   ![chlimage_1-316](assets/chlimage_1-316.png)

   Du kan redigera textegenskaperna, till exempel teckensnittsstil, färg och storlek, med de alternativ som finns.

1. Klicka/tryck på ikonen **[!UICONTROL Preview]** för att förhandsgranska textändringarna.

   ![chlimage_1-317](assets/chlimage_1-317.png)

1. Klicka/tryck på ikonen **[!UICONTROL Asset Finder]** om du vill byta ut en bild.

   ![chlimage_1-318](assets/chlimage_1-318.png)

1. Markera bildfältet i listan med redigerbara fält och dra sedan en önskad bild från resursväljaren till det redigerbara fältet.

   ![chlimage_1-319](assets/chlimage_1-319.png)

   Du kan också söka efter bilder med nyckelord, taggar och baserat på deras publiceringsstatus. Du kan bläddra i AEM Assets-databasen och navigera till den önskade bildens plats.

   ![chlimage_1-320](assets/chlimage_1-320.png)

1. Klicka/tryck på ikonen **[!UICONTROL Preview]** för att förhandsgranska bilden.

   ![chlimage_1-321](assets/chlimage_1-321.png)

1. Om du vill redigera en viss sida i en flersidig säkerhetssida använder du sidnavigeraren längst ned.

   ![chlimage_1-322](assets/chlimage_1-322.png)

1. Klicka/tryck på ikonen **[!UICONTROL Preview]** i verktygsfältet för att förhandsgranska alla ändringar. Klicka/tryck på **[!UICONTROL Done]** om du vill spara redigeringsändringarna för den aktuella informationen.

   >[!NOTE]
   >
   >Ikonerna Förhandsvisa och Klar är bara aktiverade när de redigerbara bildfälten i den sammansatta bilden inte har några ikoner som saknas. Om det finns saknade ikoner i din säkerhetsinformation beror det på att AEM inte kan matcha bilderna i InDesign-mallen. Vanligtvis kan AEM inte lösa bilder i följande fall:
   >
   >* Bilder är inte inbäddade i den underliggande InDesign-mallen
   >* Bilderna länkas från det lokala filsystemet

   >
   >Så här aktiverar du AEM att lösa bilder:
   >
   >* Bädda in bilder när du skapar InDesign-mallar (se [Om länkar och inbäddade bilder](https://helpx.adobe.com/indesign/using/graphics-links.html)).
   >* Montera AEM i det lokala filsystemet och mappa sedan saknade ikoner med befintliga AEM.

   >
   >Mer information om hur du arbetar med InDesign-dokument finns i [Bästa metoder för att arbeta med InDesign-dokument i AEM](https://helpx.adobe.com/experience-manager/kb/best-practices-idd-docs-aem.html).

1. Om du vill generera en PDF-återgivning för broschyren väljer du alternativet Acrobat i dialogrutan och klickar sedan på **[!UICONTROL Continue]**.
1. Säkerheten skapas i den mapp du började med. Om du vill visa återgivningarna öppnar du materialet och väljer **[!UICONTROL Renditions]** i listan GlobalNav.

   ![chlimage_1-323](assets/chlimage_1-323.png)

1. Klicka på/tryck på PDF-återgivningen i listan över återgivningar för att hämta PDF-filen. Öppna PDF-filen för att granska materialet.

   ![chlimage_1-324](assets/chlimage_1-324.png)

## Lägg samman säkerhet {#merge-collateral}


1. Klicka eller tryck på **[!UICONTROL Tools > Assets]**.
1. Välj **[!UICONTROL Templates]** bland alternativen.
1. Klicka/tryck på **[!UICONTROL Create]** och välj **[!UICONTROL Merge]** på menyn.

   ![chlimage_1-325](assets/chlimage_1-325.png)

1. Klicka på/tryck på ikonen Sammanfoga på sidan Mallsammanfogning.

   ![chlimage_1-326](assets/chlimage_1-326.png)

1. Navigera till platsen för den säkerhet som du vill sammanfoga, klicka/tryck på miniatyrbilderna för den säkerhet som du vill sammanfoga för att markera dem.

   ![chlimage_1-327](assets/chlimage_1-327.png)

   Du kan till och med söka efter mallar i rutan OmniSearch.

   ![chlimage_1-328](assets/chlimage_1-328.png)

   Du kan bläddra igenom AEM Assets-databasen eller samlingar, navigera till platsen för mallarna och sedan välja dem att sammanfoga.

   ![chlimage_1-329](assets/chlimage_1-329.png)

   Du kan använda olika filter för att söka efter de önskade mallarna. Du kan till exempel söka efter mallar baserat på filtyp eller taggar.

   ![chlimage_1-330](assets/chlimage_1-330.png)

1. Klicka/tryck på **[!UICONTROL Next]** i verktygsfältet.
1. På skärmen **[!UICONTROL Preview & Reorder]** ordnar du om mallarna om det behövs och förhandsgranskar valet av mallar som ska sammanfogas. Klicka/tryck sedan på **[!UICONTROL Next]** från verktygsfältet.

   ![chlimage_1-331](assets/chlimage_1-331.png)

1. Ange ett namn för säkerheten på skärmen Konfigurera mall. Du kan också ange de taggar som du anser lämpliga. Om du vill exportera utdata i PDF-format väljer du alternativet **[!UICONTROL Acrobat (.PDF)]**. Som standard exporteras säkerheten i JPG- och InDesign-format. Klicka/tryck på **[!UICONTROL Change Thumbnail]** om du vill ändra visningsminiatyrbilden för flersidessäkerheten.

   ![chlimage_1-332](assets/chlimage_1-332.png)

1. Klicka/tryck på **[!UICONTROL Save]** och sedan på/på **[!UICONTROL OK]** i dialogrutan för att stänga dialogrutan. Den flersidiga säkerheten skapas i den mapp du började med.

   >[!NOTE]
   >
   >Du kan inte redigera en sammanfogad säkerhet senare eller använda den för att skapa annan säkerhet.

