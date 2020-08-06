---
title: Lägga till bilagor
seo-title: Lägga till bilagor
description: Lägga till foton och anteckningar som anteckningar till dina uppgifter i AEM Forms-appen
seo-description: Lägga till foton och anteckningar som anteckningar till dina uppgifter i AEM Forms-appen
uuid: cf8b54a8-e5bc-49df-90f8-c6a37533c347
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 184b5c7f-a704-4b8c-b1ec-f4d6616a1afc
translation-type: tm+mt
source-git-commit: 0ce79686522da4fb3d017068b623c76f81c6b23a
workflow-type: tm+mt
source-wordcount: '565'
ht-degree: 0%

---


# Lägga till bilagor {#adding-attachments}

## Lägga till bilagor i formulär som har synkroniserats med AEM Forms Workflow Server (AEM Forms on JEE) {#adding-annotations}

Med AEM Forms-appen kan du bifoga bilder, anteckningar och textanteckningar i ditt formulär som synkroniseras med AEM Forms JEE-servern. Om formuläret läses in från en AEM Forms Workflow-server läggs dina bilagor till i formuläret. Du kan trycka på knappen Bifogade ![bilagor-app](assets/attachments-app.png) om du vill visa alla bifogade filer i ett formulär tillsammans. Det röda meddelandet anger antalet bilagor i formuläret. Om det inte finns några bifogade filer i formuläret kan du inte se knappen med röda meddelanden. Om det inte finns några bifogade filer i formuläret får du alternativ för att bifoga foton eller ![klotter när du trycker på knappen Bifogade](assets/attch.png).

Dina alternativ är:

* **[!UICONTROL Gallery]**: Gör att du kan lägga till en bild från de bilder du har sparat på enheten.

* **[!UICONTROL Camera]**: Gör att du kan ta en bild och lägga till den i formuläret.

* **[!UICONTROL Notes]**: Gör att du kan lägga till en klottra eller en textanteckning. Använd ![klottra](assets/scribble.png) för att lägga till ett klottrigt och ![tangentbord](assets/keyboard.png) för att lägga till en textanteckning.

>[!NOTE]
>
>Bifogade filer som läggs till av en användare visas för andra AEM Forms-appanvändare. Andra användare kan inte ta bort bilagor som lagts till av en användare.


### Skärmen Bifogade filer {#the-attachments-screen}

Om du vill se alla bilagor på en plats trycker du på ![appen](assets/attachments-app.png)för bilagor. Du kan lägga till, byta namn på och ta bort bifogade filer här.

![Alla bilagor på en plats](assets/attachments-screen.png)

Du kan använda **+** -knappen på skärmen Bifogade filer för att bifoga ytterligare en bild, klottra eller text.

### Lägga till ett foto {#adding-a-photograph}

Du kan använda kameran på din mobila enhet eller sparade bilder på enheten för att bifoga en bild i formuläret.

1. Tryck på knappen Bifogad fil ![längst ned](assets/attch.png) i fönstret.
1. Tryck på **[!UICONTROL Gallery]** eller **[!UICONTROL Camera]** i popup-fönstret som visas.
1. Utför följande beroende på vilket alternativ du väljer:

   1. Om du väljer **[!UICONTROL Camera]**.

      Ta ett foto. Tryck sedan på knappen **[!UICONTROL Use]** use-pic ![](assets/use-pic.png) .

      Eller tryck på **[!UICONTROL Retake]** knappen ![Ta](assets/retake.png) om för att ta fotot igen.

   1. Om du väljer **[!UICONTROL Gallery]**.

      Enhetens bildläsare visas. Tryck på den bild du vill bifoga i bildwebbläsaren på enheten.

### Lägga till en anteckning {#adding-a-note}

Med alternativet **Anteckningar** kan du lägga till frihandsskript och textbilagor i formuläret.

1. Tryck på knappen Bifogad fil ![längst ned](assets/attch.png) i fönstret.
1. Tryck **[!UICONTROL Notes]** på popup-fönstret som visas.
1. Hämta ett frihandsskript i anteckningsgränssnittet som startas.

   ![Klottra](assets/scribble-ui.png)
   **Bild:** *Klottra*

   Du kan använda följande alternativ i gränssnittet Klottra:

   * **[!UICONTROL Clear]**: Rensar skärmen.
   * **[!UICONTROL Done]**: Kopplar det aktuella klottret.
   * **[!UICONTROL Cancel]**: Ignorerar det aktuella klottret och avslutar användargränssnittet i klottret.
   * ![tangentbord](assets/keyboard.png): Rensar klottret och låter dig lägga till en textanteckning.

   ![Tangentbord i AEM Forms app scribble](assets/keyboard-inapp.png)

## Bifogade filer i formulär som synkroniseras med AEM Forms-servrar utan AEM Forms Workflow (AEM Forms on OSGi) {#attachments-in-forms-synced-with-the-aem-forms-servers-without-aem-forms-workflow-aem-forms-on-osgi}

Bifogade filer för mobilformulär som synkroniseras med AEM Forms OSGi-servrar fungerar på samma sätt som AEM Forms JEE-servrar.

Bilagor på formulärnivå stöds inte för adaptiva formulär som läses in i appen från en AEM Forms OSGi-server. Om du vill bifoga bilder eller textanteckningar aktiverar du bilagor på fältnivå i formuläret när du redigerar det. Dra och släpp den bifogade filkomponenten från komponentwebbläsaren i fältet.

När det gäller anpassningsbara formulär kan du visa de bifogade filerna i postdokumentet (DoR). Se [Generera arkivdokument för icke-XFA adaptiva formulär](/help/forms/using/generate-document-of-record-for-non-xfa-based-adaptive-forms.md).
