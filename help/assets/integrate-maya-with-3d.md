---
title: Integrera AEM 3D med Autodesk Maya
seo-title: Integrera AEM 3D med Autodesk Maya
description: Du kan även integrera AEM 3D med Autodesk® Maya® för att aktivera stöd för Maya-filer (.MA och .MB) och för att du ska kunna återge 3D-resurser i AEM med alla tillgängliga Maya-renderare.
seo-description: Du kan även integrera AEM 3D med Autodesk® Maya® för att aktivera stöd för Maya-filer (.MA och .MB) och för att du ska kunna återge 3D-resurser i AEM med alla tillgängliga Maya-renderare.
uuid: 07ff17b6-bdfc-4617-8b16-42aaf5c73fc7
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 3d063268-17d7-4db6-8028-682537645377
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

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

1. Installera Autodesk Maya 2016 på samma servrar där AEM ligger.

   Efter installationen bör du kontrollera att du kan öppna och använda Maya och att det inte finns några licensproblem.

   >[!NOTE]
   >
   >AEM använder bara kommandoradsåtergivning på Maya (`render.exe`). En enda Maya-nätverkslicens tillåter upp till fem servrar att bearbeta eller återge Maya-innehåll samtidigt.

1. Aktivera Autodesk FBX® Plug-In på Maya.
1. Installera plugin-programmet för MentalRay-rendering eller någon annan renderare.

   Efter installationen bör du kontrollera att MentalRay finns på Maya.

1. Lägg till sökvägen till den körbara mappen Maya i systemvariabeln Windows PATH.

   I Windows Server 2012 trycker du till exempel på **[!UICONTROL Start > Kontrollpanelen > System och säkerhet > System > Avancerade systeminställningar > Miljövariabler**. Lägg till den fullständiga sökvägen till `Maya2016\bin` mappen i `Path`systemvariabeln.

   ![chlimage_1-53](assets/chlimage_1-53.png)

1. Om du vill aktivera Maya för förtäring och återgivning öppnar du **[!UICONTROL CRXDE Lite]** och navigerar till `/libs/settings/dam/v3D/assetTypes/maya` och ställer in egenskapen **[!UICONTROL Enabled]** på `true`.

   ![image2018-6-22_12-42-7](assets/image2018-6-22_12-42-7.png)

1. Om du vill aktivera filformatet JT (Siemens PLM Open CAD) går du till `/libs/settings/dam/v3D/assetTypes/jt` och anger egenskapen **[!UICONTROL Enabled]** till `true`.
1. Aktivera Maya som renderare i AEM. Börja med att gå till **[!UICONTROL Verktyg > Allmänt > CRXDE Lite]**.
1. Gå till följande på **[!UICONTROL CRXDE Lite]** -sidan i den vänstra panelen:

   `/libs/settings/dam/v3D/renderers/maya`

   ![image2018-6-22_12-46-18](assets/image2018-6-22_12-46-18.png)

1. Ställ in egenskapen **[!UICONTROL Enabled]** på `true`.

1. I det övre vänstra hörnet av **[!UICONTROL CRXDE Lite]** -sidan trycker du på **[!UICONTROL Spara alla]**.

   Maya är nu aktiverat som renderare.

## Testa integrationen av AEM 3D med Autodesk Maya {#testing-the-integration-of-aem-d-with-autodesk-maya}

1. Öppna AEM Resurser och överför sedan `.MA` filerna som finns i `sample-3D-content/models` till `test3d` mappen.

   Observera att du `sample-3D-content.zip` laddat ned tidigare för att validera de grundläggande 3D-funktionerna.

1. Gå tillbaka till vyn **[!UICONTROL-kort** och observera de meddelandebanners som visas på de överförda resurserna.

   Banderollen för konverteringsformat visas medan Maya konverterar det ursprungliga `.MA` formatet till `.FBX`.

1. När all bearbetning är klar öppnar du `logo-sphere.ma` resursen och väljer `stage-helipad.ma` scenen.

   Förhandsgranskningen fungerar på samma sätt som med `logo_sphere.fbx` och `stage-helipad.fbx`.

1. I närheten av sidans övre vänstra hörn trycker eller klickar du på listrutan och väljer sedan **[!UICONTROL CRender]**.

   ![chlimage_1-54](assets/chlimage_1-54.png)

1. I listrutan **[!UICONTROL Återgivning]** väljer du **[!UICONTROL Autodesk Maya]** och trycker sedan på **[!UICONTROL Starta återgivning]**.
1. I närheten av sidans övre högra hörn: tryck eller klicka på **[!UICONTROL Stäng]** för att återgå till **[!UICONTROL kortvyn]** .

   Lägg märke till meddelandebanderollen på den bildresurs som återges (`logo-sphere`om inte ett annat bildnamn har angetts). En förloppsindikator på banderollen visar återgivningsförloppet.

   >[!NOTE]
   >
   >Återgivning är mycket processorintensivt och kan ta flera minuter att slutföra

1. Öppna den återgivna bildresursen när återgivningen är klar.

   Kontrollera att den återgivna bilden på ett rimligt sätt matchar den bild du visade när du klickade på **[!UICONTROL Återge nu]**.

## Aktivera ytterligare format som stöds av Maya {#enabling-additional-formats-supported-by-maya}

(Valfritt) Maya stöder ett antal 3D-indataformat, som alla kan aktiveras så att AEM känner igen filtypen. När AEM är aktiverat skickas filen till Maya för att konvertera den till ett mellanliggande format som kan importeras direkt av AEM.

Beroende på format kan det finnas begränsat stöd för funktioner (t.ex. material som inte skickas) och kvalitet/återgivning kan vara begränsad (t.ex. omvända ansikten). Adobe stöder bara den allmänna mekanismen, men inte någon specifik formatkonvertering.

Se [Dataimportformat som stöds| Maya](https://knowledge.autodesk.com/support/maya/learn-explore/caas/CloudHelp/cloudhelp/2016/ENU/Maya/files/GUID-69BC066D-D4D8-4B12-900C-CF42E798A5D6-htm.html) för information om de format som stöds av Maya.

**Om du vill aktivera ytterligare format som stöds av AEM**:

1. Navigera till **[!UICONTROL CRXDE Lite]**`/libs/settings/dam/v3D/assetTypes`.
1. Gör en kopia av den **[!UICONTROL jt]** -noden. Högerklicka på den **[!UICONTROL jt]** -noden och välj **[!UICONTROL Kopiera]**. Högerklicka sedan på mappen **[!UICONTROL assetTypes]** och välj **[!UICONTROL Klistra in]**. Detta bör skapa en ny nod `/apps/cq-scene7-v3D/config/assetTypes/Copy of jt`.
1. Byt namn på den nya noden så att den får ett unikt namn som representerar den filtyp som ska läggas till. Filsuffixet kan användas eller någon annan unik identifierare.

1. Ange den nya nodens **[!UICONTROL aktiverade]** egenskap som `true`.

1. Ange **[!UICONTROL tilläggsegenskapen]** för den nya anteckningen till filsuffixet/filtillägget för det format som läggs till.
1. Ställ in **[!UICONTROL MimeType]** -egenskapen på ett lämpligt värde. `application/x-` följt av värdet för egenskapen **[!UICONTROL Extension]** bör fungera för de flesta filtyper.
1. Kontrollera att egenskapen **[!UICONTROL Conversion]** är inställd på `fbx` och **[!UICONTROL IngestRegime]** på `Maya`.
1. Klicka på **[!UICONTROL Spara alla]** uppe till vänster på sidan.

Följande skärmbild visar ett tillagt filformat med COLLADA DAE som exempel:

![image2018-6-22_12-50-39](assets/image2018-6-22_12-50-39.png)

