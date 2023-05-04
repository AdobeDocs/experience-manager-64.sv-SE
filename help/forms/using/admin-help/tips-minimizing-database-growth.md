---
title: Tips för att minimera databastillväxt
seo-title: Tips for minimizing database growth
description: I långvariga processer lagras processdata i AEM. Tillväxten i AEM kan minimeras med några enkla processkonfigurations- och produktkonfigurationsstrategier.
seo-description: Long-lived processes store process data in the AEM forms database. The growth of the AEM forms database can be minimized using a few easy process design and product configuration strategies.
uuid: 13f99d4f-848e-451e-90d9-55e202dc0bdb
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/maintaining_the_aem_forms_database
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 89441336-babc-4d1f-9053-d1566cd42d22
exl-id: 7b266170-c7e2-42e7-8ee0-153e1e73a901
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---

# Tips för att minimera databastillväxt {#tips-for-minimizing-database-growth}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

I långvariga processer lagras processdata i AEM. Tillväxten i AEM kan minimeras med några enkla processkonfigurations- och produktkonfigurationsstrategier.

## Processdesigntips {#process-design-tips}

Använd kortvariga processer när det är möjligt. Kortlivade processer lagrar inte processdata i databasen. Nackdelen med kortlivade processer är att deras status och tillstånd inte spåras i administrationskonsolen och att det inte finns någon historik över processen.

Vissa tjänståtgärder, till exempel Tilldela uppgift (användartjänst), kräver att de används i långvariga processer. I det här fallet kan du segmentera processen i flera underprocesser och göra dem kortvariga när det är möjligt. Om du använder den här strategin bör kortlivade underprocesser hantera stora dataobjekt, som dokumentvärden.

Använd variabler sparsamt. När du använder långvariga processer tilldelas utrymme för varje processinstans i databasen för varje variabel i processen. Strategisk användning av variabler kan spara mycket utrymme. Du kan till exempel skriva över variabelvärden när gamla värden inte längre behövs i processen. Och ta bort alla variabler som du har skapat och inte använder. Du kan validera processen för att hitta oanvända variabler.

Använd enkla variabeltyper (till exempel sträng eller int) och undvik att använda komplexa variabeltyper när det är möjligt. Databasutrymme tilldelas för variabler även när de inte innehåller något värde. Komplexa variabler kräver vanligtvis mer utrymme än enkla.

## Tips för produktadministration {#product-administration-tips}

Använd global dokumentlagring (GDS) effektivt. GDS-katalogen på formulärservern används för att lagra bland annat filer som skickas till tjänster som är en del av AEM formulär i processer. För att förbättra prestandan lagras mindre dokument i stället i minnet och sparas i databasen.

administrationskonsolen visar egenskapen Maximal intern dokumentstorlek för standarddokument för att konfigurera den maximala storleken på dokument som lagras i minnet och som finns kvar i databasen. (Se [Konfigurera allmänna inställningar AEM formulär](/help/forms/using/admin-help/configure-general-aem-forms-settings.md#configure-general-aem-forms-settings).) Om du anger den här egenskapen till ett lågt värde sparas de flesta dokument i GDS-katalogen i stället för i databasen. Fördelen är att du enklare kan ta bort filerna när de inte längre behövs när de lagras i GDS-katalogen.
