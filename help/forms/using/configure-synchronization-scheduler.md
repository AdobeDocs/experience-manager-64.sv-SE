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
role: Administratör
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '307'
ht-degree: 0%

---


# Konfigurerar synkroniseringsschemaläggaren {#configuring-the-synchronization-scheduler}

Som standard körs synkroniseringsschemaläggaren efter var tredje minut för att synkronisera alla resurser som ändrats och uppdaterats i databasen via LiveCycle Workbench 11. Program som innehåller formulär och resurser visas i AEM Forms användargränssnitt när synkroniseringsprocessen är klar.

## Ändra intervall för synkroniseringsschemaläggaren {#change-interval-of-the-synchronization-scheduler}

Utför följande steg för att ändra intervallet för synkroniseringsplaneraren:

1. Logga in AEM Configuration Manager. URL:en för Configuration Manager är `https://[Server]:[Port]/lc/system/console/configMgr`

1. Leta reda på och öppna paketet **FormsManagerConfiguration**.

1. Ange ett nytt värde för alternativet **Schemaläggarens synkroniseringsfrekvens**.

   Frekvensenheten är minuter. Om du till exempel vill konfigurera schemaläggaren att köras efter var 60:e minut anger du 60.

## Synkroniserar resurser {#synchronizing-assets}

Du kan använda alternativet **Synkronisera resurser från databas** om du vill synkronisera resurserna manuellt. Så här synkroniserar du resurserna manuellt:

1. Logga in på AEM Forms. Standardwebbadressen är `https://[Server]:[Port]/lc/aem/forms/`.

   ![AEM Forms användargränssnitt](assets/aem_forms_ui.png)

   **Bild:** *AEM Forms användargränssnitt*

1. Klicka på ikonen ![aem6forms_sync](assets/aem6forms_sync.png) i verktygsfältet. Om du inte har några resurser på den senast konfigurerade sökvägen visas dialogrutan enligt nedan. Klicka på **Starta** för att starta synkroniseringen.

   ![Synkroniseringsdialogruta](assets/migrate-and-syncronize.png)

   **Figur:** *Synkroniseringsdialogruta*

## Felsökning av synkroniseringsfel {#troubleshooting-synchronization-error}

Du kan skapa nya program i arbetsflödesdesignern (LiveCycle Workbench).

Om det nyligen skapade programmet och en mapp på /content/dam/formsanddocuments har samma namn, finns det ett fel &quot;*En resurs med samma namn som det här programmet redan på rotnivå.*&quot; är loggad.

Lös konflikten genom att byta namn på programmet och manuellt synkronisera resurserna.

![Konflikter i dialogrutan för resurssynkronisering](assets/sync-conflict.png)

**Figur:** *Konflikter i dialogrutan för resurssynkronisering*

