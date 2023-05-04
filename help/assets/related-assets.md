---
title: Relaterade tillgångar
description: Lär dig hur du relaterar resurser som delar vissa gemensamma attribut. Du kan också använda funktionen för att skapa käll-/härledda relationer mellan resurser.
contentOwner: AG
feature: Asset Management,Collaboration
role: User
exl-id: d19544c4-c8e7-4a39-9c86-15a46dca848e
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '624'
ht-degree: 2%

---

# Relaterade tillgångar {#related-assets}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med Adobe Experience Manager Assets kan du manuellt relatera resurser baserat på organisationens behov med hjälp av funktionen Relaterade resurser. Du kan till exempel relatera en licensfil till en resurs eller en bild/video på ett liknande ämne. Du kan relatera resurser som delar vissa gemensamma attribut. Du kan också använda funktionen för att skapa käll-/härledda relationer mellan resurser. Om du till exempel har en PDF-fil som genereras från en INDD-fil kan du koppla PDF-filen till dess INDD-källfil.

På så sätt kan du dela en fil med låg upplösning (t.ex. PDF/JPG) till leverantörer/byråer och göra den högupplösta filen (t.ex. INDD) tillgänglig endast på begäran.

## Relaterade resurser {#relating-assets}

1. I gränssnittet Resurser öppnar du egenskapssidan för en resurs som du vill relatera.

   ![chlimage_1-272](assets/chlimage_1-272.png)

   Du kan också välja resursen i listvyn.

   ![chlimage_1-273](assets/chlimage_1-273.png)

   Du kan också välja resursen från en samling.

   ![chlimage_1-274](assets/chlimage_1-274.png)

1. Om du vill koppla en annan resurs till den valda resursen klickar/trycker du på **[!UICONTROL Relate]** -ikonen i verktygsfältet.

   ![chlimage_1-275](assets/chlimage_1-275.png)

1. Gör något av följande:

   * Om du vill relatera resursens källfil väljer du **[!UICONTROL Source]** från listan.
   * Om du vill relatera en härledd fil väljer du **[!UICONTROL Derived]** från listan.
   * Om du vill skapa en dubbelriktad relation mellan resurserna väljer du **[!UICONTROL Others]** från listan.

   ![chlimage_1-276](assets/chlimage_1-276.png)

1. Från **[!UICONTROL Select Asset]** navigera till platsen för resursen som du vill relatera och markera den.

   ![chlimage_1-277](assets/chlimage_1-277.png)

1. Klicka/tryck på **[!UICONTROL Confirm]** ikon.
1. Klicka/tryck **[!UICONTROL OK]** för att stänga dialogrutan. Beroende på ditt val av relation i steg 3 listas den relaterade tillgången under en lämplig kategori i **[!UICONTROL Related]** -avsnitt. Om den resurs du har relaterat är källfilen för den aktuella resursen visas den under **[!UICONTROL Source]**.

   ![chlimage_1-278](assets/chlimage_1-278.png)

1. Om du vill ta bort kopplingen för en resurs klickar/trycker du på **[!UICONTROL Unrelate]** -ikonen i verktygsfältet.

   ![chlimage_1-279](assets/chlimage_1-279.png)

1. Markera de resurser som du vill ta bort kopplingen för i **[!UICONTROL Remove Relations]** och klicka/tryck **[!UICONTROL Unrelate]**.

   ![chlimage_1-280](assets/chlimage_1-280.png)

1. Klicka/tryck **[!UICONTROL OK]** för att stänga dialogrutan. Resurserna som du har tagit bort relationer för tas bort från listan över relaterade resurser under **[!UICONTROL Related]** -avsnitt.

## Översätter relaterade resurser {#translating-related-assets}

Det är också praktiskt att skapa käll-/härledda relationer mellan resurser med hjälp av funktionen Relaterade resurser i översättningsarbetsflöden. När du kör ett översättningsarbetsflöde på en härledd resurs, [!DNL Experience Manager] Resurser hämtar automatiskt alla resurser som källfilen refererar till och inkluderar dem för översättning. På så sätt översätts den resurs som källresursen refererar till tillsammans med källresursen och de härledda resurserna. Tänk dig till exempel ett scenario där den engelska språkkopian innehåller en härledd resurs och dess källfil som visas.

![chlimage_1-281](assets/chlimage_1-281.png)

Om källfilen är relaterad till en annan resurs [!DNL Experience Manager] Resurser hämtar den refererade resursen och inkluderar den för översättning.

![chlimage_1-282](assets/chlimage_1-282.png)

1. Översätt resurserna i källmappen till ett målspråk genom att följa stegen i [Skapa ett nytt översättningsprojekt](translation-projects.md#create-a-new-translation-project). I det här fallet kan du till exempel översätta dina resurser till franska.
1. Öppna översättningsmappen på sidan Projekt.

   ![chlimage_1-283](assets/chlimage_1-283.png)

1. Klicka/tryck på projektpanelen för att öppna informationssidan.

   ![chlimage_1-284](assets/chlimage_1-284.png)

1. Klicka på/tryck på ellipserna under översättningsjobbkortet för att visa översättningsstatusen.

   ![chlimage_1-285](assets/chlimage_1-285.png)

1. Markera resursen och klicka/tryck sedan på **[!UICONTROL Reveal in Assets]** i verktygsfältet för att visa översättningsstatusen för resursen.

   ![chlimage_1-286](assets/chlimage_1-286.png)

1. Om du vill kontrollera om de resurser som är relaterade till källan har översatts klickar/trycker du på källresursen.

   ![chlimage_1-287](assets/chlimage_1-287.png)

1. Välj den resurs som är relaterad till källan och klicka/tryck sedan **[!UICONTROL Reveal in Assets]**. Den översatta relaterade resursen visas.

   ![chlimage_1-288](assets/chlimage_1-288.png)
