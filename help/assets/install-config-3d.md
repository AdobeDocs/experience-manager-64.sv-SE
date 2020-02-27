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
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Installera och konfigurera AEM 3D {#installing-and-configuring-aem-d}

Installation och konfiguration av AEM 3D (version 3.0) innefattar följande:

1. Installera Autodesk® FBX® SDK-biblioteket.
1. Hämta och installera det inbyggda 3D-kodpaketet.
1. Konfigurerar arbetsflödet för att hämta 3D-resurser och startar om AEM.
1. Verifierar installationen av AEM 3D.

Se även [Arbeta med 3D-resurser](assets-3d.md).

Se även [AEM 3D Assets versionsinformation](/help/release-notes/aem3d-release-notes.md) för information om krav, webbläsare som stöds och annan viktig versionsinformation.

Se även [Arbeta med komponenten](using-the-3d-sites-component.md)3D-platser.

>[!NOTE]
>
>Innan du hämtar och installerar 3D-paketet kontrollerar du att du har installerat alla nödvändiga AEM-paket korrekt. Se versionsinformationen för [AEM 3D.](install-config-3d.md)

## Installera Autodesk FBX SDK-biblioteket {#installing-the-autodesk-fbx-sdk-library}

Den inbyggda AEM 3D-koden kräver Autodesk FBX-biblioteket för att stödja FBX-filformatet. (Adobe kan för närvarande inte återdistribuera det här biblioteket.)

Se även [Avancerade konfigurationsinställningar](advanced-config-3d.md).

1. Logga in på värddatorn där AEM är installerat.

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
   * Linux. Extrahera det hämtade paketet och följ instruktionerna i `<yourFBXSDKpath>/Install_FbxFileSdk.txt`. Installera SDK i `/usr`.

## Hämta och installera det inbyggda 3D-kodpaketet {#downloading-and-installing-the-native-d-code-package}

>[!NOTE]
>
>Innan du fortsätter med installationen och konfigurationen av AEM 3D rekommenderar Adobe att du distribuerar alla tillämpliga servicepaket och andra relaterade funktionspaket. Se [Versionsinformation](/help/release-notes/aem3d-release-notes.md)för AEM 3D.

Se även [Avancerade konfigurationsinställningar](advanced-config-3d.md).

**Så här installerar du det inbyggda 3D-kodpaketet**:

1. Gör något av följande:

   * Om det här är en Windows Server-distribution loggar du in på servern som administratör.
   * Om det här är ett Mac- eller Windows-skrivbord kontrollerar du att du har administratörsbehörighet.

1. Kontrollera att du har en webbläsare som stöds tillgänglig för att komma åt AEM.

   Se [Systemkrav](/help/release-notes/aem3d-release-notes.md#system-requirements).

1. Logga in på AEM med administratörsbehörighet i en webbläsare som stöds.
1. I AEM klickar du på AEM-logotypen för att komma åt den globala navigeringskonsolen, klickar sedan på **[!UICONTROL verktygsikonen]** och går till **[!UICONTROL Administration > Distribution > Paketdelning]**.
1. På Adobe-sidan använder du dina Adobe ID-uppgifter för att logga in på ditt Adobe Creative Cloud-konto.
1. Gå till version 3.0.1 av funktionspaketet på sidan Adobe-paket och ladda sedan ned det `AEM-6.4-DynamicMedia-3D` .

1. I AEM klickar du på **[!UICONTROL Verktyg > Administration > Distribution > Pakethanteraren]**.
1. Leta reda på det hämtade funktionspaketet och klicka sedan på **[!UICONTROL Installera]**.

1. Expandera **[!UICONTROL Avancerade inställningar]** i dialogrutan **Installera paket** och ange **[!UICONTROL Åtkomstkontrollhantering]** till **Sammanfoga**.
1. Klicka på **[!UICONTROL Installera]** för att påbörja installationen av paketet.

   Filen `sample-3D-content.zip` placeras i rotmappen **[!UICONTROL Resurser]** . Mer information finns i [Validera installationen av AEM 3D](#validating-the-setup-of-aem-d) .

## Konfigurera arbetsflödet för inhämtning av 3D-resurser och starta om AEM {#configuring-the-d-asset-ingestion-workflow-and-restarting-aem}

**Så här konfigurerar du arbetsflödet** för 3D-tillgångsinmatning:

1. I AEM klickar du på AEM-logotypen för att komma åt den globala navigeringskonsolen, klickar sedan på **[!UICONTROL verktygsikonen]** och navigerar till **[!UICONTROL Arbetsflöde > Modeller]**.
1. På sidan **[!UICONTROL Arbetsflödesmodeller]** för du muspekaren över arbetsflödet för **[!UICONTROL DAM-uppdatering av resurs]** och markerar det när markeringen visas.

1. Klicka på **[!UICONTROL Redigera]** i verktygsfältet.
1. På skärmen **[!UICONTROL DAM Update Asset]** klickar du på **** plusikonen till höger om arbetsflödet på den flytande AEM-panelen för att utöka listan. Välj **[!UICONTROL Processsteg]** i listan.
1. Dra **[!UICONTROL Processsteg]** och släpp det i arbetsflödet precis innan komponenten **[!UICONTROL DAM Update Asset Workflow Completed]** är klar i slutet av arbetsflödet.

   ![3d_process_step_underaem6-4](assets/3d_process_step_underaem6-4.png)

1. Dubbelklicka på det nya processsteget.
1. I dialogrutan **[!UICONTROL Stegegenskaper]** , under fliken **[!UICONTROL Allmänt]** , i fältet **[!UICONTROL Titel]** , anger du en lämplig beskrivning av processen, till exempel `Process 3D content`.
1. Klicka på fliken **[!UICONTROL Process]** .

1. I listrutan **[!UICONTROL Process]** väljer du **[!UICONTROL Geometrisk 3D-objekttjänst]** och markerar kryssrutan **[!UICONTROL Avancerat]** för hanterare.

   ![3d_install-process-steppropertiesdlg](assets/3d_install-process-steppropertiesdlg.png)

1. Klicka på bockmarkeringsikonen i dialogrutans övre högra hörn för att gå tillbaka till sidan DAM-uppdatering.
1. Klicka på **[!UICONTROL Synkronisera]** för att spara den redigerade arbetsflödesmodellen nära det övre högra hörnet på sidan **[!UICONTROL DAM-uppdatering av resurser]** .
1. Starta om AEM.

   Efter omstart är du redo att överföra 3D-innehåll och låta AEM bearbeta det.

   Fortsätt med [valideringen av installationen av AEM 3D](#validating-the-setup-of-aem-d).

## Validera installationen av AEM 3D {#validating-the-setup-of-aem-d}

1. I AEM klickar du på **[!UICONTROL Verktyg > Resurser]**, hämtar `sample-3D-content.zip`och expanderar den hämtade filen. (Du kan nu ta bort `sample-3D-content.zip` i AEM.)

   Se till att du är i **[!UICONTROL kortvyn]** för att visa överföring och bearbetning av feedback i återstående steg.

1. Skapa en mapp med namnet `test3d` för att ta emot testinnehåll.
1. Överför alla filer från `sample-3D-content/images` till `test3d` mappen.
1. Vänta tills överföringen och bearbetningen är klar. Du kan behöva uppdatera webbläsaren.

   Överför de tre `.fbx` filerna från `sample-3D-content/` till `test3d` mappen.

   Överför inte .ma-modellfilerna ännu.

1. I kortvyn kan du titta på de meddelandebanderoller som visas på 3D-resurskortet.

   Varje resurs går igenom flera bearbetningssteg. **[!UICONTROL När förhandsgranskningen]** skapas.. när bearbetningen är klar uppdateras kortet med en miniatyrbild. När slutbearbetningen är klar ersätts banderollen med indikatorn **[!UICONTROL NEW]** .

   >[!NOTE]
   >
   >Förvänta dig mycket hög processoranvändning medan 3D-bearbetning pågår. Beroende på tillgänglig processorkapacitet kan det ta lång tid att slutföra all bearbetning.

   ![screenshot_2017-01-2518-29-32](assets/screenshot_2017-01-2518-29-32.png)

1. Nu får du lära dig att lösa filberoenden.

   På banderollen **[!UICONTROL Olösta beroenden]** för `stage-helipad.fbx` kortet klickar du på ikonen **[!UICONTROL Utropstecken]** för att navigera till resursens egenskaper och öppna fliken **Beroenden** .

   ![chlimage_1-372](assets/chlimage_1-372.png)

1. Klicka på ikonen **[!UICONTROL Mapp/förstoringsglas]** till höger om filnamnet för att öppna resursläsaren och lösa beroendena enligt följande:

   ![chlimage_1-373](assets/chlimage_1-373.png)

1. Klicka på **[!UICONTROL Spara]** och **[!UICONTROL Stäng]** för att slutföra bearbetningen av resursen och återgå till **[!UICONTROL kortvyn]**.
1. När bearbetningen är klar visas följande i **[!UICONTROL kortvyn]**:

   ![chlimage_1-374](assets/chlimage_1-374.png)

1. På test3d-sidan klickar du på `logo-sphere.fbx` kortet för att öppna modellen i **[!UICONTROL detaljvyn]**.

   I närheten av det övre högra hörnet av sidan logo-sphere.fbx klickar du på ikonen Stage Spotlight för att expandera listrutan och väljer sedan `stage-spotlights.fbx`.

   ![chlimage_1-375](assets/chlimage_1-375.png)

1. I listrutan **[!UICONTROL Strålkastare]** väljer du `stage-helipad.fbx`.

   Justera vyn med vänster musknapp. Bakgrunds- och modellljussättningen ändras för att återspegla den nya scenmarkeringen.

   ![chlimage_1-376](assets/chlimage_1-376.png)

## Konfigurera stöd för Adobe Dimension-resurser {#configuring-support-for-adobe-dimension-assets}

>[!NOTE]
>
>Den här konfigurationsaktiviteten är valfri.

Du kan också konfigurera stöd i AEM 3D för Adobe Dimension-resurser.

Du måste konfigurera en extern konverteringstjänst så att Adobe Dimension 3D-resurser kan hämtas, förhandsgranskas och publiceras i AEM. Tjänsten konverterar från det egna Adobe Dimension-formatet (`.dn`) till en variant av glTF (formaterad som en `.glb` fil) som sparas med resursen Dn som en rendering. Renderingen används för webbaserad visning av 3D-resursen i AEM Assets, Sites och Screens och kan även hämtas för användning med tredjepartsprogram. `.glb`

>[!NOTE]
>
>Adobe är värd för konverteringstjänsten i Amazon AWS. När tjänsten har konfigurerats på rätt sätt kopieras filer som har överförts till AEM på ett säkert sätt till konverteringstjänsten genom tillfällig lagring i Amazon S3. `.dn` Konverteringsresultatet överförs tillbaka till AEM genom temporär S3-lagring. Alla överföringar och lagring är skyddade. Innehållet finns också kvar i S3 och konverteringstjänsten är bara kort (vanligtvis inte längre än några minuter).

**Så här konfigurerar du stöd för Adobe Dimension-resurser**:

1. Kontakta er kontoansvarige på Adobe AEM, er provisioneringsexpert eller supportrepresentant för att begära inloggningsuppgifter för **AEM3D-tjänster**.

   >[!NOTE]
   >
   >Endast en uppsättning autentiseringsuppgifter krävs för varje organisation, oavsett hur många AEM-instanser autentiseringsuppgifterna är installerade på.

1. Kontrollera att du har fått följande information:

   * accountId
   * customerId
   * password
   * identityPoolId
   * userPoolId
   * clientId

1. Som administratör loggar du in på den AEM-författarinstans där du vill ha inloggningsuppgifterna installerade och öppnar sedan **[!UICONTROL CRXDE Lite]**.
1. Konfigurera den nya inloggningsinformationen genom att göra följande i CRXDE Lite:

   1. Navigera till `/libs/settings/dam/v3D/services/dncr` och ställ in `clientId` egenskapen på det nya värdet.
   1. Navigera till `/libs/settings/dam/v3D/services/aws` och ange egenskaperna `accountId`, `customerId`, `identityPoolId`och `userPoolId` till de nya värdena.
   1. Läs in det nya lösenordsvärdet i `encryptedPassword` egenskapen. Det här värdet krypteras automatiskt när du trycker på **[!UICONTROL Spara alla]**.
   1. Tryck på **[!UICONTROL Spara alla]**, läs in sidan igen och kontrollera sedan att `encryptedPassword` egenskapen visar en annan sträng omsluten av klammerparenteser. Det här utseendet visar att lösenordet är korrekt krypterat och säkert.

1. Ange formatet för `.glb` konverteringsrenderingen genom att göra följande i **[!UICONTROL CRXDE Lite]**:

   1. Navigera till `/libs/settings/dam/v3D/services/dncr` i **[!UICONTROL CRXDE Lite]**.
   1. Ange `outputFormat` egenskapen till antingen `Dn` eller `generic`.

      När konverteringen är inställd på `Dn``.glb` innehåller den Adobe-specifika tillägg, till exempel IBL-ljus, för bästa kvalitet när du visar Dn-resurser i AEM. Den konverterade .glb-renderingen kanske inte återges bra i tredjepartsprogram.

      När den anges till `generic`är `.glb` återgivningen generisk utan Adobe-specifika tillägg. Med den här inställningen kan den användas i tredjepartsprogram, medan visning med AEM 3D-visningsprogrammet blir visuellt suboptimalt.

1. Aktivera Dn-filformatet genom att göra följande i **[!UICONTROL CRXDE Lite]**:

   1. Navigera till `/libs/settings/dam/v3D/assetTypes/Dn`.
   1. Ställ in egenskapen på true `Enabled` .

1. Validera konfigurationen genom att göra följande:

   1. Öppna AEM Resurser.
   1. Överför `logo_sphere.dn` till `test3d` mappen. Filen finns i `sample-3D-content/models`.

      Observera att du `sample-3D-content.zip` laddat ned tidigare för att validera de grundläggande 3D-funktionerna.
   1. Gå tillbaka till **[!UICONTROL kortvyn]** och observera den meddelandebanderoll som visas på den överförda resursen. **[!UICONTROL Konverterar]** format.. bannern visas medan konverteringsprocessen pågår.
   1. När all bearbetning är klar öppnar du resursen i **[!UICONTROL detaljvyn]** för att kontrollera att den konverterade resursen visas korrekt och att visningsprogrammets navigeringskontroller är användbara.
   ![image2018-11-2_15-51-19](assets/image2018-11-2_15-51-19.png)

   Om ett &quot;bearbetningsfel&quot; visas på Dn-resursen i **[!UICONTROL kortvyn]** efter 10-15 minuter misslyckades konverteringen.

   Om så är fallet kan du felsöka konverteringen genom att göra följande:

   * Ta bort resursen och överför den sedan igen.
   * Kontrollera att du har angett alla konfigurationsparametrar korrekt i **[!UICONTROL CRXDE Lite]**.
   * Kontrollera att ingen brandvägg blockerar åtkomst till konverteringstjänsten och AWS-slutpunkter.
