---
title: Hantera resurssamlingar
description: Lär dig mer om hur du hanterar samlingar med resurser, som att skapa, visa, ta bort, redigera och hämta samlingar.
contentOwner: AG
mini-toc-levels: 1
feature: Collections
role: User
exl-id: cadfc569-5725-4012-9f73-864243ba7743
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '2211'
ht-degree: 13%

---

# Hantera samlingar {#managing-collections}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

En samling är en uppsättning resurser i Adobe Experience Manager Assets. Använd samlingar för att dela resurser mellan användare. Uppsättningen kan vara en statisk samling eller en dynamisk samling som baseras på sökresultat.

Till skillnad från mappar kan en samling innehålla resurser från olika platser. Du kan dela samlingar med olika användare som har olika behörighetsnivåer, t.ex. visning, redigering och så vidare.

Du kan dela flera samlingar med en användare. Varje samling innehåller referenser till resurser. Resursernas referensintegritet bevaras i alla samlingar.

Samlingar är av följande typer, baserat på det sätt som de samlar resurser på:

* En samling som innehåller en statisk referenslista med resurser, mappar och andra samlingar.
* En smart samling som dynamiskt inkluderar resurser baserat på sökvillkor.

## Åtkomst till samlingskonsolen {#navigating-the-collections-console}

Öppna **[!UICONTROL Collections]**, tryck eller klicka på Experience Manager-logotypen. Gå till **[!UICONTROL Assets]** > **[!UICONTROL Collections]**.

## Skapa en samling {#creating-a-collection}

Du kan skapa en samling med [statiska referenser](#creating-a-collection-with-static-references) eller baserat på en [sökkriteriebaserat filter](#creating-a-smart-collection). Du kan också skapa en samling från en ljuslåda.

### Skapa en samling med statiska referenser {#creating-a-collection-with-static-references}

Du kan skapa en samling med statiska referenser, t.ex. en samling med referenser till resurser, mappar, samlingar, snurrsuppsättningar och bilduppsättningar.

1. Navigera till **[!UICONTROL Collections]** konsol.
1. Tryck/klicka i verktygsfältet **[!UICONTROL Create]**.
1. I **[!UICONTROL Create Collection]** anger du en rubrik och en valfri beskrivning för samlingen.
1. Lägg till medlemmar i samlingen och tilldela lämpliga behörigheter. Du kan också välja **[!UICONTROL Public Collection]** om du vill tillåta alla användare att komma åt samlingen.

   >[!NOTE]
   >
   >Om du vill att medlemmarna ska kunna dela samlingar med andra användare anger du `dam-users` gruppera läsbehörigheter i sökvägen `home/users`. Ge behörighet till användarna på `/content/dam/collections` plats där användarna kan visa samlingar i popup-listor. Du kan även göra användaren till en del av `dam-users` grupp.

1. (Valfritt) Lägg till en miniatyrbild för samlingen.
1. Tryck/klicka på **[!UICONTROL Create]** och tryck/klicka sedan på **[!UICONTROL OK]** för att stänga dialogrutan. En samling med den angivna titeln och de angivna egenskaperna öppnas i konsolen Samlingar.

   >[!NOTE]
   >
   >Med Experience Manager Assets kan du skapa granskningsåtgärder för en samling som liknar hur du skapar granskningsåtgärder för en resursmapp.

   Om du vill lägga till resurser i samlingen går du till användargränssnittet Resurser. Mer information finns i [Lägga till resurser i en samling](/help/assets/managing-collections-touch-ui.md#adding-assets-to-a-collection).

### Skapa samlingar med dropzone {#create-collections-using-dropzone}

Du kan dra resurser från resursgränssnittet till en samling. Du kan också skapa en kopia av en samling och dra resurserna dit.

1. I resursgränssnittet väljer du de resurser som du vill lägga till i en samling.
1. Dra resurserna till **[!UICONTROL Drop in Collection]** zon.

   ![drop_in_collection](assets/drop_in_collection.png)

   Släpp musknappen när Dropzone aktiveras och etiketten ändras till **[!UICONTROL Drop to Add]**.

   ![drop_to_add](assets/drop_to_add.png)

   Du kan också trycka/klicka på **[!UICONTROL To Collection]** -ikonen i verktygsfältet.

   ![chlimage_1-109](assets/chlimage_1-109.png)

1. På sidan **[!UICONTROL Add To Collection]** trycker/klickar du på ikonen **[!UICONTROL Create Collection]** i verktygsfältet.

   Om du vill lägga till resurserna i en befintlig samling markerar du den på sidan och trycker/klickar på **[!UICONTROL Add]**. Som standard väljs den senast uppdaterade samlingen.

1. Ange ett namn för samlingen i dialogrutan **[!UICONTROL Create New Collection]**. Om du vill att samlingen ska vara tillgänglig för alla användare väljer du **[!UICONTROL Public Collection]**.
1. Tryck/klicka **[!UICONTROL Continue]** för att skapa samlingen.

### Skapa en smart samling {#creating-a-smart-collection}

En smart samling använder ett sökvillkor för att dynamiskt fylla i resurser. Du kan skapa en smart samling med enbart filer och inte med mappar eller filer och mappar.

Så här skapar du en smart samling:

1. Navigera till användargränssnittet Resurser och tryck/klicka på sökikonen.

1. Ange sökordet i rutan Omnissearch och tryck på Retur. Öppna filterpanelen och använd ett sökfilter.

1. Från **[!UICONTROL Files & Folders]** lista, välj **[!UICONTROL Files]**.

   ![files_option](assets/files_option.png)

1. Tryck/klicka på **[!UICONTROL Save Smart Collection]**.
1. Ange ett namn för samlingen. Välj **[!UICONTROL Public]** om du vill lägga till gruppen DAM-användare med rollen Viewer i den smarta samlingen.

   ![save_collection](assets/save_collection.png)

   >[!NOTE]
   >
   >Om du väljer **[!UICONTROL Public]** blir den smarta samlingen tillgänglig för alla med ägarrollen när du har skapat den. Om du avmarkerar **[!UICONTROL Public]** -alternativet är DAM-användargruppen inte längre kopplad till den smarta samlingen.

1. Tryck/klicka på **[!UICONTROL Save]** för att skapa den smarta samlingen och stäng sedan meddelanderutan för att slutföra processen.

   Den nya smarta samlingen läggs också till i **[!UICONTROL Saved Searches]** lista.

   ![collection_listing](assets/collection_listing.png)

   Etiketten på knappen **[!UICONTROL Create Smart Selection]** ändras till **[!UICONTROL Edit Smart Selection]**. Om du vill redigera inställningarna för den smarta samlingen väljer du **[!UICONTROL Files]** i listan **[!UICONTROL Files & Folders]**. Tryck/klicka sedan på knappen **[!UICONTROL Edit Smart Selection]**.

   ![chlimage_1-112](assets/chlimage_1-112.png)

## Lägga till resurser i en samling {#adding-assets-to-a-collection}

Du kan lägga till resurser i en samling som innehåller en lista med refererade resurser eller mappar. Smarta samlingar använder en sökfråga för att fylla i resurser. Statiska referenser till resurser och mappar kan därför inte användas för dem.

1. I Assets-användargränssnittet markerar du resursen och trycker/klickar på **[!UICONTROL To Collection]** -ikonen i verktygsfältet.

   ![chlimage_1-113](assets/chlimage_1-113.png)

   Du kan också dra resursen till **[!UICONTROL Drop in Collection]** -området i gränssnittet. Lägg till resurserna när regionens etikett ändras till **[!UICONTROL Drop to Add]**.

1. I **[!UICONTROL Add To Collection]** väljer du den samling som du vill lägga till resursen i.

1. Tryck/klicka **[!UICONTROL Add]** och stäng sedan bekräftelsemeddelandet. Resursen läggs till i samlingen.

## Redigera en smart samling {#editing-a-smart-collection}

Smarta samlingar byggs genom att en sökning sparas så att du kan ändra deras innehåll genom att ändra sökparametrarna för [sparad sökning](#editing-saved-searches).

1. I resursanvändargränssnittet: tryck/klicka på sökikonen i verktygsfältet.

   ![chlimage_1-114](assets/chlimage_1-114.png)

1. Tryck på returtangenten när markören är i Omnissearch-rutan.

1. Tryck/klicka på ikonen GlobalNav för att visa panelen Filter.

1. Välj den smarta samling du vill ändra i listan **[!UICONTROL Saved Searches]**. På sökpanelen visas de filter som har konfigurerats för den sparade sökningen.

   ![select_smart_collection](assets/select_smart_collection.png)

1. Från **[!UICONTROL Files & Folders]** lista, välj **[!UICONTROL Files]**.

1. Ändra ett eller flera filter efter behov. Tryck/klicka på **[!UICONTROL Edit Smart Collection]**.

   Du kan också redigera namnet på den smarta samlingen.

   ![edit_smart_collection,dialog](assets/edit_smart_collectiondialog.png)

1. Tryck/klicka på **[!UICONTROL Save]**. The **[!UICONTROL Edit Smart Collection]** visas.

1. Tryck/klicka **[!UICONTROL Overwrite]** om du vill ersätta den ursprungliga smarta samlingen med den redigerade samlingen. Du kan också välja **[!UICONTROL Save As]** om du vill spara den redigerade samlingen separat.

1. I bekräftelsedialogrutan: tryck/klicka **[!UICONTROL Save]** för att slutföra processen.

## Visa och redigera samlingsmetadata {#viewing-and-editing-collection-metadata}

Samlingsmetadata omfattar data om samlingen, inklusive taggar som läggs till.

1. Välj en samling i konsolen Samlingar och tryck/klicka på **[!UICONTROL Properties]** -ikonen i verktygsfältet.
1. I **[!UICONTROL Collection Metadata]** sidan, visa samlingsmetadata från **[!UICONTROL Basic]** och **[!UICONTROL Advanced]** -tabbar.
1. Ändra metadata efter behov och tryck/klicka sedan på **[!UICONTROL Save & Close]** i verktygsfältet för att spara ändringarna.

### Redigera metadata för flera samlingar samtidigt {#editing-collection-metadata-in-bulk}

Du kan redigera metadata för flera samlingar samtidigt. Med den här funktionen kan du snabbt replikera vanliga metadata i flera samlingar.

1. I konsolen Samlingar väljer du två eller flera samlingar som du vill redigera metadata för.
1. Tryck/klicka i verktygsfältet **[!UICONTROL Properties]**.
1. På sidan **[!UICONTROL Collection Metadata]** redigerar du metadata på flikarna **[!UICONTROL Basic]** och **[!UICONTROL Advanced]** efter behov.
1. Om du vill visa metadataegenskaperna för en viss samling avmarkerar du de återstående samlingarna i samlingslistan. Metadataredigeringsfälten fylls i med metadata för den aktuella samlingen.

   >[!NOTE]
   >
   >* På sidan med samlingsegenskaper kan du ta bort samlingar från listan med samlingar genom att avmarkera dem. I samlingslistan är alla samlingar markerade som standard. Metadata för samlingar som du tar bort uppdateras inte.
   >* Överst i listan markerar du kryssrutan nära **[!UICONTROL Title]** för att växla mellan att markera samlingarna och rensa listan.


1. Tryck/klicka **[!UICONTROL Save & Close]** i verktygsfältet och stäng sedan bekräftelsedialogrutan för att slutföra processen.
1. Om du vill lägga till nya metadata till de befintliga metadata väljer du **[!UICONTROL Append mode]**. Om du inte markerar det här alternativet ersätter de nya metadata de data som finns i fälten. Tryck/klicka på **[!UICONTROL Submit]**.

   >[!NOTE]
   >
   >De metadata som du lägger till för de valda samlingarna skriver över tidigare metadata för dessa samlingar. Använd [!UICONTROL Append mode] om du vill lägga till nya värden till befintliga metadata i fälten som kan innehålla flera värden. Enkelvärdesfält skrivs alltid över. Alla taggar som du lägger till i [!UICONTROL Tags] läggs till i den befintliga listan med taggar i metadata.

Anpassa metadata [!UICONTROL Properties] använder du schemaredigeraren för att lägga till, ändra och ta bort metadataegenskaper.

>[!TIP]
>
>Massredigeringsmetoden fungerar för resurser som är tillgängliga i en samling. För resurser som är tillgängliga i olika mappar eller som matchar ett gemensamt villkor är det möjligt att uppdatera metadata i grupp efter att ha sökt i dessa resurser.

## Sök i samlingar {#searching-collections}

Du kan söka efter samlingar från samlingskonsolen. När du söker med nyckelord i sökrutan [!DNL Experience Manager] Resurserna söker efter samlingsnamn, metadata och de taggar som har lagts till i samlingarna.

Om du söker efter samlingar från den översta nivån returneras bara enskilda samlingar i sökresultaten. Resurser eller mappar i samlingarna exkluderas. I alla andra fall (till exempel i en enskild samling eller i en mapphierarki) returneras alla relevanta resurser, mappar och samlingar.

## Sök i samlingar {#searching-within-collections}

Tryck/klicka på en samling i Samlingar-konsolen för att öppna den.

I en samling är sökningen begränsad till resurser (och deras taggar och metadata) i den samling som du visar. När du söker i en mapp returneras alla matchande resurser och underordnade mappar i den aktuella mappen. När du söker i en samling returneras endast matchande resurser, mappar och andra samlingar som är direktmedlemmar i samlingen.

## Redigera samlingsinställningar {#editing-collection-settings}

Du kan redigera samlingsinställningar, till exempel rubrik och beskrivning, eller lägga till medlemmar i en samling.

1. Välj en samling och tryck/klicka på **[!UICONTROL Settings]** i verktygsfältet. Du kan även använda **[!UICONTROL Settings]** snabbåtgärd från samlingsminiatyrbilden.
1. Ändra inställningarna för samlingen på sidan **[!UICONTROL Collection Settings]**. Du kan till exempel ändra samlingens rubrik, beskrivningar, medlemmar och behörigheter enligt [Lägga till samlingar](#creating-a-collection).

1. Spara ändringarna genom att trycka/klicka **[!UICONTROL Save]**.

## Ta bort en samling {#deleting-a-collection}

1. Välj en eller flera samlingar i konsolen Samlingar och tryck/klicka på ikonen Ta bort i verktygsfältet.

1. Tryck/klicka i dialogrutan **[!UICONTROL Delete]** för att bekräfta borttagningsåtgärden.

   >[!NOTE]
   >
   >Du kan även ta bort smarta samlingar genom att [ta bort sparade sökningar](#deleting-saved-searches).

## Hämta en samling {#downloading-a-collection}

När du hämtar en samling hämtas hela resurshierarkin i samlingen, inklusive mappar och underordnade samlingar.

1. Välj en eller flera samlingar som du vill hämta från samlingskonsolen.
1. Tryck/klicka på nedladdningsikonen i verktygsfältet.
1. I **[!UICONTROL Download]** dialogruta, trycka/klicka **[!UICONTROL Download]**. Om du vill hämta återgivningarna av resurserna i samlingen väljer du **[!UICONTROL Renditions]**. Välj **[!UICONTROL Email]** möjlighet att skicka ett e-postmeddelande till samlingens ägare.

   När du väljer en samling som ska hämtas hämtas hela mapphierarkin under samlingen. Om du vill inkludera varje samling som du hämtar (inklusive resurser i underordnade samlingar som är kapslade under den överordnade samlingen) i en enskild mapp väljer du **[!UICONTROL Create separate folder for each asset]**.

## Skapa kapslade samlingar {#creating-nested-collections}

Du kan lägga till en samling i en annan samling och på så sätt skapa en kapslad samling.

1. Välj önskad samling eller grupp med samlingar i konsolen Samlingar och tryck eller klicka på **[!UICONTROL To Collection]** i verktygsfältet.

   ![chlimage_1-117](assets/chlimage_1-117.png)

1. Från **[!UICONTROL Add To Collection]** väljer du i vilken samling samlingen ska läggas till.

   >[!NOTE]
   >
   >Den senast uppdaterade samlingen väljs som standard i **[!UICONTROL Add To Collection]** sida.

1. Tryck/klicka på **[!UICONTROL Add]**. Ett meddelande bekräftar att samlingen har lagts till i målsamlingen i **[!UICONTROL Select Destination]** sida. Stäng meddelandet för att slutföra processen.

>[!NOTE]
>
>Smarta samlingar kan inte kapslas. Smarta samlingar kan alltså inte innehålla andra samlingar.

## Sparade sökningar {#saved-searches}

I Assets-gränssnittet kan du söka efter eller filtrera resurser baserat på vissa regler, sökvillkor eller anpassade sökfasetter. Om du sparar dem som **[!UICONTROL Saved Searches]** kan du komma åt dem senare från listan **[!UICONTROL Saved Searches]** på panelen Filter. När du skapar en sparad sökning skapas även en smart samling.

![saved_searches_list](assets/saved_searches_list.png)

### Skapa sparade sökningar {#creating-saved-searches}

Sparade sökningar skapas när du skapar en smart samling. Smarta samlingar läggs automatiskt till i listan **[!UICONTROL Saved Searches]**. Frågan om sparade sökningar för samlingen sparas i `dam:query` egenskapen i crxed vid den relativa platsen `/content/dam/collections/`. Det finns inga begränsningar för de sökningar som du kan spara och för de sparade sökningarna som visas i listan.

>[!NOTE]
>
>Du kan dela smarta samlingar på samma sätt som du delar statiska samlingar.

### Redigera sparade sökningar {#editing-saved-searches}

Att redigera sparade sökningar är detsamma som att redigera smarta samlingar. Mer information finns i [Redigera en smart samling](/help/assets/managing-collections-touch-ui.md#editing-a-smart-collection).

### Ta bort sparade sökningar {#deleting-saved-searches}

1. I resursanvändargränssnittet: tryck/klicka på sökikonen i verktygsfältet.

   ![chlimage_1-118](assets/chlimage_1-118.png)

1. Tryck på Retur när markören är i omsökningsfältet.

1. Klicka på eller tryck på ikonen GlobalNav för att visa filterpanelen.

1. Från **[!UICONTROL Saved Searches]** klickar du på ikonen Ta bort bredvid den smarta samling som du vill ta bort.

   ![select_smart_collection-1](assets/select_smart_collection-1.png)

1. Tryck/klicka i dialogrutan **[!UICONTROL Delete]** om du vill ta bort den sparade sökningen.

## Köra ett arbetsflöde i en samling {#running-a-workflow-on-a-collection}

Du kan köra ett arbetsflöde för resurserna i en samling. Om samlingen innehåller kapslade samlingar körs arbetsflödet även på resurserna i de kapslade samlingarna. Om samlingen och den kapslade samlingen innehåller duplicerade resurser körs arbetsflödet bara en gång för sådana resurser.

1. Välj en samling som du vill köra ett arbetsflöde för i samlingskonsolen.
1. Tryck/klicka på ikonen GlobalNav och välj **[!UICONTROL Timeline]** från listan.
1. Klicka eller tryck på ikonen för cirkumflex längst ned på tidslinjen och tryck/klicka sedan på **[!UICONTROL Start Workflow]**.

   ![chlimage_1-119](assets/chlimage_1-119.png)

1. I **[!UICONTROL Start Workflow]** väljer du en arbetsflödesmodell i listan. Välj till exempel **[!UICONTROL DAM Update Asset]** modell.
1. Ange en titel för arbetsflödet och tryck/klicka **[!UICONTROL Start]**.
1. Tryck/klicka i dialogrutan **[!UICONTROL Proceed]**. Arbetsflödet körs på alla resurser i samlingen.

>[!MORELIKETHIS]
>
>* [Konfigurera e-postmeddelanden från Experience Manager Assets](/help/sites-administering/notification.md#assetsconfig)
>* [Skapa en granskningsuppgift för samlingar](bulk-approval.md)

