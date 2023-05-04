---
title: Innehållsdispositionsfilter
seo-title: Content Disposition Filter
description: Lär dig hur du använder filtret för innehållsdisposition för att förhindra XSS-attacker.
seo-description: Learn how to use the Content Disposition Filter to prevent XSS attacks.
uuid: 145a88e0-9fa8-42db-b189-eda507c33049
contentOwner: trushton
products: SG_EXPERIENCEMANAGER/6.4/SITES
content-type: reference
topic-tags: Security
discoiquuid: badfaa18-472e-4777-a7dc-9c28441b38b7
exl-id: bb022f6b-938b-4421-8860-4c22aecf5b85
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '275'
ht-degree: 0%

---

# Innehållsdispositionsfilter {#content-disposition-filter}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Dispositionsfiltret är en säkerhetsfunktion mot XSS-attacker mot SVG-filer.

När filtret har installerats blockeras åtkomsten till alla resurser. Du kan till exempel inte visa PDF online. I det här avsnittet beskrivs hur du konfigurerar filtret efter dina behov.

## Konfigurera filtret för innehållsdisposition {#configure-content-disposition-filter}

Du kan visa [Apache Sling Content Disposition Filter i GitHub.](https://github.com/apache/sling-org-apache-sling-security/blob/master/src/main/java/org/apache/sling/security/impl/ContentDispositionFilterConfiguration.java)

Alternativen för Innehållsdispositionsfilter innehåller följande funktioner:

* **Sökvägar för innehållsdisposition:** en lista med sökvägar där filtret ska användas följt av en lista med MIME-typer som ska uteslutas på den sökvägen. Sökvägen måste vara en absolut sökväg och kan innehålla ett jokertecken (`*`) i slutet så att alla resurssökvägar matchar det angivna sökvägsprefixet. Till exempel: `/content/*:image/jpeg,image/svg+xml` kommer att tillämpa filtret på alla noder i `/content` förutom jpg- och svg-bilder

* **Uteslutna resurssökvägar:** En lista över uteslutna resurser. Varje resurssökväg måste anges som en absolut och fullständig sökväg. Prefixmatchning/jokertecken stöds inte.

* **Aktivera för alla resurssökvägar:** Den här flaggan anger om det här filtret ska aktiveras för alla sökvägar, förutom för de uteslutna sökvägarna som definieras av Uteslutna resurssökvägar. Om du anger värdet true ignoreras innehållets dispositionsbanor. Oberoende av konfigurationen finns bara resurssökvägar som innehåller en egenskap med namnet `jcr:data` eller
   `jcr:content jcr:data`.
