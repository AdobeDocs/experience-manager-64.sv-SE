---
title: Arbeta med IBL-steg
seo-title: Arbeta med IBL-steg
description: AEM 3D har stöd för bildbaserad belysning (IBL) för både interaktiv visning och återgivning med den inbyggda renderaren Adobe Rapid Refine™ och tredjepartsrenderare.
seo-description: AEM 3D har stöd för bildbaserad belysning (IBL) för både interaktiv visning och återgivning med den inbyggda renderaren Adobe Rapid Refine™ och tredjepartsrenderare.
uuid: 495ba9cc-02f5-4ce5-9503-9f61ca5482db
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 658ff671-16b9-41bd-ba24-b77a32b3346b
translation-type: tm+mt
source-git-commit: 5acb16b1734331767554261bbcf9640947f2e23f

---


# Arbeta med IBL-steg {#about-working-with-ibl-stages}

AEM 3D har stöd för bildbaserad belysning (IBL) för både interaktiv visning och återgivning med den inbyggda renderaren Adobe Rapid Refine™ och tredjepartsrenderare. Du kan skapa IBL-stadier med vanliga redigeringsverktyg som Autodesk® Maya® eller Autodesk® 3ds Max®.

## Bilder för IBL {#images-for-ibl}

Bilder som används för bildbaserad belysning bör ha HDR (High Dynamic Range) för bästa resultat. De måste vara i lat/långt format med sfärisk avbildning som täcker hela miljön.

För närvarande stöder AEM 3D endast 32-bitars TIFF-filer. Använd vid behov Adobe Photoshop eller ett liknande verktyg för att konvertera HDR-bilden till en TIFF-bild med följande inställningar i dialogrutan Exportera i Adobe Photoshop TIFF:

* **[!UICONTROL Bitdjup]** - 32-bitars (flyttal)
* **[!UICONTROL Pixelordning]** - Varvad (RGBRGB)
* **[!UICONTROL Bildkomprimering]** - LZW
* **[!UICONTROL-byteordning** - IBM PC

En HDR-bild räcker ofta för IBL-steg, men AEM 3D ger ytterligare kontroll över IBL-effekter genom att upp till tre separata bilder tillåts:

* **Diffus ljusmiljöbild** - Den här typen av bild ska vara en HDR-bild, men den kan vara ganska liten eftersom bilden filtreras kraftigt innan den används för diffus belysning.
* **Reflektionsmiljöbild** - Den här typen av bild används för att skapa speglingar i objektytor. Det kan vara en 8-bitars RGB-standardbild med en storlek och upplösning som ger önskad kvalitet och skärpa för speglingar. Om en HDR-bild anges konverterar AEM 3D den till 8-bitars RGB innan en egen algoritm används.
* **Bakgrundsmiljöbild** - Den här typen av bild används som bakgrund. Det kan vara en 8-bitars RGB-standardbild och bör ha önskad storlek/upplösning/detaljnivå för scenens bakgrund. Om en HDR-bild anges konverterar AEM 3D den till 8-bitars RGB med en egen algoritm. &quot;

>[!NOTE]
>
>Konverteringsalgoritmen kan ha problem med vissa IBL-bilder. Svårigheten kan resultera i bakgrunder som är för ljusa eller för mättade i Förhandsgranska eller vid återgivning med Snabb förfining. I sådana fall rekommenderar Adobe att du använder Photoshop eller ett liknande verktyg för att manuellt konvertera IBL-bilden till en 8-bitars RGB-bild. Överför den här bilden separat och bifoga den till scenen som bakgrundsmiljöbild. Diffusera foton för belysnings- och reflektionsmiljö måste alltid vara 32-bitars TIFF-bilder.

## Justera IBL-scenens utseende {#adjusting-the-ibl-stage-appearance}

Du kan finjustera utseendet på IBL-scenen med följande scenegenskaper:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Egenskap</strong><br /> </td> 
   <td><strong>Beskrivning</strong></td> 
  </tr> 
  <tr> 
   <td>Information om IBL Sun</td> 
   <td><p>Gör att du kan justera riktning och styrka för den extra ljuskälla som simulerar solen. <span class="diff-html-added">Ljuskällan ökar ljusstyrkan och gör att objektet kastar en skugga på markplanet. Skuggskiftning stöds vid återgivning med Rapid Refine och vid förhandsgranskning med Google Chrome. men stöds för närvarande inte av andra webbläsare.</span></p> 
    <ul> 
     <li><strong>lat</strong> - Solljuskällans lodräta position (<code>0.0</code>-<code>1.0</code>).<br /> Inställningen är <code>0.0</code> vid horisonten (vertikal mittpunkt av bilden med diffus ljusmiljö). finns <code>1.0</code> i den övre kanten av bilden för diffus ljusmiljö.</li> 
     <li><strong>long</strong> - Solljuskällans vågräta position (<code>0.0</code>-<code>1.0</code>).<br /> Inställningen 0,0 motsvarar vänster. 1.0 motsvarar högerkanten av bilden för diffus ljusmiljö.<br /> </li> 
     <li><strong>stark</strong> - Solljuskällans ljusstyrka. Öka detta värde för att göra solljuset ljusare. minska värdet för att göra det mörkare. <br /> En inställning som <code>0</code> inaktiverar extra ljus och inaktiverar skuggor. Parametern påverkar inte miljöreflektioner.<br /> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>IBL-kamerahöjd</td> 
   <td>Om IBL-bakgrunden ser ut att vara förvrängd nära horisonten kan du minska eller eliminera förvrängningen genom att justera den här egenskapen. <br /> </td> 
  </tr> 
  <tr> 
   <td>Miljöbelysning</td> 
   <td><p><span class="diff-html-added">Du kan styra diffus belysning. Du kan behöva justera den här egenskapen manuellt för att korrigera ljusstyrkan om bilden för diffus ljusmiljö är ovanligt ljus eller mörk (till exempel nattscener).</span></p> 
    <ul> 
     <li><strong>r, g, b</strong> - Används för närvarande inte.</li> 
     <li><strong>bright</strong> - Multiplikator för <span class="diff-html-added">intensitet. Om du ökar eller minskar det här värdet ökar eller minskar den totala ljusstyrkan (både den grundläggande IBL-belysningen och ljuskällans ljusstyrka).</span></li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Ökning av den sfäriska bakgrundsdiametern i ett IBL-stadium {#increasing-the-spherical-background-diameter-of-an-ibl-stage}

I IBL-faser används sfäriska bakgrundsbilder som har en diameter på 20 meter som standard. Sådana stadier fungerar bra för objekt på upp till 10 meter. Om du visar större objekt kan du öka den sfäriska bakgrundsdiametern för en IBL-scen.

**Så här ökar du den sfäriska bakgrundsdiametern på ett IBL-stadium**:

1. I CRXDE Lite navigerar du till den scen vars sfäriska bakgrundsdiameter du vill öka. Exempel:

   `/content/dam/test3d/stage-helipad.fbx`

1. Expandera scennoden till `jcr:content/metadata`.
1. Ange egenskapen `dam:gPlaneRadius` till önskat millimetervärde.

   För att återgivningen ska bli effektiv rekommenderar Adobe att du begränsar värdet till ungefär den största dimensionen av det största objekt som du vill visa på scenen.

   Exempelvis visas en flygplansmodell som är 20 meter lång bra om `dam:gPlaneRadius=20000`.

1. I det övre vänstra hörnet av CRXDE Lite-sidan trycker du på **[!UICONTROL Spara alla]**.

