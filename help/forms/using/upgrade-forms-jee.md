---
title: Uppgradera till AEM 6.4 Forms
seo-title: Uppgradera till AEM 6.4 Forms
description: 'Du kan uppgradera direkt från AEM 6.1 Forms, AEM 6.2 Forms och LiveCycle ES4 SP1 till AEM 6.3 Forms. '
seo-description: 'Du kan uppgradera direkt från AEM 6.1 Forms, AEM 6.2 Forms och LiveCycle ES4 SP1 till AEM 6.3 Forms. '
uuid: 1435246a-9215-4d88-b52c-59a5c329bb77
content-type: reference
products: SG_EXPERIENCEMANAGER/6.3/FORMS
topic-tags: installing
geptopics: SG_AEMFORMS/categories/jee
discoiquuid: e745033f-8015-4fae-9d82-99d35802c0a6
translation-type: tm+mt
source-git-commit: ffa45c8fa98e1ebadd656ea58e4657b669ddd830
workflow-type: tm+mt
source-wordcount: '1678'
ht-degree: 0%

---


# Uppgradera till AEM 6.4 Forms på JEE {#upgrade-to-aem-forms-jee}

Använd någon av följande uppgraderingsvägar, beroende på vad som passar din miljö.

## AEM 6.2 Forms on JEE eller AEM 6.3 Forms on JEE > AEM 6.4 Forms on JEE {#aem-forms-jee-62-63-to-64}

Gör så här för att uppgradera befintliga AEM 6.2 Forms på JEE eller AEM 6.3 Forms på JEE till AEM 6.4 Forms på JEE:

1. Ladda ned installationsprogrammet för AEM 6.4 Forms på JEE från [Adobe Licensing Website (LWS)](https://licensing.adobe.com/). Du behöver ett giltigt Maintenance &amp; Support-avtal för att ladda ned installationsprogrammet.
1. Läs [Upgrade checklist and planning](https://www.adobe.com/go/learn_aemfroms_upgrade_checklist_63) om du vill veta mer om vilka kontroller som utförs för att säkerställa en lyckad uppgradering.
1. Se [Förbered dig på att uppgradera till AEM Forms](https://www.adobe.com/go/learn_aemforms_prepareupgrade_63) för att lära dig mer och utföra de uppgifter som säkerställer att uppgraderingen körs korrekt med minimal serverdriftstopp.
1. Beroende på din befintliga miljö och programserver väljer du något av följande dokument och följer instruktionerna.

   * [Uppgradera från AEM 6.2 eller AEM 6.3 Forms till AEM 6.4 Forms for JBoss](assets/upgrade-jboss.pdf)
   * [Uppgradera från AEM 6.2 eller AEM 6.3 Forms till AEM 6.4 Forms för WebLogic](assets/upgrade-weblogic.pdf)
   * [Uppgradera från AEM 6.2 eller AEM 6.3 Forms till AEM 6.4 Forms för WebSphere](assets/upgrade-websphere.pdf)
   * [Uppgradera från AEM 6.2 eller AEM 6.3 Forms till AEM 6.4 Forms for JBoss Turnkey](assets/upgrade-turnkey.pdf)

## AEM 6.0 Forms on JEE > AEM 6.3 Forms on JEE {#aem-forms-jee-60-to-63}

Direktuppgradering från LiveCycle ES2, LiveCycle ES3, AEM 6.0 Forms, AEM 6.1 Forms till AEM 6.4 Forms är inte tillgängligt. Du kan uppgradera till en eller flera versioner av LiveCycle eller AEM Forms och sedan uppgradera från AEM 6.4 Forms. En lista över mellanliggande versioner och motsvarande uppgraderingsinstruktioner finns i [Välj en uppgraderingssökväg](upgrade.md).

## LiveCycle ES4 SP1 > AEM 6.4 Forms på JEE {#livecycle-es4sp1-forms-jee}

Uppgradering av LiveCycle ES4 SP1 till AEM 6.4 Forms på JEE är en uppgradering som inte är på plats, eftersom det handlar om att migrera resurser och data från tidigare versioner till nya instanser (nya versioner) av programservrar, operativsystem och databaser som stöds.

Här följer en översikt över hur du uppgraderar en befintlig LiveCycle ES4 SP1-server till AEM 6.4 Forms. Detaljerade instruktioner finns i dokumenten som listas i slutet av proceduren.

1. Innan du uppgraderar:

   1. Ladda ned installationsprogrammet för AEM 6.4 Forms på JEE från [Adobe Licensing Website (LWS)](https://licensing.adobe.com/). Du behöver ett giltigt Maintenance &amp; Support-avtal för att ladda ned installationsprogrammet.
   1. Bestäm vilken typ av innehållsdatabas (CRX Repository) som ska användas. Endast ett fåtal AEM Forms-funktioner för JEE använder Content Repository-beständighet för att lagra innehåll och resurser. Installera och konfigurera Content Repository endast om du tänker använda sådana AEM Forms på JEE-funktioner:

      * I LiveCycle ES4 SP1 använder funktionerna Korrespondenshantering, Forms Portal, HTML Workspace och Process Reporting Content Repository. Om du inte har använt dessa funktioner i LiveCycle ES4 och inte tänker använda dessa funktioner i AEM Forms behövs inte Content Repository.
      * I AEM Forms, Adaptive Forms, Correspondence Management, HTML5 Forms (Known as Mobile Forms in LiveCycle ES4 SP1), Forms Portal, HTML Workspace, Process Reporting, Forms centric workflows on OSGi, används Content Repository. Om du tänker använda AEM Forms för dessa funktioner krävs Content Repository.
      * Du behöver inte Innehållsdatabas för AEM Forms Document Security.

      Dessutom är databastypen för LiveCycle och AEM Forms olika. Tillgängliga databastyper och relaterad information finns i [Välja en beständig typ för en AEM Forms-installation](/help/forms/using/choosing-persistence-type-for-aem-forms.md).

   1. Skapa en säkerhetskopia av innehåll och data för LiveCycle ES4 SP1:

      Skapa en säkerhetskopia av LiveCycle ES4 SP1-databasen, GDS (Global Data Storage) och crx-databasen (krävs inte för dokumentsäkerhet). Om du uppgraderar till MongoMK eller RDBMK persistence exporterar du LiveCycle ES4 SP1-resurser för korrespondenshantering i en .cmp-fil och skapar resurser som ett AEM.

   1. Kontrollera att din befintliga plattform (dvs. programserver, databas, operativsystem, Adobe Acrobat, tredjepartsprogram och maskinvara) stöds för AEM 6.4 Forms på JEE. Mer information om vilken maskin- och programvara som stöds finns i [dokumentet om plattformskombinationer som stöds](/help/forms/using/aem-forms-jee-supported-platforms.md).

      Om du skapar en ny instans av databasen importerar du de data som säkerhetskopierades i steg 3 till databasen. Mer information om hur du importerar data till en databas finns i dokumentationen för motsvarande databasleverantör.

      >[!NOTE]
      >
      >Om du använder ett beständigt RDBMK-format ska du använda en databas för både beständighet och dokumenttjänster som körs på AEM Forms på JEE.


1. Uppgradera:

   1. Installera AEM 6.4 Forms på JEE på en ny server genom att köra installationsprogrammet. Installationsprogrammet placerar alla filer som behövs på datorn i en installationskatalogstruktur.
   1. När installationen är klar kör du **Configuration Manager** för att konfigurera olika AEM Forms-moduler och ange lämpliga konfigurationer. Förutom att konfigurera inställningar kan du ange sökvägen till GDS (Global Data Storage) och crx-databasen.

      >[!NOTE]
      >
      >Välj alternativet **[!UICONTROL Upgrade from Adobe Experience Manager Forms 6.2.0]** på skärmen Uppgradera aktivitetsval. Med alternativet **[!UICONTROL Upgrade from Adobe Experience Manager Forms 6.2.0]** kan konfigurationshanteraren uppgradera från LiveCycle ES4 SP1 till AEM 6.4 Forms.

   1. (Krävs inte för AEM Forms dokumentsäkerhetsmodul) Importera innehåll till innehållslagringsplatsen (CRX-Repository) till Forms 6.4-AEM.

      >[!NOTE]
      >
      >* När crx-databasen har uppgraderats och innehållet har migrerats ändrar du lösenordet för administratörskontot. Detaljerade instruktioner finns i [Ändra lösenordet för en befintlig användare](/help/sites-administering/granite-user-group-admin.md).


1. Utför uppgifterna efter distributionen för att verifiera inloggningsuppgifter, konfigurera dokumenttjänster, korrespondenshantering, dokumentsäkerhet med mera beroende på ditt användningssätt.
1. Kontrollera att servern har uppgraderats:

   Utför några rutinåtgärder på den uppgraderade AEM Forms-servern för att säkerställa att servern uppgraderas. Du kan fylla i och skicka in några migrerade formulär eller skydda dokument för att säkerställa en lyckad uppgradering.

   >[!NOTE]
   >
   >I AEM 6.4 Forms har strukturen för crx-database ändrats. När du har uppgraderat till AEM 6.4-formulär kan du använda de ändrade sökvägarna för anpassning som du skapar på nytt. En fullständig lista över ändrade sökvägar finns i [Omstrukturering av Forms-databaser i AEM 6.4](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md).

**Beroende på din befintliga miljö och programserver väljer du ett av följande dokument och följer instruktionerna:**

* [Uppgradera från LiveCycle ES4 SP1 till AEM 6.4 Forms för JBoss](assets/upgrade-jboss-livecycle.pdf)
* [Uppgradera från LiveCycle ES4 SP1 till AEM 6.4 Forms för WebLogic](assets/upgrade-weblogic-livecycle.pdf)
* [Uppgradera från LiveCycle ES4 SP1 till AEM 6.4 Forms for WebSphere](assets/upgrade-websphere-livecycle.pdf)
* [Uppgradera från LiveCycle ES4 SP1 till AEM 6.4 Forms med JBoss Turnkey](assets/upgrade-turnkey-livecycle.pdf)

<!--Theses sections used to be an accordion until converted to straight Markdown. When accordions are enabled, revert-->

## LiveCycle ES3 > AEM 6.4 Forms on JEE {#livecycle-es3-forms-jee}

Uppgradering av LiveCycle ES3 till AEM 6.4 Forms på JEE är en uppgradering som inte är på plats, eftersom det handlar om att migrera resurser och data från tidigare versioner till nya instanser (nya versioner) av programservrar, operativsystem och databaser som stöds.

Här följer en översikt över hur du uppgraderar en befintlig LiveCycle ES3-server till AEM 6.4 Forms. Detaljerade instruktioner finns i dokumenten som listas i slutet av proceduren.

1. Innan du uppgraderar:

   1. Ladda ned installationsprogrammet för AEM 6.4 Forms på JEE från [Adobe Licensing Website (LWS)](https://licensing.adobe.com/). Du behöver ett giltigt Maintenance &amp; Support-avtal för att ladda ned installationsprogrammet.
   1. Bestäm vilken typ av innehållsdatabas (CRX Repository) som ska användas. Endast ett fåtal AEM Forms-funktioner för JEE använder Content Repository-beständighet för att lagra innehåll och resurser. Installera och konfigurera Content Repository endast om du tänker använda sådana AEM Forms på JEE-funktioner:

      * I AEM Forms används Content Repository för arbetsflöden för adaptiv Forms, Correspondence Management, HTML5 Forms, Forms Portal, HTML Workspace, Process Reporting och Forms-baserade arbetsflöden i OSGi. Om du tänker använda AEM Forms för dessa funktioner krävs Content Repository.
      * Du behöver inte Innehållsdatabas för AEM Forms Document Security.

      Dessutom är databastypen för LiveCycle och AEM Forms olika. Tillgängliga databastyper och relaterad information finns i [Välja en beständig typ för en AEM Forms-installation](/help/forms/using/choosing-persistence-type-for-aem-forms.md).

   1. Skapa en säkerhetskopia av LiveCycle ES3-databasen, GDS (Global Data Storage) och Content Repository (krävs inte för dokumentsäkerhet). Om du uppgraderar till MongoMK eller RDBMK persistence exporterar du LiveCycle ES3-resurser för korrespondenshantering som arkiv.
   1. Kontrollera att din befintliga plattform (dvs. programserver, databas, operativsystem, Adobe Acrobat, tredjepartsprogram och maskinvara) stöds för AEM 6.4 Forms på JEE. Mer information om vilken maskin- och programvara som stöds finns i [dokumentet om plattformskombinationer som stöds](/help/forms/using/aem-forms-jee-supported-platforms.md).

      Om du skapar en ny instans av databasen importerar du de data som säkerhetskopierades i steg 3 till databasen. Mer information om hur du importerar data till en databas finns i dokumentationen för motsvarande databasleverantör.

      >[!NOTE]
      >
      >Om du använder ett beständigt RDBMK-format kan du använda en databas för både beständighet och dokumenttjänster som körs på AEM Forms på JEE.


1. Uppgradera:

   1. Installera AEM 6.4 Forms på JEE på en ny server genom att köra installationsprogrammet. Installationsprogrammet placerar alla filer som behövs på datorn i en installationskatalogstruktur.
   1. När installationen är klar kör du **Configuration Manager** för att konfigurera olika AEM Forms-moduler och ange lämpliga konfigurationer. Förutom att konfigurera inställningar kan du ange sökvägen till GDS (Global Data Storage) och crx-databasen.

      >[!NOTE]
      >
      >Välj alternativet **[!UICONTROL Upgrade from Adobe Experience Manager Forms 6.2.0]** på skärmen Uppgradera aktivitetsval. Med alternativet **[!UICONTROL Upgrade from Adobe Experience Manager Forms 6.2.0]** kan konfigurationshanteraren uppgradera från LiveCycle ES3 till AEM 6.4 Forms.

   1. (Krävs inte för AEM Forms dokumentsäkerhetsmodul) Uppgradera och importera CRX-databasen till Forms 6.4-AEM.

      >[!NOTE]
      >
      >När crx-databasen har uppgraderats och innehållet har migrerats ändrar du lösenordet för administratörskontot. Detaljerade instruktioner finns i [Ändra lösenordet för en befintlig användare](/help/sites-administering/granite-user-group-admin.md).
1. Utför uppgifterna efter distributionen för att verifiera inloggningsuppgifter, konfigurera dokumenttjänster, korrespondenshantering, dokumentsäkerhet med mera beroende på ditt användningssätt.
1. Kontrollera att servern har uppgraderats:

   Utför några rutinåtgärder på den uppgraderade AEM Forms-servern för att säkerställa att servern uppgraderas. Du kan fylla i och skicka in några migrerade formulär eller skydda dokument för att säkerställa en lyckad uppgradering.

   >[!NOTE]
   >
   >I AEM 6.4 Forms har strukturen för crx-database ändrats. När du har uppgraderat till AEM 6.4-formulär kan du använda de ändrade sökvägarna för anpassning som du skapar på nytt. En fullständig lista över ändrade sökvägar finns i [Omstrukturering av Forms-databaser i AEM 6.4](/help/sites-deploying/forms-repository-restructuring-in-aem-6-4.md).

**Beroende på din befintliga miljö och programserver väljer du ett av följande dokument och följer instruktionerna:**

* [Uppgradera från LiveCycle ES3 till AEM 6.4 Forms för JBoss](assets/upgrade-jboss-livecycle-es3.pdf)
* [Uppgradera från LiveCycle ES3 till AEM 6.4 Forms för WebLogic](assets/upgrade-weblogic-livecycle-es3.pdf)
* [Uppgradera från LiveCycle ES3 till AEM 6.4 Forms for WebSphere](assets/upgrade-websphere-livecycle-es3.pdf)
* [Uppgradera från LiveCycle ES3 till AEM 6.4 Forms med JBoss Turnkey](assets/upgrade-turnkey-livecycle-es3.pdf)
