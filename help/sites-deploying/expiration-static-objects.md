---
title: Förfallotid för statiska objekt
seo-title: Expiration of Static Objects
description: Lär dig hur du konfigurerar AEM så att statiska objekt inte förfaller (under en rimlig tidsperiod).
seo-description: Learn how to configure AEM so that static objects do not expire (for a reasonable period of time).
uuid: ee019a3d-4133-4d40-98ec-e0914b751fb3
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: configuring
content-type: reference
discoiquuid: 73f37b3c-5dbe-4132-bb60-daa8de871884
feature: Configuring
exl-id: 3551d25c-c852-4f59-84fe-5e62f57ae63f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 0%

---

# Förfallotid för statiska objekt{#expiration-of-static-objects}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Statiska objekt (till exempel ikoner) ändras inte. Därför bör systemet konfigureras så att det inte upphör att gälla (under en rimlig tidsperiod) och på så sätt minskar onödig trafik.

Detta har följande effekt:

* Avlastar begäranden från serverinfrastrukturen.
* Förbättrar sidinläsningens prestanda när webbläsaren cachelagrar objekt i webbläsarens cache.

Förfallodatum anges av HTTP-standarden med avseende på &quot;förfallodatum&quot; för filer (se t.ex. kapitel 14.21 i [RFC 2616](https://www.ietf.org/rfc/rfc2616.txt) &quot; Hypertext Transfer Protocol - HTTP 1.1&quot;). I den här standarden används rubriken för att tillåta klienter att cachelagra objekt tills de betraktas som inaktuella. sådana objekt cachelagras under den angivna tiden utan att någon statuskontroll görs på den ursprungliga servern.

>[!NOTE]
>
>Den här konfigurationen är helt skild från (och fungerar inte för) Dispatcher.
>
>Syftet med Dispatcher är att cachelagra data framför AEM.

Alla filer som inte är dynamiska och som inte ändras över tid kan och bör cachas. Konfigurationen för Apache HTTPD-servern kan se ut som något av följande, beroende på miljön:

>[!CAUTION]
>
>Du måste vara försiktig när du definierar den tidsperiod under vilken ett objekt anses vara uppdaterat. Som det finns *ingen kontroll förrän den angivna tidsperioden har gått ut* kan klienten presentera gammalt innehåll från cachen.

1. **För en Author-instans:**

   ```xml
   LoadModule expires_module modules/mod_expires.so
   <Location /libs>
     ExpiresByType text/css "access plus 1 month"
     ExpiresByType text/javascript "access plus 1 month"
     ExpiresByType image/png "access plus 1 month"
     ExpiresByType image/gif "access plus 1 month"
   </Location>
   ```

   Detta gör att det mellanliggande cacheminnet (t.ex. webbläsarens cacheminne) kan lagra CSS-, Javascript-, PNG- och GIF-filer i upp till en månad tills de upphör att gälla. Det innebär att de inte behöver begäras från AEM eller webbservern, men de kan finnas kvar i webbläsarens cache.

   Andra delar av webbplatsen bör inte cachas i en författarinstans eftersom de kan ändras när som helst.

1. **För en Publish-instans:**

   ```xml
   LoadModule expires_module modules/mod_expires.so
   <Location /content>
     ExpiresByType text/css "access plus 1 day"
     ExpiresByType text/javascript "access plus 1 day"
     ExpiresByType image/png "access plus 1 day"
     ExpiresByType image/gif "access plus 1 day"
   </Location>
   <Location /etc/designs>
     ExpiresByType text/css "access plus 1 day"
     ExpiresByType text/javascript "access plus 1 day"
     ExpiresByType image/png "access plus 1 day"
     ExpiresByType image/gif "access plus 1 day"
   </Location>
   ```

   Detta gör att det mellanliggande cacheminnet (t.ex. webbläsarens cacheminne) kan lagra CSS-, Javascript-, PNG- och GIF-filer i upp till en dag i klientcachen. I det här exemplet visas globala inställningar för allt nedan `/content` och `/etc/designs`bör du göra det mer granulärt.

   Beroende på hur ofta webbplatsen uppdateras kan du även cachelagra HTML-sidor. En rimlig tidsperiod är 1 timme:

   ```xml
   <Location /content>
     ExpiresByType text/html "access plus 1 hour"
   </Location>
   ```

När du har konfigurerat statiska objekt kan du skanna `request.log`, när du markerar sidor som innehåller sådana objekt, för att bekräfta att inga (onödiga) begäranden görs för statiska objekt.
