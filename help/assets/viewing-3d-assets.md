---
title: Visa 3D-resurser
description: Lär dig mer om det interaktiva 3D-visningsprogrammet som finns på sidan med resursinformation i AEM och hur du använder det för att visa 3D-resurser.
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
exl-id: 71f89564-a413-49f6-8d6e-c5305bf92c75
feature: 3D-resurser
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '1719'
ht-degree: 0%

---

# Visa 3D-resurser {#viewing-d-assets}

>[!IMPORTANT]
>
>AEM 3D i AEM 6.4 stöds inte längre. Adobe rekommenderar att du använder funktionen 3D-resurser i [AEM som en Cloud Service](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/assets/dynamicmedia/assets-3d.html#dynamicmedia) eller [AEM 6.5.3 eller senare.](https://experienceleague.adobe.com/docs/experience-manager-65/assets/dynamic/assets-3d.html#dynamic) för att visa 3D-resurser.

I det här dokumentet beskrivs både hur du visar 3D-resurser i resursinformation och hur du visar resurser som finns i 3D-komponenten på platser.

## Visa 3D-resurser på sidan Resursinformation {#viewing-d-assets-in-the-asset-details-page}

Det interaktiva 3D-visningsprogrammet är tillgängligt från sidan med resursinformation i AEM. Visningsprogrammet innehåller bland annat en samling interaktiva kamerakontroller som du kan använda för att rotera, zooma och panorera 3D-resursen.

![chlimage_1-139](assets/chlimage_1-139.png)

Förutom att använda standardfaserna i AEM 3D kan du även använda faser som du har skapat i ett tredjepartsprogram och överfört till AEM.

Se [Använda faser i AEM 3D](about-the-use-of-stages-in-aem-3d.md).

>[!NOTE]
>
>Om du vill visa en 3D-resurs måste webbläsaren på enheten eller datorn vara WebGL-aktiverad. Dessutom måste den underliggande grafikmaskinvaran ha tillräcklig kapacitet och tillräckligt med minne för att återge modeller av önskad storlek och komplexitet. Vissa förhandsvisningsfunktioner, till exempel skugga, är inte tillgängliga i alla webbläsare.

### Prestandaöverväganden när du visar 3D-resurser {#performance-considerations-when-you-view-d-assets}

Hur lång tid det tar att öppna en 3D-resurs i vyn med tillgångsinformation beror på flera faktorer. Bland dessa faktorer finns följande:

* Bandbredd och fördröjningar för servern.
* Modellstorlek (antal ytor).
* Antal och storlek på kartor.
* Scenens komplexitet. Till exempel storleken på IBL-bilden.

Dessutom är funktioner i klientdatorn, t.ex. en arbetsstation, bärbar dator eller en mobil pekenhet, också viktiga att tänka på när du manipulerar kameran interaktivt. Ett relativt kraftfullt system med bra grafikfunktioner kan göra den interaktiva 3D-visningen smidigare och mer gynnsam.

**Så här visar du 3D-resurser**:

1. Se till att du har överfört 3D-resurser till AEM.

   Se [Om överföring och bearbetning av 3D-resurser i AEM](upload-processing-3d-assets.md).

1. Tryck på **[!UICONTROL Assets]** på sidan **[!UICONTROL Navigation]** från AEM.
1. Tryck på **[!UICONTROL Card View]** i den nedrullningsbara listan **[!UICONTROL View]** i sidans övre högra hörn.
1. Navigera till en 3D-resurs som du vill visa.
1. Tryck på 3D-resursens kort för att öppna den på sidan med resursinformation.
1. Gör något av följande:

   * Använd kamerakontrollpaletten i det nedre högra hörnet på sidan med resursinformation för att ändra olika vyer av resursen.

      Om du använder en indataenhet utan pekfunktion utan rullhjul, till exempel en klassisk mus från Apple med en knapp, kan du fortfarande ändra zoomning eller perspektiv för en 3D-resurs, medan du arbetar i varje läge. Du slutför åtgärden genom att trycka på och hålla ned `SHIFT`medan du trycker ned musknappen och drar uppåt eller nedåt.

      När du använder en pekplatta på en vanlig bärbar dator är det ofta svårt att styra zoomnings- eller perspektivbeteendena med en gest med två fingrar. I så fall kan du trycka och hålla ned `SHIFT`under åtgärden. Den här typen av åtgärd minskar hastigheten på nypningsgesten och gör det enklare att uppnå exakt zoomnivå eller perspektiv som du vill ha. Du kan också använda ett finger för att dra uppåt eller nedåt medan `SHIFT`tangenten trycks ned för att påverka zoomnings- eller perspektivbeteenden.
   <table> 
    <tbody> 
      <tr> 
      <td><strong>Kamerakontrollnamn</strong><br /> </td> 
      <td><strong>Beskrivning</strong></td> 
      </tr> 
      <tr> 
      <td><p>Zoomning</p> <p>eller</p> <p>Perp</p> </td> 
      <td><p>Tryck eller klicka för att växla mellan zoomnings- och perspektivlägen.</p> <p>Du kan också trycka på och hålla ned <code>ALT/OPTION</code>-tangenten under åtgärden för att tillfälligt växla till perspektivläget<br />. Släpp tangenten för att återgå till zoomläget.</p> 
      <ul> 
      <li><strong>Zooma</strong>-Dolly in och ut vilket flyttar kameran närmare eller längre bort från <br /> materialet du tittar på. Zoom är standardbeteendet för rullningshjulet på en mus (om tillgängligt 0), för nypningsgester med två fingrar på mobila enheter eller när du håller ned Skift-tangenten medan du drar uppåt eller nedåt med vänster musknapp.</li> 
      <li><strong>Perspektiv</strong>-Ändrar kamerans brännvidd (kallas även för visningsfält) samtidigt som resursens relativa storlek behålls i vyn. Perspektiv är det alternativa beteendet för rullningshjulet (om det är tillgängligt), för nypningsgester med två fingrar på mobila enheter eller när du håller ned Skift-tangenten samtidigt som du drar uppåt eller nedåt med vänster musknapp.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td><p>Fågelperspektiv</p> <p>eller</p> <p>Panorera</p> </td> 
      <td><p>Tryck eller klicka om du vill växla mellan lägena för omloppsbana och panorering.</p> <p>Du kan också hålla ned <code>ALT/OPTION</code>-tangenten under åtgärden för att tillfälligt växla till panoreringsläge. Släpp tangenten för att återgå till moturs-läge.</p> 
      <ul> 
      <li><strong>Omloppsbana</strong> - Flyttar betraktningskameran till en sfär centrerad på en målpunkt som är placerad nära 3D-resursens mitt som standard. Omloppsbana är standardbeteendet för en vänsterknappsdragning eller en pekdragning på mobila enheter.</li> 
      <li><strong>Panorera</strong> - Flyttar kameran i visningsplanet. Målpunkten flyttas på motsvarande sätt, så efterföljande omloppsåtgärder flyttar kameran runt en ny målpunkt. Panorering är det alternativa beteendet för vänsterknappsdragning och enkel pekdragning.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td><p>Undersök</p> <p>eller</p> <p>Mål</p> </td> 
      <td><p>Tryck eller klicka för att växla mellan gransknings- och mållägen.</p> 
      <ul> 
      <li><strong>Gå till målläget genom att</strong> trycka på eller klicka.</li> 
      <li><strong>Tryck</strong> på eller klicka någonstans på 3D-resursen för att centrera vyn på den delen av resursen.<br /> Omloppsåtgärder använder den nya målpunkten.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td>Återställ</td> 
      <td>Tryck eller klicka för att återställa vymålpunkten till modellens mitt. Återställ flyttar också kameran<br /> närmare eller längre bort för att visa resursen i sin helhet och med en rimlig visningsstorlek.</td> 
      </tr> 
    </tbody> 
    </table>

   * I det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Stage Selector]**. Välj ett scennamn med den bakgrund och det ljus som du vill använda på 3D-resursen.

   ![chlimage_1-140](assets/chlimage_1-140.png)

   Stegen tillhandahåller den miljö-bakgrund, det markplan och det ljus-in som 3D-modellen visas i.

   Se [Använda faser i AEM 3D](about-the-use-of-stages-in-aem-3d.md).

   * I närheten av det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Camera Selector]** och väljer sedan en kameravy som du vill använda för 3D-resursen.

   ![chlimage_1-141](assets/chlimage_1-141.png)

   Stegen innehåller ofta fördefinierade kameror. Du kan välja den aktuella kameran igen om du vill återställa den till de fördefinierade inställningarna.

   Se [Använda faser i AEM 3D](about-the-use-of-stages-in-aem-3d.md).

1. Tryck på **[!UICONTROL Save]** i det övre högra hörnet på sidan.
1. Gör något av följande:

   * Återge 3D-resursen.

      Se [Återge 3D-resurser](rendering-3d-assets.md).

   * Tryck på **[!UICONTROL Close]** längst upp till höger på sidan för att gå tillbaka till sidan Resurser.

## Visa 3D-resurser i 3D-komponenten för platser {#viewing-d-assets-in-the-sites-d-component}

>[!NOTE]
>
>Det här avsnittet gäller endast för det klassiska WebGL-visningsprogrammet som används för andra 3D-resurstyper än Adobe Dimension.

Beroende på vilken typ av enhet du använder har du tillgång till funktionerna för 3D-komponenten på flera olika sätt.

Mer information finns i följande:

* [Pekskärmsenheter](#touchscreen-devices)
* [Styrplattor](#touchpad-devices)
* [Mus- och styrkuleenheter](#mouse-and-trackball-devices)

Se även [Förhandsgranska en webbsida som har en 3D-komponent](using-the-3d-sites-component.md#previewing-a-web-page-that-has-a-d-component).

![screen_shot_2017-12-11at145654](assets/screen_shot_2017-12-11at145654.png)

### Pekskärmsenheter {#touchscreen-devices}

Så här arbetar du med 3D-komponenter med enheter med pekskärm:

1. Flytta (&quot;omloppsbana&quot;) vypunkten (&quot;kamera&quot;) runt objektet med ett finger. Du kan visa objektet från vilken riktning som helst.

1. Dra kameran närmare eller längre bort från objektet med en nypa med två fingrar. Den här åtgärden liknar att zooma in eller ut och gör att du kan granska information om objektet. Du kan också trycka på och hålla ned knapparna + eller - för att flytta kameran närmare eller längre bort från objektet.

1. Dra med två fingrar för att panorera kameran. Den här åtgärden flyttar kameran i sidled så att du kan titta på olika delar av objektet när du zoomar in. Du kan också trycka på knappen **[!UICONTROL Orbit/Pan Toggle]** för att växla till panoreringsläge och sedan använda ett finger för att panorera kameran. Tryck på knappen **[!UICONTROL Orbit/Pan Toggle]** för att återgå till **[!UICONTROL Orbit]**-läget.

1. Tryck på **[!UICONTROL Reset Viewer]** för att återställa kameran. Den här åtgärden återför objektet till den fullständiga vyn och, om den är aktiverad, återtar den automatiska rotationen.

1. Tryck på **[!UICONTROL Full Screen]** för att aktivera helskärmsläget (om det stöds av enheten). Tryck på **[!UICONTROL Full Screen]** igen för att återställa 3D-visningsprogrammet till sidinbäddat läge.

### Styrplattor {#touchpad-devices}

Så här arbetar du med 3D-komponenter med pekplatteenheter:

1. Använd ett finger och dra samtidigt som du håller ned (vänster)-knappen för att flytta (&quot;omloppsbana&quot;) vypunkten (&quot;kamera&quot;) runt objektet. Du kan visa objektet från vilken riktning som helst.

1. Dra upp eller ned med knapparna på styrplattan uppåt eller nedåt med två fingrar för att flytta kameran närmare eller längre bort från objektet. Den här åtgärden liknar att zooma in eller ut och gör det möjligt att inspektera information om objektet. Du kan också klicka och hålla ned knapparna **[!UICONTROL Zoom In]** eller **[!UICONTROL Zoom Out]** för att flytta kameran närmare eller längre bort från objektet.

1. Använd ett finger och dra samtidigt som du håller ned **ALT/option**-tangenten och (vänster)-styrplattan för att panorera kameran. Den här åtgärden flyttar kameran i sidled så att du kan titta på olika delar av objektet när du zoomar in. Du kan också klicka på knappen **[!UICONTROL Orbit/Pan Toggle]** för att växla till **[!UICONTROL Pan]**-läge och sedan använda ett finger för att panorera kameran medan du håller ned knappen (vänster). Klicka på knappen **[!UICONTROL Orbit/Pan Toggle]** igen för att återgå till **[!UICONTROL Orbit]**-läget.

1. Klicka på **[!UICONTROL Reset Viewer]** för att återställa kameran. Den här åtgärden återför objektet till den fullständiga vyn och, om den är aktiverad, återtar den automatiska rotationen.

1. Klicka på **[!UICONTROL Full Screen]** för att aktivera helskärmsläget. Använd tangenten **Esc** på tangentbordet eller klicka på **[!UICONTROL Full Screen]** igen för att återställa 3D-visningsprogrammet till sidinbäddat läge.

### Mus- och styrkuleenheter {#mouse-and-trackball-devices}

Så här arbetar du med 3D-komponenter med mus- och styrkuleenheter:

1. Dra medan du håller ned den vänstra musknappen för att flytta (&quot;omloppsbana&quot;) vypunkten (&quot;kamera&quot;) runt objektet. Du kan visa objektet från vilken riktning som helst.

1. Använd rullningshjulet för att flytta kameran närmare eller längre bort från objektet. Det liknar att zooma in och ut och gör att du kan granska information om objektet. Du kan också klicka och hålla ned knapparna **[!UICONTROL Zoom In]** eller **[!UICONTROL Zoom Out]** för att flytta kameran närmare eller längre bort från objektet.

1. Dra samtidigt som du håller ned **ALT/option**-tangenten och vänster musknapp för att panorera kameran. Då flyttas kameran i sidled så att du kan titta på olika delar av objektet när du zoomar in. Du kan också klicka på knappen **[!UICONTROL Orbit/Pan Toggle]** för att växla till läget **[!UICONTROL Pan]** och sedan dra medan du håller ned vänster musknapp för att panorera kameran. Klicka på **[!UICONTROL Orbit/Pan Toggle]** igen för att återgå till **[!UICONTROL Orbit]**-läget.
1. Klicka på **[!UICONTROL Reset Viewer]** för att återställa kameran. Den här åtgärden återför objektet till den fullständiga vyn och, om den är aktiverad, återtar den automatiska rotationen.
1. Klicka på **[!UICONTROL Full Screen]** för att aktivera helskärmsläget. Använd **[!UICONTROL Escape]**-tangenten på tangentbordet eller klicka på **[!UICONTROL Full Screen]** igen för att återställa 3D-visningsprogrammet till sidinbäddat läge.
