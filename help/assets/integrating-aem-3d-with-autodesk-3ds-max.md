---
title: Integrera AEM 3D med Autodesk 3ds Max
seo-title: Integrera AEM 3D med AutoDesk 3ds Max
description: Du kan även integrera AEM 3D med Autodesk 3ds Max för att aktivera stöd för 3ds Max-filer (.MAX). Rendering med 3ds Max stöds inte just nu.
seo-description: Du kan även integrera AEM 3D med Autodesk 3ds Max för att aktivera stöd för 3ds Max-filer (.MAX). Rendering med 3ds Max stöds inte just nu.
uuid: 6c160ad3-6b6f-43f5-9e97-5b5d962a8d1a
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
topic-tags: 3D
discoiquuid: 0d7fefc0-6923-4ac3-9e90-335c08fa56f0
exl-id: 2edecd53-0a2d-44bb-968a-d988c780e142
feature: 3D-resurser
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 0%

---

# Integrera AEM 3D med Autodesk 3ds Max {#integrating-aem-d-with-autodesk-ds-max}

>[!NOTE]
>
>Den här aktiviteten är valfri och gäller endast Windows.

Du kan även integrera AEM 3D med Autodesk 3ds Max för att aktivera stöd för 3ds Max-filer (.MAX). Rendering med 3ds Max stöds inte just nu.

Se [Avancerade konfigurationsinställningar](advanced-config-3d.md).

Se även [Integrera AEM 3D med AutoDesk Maya](integrate-maya-with-3d.md).

**Integrera AEM 3D med Autodesk 3ds Max**:

1. Installera Autodesk 3ds Max på samma servrar där AEM Author-noder är installerade.

   Efter installationen bör du kontrollera att du kan öppna och använda Maya och att det inte finns några licensproblem.

   >[!NOTE]
   >
   >Du kan undvika problem med nekad åtkomst genom att installera 3ds Max med samma administratörskonto som AEM.

1. Klicka på **[!UICONTROL Customize > Plug-in Manager]** i 3ds Max.

   Leta reda på `FBXMAX.DLU` och verifiera att dess **[!UICONTROL Status]** är **[!UICONTROL loaded]**.

   Stäng dialogrutan **[!UICONTROL Plug-In Manager]** och 3ds Max.

1. Uppdatera konverteringsskriptet.

   AEM använder ett kommandoradsskript för att anropa 3ds Max-kommandoradsverktyget `3dsmaxcmd.exe`. Du måste redigera det här skriptet om du har installerat en annan version än 3ds Max 2016, om du har installerat 3ds Max på en icke-standardplats eller om du har installerat AEM på en annan partition eller enhet.

   1. Öppna CRXDE Lite och navigera till `/libs/settings/dam/v3D/scripts/max`.
   1. Dubbelklicka på `export-fbx.bat` för att öppna den.
   1. Redigera den första raden i skriptet efter behov för att spegla platsen för verktyget `3dsmaxcmd.exe`. Om 3ds Max 2017 till exempel används och AEM installeras på en annan diskenhet:

   ![image2018-6-22_13-35-8](assets/image2018-6-22_13-35-8.png)

1. I närheten av det övre vänstra hörnet på CRXDE Lite-sidan trycker du på **[!UICONTROL Save All]**.

   I närheten av det övre vänstra hörnet på CRXDE Lite-sidan trycker du på **[!UICONTROL Save All]**.

1. Ta bort arbetsmappen (endast nödvändigt om ett tidigare försök gjordes att importera en .MAX-fil).

   1. Gå till `/libs/settings/dam/v3D/Paths/maxWorkPath` i CRXDE Lite. Som standard är värdet för den här inställningen `./MaxWork`, som är relativ till AEM installationens rotmapp.
   1. Logga in på själva servern och använd Utforskaren för att navigera till AEM installationens rotmapp.
   1. Ta bort mappen **[!UICONTROL MaxWork]**, inklusive allt innehåll, om den finns.

      Mappen återskapas automatiskt nästa gång en .MAX-fil importeras.

1. Aktivera 3ds Max för förtäring genom att göra följande:

   1. I CRXDE Lite går du till `/libs/settings/dam/v3D/assetTypes/max` och anger egenskapen **[!UICONTROL Enabled]** till true:

   ![image2018-6-22_13-50-50](assets/image2018-6-22_13-50-50.png)

1. I närheten av det övre vänstra hörnet på CRXDE Lite-sidan trycker du på **[!UICONTROL Save All]**.

## Testa integrationen av AEM 3D med Autodesk 3ds Max {#testing-the-integration-of-aem-d-with-autodesk-ds-max}

1. Öppna AEM Assets och överför sedan filen `.max` som finns i `sample-3D-content/models` till mappen **[!UICONTROL test3d]**.

   Observera att sample-3D-content.zip tidigare hämtades för validering av de grundläggande 3D-funktionerna.

1. Gå tillbaka till vyn **[!UICONTROL Card]** och observera de meddelandebanners som visas på de överförda resurserna.

   Banderollen för konverteringsformat visas medan 3ds Max konverterar det ursprungliga 3ds Max-formatet till .FBX.

1. När bearbetningen är klar öppnar du `logo-sphere.max` i vyn **[!UICONTROL Detail]**.

   Förhandsgranskningen fungerar på samma sätt som med `logo_sphere.fbx`.
