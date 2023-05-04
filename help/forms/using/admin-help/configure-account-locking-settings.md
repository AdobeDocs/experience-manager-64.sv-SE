---
title: Konfigurera inställningar för låsning av konto
seo-title: Configure account-locking settings
description: Använd alternativet Aktivera låsning av konto om du vill låsa användarkonton efter ett angivet antal på varandra följande autentiseringsfel.
seo-description: Use the Enable Account Locking option to lock user accounts after a specified number of consecutive authentication failures.
uuid: 5ff3fb76-8b11-4818-9a75-40ed8e121da5
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/setting_up_and_managing_domains
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: d4409c6b-f4ef-499c-8daa-e93a163ff8ab
exl-id: e407c643-5753-447e-ad4e-deb7b9eb2b55
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 0%

---

# Konfigurera inställningar för låsning av konto {#configure-account-locking-settings}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När du lägger till en domän anger du om kontolåsning ska aktiveras. När alternativet Aktivera låsning av konto är markerat låses användarkonton efter ett angivet antal på varandra följande autentiseringsfel. Efter en viss tid kan användaren försöka autentisera igen. Den här funktionen förhindrar användare från att testa olika autentiseringskombinationer för att få åtkomst till systemet.

Använd inställningarna på sidan Domänhantering för att ange maximalt antal autentiseringsfel och hur länge kontona är låsta. De här inställningarna gäller för alla domäner där kontolåsning är aktiverat.

1. I administrationskonsolen klickar du på **[!UICONTROL Settings > User Management > Domain Management]**.
1. I rutan Maximalt antal misslyckade autentiseringar i följd anger du antalet gånger i följd som en användare inte kan försöka logga in innan kontot är låst. Standardvärdet är 20.
1. I rutan Lås upp kontot efter (minuter) anger du antalet minuter som användarkontot är låst. Efter det angivna antalet minuter kan användaren försöka logga in igen. Standardvärdet är 30.
1. Klicka på **[!UICONTROL Save]**.
