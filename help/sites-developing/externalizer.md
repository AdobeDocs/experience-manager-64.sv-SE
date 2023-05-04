---
title: Extern URL
seo-title: Externalizing URLs
description: Externalizer är en tjänst av typen OSGI som gör att du kan omvandla en resurssökväg programmatiskt till en extern och absolut URL
seo-description: The Externalizer is an OSGI service that allows you to programmatically transform a resource path into an external and absolute URL
uuid: ea887096-1a48-4bdb-bc5c-e4fe719e5632
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 53342acb-c1a5-443d-8727-cb27cc9d6845
exl-id: 123ef72b-f09b-47eb-9b5a-e0deb38799df
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '546'
ht-degree: 0%

---

# Extern URL{#externalizing-urls}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM **Externalizer** är en OSGI-tjänst som gör att du kan omforma en resurssökväg programmatiskt (t.ex. `/path/to/my/page`) till en extern och absolut URL (till exempel `https://www.mycompany.com/path/to/my/page`) genom att ange sökvägen som prefix med en förkonfigurerad DNS.

Eftersom en instans inte känner till sin externt synliga URL-adress om den körs bakom ett webblager, och eftersom en länk ibland måste skapas utanför det begärda omfånget, utgör den här tjänsten en central plats för att konfigurera dessa externa URL-adresser och skapa dem.

På den här sidan beskrivs hur du konfigurerar **Externalizer** och hur du använder den. Mer information finns i [Javadocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html).

## Konfigurera tjänsten Externalizer {#configuring-the-externalizer-service}

The **Externalizer** kan du centralt definiera flera domäner som kan användas för att programmässigt prefix för resurssökvägar. Varje domän identifieras med ett unikt namn som används för att programmässigt referera till domänen.

Definiera en domänmappning för **Externalizer** tjänst:

1. Navigera till konfigurationshanteraren via **verktyg** sedan **Webbkonsol** eller ange `https://<host>:<port>/system/console/configMgr.`
1. Klicka **Day CQ Link Externalizer** för att öppna konfigurationsdialogrutan.

   >[!NOTE]
   >
   >Den direkta länken till konfigurationen är `https://<host>:<port>/system/console/configMgr/com.day.cq.commons.impl.ExternalizerImpl`

   ![chlimage_1-44](assets/chlimage_1-44.png)

1. Definiera en domänmappning: en mappning består av ett unikt namn som kan användas i koden för att referera till domänen, ett blanksteg och domänen:

   `<unique-name> [scheme://]server[:port][/contextpath]`, där:

   * **system** är vanligtvis http eller https, men kan också vara ftp o.s.v.; använda https för att framtvinga https-länkar om det behövs; den kommer att användas om klientkoden inte åsidosätter schemat när en URL-adress begärs externt.
   * **server** är värdnamnet (kan vara ett domännamn eller en IP-adress).
   * **port** (valfritt) är portnumret.
   * **kontextbana** (valfritt) anges bara om AEM har installerats som ett webbprogram under en annan kontextsökväg.

   Till exempel: `production https://my.production.instance`

   Följande mappningsnamn är fördefinierade och måste alltid anges som AEM är beroende av dem:

   * **lokal** - den lokala instansen
   * **författare** - redigeringssystemets DNS
   * **publicera** - den offentliga webbplatsens DNS

   >[!NOTE]
   >
   >Med en anpassad konfiguration kan du lägga till en ny kategori, till exempel&quot;produktion&quot;,&quot;staging&quot; eller till och med externa icke-AEM system som&quot;my-internal-webservice&quot;. Den är användbar för att undvika hårdkodning av sådana URL:er på olika platser i ett projekts kodbas.

1. Klicka **Spara** för att spara ändringarna.

>[!NOTE]
>
>Adobe rekommenderar att du [lägg till konfigurationen i databasen](/help/sites-deploying/configuring-osgi.md#adding-a-new-configuration-to-the-repository).

## Använda tjänsten Externalizer {#using-the-externalizer-service}

I det här avsnittet visas några exempel på hur **Externalizer** kan användas.

**Så här hämtar du tjänsten Externalizer i en JSP:**

`Externalizer externalizer = resourceResolver.adaptTo(Externalizer.class);`

**Så här gör du en extern sökväg med domänen &#39;publish&#39;:**

`String myExternalizedUrl = externalizer.publishLink(resolver, "/my/page") + ".html";`

Anta domänmappningen `publish https://www.website.com`&quot;, myExternalizedUrl avslutas med värdet &quot; `https://www.website.com/contextpath/my/page.html`&quot;.

**Så här gör du en extern sökväg med domänen &#39;författare&#39;:**

`String myExternalizedUrl = externalizer.authorLink(resolver, "/my/page") + ".html";`

Anta domänmappningen `author https://author.website.com`&quot;, myExternalizedUrl avslutas med värdet &quot; `https://author.website.com/contextpath/my/page.html`&quot;.

**Så här externaliserar du en sökväg med domänen&quot;local&quot;:**

`String myExternalizedUrl = externalizer.externalLink(resolver, Externalizer.LOCAL, "/my/page") + ".html";`

Anta domänmappningen `local https://publish-3.internal`&quot;, myExternalizedUrl avslutas med värdet &quot; `https://publish-3.internal/contextpath/my/page.html`&quot;.

Du hittar fler exempel i [Javadocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html).
