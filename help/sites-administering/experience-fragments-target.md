---
title: Målintegrering med upplevelsefragment
seo-title: Target Integration with Experience Fragments
description: Målintegrering med upplevelsefragment
seo-description: Target Integration with Experience Fragments
uuid: 621f57d4-3b8d-49ea-b193-8530c8fbd74e
contentOwner: carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 6911c8e3-b12c-466e-8255-5dcd09557d35
exl-id: dbde3cb6-4132-4462-bd4c-0e4439110e2e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '683'
ht-degree: 0%

---

# Målintegrering med upplevelsefragment{#target-integration-with-experience-fragments}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!NOTE]
>
>Den här funktionen kräver att [AEM 6.4 Service Pack 2 (6.4.2.0)](/help/release-notes/sp-release-notes.md) eller senare.

Du kan exportera [Upplevelsefragment](/help/sites-authoring/experience-fragments.md), som har skapats i Adobe Experience Manager (AEM), till Adobe Target. De kan sedan användas som erbjudanden i Target-aktiviteter för att testa och personalisera upplevelser i stor skala. Detta gör att du kan kombinera enkelheten och kraften i AEM med de kraftfulla funktionerna för automatiserad intelligens (AI) och maskininlärning (ML) i Target.

## Förutsättningar {#prerequisites}

Du måste utföra olika åtgärder:

1. Ni måste integrera AEM med Target. Se [Integrera med Adobe Target](/help/sites-administering/target.md) för mer information.
1. Experience Fragments exporteras från författarinstansen, så du måste [Konfigurera länkfunktionen](/help/sites-developing/externalizer.md) på författarinstansen för att säkerställa att alla länkar är externaliserade för publiceringsinstansen.

## Lägg till molnkonfigurationen {#add-the-cloud-configuration}

Innan du exporterar ett fragment måste du lägga till **Molnkonfiguration** for **Adobe Target** till fragmentet eller mappen:

1. Navigera till **Upplevelsefragment** konsol.
1. Öppna **Sidegenskaper** för rätt mapp eller fragment.

   >[!NOTE]
   >
   >Om du lägger till molnkonfigurationen i den överordnade Experience Fragment-mappen ärvs konfigurationen av alla underordnade.
   >
   >Om du lägger till molnkonfigurationen i själva Experience Fragment ärvs konfigurationen av alla variationer.

1. Välj **Cloud Services** -fliken.

1. Under **Konfiguration av Cloud Service**, markera **Adobe Target** i listrutan.
1. Under **Adobe Target** väljer du lämplig konfiguration.

1. **Spara och stäng**.

## Exportera ett Experience Fragment till Target {#exporting-an-experience-fragment-to-target}

>[!NOTE]
>
>För medieresurser, till exempel bilder, exporteras bara en referens till Target. Resursen lagras i AEM Assets och levereras från den AEM publiceringsinstansen.
>
>På grund av detta måste Experience Fragment, med alla relaterade resurser, publiceras före export till Target.

Så här exporterar du ett upplevelsefragment från AEM till mål (efter att du har angett molnkonfigurationen):

1. Navigera till Experience Fragment-konsolen.
1. Välj den Experience Fragment som du vill exportera till mål.

   >[!NOTE]
   >
   >Det måste vara en webbvariant för Experience Fragment.

1. Tryck/klicka **Exportera till Adobe Target**.

   >[!NOTE]
   >
   >Om Experience Fragment redan har exporterats väljer du **Uppdatera i Adobe Target**.

1. Tryck/klicka **Exportera utan publicering** eller **Publicera** efter behov.

   >[!NOTE]
   >
   >Om du väljer* Publicera** publiceras upplevelsefragmentet direkt och skickas till Target.

1. Tryck/klicka **OK** i bekräftelsedialogrutan.

   Ditt upplevelsefragment bör nu finnas i Target.

>[!NOTE]
>
>Du kan också exportera från sidredigeraren med jämförbara kommandon i [Sidinformation](/help/sites-authoring/author-environment-tools.md#page-information) -menyn.

## Använda era upplevelsefragment i Target {#using-your-experience-fragments-in-target}

När du har utfört de föregående åtgärderna visas upplevelsefragmentet på sidan Erbjudanden i Target. Ta en titt på [specifik Target-dokumentation](https://experiencecloud.adobe.com/resources/help/en_US/target/target/aem-experience-fragments.html) om du vill veta vad du kan uppnå där.

## Ta bort ett Experience Fragment som redan har exporterats till Target {#deleting-an-experience-fragment-already-exported-to-target}

Om du tar bort ett Experience Fragment som redan har exporterats till Target kan det orsaka problem om fragmentet redan används i ett erbjudande i Target. Om du tar bort fragmentet blir erbjudandet oanvändbart eftersom fragmentinnehållet levereras av AEM.

För att undvika sådana situationer:

* Om Experience Fragment inte används för närvarande i en aktivitet kan AEM användaren ta bort fragmentet utan ett varningsmeddelande.
* Om Experience Fragment används för närvarande av en aktivitet i Target får AEM ett felmeddelande om eventuella konsekvenser som en borttagning av fragmentet kan ha för aktiviteten.

   Felmeddelandet i AEM förhindrar inte användaren från att (tvinga) ta bort Experience Fragment. Om Experience Fragment tas bort:

   * Målerbjudandet med AEM Experience Fragment kan visa oönskat beteende

      * Erbjudandet kommer troligtvis fortfarande att återges eftersom Experience Fragment HTML flyttades till Target
      * Eventuella referenser i Experience Fragment kanske inte fungerar korrekt om refererade resurser också tas bort i AEM.
   * Det är förstås inte möjligt att göra ytterligare ändringar i Experience Fragment eftersom Experience Fragment inte längre finns i AEM.
