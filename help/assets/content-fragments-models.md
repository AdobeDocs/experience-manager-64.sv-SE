---
title: Modeller för innehållsfragment
seo-title: Modeller för innehållsfragment
description: Content Fragment Models används för att skapa innehållsfragment med strukturerat innehåll.
seo-description: Content Fragment Models används för att skapa innehållsfragment med strukturerat innehåll.
uuid: 59176a32-1255-4a46-ad00-344bde843ea6
content-type: reference
topic-tags: content-fragments
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 45e67357-4524-4d25-b5f1-21182b8e803c
exl-id: 39ed07ec-54a6-4387-8435-e891726c411c
feature: Innehållsfragment
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 5%

---

# Modeller för innehållsfragment {#content-fragment-models}

>[!CAUTION]
>
>Vissa funktioner för innehållsfragment kräver [AEM 6.4 Service Pack 2 (6.4.2.0) eller senare](../release-notes/sp-release-notes.md).

Modeller för innehållsfragment definierar innehållsstrukturen för dina [innehållsfragment](content-fragments.md).

## Aktivera modeller för innehållsfragment {#enable-content-fragment-models}

>[!CAUTION]
>
>Om du inte aktiverar **[!UICONTROL Content Fragment Models]** kommer alternativet **[!UICONTROL Create]** inte att vara tillgängligt för att skapa nya modeller.

Om du vill aktivera innehållsfragmentmodeller måste du:

* Aktivera användning av innehållsfragmentmodeller i konfigurationshanteraren
* Använda konfigurationen i resursmappen

### Aktivera modeller för innehållsfragment i Configuration Manager {#enable-content-fragment-models-in-configuration-manager}

Om du vill [skapa en ny innehållsfragmentmodell](#creating-a-content-fragment-model) måste du **först aktivera dem med Configuration Manager:**

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL General]** och öppna sedan **[!UICONTROL Configuration Browser]**.
   * Mer information finns i [Configuration Browser-dokumentationen](/help/sites-administering/configurations.md).
1. Välj lämplig plats för webbplatsen.
1. Använd **[!UICONTROL Create]** för att öppna dialogrutan där du:

   1. Ange en **[!UICONTROL Title]**.
   1. Välj **[!UICONTROL Content Fragment Models]** om du vill aktivera deras användning.

   ![cfm-6420-09](assets/cfm-6420-09.png)

1. Välj **[!UICONTROL Create]** om du vill spara definitionen.

### Använd konfigurationen i resursmappen {#apply-the-configuration-to-your-assets-folder}

När konfigurationen **[!UICONTROL global]** är aktiverad för innehållsfragmentmodeller kan alla modeller som användarna skapar användas i alla resursmappar.

Om du vill använda andra konfigurationer (dvs. exkludera globala) med en jämförbar Assets-mapp måste du definiera kopplingen. Detta görs med **[!UICONTROL Configuration]** på fliken **[!UICONTROL Cloud Services]** i **[!UICONTROL Folder Properties]** för den aktuella mappen.

## Skapa en innehållsfragmentmodell {#creating-a-content-fragment-model}

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]** och öppna **[!UICONTROL Content Fragment Models]**.
1. Navigera till den mapp som passar din [konfiguration](#enable-content-fragment-models).
1. Använd **[!UICONTROL Create]** för att öppna guiden.

   >[!CAUTION]
   >
   >Om [användningen av innehållsfragmentmodeller inte har aktiverats](#enable-content-fragment-models) är alternativet **Skapa** inte tillgängligt.

1. Ange **[!UICONTROL Model Title]**. Du kan också lägga till en **[!UICONTROL Description]** om det behövs.

   ![cfm-6420-10](assets/cfm-6420-10.png)

1. Använd **[!UICONTROL Create]** för att spara den tomma modellen. Ett meddelande visar att åtgärden lyckades, du kan välja **[!UICONTROL Open]** om du vill redigera modellen omedelbart eller **[!UICONTROL Done]** om du vill återgå till konsolen.

## Definiera innehållsfragmentmodellen {#defining-your-content-fragment-model}

Modellen för innehållsfragment definierar effektivt strukturen för de resulterande innehållsfragmenten. Med modellredigeraren kan du lägga till och konfigurera obligatoriska fält:

>[!CAUTION]
>
>Om du redigerar en befintlig innehållsfragmentmodell kan det påverka beroende fragment.

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]** och öppna **[!UICONTROL Content Fragment Models]**.

1. Navigera till mappen som innehåller innehållsfragmentmodellen.
1. Öppna den modell som krävs för **[!UICONTROL Edit]**; använd snabbåtgärden eller välj modell och sedan åtgärden från verktygsfältet.

   När du har öppnat modellredigeraren visas följande:

   * vänster: fält har redan definierats
   * höger: **[!UICONTROL Data Types]** tillgängligt för att skapa fält (och **[!UICONTROL Properties]** för användning när fält har skapats)

   >[!NOTE]
   >
   >När ett fält är **Obligatoriskt** kommer den **etikett** som anges i den vänstra rutan att markeras med asterix (**&amp;ast;**).

   ![cfm-6420-12](assets/cfm-6420-12.png)

1. **Lägga till ett fält**

   * Dra en obligatorisk datatyp till önskad plats för ett fält:

   ![cfm-6420-11](assets/cfm-6420-11.png)

   * När ett fält har lagts till i modellen visar den högra panelen de **egenskaper** som kan definieras för den aktuella datatypen. Här definierar du vad som krävs för fältet. Till exempel:

   ![cfm-6420-13](assets/cfm-6420-13.png)

1. **Ta bort ett fält**

   Markera det obligatoriska fältet och klicka/tryck sedan på papperskorgsikonen. Du ombeds bekräfta åtgärden.

   ![cf-32](assets/cf-32.png)

1. När du har lagt till alla obligatoriska fält och definierat egenskaperna använder du **[!UICONTROL Save]** för att behålla definitionen. Till exempel:

   ![cfm-6420-14](assets/cfm-6420-14.png)

## Ta bort en innehållsfragmentmodell {#deleting-a-content-fragment-model}

>[!CAUTION]
>
>Om du tar bort en innehållsfragmentmodell kan det påverka beroende fragment.

Så här tar du bort en innehållsfragmentmodell:

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]** och öppna **[!UICONTROL Content Fragment Models]**.

1. Navigera till mappen som innehåller innehållsfragmentmodellen.
1. Välj en modell följt av **[!UICONTROL Delete]** i verktygsfältet.

   >[!NOTE]
   >
   >Om det refereras till modellen visas en varning. Vidta lämpliga åtgärder.

## Publicera en innehållsfragmentmodell {#publishing-a-content-fragment-model}

Modeller för innehållsfragment måste publiceras när/innan beroende innehållsfragment publiceras.

Så här publicerar du en innehållsfragmentmodell:

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]** och öppna **[!UICONTROL Content Fragment Models]**.

1. Navigera till mappen som innehåller innehållsfragmentmodellen.
1. Välj en modell följt av **[!UICONTROL Publish]** i verktygsfältet.

   >[!NOTE]
   >
   >Om du publicerar ett innehållsfragment för vilket modellen ännu inte har publicerats, visas detta i en urvalslista och modellen publiceras med fragmentet.
