---
title: Känna igen giltiga och utgångna certifikat i PDF-dokument
seo-title: Recognizing valid and expired certificates in PDF documents
description: Lär dig hur du känner igen giltiga och utgångna certifikat i PDF-dokument.
seo-description: Learn how to recognize valid and expired certificates in PDF documents.
uuid: ceeff57a-586f-4f7b-852f-2a637f003d7e
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_acrobat_reader_dc_extensions
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 4559218a-65ba-4577-ad26-7721e28971bc
exl-id: 6e2c109c-381f-455d-bd1d-b08c37c0bd67
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---

# Känna igen giltiga och utgångna certifikat i PDF-dokument {#recognizing-valid-and-expired-certificates-in-pdf-documents}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När ett PDF-dokument som har användningsrättigheter som används av Reader Extensions öppnas i Adobe Reader visas ett statusfält som beskriver de specifika användningsrättigheter som är aktiverade i PDF-dokumentet.

När det digitala certifikatet som anger användningsrättigheterna för ett PDF-dokument upphör att gälla och PDF-dokumentet öppnas i Adobe Reader visas en dialogruta som informerar användaren om att PDF-dokumentet har användningsbehörighet, men dessa rättigheter är inaktiverade. Även om meddelandet anger att dokumentet i PDF har ändrats eller manipulerats behöver detta inte nödvändigtvis vara fallet. Det här meddelandet visas i Adobe Reader när ett certifikat upphör att gälla eller när ett dokument ändras. I Adobe Reader 7.0.x eller senare kan du inte avgöra vilket fall som är det aktuella problemet.

När du har stängt dialogrutan öppnas dokumentet PDF. Användningsrättigheterna som tillämpades med Acrobat Reader DC-tillägg är inte tillgängliga som förväntat. Om PDF-dokumentet är ett interaktivt formulär låses formulärfälten och användaren kan inte ändra formulärdata.
