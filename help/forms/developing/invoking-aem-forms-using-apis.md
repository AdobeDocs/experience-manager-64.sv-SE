---
title: Anropa AEM Forms med API:er
seo-title: Invoking AEM Forms using APIs
description: Adobe Experience Manager Forms är en J2EE-baserad företagsprogramvara som består av tjänster som fungerar i en delad infrastruktur. Lär dig hur du använder klientprogram för att anropa AEM Forms programmatiskt med ett Java API, webbtjänster, Remoting och REST API.
seo-description: Adobe Experience Manager Forms is J2EE-based enterprise software that consists of services that operate within a shared infrastructure. Learn how to use client applications to invoke AEM Forms programmatically using a Java API, web services, Remoting, and REST API.
uuid: d100e106-e508-4d3c-ba8c-b5fe13c9e2d6
contentOwner: admin
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: development-tools, coding
discoiquuid: 1825e12c-0306-4e0a-9643-47ce1ce82132
role: Developer
exl-id: 6b60209f-aced-4698-97f1-b1a7782eef46
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '340'
ht-degree: 0%

---

# Anropa AEM Forms med API:er {#invoking-aem-forms-using-apis}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Adobe Experience Manager Forms är en J2EE-baserad företagsprogramvara som består av tjänster som fungerar i en delad infrastruktur. Serviceåtgärder brukar förbruka eller producera dokument. Med AEM Forms kan man kombinera arbetsflöden för blanketter med elektroniska blanketter, dokumentsäkerhet och dokumentgenerering i en integrerad och sammanhängande uppsättning tjänster. Dessa tjänster kan nås inifrån och utanför brandväggen.

Klientprogram kan programmatiskt anropa AEM Forms-tjänster med ett Java-API, webbtjänster, Remoting och REST. Med administrationskonsolen kan du konfigurera en tjänst så att en slutpunkt visas som gör att AEM Forms-tjänster kan anropas via programmering. Som standard är de flesta tjänster förkonfigurerade för att visa slutpunkter för Remoting, Java och webbtjänster.

Dina affärskrav avgör vilken anropsmetod som ska användas. Med Java API kan du t.ex. integrera AEM Forms-funktioner i Java Enterprise-program som Java Entity och Message Beans. På samma sätt kan du integrera AEM Forms-funktionalitet i .NET-projekt (eller andra projekt som utvecklats med utvecklingsmiljöer som stöder webbtjänststandarder) med hjälp av webbtjänster.

Tjänsterna kräver en tjänstbehållare för att köras, ungefär som Enterprise JavaBeans™ (EJB) kräver en J2EE-behållare. AEM Forms innehåller endast en implementering av en tjänstbehållare. Tjänstbehållaren ansvarar för att hantera tjänstens livstid, inklusive distribuering, och ser till att alla begäranden skickas till rätt tjänst. Den hanterar också dokument som en tjänst förbrukar eller producerar.

>[!NOTE]
>
>Programmering med AEM innehåller ingen information om hur du anropar AEM Forms med Bevakade mappar eller e-post.
