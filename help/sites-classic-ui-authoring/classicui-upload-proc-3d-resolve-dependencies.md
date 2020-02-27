---
title: Lösa filberoenden
seo-title: Lösa filberoenden
description: Primära 3D-modellfilberoenden, som texturschemafiler, löses automatiskt där det är möjligt. Den här funktionaliteten uppnås genom att AEM söker i närliggande resursmappar efter filer med samma namn som finns i 3D-filen.
seo-description: Primära 3D-modellfilberoenden, som texturschemafiler, löses automatiskt där det är möjligt. Den här funktionaliteten uppnås genom att AEM söker i närliggande resursmappar efter filer med samma namn som finns i 3D-filen.
uuid: b1b83cb7-b6e5-4417-9a53-b6d8bcf8d2e0
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
topic-tags: authoring
content-type: reference
discoiquuid: 14754023-e7c4-4dc5-a9d8-408b81861d95
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Lösa filberoenden{#resolving-file-dependencies}

Primära 3D-modellfilberoenden, som texturschemafiler, löses automatiskt där det är möjligt. Den här funktionaliteten uppnås genom att AEM söker i närliggande resursmappar efter filer med samma namn som finns i 3D-filen. Om ett eller flera beroenden inte kan lösas under förgranskningsfasen visas följande röda banderollmeddelande i [!UICONTROL kortvyn]på resurskortet:

![chlimage_1-189](assets/chlimage_1-189.png)

**Så här löser du filberoenden**:

1. Håll pekaren över banderollmeddelandet **[!UICONTROL Olösta beroenden]** på kortet i **[!UICONTROL kortvyn]** och tryck sedan på ikonen för utropstecknet.

   ![chlimage_1-190](assets/chlimage_1-190.png)

1. Tryck på fliken **[!UICONTROL Beroenden]** på egenskapssidan för metadata.

   De filer som AEM inte kunde lösa automatiskt visas i röd lista under kolumnen Originalbanor.

1. Gör något av följande:

   * **[!UICONTROL Bläddra till och välj beroenden]**. (Det här alternativet förutsätter att du redan har överfört beroendefilerna.

      1. Tryck på ikonen **[!UICONTROL Filbläddring]** till vänster om den röda sökvägen.
      1. Navigera till den saknade filen på sidan **[!UICONTROL Välj innehåll]** och tryck sedan på filens kort för att markera den.
      1. I det övre vänstra hörnet på sidan **[!UICONTROL Välj innehåll]** trycker du på **[!UICONTROL Stäng]** (X-ikonen) för att gå tillbaka till sidan **[!UICONTROL Visa egenskaper]** .
   * **[!UICONTROL Överför beroenden]**. (Det här alternativet förutsätter att du ännu inte har överfört de saknade filerna.)

      1. Observera de saknade sökvägarna och filnamnen.
      1. I egenskapsidans övre högra hörn trycker du på **[!UICONTROL Stäng]**.
   När filerna har överförts går du tillbaka till sidan **[!UICONTROL Visa egenskaper > Beroenden]** . Den nyligen överförda resursen visas nu korrekt som refererade resurser.

   * **[!UICONTROL Ignorera beroenden]**.

      Om ett beroende som saknas inte längre behövs, under kolumnen **[!UICONTROL Refererad resurs]** , i textfältet till vänster om den saknade filen, skriver du `n/a` så att AEM 3D ignorerar filen.



1. I det övre högra hörnet av sidan **[!UICONTROL Visa egenskaper]** trycker du på **[!UICONTROL Spara]**.
1. Tryck på **[!UICONTROL Stäng]** för att återgå till **[!UICONTROL kortvyn]**.

   Resursen bearbetas automatiskt om med de nyligen lösta beroendena.

