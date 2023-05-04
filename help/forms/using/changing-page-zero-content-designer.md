---
title: Ändra sidans nollinnehåll i Designer
seo-title: Changing Page Zero content in Designer
description: Vet du hur du kan ändra meddelandet som visas på sidnoll i en XFA-PDF när du visar det i ett visningsprogram som inte kommer från Adobe PDF?
seo-description: Do you know how you can change the message displayed on Page Zero of an XFA PDF when viewing it in a non-Adobe PDF viewer?
uuid: 5697f203-bb24-437d-a692-bc4bc2609b88
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: develop
discoiquuid: f458054e-885c-4c7a-afcd-ad1e4465e0c1
feature: Adaptive Forms
exl-id: 0ae34ddd-9a8d-48df-af2d-80c3fe6abd62
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '279'
ht-degree: 1%

---

# Ändra sidans nollinnehåll i Designer {#changing-page-zero-content-in-designer}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Sidnollinnehåll visas som standard när ett visningsprogram som inte är från Adobe PDF, t.ex. PDF i Chrome eller Firefox, inte kan läsa innehållet i formuläret PDF/XFA. Standardmeddelandet Sidan är noll visas nedan.

![defaultpage0message](assets/defaultpage0message.png)

Med AEM Forms Feature Pack 1 version av Designer kan du ändra meddelandet som visas på sidan noll. Gör så här om du vill ändra sidans nollmeddelande:

1. Kontrollera att du har AEM Forms Feature Pack 1 version av Designer installerad. Du kan kontrollera versionen från Om-skärmen i Designer.

1. Öppna formuläret som du vill ändra sidans nollinnehåll för.

1. Klicka **Arkiv > Formuläregenskaper**.

1. I dialogrutan Formuläregenskaper klickar du på ![plus](assets/plus.png) (Plus-ikon) om du vill lägga till en anpassad egenskap.

1. Ange **pagezerocontent** som namnet på egenskapen.
1. Lägg till det nya sidans nollmeddelande i RTF-format som värde. Till exempel:

   `<body xmlns="https://www.w3.org/1999/xhtml" xmlns:xfa="https://www.xfa.org/schema/xfa-data/1.0/"><p style="font-family:'Times';font-size:12pt;letter-spacing:0in"><span style="xfa-spacerun:yes"> </span></p><p style="font-family:'Times';font-size:12pt;letter-spacing:0in">You are seeing this message maybe because you are using a non Adobe PDF Viewer or an Old version of Adobe Reader. You can upgrade to the latest version of Adobe Reader for Windows, Mac, or Linux by visiting <span style="xfa-spacerun:yes"> </span>https://www.adobe.com/go/reader_download.</p><p style="font-family:'Times';font-size:12pt;letter-spacing:0in"><span style="xfa-spacerun:yes"> </span></p><p style="font-family:'Times';font-size:12pt;letter-spacing:0in">For more assistance with Adobe Reader visit <span style="xfa-spacerun:yes"> </span>https://www.adobe.com/go/acrreader.</p></body>`

1. Spara formuläret som PDF.

1. Visa formuläret PDF i webbläsaren för att bekräfta att meddelandet har uppdaterats. Exempelvärdet ovan ser ut så här:

   ![ändrat meddelande](assets/changedmessage.png)

>[!NOTE]
>
>Den anpassade egenskap som du just skapade kanske inte visas korrekt i dialogrutan Formuläregenskaper när du öppnar formuläret igen. Det fungerar dock bra och formuläret visar det uppdaterade sidnollmeddelandet.
