---
title: Ändra teckenuppsättningen
seo-title: Change the character set
description: Du kan ange den teckenuppsättning som används för att koda utdataströmmen. Lär dig hur du kan ändra teckenuppsättningen.
seo-description: You can specify the character set used to encode the output stream. Learn how you can change the character set.
uuid: ecb0c3ff-368c-4553-80e4-aa35fc15af62
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 811b31f8-5465-4fb2-b1f9-513936041771
exl-id: 7961efc6-4b11-423a-871d-7b37e3f36781
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 0%

---

# Ändra teckenuppsättningen {#change-the-character-set}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan ange den teckenuppsättning som används för att koda utdataströmmen.

1. I administrationskonsolen klickar du på **[!UICONTROL Services > output]**.
1. Välj en teckenuppsättning i listan Teckenuppsättning under Internationalisering. Den här inställningen är beroende av `TransformationFormat` och `PrintFormat` som anges via API. Om du vill ange en annan teckenuppsättning än de som visas väljer du Anpassad och anger ett kodningsvärde i rutan som visas.

   If `TransformationFormat` är PDF och PDF/A eller `PrintFormat` är PCL, PostScript, Zebra-etikett, IPL, DPL, TPCL, GenericColorPCL eller GenericPSLevel3. Endast specifika teckenuppsättningar stöds.

   Teckenuppsättningen måste vara ett giltigt kanoniskt namn. Standardvärdet är ISO-8859-1.

1. Klicka på **[!UICONTROL Save]**.
