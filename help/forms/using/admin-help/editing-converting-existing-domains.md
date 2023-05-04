---
title: Redigera och konvertera befintliga domäner
seo-title: Editing and converting existing domains
description: Lär dig hur du ändrar inställningarna för befintliga domäner på sidan Domänhantering. Konvertera en befintlig företagsdomän till en hybriddomän eller vice versa.
seo-description: Learn how to change the settings for existing domains from the Domain Management page. Convert an existing enterprise domain to a hybrid domain or vice versa.
uuid: 4cc9547e-b4ec-4588-b1cf-18720f06149a
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/setting_up_and_managing_domains
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 44dec184-3ef7-4ba6-a87f-ad171d3cb188
exl-id: 07ca7715-f7b3-40e0-95bc-e05f0662ed08
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '346'
ht-degree: 0%

---

# Redigera och konvertera befintliga domäner{#editing-and-converting-existing-domains}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan ändra inställningarna för befintliga domäner på sidan Domänhantering. Du kan också konvertera en befintlig företagsdomän till en hybriddomän.

## Redigera en befintlig domän {#edit-an-existing-domain}

1. I administrationskonsolen klickar du på Inställningar > Användarhantering > Domänhantering.
1. Klicka på namnet på den domän som ska redigeras.
1. Om du vill ändra domännamnet ändrar du texten i rutan Namn.
1. Om du vill ändra autentiseringsinformationen för ett företag eller en hybriddomän klickar du på lämpligt autentiseringsnamn längst ned på sidan. På sidan Redigera autentisering ändrar du inställningarna efter behov. (Se [Autentiseringsinställningar](/help/forms/using/admin-help/configuring-authentication-providers.md#authentication-settings).)
1. Om du vill ändra kataloginformationen för en företagsdomän klickar du på lämpligt katalognamn längst ned på sidan. Ändra inställningarna på sidan Redigera katalog. (Se [Lägga till kataloger eller anpassade SPI-filer](/help/forms/using/admin-help/configuring-directories.md#adding-directories-or-custom-spis).)
1. Klicka på OK när du är klar med ändringarna.

## Konvertera en företagsdomän till en hybriddomän {#convert-an-enterprise-domain-to-a-hybrid-domain}

1. I administrationskonsolen klickar du på Inställningar > Användarhantering > Domänhantering.
1. Klicka på namnet på den företagsdomän som ska konverteras.
1. Klicka på Konvertera till hybrid-domän.
1. Granska informationen om användar- och gruppdata och autentisering av användare och klicka på OK.
1. Redigera inställningarna för den hybriddomänen och klicka på OK.

>[!NOTE]
>
>Om den företagsdomän som du konverterar inte innehåller kataloginställningar går alla LDAP-autentiseringsinställningar förlorade.

## Konvertera en hybriddomän till en företagsdomän {#convert-a-hybrid-domain-to-an-enterprise-domain}

1. I administrationskonsolen klickar du på Inställningar > Användarhantering > Domänhantering.
1. Klicka på namnet på den hybriddomän som ska konverteras.
1. Klicka på Konvertera till företagsdomän.
1. Granska informationen om användar- och gruppdata och autentisering av användare och klicka på OK.
1. Klicka på Lägg till katalog och konfigurera nödvändig kataloginformation. (Se [Lägga till kataloger eller anpassade SPI-filer](/help/forms/using/admin-help/configuring-directories.md#adding-directories-or-custom-spis).)
