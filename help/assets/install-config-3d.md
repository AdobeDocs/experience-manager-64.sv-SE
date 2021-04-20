---
title: Installera och konfigurera AEM 3D
seo-title: Installera och konfigurera AEM 3D
description: Lär dig installera och konfigurera AEM 3D
seo-description: Lär dig installera och konfigurera AEM 3D
uuid: a60732ff-fd66-4f29-b901-42a3cfd58b65
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 5898d084-4b45-41bc-ad2e-2fcc65b0392c
exl-id: 5baaef61-5c70-4796-8ae2-44053e855ad9
feature: 3D Assets
role: Administrator,Business Practitioner
translation-type: tm+mt
source-git-commit: 13eb1d64677f6940332a2eeb4d3aba2915ac7bba
workflow-type: tm+mt
source-wordcount: '1584'
ht-degree: 1%

---

# Installera och konfigurera AEM 3D {#installing-and-configuring-aem-d}

>[!IMPORTANT]
>
>AEM 3D i AEM 6.4 stöds inte längre. Adobe rekommenderar att du använder funktionen 3D-resurser i [AEM som en Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html#dynamicmedia) eller [AEM 6.5.3 eller senare.](https://experienceleague.adobe.com/docs/experience-manager-65/assets/dynamic/assets-3d.html#dynamic)

Installation och konfigurering av AEM 3D (version 3.0) innefattar följande:

1. Installera Autodesk® FBX® SDK-biblioteket.
1. Hämta och installera det inbyggda 3D-kodpaketet.
1. Konfigurerar arbetsflödet för inmatning av 3D-resurser och startar om AEM.
1. Validerar inställningen av AEM 3D.

Se även [Arbeta med 3D-resurser](assets-3d.md).

Se även [AEM Versionsinformation för 3D-resurser](/help/release-notes/aem3d-release-notes.md) för information om krav, webbläsare som stöds och annan viktig versionsinformation.

Se även [Arbeta med 3D-platskomponenten](using-the-3d-sites-component.md).

>[!NOTE]
>
>Innan du hämtar och installerar 3D-paketet kontrollerar du att du har installerat alla AEM som krävs. Se [AEM 3D Release Notes.](install-config-3d.md)

## Installera Autodesk FBX SDK-biblioteket {#installing-the-autodesk-fbx-sdk-library}

Den inbyggda AEM 3D-koden kräver Autodesk FBX-biblioteket för att stödja FBX-filformatet. (Adobe kan inte återdistribuera det här biblioteket.)

Se även [Avancerade konfigurationsinställningar](advanced-config-3d.md).

1. Logga in på värddatorn där AEM är installerad.

   * Om det här är en Windows Server-distribution loggar du in på servern som administratör.
   * Om det här är ett Mac- eller Windows-skrivbord måste du ha administratörsbehörighet.

1. Använd den länk som är lämplig för ditt operativsystem för att hämta **FBX SDK version 2016.1.2**

   * **Windows**

      [https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_vs2010_win.exe](https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_vs2010_win.exe)

   * **OS X**

      [https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_clang_mac.pkg.tgz](https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_clang_mac.pkg.tgz)

   * **Linux**

      [https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_linux.tar.gz](https://download.autodesk.com/us/fbx_release_older/2016.1.2/fbx20161_2_fbxsdk_linux.tar.gz)

1. Installera FBX SDK:

   * Windows. Installera på den enhet där AEM finns.
   * Mac. Installera på samma partition där AEM finns.
   * Linux. Extrahera det hämtade paketet och följ instruktionerna i `<yourFBXSDKpath>/Install_FbxFileSdk.txt`. Installera SDK till `/usr`.

## Hämta och installera det inbyggda 3D-kodpaketet {#downloading-and-installing-the-native-d-code-package}

>[!NOTE]
>
>Innan du fortsätter med installationen och konfigurationen av AEM 3D rekommenderar Adobe att du distribuerar alla tillämpliga servicepaket och andra relaterade funktionspaket. Se [AEM 3D-versionsinformation](/help/release-notes/aem3d-release-notes.md).

Se även [Avancerade konfigurationsinställningar](advanced-config-3d.md).

**Så här installerar du det inbyggda 3D-kodpaketet**:

1. Gör något av följande:

   * Om det här är en Windows Server-distribution loggar du in på servern som administratör.
   * Om det här är ett Mac- eller Windows-skrivbord måste du ha administratörsbehörighet.

1. Se till att du har en webbläsare som stöds tillgänglig för AEM.

   Se [Systemkrav](/help/release-notes/aem3d-release-notes.md#system-requirements).

1. Få åtkomst till [portalen för programvarudistribution](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html). Leta rätt på version 3.0.1 av `AEM-6.4-DynamicMedia-3D`-funktionspaketet och ladda ned det.

1. Klicka på **[!UICONTROL Tools > Administration > Deployment > Package Manager]** i AEM.

1. Överför det hämtade funktionspaketet till AEM. Leta reda på den och klicka på **[!UICONTROL Install]**.

1. Expandera **Avancerade inställningar** i dialogrutan **[!UICONTROL Install Package]** och ange **[!UICONTROL Access Control Handling]** till **Sammanfoga**.
1. Klicka på **[!UICONTROL Install]** för att påbörja installationen av paketet.

   Filen `sample-3D-content.zip` placeras i rotmappen **[!UICONTROL Assets]**. Mer information finns i [Validera inställningen av AEM 3D](#validating-the-setup-of-aem-d).

## Konfigurera arbetsflödet för att lägga till 3D-resurser och starta om AEM {#configuring-the-d-asset-ingestion-workflow-and-restarting-aem}

**Så här konfigurerar du arbetsflödet** för 3D-tillgångsinmatning:

1. I AEM klickar du på den AEM logotypen för att komma åt den globala navigeringskonsolen, klickar sedan på ikonen **[!UICONTROL Tools]** och navigerar till **[!UICONTROL Workflow > Models]**.
1. På sidan **[!UICONTROL Workflow Models]** för du muspekaren över arbetsflödet för **[!UICONTROL DAM Update Asset]** och när markeringen visas markerar du den.

1. Klicka på **[!UICONTROL Edit]** i verktygsfältet.
1. På skärmen **[!UICONTROL DAM Update Asset]** klickar du på ikonen **[!UICONTROL Plus]** till höger om arbetsflödet på den AEM flytande panelen för att utöka listan. Välj **[!UICONTROL Process Step]** i listan.
1. Dra **[!UICONTROL Process Step]** och släpp den i arbetsflödet precis före **[!UICONTROL DAM Update Asset Workflow Completed]**-komponenten i slutet av arbetsflödet.

   ![3d_process_step_underaem6-4](assets/3d_process_step_underaem6-4.png)

1. Dubbelklicka på det nya processsteget.
1. I dialogrutan **[!UICONTROL Step Properties]**, under fliken **[!UICONTROL Common]** i fältet **[!UICONTROL Title]**, anger du en lämplig beskrivning för processen, till exempel `Process 3D content`.
1. Klicka på fliken **[!UICONTROL Process]**.

1. Välj **[!UICONTROL Geometric 3D Object Service]** i listrutan **[!UICONTROL Process]** och markera sedan kryssrutan **[!UICONTROL Handler Advance]**.

   ![3d_install-process-steppropertiesdlg](assets/3d_install-process-steppropertiesdlg.png)

1. Klicka på bockmarkeringsikonen i dialogrutans övre högra hörn för att gå tillbaka till sidan DAM-uppdatering.
1. Klicka på **[!UICONTROL Sync]** längst upp till höger på sidan **[!UICONTROL DAM Update Asset]** för att spara den redigerade arbetsflödesmodellen.
1. Starta om AEM.

   Efter omstart är du redo att överföra 3D-innehåll och måste AEM bearbeta det.

   Fortsätt med [Verifiera installationen av AEM 3D](#validating-the-setup-of-aem-d).

## Verifierar inställningen av AEM 3D {#validating-the-setup-of-aem-d}

1. I AEM klickar du på **[!UICONTROL Tools > Assets]**, hämtar `sample-3D-content.zip` och expanderar den hämtade filen. (Du kan nu ta bort `sample-3D-content.zip` i AEM.)

   Se till att du är i **[!UICONTROL Card View]** för att visa överföring och bearbetning av feedback i de återstående stegen.

1. Skapa en mapp med namnet `test3d` för att ta emot testinnehåll.
1. Överför alla filer från `sample-3D-content/images` till mappen `test3d`.
1. Vänta tills överföringen och bearbetningen är klar. Du kan behöva uppdatera webbläsaren.

   Överför de tre `.fbx`-filerna från `sample-3D-content/` till mappen `test3d`.

   Överför inte .ma-modellfilerna ännu.

1. I kortvyn kan du titta på de meddelandebanderoller som visas på 3D-resurskortet.

   Varje resurs går igenom flera bearbetningssteg. När **[!UICONTROL Creating Preview...]**-bearbetningssteget har slutförts uppdateras kortet med en miniatyrbild. När den slutliga bearbetningen är klar ersätts banderollen med indikatorn **[!UICONTROL NEW]**.

   >[!NOTE]
   >
   >Förvänta dig mycket hög processoranvändning medan 3D-bearbetning pågår. Beroende på tillgänglig processorkapacitet kan det ta lång tid att slutföra all bearbetning.

   ![screenshot_2017-01-2518-29-32](assets/screenshot_2017-01-2518-29-32.png)

1. Nu får du lära dig att lösa filberoenden.

   På **[!UICONTROL Unresolved Dependencies]**-banderollen för `stage-helipad.fbx`-kortet klickar du på ikonen **[!UICONTROL Exclamation Point]** för att navigera till resursens egenskaper och öppna fliken **Beroenden**.

   ![chlimage_1-372](assets/chlimage_1-372.png)

1. Klicka på ikonen **[!UICONTROL Folder/Magnifying Glass]** till höger om filnamnet för att öppna resursläsaren och lösa beroendena enligt följande:

   ![chlimage_1-373](assets/chlimage_1-373.png)

1. Klicka på **[!UICONTROL Save]** och **[!UICONTROL Close]** för att slutföra bearbetningen av resursen och återgå till **[!UICONTROL Card View]**.
1. När bearbetningen är klar visas följande i **[!UICONTROL Card View]**:

   ![chlimage_1-374](assets/chlimage_1-374.png)

1. På test3d-sidan klickar du på `logo-sphere.fbx`-kortet för att öppna modellen i **[!UICONTROL Detail View]**.

   I närheten av det övre högra hörnet av sidan logo-sphere.fbx klickar du på ikonen Stage Spotlight för att expandera listrutan och väljer sedan `stage-spotlights.fbx`.

   ![chlimage_1-375](assets/chlimage_1-375.png)

1. I listrutan **[!UICONTROL Stage Spotlight]** väljer du `stage-helipad.fbx`.

   Justera vyn med vänster musknapp. Bakgrunds- och modellljussättningen ändras för att återspegla den nya scenmarkeringen.

   ![chlimage_1-376](assets/chlimage_1-376.png)

## Konfigurera stöd för Adobe Dimension-resurser {#configuring-support-for-adobe-dimension-assets}

>[!NOTE]
>
>Den här konfigurationsaktiviteten är valfri.

Du kan också konfigurera stöd i AEM 3D för Adobe Dimension-resurser.

Du måste konfigurera en extern konverteringstjänst så att den tillåter inhämtning, förhandsgranskning och publicering av Adobe Dimension 3D-resurser i AEM. Tjänsten konverterar från det egna Adobe Dimension-formatet (`.dn`) till en variant av glTF (formaterad som en `.glb`-fil) som sparas med Dn-resursen som en återgivning. `.glb`-renderingen används för webbaserad visning av 3D-resursen i AEM Assets, Sites och Screens och kan även hämtas för användning med tredjepartsprogram.

>[!NOTE]
>
>Adobe är värd för konverteringstjänsten i Amazon AWS. Efter att tjänsten konfigurerats korrekt kopieras `.dn` filer som överförts till AEM på ett säkert sätt till konverteringstjänsten via tillfällig lagring i Amazon S3. Konverteringsresultatet överförs tillbaka till AEM via temporär S3-lagring. Alla överföringar och lagring är skyddade. Innehållet finns också kvar i S3 och konverteringstjänsten är bara kort (vanligtvis inte längre än några minuter).

**Så här konfigurerar du stöd för Adobe Dimension-resurser**:

1. Kontakta kontohanteraren, provisioneringsexperten eller supportrepresentanten för Adobe för att begära inloggningsuppgifter för **AEM3D-tjänster**.

   >[!NOTE]
   >
   >Endast en uppsättning autentiseringsuppgifter krävs för varje organisation, oavsett hur många AEM som autentiseringsuppgifterna är installerade på.

1. Kontrollera att du har fått följande information:

   * accountId
   * customerId
   * password
   * identityPoolId
   * userPoolId
   * clientId

1. Som administratör loggar du in på den AEM författarinstansen där du vill ha inloggningsuppgifterna installerade och öppnar sedan **[!UICONTROL CRXDE Lite]**.
1. Konfigurera den nya inloggningsinformationen genom att göra följande i CRXDE Lite:

   1. Navigera till `/libs/settings/dam/v3D/services/dncr` och ställ in egenskapen `clientId` på det nya värdet.
   1. Navigera till `/libs/settings/dam/v3D/services/aws` och ställ in egenskaperna `accountId`, `customerId`, `identityPoolId` och `userPoolId` på de nya värdena.
   1. Läs in det nya lösenordsvärdet i egenskapen `encryptedPassword`. Det här värdet krypteras automatiskt när du trycker på **[!UICONTROL Save All]**.
   1. Tryck på **[!UICONTROL Save All]**, läs in sidan igen och kontrollera sedan att egenskapen `encryptedPassword` visar en annan sträng omsluten av klammerparenteser. Det här utseendet visar att lösenordet är korrekt krypterat och säkert.

1. Ange formatet för konverteringsrenderingen `.glb` genom att göra följande i **[!UICONTROL CRXDE Lite]**:

   1. Navigera till `/libs/settings/dam/v3D/services/dncr` i **[!UICONTROL CRXDE Lite]**.
   1. Ange egenskapen `outputFormat` till antingen `Dn` eller `generic`.

      När `Dn` är inställt på `.glb` innehåller konverteringen Adobe-specifika tillägg, som IBL-ljus, för bästa kvalitet när du visar Dn-resurser i AEM. Den konverterade .glb-renderingen kanske inte återges bra i tredjepartsprogram.

      Om `generic` anges är `.glb`-återgivningen generisk utan Adobe-specifika tillägg. Med den här inställningen kan den användas i tredjepartsprogram, medan visning med AEM 3D-visningsprogram blir visuellt suboptimalt.

1. Aktivera Dn-filformatet genom att göra följande i **[!UICONTROL CRXDE Lite]**:

   1. Navigera till `/libs/settings/dam/v3D/assetTypes/Dn`.
   1. Ställ in egenskapen `Enabled` på true.

1. Validera konfigurationen genom att göra följande:

   1. Öppna AEM Assets.
   1. Överför `logo_sphere.dn` till mappen `test3d`. Filen finns i `sample-3D-content/models`.

      Observera att `sample-3D-content.zip` tidigare hämtades för validering av de grundläggande 3D-funktionerna.
   1. Gå tillbaka till **[!UICONTROL Card View]** och observera den meddelandebanderoll som visas på den överförda resursen. Banderollen **[!UICONTROL Converting Format...]** visas medan konverteringsprocessen pågår.
   1. När all bearbetning är klar öppnar du resursen i **[!UICONTROL Detail View]** för att verifiera att den konverterade resursen visas korrekt och att visningsprogrammets navigeringskontroller är användbara.

   ![image2018-11-2_15-51-19](assets/image2018-11-2_15-51-19.png)

   Om ett &quot;Bearbetningsfel&quot; visas på Dn-resursen i **[!UICONTROL Card View]** efter 10-15 minuter misslyckades konverteringen.

   Om så är fallet kan du felsöka konverteringen genom att göra följande:

   * Ta bort resursen och överför den sedan igen.
   * Kontrollera att du har angett alla konfigurationsparametrar korrekt i **[!UICONTROL CRXDE Lite]**.
   * Kontrollera att ingen brandvägg blockerar åtkomst till konverteringstjänsten och AWS-slutpunkter.
