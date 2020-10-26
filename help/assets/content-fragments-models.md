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
translation-type: tm+mt
source-git-commit: b61c20c65ceade0153f5cd04fbedfd02e919d483
workflow-type: tm+mt
source-wordcount: '650'
ht-degree: 4%

---


# Modeller för innehållsfragment {#content-fragment-models}

>[!CAUTION]
>
>Vissa funktioner för innehållsfragment kräver att [AEM 6.4 Service Pack 2 (6.4.2.0) eller senare](../release-notes/sp-release-notes.md)används.

Modeller för innehållsfragment definierar innehållsstrukturen för dina [innehållsfragment](content-fragments.md).

## Enable Content Fragment Models {#enable-content-fragment-models}

>[!CAUTION]
>
>Om du inte aktiverar **[!UICONTROL Content Fragment Models]** kan du inte **[!UICONTROL Create]** skapa nya modeller.

Om du vill aktivera innehållsfragmentmodeller måste du:

* Aktivera användning av innehållsfragmentmodeller i konfigurationshanteraren
* Använda konfigurationen i resursmappen

### Aktivera modeller för innehållsfragment i Configuration Manager {#enable-content-fragment-models-in-configuration-manager}

Om du vill [skapa en ny modell](#creating-a-content-fragment-model) för innehållsfragment **måste** du först aktivera dem med Configuration Manager:

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL General]** och öppna sedan **[!UICONTROL Configuration Browser]**.
   * Mer information finns i dokumentationen [till](/help/sites-administering/configurations.md) Configuration Browser.
1. Välj lämplig plats för webbplatsen.
1. Använd **[!UICONTROL Create]** för att öppna dialogrutan där du:

   1. Ange en **[!UICONTROL Title]**.
   1. Markera **[!UICONTROL Content Fragment Models]** om du vill aktivera deras användning.

   ![cfm-6420-09](assets/cfm-6420-09.png)

1. Välj **[!UICONTROL Create]** att spara definitionen.

### Använd konfigurationen i resursmappen {#apply-the-configuration-to-your-assets-folder}

När konfigurationen **[!UICONTROL global]** är aktiverad för innehållsfragmentmodeller kan alla modeller som användarna skapar användas i alla Resursmappar.

Om du vill använda andra konfigurationer (dvs. exkludera globala) med en jämförbar Assets-mapp måste du definiera kopplingen. This is done using **[!UICONTROL Configuration]** in the **[!UICONTROL Cloud Services]** tab of the **[!UICONTROL Folder Properties]** of the appropriate folder.

## Skapa en innehållsfragmentmodell {#creating-a-content-fragment-model}

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]** och öppna **[!UICONTROL Content Fragment Models]**.
1. Navigera till den mapp som passar din [konfiguration](#enable-content-fragment-models).
1. Används **[!UICONTROL Create]** för att öppna guiden.

   >[!CAUTION]
   >
   >Om [användningen av innehållsfragmentmodeller inte har aktiverats](#enable-content-fragment-models)är alternativet **Skapa** inte tillgängligt.

1. Specify the **[!UICONTROL Model Title]**. You can also add a **[!UICONTROL Description]** if required.

   ![cfm-6420-10](assets/cfm-6420-10.png)

1. Spara **[!UICONTROL Create]** den tomma modellen. Ett meddelande visar att åtgärden lyckades, du kan välja **[!UICONTROL Open]** att redigera modellen omedelbart eller **[!UICONTROL Done]** att återgå till konsolen.

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
   * right: **[!UICONTROL Data Types]** available for creating fields (and **[!UICONTROL Properties]** for use once fields have been created)

   >[!NOTE]
   >
   >When a field is **Required**, the **Label** indicated in the left pane will be marked with an asterix (**&amp;ast;**).

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
1. Välj en modell, följt av **[!UICONTROL Delete]** från verktygsfältet.

   >[!NOTE]
   >
   >Om det refereras till modellen visas en varning. Vidta lämpliga åtgärder.

## Publicera en innehållsfragmentmodell {#publishing-a-content-fragment-model}

Modeller för innehållsfragment måste publiceras när/innan beroende innehållsfragment publiceras.

Så här publicerar du en innehållsfragmentmodell:

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]** och öppna **[!UICONTROL Content Fragment Models]**.

1. Navigera till mappen som innehåller innehållsfragmentmodellen.
1. Välj en modell, följt av **[!UICONTROL Publish]** från verktygsfältet.

   >[!NOTE]
   >
   >Om du publicerar ett innehållsfragment för vilket modellen ännu inte har publicerats, visas detta i en urvalslista och modellen publiceras med fragmentet.

