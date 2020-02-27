---
title: Extern URL
seo-title: Extern URL
description: Externalizer är en tjänst av typen OSGI som gör att du kan omvandla en resurssökväg programmatiskt till en extern och absolut URL
seo-description: Externalizer är en tjänst av typen OSGI som gör att du kan omvandla en resurssökväg programmatiskt till en extern och absolut URL
uuid: ea887096-1a48-4bdb-bc5c-e4fe719e5632
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: platform
content-type: reference
discoiquuid: 53342acb-c1a5-443d-8727-cb27cc9d6845
translation-type: tm+mt
source-git-commit: 8e2bd579e4c5edaaf86be36bd9d81dfffa13a573

---


# Extern URL{#externalizing-urls}

I AEM är **Externalizer** en OSGI-tjänst som du kan använda för att programmässigt omvandla en resurssökväg (t.ex. till `/path/to/my/page`en extern och absolut URL (till exempel `https://www.mycompany.com/path/to/my/page`) genom att prefix-sökvägen med en förkonfigurerad DNS.

Eftersom en instans inte känner till sin externt synliga URL-adress om den körs bakom ett webblager, och eftersom en länk ibland måste skapas utanför det begärda omfånget, utgör den här tjänsten en central plats för att konfigurera de externa URL-adresserna och skapa dem.

På den här sidan beskrivs hur du konfigurerar tjänsten **Externalizer** och hur du använder den. Mer information finns i [Javadocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html).

## Konfigurera tjänsten Externalizer {#configuring-the-externalizer-service}

Med **tjänsten Externalizer** kan du centralt definiera flera domäner som kan användas för att programmässigt prefix för resurssökvägar. Varje domän identifieras med ett unikt namn som används för att programmässigt referera till domänen.

Så här definierar du en domänmappning för tjänsten **Externalizer** :

1. Navigera till konfigurationshanteraren via **Verktyg**, **Webbkonsol** eller ange `https://<host>:<port>/system/console/configMgr.`
1. Klicka på **Day CQ Link Externalizer** för att öppna konfigurationsdialogrutan.

   >[!NOTE]
   >
   >Den direkta länken till konfigurationen är `https://<host>:<port>/system/console/configMgr/com.day.cq.commons.impl.ExternalizerImpl`

   ![chlimage_1-44](assets/chlimage_1-44.png)

1. Definiera en domänmappning: en mappning består av ett unikt namn som kan användas i koden för att referera till domänen, ett blanksteg och domänen:

   `<unique-name> [scheme://]server[:port][/contextpath]`, där:

   * **Schemat** är vanligtvis http eller https, men kan också vara ftp o.s.v.; använda https för att framtvinga https-länkar om det behövs;den kommer att användas om klientkoden inte åsidosätter schemat när den frågar efter en URL-adress.
   * **server** är värdnamnet (kan vara ett domännamn eller en IP-adress).
   * **port** (valfritt) är portnumret.
   * **kontextsökväg** (valfritt) anges bara om AEM är installerat som en webbapp under en annan kontextsökväg.
   Exempel: `production https://my.production.instance`

   Följande mappningsnamn är fördefinierade och måste alltid anges som AEM är beroende av dem:

   * **local** - den lokala instansen
   * **författare** - redigeringssystemets DNS
   * **publicera** - den offentliga webbplatsens DNS
   >[!NOTE]
   >
   >Med en anpassad konfiguration kan du lägga till en ny kategori, till exempel&quot;produktion&quot;,&quot;staging&quot; eller till och med externa icke-AEM-system som&quot;my-internal-webservice&quot;, och det är användbart för att undvika hårdkodning av sådana URL:er på olika platser i ett projekts kodbas.

1. Klicka på **Spara** för att spara ändringarna.

>[!NOTE]
>
>Adobe rekommenderar att du [lägger till konfigurationen i databasen](/help/sites-deploying/configuring-osgi.md#adding-a-new-configuration-to-the-repository).

## Använda tjänsten Externalizer {#using-the-externalizer-service}

I det här avsnittet visas några exempel på hur **tjänsten Externalizer** kan användas.

**Så här hämtar du tjänsten Externalizer i en JSP:**

`Externalizer externalizer = resourceResolver.adaptTo(Externalizer.class);`

**Så här gör du en extern sökväg med domänen &#39;publish&#39;:**

`String myExternalizedUrl = externalizer.publishLink(resolver, "/my/page") + ".html";`

Om domänmappningen &quot; `publish https://www.website.com`&quot; antas avslutas myExternalizedUrl med värdet &quot; `https://www.website.com/contextpath/my/page.html`&quot;.

**Så här gör du en extern sökväg med domänen &#39;författare&#39;:**

`String myExternalizedUrl = externalizer.authorLink(resolver, "/my/page") + ".html";`

Om domänmappningen &quot; `author https://author.website.com`&quot; antas avslutas myExternalizedUrl med värdet &quot; `https://author.website.com/contextpath/my/page.html`&quot;.

**Så här externaliserar du en sökväg med domänen&quot;local&quot;:**

`String myExternalizedUrl = externalizer.externalLink(resolver, Externalizer.LOCAL, "/my/page") + ".html";`

Om domänmappningen &quot; `local https://publish-3.internal`&quot; antas avslutas myExternalizedUrl med värdet &quot; `https://publish-3.internal/contextpath/my/page.html`&quot;.

Fler exempel finns i [Javadocs](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/day/cq/commons/Externalizer.html).
