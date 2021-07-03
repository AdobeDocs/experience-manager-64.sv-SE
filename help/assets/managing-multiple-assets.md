---
title: Redigera metadata gruppvis för flera resurser och samlingar
description: Lär dig hur du redigerar metadata för många resurser och samlingar samtidigt för att snabbt sprida vanliga metadataändringar.
contentOwner: AG
feature: Resurshantering,Metadata,Samlingar
role: User
exl-id: 3541b50a-f226-4a6a-9c2a-03a5f47f1c23
source-git-commit: 5d96c09ef764b02e08dcdf480da1ee18f4d9a30c
workflow-type: tm+mt
source-wordcount: '418'
ht-degree: 13%

---

# Hantera flera resurser och samlingar {#managing-multiple-assets-and-collections}

Lär dig hur du redigerar metadata för flera resurser och samlingar samtidigt för att snabbt sprida vanliga metadataändringar.

Med Adobe Enterprise Manager (AEM) Assets kan du redigera metadata för flera resurser samtidigt så att du snabbt kan sprida vanliga metadataändringar till resurser samtidigt. Du kan också redigera metadata för flera samlingar samtidigt.

Använd egenskapssidan för att utföra metadataändringar på flera resurser eller samlingar:

* Ändra metadataegenskaper till ett gemensamt värde
* Lägga till eller ändra taggar

Om du vill anpassa sidan med metadataegenskaper, inklusive lägga till, ändra eller ta bort metadataegenskaper, använder du schemaredigeraren.

>[!NOTE]
>
>Massredigeringsmetoderna fungerar för resurser som är tillgängliga i en mapp eller en samling. För resurser som är tillgängliga i olika mappar eller matchar ett gemensamt villkor är det möjligt att uppdatera metadata i grupp utifrån resurssökningsresultaten.

## Redigera metadataegenskaper för flera resurser {#editing-metadata-properties-of-multiple-assets}

1. Navigera till platsen för de resurser som du vill redigera i användargränssnittet Resurser.
1. Markera de resurser som du vill redigera gemensamma egenskaper för.
1. Klicka på **[!UICONTROL Properties]** i verktygsfältet för att öppna egenskapssidan för de valda resurserna.
1. Ändra metadataegenskaperna för markerade resurser på de olika flikarna.
1. Om du vill visa metadata för en viss resurs avbryter du valet av återstående resurser i listan. Om du avbryter markeringen av ett fåtal resurser på sidan [!UICONTROL Properties] uppdateras inte metadata för sådana resurser.
1. Klicka på **[!UICONTROL Settings]** i verktygsfältet och välj ett schema om du vill välja ett annat metadatamatchschema för resurserna. Klicka på **[!UICONTROL Save & Close]**.
1. Om du vill lägga till nya metadata till befintliga metadata i fält som innehåller flera värden väljer du **[!UICONTROL Append mode]**. Om du inte markerar det här alternativet ersätter de nya metadata de data som finns i fälten. Klicka på **[!UICONTROL Submit]**.

![Massor av metadatamatcheman gäller för flera resurser](assets/metadata-schema-bulk-edit.gif)

>[!CAUTION]
>
>För fält med ett enda värde läggs de nya metadata inte till det befintliga värdet i fältet, även om du väljer **[!UICONTROL Append mode]**.

## Konfigurera gräns för uppdatering av massmetadata {#configure-limit-for-bulk-metadata-update}

För att förhindra DOS-liknande situationer begränsar AEM antalet parametrar som stöds i en Sling-begäran. När du uppdaterar metadata för många resurser på en gång kan du nå gränsen och metadata uppdateras inte för fler resurser. AEM genererar följande varning i loggarna:

`org.apache.sling.engine.impl.parameters.Util Too many name/value pairs, stopped processing after 10000 entries`

Om du vill ändra gränsen öppnar du **[!UICONTROL Tools > Operations > Web Console]** och ändrar värdet för [!UICONTROL Maximum POST Parameters] i OSGi-konfigurationen.[!UICONTROL Apache Sling Request Parameter Handling]

>[!MORELIKETHIS]
>
>* [Redigera metadata för flera samlingar samtidigt](managing-collections-touch-ui.md#editing-collection-metadata-in-bulk)

