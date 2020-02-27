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
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Integrera AEM 3D med Autodesk 3ds Max {#integrating-aem-d-with-autodesk-ds-max}

>[!NOTE]
>
>Den här aktiviteten är valfri och gäller endast Windows.

Du kan även integrera AEM 3D med Autodesk 3ds Max för att aktivera stöd för 3ds Max-filer (.MAX). Rendering med 3ds Max stöds inte just nu.

Se [Avancerade konfigurationsinställningar](advanced-config-3d.md).

Se även [Integrera AEM 3D med AutoDesk Maya](integrate-maya-with-3d.md).

**För att integrera AEM 3D med Autodesk 3ds Max**:

1. Installera Autodesk 3ds Max på samma servrar där AEM Author-noder är installerade.

   Efter installationen bör du kontrollera att du kan öppna och använda Maya och att det inte finns några licensproblem.

   >[!NOTE]
   >
   >Du kan undvika problem med nekad åtkomst genom att installera 3ds Max med samma administratörskonto som AEM.

1. I 3ds Max klickar du på **[!UICONTROL Anpassa > Plugin-hanteraren]**.

   Leta reda på `FBXMAX.DLU` och verifiera att dess **[!UICONTROL status]** är **[!UICONTROL loaded**.

   Stäng dialogrutan **[!UICONTROL Plugin-hanteraren]** och 3ds Max.

1. Uppdatera konverteringsskriptet.

   AEM använder ett kommandoradsskript för att anropa kommandoradsverktyget 3ds Max `3dsmaxcmd.exe`. Du måste redigera det här skriptet om du har installerat en annan version än 3ds Max 2016, om du har installerat 3ds Max på en icke-standardplats eller om du har installerat AEM på en annan partition eller enhet.

   1. Öppna CRXDE Lite och navigera till `/libs/settings/dam/v3D/scripts/max`.
   1. Öppna den genom `export-fbx.bat` att dubbelklicka på den.
   1. Redigera den första raden i skriptet efter behov för att spegla platsen för `3dsmaxcmd.exe` verktyget. Om 3ds Max 2017 till exempel används och AEM är installerat på en annan diskenhet:
   ![image2018-6-22_13-35-8](assets/image2018-6-22_13-35-8.png)

1. I det övre vänstra hörnet av CRXDE Lite-sidan trycker du på **[!UICONTROL Spara alla]**.

   I det övre vänstra hörnet av CRXDE Lite-sidan trycker du på **[!UICONTROL Spara alla]**.

1. Ta bort arbetsmappen (endast nödvändigt om ett tidigare försök gjordes att importera en .MAX-fil).

   1. Navigera till CRXDE Lite `/libs/settings/dam/v3D/Paths/maxWorkPath`. Som standard är den här inställningen `./MaxWork`relativ till AEM-installationens rotmapp.
   1. Logga in på själva servern och använd Utforskaren för att navigera till rotmappen för AEM-installationen.
   1. Ta bort mappen **[!UICONTROL MaxWork]** - inklusive allt innehåll - om den finns.

      Mappen återskapas automatiskt nästa gång en .MAX-fil importeras.

1. Aktivera 3ds Max för förtäring genom att göra följande:

   1. I CRXDE Lite navigerar du till `/libs/settings/dam/v3D/assetTypes/max` och ställer in egenskapen **[!UICONTROL Enabled]** på true:
   ![image2018-6-22_13-50-50](assets/image2018-6-22_13-50-50.png)

1. I det övre vänstra hörnet av CRXDE Lite-sidan trycker du på **[!UICONTROL Spara alla]**.

## Testa integrationen av AEM 3D med Autodesk 3ds Max {#testing-the-integration-of-aem-d-with-autodesk-ds-max}

1. Öppna AEM Resurser och överför sedan `.max` filen som finns i `sample-3D-content/models` mappen **[!UICONTROL test3d]** .

   Observera att sample-3D-content.zip tidigare hämtades för validering av de grundläggande 3D-funktionerna.

1. Gå tillbaka till **[!UICONTROL kortvyn]** och observera de meddelandebanners som visas på de överförda resurserna.

   Banderollen för konverteringsformat visas medan 3ds Max konverterar det ursprungliga 3ds Max-formatet till .FBX.

1. När bearbetningen är klar öppnar du `logo-sphere.max` i vyn **[!UICONTROL Detalj]** .

   Förhandsgranskningen fungerar på samma sätt som med `logo_sphere.fbx`.

