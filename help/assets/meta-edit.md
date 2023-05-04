---
title: Redigera eller lägga till metadata
description: Läs om metadata för resurser i [!DNL Experience Manager] Resurser är olika sätt att redigera metadata för resurser.
contentOwner: AG
feature: Metadata
role: User,Admin
exl-id: f0522343-f8a9-4d89-8ce8-b3357ae3fe70
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 6%

---

# Redigera eller lägga till metadata {#how-to-edit-or-add-metadata}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Metadata är ytterligare information om resursen som kan sökas igenom. Den extraheras automatiskt när du överför en bild. Du kan redigera befintliga metadata eller lägga till nya metadataegenskaper i befintliga fält (till exempel när ett metadatafält är tomt).

Eftersom företag behöver kontrollerade och tillförlitliga metadata-språk, [!DNL Experience Manager] Resurser tillåter inte att nya metadataegenskaper läggs till för hand. Även om författare inte kan lägga till nya metadatafält för resurser kan utvecklare göra det. Se [Skapar ny metadataegenskap för resurser](meta-edit.md#editing-metadata-schema).

## Redigera metadata för en resurs {#editing-metadata-for-an-asset}

Så här redigerar du metadata:

1. Gör något av följande:

   * Välj resursen i resursgränssnittet och klicka/tryck på **[!UICONTROL View Properties]** -ikonen i verktygsfältet.
   * Välj miniatyrbilden för resursen **[!UICONTROL View Properties]** snabbåtgärd.
   * Klicka/tryck på **[!UICONTROL View Properties]** icon ![informationsikon](assets/do-not-localize/info_icon.png) i verktygsfältet.

   Resurssidan visar alla metadata för resursen. Dessa metadata extraherades automatiskt när de överfördes till [!DNL Experience Manager] Resurser.

   ![chlimage_1-169](assets/chlimage_1-169.png)

1. Redigera metadata på de olika flikarna efter behov och klicka/tryck sedan på **[!UICONTROL Save]** i verktygsfältet för att spara ändringarna. Klicka/tryck på **[!UICONTROL Close]** för att gå tillbaka till Assets-webbgränssnittet.

   >[!NOTE]
   >
   >Om ett textfält är tomt finns det ingen befintlig metadatauppsättning. Du kan ange ett värde i fältet och spara det för att lägga till metadataegenskapen.

Alla ändringar av metadata för en resurs skrivs tillbaka till den ursprungliga binärfilen som en del av dess XMP data. Detta görs via AEM för återskrivning av metadata. Ändringar som gjorts i befintliga egenskaper (t.ex. `dc:title`) skrivs över och nya egenskaper (inklusive anpassade egenskaper som `cq:tags`) läggs till tillsammans med schemat.

XMP stöds och är aktiverat för de plattformar och filformat som beskrivs i [Tekniska krav.](/help/sites-deploying/technical-requirements.md)

## Redigerar metadataschema {#editing-metadata-schema}

Mer information om hur du redigerar metadataschemat finns i [Redigera metadata-schemaformulär](metadata-schemas.md#editing-metadata-schema-forms).

## Registrera ett anpassat namnutrymme i [!DNL Experience Manager] {#registering-a-custom-namespace-within-aem}

Du kan lägga till egna namnutrymmen i AEM. Precis som det finns fördefinierade namnutrymmen som cq, jcr och sling kan du ha ett namnutrymme för databasens metadata och XML-bearbetning.

1. Gå till administrationssidan för nodtypen `https://[AEM_server]:[port]/crx/explorer/nodetypes/index.jsp`.
1. Klicka eller tryck **[!UICONTROL Namespaces]** överst på sidan. Namnutrymmesadministrationssidan visas i ett fönster.

1. Om du vill lägga till ett namnutrymme klickar du på eller trycker **[!UICONTROL New]** längst ned.
1. Ange ett anpassat namnutrymme i XML-namnutrymmeskonventionen (ange id:t i form av en URI och ett associerat prefix för id:t) och klicka eller tryck **[!UICONTROL Save]**.

## Tips och begränsningar {#best-practices-limitations}

* Metadatauppdateringar via Touch-UI ändrar metadataegenskaperna i `dc` namnutrymme. Alla uppdateringar som görs via HTTP API ändrar metadataegenskaperna i `jcr` namnutrymme. Se [uppdatera metadata med HTTP API](/help/assets/mac-api-assets.md#update-asset-metadata).

>[!MORELIKETHIS]
>
>* [Om metadata och dess behov i Assets](metadata.md)

