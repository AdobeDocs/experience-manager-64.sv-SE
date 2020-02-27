---
title: Visa 3D-resurser
seo-title: Visa 3D-resurser
description: Läs mer om det interaktiva 3D-visningsprogrammet som finns på sidan med tillgångsinformation i AEM och hur du använder det för att visa 3D-resurser.
seo-description: Läs mer om det interaktiva 3D-visningsprogrammet som finns på sidan med tillgångsinformation i AEM och hur du använder det för att visa 3D-resurser.
uuid: 7d8133ac-3110-4979-8e19-e65090e791be
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 65040923-a8a8-4e27-82c0-67a04348e238
translation-type: tm+mt
source-git-commit: 5acb16b1734331767554261bbcf9640947f2e23f

---


# Visa 3D-resurser {#viewing-d-assets}

I det här dokumentet beskrivs både hur du visar 3D-resurser i resursinformation och hur du visar resurser som finns i 3D-komponenten på platser.

## Visa 3D-resurser på sidan Resursinformation {#viewing-d-assets-in-the-asset-details-page}

Det interaktiva 3D-visningsprogrammet finns på sidan med resursinformation i AEM. Visningsprogrammet innehåller bland annat en samling interaktiva kamerakontroller som du kan använda för att rotera, zooma och panorera 3D-resursen.

![chlimage_1-139](assets/chlimage_1-139.png)

Förutom att använda standardfaserna i AEM 3D kan du även använda faser som du har skapat i ett tredjepartsprogram och överfört till AEM.

Se [Använda scener i AEM 3D](about-the-use-of-stages-in-aem-3d.md).

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

1. Kontrollera att du har överfört 3D-resurser till AEM.

   Se [Om överföring och bearbetning av 3D-resurser i AEM](upload-processing-3d-assets.md).

1. Tryck på **[!UICONTROL Resurser]** på **[!UICONTROL navigeringssidan i AEM]**.
1. I närheten av det övre högra hörnet på sidan, i listrutan **[!UICONTROL Visa]** , trycker du på **[!UICONTROL kortvyn]**.
1. Navigera till en 3D-resurs som du vill visa.
1. Tryck på 3D-resursens kort för att öppna den på sidan med resursinformation.
1. Gör något av följande:

   * Använd kamerakontrollpaletten i det nedre högra hörnet på sidan med resursinformation för att ändra olika vyer av resursen.

      Om du använder en indataenhet utan pekfunktion utan rullhjul, till exempel en klassisk mus från Apple med en knapp, kan du fortfarande ändra zoomning eller perspektiv för en 3D-resurs, medan du arbetar i varje läge. Du slutför åtgärden genom att trycka på och hålla ned `SHIFT`tangenten samtidigt som du håller ned musknappen och drar uppåt eller nedåt.

      När du använder en pekplatta på en vanlig bärbar dator är det ofta svårt att styra zoomnings- eller perspektivbeteendena med en gest med två fingrar. I så fall kan du trycka och hålla ned `SHIFT`under funktionsmakrot. Den här typen av åtgärd minskar hastigheten på nypningsgesten och gör det enklare att uppnå exakt zoomnivå eller perspektiv som du vill ha. Du kan också använda ett finger för att dra uppåt eller nedåt medan `SHIFT`tangenten trycks ned för att påverka zoomnings- eller perspektivbeteenden.
   <table> 
    <tbody> 
      <tr> 
      <td><strong>Kamerakontrollnamn</strong><br /> </td> 
      <td><strong>Beskrivning</strong></td> 
      </tr> 
      <tr> 
      <td><p>Zoomning</p> <p>eller</p> <p>Perp</p> </td> 
      <td><p>Tryck eller klicka för att växla mellan zoomnings- och perspektivlägen.</p> <p>Du kan också trycka på och hålla ned <code>ALT/OPTION</code> tangenten under åtgärden för att tillfälligt växla till perspektivläge<br /> . Släpp tangenten för att återgå till zoomläget.</p> 
      <ul> 
      <li><strong>Zooma</strong>-Dolly in och ut som flyttar kameran närmare eller längre bort från resursen<br /> som du tittar på. Zoom är standardbeteendet för rullningshjulet på en mus (om tillgängligt 0), för nypningsgester med två fingrar på mobila enheter eller när du håller ned Skift-tangenten medan du drar uppåt eller nedåt med vänster musknapp.</li> 
      <li><strong>Perspektiv</strong>-Ändrar kamerans brännvidd (kallas även för visningsfält) samtidigt som resursens relativa storlek behålls i vyn. Perspektiv är det alternativa beteendet för rullningshjulet (om det är tillgängligt), för nypningsgester med två fingrar på mobila enheter eller när du håller ned Skift-tangenten samtidigt som du drar uppåt eller nedåt med vänster musknapp.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td><p>Fågelperspektiv</p> <p>eller</p> <p>Panorera</p> </td> 
      <td><p>Tryck eller klicka om du vill växla mellan lägena för omloppsbana och panorering.</p> <p>Du kan också trycka på och hålla ned <code>ALT/OPTION</code> under funktionsmakrot för att tillfälligt växla till panoreringsläge. Släpp tangenten för att återgå till moturs-läge.</p> 
      <ul> 
      <li><strong>Omloppsbana</strong>- Flyttar betraktningskameran till en sfär centrerad på en målpunkt som är placerad nära 3D-resursens mitt som standard. Omloppsbana är standardbeteendet för en vänsterknappsdragning eller en pekdragning på mobila enheter.</li> 
      <li><strong>Panorera</strong>- Flyttar kameran i visningsplanet. Målpunkten flyttas på motsvarande sätt, så efterföljande omloppsåtgärder flyttar kameran runt en ny målpunkt. Panorering är det alternativa beteendet för vänsterknappsdragning och enkel pekdragning.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td><p>Undersök</p> <p>eller</p> <p>Mål</p> </td> 
      <td><p>Tryck eller klicka för att växla mellan gransknings- och mållägen.</p> 
      <ul> 
      <li><strong>Gå till målläget genom att</strong>trycka på eller klicka.</li> 
      <li><strong>Tryck</strong>på eller klicka någonstans på 3D-resursen för att centrera vyn på den delen av resursen.<br /> Omloppsåtgärder använder den nya målpunkten.</li> 
      </ul> </td> 
      </tr> 
      <tr> 
      <td>Återställ</td> 
      <td>Tryck eller klicka för att återställa vymålpunkten till modellens mitt. Med Återställ flyttas kameran<br /> närmare eller längre bort för att visa resursen i sin helhet och med en rimlig visningsstorlek.</td> 
      </tr> 
    </tbody> 
    </table>

   * I det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Scenväljare]** . Välj ett scennamn med den bakgrund och det ljus som du vill använda på 3D-resursen.
   ![chlimage_1-140](assets/chlimage_1-140.png)

   Stegen tillhandahåller den miljö-bakgrund, det markplan och det ljus-in som 3D-modellen visas i.

   Se [Använda scener i AEM 3D](about-the-use-of-stages-in-aem-3d.md).

   * I det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Kameraväljare]** och väljer sedan en kameravy som du vill använda för 3D-resursen.
   ![chlimage_1-141](assets/chlimage_1-141.png)

   Stegen innehåller ofta fördefinierade kameror. Du kan välja den aktuella kameran igen om du vill återställa den till de fördefinierade inställningarna.

   Se [Använda scener i AEM 3D](about-the-use-of-stages-in-aem-3d.md).

1. Tryck på **[!UICONTROL Spara]** i det övre högra hörnet på sidan.
1. Gör något av följande:

   * Återge 3D-resursen.

      Se [Återge 3D-resurser](rendering-3d-assets.md).

   * Tryck på **[!UICONTROL Stäng]** i det övre högra hörnet av sidan för att gå tillbaka till sidan Resurser.

## Visa 3D-resurser i 3D-komponenten Sites {#viewing-d-assets-in-the-sites-d-component}

>[!NOTE]
>
>Det här avsnittet gäller endast för det klassiska WebGL-visningsprogrammet som används för andra 3D-resurstyper än Adobe Dimension.

Beroende på vilken typ av enhet du använder har du tillgång till funktionerna för 3D-komponenten på flera olika sätt.

Mer information finns i följande:

* [Pekskärmsenheter](#touchscreen-devices)
* [Styrplattor](#touchpad-devices)
* [Mus- och styrkuleenheter](#mouse-and-trackball-devices)

Se även [Förhandsvisa en webbsida som har en 3D-komponent](using-the-3d-sites-component.md#previewing-a-web-page-that-has-a-d-component).

![screen_shot_2017-12-11at145654](assets/screen_shot_2017-12-11at145654.png)

### Pekskärmsenheter {#touchscreen-devices}

Så här arbetar du med 3D-komponenter med enheter med pekskärm:

1. Flytta (&quot;omloppsbana&quot;) vypunkten (&quot;kamera&quot;) runt objektet med ett finger. Du kan visa objektet från vilken riktning som helst.

1. Dra kameran närmare eller längre bort från objektet med en nypa med två fingrar. Den här åtgärden liknar att zooma in eller ut och gör att du kan granska information om objektet. Du kan också trycka på och hålla ned knapparna + eller - för att flytta kameran närmare eller längre bort från objektet.

1. Dra med två fingrar för att panorera kameran. Den här åtgärden flyttar kameran i sidled så att du kan titta på olika delar av objektet när du zoomar in. Du kan också växla till panoreringsläget genom att trycka på **[!UICONTROL Växla]** /Panorera och sedan panorera med ett finger. Tryck på växlingsknappen för **[!UICONTROL omloppsbana/panorering]** för att återgå till **[!UICONTROL omloppsläge]** .

1. Tryck på **[!UICONTROL Återställ visningsprogram]** för att återställa kameran. Den här åtgärden återför objektet till den fullständiga vyn och, om den är aktiverad, återtar den automatiska rotationen.

1. Tryck på **[!UICONTROL Helskärm]** för att aktivera helskärmsläget (om det stöds av enheten). Tryck på **[!UICONTROL Helskärm]** igen för att återställa 3D-visningsprogrammet till sidinbäddat läge.

### Styrplattor {#touchpad-devices}

Så här arbetar du med 3D-komponenter med pekplatteenheter:

1. Använd ett finger och dra samtidigt som du håller ned (vänster)-knappen för att flytta (&quot;omloppsbana&quot;) vypunkten (&quot;kamera&quot;) runt objektet. Du kan visa objektet från vilken riktning som helst.

1. Dra upp eller ned med knapparna på styrplattan uppåt eller nedåt med två fingrar för att flytta kameran närmare eller längre bort från objektet. Den här åtgärden liknar att zooma in eller ut och gör det möjligt att inspektera information om objektet. Du kan också klicka och hålla ned **[!UICONTROL Zooma in]** eller **[!UICONTROL Zooma ut]** för att flytta kameran närmare eller längre bort från objektet.

1. Använd ett finger och dra samtidigt som du håller ned **ALT/Option** -tangenten och (vänster) styrplatteknappen för att panorera kameran. Den här åtgärden flyttar kameran i sidled så att du kan titta på olika delar av objektet när du zoomar in. Du kan också klicka på knappen Växla **[!UICONTROL omloppsbana/panorering]** för att växla till **[!UICONTROL panoreringsläget]** och sedan använda ett finger för att panorera kameran samtidigt som du håller ned knappen (vänster). Klicka på växlingsknappen för **[!UICONTROL omloppsbana/panorering]** igen för att återgå till **[!UICONTROL omloppsläge]** .

1. Klicka på **[!UICONTROL Återställ visningsprogram]** för att återställa kameran. Den här åtgärden återför objektet till den fullständiga vyn och, om den är aktiverad, återtar den automatiska rotationen.

1. Klicka på **[!UICONTROL Helskärm]** för att aktivera helskärmsläget. Använd **Esc** på tangentbordet eller klicka på **[!UICONTROL Helskärm]** igen för att återställa 3D-visningsprogrammet till sidinbäddat läge.

### Mus- och styrkuleenheter {#mouse-and-trackball-devices}

Så här arbetar du med 3D-komponenter med mus- och styrkuleenheter:

1. Dra medan du håller ned den vänstra musknappen för att flytta (&quot;omloppsbana&quot;) vypunkten (&quot;kamera&quot;) runt objektet. Du kan visa objektet från vilken riktning som helst.

1. Använd rullningshjulet för att flytta kameran närmare eller längre bort från objektet. Det liknar att zooma in och ut och gör att du kan granska information om objektet. Du kan också klicka och hålla ned **[!UICONTROL Zooma in]** eller **[!UICONTROL Zooma ut]** för att flytta kameran närmare eller längre bort från objektet.

1. Dra med **ALT/Option** -tangenten och vänster musknapp för att panorera kameran. Då flyttas kameran i sidled så att du kan titta på olika delar av objektet när du zoomar in. Du kan också klicka på knappen Växla **[!UICONTROL omloppsbana/panorering]** för att växla till **[!UICONTROL panoreringsläge]** och sedan dra med vänster musknapp för att panorera kameran. Klicka på Växla **[!UICONTROL omloppsbana/panorering]** igen för att återgå till **[!UICONTROL omloppsläge]** .
1. Klicka på **[!UICONTROL Återställ visningsprogram]** för att återställa kameran. Den här åtgärden återför objektet till den fullständiga vyn och, om den är aktiverad, återtar den automatiska rotationen.
1. Klicka på **[!UICONTROL Helskärm]** för att aktivera helskärmsläget. Använd **[!UICONTROL Esc]** på tangentbordet eller klicka på **[!UICONTROL Helskärm]** igen för att återställa 3D-visningsprogrammet till sidinbäddat läge.

