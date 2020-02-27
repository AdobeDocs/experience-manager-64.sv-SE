---
title: Använd metadataprofiler för att använda standardmetadata på alla resurser i en mapp
description: Lär dig mer om metadataprofiler för resurser. Lär dig hur du skapar en metadataprofil och använder den på mappresurser.
contentOwner: AG
translation-type: tm+mt
source-git-commit: af1955ab1fdcf16dd9a9d3ad36336e6c1aac9312

---


# Metadataprofiler {#metadata-profiles}

Med en metadataprofil kan du använda standardmetadata för resurser i en mapp. Skapa en metadataprofil och tillämpa den på en mapp. Alla resurser som du sedan överför till mappen ärver de standardmetadata som du konfigurerade i metadataprofilen.

## Lägg till en metadataprofil {#adding-a-metadata-profile}

1. Tryck eller klicka på AEM-logotypen och navigera till **[!UICONTROL Verktyg > Resurser > Metadataprofiler]** och tryck sedan på **[!UICONTROL Skapa]**.
1. Ange en rubrik för metadataprofilen, till exempel Exempelmetadata, och klicka på **[!UICONTROL Skicka]**. Metadataprofilens **[!UICONTROL redigeringsformulär]** visas.

   ![chlimage_1-480](assets/chlimage_1-480.png)

1. Klicka på en komponent och konfigurera dess egenskaper på fliken **[!UICONTROL Inställningar]** . Klicka till exempel på komponenten **[!UICONTROL Beskrivning]** och redigera dess egenskaper.

   ![chlimage_1-481](assets/chlimage_1-481.png)

   Redigera följande egenskaper för komponenten **[!UICONTROL Description]** :

   * **[!UICONTROL Fältetikett]**: Visningsnamnet för metadataegenskapen. Det är bara till för användarreferensen.
   * **[!UICONTROL Mappa till egenskap]**: Värdet för den här egenskapen anger den relativa sökvägen/namnet till resursnoden där den sparas i databasen. Värdet ska alltid börja med `./` eftersom det anger att sökvägen finns under objektets nod.
   ![chlimage_1-482](assets/chlimage_1-482.png)

   Värdet som du anger för **[!UICONTROL Mappa till egenskap]** lagras som en egenskap under objektets metadatanod. Om du till exempel anger . `/jcr:content/metadata/dc:desc` som namnet på **[!UICONTROL Mappa till egenskap]** lagrar AEM Resurser värdet `dc:desc` i objektets metadatanod.

   * **[!UICONTROL Standardvärde]**: Använd den här egenskapen om du vill lägga till ett standardvärde för metadatakomponenten. Om du till exempel anger &quot;Min beskrivning&quot; tilldelas det här värdet till egenskapen `dc:desc` vid objektets metadatanod.
   ![chlimage_1-483](assets/chlimage_1-483.png)

   >[!NOTE]
   >
   >Lägga till ett standardvärde i en ny metadataegenskap (som inte redan finns i . `/jcr:content/metadata` nod) visar inte egenskapen och dess värde på objektets **[!UICONTROL egenskapssida]** som standard. Om du vill visa den nya egenskapen på sidan [!UICONTROL Egenskaper] för resursen ändrar du motsvarande schemaformulär.

1. (Valfritt) Lägg till fler komponenter i **[!UICONTROL Redigera formulär]** på fliken **[!UICONTROL Skapa formulär]** och konfigurera deras egenskaper på fliken **[!UICONTROL Inställningar]** . Följande egenskaper är tillgängliga på fliken **[!UICONTROL Skapa formulär]** :

| Komponent | Egenskaper |
|---|---|
| [!UICONTROL Avsnittshuvud] | Fältetikett, <br> beskrivning |
| [!UICONTROL Enkelradstext] | Fältetikett, <br> Koppla till egenskap, <br> standardvärde |
| [!UICONTROL Flervärdestext] | Fältetikett, <br> Koppla till egenskap, <br> standardvärde |
| [!UICONTROL Siffra] | Fältetikett, <br> Koppla till egenskap, <br> standardvärde |
| [!UICONTROL Date] | Fältetikett, <br> Koppla till egenskap, <br> standardvärde |
| [!UICONTROL Standardtaggar] | Fältetikett, <br> Koppla till egenskap, <br> Standardvärde, <br> Beskrivning |

![chlimage_1-484](assets/chlimage_1-484.png)

1. Klicka på **[!UICONTROL Klar]**. Metadataprofilen läggs till i listan med profiler på sidan **[!UICONTROL Metadataprofiler]** .

   ![chlimage_1-485](assets/chlimage_1-485.png)

## Kopiera en metadataprofil {#copying-a-metadata-profile}

1. Välj en profil på sidan **[!UICONTROL Metadataprofiler]** och gör en kopia av den.

   ![chlimage_1-486](assets/chlimage_1-486.png)

1. Klicka på **[!UICONTROL Kopiera]** i verktygsfältet.
1. I dialogrutan **[!UICONTROL Kopiera metadataprofil]** anger du en rubrik för den nya kopian av profilen.
1. Klicka på **[!UICONTROL Kopiera]**. En kopia av profilen visas i listan över profiler på sidan **[!UICONTROL Metadataprofiler]** .

   ![chlimage_1-487](assets/chlimage_1-487.png)

## Ta bort en metadataprofil {#deleting-a-metadata-profile}

1. På sidan **[!UICONTROL Metadataprofiler]** väljer du en profil som ska tas bort.

   ![chlimage_1-488](assets/chlimage_1-488.png)

1. Klicka på **[!UICONTROL Ta bort metadataprofiler]** i verktygsfältet.
1. Bekräfta borttagningsåtgärden genom att klicka på **[!UICONTROL Ta bort]** i dialogrutan. Metadataprofilen tas bort från listan.

## Använda en metadataprofil för mappar {#applying-a-metadata-profile-to-folders}

När du tilldelar en metadataprofil till en mapp ärver alla undermappar automatiskt profilen från den överordnade mappen. Det innebär att du bara kan tilldela en metadataprofil till en mapp. Fundera därför noga över mappstrukturen för var du överför, lagrar, använder och arkiverar resurser.

Om du har tilldelat en annan metadataprofil till en mapp åsidosätter den nya profilen den tidigare profilen. De tidigare befintliga mappresurserna ändras inte. Den nya profilen används för resurser som läggs till i mappen senare.

Mappar som har tilldelats en profil visas i användargränssnittet med namnet på profilen som visas i kortnamnet.

![chlimage_1-489](assets/chlimage_1-489.png)

Du kan tillämpa metadataprofiler på specifika mappar eller globalt på alla resurser.

### Använda metadataprofiler på specifika mappar {#applying-metadata-profiles-to-specific-folders}

Du kan tillämpa en metadataprofil på en mapp från **[!UICONTROL Verktyg]** -menyn eller, om du är i mappen, från **[!UICONTROL Egenskaper]**. I det här avsnittet beskrivs hur du använder metadataprofiler på mappar på båda sätten.

Mappar som redan har tilldelats en profil visas genom att profilens namn visas direkt under mappnamnet.

#### Använda metadataprofiler på mappar från användargränssnittet för profiler {#applying-metadata-profiles-to-folders-from-profiles-user-interface}

1. Tryck på AEM-logotypen och navigera till **[!UICONTROL Verktyg > Resurser > Metadataprofiler]**.
1. Välj den metadataprofil som du vill använda för en eller flera mappar.

   ![chlimage_1-490](assets/chlimage_1-490.png)

1. Tryck på **[!UICONTROL Använd metadataprofil för mappar]** och markera den eller de mappar som du vill använda för att ta emot de nyligen överförda resurserna. Tryck sedan på **[!UICONTROL Klar]**. Mappar som redan har tilldelats en profil visas genom att profilens namn visas direkt under mappnamnet.

#### Använd metadataprofiler på mappar från Egenskaper {#applying-metadata-profiles-to-folders-from-properties}

1. I den vänstra listen trycker du på **[!UICONTROL Resurser]** och navigerar sedan till mappen som du vill använda en metadataprofil på.
1. Markera mappen genom att trycka på bockmarkeringen och sedan på **[!UICONTROL Egenskaper]**.

1. Välj fliken **[!UICONTROL Metadataprofiler]** och välj profilen i listrutan och klicka på **[!UICONTROL Spara]**.

   ![chlimage_1-491](assets/chlimage_1-491.png)

   Mappar som redan har tilldelats en profil visas genom att profilens namn visas direkt under mappnamnet.

### Använd en metadataprofil globalt {#applying-a-metadata-profile-globally}

Förutom att tillämpa en profil på en mapp kan du även tillämpa en profil globalt så att allt innehåll som överförs till AEM-resurser i en mapp har den valda profilen. Så här använder du en metadataprofil globalt:

1. Gör något av följande:

   * Navigera till `https://[aem_server]:[port]/mnt/overlay/dam/gui/content/assets/foldersharewizard.html/content/dam` och använd rätt profil och tryck eller klicka på **[!UICONTROL Spara]**.

      ![chlimage_1-492](assets/chlimage_1-492.png)

   * Navigera till CRXDE Lite till följande nod: `/content/dam/jcr:content`. Lägg till egenskapen `metadataProfile:/etc/dam/metadata/dynamicmedia/<name_of_metadata_profile>` och tryck på **[!UICONTROL Spara alla]**.

      ![chlimage_1-493](assets/chlimage_1-493.png)

## Ta bort en metadataprofil från mappar {#removing-a-metadata-profile-from-folders}

När du tar bort en metadataprofil från en mapp ärver alla undermappar automatiskt borttagningen av profilen från den överordnade mappen. All bearbetning av filer som har inträffat i mapparna förblir dock oförändrad.

Du kan ta bort en metadataprofil från en mapp från **[!UICONTROL Verktyg]** -menyn eller, om du är i mappen, från **[!UICONTROL Egenskaper]**. I det här avsnittet beskrivs hur du tar bort metadataprofiler från mappar på båda sätten.

### Ta bort metadataprofiler från mappar via användargränssnittet Profiler {#removing-metadata-profiles-from-folders-via-profiles-user-interface}

Så här tar du bort en metadataprofil från mappar via användargränssnittet för profiler:

1. Tryck på AEM-logotypen och navigera till **[!UICONTROL Verktyg > Resurser > Metadataprofiler]**.
1. Markera den metadataprofil som du vill ta bort från en eller flera mappar.
1. Tryck på **[!UICONTROL Ta bort metadataprofil från]** mapp(ar) och markera den eller de mappar du vill ta bort en profil från. Tryck sedan på **[!UICONTROL Klar]**.

   Du kan bekräfta att metadataprofilen inte längre används för en mapp eftersom namnet inte längre visas under mappnamnet.

### Ta bort metadataprofiler från mappar via Egenskaper {#removing-metadata-profiles-from-folders-via-properties}

1. Tryck på AEM-logotypen, navigera till **[!UICONTROL Resurser]** och sedan till den mapp som du vill ta bort en metadataprofil från.
1. Markera mappen genom att trycka på bockmarkeringen och sedan på **[!UICONTROL Egenskaper]**.
1. Välj fliken **[!UICONTROL Metadataprofiler]** och välj **[!UICONTROL Ingen]** i listrutan. Tryck på **[!UICONTROL Spara]**.

Mappar som redan har tilldelats en profil visas genom att profilens namn visas direkt under mappnamnet.
