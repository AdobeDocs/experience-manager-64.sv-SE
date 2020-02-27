---
title: Målintegrering med upplevelsefragment
seo-title: Målintegrering med upplevelsefragment
description: Målintegrering med upplevelsefragment
seo-description: Målintegrering med upplevelsefragment
uuid: 621f57d4-3b8d-49ea-b193-8530c8fbd74e
contentOwner: carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 6911c8e3-b12c-466e-8255-5dcd09557d35
translation-type: tm+mt
source-git-commit: 4e5d3c0ae71f601bcf39fa768c8b5ac86decc1eb

---


# Målintegrering med upplevelsefragment{#target-integration-with-experience-fragments}

>[!NOTE]
>
>Den här funktionen kräver att [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) eller senare används.

Du kan exportera [Experience Fragments](/help/sites-authoring/experience-fragments.md), som har skapats i Adobe Experience Manager (AEM), till Adobe Target. De kan sedan användas som erbjudanden i Target-aktiviteter för att testa och personalisera upplevelser i stor skala. På så sätt kan du kombinera enkelheten och kraften i AEM med de kraftfulla funktionerna för automatiserad intelligens (AI) och maskininlärning (ML) i Target.

## Förutsättningar {#prerequisites}

Du måste utföra olika åtgärder:

1. Ni måste integrera AEM med Target. Mer information finns i [Integrera med Adobe Target](/help/sites-administering/target.md) .
1. Experience Fragments exporteras från författarinstansen, så du måste [konfigurera länkfunktionen](/help/sites-developing/externalizer.md) i författarinstansen för att se till att eventuella länkar är externaliserade för publiceringsinstansen.

## Lägg till molnkonfigurationen {#add-the-cloud-configuration}

Innan du exporterar ett fragment måste du lägga till **molnkonfigurationen** för **Adobe Target** i fragmentet eller mappen:

1. Gå till konsolen **Experience Fragments** .
1. Öppna **Sidegenskaper** för rätt mapp eller fragment.

   >[!NOTE]
   >
   >Om du lägger till molnkonfigurationen i den överordnade Experience Fragment-mappen ärvs konfigurationen av alla underordnade.
   >
   >Om du lägger till molnkonfigurationen i själva Experience Fragment ärvs konfigurationen av alla variationer.

1. Välj fliken **Molntjänster** .

1. Välj **Adobe Target** i listrutan under Konfiguration **av** molntjänster.
1. Välj lämplig konfiguration under **Adobe Target**.

1. **Spara och stäng**.

## Exportera ett Experience Fragment till Target {#exporting-an-experience-fragment-to-target}

>[!NOTE]
>
>För medieresurser, till exempel bilder, exporteras bara en referens till Target. Resursen lagras i AEM Resurser och levereras från AEM-publiceringsinstansen.
>
>På grund av detta måste Experience Fragment, med alla relaterade resurser, publiceras före export till Target.

Så här exporterar du ett upplevelsefragment från AEM till Target (efter att du har angett molnkonfigurationen):

1. Navigera till Experience Fragment-konsolen.
1. Välj den Experience Fragment som du vill exportera till mål.

   >[!NOTE]
   >
   >Det måste vara en webbvariant för Experience Fragment.

1. Tryck/klicka på **Exportera till Adobe Target**.

   >[!NOTE]
   >
   >Om Experience Fragment redan har exporterats väljer du **Uppdatera i Adobe Target**.

1. Tryck/klicka på **Exportera utan publicering** eller **Publicera** efter behov.

   >[!NOTE]
   >
   >Om du väljer* Publicera** publiceras upplevelsefragmentet direkt och skickas till Target.

1. Tryck/klicka på **OK** i bekräftelsedialogrutan.

   Ditt upplevelsefragment bör nu finnas i Target.

>[!NOTE]
>
>Du kan också exportera från sidredigeraren med hjälp av jämförbara kommandon på menyn [Sidinformation](/help/sites-authoring/author-environment-tools.md#page-information) .

## Använda era upplevelsefragment i Target {#using-your-experience-fragments-in-target}

När du har utfört de föregående åtgärderna visas upplevelsefragmentet på sidan Erbjudanden i Target. Ta en titt på den [specifika Target-dokumentationen](https://experiencecloud.adobe.com/resources/help/en_US/target/target/aem-experience-fragments.html) och lär dig mer om vad du kan uppnå där.

## Ta bort ett Experience Fragment som redan har exporterats till Target {#deleting-an-experience-fragment-already-exported-to-target}

Om du tar bort ett Experience Fragment som redan har exporterats till Target kan det orsaka problem om fragmentet redan används i ett erbjudande i Target. Om du tar bort fragmentet blir erbjudandet oanvändbart eftersom fragmentinnehållet levereras av AEM.

För att undvika sådana situationer:

* Om Experience Fragment inte används för närvarande i en aktivitet kan användaren ta bort fragmentet utan ett varningsmeddelande.
* Om Experience Fragment används av en aktivitet i Target får AEM-användaren ett felmeddelande om eventuella konsekvenser som en borttagning av fragmentet kan ha för aktiviteten.

   Felmeddelandet i AEM förhindrar inte användaren från att (tvinga) ta bort Experience Fragment. Om Experience Fragment tas bort:

   * Target-erbjudandet med AEM Experience Fragment kan visa oönskat beteende

      * Erbjudandet kommer troligtvis fortfarande att återges eftersom Experience Fragment HTML överfördes till Target
      * Eventuella referenser i Experience Fragment kanske inte fungerar korrekt om refererade resurser även har tagits bort i AEM.
   * Det är förstås inte möjligt att göra ytterligare ändringar i Experience Fragment eftersom Experience Fragment inte längre finns i AEM.


