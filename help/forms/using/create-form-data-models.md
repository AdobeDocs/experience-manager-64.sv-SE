---
title: Skapa formulärdatamodell
seo-title: Skapa formulärdatamodell
description: Lär dig hur du skapar formulärdatamodeller med eller utan konfigurerade datakällor.
seo-description: Lär dig hur du skapar formulärdatamodeller med eller utan konfigurerade datakällor.
uuid: bed1a82e-a799-4034-9068-1478b95e6c70
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: integration
discoiquuid: 3a3a6ede-52af-4c37-8a51-c2ea721a28dc
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '935'
ht-degree: 0%

---


# Skapa formulärdatamodell {#create-form-data-model}

Lär dig hur du skapar formulärdatamodeller med eller utan konfigurerade datakällor.

![](do-not-localize/data-integeration.png)

AEM Forms dataintegrering ger ett intuitivt användargränssnitt för att skapa och arbeta med formulärdatamodeller. En formulärdatamodell bygger på datakällor för datautbyte. Du kan dock skapa en formulärdatamodell med eller utan en datakälla. Det finns två sätt att skapa en utifrån datamodell beroende på om du har konfigurerat datakällor:

* **Använda förkonfigurerade datakällor**: Om du har konfigurerat datakällor enligt beskrivningen i [Konfigurera datakällor](/help/forms/using/configure-data-sources.md)kan du välja dem när du skapar en formulärdatamodell. Den hämtar alla datamodellsobjekt, egenskaper och tjänster från de valda datakällorna som är tillgängliga för användning i formulärdatamodellen.

* **Utan datakällor**: Om du inte har konfigurerat datakällor för formulärdatamodellen kan du fortfarande skapa den utan datakällor. Du kan använda formulärdatamodellen för att skapa adaptiva formulär och interaktiv kommunikation och testa dem med exempeldata. När datakällor är tillgängliga kan du binda formulärdatamodellen till datakällor, som automatiskt återspeglas i de tillhörande adaptiva formulären och interaktiva kommunikationerna.

>[!NOTE]
>
>Du måste vara medlem i både **fdm-author** - och **forms-user** -grupper för att kunna skapa och arbeta med formulärdatamodellen. Kontakta AEM om du vill bli medlem i grupperna.

## Skapa formulärdatamodell {#data-sources}

Kontrollera att du har konfigurerat de datakällor som du vill använda i formulärdatamodellen enligt beskrivningen i [Konfigurera datakällor](/help/forms/using/configure-data-sources.md). Så här skapar du en formulärdatamodell som baseras på konfigurerade datakällor:

1. Navigera AEM författarinstansen till **[!UICONTROL Forms > Data Integrations]**.
1. Tryck på **[!UICONTROL Create > Form Data Model]**.
1. I dialogrutan Skapa formulärdatamodell:

   * Ange ett namn för formulärdatamodellen.
   * (**Valfritt**) Ange rubrik, beskrivning och taggar för formulärdatamodellen.
   * (**Valfritt och endast tillämpligt om datakällor har konfigurerats**) Tryck på bockikonen bredvid **[!UICONTROL Data Source Configuration]** fältet och välj konfigurationsnoden där molntjänster för de datakällor som du vill använda finns. Den begränsar listan med datakällor som är tillgängliga för val på nästa sida till de som är tillgängliga i den valda konfigurationsnoden. Alla JDBC-databaser och AEM datakällor för användarprofiler listas som standard. Om du inte väljer en konfigurationsnod visas datakällor från alla konfigurationsnoder.

   Tryck på **[!UICONTROL Next]**.

1. (**Gäller endast om datakällor har konfigurerats**) På skärmen visas tillgängliga datakällor, om det finns några, på **[!UICONTROL Select Datasource]** skärmen. Välj datakällor som du vill använda i formulärdatamodellen.
1. Tryck **[!UICONTROL Create]** och tryck på bekräftelsedialogrutan för **[!UICONTROL Open]** att öppna formulärdatamodellens redigerare.

Låt oss granska de olika komponenterna i användargränssnittet för formulärdatamodellsredigeraren.

![En formulärdatamodell med tre datakällor - en RESTful-tjänst, AEM användarprofil och ett RDBMS](assets/fdm-ui.png)

**S. Datakällor** Visar datakällor i en formulärdatamodell. Expandera en datakälla för att visa dess datamodellsobjekt och tjänster.

**B. Uppdatera definitioner** för datakälla Hämtar alla ändringar i datakälldefinitioner från konfigurerade datakällor och uppdaterar dem på fliken Datakällor i formulärdatamodellens redigerare.

**C. Modellinnehållsområdet** där datamodellsobjekt som lagts till visas.

**D. Området Services** Content där tillagda datakällåtgärder eller -tjänster visas.

**E. Verktyg i verktygsfältet** för att arbeta med formulärdatamodell. I verktygsfältet visas fler alternativ beroende på vilket objekt som är markerat i formulärdatamodellen.

**F. Lägg till markerade** Lägger till markerade datamodellsobjekt och tjänster i formulärdatamodellen.

Mer information om formulärdatamodellredigerare och hur du kan arbeta med den för att redigera och konfigurera formulärdatamodellen finns i [Arbeta med formulärdatamodell](/help/forms/using/work-with-form-data-model.md).

## Uppdatera datakällor {#update}

Gör följande för att lägga till eller uppdatera datakällor till en befintlig formulärdatamodell.

1. Gå till **[!UICONTROL Forms > Data Integrations]** och välj den formulärdatamodell i vilken du vill lägga till eller uppdatera datakällor. Tryck sedan på **[!UICONTROL Properties]**.
1. Gå till fliken **[!UICONTROL Update Source]** i egenskaperna för formulärdatamodellen.

   På fliken Uppdateringskälla:

   * Tryck på bläddringsikonen i **[!UICONTROL Context-Aware Configuration]** fältet och välj en konfigurationsnod där molnkonfigurationen för den datakälla som du vill lägga till finns. Om du inte väljer en nod visas molnkonfigurationer som bara finns i noden när du trycker `global` **[!UICONTROL Add Sources]**.
   * Om du vill lägga till en ny datakälla trycker du på **[!UICONTROL Add Sources]** och väljer de datakällor som ska läggas till i formulärdatamodellen. Alla datakällor som är konfigurerade i `global` och den valda konfigurationsnoden (om det finns någon) visas.
   * Om du vill ersätta en befintlig datakälla med en annan datakälla av samma typ trycker du på **[!UICONTROL Edit]** ikonen för datakällan och väljer i listan med tillgängliga datakällor.
   * Om du vill ta bort en befintlig datakälla trycker du på **[!UICONTROL Delete]** ikonen för datakällan. Ikonen Ta bort är inaktiverad om ett datamodellsobjekt i datakällan läggs till i formulärdatamodellen.

   ![fdm-properties](assets/fdm-properties.png)

1. Tryck **[!UICONTROL Save & Close]** för att spara uppdateringarna.

>[!NOTE]
>
>När du lägger till nya datakällor eller uppdaterar befintliga datakällor i en formulärdatamodell måste du uppdatera bindningsreferenserna, beroende på vad som är lämpligt, i anpassningsbara formulär och interaktiv kommunikation som använder den uppdaterade formulärdatamodellen.

## Nästa steg {#next-steps}

Nu har du en formulärdatamodell med nya datakällor. Därefter kan du redigera formulärdatamodellen för att lägga till och konfigurera datamodellsobjekt och -tjänster, lägga till associationer mellan datamodellsobjekt, redigera egenskaper, lägga till anpassade datamodellsobjekt och egenskaper, generera exempeldata osv.

Mer information finns i [Arbeta med formulärdatamodell](/help/forms/using/work-with-form-data-model.md).
