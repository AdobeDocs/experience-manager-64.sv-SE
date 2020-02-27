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
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Lösa filberoenden {#resolving-file-dependencies}

Primära 3D-modellfilberoenden, som texturschemafiler, löses automatiskt där det är möjligt. Den här funktionaliteten uppnås genom att AEM söker i närliggande resursmappar efter filer med samma namn som finns i 3D-filen. Om ett eller flera beroenden inte kan lösas under förgranskningsfasen visas följande röda banderollmeddelande i **[!UICONTROL kortvyn]** på resurskortet:

![chlimage_1-124](assets/chlimage_1-124.png)

**Så här löser du filberoenden**:

1. I **[!UICONTROL kortvyn]** för du pekaren över banderollmeddelandet **[!UICONTROL Olösta beroenden]** på kortet och trycker sedan på ikonen **[!UICONTROL Exclamation Point]** (Exclamation Point).

   ![chlimage_1-125](assets/chlimage_1-125.png)

1. På sidan **[!UICONTROL Metadataegenskaper]** trycker du på fliken **[!UICONTROL Beroenden]** .

   De filer som AEM inte kunde lösa automatiskt visas i röd lista under kolumnen **[!UICONTROL Originalbanor]** .

1. Gör något av följande:

   * **Bläddra till och välj beroenden**. (Det här alternativet förutsätter att du redan har överfört beroendefilerna.

      1. Tryck på ikonen **[!UICONTROL Filbläddring]** till vänster om den röda sökvägen.
      1. Navigera till den saknade filen på sidan **[!UICONTROL Välj innehåll]** och tryck sedan på filens kort för att markera den.
      1. I det övre vänstra hörnet på sidan **[!UICONTROL Välj innehåll]** trycker du på **[!UICONTROL Stäng]** (X-ikonen) för att gå tillbaka till sidan **[!UICONTROL Visa egenskaper]** .
   * **Överför beroenden**. (Det här alternativet förutsätter att du ännu inte har överfört de saknade filerna.)

      1. Observera de saknade sökvägarna och filnamnen.
      1. I egenskapsidans övre högra hörn trycker du på **[!UICONTROL Stäng]**.
   När filerna har överförts går du tillbaka till sidan **[!UICONTROL Visa egenskaper > Beroenden]** . Den nyligen överförda resursen visas nu korrekt som refererade resurser.

   * **Ignorera beroenden**.

      Om ett beroende som saknas inte längre behövs, under kolumnen **[!UICONTROL Refererad resurs]** , i textfältet till vänster om den saknade filen, skriver du `n/a` så att AEM 3D ignorerar filen.



1. I det övre högra hörnet av sidan **[!UICONTROL Visa egenskaper]** trycker du på **[!UICONTROL Spara]**.
1. Tryck på **[!UICONTROL Stäng]** för att återgå till **[!UICONTROL kortvyn]**.

   Resursen bearbetas automatiskt om med de nyligen lösta beroendena.

