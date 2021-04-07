---
title: Lösa filberoenden
seo-title: Lösa filberoenden
description: Hur du löser 3D-filberoenden som t.ex. texturschemafiler när automatisk upplösning misslyckas.
seo-description: Hur du löser 3D-filberoenden som t.ex. texturschemafiler när automatisk upplösning misslyckas.
uuid: 49cefabf-147b-4a78-90f3-0f2d6a8e8cae
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: 05b7410b-82a1-4267-ac07-2edbc29e9ee8
exl-id: 088d32a8-a47e-4ae6-a171-8d327d3dac64
feature: 3D-resurser
role: Business Practitioner
translation-type: tm+mt
source-git-commit: f9faa357f8de92d205f1a297767ba4176cfd1e10
workflow-type: tm+mt
source-wordcount: '316'
ht-degree: 0%

---

# Lösa filberoenden {#resolving-file-dependencies}

Primära 3D-modellfilberoenden, som texturschemafiler, löses automatiskt där det är möjligt. Den här funktionaliteten åstadkoms genom att AEM i närliggande resursmappar söka efter filer med samma namn som finns i 3D-filen. Om ett eller flera beroenden inte kan lösas under förgranskningsfasen visas följande röda banderollmeddelande i **[!UICONTROL Card View]** på resurskortet:

![chlimage_1-124](assets/chlimage_1-124.png)

**Så här löser du filberoenden**:

1. Håll pekaren över banderollmeddelandet **[!UICONTROL Unresolved Dependencies]** på kortet i **[!UICONTROL Card View]** och tryck sedan på ikonen **[!UICONTROL Exclamation Point]**.

   ![chlimage_1-125](assets/chlimage_1-125.png)

1. Tryck på fliken **[!UICONTROL Dependencies]** på sidan **[!UICONTROL Metadata Properties]**.

   Filerna som AEM inte kunde matcha automatiskt visas i rött under kolumnen **[!UICONTROL Original Paths]**.

1. Gör något av följande:

   * **Bläddra till och välj beroenden**. (Det här alternativet förutsätter att du redan har överfört beroendefilerna.

      1. Tryck på ikonen **[!UICONTROL File Browse]** till vänster om den röda banan.
      1. På sidan **[!UICONTROL Select Content]** navigerar du till den saknade filen och trycker sedan på filens kort för att markera den.
      1. Tryck på **[!UICONTROL Close]** (X-ikonen) i det övre vänstra hörnet av sidan **[!UICONTROL Select Content]** för att återgå till sidan **[!UICONTROL View Properties]**.
   * **Överför beroenden**. (Det här alternativet förutsätter att du ännu inte har överfört de saknade filerna.)

      1. Observera de saknade sökvägarna och filnamnen.
      1. I egenskapsidans övre högra hörn trycker du på **[!UICONTROL Close]**.

   När filerna har överförts går du tillbaka till sidan **[!UICONTROL View Properties > Dependencies]**. Den nyligen överförda resursen visas nu korrekt som refererade resurser.

   * **Ignorera beroenden**.

      Om ett beroende som saknas inte längre behövs skriver du `n/a` under kolumnen **[!UICONTROL Referenced Asset]** i textfältet till vänster om den saknade filen så att AEM 3D ignorerar filen.



1. I det övre högra hörnet av sidan **[!UICONTROL View Properties]** trycker du på **[!UICONTROL Save]**.
1. Tryck på **[!UICONTROL Close]** för att återgå till **[!UICONTROL Card View]**.

   Resursen bearbetas automatiskt om med de nyligen lösta beroendena.
