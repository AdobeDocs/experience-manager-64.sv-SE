---
title: Arbeta med komponenten 3D-platser
seo-title: Arbeta med komponenten 3D-platser
description: AEM 3D innehåller en AEM Sites-komponent som kan användas för att implementera interaktiv visning av 3D-modeller på webbsidor.
seo-description: AEM 3D innehåller en AEM Sites-komponent som kan användas för att implementera interaktiv visning av 3D-modeller på webbsidor.
uuid: 4f06bab3-1e31-49ef-89e3-b26195966538
contentOwner: Rick Brough
topic-tags: 3D
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
content-type: reference
discoiquuid: 9017ab55-6d4a-4306-922f-223ab1b2504b
exl-id: bf87b470-08c8-44b4-95d9-1251586b0610
feature: 3D-resurser
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '1007'
ht-degree: 0%

---

# Arbeta med 3D-platskomponenten {#working-with-the-d-sites-component}

AEM 3D innehåller en AEM Sites-komponent som du kan använda för att implementera interaktiv visning av 3D-modeller på webbsidor.

När du har lagt till 3D-komponenten kan du [visa 3D-resursen i den komponenten.](viewing-3d-assets.md)

## Lägga till 3D-komponenten i sidmallen {#adding-the-d-component-to-the-page-template}

Du måste aktivera 3D-komponenten på sidan innan du kan placera den på en sida. Mer information om hur du aktiverar komponenter i mallar finns i [Redigera mallar](/help/sites-authoring/templates.md#editing-a-template-layout-template-author).

**Lägga till 3D-komponenten i sidmallen**:

1. Navigera till **[!UICONTROL Tools > General > Templates]**.

1. Navigera till den sidmall som du vill aktivera 3D-komponenten i och markera mallen.

1. Tryck på **[!UICONTROL Edit]** för att öppna mallen.
1. I den nedrullningsbara menyn i sidans övre högra hörn väljer du läget **[!UICONTROL Structure]**, om det inte redan är aktivt.

   ![image2017-11-14_15-33-57](assets/image2017-11-14_15-33-57.png)

1. Tryck på **[!UICONTROL Layout Container]**-regionen för att markera den.

1. Tryck på knappen **[!UICONTROL Policy]** för att öppna **[!UICONTROL Policy Editor]**.
1. Markera **[!UICONTROL 3D]**-bockmarkeringen i **[!UICONTROL Properties]**-avsnittet och tryck sedan på **[!UICONTROL Done]** för att spara ändringarna och stänga **[!UICONTROL Policy Editor]**.

   Nu kan du placera 3D-platskomponenten på alla sidor som använder den här mallen.

## Lägga till 3D-visningsprogramkomponenten på en webbsida {#adding-the-d-viewer-component-to-a-web-page}

>[!CAUTION]
>
>Den här versionen av AEM 3D stöder endast en instans av 3D-komponenten på varje webbsida. Flera 3D-komponenter på samma sida fungerar inte korrekt.

**Så här lägger du till 3D-visningsprogramkomponenten på en webbsida**:

1. Öppna AEM Sites och markera den webbsida där du vill lägga till 3D-komponenten.

1. Tryck på ikonen **[!UICONTROL Edit]** (penna) för att öppna sidan i sidredigeraren. Kontrollera att **[!UICONTROL Edit]**-läget nära sidans övre högra hörn är markerat.

   ![image2017-11-14_15-44-40](assets/image2017-11-14_15-44-40.png)

1. Tryck på rälsväljaren för att öppna sidopanelen.

1. Tryck på plustecknet för att öppna listan **[!UICONTROL Components]**.

1. Dra **[!UICONTROL 3D Viewer]**-komponenten från **[!UICONTROL Components]**-listan till den plats på sidan där du vill att 3D-visningsprogrammet ska visas.

## Konfigurera 3D-komponenten {#configuring-the-d-component}

1. I sidredigeraren i AEM Sites väljer du den **[!UICONTROL 3D Viewer]**-komponent som du tidigare har lagt till på sidan.

1. Tryck på ikonen **[!UICONTROL Configuration]** (skiftnyckel) för att öppna dialogrutan för komponentkonfiguration.

   Du kan ange följande komponentegenskaper:

   <table> 
    <tbody> 
    <tr> 
    <td>Egenskap</td> 
    <td>Beskrivning</td> 
    <td>Tillämplighet</td> 
    </tr> 
    <tr> 
    <td>Höjd (px)</td> 
    <td>Ange önskad höjd för 3D-komponenten i pixlar. Om inget anges är standardvärdet 600 pixlar.</td> 
    <td> </td> 
    </tr> 
    <tr> 
    <td>Scennamn</td> 
    <td><p>Välj en 3D-scen i listan över tillgängliga faser. Scenen innehåller bakgrund och ljus.</p> <p>Se <a href="/help/assets/about-the-use-of-stages-in-aem-3d.md" target="_blank">Använda scener i AEM 3D-platser</a>.</p> </td> 
    <td>Ignorerad för Adobe Dimension-resurser.</td> 
    </tr> 
    <tr> 
    <td>Snurra hastighet automatiskt (RPM)</td> 
    <td><p>3D-visningsprogrammet skickar kameran oavbrutet efter inläsning och återställning. Det automatiska rotationsfältet avslutas när användaren startar en manuell omloppsåtgärd.</p> <p>Du kan ange rotationshastighet i RPM med följande värden:</p> 
        <ul> 
        <li>Ange ett positivt värde för att snurra åt höger</li> 
        <li>Ange ett negativt värde för att snurra åt vänster</li> 
        <li>Ange ett 0-värde om du vill inaktivera automatisk rotation.</li> 
        </ul> <p>Standardvärdet är 3 varv/min, vilket motsvarar 20 sekunder per fullständig revolution.<br /> <br /> <strong>Obs!</strong> Rotationshastigheten antar en bildrutefrekvens på 60/sek. Den här hastigheten uppnås vanligtvis med små till måttliga modeller på kraftfullare grafikmaskinvara. Större modeller eller långsammare enheter snurrar automatiskt med lägre hastigheter.</p> </td> 
    <td>Ignorerad för Adobe Dimension-resurser.</td> 
    </tr> 
    <tr> 
    <td>Navigeringsknappsfärg</td> 
    <td>Använd färgväljaren för att välja den primära färgen för visarens kontrollknappar.</td> 
    <td>Ignorerad för Adobe Dimension Assets.</td> 
    </tr> 
    <tr> 
    <td>Hovringsfärg för navigering</td> 
    <td>Använd färgväljaren för att välja hovring/vald färg för visarens kontrollknappar.</td> 
    <td>Ignorerad för Adobe Dimension-resurser.</td> 
    </tr> 
    <tr> 
    <td>Visa färgrutor</td> 
    <td>För framtida bruk.</td> 
    <td>Ignorerad för Adobe Dimension-resurser.</td> 
    </tr> 
    <tr> 
    <td>Visa förinställningar för GLTF-kamera</td> 
    <td>Visa eller dölj de kameraförinställningar som kan finnas i Adobe Dimension-resurser.</td> 
    <td>Endast för Adobe Dimension-resurser.</td> 
    </tr> 
    <tr> 
    <td>GLTF-bakgrundsfärg</td> 
    <td>Standardbakgrundsfärg om 3D-modellen inte innehåller någon bakgrund.</td> 
    <td>Endast för Adobe Dimension-resurser.</td> 
    </tr> 
    </tbody> 
   </table>

1. Tryck på bockmarkeringen för att spara ändringarna.

   Förutom de inställningar som är tillgängliga i dialogrutan för komponentkonfiguration finns det ett antal globala konfigurationsinställningar som kan ändras via CRXDE Lite.
Mer information om de här globala inställningarna finns i [Avancerade konfigurationsinställningar](advanced-config-3d.md).

## Tilldela en 3D-modell till komponenten {#assigning-a-d-model-to-the-component}

1. Klicka på ikonen **[!UICONTROL Assets]** i sidredigeraren för AEM Sites för att öppna resurslistan i sidpanelen.

1. Välj filtret **[!UICONTROL 3D Models]** om du vill dölja oönskade resurstyper.

   ![screen_shot_2017-12-11at124258](assets/screen_shot_2017-12-11at124258.png)

1. Sök efter eller bläddra till den 3D-resurs som du vill visa på sidan som redigeras.

1. Dra 3D-resursen från listan **[!UICONTROL Assets]** till den **[!UICONTROL 3D Viewer]**-komponent som tidigare placerats på sidan.

   Adobe Dimension-resurser återges med den nya visningsprogramtekniken som bygger på den öppna glTF-standarden, medan alla andra 3D-resurstyper är beroende av det klassiska AEM 3D webGL-visningsprogrammet. Komponenten väljer automatiskt lämpligt visningsprogram baserat på 3D-modellens typ.

## Förhandsgranska en webbsida som har en 3D-komponent {#previewing-a-web-page-that-has-a-d-component}

När webbsidan är i **[!UICONTROL Edit]**-läge visar 3D-komponenten 3D-modellen, men ingen interaktion med modellen är möjlig.

Du kan förhandsgranska webbsidan i sidredigeraren med fullständig åtkomst till 3D-komponentens funktioner.

Se även [Visa 3D-resurser i 3D-komponenten för platser](viewing-3d-assets.md#viewing-d-assets-in-the-sites-d-component).

**Så här förhandsgranskar du en webbsida som har en 3D-komponent**:

1. Gör något av följande:

   * Klicka på **[!UICONTROL Preview]** uppe till höger på sidan för att öppna förhandsvisningsläget.
   * Ta bort `/edit.html` från sidans URL i webbläsaren.

## Publicera sidan och resurserna {#publishing-the-page-and-assets}

Mer information om hur du publicerar resurser finns i [Publicera resurser](managing-assets-touch-ui.md). Mer information om hur du publicerar sidor finns i [Publicera sidor](/help/sites-authoring/publishing-pages.md).

>[!NOTE]
>
>Om du använder menyalternativet **[!UICONTROL Publish Page]** på **[!UICONTROL Page Information]**-menyn kommer sidan och alla primära sidberoenden att publiceras. Sekundära beroenden som kan refereras av 3D-modellen och/eller 3D-scenen, som texturscheman och IBL-bilder, publiceras inte när du publicerar sidan på det här sättet.
>
>Adobe rekommenderar att du publicerar alla 3D-resurser och deras beroenden direkt från AEM Assets innan du publicerar webbsidan som refererar till dessa resurser.
