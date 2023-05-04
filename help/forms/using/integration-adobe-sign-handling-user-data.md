---
title: Integrering med Acrobat Sign | Hantera användardata
seo-title: Integration with Acrobat Sign | Handling user data
description: AEM Forms kan integreras med Acrobat Sign för att möjliggöra e-signaturarbetsflöden i anpassningsbara formulär för att bearbeta formulär eller avtal för arbetsflöden inom juridik, försäljning, lön och personaladministration. Gå ett steg längre när det gäller användardata, datalager samt få tillgång till och ta bort användardata.
seo-description: AEM Forms integrates with Acrobat Sign to enable e-signature workflows in adaptive forms to process forms or agreements for legal, sales, payroll, human resource management workflows. Dig deeper on user data, data stores, and access and delete user data.
uuid: cb3a455d-2e33-44c8-8f71-3a7ecd939cd8
topic-tags: grdp
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: e9e0d8fb-955e-4021-9e9a-9c95c6ffe88d
feature: Acrobat Sign
role: Admin
exl-id: c2061de7-8627-4595-b96c-aa2d6abffddd
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 0%

---

# Integrering med Acrobat Sign | Hantera användardata {#integration-with-adobe-sign-handling-user-data}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM Forms kan integreras med Acrobat Sign för att möjliggöra e-signaturarbetsflöden i anpassningsbara formulär för att bearbeta formulär eller avtal för arbetsflöden inom juridik, försäljning, lön och personaladministration. Det möjliggör signering för en eller flera användare, sekventiella och samtidiga signeringsarbetsflöden, signering av formulär som anonyma eller inloggade användare samt flera sätt att autentisera användare.

När en eller flera signerare signerar och skickar ett anpassat formulär skapas ett Acrobat Sign-avtal som innehåller information om signerarna.

Mer information om AEM Forms integrering med Acrobat Sign finns i [Använda Acrobat Sign i en adaptiv form](/help/forms/using/working-with-adobe-sign.md).

## Användardata och datalager {#data}

Anpassningsbart formulär som kan aktiveras av Acrobat Sign innehåller information om signerare och kan innehålla andra användardata som samlats in med det adaptiva formuläret. Acrobat Sign-tjänsten sparar användardata med signaturen i avtalet. Avtalet sparas på en Acrobat Sign-server som är konfigurerad i AEM Forms molntjänster. Om det adaptiva formuläret dessutom är konfigurerat att använda Forms Portal-åtgärden, sparas avtalsdata i formulärportalens datalager tillsammans med formulärdata.

## Få åtkomst till och ta bort användardata {#access-and-delete-user-data}

Användardata samlas in i avtalet men sparas inte i någon av tjänsttabellerna. Med Acrobat Sign kan administratörer själva välja hur de vill hantera data som de har kontroll över i tjänsten. Sekretessadministratörer för Acrobat Sign-tjänsten kan lista eller ta bort avtal baserat på e-postadressen till en begärande.

Acrobat Sign erbjuder ett webbprogram som tillåter att deltagare kan söka efter avtal och vid behov ta bort dem. Mer information finns i [Acrobat Sign - funktion: Ta bort användarinformation](https://helpx.adobe.com/sign/help/adobesign_gdpr_user_deletion.html).

Avtalsdata för adaptiva formulär som har konfigurerats att använda Forms Portal-åtgärden för att skicka sparas också i datalagret för formulärportalen. Information om hur du får åtkomst till och tar bort data från formulärportalens datalager finns i [Forms portal | Hantera användardata](/help/forms/using/forms-portal-handling-user-data.md).
