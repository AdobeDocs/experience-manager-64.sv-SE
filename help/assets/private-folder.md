---
title: Delning av privata mappar
description: Lär dig hur du skapar en privat mapp i Adobe Experience Manager-resurserna (AEM) och delar den med andra användare och tilldelar olika behörigheter till dem.
contentOwner: AG
translation-type: tm+mt
source-git-commit: 0d70a672a2944e2c03b54beb3b5f734136792ab1

---


# Delning av privata mappar {#private-folder-sharing}

Du kan skapa en privat mapp i användargränssnittet för Adobe Experience Manager (AEM) Assets som är tillgängligt enbart för dig. Du kan dela den här privata mappen med andra användare och tilldela olika behörigheter till dem. Beroende på vilken behörighetsnivå du tilldelar kan användare utföra olika åtgärder i mappen, till exempel visa resurser i mappen eller redigera resurserna.

1. I resurskonsolen: tryck/klicka på **[!UICONTROL Skapa]** i verktygsfältet och välj sedan **[!UICONTROL Mapp]** på menyn.

   ![chlimage_1-411](assets/chlimage_1-411.png)

1. I dialogrutan **[!UICONTROL Lägg till mapp]** anger du en rubrik och ett namn (valfritt) för mappen och väljer **[!UICONTROL Privat]**.

   ![chlimage_1-412](assets/chlimage_1-412.png)

1. Tryck/klicka på **[!UICONTROL Skapa]**. En privat mapp skapas i användargränssnittet.

   ![chlimage_1-413](assets/chlimage_1-413.png)

1. Om du vill dela mappen med andra användare och tilldela behörigheter till dem markerar du mappen och klickar på/trycker på ikonen **[!UICONTROL Egenskaper]** i verktygsfältet.

   ![chlimage_1-414](assets/chlimage_1-414.png)

   >[!NOTE]
   >
   >Mappen visas inte för andra användare förrän du delar den.

1. På sidan Mappegenskaper väljer du en användare i listan **[!UICONTROL Lägg till användare]** , tilldelar en roll till användaren i din privata mapp och klickar på **[!UICONTROL Lägg till]**.

   ![chlimage_1-415](assets/chlimage_1-415.png)

   >[!NOTE]
   >
   >Du kan tilldela olika roller, till exempel redigeraren, ägaren eller visningsprogrammet, till användaren som du delar mappen med. Om du tilldelar användaren en ägarroll har användaren redigeringsbehörighet för mappen. Dessutom kan användaren dela mappen med andra. Om du tilldelar en redigeringsroll kan användaren redigera resurserna i din privata mapp. Om du tilldelar en visningsprogramroll kan användaren bara visa resurserna i din privata mapp.

1. Click **[!UICONTROL Save]**. Beroende på vilken roll du tilldelar tilldelas användaren en uppsättning behörigheter i din privata mapp när användaren loggar in på AEM Resurser.
1. Klicka på **[!UICONTROL OK]** för att stänga bekräftelsemeddelandet.
1. Användaren som du delar mappen med får ett delningsmeddelande. Logga in på AEM Assets med användarens inloggningsuppgifter för att visa meddelandet.

   ![chlimage_1-416](assets/chlimage_1-416.png)

1. Tryck/klicka på meddelandeikonen för att öppna listan med meddelanden.

   ![chlimage_1-417](assets/chlimage_1-417.png)

1. Klicka på/tryck på posten för den privata mappen som delas av administratören för att öppna mappen.

>[!NOTE]
>
>Om du vill kunna skapa en privat mapp måste du ha behörigheten Läs och Redigera åtkomstkontrollista för den överordnade mappen som du vill skapa en privat mapp i. Om du inte är administratör aktiveras dessa behörigheter inte som standard för */content/dam*. I så fall måste du först skaffa dessa behörigheter för ditt användar-ID/din grupp innan du försöker skapa privata mappar eller visa mappinställningar.

