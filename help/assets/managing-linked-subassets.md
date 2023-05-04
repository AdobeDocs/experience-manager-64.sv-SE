---
title: Hantera sammansatta resurser och generera delresurser.
description: Lär dig hur du skapar referenser till [!DNL Experience Manager] material från InDesign, Adobe Illustrator och Photoshop. Lär dig även hur du använder funktionen för sidvisning för att visa enskilda sidor med flersidiga filer.
contentOwner: AG
feature: Asset Management
role: User,Admin
exl-id: 9fa44b26-76f7-48e2-a9df-4fd1c0074158
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1354'
ht-degree: 0%

---

# Hantera sammansatta resurser med delresurser {#managing-compound-assets}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Assets kan identifiera om en överförd fil innehåller referenser till resurser som redan finns i databasen. Den här funktionen är endast tillgänglig för filformat som stöds. Om den överförda resursen innehåller referenser till [!DNL Experience Manager] resurser skapas en dubbelriktad länk mellan de överförda och refererade resurserna.

Förutom att eliminera redundans, referera [!DNL Experience Manager] resurser i Adobe Creative Cloud-program förbättrar samarbetet och ökar användarnas effektivitet och produktivitet.

[!DNL Experience Manager] Resurserna har stöd för **dubbelriktad referens**. Du kan hitta refererade resurser på sidan med tillgångsinformation i den överförda filen. Dessutom kan du visa de refererande filerna för [!DNL Experience Manager] resurser på sidan med tillgångsinformation för den refererade resursen.

Referenser tolkas utifrån sökväg, dokument-ID och instans-ID för de refererade resurserna.

## Adobe Illustrator: Lägga till resurser som referenser {#refai}

Du kan referera till befintliga [!DNL Experience Manager] resurser från en Adobe Illustrator-fil.

1. Använda [[!DNL Experience Manager] datorprogram](https://helpx.adobe.com/experience-manager/desktop-app/aem-desktop-app.html), montera [!DNL Experience Manager] Resurskatalogen som en enhet på den lokala datorn. Navigera till platsen för resursen som du vill referera till i den monterade enheten.
1. Dra resursen från den monterade enheten till Illustrator-filen.
1. Spara Illustrator-filen på den monterade enheten, eller [ladda upp](managing-assets-touch-ui.md#uploading-assets) till [!DNL Experience Manager] databas.
1. När arbetsflödet är klart går du till sidan med resursinformation för resursen. Referenserna till befintliga [!DNL Experience Manager] tillgångar anges under **[!UICONTROL Dependencies]** i **[!UICONTROL References]** kolumn.

   ![chlimage_1-258](assets/chlimage_1-258.png)

1. De refererade resurserna som visas under **[!UICONTROL Dependencies]** kan också refereras av andra filer än den aktuella. Om du vill visa en lista med refererade filer för en resurs klickar du på resursen i listan under **[!UICONTROL Dependencies]**.

   ![chlimage_1-259](assets/chlimage_1-259.png)

1. Klicka på **[!UICONTROL View Properties]** -ikonen i verktygsfältet. På egenskapssidan visas listan med filer som refererar till den aktuella resursen under **[!UICONTROL References]** kolumn i **[!UICONTROL Basic]** -fliken.

   ![chlimage_1-260](assets/chlimage_1-260.png)

## Adobe InDesign: Lägga till resurser som referenser {#add-aem-assets-as-references-in-adobe-indesign}

Till referens [!DNL Experience Manager] resurser från en InDesign-fil, antingen dra [!DNL Experience Manager] till filen InDesign eller exportera InDesign som en ZIP-fil.

Refererade resurser finns redan i [!DNL Experience Manager] Resurser. Du kan extrahera delresurser med [konfigurera InDesign-server](indesign.md). Inbäddade resurser i en InDesign-fil extraheras som delresurser.

>[!NOTE]
>
>Om InDesign-servern är proxibel bäddas förhandsvisningen in i InDesign-filernas XMP metadata. I det här fallet krävs inte extrahering av miniatyrer uttryckligen. Om InDesign-servern inte är proxyserver måste miniatyrbilder extraheras explicit för InDesign-filer.

När en INDD-fil överförs hämtas referenserna genom att resurser som har `xmpMM:InstanceID` och `xmpMM:DocumentID` i databasen.

### Skapa referenser genom att dra resurser {#create-references-by-dragging-aem-assets}

Den här proceduren liknar [Lägga till resurser som referenser i Adobe Illustrator](#refai).

### Skapa referenser till resurser genom att exportera en ZIP-fil {#create-references-to-aem-assets-by-exporting-a-zip-file}

1. Utför stegen i [Skapa arbetsflödesmodeller](/help/sites-developing/workflows-models.md) för att skapa ett nytt arbetsflöde.
1. Använd [Paketfunktioner i Adobe InDesign](https://helpx.adobe.com/indesign/how-to/indesign-package-files-for-handoff.html) för att exportera dokumentet. Adobe InDesign kan exportera ett dokument och de länkade resurserna som ett paket. I det här fallet innehåller den exporterade mappen en `Links` mapp som innehåller delresurser i filen InDesign. The `Links` finns i samma mapp som INDD-filen.
1. Skapa en ZIP-fil och överför den till [!DNL Experience Manager] databas.
1. Starta arbetsflödet för Unarchiver.
1. När arbetsflödet är klart refereras referenserna i mappen Länkar automatiskt till underresurser. Om du vill visa en lista över refererade resurser går du till sidan med tillgångsinformation för InDesign-resursen och stänger [Rail](/help/sites-authoring/basic-handling.md#rail-selector).

## Adobe Photoshop: Lägga till resurser som referenser {#refps}

1. Montera med en WebDav-klient [!DNL Experience Manager] Resurser som en enhet.
1. Skapa referenser till [!DNL Experience Manager] resurser i en Photoshop-fil navigerar till motsvarande resurser på den monterade enheten med hjälp av funktionen Montera länkad i Photoshop.

   ![chlimage_1-261](assets/chlimage_1-261.png)

1. Spara i Photoshop-fil till monterad enhet eller [ladda upp](managing-assets-touch-ui.md#uploading-assets) till [!DNL Experience Manager] databas.
1. När arbetsflödet är klart refererar referenserna till befintliga [!DNL Experience Manager] resurser visas på sidan med tillgångsinformation.

   Om du vill visa de refererade resurserna stänger du [Rail](/help/sites-authoring/basic-handling.md#rail-selector) på sidan med tillgångsinformation.

1. De refererade resurserna innehåller även en lista med resurser som de refereras till från. Om du vill visa en lista med refererade resurser går du till sidan med tillgångsinformation och stänger dialogrutan [järnväg](/help/sites-authoring/basic-handling.md#rail-selector).

>[!NOTE]
>
>Resurserna i sammansatta resurser kan också refereras baserat på deras dokument-ID och instans-ID. Den här funktionaliteten finns endast i Adobe Illustrator- och Adobe Photoshop-versionerna. För andra görs en referens på grundval av den relativa sökvägen för länkade tillgångar i den huvudsakliga sammansatta tillgången, som i tidigare versioner av AEM.

## Skapa delresurser {#generate-subassets}

För resurser som stöds i flersidiga format - PDF-filer, AI-filer, Microsoft PowerPoint- och Apple Keynote-filer samt Adobe InDesign-filer - [!DNL Experience Manager] kan generera delresurser som motsvarar varje enskild sida i den ursprungliga tillgången. Dessa delresurser är länkade till *parent* och underlätta flersidig visning. I alla andra syften behandlas deltillgångarna som normala tillgångar i AEM.

Generering av delresurser är inaktiverat som standard. Så här aktiverar du generering av delresurser:

1. Logga in i Experience Manager som administratör. Öppna **[!UICONTROL Tools > Workflow > Models]**.
1. Välj **[!UICONTROL DAM Update Asset]** arbetsflöde och klicka **[!UICONTROL Edit]**.
1. Klicka **[!UICONTROL Toggle Side Panel]** och hitta **[!UICONTROL Create Sub Asset]** steg. Lägg till steget i arbetsflödet. Klicka på **[!UICONTROL Sync]**.

Gör något av följande om du vill generera delresurserna:

* Nya resurser: The [!UICONTROL DAM Update Assets] arbetsflödet körs på alla nya resurser som överförs till AEM. Delresurser genereras automatiskt för nya flersidiga resurser.
* Befintliga flersidiga resurser: Kör [!UICONTROL DAM Update Assets] arbetsflöde som följer något av stegen:

   * Markera en resurs och klicka på [!UICONTROL Timeline] för att öppna den vänstra panelen. Du kan även använda kortkommandot `alt + 3`. Klicka [!UICONTROL Start Workflow], markera [!UICONTROL DAM Update Asset], klicka [!UICONTROL Start]och klicka [!UICONTROL Proceed].
   * Markera en resurs och klicka på [!UICONTROL Create > Workflow] i verktygsfältet. I popup-dialogrutan väljer du [!UICONTROL DAM Update Asset] arbetsflöde, klicka [!UICONTROL Start]och klicka [!UICONTROL Proceed].

För Microsoft Word-dokument gäller följande: **[!UICONTROL DAM Parse Word Documents]** arbetsflöde. Det genererar en `cq:Page` från innehållet i Microsoft Word-dokumentet. De bilder som extraheras från dokumentet refereras från `cq:Page` -komponenten. Dessa bilder extraheras även om generering av delresurser är inaktiverat.

## Visa delresurser {#viewing-subassets}

Delresurserna visas bara om delresurserna genereras och är tillgängliga för den valda flersidiga resursen. Om du vill visa de genererade delresurserna öppnar du flersidesresursen. Klicka på i det övre vänstra området på sidan ![Ikon för vänster räl](assets/do-not-localize/aem_leftrail_contentonly.png) och klicka **[!UICONTROL Subassets]** från listan. När du väljer **[!UICONTROL Subassets]** från listan. Du kan även använda kortkommandot `alt + 5`.

![Visa delresurser för en flersidig resurs](assets/view_subassets_simulation.gif)

## Visa sidor i en flersidig fil {#view-pages-of-a-multi-page-file}

Du kan visa en flersidig fil, t.ex. PDF, INDD, PPT, PPTX och AI, med hjälp av sidvisningsprogrammet i [!DNL Experience Manager] Resurser. Öppna en flersidig resurs och klicka på **[!UICONTROL View Pages]** från det övre vänstra hörnet på sidan. Sidvisningsprogrammet som öppnas visar sidorna för resursen och kontrollerna för att bläddra igenom och zooma varje sida.

![Visa och visa sidor för en flersidig resurs](assets/view_multipage_asset_fmr.gif)

För InDesign kan du extrahera sidor med hjälp av InDesign-servern. Om förhandsgranskningarna av sidorna sparas när du skapar InDesign-filer behövs inte InDesign Server för sidextraheringen.

Följande alternativ är tillgängliga i verktygsfältet, i den vänstra listen och i kontrollerna i sidvisningsprogrammet:

* **[!UICONTROL Desktop Actions]** för att öppna eller visa en viss underresurs med [!DNL Experience Manager] datorprogram. Se hur man [konfigurera skrivbordsåtgärder](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html#desktopactions-v2) om du använder [!DNL Experience Manager] datorprogram.

* **[!UICONTROL Properties]** öppnar [!UICONTROL Properties] sidan för den specifika underresursen.

* **[!UICONTROL Annotate]** kan du göra anteckningar i den specifika underresursen. De anteckningar du använder på separata underresurser samlas in och visas tillsammans när den överordnade resursen öppnas för visning.

* **[!UICONTROL Page Overview]** visar alla delresurser samtidigt.

* **[!UICONTROL Timeline]** från vänster ratt efter klickning ![Ikon för vänster räl](assets/do-not-localize/aem_leftrail_contentonly.png) visar filens aktivitetsström.

## God praxis och begränsning {#best-practice-limitation-tips}

* Generering av delresurser kan vara mycket resurskrävande för alla Experience Manager-distributioner. Om du genererar delresurser när komplexa resurser överförs lägger du till steget i arbetsflödet DAM-uppdatering av resurser. Om du genererar delresurser on demand skapar du ett separat arbetsflöde för att generera delresurser. Med ett dedikerat arbetsflöde kan du hoppa över de andra stegen i arbetsflödet för DAM-uppdatering av resurser och spara beräkningsresurser.

>[!MORELIKETHIS]
>
>* [Använd Adobe Experience Manager datorprogram](https://experienceleague.adobe.com/docs/experience-manager-desktop-app/using/using.html)

