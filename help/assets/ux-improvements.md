---
title: Förbättringar av användarupplevelsen i Assets
description: I den här artikeln beskrivs förbättringarna av användarupplevelsen i AEM 6.4 Assets.
contentOwner: AG
feature: Versionsinformation
role: Ledare,Affärsledare
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '630'
ht-degree: 0%

---


# Förbättringar av användarupplevelsen i resurser {#user-experience-enhancements-in-assets}

AEM 6.4 Assets innehåller flera förbättringar av användbarheten som ger en smidig användarupplevelse och förbättrar produktiviteten. Den snabba hastigheten med vilken ni kan skapa/hantera ert marknadsmaterial ökar företagets innehållshastighet.

Gränssnittet är mer responsivt, vilket hjälper dig att hantera en stor portfölj med resurser på ett effektivt sätt. Du kan snabbt söka, visa, sortera och smidigt bläddra igenom en lång lista med objekt.

Du kan anpassa de olika vyerna - kort-, lista- och kolumnvyer. Du kan till exempel konfigurera storleken på miniatyrbilder som du vill visa i kortvyn. I listvyn kan du konfigurera den detaljnivå som du vill visa för resurser i listan. AEM 6.4 Assets innehåller en ny trädvy där du bekvämt kan navigera i resurskatalogen och hitta dina resurser.

## Lazy läser in {#lazy-loading}

När du söker efter resurser i AEM 6.4 visas upp till 200 resurser i taget. Du kan bläddra igenom resultaten snabbare, vilket är särskilt användbart när du bläddrar igenom en lång lista med resultat. Eftersom ett stort antal resurser läses in samtidigt blir webbläsarupplevelsen smidig.

Om du trycker/klickar på en resurs för att granska dess informationssida kan du gå tillbaka till resultatsidan genom att trycka/klicka på knappen Bakåt i verktygsfältet.

## Förbättringar i kortvyn {#card-view-improvements}

Beroende på vilken enhet du använder och hur detaljerad du behöver kan du ändra storlek på miniatyrbilderna för resursen i kortvyn. På så sätt kan du anpassa visningen och styra antalet miniatyrbilder som visas.

Så här ändrar du storlek på miniatyrbilder i kortvyn:

1. Tryck/klicka på layoutikonen i verktygsfältet och välj sedan alternativet **[!UICONTROL View Settings]**.

   ![view_settings](assets/view_settings.png)

1. Välj önskad miniatyrstorlek i dialogrutan **[!UICONTROL View Settings]** och tryck/klicka sedan på **[!UICONTROL Update]**.

   ![view_settings_dialog](assets/view_settings_dialog.png)

1. Granska miniatyrbilderna som visas i vald storlek.

   ![thumbnails_changed](assets/thumbnails_changed.png)

Rutan i kortvyn visar nu ytterligare information, till exempel publiceringsstatus.

![publish_status](assets/publish_status.png)

## Förbättringar i listvyn {#list-view-improvements}

I listvyn visar den första kolumnen nu filnamnen på resurserna som standard. Ytterligare information, som publicerings- och bearbetningsstatus samt språkområde, visas också.

![list_view](assets/list_view.png)

Du kan välja att konfigurera hur mycket information du vill visa. Tryck/klicka på layoutikonen, välj alternativet **[!UICONTROL View Settings]** och ange de kolumner som du vill visa i dialogrutan **[!UICONTROL View Settings]**.

![view_settings_dialoglistview](assets/view_settings_dialoglistview.png)

## Förbättringar i kolumnvyn {#column-view-improvements}

Förutom kort- och listvyer kan du nu navigera till informationssidan för en resurs från kolumnvyn. Välj en resurs i kolumnvyn och tryck/klicka sedan på **[!UICONTROL More Details]** under ögonblicksbilden av resursen.

![more_details](assets/more_details.png)

## Trädvy {#tree-view}

AEM 6.4 Resurser innehåller en trädvy där du bekvämt kan bläddra i resurshierarkin och navigera till önskad resurs eller mapp.

Om du vill öppna trädvyn trycker/klickar du på ikonen GlobalNav i `Assets UI` och väljer **[!UICONTROL Content tree]** på menyn.

![content_tree](assets/content_tree.png)

Navigera från innehållshierarkin till önskad resurs.

![navigate_contenttree](assets/navigate_contenttree.png)

## Navigera i resursinformation {#navigating-asset-details}

Sidan med resursinformation innehåller nu knapparna Föregående och Nästa i verktygsfältet så att du kan visa alla bilder i en mapp i följd.

Beroende på vilken enhet du använder kan du även svepa eller använda piltangenterna på tangentbordet för att gå fram och tillbaka mellan bilderna.

Beroende på den valda layouten kan du öppna informationssidan för en resurs på följande sätt:

| **Visa** | **Öppna sidan med resursinformation** |
|---|---|
| [!UICONTROL Card View] | Tryck/klicka på resurspanelen. |
| [!UICONTROL List View] | Tryck/klicka på radposten för resursen i listan. |
| [!UICONTROL Column View] | Tryck/klicka på knappen **[!UICONTROL More Details]** från ögonblicksbilden av resursen. |

Använd knapparna Föregående/Nästa för att gå fram och tillbaka mellan resurserna.

![prev_next_buttons](assets/prev_next_buttons.png)
