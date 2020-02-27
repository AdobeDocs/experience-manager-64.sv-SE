---
title: Konfigurera synkroniseringsplaneraren
seo-title: Konfigurera synkroniseringsplaneraren
description: Lär dig hur du migrerar och synkroniserar resurser, konfigurerar schemaläggaren för synkronisering och använder mappar för att ordna resurser.
seo-description: Lär dig hur du migrerar och synkroniserar resurser, konfigurerar schemaläggaren för synkronisering och använder mappar för att ordna resurser.
uuid: a6445b45-9c1c-4483-a32e-453648c488c5
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: 2c8cea3c-8d8b-41d4-8ef9-a0ada8f86be6
translation-type: tm+mt
source-git-commit: 8cbfa421443e62c0483756e9d5812bc987a9f91d

---


# Konfigurera synkroniseringsplaneraren {#configuring-the-synchronization-scheduler}

Som standard körs synkroniseringsschemaläggaren efter var tredje minut för att synkronisera alla resurser som ändrats och uppdaterats i databasen via LiveCycle Workbench 11. Program som innehåller formulär och resurser visas i AEM Forms-användargränssnittet när synkroniseringsprocessen är slutförd.

## Ändra intervall för synkroniseringsschemaläggaren {#change-interval-of-the-synchronization-scheduler}

Utför följande steg för att ändra intervallet för synkroniseringsplaneraren:

1. Logga in på AEM Configuration Manager. URL:en för Configuration Manager är `https://[Server]:[Port]/lc/system/console/configMgr`

1. Leta upp och öppna **FormsManagerConfiguration** -paketet.

1. Ange ett nytt värde för alternativet **Synkroniseringsfrekvens** för schemaläggaren.

   Frekvensenheten är minuter. Om du till exempel vill konfigurera schemaläggaren att köras efter var 60:e minut anger du 60.

## Synkronisera resurser {#synchronizing-assets}

Du kan använda alternativet **Synkronisera resurser från databas** om du vill synkronisera resurserna manuellt. Så här synkroniserar du resurserna manuellt:

1. Logga in på AEM Forms. Standardwebbadressen är `https://[Server]:[Port]/lc/aem/forms/`.

   ![AEM Forms användargränssnitt](assets/aem_forms_ui.png)

   **** Bild: Användargränssnittet *AEM Forms*

1. Klicka på ![ikonen aem6forms_sync](assets/aem6forms_sync.png) i verktygsfältet. Om du inte har några resurser på den senast konfigurerade sökvägen visas dialogrutan enligt nedan. Klicka på **Start** för att starta synkroniseringen.

   ![Synkroniseringsdialogruta](assets/migrate-and-syncronize.png)

   **** Bild: Dialogrutan *Synkronisering*

## Felsökning av synkroniseringsfel {#troubleshooting-synchronization-error}

Du kan skapa nya program i arbetsflödesdesignern (LiveCycle Workbench).

Om det nyligen skapade programmet och en mapp på /content/dam/formSanddocuments har samma namn, visas felet&quot;*En resurs med samma namn som det här programmet finns redan på rotnivå.*&quot; är loggad.

Lös konflikten genom att byta namn på programmet och manuellt synkronisera resurserna.

![Konflikter i dialogrutan för resurssynkronisering](assets/sync-conflict.png)

**** Bild: Konflikter *i dialogrutan för resurssynkronisering*

