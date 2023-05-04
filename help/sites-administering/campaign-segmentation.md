---
title: Konfigurera segmentering
seo-title: Configuring Segmentation
description: Lär dig hur du konfigurerar segmentering för AEM Campaign.
seo-description: Learn how to configure segmentation for AEM Campaign.
uuid: f22e41b6-d9d9-4f18-9925-2d4aebc167b3
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: personalization
content-type: reference
discoiquuid: 49c9c9ab-632a-40f7-8c30-d6a8c0f1b420
exl-id: 92302067-3500-41ca-9855-87f36148bfbc
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1132'
ht-degree: 0%

---

# Konfigurera segmentering{#configuring-segmentation}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>I det här dokumentet beskrivs konfigurationen av segmentering så som den används med klientkontexten. Information om hur du konfigurerar segment med ContextHub med hjälp av pekrörelsegränssnittet finns i [Konfigurera segmentering med ContextHub](/help/sites-administering/segmentation.md).

Segmentering är en viktig faktor när man skapar en kampanj. Se [Segmenteringsordlista](/help/sites-authoring/segmentation-overview.md) för information om hur segmentering fungerar och nyckeltermer.

Beroende på den information du redan har samlat in om webbplatsbesökarna och vilka mål du vill uppnå, måste du definiera de segment och strategier som behövs för målinnehållet.

Dessa segment används sedan för att förse en besökare med specifikt riktat innehåll. Det här innehållet bevaras i [Kampanjer](/help/sites-authoring/personalization.md) på webbplatsen. Teaser pages defined here can be included as teaser paragraphs on any page and define which visitor segment the specialized content is applicable for.

AEM gör det enkelt att skapa och uppdatera segment, teasers och kampanjer. Du kan även verifiera resultatet av dina definitioner.

The **Segmentredigerare** gör att du enkelt kan definiera ett segment:

![segmenteditor-1](assets/segmenteditor-1.png)

Du kan **Redigera** varje segment för att ange **Titel**, **Beskrivning** och **Öka** faktor. Med hjälp av sidbrytaren kan du lägga till **OCH** och **ELLER** behållare för att definiera **Segmentlogik** och lägg sedan till **Segmentegenskaper** för att definiera urvalskriterierna.

## Förstärkningsfaktor {#boost-factor}

Varje segment har en **Öka** parameter som används som viktningsfaktor, ett högre tal anger att segmentet kommer att markeras framför ett segment med ett lägre tal.

* Minsta värde: `0`
* Högsta värde: `1000000`

## Segmentlogik {#segment-logic}

Följande logikbehållare är tillgängliga när de är klara och gör att du kan skapa logiken för ditt segmentval. De kan dras från sidosparken till redigeraren:

<table> 
 <tbody> 
  <tr> 
   <td> AND-behållare<br /> </td> 
   <td> Den booleska operatorn AND.<br /> </td> 
  </tr> 
  <tr> 
   <td> ELLER-behållare<br /> </td> 
   <td> Operatorn boolesk OR.</td> 
  </tr> 
 </tbody> 
</table>

## Segmentegenskaper {#segment-traits}

Följande segmentegenskaper är färdiga att användas: de kan dras från sidosparken till redigeraren:

<table> 
 <tbody> 
  <tr> 
   <td> IP-intervall<br /> </td> 
   <td>Definierar ett intervall med IP-adresser som besökaren kan ha.<br /> </td> 
  </tr> 
  <tr> 
   <td> Sidträffar<br /> </td> 
   <td>Hur ofta sidan har begärts. <br /> </td> 
  </tr> 
  <tr> 
   <td> Sidegenskap<br /> </td> 
   <td>Alla egenskaper för den besökta sidan.<br /> </td> 
  </tr> 
  <tr> 
   <td> Referensnyckelord<br /> </td> 
   <td>Nyckelord som matchar information från den refererande webbplatsen. <br /> </td> 
  </tr> 
  <tr> 
   <td> Skript</td> 
   <td>Javascript-uttryck som ska utvärderas.<br /> </td> 
  </tr> 
  <tr> 
   <td> Segmentreferens <br /> </td> 
   <td>Referens till en annan segmentdefinition.<br /> </td> 
  </tr> 
  <tr> 
   <td> Tag Cloud<br /> </td> 
   <td>Taggar som ska matchas med taggar från besökta sidor.<br /> </td> 
  </tr> 
  <tr> 
   <td> Användarålder<br /> </td> 
   <td>Som hämtat från användarprofilen.<br /> </td> 
  </tr> 
  <tr> 
   <td> Användaregenskap<br /> </td> 
   <td>Annan information som är tillgänglig i användarprofilen. </td> 
  </tr> 
 </tbody> 
</table>

Du kan kombinera dessa egenskaper med hjälp av de booleska operatorerna OR och AND (se [Skapa ett nytt segment](#creating-a-new-segment)) för att definiera det exakta scenariot för markering av det här segmentet.

När hela programsatsen utvärderas till true är det här segmentet löst. Om flera segment är tillämpliga ska **[Öka](/help/sites-administering/campaign-segmentation.md#boost-factor)** Även faktor används.

>[!CAUTION]
>
>Segmentredigeraren söker inte efter några cirkelreferenser. Segment A refererar till exempel till ett annat segment B, som i sin tur refererar till segment A. Du måste se till att dina segment inte innehåller några cirkelreferenser.

>[!NOTE]
>
>Egenskaper med **_i18n** suffixet anges av ett skript som är en del av personaliseringens användargränssnittsklient. Alla användargränssnittsrelaterade klienter läses bara in på författaren eftersom användargränssnittet inte behövs vid publicering.
>
>När du skapar ett segment med sådana egenskaper är det därför normalt nödvändigt att förlita sig på **browserFamily** i stället för **browserFamily_i18n**.

## Skapa ett nytt segment {#creating-a-new-segment}

Så här definierar du det nya segmentet:

1. Välj **Verktyg > Åtgärder > Konfiguration**.
1. Klicka på **Segmentering** till vänster och navigera till önskad plats.
1. Skapa en [ny sida](/help/sites-authoring/managing-pages.md) med **Segment** mall.
1. Öppna den nya sidan och se segmentredigeraren:

   ![screen_shot_2012-02-02at101726am](assets/screen_shot_2012-02-02at101726am.png)

1. Använd antingen sidosparken eller snabbmenyn (oftast högerklickar du med musknappen och väljer sedan **Nytt...** för att öppna fönstret Infoga ny komponent) för att hitta det segment du behöver. Dra den sedan till **Segmentredigerare** kommer det att visas i standardinställningarna **OCH** behållare.
1. Dubbelklicka på den nya egenskapen för att redigera de specifika parametrarna. till exempel musens position:

   ![screen_shot_2012-02-02at103135am-1](assets/screen_shot_2012-02-02at103135am-1.png)

1. Klicka **OK** för att spara definitionen:
1. Du kan **Redigera** segmentdefinitionen för att ge den en **Titel**, **Beskrivning** och **[Öka](/help/sites-administering/campaign-segmentation.md#boost-factor)** faktor:

   ![screen_shot_2012-02-02at103547am](assets/screen_shot_2012-02-02at103547am.png)

1. Lägg till fler egenskaper om det behövs. Du kan formulera booleska uttryck med **AND-behållare** och **ELLER-behållare** komponenter hittades under **Segmentlogik**. Med segmentredigeraren kan du ta bort egenskaper eller behållare som inte längre behövs, eller dra dem till nya positioner i programsatsen.

## Använda OCH- och ELLER-behållare {#using-and-and-or-containers}

Du kan skapa komplexa segment i AEM. Man bör vara medveten om några grundläggande punkter:

* Definitionens översta nivå är alltid den AND-behållare som skapas från början. detta kan inte ändras, men påverkar inte resten av segmentdefinitionen.
* Se till att det är rimligt att kapsla behållaren. Behållarna kan ses som parenteser i ditt booleska uttryck.

Följande exempel används för att välja besökare som antingen är:

Man och mellan 16 och 65 år

ELLER

Kvinnor och mellan 16 och 62 år

Som huvudoperator är OR måste du börja med ett **ELLER-behållare**. Här finns två AND-programsatser för varje programsats som du behöver en **AND-behållare** där du kan lägga till de enskilda egenskaperna.

![screen_shot_2012-02-02at105145am-1](assets/screen_shot_2012-02-02at105145am-1.png)

## Testa tillämpningen av ett segment {#testing-the-application-of-a-segment}

När segmentet är definierat kan man testa potentiella resultat med hjälp av **[Klientkontext](/help/sites-administering/client-context.md)**:

1. Välj det segment som ska testas.
1. Tryck **[Ctrl-Alt-C](/help/sites-authoring/keyboard-shortcuts.md)** för att öppna **[Klientkontext](/help/sites-administering/client-context.md)**, som visar de data som har samlats in. I testsyfte kan du **Redigera** vissa värden, eller **Läs in** en annan profil för att se effekten där.

1. Beroende på vilka egenskaper som har definierats, kanske data som är tillgängliga för den aktuella sidan inte matchar segmentdefinitionen. Status för matchningen visas under definitionen.

En enkel segmentdefinition kan till exempel baseras på användarens ålder och kön. När du läser in en viss profil visas att segmentet har lösts:

![screen_shot_2012-02-02at105926am-1](assets/screen_shot_2012-02-02at105926am-1.png)

Eller inte:

![screen_shot_2012-02-02at110019am-1](assets/screen_shot_2012-02-02at110019am-1.png)

>[!NOTE]
>
>Alla egenskaper åtgärdas omedelbart, men de flesta ändras bara vid sidinläsning. Ändringar av musens position visas omedelbart, vilket är praktiskt vid testning.

Sådana tester kan även utföras på innehållssidor och i kombination med **Teaser** -komponenter.

Om du för musen över ett teaser-stycke visas de segment som används, oavsett om de för närvarande löses och varför den aktuella teaser-instansen har valts:

![chlimage_1-408](assets/chlimage_1-408.png)

## Använda ditt segment {#using-your-segment}

Segment används för närvarande inom [Kampanjer](/help/sites-authoring/personalization.md). De används för att styra det faktiska innehåll som ses av specifika målgrupper. Se [Förstå segment](/help/sites-authoring/segmentation-overview.md) för mer information.
