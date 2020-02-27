---
title: Avancerade konfigurationsinställningar
seo-title: Avancerade konfigurationsinställningar
description: Lär dig mer om avancerade konfigurationsinställningar som gäller för integrering av AEM 3D för både Maya- och icke-Maya-distributioner.
seo-description: Lär dig mer om avancerade konfigurationsinställningar som gäller för integrering av AEM 3D för både Maya- och icke-Maya-distributioner.
uuid: 016e7745-e3c3-4d77-b95a-c0e671d719e2
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: e43fd002-2954-4ef1-ac2b-e8d45afa75be
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Avancerade konfigurationsinställningar {#advanced-configuration-settings}

Även om standardkonfigurationsinställningarna är lämpliga för vanliga fall kan det i vissa fall krävas att du gör ändringar.

Följande avancerade konfigurationsinställningar gäller för integrering av AEM 3D för både Maya- och icke-Maya-distributioner.

Alla inställningar nås med **CRXDE Lite** i AEM (**[!UICONTROL Verktyg > Allmänt > CRXDE Lite]**).

>[!NOTE]
>
>Om du installerar om paketet återställs alla inställningar till standardvärdena.

>[!CAUTION]
>
>Om du redigerar inställningar som inte finns med i tabellen nedan kan det leda till oväntade eller oönskade programbeteenden.

## Konfiguration av tillgångstyper {#asset-types-configuration}

I **CRXDE Lite** in AEM (**[!UICONTROL Verktyg > Allmänt > CRXDE Lite]**), gå till följande konfigurationer:

| Bana | Beskrivning |
|---|---|
| `/libs/settings/dam/v3D/assetTypes/*/Conversion` | Anger filtypen för det mellanliggande 3D-formatet som skapas vid importen. Måste vara tomt för filformaten fbx och obj eller fbx för format som aktiveras av Maya. |
| `/libs/settings/dam/v3D/assetTypes/*/Enabled` | Ange som true eller false om du vill aktivera eller inaktivera den här posten i listan **[!UICONTROL assetTypes]** . |
| `/libs/settings/dam/v3D/assetTypes/*/Extension` | Ange ett eller flera kommaavgränsade filsuffix eller filtillägg som ska associeras med den här resurstypen. |
| `/libs/settings/dam/v3D/assetTypes/*/IngestRegime` | Måste vara `native` för filformaten FBX och OBJ och `maya` för format som aktiveras av Maya. |
| `/libs/settings/dam/v3D/assetTypes/*/MimeType` | Anger MIME-typen för den här resurstypen. För format som aktiveras av Maya rekommenderas du att använda `application/x-ext`, där `ext` är strängen som anges som `Extension` värde. |

## Inmatningskonfiguration {#ingestion-configuration}

I **CRXDE Lite** in AEM (**[!UICONTROL Verktyg > Allmänt > CRXDE Lite]**), gå till följande konfigurationer:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Bana</strong></td> 
   <td><strong>Beskrivning</strong></td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/addGroundPlaneImageOnIngest</td> 
   <td>Möjliggör generering av en skugga för omgivande ocklusion vid visning eller återgivning med en IBL-fas. Gäller för förhandsgranskning och återgivning med RapidRefine</td> 
  </tr> 
  <tr> 
   <td><p>/libs/settings/dam/v3D/settings/cleanupRenderWorkDir</p> </td> 
   <td>Ange som <strong>false</strong> om du vill behålla tillfälliga filer i mappen MayaWork efter konvertering och återgivning. Kan vara användbart vid felsökning av Maya-konvertering och -återgivning.</td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/invokeAnimationOnIngest</td> 
   <td><p>När det här alternativet är aktiverat installeras ImageMagick på servern och magickPath konfigureras. Rapid Refine används för att skapa en enkel animering för 3D-objekt som används som miniatyrbilder i kortvyn och andra vyer.</p> <p>Att skapa animeringar kräver mycket processorresurser under själva importen.</p> </td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/invokeLightMapsOnIngest</td> 
   <td>Gör det möjligt att automatiskt skapa ljusscheman vid intag. Inställd på <strong>false</strong> för att inaktivera automatisk generering av ljusscheman. Detta kan avsevärt minska CPU-förbrukningen till en kostnad som reducerar kvaliteten för förhandsgranskning och återgivning med Rapid Refine. Påverkar inte återgivning med Maya.</td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/gPlaneZero</td> 
   <td><p>Om värdet är <strong>true</strong> (standard) flyttas objekt lodrätt, om det behövs, för att säkerställa att alla delar av objektet är ovanför markplanet (y=0).</p> <p>När värdet är <strong>false</strong> (standard) flyttas inte objekten och kan vara delvis dolda av scenens markplan. (Gäller endast förhandsgranskning och återgivning med Snabb förfining.) Det påverkar dock inte återgivningen med Maya. Om värdet är <strong>true</strong>kan objektens lodräta position i Maya vara en annan än i förhandsvisningen eller vid återgivning med Snabb förfining.</p> </td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/Paths/magickPath</td> 
   <td>Sökväg och namn till ImageMagick-konverteringsverktyget. En absolut sökväg krävs om du har aktiverat skapande av animerade miniatyrer.</td> 
  </tr> 
  <tr> 
   <td>/libs/settings/dam/v3D/settings/MaxCpuPercentage</td> 
   <td><p>Anger hur många CPU:er som används som mest för att hantera 3D-resurser.</p> <p>Högre värden snabbar upp inmatningen, men kan leda till att AEM blir mindre responsiv totalt sett. Den här inställningen är ungefärlig. Noggrannheten ökar alltså med antalet tillgängliga processorkärnor.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Konfigurationsinställningar för molntjänster {#cloud-services-configuration-settings}

Värden för följande inställningar tillhandahålls av din Adobe-kontoansvarige, provisioneringsexpert eller supportrepresentant.

| **Bana** | **Beskrivning** |
|---|---|
| `/libs/settings/dam/v3D/services/aws/accountId` | Konto-ID för Adobe AWS-kontot. |
| `/libs/settings/dam/v3D/services/aws/bucketName` | Namnet på S3-överföringskassetten. normalt `aem3d`. |
| `/libs/settings/dam/v3D/services/aws/customerId` | Det unika ID som tilldelats av Adobe till din organisation. Används som användar-ID för AWS Cognito. |
| `/libs/settings/dam/v3D/services/aws/encryptedPassword` | Lösenordet som är associerat med detta customerId. Används som AWS Cognito-lösenord. |
| `/libs/settings/dam/v3D/services/aws/region` | AWS-regionen där molntjänsterna distribueras. |
| `/libs/settings/dam/v3D/services/aws/userPoolId` | Tillämpligt ID för AWS Cognito-användarpool. |
| `/libs/settings/dam/v3D/services/dncr/clientId` | Klient-ID:t för AWS Cognito för DCR-konverteringstjänsten. |

## Vanliga bearbetningsinställningar {#common-processing-settings}

I **CRXDE Lite** in AEM (**[!UICONTROL Verktyg > Allmänt > CRXDE Lite]**), gå till följande konfigurationer:

| **Bana** | **Beskrivning** |
|---|---|
| `/libs/settings/dam/v3D/Paths/mayaWorkPath` | Namnet på och platsen för arbetsmappen för Maya-konvertering och -återgivning. Mappen skapas automatiskt om den inte finns. |
| `/libs/settings/dam/v3D/Paths/maxWorkPath` | Namn och plats för arbetsmappen för maximal 3ds-konvertering. Mappen skapas automatiskt om den inte finns. |
| `/libs/settings/dam/v3D/settings/debugNative` | Ange som **[!UICONTROL true]** om du vill att felsökningsinformation ska kunna skapas vid formatkonvertering och återgivning med RapidRefine-renderaren. |

## Renderingskonfiguration {#renderer-configuration}

I **CRXDE Lite** in AEM (**[!UICONTROL Verktyg > Allmänt > CRXDE Lite]**), gå till följande konfigurationer:

| **Bana** | **Beskrivning** |
|---|---|
| `/libs/settings/dam/v3D/settings/dynamicIBL` | Om värdet är **[!UICONTROL true]** och förgenererade ljusscheman inte är tillgängliga (det vill säga invokeLightMapsOnIngest=false) skapar Rapid Refine-renderaren ljusscheman under återgivningen för att förbättra återgivningskvaliteten. Den här inställningen kan avsevärt öka återgivningstiden. Om du anger värdet **[!UICONTROL false]** minimeras processoranvändningen i sådana situationer, men det kan leda till en lägre återgivningskvalitet. |
| `/libs/settings/dam/v3D/renderers/*/Enabled` | Ange som **[!UICONTROL true]** eller **[!UICONTROL false]** om du vill aktivera eller inaktivera en återgivning. |
| `/libs/settings/dam/v3D/renderers/*/Display` | Gör att du kan ändra strängen som visas för en aktiverad återgivning i återgivningsväljaren på panelen Återgivning. |
| `/libs/settings/dam/v3D/renderers/*/MaxCpuPercentage` | Anger hur många CPU:er som används som mest för återgivning av 3D-scener. Högre värden snabbar upp återgivningen men kan leda till att AEM blir mindre responsiv totalt sett. Den här inställningen är ungefärlig. Noggrannheten ökar alltså med antalet tillgängliga processorkärnor. |

## Inställningar för förhandsgranskning av 3D-resurs {#d-asset-preview-settings}

I **CRXDE Lite** in AEM (**[!UICONTROL Verktyg > Allmänt > CRXDE Lite]**), gå till följande konfigurationer:

| Bana | Beskrivning |
|---|---|
| `/libs/settings/dam/v3D/WebGLSites/autoSpin` | Ange som **[!UICONTROL true]** eller **[!UICONTROL false]** om du vill aktivera eller inaktivera automatisk rotation (automatisk kamera eller omloppsbana) vid sidinläsning. |
| `/libs/settings/dam/v3D/WebGLSites/autoSpinAfterReset` | Ange som **[!UICONTROL true]** om du vill starta om automatisk rotation när **[!UICONTROL Återställ]** trycks ned. Ignoreras när automatisk rotation är inaktiverad. |
| `/libs/settings/dam/v3D/WebGLSites/autoSpinSpeed` | Anger hastigheten (varv per minut) och riktningen för automatisk rotation, med negativa värden för höger-till-vänster och positiva värden för vänster-till-höger-rotation. |
| `/libs/settings/dam/v3D/WebGL/continueRotate` | Inställd på **[!UICONTROL false]** om du vill inaktivera fortsättning med gradvis uttoning av visningsprogramsvar för pek- och musgester. |
| `/libs/settings/dam/v3D/WebGL/curtainColor` | Anger färgen på inläsningskurvan som kan täcka visningsrutan för förhandsvisningen av 3D-resursen under inläsning och initiering. R,G,B-värde, med varje färgkomponent i intervallet 0 till 255. |
| `/libs/settings/dam/v3D/WebGL/fadeCurtains` | Om värdet är **[!UICONTROL true]** tonas lastgardinen gradvis ut under de senare delarna av visningsprograminitieringen. När värdet är **[!UICONTROL false]** förblir draperiet ogenomskinligt tills inläsning och initiering har slutförts. |
| `/libs/settings/dam/v3D/WebGL/showCurtains` | Ange som **[!UICONTROL true]** eller **[!UICONTROL false]** om du vill aktivera eller inaktivera inläsningskurvan för förhandsvisning av 3D-resurser. |
| `/libs/settings/dam/v3D/WebGL/spinHeight` | När automatisk rotation är aktiverad och aktiv justeras kamerans lodräta position automatiskt i förhållande till 3D-objektets höjd. Om värdet är 0,5 kommer kameran att placeras lodrätt vid 1/2 av objektets höjd, vilket gör att horisonten centreras lodrätt i visningsrutan. Ju större värde, desto mer tittar kameran ned på objektet och höjer höjden på den renderade horisonten, desto mindre värden tittar kameran upp på objektet och sänker horisonten. |

## Inställningar för 3D-platskomponenten {#d-sites-component-settings}

I **CRXDE Lite** in AEM (**[!UICONTROL Verktyg > Allmänt > CRXDE Lite]**), gå till följande konfigurationer:

| Bana | Beskrivning |
|---|---|
| `/libs/settings/dam/v3D/WebGLSites/autoSpinAfterReset` | Ange som **[!UICONTROL true]** för att återaktivera automatisk rotation (automatisk kamera eller bitmapp) när hemmet trycks ned. Ignoreras när automatisk rotation är inaktiverad. |
| `/libs/settings/dam/v3D/WebGLSites/continueRotate` | Inställd på **[!UICONTROL false]** om du vill inaktivera fortsättning med gradvis uttoning av visningsprogramsvar för pek- och musgester. |
| `/libs/settings/dam/v3D/WebGLSites/curtainColor` | Anger färgen på inläsningskurvan som kan omfatta visningsrutan för 3D-platskomponenten under inläsningen. R,G,B-värde, med varje färgkomponent i intervallet 0 till 255. |
| `/libs/settings/dam/v3D/WebGLSites/fadeCurtains` | Om värdet är **[!UICONTROL true]** tonas lastgardinen gradvis ut under de senare delarna av inläsning och initiering. När värdet är **[!UICONTROL false]** förblir draperiet ogenomskinligt tills inläsning och initiering har slutförts. |
| `/libs/settings/dam/v3D/WebGLSites/showCurtains` | Ange som **[!UICONTROL true]** eller **[!UICONTROL false]** för att aktivera eller inaktivera inläsningskurvan för 3D-platskomponenten. |
| `/libs/settings/dam/v3D/WebGLSites/spinHeight` | När automatisk rotation är aktiverad och aktiv justeras kamerans lodräta position automatiskt i förhållande till 3D-objektets höjd. Om värdet är 0,5 kommer kameran att placeras lodrätt vid 1/2 av objektets höjd, vilket gör att horisonten centreras lodrätt i visningsrutan. Ju större värde, desto mer tittar kameran ned på objektet och höjer höjden på den renderade horisonten, desto mindre värden tittar kameran upp på objektet och sänker horisonten. |

