---
title: Bearbeta material för att genomföra affärsprocesser, utföra revisioner, uppfylla regelkrav och upprätthålla en grundläggande smidighet
description: Resursbearbetning för att konvertera format, skapa renderingar, hantera resurser, validera resurser och köra arbetsflöden.
contentOwner: AG
feature: Workflow,Renditions
role: User,Admin
exl-id: 4fb3d12c-feac-45b9-8d09-3b6995591b3d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1031'
ht-degree: 3%

---

# Bearbeta digitala resurser {#process-assets}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

[!DNL Adobe Experience Manager Assets] gör att du kan arbeta med dina digitala resurser på många olika sätt för att möjliggöra robust materialbearbetning. Du kan använda de tillgängliga processmetoderna eller utöka metoderna för att säkerställa att hela processen slutförs med hjälp av, granskning och regelefterlevnad av, identifiering och distribution av samt grundläggande trygghet i era digitala resurser. Du kan göra allt detta samtidigt som du får önskad skala och anpassning.

## Förstå arbetsflöden {#understand-workflows}

För bearbetning av tillgångar [!DNL Experience Manager] använder arbetsflöden. Arbetsflöden hjälper till att automatisera affärslogiken eller -aktiviteterna. Detaljerade steg för att utföra specifika uppgifter anges som standard och utvecklare kan skapa egna anpassade steg. Dessa steg kan kombineras i en logisk ordning för att skapa arbetsflöden. Ett arbetsflöde kan t.ex. automatiskt lägga till vattenstämpel i överförda bilder baserat på ett visst villkor, t.ex. metadata inbäddade i en bild, mapp som den överförs till, upplösning för bilden osv. Ett annat exempel är ett arbetsflöde som är konfigurerat för vattenstämpelbilder på ett sådant sätt och som samtidigt hanterar flera resurshanteringsbehov, som att lägga till metadata, skapa återgivningar, lägga till smarta taggar för tillgångsidentifiering, publicera i ett datalager, ange behörigheter för användaråtkomst och så vidare.

## Standardarbetsflöden i Experience Manager {#default-workflows}

Som standard bearbetas alla överförda resurser med [!UICONTROL DAM Update Asset] arbetsflöde. Arbetsflödet körs för varje överförd resurs och utför grundläggande resurshanteringsåtgärder som återgivningsgenerering, tillbakaskrivning av metadata, sidextrahering, medieextrahering och omkodning.

Information om de olika arbetsflödesmodellerna som är tillgängliga som standard finns i [!UICONTROL Tools > Workflow > Models] in [!DNL Experience Manager].

![En del av standardarbetsflödet](assets/aem-default-workflows.png)

*Bild: Vissa standardarbetsflöden finns i [!DNL Experience Manager].*

## Tillämpa arbetsflöden på resurser {#applying-workflows-to-assets}

Att använda arbetsflöden på digitala resurser är detsamma som för webbsidor. En fullständig guide om hur du skapar och använder arbetsflöden finns på [starta arbetsflöden](/help/sites-authoring/workflows-participating.md).

Använd arbetsflöden i digitala resurser för att aktivera resursen eller skapa vattenstämplar. Många av arbetsflödena för resurser aktiveras automatiskt. Arbetsflödet som automatiskt skapar en återgivning efter att en bild har redigerats aktiveras till exempel automatiskt.

>[!NOTE]
>
>Om ett arbetsflöde som är tillgängligt i det klassiska användargränssnittet inte är tillgängligt i det Touch-aktiverade användargränssnittet, som [!UICONTROL Request to Activate] och [!UICONTROL Request to Deactivate], se [skapa arbetsflödesmodeller](/help/sites-developing/workflows-models.md#make-workflow-models-available-in-touchui).

## Tillämpa ett arbetsflöde på ett [!DNL Experience Manager] resurs {#apply-a-workflow-to-an-aem-asset}

<!-- 
TBD: Add animated GIF for these steps instead of all these screenshots.
-->

Så här använder du ett arbetsflöde för en resurs:

1. Navigera till platsen för resursen som du vill starta ett arbetsflöde för och klicka på resursen för att öppna resurssidan.

1. Navigera till platsen för resursen som du vill starta ett arbetsflöde för och klicka på resursen för att öppna resurssidan. Välj **[!UICONTROL Timeline]** på menyn för att visa tidslinjen.

   ![tidslinje-2](assets/timeline-2.png)

1. Klicka **[!UICONTROL Actions]** längst ned för att öppna en lista med tillgängliga åtgärder för resursen.

1. Klicka **[!UICONTROL Start Workflow]** från listan.

1. I **[!UICONTROL Start Workflow]** väljer du en arbetsflödesmodell i listan.

   ![chlimage_1-50](assets/chlimage_1-50.png)

1. (Valfritt) Ange en rubrik för arbetsflödet som kan användas som referens för arbetsflödesinstansen.

   ![chlimage_1-51](assets/chlimage_1-51.png)

1. Klicka **[!UICONTROL Start]** och sedan klicka **[!UICONTROL Proceed]** i dialogrutan för att bekräfta. Varje steg i arbetsflödet visas på tidslinjen som en händelse.

   ![chlimage_1-52](assets/chlimage_1-52.png)

## Tillämpa ett arbetsflöde på flera resurser {#applying-a-workflow-to-multiple-assets}

1. I resurskonsolen navigerar du till platsen för de resurser som du vill starta ett arbetsflöde för och väljer resurser. Välj **[!UICONTROL Timeline]** på menyn för att visa tidslinjen.

   ![chlimage_1-136](assets/chlimage_1-136.png)

1. Klicka på **[!UICONTROL Actions]** längst ned.

1. Klicka på **[!UICONTROL Start Workflow]**. I **[!UICONTROL Start Workflow]** väljer du en arbetsflödesmodell i listan.

   ![chlimage_1-138](assets/chlimage_1-138.png)

1. (Valfritt) Ange en rubrik för arbetsflödet som kan användas som referens för arbetsflödesinstansen.

1. Klicka på **[!UICONTROL Start]** och sedan på **[!UICONTROL Confirm]** i dialogrutan. Arbetsflödet körs på alla resurser som du har valt.

## Tillämpa ett arbetsflöde på flera mappar {#applying-a-workflow-to-multiple-folders}

Hur du tillämpar ett arbetsflöde på flera mappar liknar hur du tillämpar ett arbetsflöde på flera resurser. Markera mapparna i resurskonsolen och utför steg 2-7 i proceduren [använda ett arbetsflöde på flera resurser](assets-workflow.md#applying-a-workflow-to-multiple-assets).

## Tillämpa ett arbetsflöde på en samling {#applying-a-workflow-to-a-collection}

Mer information om hur du använder ett arbetsflöde i en samling finns i [använda ett arbetsflöde i en samling](managing-collections-touch-ui.md#running-a-workflow-on-a-collection).

## Starta ett arbetsflöde automatiskt för att bearbeta resurser {#auto-execute-workflow-on-some-assets}

Administratörer kan konfigurera arbetsflödet så att resurser automatiskt körs och bearbetas baserat på fördefinierade villkor. Funktionen är användbar för användare och marknadsförare inom olika branscher, till exempel för att skapa anpassade arbetsflöden för specifika mappar. Anta att alla resurser från en reklambyrås foton kan vara vattenstämplade eller att alla resurser som överförts av en frilansare kan bearbetas för att skapa specifika renderingar.

För en arbetsflödesmodell kan användare skapa en startfil för arbetsflödet som kör den. En arbetsflödesstartsfunktion övervakar ändringar i innehållsdatabasen och kör arbetsflödet när de fördefinierade villkoren är uppfyllda. Administratörer kan ge marknadsförarna åtkomst för att skapa arbetsflödena och konfigurera startprogrammet. Användare kan ändra standardinställningen [!UICONTROL DAM Update Asset] arbetsflöde för att lägga till de extra steg som krävs för att bearbeta specifika resurser. Arbetsflödet körs på alla nyligen överförda resurser. Använd någon av följande metoder för att begränsa utförandet av de extra stegen för specifika resurser:

* Skapa en kopia av [!UICONTROL DAM Update Asset] arbetsflöde och ändra det så att det körs i en viss mapphierarki. Den här metoden är användbar för ett fåtal mappar.
* De extra bearbetningsstegen kan läggas till med en [ELLER dela](/help/sites-developing/workflows-step-ref.md#or-split) enligt villkor som gäller för så många mappar som behövs.

## God praxis och begränsningar {#best-practices-limitations-tips}

* Tänk på dina behov av alla typer av återgivningar när du utformar arbetsflöden. Om du inte förutser att en återgivning behövs i framtiden tar du bort steget när du skapar den från arbetsflödet. Det går inte att ta bort återgivningar gruppvis efteråt. Oönskade återgivningar kan ta upp mycket lagringsutrymme efter långvarig användning av [!DNL Experience Manager]. För enskilda resurser kan du ta bort återgivningar manuellt från användargränssnittet. För flera resurser kan du antingen anpassa [!DNL Experience Manager] om du vill ta bort specifika återgivningar eller ta bort resurserna och överföra dem igen.
* Som standard [!UICONTROL DAM Update Asset] arbetsflödet innehåller några steg för att skapa miniatyrbilder och webbåtergivningar. Om någon standardåtergivning tas bort från arbetsflödet används användargränssnittet i [!DNL Assets] återger inte korrekt.

>[!MORELIKETHIS]
>
>* [Använda och delta i arbetsflöden](/help/sites-authoring/workflows.md)
>* [Skapa arbetsflödesmodeller och utöka arbetsflödesfunktioner](/help/sites-developing/workflows.md)
>* [Metoder som kör arbetsflöden](/help/sites-administering/workflows-starting.md)
>* [Bästa arbetsflöden](/help/sites-developing/workflows-best-practices.md)

