---
title: Konfigurera synkroniseringsplaneraren
seo-title: Configuring the synchronization scheduler
description: Lär dig hur du migrerar och synkroniserar resurser, konfigurerar schemaläggaren för synkronisering och använder mappar för att ordna resurser.
seo-description: Learn how to migrate and sync assets, configure sync scheduler, and use folders to arrange assets.
uuid: a6445b45-9c1c-4483-a32e-453648c488c5
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: Configuration
discoiquuid: 2c8cea3c-8d8b-41d4-8ef9-a0ada8f86be6
role: Admin
exl-id: 7f1c4bac-accf-43e4-9439-89c5420d50f2
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 0%

---

# Konfigurera synkroniseringsplaneraren {#configuring-the-synchronization-scheduler}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Som standard körs synkroniseringsschemaläggaren efter var tredje minut för att synkronisera alla resurser som ändrats och uppdaterats i databasen via LiveCycle Workbench 11. Program som innehåller formulär och resurser visas i AEM Forms användargränssnitt när synkroniseringsprocessen är klar.

## Ändra intervall för synkroniseringsschemaläggaren {#change-interval-of-the-synchronization-scheduler}

Utför följande steg för att ändra intervallet för synkroniseringsplaneraren:

1. Logga in AEM Configuration Manager. URL:en för Configuration Manager är `https://[Server]:[Port]/lc/system/console/configMgr`

1. Leta reda på och öppna **FormsManagerConfiguration** paket.

1. Ange ett nytt värde för **Frekvens för synkroniseringsschemaläggare** alternativ.

   Frekvensenheten är minuter. Om du till exempel vill konfigurera schemaläggaren att köras efter var 60:e minut anger du 60.

## Synkronisera resurser {#synchronizing-assets}

Du kan använda **Synkronisera resurser från databas** om du vill synkronisera resurserna manuellt. Så här synkroniserar du resurserna manuellt:

1. Logga in på AEM Forms. Standardwebbadressen är `https://[Server]:[Port]/lc/aem/forms/`.

   ![AEM Forms användargränssnitt](assets/aem_forms_ui.png)

   **Bild:** *AEM Forms användargränssnitt*

1. Klicka på ![aem6forms_sync](assets/aem6forms_sync.png) i verktygsfältet. Om du inte har några resurser på den senast konfigurerade sökvägen visas dialogrutan enligt nedan. Klicka **Starta** för att initiera synkroniseringen.

   ![Synkroniseringsdialogruta](assets/migrate-and-syncronize.png)

   **Bild:** *Synkroniseringsdialogruta*

## Felsökning av synkroniseringsfel {#troubleshooting-synchronization-error}

Du kan skapa nya program i arbetsflödesdesignern (LiveCycle Workbench).

Om det nyligen skapade programmet och en mapp på /content/dam/formsanddocuments har samma namn visas ett felmeddelande &quot;*Det finns redan en resurs med samma namn som det här programmet på rotnivå.*&quot; är loggad.

Lös konflikten genom att byta namn på programmet och manuellt synkronisera resurserna.

![Konflikter i dialogrutan för resurssynkronisering](assets/sync-conflict.png)

**Bild:** *Konflikter i dialogrutan för resurssynkronisering*
