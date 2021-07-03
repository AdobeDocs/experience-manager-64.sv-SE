---
title: Förhandsgranska Dynamic Media-resurser
seo-title: Förhandsgranska Dynamic Media-resurser
description: Lär dig förhandsgranska resurser i Dynamic Media
seo-description: Lär dig förhandsgranska resurser i Dynamic Media
uuid: f0ff2fc4-a263-4dbe-ba46-b07077b49ae0
contentOwner: Rick Brough
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: dynamic-media
content-type: reference
discoiquuid: 77296bff-8429-4240-af93-26076ae431ec
exl-id: ec05569a-6449-4430-9b9f-7ab051f44970
feature: Resurshantering,Återgivningar
role: User
source-git-commit: 5d96c09ef764b02e08dcdf480da1ee18f4d9a30c
workflow-type: tm+mt
source-wordcount: '1019'
ht-degree: 2%

---

# Förhandsgranska Dynamic Media-resurser {#previewing-assets}

Du kan använda **[!UICONTROL Preview]** för att se hur en digital Dynamic Media-resurs ser ut när den visas av en kund i en egen webbläsare. Standardvisningsprogrammet för inbäddade enheter som är tilldelade resursen används för **[!UICONTROL Preview]**.

Ett visningsprogram är en samling med olika inställningar eller&quot;förinställningar&quot;, t.ex. visningsprogrammets visningsstorlek, zoombeteende, färgscheman, kanter, teckensnitt osv., som avgör hur användare visar mediefiler på datorskärmar och mobila enheter.

Förutom att använda den dedikerade förhandsvisningsfunktionen för video, snurra och bilduppsättningar kan du även förhandsgranska en resurs med de förinställningar för visningsprogram som du har skapat. Du kan också använda bildförinställningar för att förhandsgranska återgivningar av bilder.

* [Använda bildförinställningar](image-presets.md)
* [Använda visningsförinställningar](viewer-presets.md)

>[!NOTE]
>
>När du är på en webbsida (Webbplatser) i AEM kan du inte förhandsgranska resurser i **[!UICONTROL Edit]**-läge. Du måste gå till **[!UICONTROL Preview]**-läget genom att klicka på **Förhandsgranska** i det övre högra hörnet.

**Så här förhandsgranskar du resurser**:

1. Från **Adobe Experience Manager** på **[!UICONTROL Navigation]**-sidan trycker du på **[!UICONTROL Asset]s** och sedan **[!UICONTROL Files]** för att komma åt resurser.
1. Tryck på **[!UICONTROL List View]** i den nedrullningsbara listan **[!UICONTROL View]** i sidans övre högra hörn.
1. (Valfritt) Använd kolumnen **[!UICONTROL Type]** för att sortera resurserna efter den typ som du vill förhandsgranska.
1. Klicka på titelnamnet (inte miniatyrbilden) för resursen som du vill förhandsgranska i kolumnen **[!UICONTROL Title]**.
1. Beroende på vilken resurstyp du klickade på gör du något av följande:

<table> 
 <tbody>
  <tr>
   <td><strong>Tillgångstyp som du knackade på</strong><br /> </td> 
   <td><strong>Kan du förhandsgranska mediefilen i en viss återgivning?</strong></td> 
   <td><strong>Kan du förhandsgranska mediefilen i ett visst visningsprogram?</strong></td> 
  </tr>
  <tr>
   <td><p>Bild</p> </td> 
   <td>Ja</td> 
   <td>Ja</td> 
   <td><p><strong>Så här förhandsgranskar du en resurs i en viss återgivning</strong></p> 
    <ul> 
     <li>Klicka på ikonen i det övre vänstra hörnet av sidan så att listrutan visas. Klicka på <strong>Återgivningar </strong>i listan och välj sedan en viss återgivning som du vill förhandsgranska.</li> 
    </ul> <p><strong>Förhandsgranska resurs i ett visst visningsprogram</strong></p> 
    <ul> 
     <li>Klicka på ikonen i det övre vänstra hörnet av sidan så att listrutan visas. Klicka på <strong>Tittare</strong> i listan och välj sedan ett visningsprogram som du vill använda för resursen.</li> 
    </ul> <p>Använd ikonerna <strong>+</strong> och <strong>- </strong>för att öka respektive minska zoomningen för den markerade bilden. Klicka på <strong>Återställ</strong> om du vill återställa bilden till den ursprungliga zoomningen.<br /> Om du använder en mobil enhet dubbeltrycker du på bilden för att zooma in steg. När du har uppnått maximal zoom dubbeltrycker du på bilden igen för att återställa zoomläget. Dra över bilden för att panorera.</p> <p>Information om hur du aktiverar eller inaktiverar visningsförinställningar i användargränssnittet finns i <a href="/help/assets/managing-viewer-presets.md">Hantera visningsförinställningar</a>.<br /> </p> </td> 
  </tr>
  <tr>
   <td>Multimedia</td> 
   <td>Ja</td> 
   <td>Ja</td> 
   <td><p><strong>Så här förhandsgranskar du en resurs i en viss återgivning</strong></p> 
    <ul> 
     <li>Klicka på ikonen i det övre vänstra hörnet av sidan så att listrutan visas. Klicka på <strong>Återgivningar </strong>i listan och välj sedan en viss återgivning som du vill förhandsgranska.</li> 
    </ul> <p>Om du väljer en videoåtergivning med högre upplösning för förhandsgranskning kan videon bli trunkerad. Det beror på att återgivningsförhandsvisningen visar exakt den upplösning som kunderna kommer att se, allt i kontexten för det inbäddade visningsprogrammet som används för förhandsgranskningen.</p> <p>När du förhandsgranskar en adaptiv videouppsättning på resursnivå grupperas återgivningarna i en uppspelningsupplevelse. Det innebär att den adaptiva videon har rätt storlek för visning och uppspelning med den bästa upplösningen i visningsenhetens kontext och anslutningshastigheten.<br /> </p> <p><strong>Förhandsgranska en resurs i ett visst visningsprogram</strong></p> 
    <ul> 
     <li>Klicka på ikonen i det övre vänstra hörnet av sidan så att listrutan visas. Klicka på <strong>Tittare</strong> i listan och välj sedan ett visningsprogram som du vill använda för resursen.</li> 
    </ul> <p>Information om hur du aktiverar eller inaktiverar visningsförinställningar i användargränssnittet finns i <a href="/help/assets/managing-viewer-presets.md">Hantera visningsförinställningar</a>.</p> </td> 
  </tr>
  <tr>
   <td>Bilduppsättning</td> 
   <td>Nej</td> 
   <td>Ja</td> 
   <td><p><strong>Förhandsgranska en resurs i ett visst visningsprogram</strong></p> 
    <ul> 
     <li>Klicka på ikonen i det övre vänstra hörnet av sidan så att listrutan visas. Klicka på <strong>Tittare</strong> i listan och välj sedan ett visningsprogram som du vill använda för resursen.</li> 
    </ul> <p>Använd ikonerna <strong>+</strong> och <strong>- </strong>för att öka respektive minska zoomningen för den markerade bilden. Klicka på <strong>Återställ</strong> om du vill återställa bilden till den ursprungliga zoomningen.<br /> Om du använder en mobil enhet dubbeltrycker du på bilden för att zooma in steg. När du har uppnått maximal zoom dubbeltrycker du på bilden igen för att återställa zoomläget. Dra över bilden för att panorera.</p> <p>Information om hur du aktiverar eller inaktiverar visningsförinställningar i användargränssnittet finns i <a href="/help/assets/managing-viewer-presets.md">Hantera visningsförinställningar</a>.</p> </td> 
  </tr>
  <tr>
   <td>Rotation</td> 
   <td>Nej</td> 
   <td>Ja</td> 
   <td><p><strong>Förhandsgranska en resurs i ett visst visningsprogram</strong></p> 
    <ul> 
     <li>Klicka på ikonen i det övre vänstra hörnet av sidan så att listrutan visas. Klicka på <strong>Tittare</strong> i listan och välj sedan ett visningsprogram som du vill använda för resursen.</li> 
    </ul> <p>Använd ikonerna <strong>+</strong> och <strong>- </strong>för att öka respektive minska zoomningen för den markerade bilden. Klicka på <strong>Återställ</strong> om du vill återställa bilden till den ursprungliga zoomningen.<br /> Om du använder en mobil enhet dubbeltrycker du på bilden för att zooma in steg. När du har uppnått maximal zoom dubbeltrycker du på bilden igen för att återställa zoomläget. Dra över bilden för att panorera.</p> <p>Information om hur du aktiverar eller inaktiverar visningsförinställningar i användargränssnittet finns i <a href="/help/assets/managing-viewer-presets.md">Hantera visningsförinställningar</a>.</p> </td> 
  </tr>
  <tr>
   <td>Blandad medieuppsättning</td> 
   <td>Nej</td> 
   <td>Ja</td> 
   <td><p><strong>Förhandsgranska en resurs i ett visst visningsprogram</strong></p> 
    <ul> 
     <li>Klicka på ikonen i det övre vänstra hörnet av sidan så att listrutan visas. Klicka på <strong>Tittare</strong> i listan och välj sedan ett visningsprogram som du vill använda för resursen.</li> 
    </ul> <p>Använd ikonerna <strong>+</strong> och <strong>- </strong>för att öka respektive minska zoomningen för den markerade bilden. Klicka på <strong>Återställ</strong> om du vill återställa bilden till den ursprungliga zoomningen.<br /> Om du använder en mobil enhet dubbeltrycker du på bilden för att zooma in steg. När du har uppnått maximal zoom dubbeltrycker du på bilden igen för att återställa zoomläget. Dra över bilden för att panorera.</p> <p>Information om hur du aktiverar eller inaktiverar visningsförinställningar i användargränssnittet finns i <a href="/help/assets/managing-viewer-presets.md">Hantera visningsförinställningar</a>.</p> </td> 
  </tr>
  <tr>
   <td>Carousel set</td> 
   <td>Nej</td> 
   <td>Ja</td> 
   <td><p><strong>Förhandsgranska en resurs i ett visst visningsprogram</strong></p> 
    <ul> 
     <li>Klicka på ikonen i det övre vänstra hörnet av sidan så att listrutan visas. Välj ett visningsprogram som du vill använda för resursen.</li> 
    </ul> <p>Information om hur du aktiverar eller inaktiverar visningsförinställningar i användargränssnittet finns i <a href="/help/assets/managing-viewer-presets.md">Hantera visningsförinställningar</a>.</p> </td> 
  </tr>
 </tbody>
</table>
