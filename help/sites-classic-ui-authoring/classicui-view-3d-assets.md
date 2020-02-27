---
title: Visa 3D-resurser
seo-title: Visa 3D-resurser
description: Det interaktiva 3D-visningsprogrammet finns på sidan med resursinformation i AEM. Visningsprogrammet innehåller bland annat en samling interaktiva kamerakontroller som du kan använda för att rotera, zooma och panorera 3D-resursen.
seo-description: Det interaktiva 3D-visningsprogrammet finns på sidan med resursinformation i AEM. Visningsprogrammet innehåller bland annat en samling interaktiva kamerakontroller som du kan använda för att rotera, zooma och panorera 3D-resursen.
uuid: 06dea4d6-c33a-45da-a9a7-7caae9d1717a
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 5e1e0039-670e-4051-9f2a-e88162482467
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Visa 3D-resurser{#viewing-d-assets}

Det interaktiva 3D-visningsprogrammet finns på sidan med resursinformation i AEM. Visningsprogrammet innehåller bland annat en samling interaktiva kamerakontroller som du kan använda för att rotera, zooma och panorera 3D-resursen.

![chlimage_1-16](assets/chlimage_1-16.png)

Förutom att använda standardfaserna i AEM 3D kan du även använda faser som du har skapat i ett tredjepartsprogram och överfört till AEM.

Se [Använda scener i AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

>[!NOTE]
>
>Om du vill visa en 3D-resurs måste webbläsaren på enheten eller datorn vara WebGL-aktiverad. Dessutom måste den underliggande grafikmaskinvaran ha tillräcklig kapacitet och tillräckligt med minne för att återge modeller med önskad storlek.

## Prestandaöverväganden när du visar 3D-resurser {#performance-considerations-when-you-view-d-assets}

Hur lång tid det tar att öppna en 3D-resurs i vyn med tillgångsinformation beror på flera faktorer. Bland dessa faktorer finns följande:

* Bandbredd och fördröjningar för servern.
* Modellstorlek (antal ytor).
* Antal och storlek på kartor.
* Scenens komplexitet. Till exempel storleken på IBL-bilden.

Dessutom är funktioner i klientdatorn, t.ex. en arbetsstation, bärbar dator eller en mobil pekenhet, också viktiga att tänka på när du manipulerar kameran interaktivt. Ett relativt kraftfullt system med bra grafikfunktioner kan göra den interaktiva 3D-visningen smidigare och mer gynnsam.

**Så här visar du 3D-resurser**:

1. Kontrollera att du har överfört 3D-resurser till AEM.

   Se [Om överföring och bearbetning av 3D-resurser i AEM](/help/sites-classic-ui-authoring/classicui-upload-proc-3d.md).
1. Tryck på **[!UICONTROL Assets]** på **[!UICONTROL navigeringssidan]** i Adobe Experience Manager ****.
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

1. I det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Scenväljare]** . Välj ett scennamn med den bakgrund och det ljus som du vill använda på 3D-resursen.

   ![](do-not-localize/chlimage_1-2.png)

   Stegen tillhandahåller den miljö-bakgrund, det markplan och det ljus-in som 3D-modellen visas i.

   Se [Använda scener i AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

1. I det övre högra hörnet av sidan med resursinformation trycker du på ikonen **[!UICONTROL Kameraväljare]** och väljer sedan en kameravy som du vill använda för 3D-resursen.

   ![](do-not-localize/chlimage_1-3.png)

   Stegen innehåller ofta fördefinierade kameror. Du kan välja den aktuella kameran igen om du vill återställa den till de fördefinierade inställningarna.

   Se [Använda scener i AEM 3D](/help/sites-classic-ui-authoring/classicui-stages-aem3d.md).

1. Tryck på **[!UICONTROL Spara]** i det övre högra hörnet på sidan.
1. Gör något av följande:

   * Återge 3D-resursen.

      Se [Återge 3D-resurser](/help/sites-classic-ui-authoring/classicui-rendering-3d.md).

   * Tryck på **[!UICONTROL Stäng]** i det övre högra hörnet av sidan för att gå tillbaka till sidan Resurser.

