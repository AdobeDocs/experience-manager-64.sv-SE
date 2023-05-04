---
title: Starta och stoppa tjänster
seo-title: Starting and stopping services
description: Lär dig hur du startar och stoppar tjänster som är kopplade till AEM Forms-moduler samt programservern och databasen.
seo-description: Learn how to start and stop services associated with AEM Forms modules and the application server and database.
uuid: 8c831cb2-4165-4118-8a09-764cec4e5e05
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/managing_services
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: b93060bd-c6e1-40d2-8acd-ccafb8ed56da
exl-id: 6e0607d6-171c-4119-95a1-373b30fb63c1
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 0%

---

# Starta och stoppa tjänster {#starting-and-stopping-services}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Det finns två typer av tjänster som ingår i AEM:

* Tjänster som styr AEM och databas.
* Tjänster som styr AEM formulärmoduler

## Starta eller stoppa tjänster som är kopplade till AEM formulärmoduler {#start-or-stop-the-services-associated-with-aem-forms-modules}

AEM (t.ex. Forms, Rights Management, Output) fungerar som tjänster. Ibland kan du behöva stoppa eller starta tjänsterna för dessa AEM. Du måste till exempel stoppa och sedan starta om en AEM formulärtjänst när du har ändrat en inställning för tjänsten.

1. I administrationskonsolen klickar du **Tjänster** > **Program och tjänster** > **Tjänsthantering**.
1. Markera kryssrutan bredvid tjänsten som ska stoppas eller startas på sidan Tjänsthantering och klicka på Stopp eller Start.

## Starta eller stoppa tjänster för programservern och databasen {#start-or-stop-services-for-the-application-server-and-database}

En fullständig implementering av AEM innehåller en programserver och databastjänster:

* *`[application server]`* AEM formulär
* *`[database]`* AEM formulär

I Windows är dessa tjänster tillgängliga via **Administrativa verktyg** > **Panelen Tjänster**. Om du t.ex. har installerat AEM formulär på JBoss med körningsmetoden är följande tjänster tillgängliga på datorn:

* JBoss för Adobe Experience Manager-formulär
* MySQL för Adobe Experience Manager-formulär

Starta eller stoppa dessa tjänster genom att markera dem i listan på panelen Tjänster och sedan klicka på lämplig åtgärdsknapp på panelen.

I UNIX® eller Linux anger du följande text från en kommandorad, där *`[service name]`* är namnet på den tjänst du verifierar:

```as3
     ps -A | grep [service name]
```
