---
title: Integrera AEM 3D med Autodesk Maya
seo-title: Integrera AEM 3D med Autodesk Maya
description: Du kan även integrera AEM 3D med Autodesk® Maya® för att aktivera stöd för egna Maya-filer (.MA och .MB) och för att du ska kunna återge 3D-resurser i AEM med alla tillgängliga Maya-renderare.
seo-description: Du kan även integrera AEM 3D med Autodesk® Maya® för att aktivera stöd för egna Maya-filer (.MA och .MB) och för att du ska kunna återge 3D-resurser i AEM med alla tillgängliga Maya-renderare.
uuid: 07ff17b6-bdfc-4617-8b16-42aaf5c73fc7
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 3d063268-17d7-4db6-8028-682537645377
exl-id: 52ecbf81-0953-4c44-bc2c-d40e507b8d98
feature: 3D-resurser
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '823'
ht-degree: 0%

---

# Integrera AEM 3D med Autodesk Maya {#integrating-aem-d-with-autodesk-maya}

>[!NOTE]
>
>Den här aktiviteten är valfri och gäller endast Windows.

Du kan även integrera AEM 3D med Autodesk® Maya® för att aktivera stöd för egna Maya-filer (`.MA` och `.MB`) och för att du ska kunna återge 3D-resurser i AEM med alla tillgängliga Maya-renderare.

*Den här integreringen gäller endast* Windows.

När du integrerar med Autodesk Maya måste du installera och konfigurera Autodesk Maya, lägga till sökvägen till den körbara mappen Maya, aktivera Maya för förtäring och rendering samt testa integreringen.

Se [Avancerade konfigurationsinställningar](advanced-config-3d.md).

Se även [Integrera AEM 3D med AutoDesk 3ds Max](integrating-aem-3d-with-autodesk-3ds-max.md).

**För att integrera AEM 3D med Autodesk Maya**:

1. Installera Autodesk Maya 2016 på samma servrar där AEM finns.

   Efter installationen bör du kontrollera att du kan öppna och använda Maya och att det inte finns några licensproblem.

   >[!NOTE]
   >
   >AEM använder bara kommandoradsåtergivning för Maya (`render.exe`). En enda Maya-nätverkslicens tillåter upp till fem servrar att bearbeta eller återge Maya-innehåll samtidigt.

1. Aktivera Autodesk FBX® Plug-In på Maya.
1. Installera plugin-programmet för MentalRay-rendering eller någon annan renderare.

   Efter installationen bör du kontrollera att MentalRay finns på Maya.

1. Lägg till sökvägen till den körbara mappen Maya i systemvariabeln Windows PATH.

   I Windows Server 2012 trycker du till exempel på **[!UICONTROL Start]> [!UICONTROL Control Panel] > [!UICONTROL System and Security] > [!UICONTROL System] > [!UICONTROL Advanced System Settings] >[!UICONTROL Environment Variables]**. Lägg till den fullständiga sökvägen till mappen `Maya2016\bin` i systemvariabeln `Path`.

   ![chlimage_1-53](assets/chlimage_1-53.png)

1. Om du vill aktivera Maya för förtäring och återgivning öppnar du **[!UICONTROL CRXDE Lite]** och navigerar till `/libs/settings/dam/v3D/assetTypes/maya` och ställer in egenskapen **[!UICONTROL Enabled]** på `true`.

   ![image2018-6-22_12-42-7](assets/image2018-6-22_12-42-7.png)

1. Om du vill aktivera filformatet JT (Siemens PLM Open CAD) går du till `/libs/settings/dam/v3D/assetTypes/jt` och anger egenskapen **[!UICONTROL Enabled]** till `true`.
1. I AEM aktiverar du Maya som renderare. Börja med att navigera till **[!UICONTROL Tools > General > CRXDE Lite]**.
1. Gå till följande på sidan **[!UICONTROL CRXDE Lite]** i den vänstra panelen:

   `/libs/settings/dam/v3D/renderers/maya`

   ![image2018-6-22_12-46-18](assets/image2018-6-22_12-46-18.png)

1. Ställ in egenskapen **[!UICONTROL Enabled]** på `true`.

1. I det övre vänstra hörnet av sidan **[!UICONTROL CRXDE Lite]** trycker du på **[!UICONTROL Save All]**.

   Maya är nu aktiverat som renderare.

## Testa integrationen av AEM 3D med Autodesk Maya {#testing-the-integration-of-aem-d-with-autodesk-maya}

1. Öppna AEM Assets och överför sedan `.MA`-filerna som finns i `sample-3D-content/models` till mappen `test3d`.

   Observera att `sample-3D-content.zip` tidigare hämtades för validering av de grundläggande 3D-funktionerna.

1. Gå tillbaka till vyn **[!UICONTROL Card]** och observera de meddelandebanners som visas på de överförda resurserna.

   Banderollen för konverteringsformat visas när Maya konverterar det ursprungliga `.MA`-formatet till `.FBX`.

1. När all bearbetning är klar öppnar du `logo-sphere.ma`-resursen och väljer scenen `stage-helipad.ma`.

   Förhandsgranskningen fungerar på samma sätt som med `logo_sphere.fbx` och `stage-helipad.fbx`.

1. I närheten av sidans övre vänstra hörn trycker eller klickar du på listrutan och väljer **[!UICONTROL CRender]**.

   ![chlimage_1-54](assets/chlimage_1-54.png)

1. Välj **[!UICONTROL Autodesk Maya]** i listrutan **[!UICONTROL Renderer]** och tryck sedan på **[!UICONTROL Start Render]**.
1. I närheten av sidans övre högra hörn trycker eller klickar du på **[!UICONTROL Close]** för att gå tillbaka till vyn **[!UICONTROL Card]**.

   Lägg märke till meddelandebanderollen på den bildresurs som återges (`logo-sphere`, om inte ett annat bildnamn angavs). En förloppsindikator på banderollen visar återgivningsförloppet.

   >[!NOTE]
   >
   >Återgivning är mycket processorintensivt och kan ta flera minuter att slutföra

1. Öppna den återgivna bildresursen när återgivningen är klar.

   Kontrollera att den återgivna bilden stämmer överens med den bild du visade när du klickade på **[!UICONTROL Render Now]**.

## Aktivera ytterligare format som stöds av Maya {#enabling-additional-formats-supported-by-maya}

(Valfritt) Maya stöder ett antal 3D-indataformat, som alla kan aktiveras så att AEM känner igen filtypen. När det här alternativet är aktiverat skickar AEM filen till Maya för att konvertera den till ett mellanliggande format som kan importeras direkt av AEM.

Beroende på format kan det finnas begränsat stöd för funktioner (t.ex. material som inte skickas) och kvalitet/återgivning kan vara begränsad (t.ex. omvända ansikten). Adobe har endast stöd för den allmänna mekanismen, men inte för någon specifik formatkonvertering.

Se [Dataimportformat som stöds | Maya](https://knowledge.autodesk.com/support/maya/learn-explore/caas/CloudHelp/cloudhelp/2016/ENU/Maya/files/GUID-69BC066D-D4D8-4B12-900C-CF42E798A5D6-htm.html) för information om de format som stöds av Maya.

**Om du vill aktivera ytterligare format som stöds av AEM**:

1. Navigera till `/libs/settings/dam/v3D/assetTypes` med **[!UICONTROL CRXDE Lite]**.
1. Skapa en kopia av noden **[!UICONTROL jt]**. Högerklicka på noden **[!UICONTROL jt]** och välj **[!UICONTROL Copy]**. Högerklicka sedan på mappen **[!UICONTROL assetTypes]** och välj **[!UICONTROL Paste]**. Detta bör skapa en ny nod `/apps/cq-scene7-v3D/config/assetTypes/Copy of jt`.
1. Byt namn på den nya noden så att den får ett unikt namn som representerar den filtyp som ska läggas till. Filsuffixet kan användas eller någon annan unik identifierare.

1. Ange den nya nodens **[!UICONTROL Enabled]**-egenskap till `true`.

1. Ange egenskapen **[!UICONTROL Extension]** för den nya anteckningen till filsuffixet/filtillägget för det format som läggs till.
1. Ange ett lämpligt värde för egenskapen **[!UICONTROL MimeType]**. `application/x-` följt av värdet för  **[!UICONTROL Extension]** egenskapen bör fungera för de flesta filtyper.
1. Kontrollera att egenskapen **[!UICONTROL Conversion]** är inställd på `fbx` och **[!UICONTROL IngestRegime]** på `Maya`.
1. Klicka på **[!UICONTROL Save All]** uppe till vänster på sidan.

Följande skärmbild visar ett tillagt filformat med COLLADA DAE som exempel:

![image2018-6-22_12-50-39](assets/image2018-6-22_12-50-39.png)
