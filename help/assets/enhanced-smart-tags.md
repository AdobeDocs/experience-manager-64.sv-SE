---
title: Förbättrade smarta taggar
description: Förbättrade smarta taggar
uuid: 4452ca05-1f20-4f80-884a-a739ae7b8b0e
contentOwner: AG
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
discoiquuid: c1b52aac-1eaf-4cfa-801f-77aeca0d90ea
feature: Smart Tags,Search
role: User
exl-id: 21a9f130-ea91-45bf-adc8-8a73a2a00c77
source-git-commit: cc9b6d147a93688e5f96620d50f8fc8b002e2d0d
workflow-type: tm+mt
source-wordcount: '1451'
ht-degree: 16%

---

# Förbättrade smarta taggar {#enhanced-smart-tags}

## Översikt över förbättrade smarta taggar {#overview-of-enhanced-smart-tags}

Organisationer som hanterar digitalt material använder i allt högre grad taxonomistyrd vokabulär i metadata. Det innehåller i själva verket en lista med nyckelord som anställda, partners och kunder vanligtvis använder för att referera till och söka efter digitala resurser i en viss klass. Genom att tagga resurser med taxonomistyrd vokabulär kan de enkelt identifieras och hämtas med taggbaserade sökningar.

Jämfört med naturtrogna språkordlistor kan taggning av digitala resurser baserat på företagsklonomi hjälpa dem att anpassa sig till företagets verksamhet och säkerställa att de mest relevanta resurserna visas i sökningar.

En biltillverkare kan t.ex. märka bilderna med modellnamn så att endast relevanta bilder visas när bilder av olika modeller söks igenom för att utforma en kampanj.

För att Smart Content Service ska kunna använda rätt taggar måste du utbilda den så att den känner igen din taxonomi. För att utbilda tjänsten måste du först strukturera en uppsättning resurser och taggar som bäst beskriver dessa resurser. Använd dessa taggar på materialet och kör ett utbildningsarbetsflöde för att hjälpa tjänsten att lära sig.

När en tagg har tränats och är klar kan tjänsten nu använda dessa taggar på resurser via ett taggningsarbetsflöde.

I bakgrunden använder smarta innehållstjänster Adobe Sensei AI-ramverket för att utbilda sin bildigenkänningsalgoritm i din taggstruktur och i din affärsklonomi. Den här innehållsintelligensen används sedan för att tillämpa relevanta taggar på en annan uppsättning resurser.

Smart Content Service är en molntjänst som finns på [!DNL Adobe I/O]. Om du vill använda den i Adobe Experience Manager måste systemadministratören integrera din [!DNL Experience Manager]-instans med [!DNL Adobe I/O].

Här är sammanfattningsvis de viktigaste stegen för att använda tjänsten Smart Content:

* Onboarding
* Granska resurser och taggar (taxonomidefinition)
* Utbilda Smart Content Service
* Automatisk taggning

![flödesdiagram](assets/flowchart.gif)

## Förutsättningar {#prerequisites}

Innan du kan använda Smart Content Service måste du ha/se till/göra följande för att kunna integrera med [!DNL Adobe I/O]:

* Ett Adobe ID-konto som har administratörsbehörighet för organisationen.
* Att Smart Content Service är aktiverad för din organisation.

## Onboarding {#onboarding}

Tjänsten Smart Content Service kan köpas som tillägg till [!DNL Experience Manager]. När du har köpt funktionen skickas ett e-postmeddelande till administratören för organisationen med en länk till [!DNL Adobe I/O].

Administratören kan följa länken för att integrera tjänsten för smart innehåll med [!DNL Experience Manager]. Information om hur du integrerar tjänsten med [!DNL Experience Manager] Resurser finns i [Konfigurera smarta taggar](config-smart-tagging.md).

Startprocessen är klar när administratören konfigurerar tjänsten och lägger till användare i [!DNL Experience Manager].

## Granska resurser och taggar {#reviewing-assets-and-tags}

När du har anslutit dig är det första du vill göra att identifiera en uppsättning taggar som bäst beskriver de här bilderna i ditt företags sammanhang.

Granska sedan bilderna för att identifiera en uppsättning bilder som bäst motsvarar din produkt för ett visst affärsbehov. Kontrollera att resurserna i din aktuella uppsättning uppfyller [riktlinjerna för utbildning i smarta innehållstjänster](smart-tags-training-guidelines.md).

Lägg till resurserna i en mapp och använd taggarna på varje resurs från egenskapssidan. Kör sedan utbildningsarbetsflödet i den här mappen. Den välstrukturerade uppsättningen resurser gör det möjligt för Smart Content Service att effektivt utbilda fler resurser med hjälp av dina taxonomidefinitioner.

>[!NOTE]
>
>1. Utbildning är en oåterkallelig process. Adobe rekommenderar att du granskar taggarna i den välstrukturerade resursuppsättningen innan du utbildar Smart Content Service på taggarna.
>1. Läs [Riktlinjer för utbildning i smarta innehållstjänster](smart-tags-training-guidelines.md) innan du påbörjar utbildning för en tagg.
>1. När du utbildar Smart Content Service för första gången rekommenderar Adobe att du utbildar den på minst två distinkta taggar.

>


## Utbilda Smart Content Service {#training-the-smart-content-service}

För att Smart Content Service ska känna igen din företagsklonomi kan du köra den på en uppsättning resurser som redan innehåller taggar som är relevanta för ditt företag. Efter utbildning kan tjänsten tillämpa samma taxonomi på liknande resurser.

Du kan utbilda tjänsten flera gånger för att förbättra dess förmåga att använda relevanta taggar. Efter varje utbildningscykel kör du ett taggningsarbetsflöde och kontrollerar om dina resurser är taggade på rätt sätt.

Du kan utbilda Smart Content Service regelbundet eller efter behov.

>[!NOTE]
>
>Utbildningsarbetsflödet kan endast användas på mappar.

### Periodisk utbildning {#periodic-training}

Du kan aktivera tjänsten Smart Content Service för att med jämna mellanrum utbilda resurser och tillhörande taggar i en mapp. Öppna egenskapssidan för resursmappen, välj **[!UICONTROL Enable Smart Tags]** under fliken **[!UICONTROL Details]** och spara ändringarna.

![enable_smart_tags](assets/enable_smart_tags.png)

När det här alternativet har valts för en mapp kör [!DNL Experience Manager] ett utbildningsarbetsflöde automatiskt för att utbilda Smart Content Service i mappresurserna och deras taggar. Som standard körs utbildningsarbetsflödet varje vecka kl. 12.30 på lördagar.

### On-demand-utbildning {#on-demand-training}

Du kan utbilda tjänsten för smart innehåll när det behövs från arbetsflödeskonsolen.

1. Tryck/klicka på logotypen [!DNL Experience Manager] och gå till **[!UICONTROL Tools > Workflow > Models]**.
1. På sidan **[!UICONTROL Workflow Models]** väljer du arbetsflödet **[!UICONTROL Smart Tags Training]** och trycker/klickar sedan på **[!UICONTROL Start Workflow]** i verktygsfältet.
1. I dialogrutan **[!UICONTROL Run Workflow]** bläddrar du till nyttolastmappen som innehåller de taggade resurserna för att utbilda tjänsten.
1. Ange en rubrik för arbetsflödet och lägg till en kommentar. Tryck/klicka sedan på **[!UICONTROL Run]**. Resurserna och taggarna skickas in för utbildning.

   ![workflow_dialog](assets/workflow_dialog.png)

>[!NOTE]
>
>När materialet i en mapp har behandlats för utbildning behandlas endast de ändrade resurserna i efterföljande utbildningscykler.

### Visa utbildningsrapporter {#viewing-training-reports}

Om du vill kontrollera om Smart Content Service är utbildad i dina taggar i övningsresurserna kan du läsa rapporten om utbildningsarbetsflödet i rapportkonsolen.

1. Tryck/klicka på logotypen [!DNL Experience Manager] och gå till **[!UICONTROL Tools > Assets > Reports]**.
1. På sidan **[!UICONTROL Asset Reports]** trycker/klickar du på **[!UICONTROL Create]**.
1. Markera rapporten **[!UICONTROL Smart Tags Training]** och tryck/klicka sedan på **[!UICONTROL Next]** i verktygsfältet.
1. Ange en titel och beskrivning för rapporten. Under **[!UICONTROL Schedule Report]** låter du alternativet **[!UICONTROL Now]** vara markerat. Om du vill schemalägga rapporten till ett senare tillfälle väljer du **[!UICONTROL Later]** och anger ett datum och en tid. Tryck/klicka sedan på **[!UICONTROL Create]** i verktygsfältet.
1. På sidan **[!UICONTROL Asset Reports]** markerar du rapporten som du skapat. Visa rapporten genom att trycka/klicka på ikonen **[!UICONTROL View]** i verktygsfältet.
1. Granska informationen i rapporten.

   Rapporten visar träningsstatusen för de taggar du har tränat. Den gröna färgen i kolumnen **[!UICONTROL Training Status]** anger att smarta innehållstjänster har tränats för taggen. Gul färg anger att tjänsten inte är helt tränad för en viss tagg. I det här fallet lägger du till fler bilder med just den taggen och kör träningsarbetsflödet för att träna tjänsten helt för taggen.

   Om du inte ser dina taggar i den här rapporten kör du utbildningsarbetsflödet igen för dessa taggar.

1. Om du vill hämta rapporten markerar du den i listan och trycker/klickar på ikonen **[!UICONTROL Download]** i verktygsfältet. Rapporten hämtas som en Excel-fil.

## Tagga resurser automatiskt {#tagging-assets-automatically}

När du har utbildat tjänsten Smart Content kan du utlösa taggningsarbetsflödet för att automatiskt tillämpa lämpliga taggar på en annan uppsättning med liknande resurser.

Du kan köra taggningsarbetsflödet periodiskt eller när det behövs.

>[!NOTE]
>
>Arbetsflödet för taggning körs både på resurser och mappar.

### Periodisk taggning {#periodic-tagging}

Du kan aktivera tjänsten Smart Content Service för att regelbundet tagga resurser i en mapp. Öppna egenskapssidan för resursmappen, välj **[!UICONTROL Enable Smart Tags]** under fliken **[!UICONTROL Details]** och spara ändringarna.

När det här alternativet har valts för en mapp taggar tjänsten Smart Content Service automatiskt resurserna i mappen. Som standard körs taggningsarbetsflödet varje dag kl. 12.00.

### On-demand-taggning {#on-demand-tagging}

Du kan aktivera taggningsarbetsflödet från följande för att tagga dina resurser direkt:

* Arbetsflödeskonsol
* Tidslinje

>[!NOTE]
>
>Om du kör taggningsarbetsflödet från tidslinjen kan du använda taggar på högst 15 resurser i taget.

#### Tagga resurser från arbetsflödeskonsolen {#tagging-assets-from-the-workflow-console}

1. Tryck/klicka på logotypen [!DNL Experience Manager] och gå till **[!UICONTROL Tools > Workflow > Models]**.
1. På sidan **[!UICONTROL Workflow Models]** väljer du arbetsflödet **[!UICONTROL DAM Smart Tags Assets]** och trycker/klickar sedan på **[!UICONTROL Start Workflow]** i verktygsfältet.

   ![dam_smart_tag_workflow](assets/dam_smart_tag_workflow.png)

1. I dialogrutan **[!UICONTROL Run Workflow]** bläddrar du till nyttolastmappen som innehåller resurser som du vill använda dina taggar på automatiskt.
1. Ange en rubrik för arbetsflödet och en valfri kommentar. Tryck/klicka sedan på **[!UICONTROL Run]**.

   ![tagging_dialog](assets/tagging_dialog.png)

   Navigera till resursmappen och granska taggarna för att kontrollera om Smart Content Service taggade dina resurser på rätt sätt. Mer information finns i [Hantera smarta taggar](managing-smart-tags.md).

#### Tagga resurser från tidslinjen {#tagging-assets-from-the-timeline}

1. I Assets-användargränssnittet väljer du den mapp som innehåller resurser eller specifika resurser som du vill använda smarta taggar på.
1. Tryck/klicka på ikonen GlobalNav och öppna tidslinjen.
1. Tryck/klicka på pilen längst ned och tryck/klicka sedan på **[!UICONTROL Start Workflow]**.

   ![start_workflow](assets/start_workflow.png)

1. Välj arbetsflödet **[!UICONTROL DAM Smart Tag Assets]** och ange en rubrik för arbetsflödet.
1. Tryck/klicka på **[!UICONTROL Start]**. Arbetsflödet använder dina taggar på resurser. Navigera till resursmappen och granska taggarna för att kontrollera om Smart Content Service taggade dina resurser på rätt sätt. Mer information finns i [Hantera smarta taggar](managing-smart-tags.md).

>[!NOTE]
>
>I de efterföljande taggningscyklerna är det bara de ändrade resurserna som taggas igen med nyligen tränade taggar.
>
>Även oförändrade resurser taggas om mellanrummet mellan den sista och den aktuella taggningscykeln för taggningsarbetsflödet överstiger 24 timmar.
>
>För periodiska taggningsarbetsflöden taggas oförändrade resurser när mellanrummet överskrider sex månader.
