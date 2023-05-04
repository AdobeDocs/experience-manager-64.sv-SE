---
title: Metadataschema för mapp
description: I den här artikeln beskrivs hur du skapar ett metadatamatema för resursmappar i [!DNL Experience Manager] Resurser
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
uuid: 286a4f26-c0ad-4691-80d8-d17ba1a2dfe0
discoiquuid: 92eacea5-7511-48ce-8a72-ff4552ebb07d
feature: Metadata
role: User,Admin
exl-id: 1bc72dac-41f7-4593-aaea-d48ebd94b43e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1041'
ht-degree: 5%

---

# Metadataschema för mapp {#folder-metadata-schema}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

I den här artikeln beskrivs hur du skapar ett metadatamatema för resursmappar i [!DNL Experience Manager] Resurser.

Med Adobe Experience Manager Assets kan du skapa metadatamappar för resurser, som definierar layouten och metadata som visas på mappegenskapssidor.

>[!NOTE]
>
>Den här funktionen kräver [!DNL Experience Manager] 6.4 med minst Service Pack 2 distribuerat. För [!DNL Experience Manager] 6.4 service pack details, see these [versionsinformation](/help/release-notes/sp-release-notes.md).

## Lägga till ett schemaformulär för mappmetadata {#add-a-folder-metadata-schema-form}

Använd schemaredigeraren för mappmetadata i Forms för att skapa och redigera metadatascheman för mappar.

1. Tryck/klicka på [!DNL Experience Manager] logotyp och gå till **[!UICONTROL Tools]** > **[!UICONTROL Assets]**> **[!UICONTROL Folder Metadata Schemas]**.
1. På Forms-sidan för mappmetadataschema trycker/klickar du **[!UICONTROL Create]**.
1. Ange ett namn för formuläret och tryck/klicka **[!UICONTROL Create]**. Det nya schemaformuläret visas på Forms-sidan Schema.

## Redigera schemaformulär för mappmetadata {#edit-folder-metadata-schema-forms}

Du kan redigera ett nyligen tillagt eller befintligt metadatchemaformulär, som innehåller följande:

* Tabbar
* Formulärobjekt på flikar.

Du kan mappa/konfigurera dessa formulärobjekt till ett fält i en metadatanod i CRX-databasen. Du kan lägga till nya flikar eller formulärobjekt i metadatchemaformuläret.

1. På Forms-sidan Schema väljer du det formulär du skapade och trycker/klickar sedan på knappen **[!UICONTROL Edit]** -ikonen i verktygsfältet.
1. Tryck/klicka på knappen **[!UICONTROL +]** om du vill lägga till en flik i formuläret. Byt namn på fliken genom att trycka/klicka på standardnamnet och ange det nya namnet under **[!UICONTROL Settings]**.

   ![custom_tab](assets/custom_tab.png)

   Om du vill lägga till fler flikar trycker/klickar du på **[!UICONTROL +]** ikon. Tryck/klicka **[!UICONTROL X]** för att ta bort en flik.

1. Lägg till en eller flera komponenter från fliken Aktiv **[!UICONTROL Build Form]** -fliken.

   ![adding_components](assets/adding_components.png)

   Om du skapar flera flikar trycker/klickar du på en viss flik för att lägga till komponenter.

1. Om du vill konfigurera en komponent markerar du den och ändrar dess egenskaper i **[!UICONTROL Settings]** -fliken.

   Ta bort en komponent från **[!UICONTROL Settings]** -fliken.

   ![configure_properties](assets/configure_properties.png)

1. Tryck/klicka **[!UICONTROL Save]** i verktygsfältet för att spara ändringarna.

### Komponenter för att skapa formulär {#components-to-build-forms}

The **[!UICONTROL Build Form]** På fliken visas formulärobjekt som du använder i schemaformuläret för mappmetadata. The **[!UICONTROL Settings]** på -fliken visas attributen för varje objekt som du väljer i **[!UICONTROL Build Form]** -fliken. Här är en lista över de tillgängliga formulärobjekten i **[!UICONTROL Build Form]** tab:

| Komponentnamn | Beskrivning |
|---|---|
| [!UICONTROL Section Header] | Lägg till en avsnittsrubrik för en lista med gemensamma komponenter. |
| [!UICONTROL Single Line Text] | Lägg till en enkelradig textegenskap. Den lagras som en sträng. |
| [!UICONTROL Multi Value Text] | Lägg till en textegenskap med flera värden. Den lagras som en strängarray. |
| [!UICONTROL Number] | Lägg till en sifferkomponent. |
| [!UICONTROL Date] | Lägg till en datumkomponent. |
| [!UICONTROL Dropdown] | Lägg till en nedrullningsbar lista. |
| [!UICONTROL Standard Tags] | Lägg till en tagg. |
| [!UICONTROL Hidden Field] | Lägg till ett dolt fält. Den skickas som en POST-parameter när resursen sparas. |

### Redigera formulärobjekt {#editing-form-items}

Om du vill redigera egenskaperna för formulärobjekt trycker/klickar du på komponenten och redigerar alla eller en delmängd av följande egenskaper i dialogrutan **[!UICONTROL Settings]** -fliken.

**[!UICONTROL Field Label]**: Namnet på metadataegenskapen som visas på egenskapssidan för mappen.

**[!UICONTROL Map to Property]**: This property specifies the relative path of the folder node in the CRX database where it is saved. Det börjar med &quot;**./**&quot;, vilket anger att sökvägen finns under mappens nod.

Följande är giltiga värden för den här egenskapen:

* `./jcr:content/metadata/dc:title`: Lagrar värdet i mappens metadatanod som egenskapen `dc:title`.

* `./jcr:created`: Visar JCR-egenskapen vid mappens nod. Om du konfigurerar de här egenskaperna i CRXDE rekommenderar Adobe att du markerar dem som Inaktivera redigering eftersom de är skyddade. Annars returneras felet `Asset(s) failed to modify`&#39; inträffar när du sparar resursens egenskaper.

För att komponenten ska visas på rätt sätt i schemaformuläret för metadata ska du inte ta med något utrymme i egenskapssökvägen.

**[!UICONTROL JSON Path]**: Använd den för att ange sökvägen till JSON-filen där du anger nyckelvärdepar för alternativ.

**[!UICONTROL Placeholder]**: Använd den här egenskapen för att ange relevant platshållartext för metadataegenskapen.

**[!UICONTROL Choices]**: Använd den här egenskapen för att ange alternativ i en lista.

**[!UICONTROL Description]**: Använd den här egenskapen om du vill lägga till en kort beskrivning för metadatakomponenten.

**[!UICONTROL Class]**: Den objektklass som egenskapen är associerad med.

## Ta bort schemaformulär för mappmetadata {#delete-folder-metadata-schema-forms}

Du kan ta bort schemaformulär för mappmetadata från Forms-sidan för mappmetadataschema. Om du vill ta bort ett formulär markerar du det och trycker/klickar på ikonen Ta bort i verktygsfältet.

![delete_form](assets/delete_form.png)

## Tilldela ett mappmetadatchema {#assign-a-folder-metadata-schema}

Du kan tilldela ett mappmetadatchema till en mapp från Forms-sidan för mappmetadataschema eller när du skapar en mapp.

Om du konfigurerar ett metadataschema för en mapp lagras sökvägen till schemaformuläret i `folderMetadataSchema` egenskapen för mappnoden under .*/jcr:innehåll*.

### Tilldela till ett schema från sidan Mappmetadatamatchema {#assign-to-a-schema-from-the-folder-metadata-schema-page}

1. Tryck/klicka på [!DNL Experience Manager] logotyp och gå till **[!UICONTROL Tools]** > **[!UICONTROL Assets]** > **[!UICONTROL Folder Metadata Schemas]**.
1. På Forms-sidan för mappmetadataschema väljer du det schemaformulär som du vill tillämpa på en mapp.
1. Tryck/klicka i verktygsfältet **[!UICONTROL Apply to Folder(s)]**.

1. Välj den mapp som du vill använda schemat på och klicka/tryck sedan på **[!UICONTROL Apply]**. Om ett metadatamatchema redan används för mappen visas ett varningsmeddelande om att du håller på att skriva över det befintliga metadatamodemet. Tryck/klicka på **[!UICONTROL Overwrite]**.
1. Öppna metadataegenskaperna för den mapp som du tillämpade metadataschemat på.

   ![folder_properties](assets/folder_properties.png)

   Om du vill visa fälten för mappmetadata trycker/klickar du på fliken **[!UICONTROL Folder Metadata]**.

   ![folder_metadata_properties](assets/folder_metadata_properties.png)

### Tilldela ett schema när du skapar en mapp {#assign-a-schema-when-creating-a-folder}

Du kan tilldela ett mappmetadatchema när du skapar en mapp. Om det finns minst ett mappmetadatchema i systemet visas en extra lista i **[!UICONTROL Create Folder]** -dialogrutan. Du kan välja önskat schema. Som standard är inget schema valt.

1. Från [!DNL Assets] användargränssnitt, knacka/klicka **[!UICONTROL Create]** i verktygsfältet.
1. Ange en rubrik och ett namn för mappen.
1. Välj önskat schema i listan Mappmetadatamatchema. Tryck/klicka sedan **[!UICONTROL Create]**.

   ![select_schema](assets/select_schema.png)

1. Öppna metadataegenskaperna för den mapp som du tillämpade metadataschemat på.
1. Om du vill visa fälten för mappmetadata trycker/klickar du på fliken **[!UICONTROL Folder Metadata]**.

## Använd mappens metadatamatchema {#use-the-folder-metadata-schema}

Öppna egenskaperna för en mapp som har konfigurerats med ett schema för mappmetadata. En flik för **[!UICONTROL Folder Metadata]** visas på sidan med mappegenskaper. Om du vill visa formuläret för schemat med mappmetadata väljer du den här fliken.

Ange metadatavärden i de olika fälten och tryck/klicka **[!UICONTROL Save]** för att lagra värdena. De värden du anger lagras i mappnoden i CRX-databasen.

![folder_metadata_properties-1](assets/folder_metadata_properties-1.png)
