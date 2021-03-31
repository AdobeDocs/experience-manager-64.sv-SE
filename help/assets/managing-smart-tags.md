---
title: Hantera smarta taggar
description: Uppdatera eller ta bort felaktiga smarta taggar för att förbättra taggarnas relevans
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
uuid: fd3eedf0-f222-45bf-aac7-90da6b7b7087
contentOwner: AG
discoiquuid: 3394b56a-3054-419b-9547-5740f8c35071
feature: Smarta taggar,Taggar,Sök
role: Yrkesverksamma inom affärsverksamhet
translation-type: tm+mt
source-git-commit: 29e3cd92d6c7a4917d7ee2aa8d9963aa16581633
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 2%

---


# Hantera smarta taggar {#managing-smart-tags}

Du kan strukturera smarta taggar om du vill ta bort felaktiga taggar som kan ha tilldelats dina varumärkesbilder så att endast de mest relevanta taggarna visas.

Genom att moderera smarta taggar kan du också förbättra taggbaserade sökningar efter bilder genom att se till att bilden visas i sökresultaten för de mest relevanta taggarna. I grund och botten eliminerar det riskerna för att bilder som inte är relaterade visas i sökresultaten.

Du kan också tilldela en högre rankning till en tagg för att öka dess relevans i förhållande till en bild. Om du befordrar en tagg för en bild ökar risken för att bilden visas i sökresultatet när en sökning utförs baserat på den aktuella taggen.

1. I rutan OmniSearch söker du efter resurser baserat på en tagg.
1. Inspect sökresultaten för att identifiera en bild som du inte tycker är relevant för sökningen.
1. Markera bilden och klicka/tryck sedan på ikonen **[!UICONTROL Manage Tags]** i verktygsfältet.
1. Granska taggarna på sidan **[!UICONTROL Manage Tags]**. Om du inte vill att bilden ska sökas igenom baserat på en viss tagg markerar du taggen och klickar/trycker sedan på ikonen **[!UICONTROL Delete]** i verktygsfältet. Du kan också klicka/trycka på symbolen (**[!UICONTROL X]**) som visas bredvid etiketten.
1. Om du vill tilldela en högre rankning till en tagg markerar du taggen och klickar/trycker på ikonen **[!UICONTROL Promote]** i verktygsfältet. Taggen som du befordrar flyttas till avsnittet **[!UICONTROL Tags]**.
1. Klicka/tryck på **[!UICONTROL Save]** och sedan på **[!UICONTROL OK]** för att stänga dialogrutan Slutfört.
1. Navigera till egenskapssidan för bilden. Observera att taggen som du befordrade har hög relevans och därför visas högre i sökresultaten.

## Förstå AEM sökresultat med smarta taggar {#understand-search-results-with-smart-tags}

Som standard kombineras söktermerna AEM en `AND`-sats. Om du använder smarta taggar ändras inte standardbeteendet. Om du använder smarta taggar läggs ytterligare en `OR`-sats till för att hitta någon av söktermerna i de använda smarta taggarna. Du kan till exempel söka efter `woman running`. Resurser med bara `woman` eller bara `running` nyckelord i metadata visas inte som standard i sökresultaten. En resurs som taggats med antingen `woman` eller `running` med smarta taggar visas i en sådan sökfråga. Sökresultaten är en kombination av

* resurser med båda nyckelorden `woman` och `running` i metadata.
* resurser som är smarta taggade med något av nyckelorden.

Sökresultaten som matchar alla söktermer i metadatafält visas först, följt av sökresultaten som matchar någon av söktermerna i de smarta taggarna. I ovanstående exempel är den ungefärliga visningsordningen för sökresultat:

1. matchar `woman running` i de olika metadatafälten.
1. matchar `woman running` i smarta taggar.
1. matchar `woman` eller `running` i smarta taggar.
