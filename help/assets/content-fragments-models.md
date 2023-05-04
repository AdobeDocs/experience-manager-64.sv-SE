---
title: Modeller för innehållsfragment
seo-title: Content Fragment Models
description: Content Fragment Models används för att skapa innehållsfragment med strukturerat innehåll.
seo-description: Content Fragment Models are used to create content fragments with structured content.
uuid: 59176a32-1255-4a46-ad00-344bde843ea6
content-type: reference
topic-tags: content-fragments
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 45e67357-4524-4d25-b5f1-21182b8e803c
exl-id: 39ed07ec-54a6-4387-8435-e891726c411c
feature: Content Fragments
role: User
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '671'
ht-degree: 4%

---

# Modeller för innehållsfragment {#content-fragment-models}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

>[!CAUTION]
>
>Vissa funktioner för innehållsfragment kräver att [AEM 6.4 Service Pack 2 (6.4.2.0) eller senare](../release-notes/sp-release-notes.md).

Content Fragment Models definierar innehållsstrukturen för [innehållsfragment](content-fragments.md).

## Aktivera modeller för innehållsfragment {#enable-content-fragment-models}

>[!CAUTION]
>
>Om du inte aktiverar **[!UICONTROL Content Fragment Models]**, **[!UICONTROL Create]** kan inte användas för att skapa nya modeller.

Om du vill aktivera innehållsfragmentmodeller måste du:

* Aktivera användning av innehållsfragmentmodeller i konfigurationshanteraren
* Använda konfigurationen i resursmappen

### Aktivera modeller för innehållsfragment i Configuration Manager {#enable-content-fragment-models-in-configuration-manager}

Till [skapa en ny modell för innehållsfragment](#creating-a-content-fragment-model) dig **måste** först aktivera dem med Configuration Manager:

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL General]**&#x200B;öppnar du **[!UICONTROL Configuration Browser]**.
   * Se [Configuration Browser-dokumentation](/help/sites-administering/configurations.md) för mer information.
1. Välj lämplig plats för webbplatsen.
1. Använd **[!UICONTROL Create]** för att öppna dialogrutan där du:

   1. Ange en **[!UICONTROL Title]**.
   1. Välj **[!UICONTROL Content Fragment Models]** för att göra det möjligt att använda dem.

   ![cfm-6420-09](assets/cfm-6420-09.png)

1. Välj **[!UICONTROL Create]** för att spara definitionen.

### Använd konfigurationen i resursmappen {#apply-the-configuration-to-your-assets-folder}

När konfigurationen **[!UICONTROL global]** är aktiverat för innehållsfragmentmodeller, kan alla modeller som användarna skapar användas i alla Resursmappar.

Om du vill använda andra konfigurationer (dvs. exkludera globala) med en jämförbar Assets-mapp måste du definiera kopplingen. Detta görs med **[!UICONTROL Configuration]** i **[!UICONTROL Cloud Services]** -fliken i **[!UICONTROL Folder Properties]** för rätt mapp.

## Skapa en innehållsfragmentmodell {#creating-a-content-fragment-model}

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]**&#x200B;öppna **[!UICONTROL Content Fragment Models]**.
1. Navigera till den mapp som passar dina [konfiguration](#enable-content-fragment-models).
1. Använd **[!UICONTROL Create]** för att öppna guiden.

   >[!CAUTION]
   >
   >Om [användning av innehållsfragmentmodeller inte har aktiverats](#enable-content-fragment-models), **Skapa** kommer inte att vara tillgängligt.

1. Ange **[!UICONTROL Model Title]**. Du kan också lägga till en **[!UICONTROL Description]** vid behov.

   ![cfm-6420-10](assets/cfm-6420-10.png)

1. Använd **[!UICONTROL Create]** för att spara den tomma modellen. Ett meddelande visar att åtgärden lyckades. Du kan välja **[!UICONTROL Open]** för att omedelbart redigera modellen, eller **[!UICONTROL Done]** för att återgå till konsolen.

## Definiera innehållsfragmentmodellen {#defining-your-content-fragment-model}

Modellen för innehållsfragment definierar effektivt strukturen för de resulterande innehållsfragmenten. Med modellredigeraren kan du lägga till och konfigurera obligatoriska fält:

>[!CAUTION]
>
>Om du redigerar en befintlig innehållsfragmentmodell kan det påverka beroende fragment.

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]**&#x200B;öppna **[!UICONTROL Content Fragment Models]**.

1. Navigera till mappen som innehåller innehållsfragmentmodellen.
1. Öppna den modell som krävs för **[!UICONTROL Edit]**; använd snabbåtgärden eller välj modell och sedan åtgärden från verktygsfältet.

   När du har öppnat modellredigeraren visas följande:

   * vänster: fält har redan definierats
   * höger: **[!UICONTROL Data Types]** tillgängliga för att skapa fält (och **[!UICONTROL Properties]** för användning när fält har skapats)

   >[!NOTE]
   >
   >När ett fält **Obligatoriskt**, **Etikett** som anges i den vänstra rutan markeras med ett asterix (**&amp;ast;**).

   ![cfm-6420-12](assets/cfm-6420-12.png)

1. **Lägga till ett fält**

   * Dra en obligatorisk datatyp till önskad plats för ett fält:

   ![cfm-6420-11](assets/cfm-6420-11.png)

   * När ett fält har lagts till i modellen visas den högra panelen **Egenskaper** som kan definieras för den aktuella datatypen. Här definierar du vad som krävs för fältet. Till exempel:

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

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]**&#x200B;öppna **[!UICONTROL Content Fragment Models]**.

1. Navigera till mappen som innehåller innehållsfragmentmodellen.
1. Välj modell, följt av **[!UICONTROL Delete]** i verktygsfältet.

   >[!NOTE]
   >
   >Om det refereras till modellen visas en varning. Vidta lämpliga åtgärder.

## Publicera en innehållsfragmentmodell {#publishing-a-content-fragment-model}

Modeller för innehållsfragment måste publiceras när/innan beroende innehållsfragment publiceras.

Så här publicerar du en innehållsfragmentmodell:

1. Navigera till **[!UICONTROL Tools]**, **[!UICONTROL Assets]**&#x200B;öppna **[!UICONTROL Content Fragment Models]**.

1. Navigera till mappen som innehåller innehållsfragmentmodellen.
1. Välj modell, följt av **[!UICONTROL Publish]** i verktygsfältet.

   >[!NOTE]
   >
   >Om du publicerar ett innehållsfragment för vilket modellen ännu inte har publicerats, visas detta i en urvalslista och modellen publiceras med fragmentet.
