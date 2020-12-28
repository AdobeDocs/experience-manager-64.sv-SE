---
title: Lösa filberoenden
seo-title: Lösa filberoenden
description: Primära 3D-modellfilberoenden, som texturschemafiler, löses automatiskt där det är möjligt. Den här funktionaliteten åstadkoms genom att AEM i närliggande resursmappar söka efter filer med samma namn som finns i 3D-filen.
seo-description: Primära 3D-modellfilberoenden, som texturschemafiler, löses automatiskt där det är möjligt. Den här funktionaliteten åstadkoms genom att AEM i närliggande resursmappar söka efter filer med samma namn som finns i 3D-filen.
uuid: b1b83cb7-b6e5-4417-9a53-b6d8bcf8d2e0
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 14754023-e7c4-4dc5-a9d8-408b81861d95
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 0%

---


# Lösa filberoenden{#resolving-file-dependencies}

Primära 3D-modellfilberoenden, som texturschemafiler, löses automatiskt där det är möjligt. Den här funktionaliteten åstadkoms genom att AEM i närliggande resursmappar söka efter filer med samma namn som finns i 3D-filen. Om ett eller flera beroenden inte kan lösas under förgranskningsfasen visas följande röda banderollmeddelande i [!UICONTROL Card View] på resurskortet:

![chlimage_1-189](assets/chlimage_1-189.png)

**Så här löser du filberoenden**:

1. Håll pekaren över banderollmeddelandet **[!UICONTROL Unresolved Dependencies]** på kortet i **[!UICONTROL Card View]** och tryck sedan på ikonen för utropstecknet.

   ![chlimage_1-190](assets/chlimage_1-190.png)

1. Tryck på fliken **[!UICONTROL Dependencies]** på sidan för metadataegenskaper.

   De filer som AEM inte kunde matcha automatiskt visas under kolumnen Originalbanor, i rött.

1. Gör något av följande:

   * **[!UICONTROL Browse to and select the dependencies]**. (Det här alternativet förutsätter att du redan har överfört beroendefilerna.

      1. Tryck på ikonen **[!UICONTROL File Browse]** till vänster om den röda banan.
      1. På sidan **[!UICONTROL Select Content]** navigerar du till den saknade filen och trycker sedan på filens kort för att markera den.
      1. Tryck på **[!UICONTROL Close]** (X-ikonen) i det övre vänstra hörnet av sidan **[!UICONTROL Select Content]** för att återgå till sidan **[!UICONTROL View Properties]**.
   * **[!UICONTROL Upload the dependencies]**. (Det här alternativet förutsätter att du ännu inte har överfört de saknade filerna.)

      1. Observera de saknade sökvägarna och filnamnen.
      1. I egenskapsidans övre högra hörn trycker du på **[!UICONTROL Close]**.

   När filerna har överförts går du tillbaka till sidan **[!UICONTROL View Properties > Dependencies]**. Den nyligen överförda resursen visas nu korrekt som refererade resurser.

   * **[!UICONTROL Ignore the dependencies]**.

      Om ett beroende som saknas inte längre behövs skriver du `n/a` under kolumnen **[!UICONTROL Referenced Asset]** i textfältet till vänster om den saknade filen så att AEM 3D ignorerar filen.



1. I det övre högra hörnet av sidan **[!UICONTROL View Properties]** trycker du på **[!UICONTROL Save]**.
1. Tryck på **[!UICONTROL Close]** för att återgå till **[!UICONTROL Card View]**.

   Resursen bearbetas automatiskt om med de nyligen lösta beroendena.

