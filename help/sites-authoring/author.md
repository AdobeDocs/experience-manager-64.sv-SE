---
title: Begreppet redigering
seo-title: Begreppet redigering
description: Begrepp att skapa i AEM
seo-description: Begrepp att skapa i AEM
uuid: 824c8b91-07c7-471b-b3aa-5a73d6d48414
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: 72ee013a-7a60-41ee-9421-2846e4c6bc68
translation-type: tm+mt
source-git-commit: b009abd8b3d55bd7dd030d7b4828aec72d9fa9ff
workflow-type: tm+mt
source-wordcount: '555'
ht-degree: 0%

---


# Koncept för redigering och publicering{#authoring}

AEM har två miljöer:

* Författare
* Publicera

Dessa interagerar så att ni kan göra innehåll tillgängligt på er webbplats så att besökarna kan läsa det.

I redigeringsmiljön finns mekanismer för att skapa, uppdatera och granska innehållet innan det publiceras:

* En författare skapar och granskar innehållet (detta kan vara av flera typer); till exempel sidor, resurser, publikationer osv.)
* som någon gång kommer att publiceras på er webbplats.

![chlimage_1-289](assets/chlimage_1-289.png)

I redigeringsmiljön är funktionaliteten för AEM tillgänglig via två användargränssnitt. För publiceringsmiljön utformar du hela det gränssnitt som är tillgängligt för användarna.

## Författarmiljö {#author-environment}

Författaren arbetar i **[författarmiljön](/help/sites-authoring/home.md)**. Detta ger ett användarvänligt gränssnitt (grafiskt användargränssnitt (GUI eller UI)) för att skapa innehållet. Det ligger vanligtvis bakom ett företags brandvägg som ger fullständigt skydd och som kräver att författaren loggar in med ett konto som tilldelats rätt åtkomstbehörighet.

>[!NOTE]
>
>Ditt konto behöver rätt behörighet för att skapa, redigera eller publicera innehåll.

Beroende på hur din instans och dina personliga åtkomsträttigheter är konfigurerade kan du utföra många åtgärder på ditt innehåll, bland annat:

* generera nytt innehåll, eller redigera befintligt innehåll, på en sida
* använda fördefinierade mallar för att skapa nya innehållssidor
* skapa, redigera och hantera dina resurser och samlingar
* skapa, redigera och hantera publikationer
* utveckla era kampanjer och relaterade resurser
* utveckla och hantera communitysajter
* flytta, kopiera eller ta bort innehållssidor, resurser osv.
* publicera (eller avpublicera) sidor, resurser osv

Det finns dessutom administrativa uppgifter som hjälper dig att hantera ditt innehåll:

* arbetsflöden som styr hur ändringar hanteras, till exempel. genomföra en granskning före publicering
* projekt som koordinerar enskilda uppgifter

>[!NOTE]
>
>AEM [administreras](/help/sites-administering/home.md) (för de flesta uppgifter) från författarmiljön.

## Publiceringsmiljö {#publish-environment}

När den är klar publiceras AEM innehåll till **publiceringsmiljön**. Här blir webbplatsens sidor tillgängliga för den avsedda publiken i enlighet med det gränssnitt som har utformats.

Normalt ligger publiceringsmiljön innanför den demilitariserade zonen. med andra ord, tillgängliga för Internet, men inte längre till fullständigt skydd för det interna nätverket.

När den AEM webbplatsen är en [community-webbplats](/help/communities/overview.md), eller innehåller [webbkomponenterna](/help/communities/author-communities.md), kan besökare (medlemmar) som är inloggade interagera med webbgruppsfunktioner. De kan till exempel publicera på ett forum, publicera en kommentar eller följa andra medlemmar. Medlemmar kan ges behörighet att utföra åtgärder som normalt bara är avsedda för författarmiljön, t.ex. skapa nya sidor (communitygrupper), bloggartiklar och moderata inlägg från andra medlemmar.

>[!NOTE]
>
>Tyvärr förekommer ibland en överlappning i den terminologi som används. Detta kan inträffa med:
>
>* **Publicera/avpublicera**
   >  Detta är de primära villkoren för de åtgärder som gör innehållet tillgängligt för allmänheten i publiceringsmiljön (eller inte).
   >
   >
* **Aktivera/inaktivera**
   >  Dessa termer är synonyma med publicera/avpublicera. De är vanligare i det klassiska användargränssnittet.
   >
   >
* **Replikering/replikering**
   >  Detta är de tekniska termer som används för att ange dataförflyttning (t.ex. sidinnehåll, filer, kod, användarkommentarer) från en miljö till en annan. t.ex. vid publicering, eller vid omvänd replikering av användarkommentarer.
>



## Dispatcher {#dispatcher}

**[dispatcher](https://helpx.adobe.com/experience-manager/dispatcher/user-guide.html)** implementerar belastningsutjämning och cachning för att optimera prestanda för besökare på webbplatsen.
