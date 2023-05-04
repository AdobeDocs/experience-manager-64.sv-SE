---
title: Gränser för medlemsbidrag
seo-title: Member Contribution Limits
description: Med funktionen för bidragsgränser kan du begränsa vilka bidrag som ska skyddas mot skräppost
seo-description: Contribution limits feature lets you limit the contributions to protect against spam
uuid: 99b2a855-3f0d-41a0-9572-517a7f29af9f
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: d855aac2-f34d-402f-9dc3-c7ad494b45f2
role: Admin
exl-id: fc7ce4d0-2051-4a67-a0d6-baf615e09ca4
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '457'
ht-degree: 0%

---

# Gränser för medlemsbidrag {#member-contribution-limits}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Funktionen för bidragsbegränsning ger möjlighet att begränsa bidrag från communitymedlemmar som ett sätt att skydda sig mot skräppost.

När en medlem är begränsad kommer alla inlägg som överskrider det tillåtna antalet bidrag att resultera i en varning om att gränsen har överskridits och att inlägget avvisas. Community-medlemmen kan sedan gå till communitymeddelandecentret och kontakta en community-ansvarig som kan ta bort begränsningarna om det är lämpligt.

Bidragsgränser kan aktiveras individuellt från [Medlemskonsol](members.md) och/eller konfigureras att aktiveras automatiskt när besökarna blir nya medlemmar.

Med hjälp av medlemskonsolen kan bidragsgränser tas bort proaktivt för en medlem av en community-chef när som helst, eller tas bort reaktivt när en medlem skickar ett meddelande till en community-administratör som gör en sådan begäran.

## Konfiguration av AEM Communities User Generated Content Contribution Limits {#aem-communities-user-generated-content-contribution-limits-configuration}

Den här OSGi-konfigurationen

* Definierar karaktärerna för bidragsgränserna (antal tjänster inom en tidsperiod).
* Identifierar vem medlemmen kan meddela när gränsen har nåtts
* Identifierar domäner som aldrig behöver begränsas

Så här når du OSGi-konfigurationen:

* På den primära utgivaren
* Logga in med administratörsbehörighet
* Öppna [Webbkonsol](../../help/sites-deploying/configuring-osgi.md)

   * Till exempel: [http://localhost:4503/system/console/configMgr](http://localhost:4503/system/console/configMgr)

* Sök `AEM Communities User Generated Content Contribution Limits Configuration`
* Markera redigeringsikonen

![chlimage_1-127](assets/chlimage_1-127.png)

* **[!UICONTROL Automatically Apply UGC Contribution Limits]**

   Om det här alternativet är markerat anger automatiskt bidragsgränser för användare när de registrerar sig som community-medlemmar. Detta återspeglas i communitymedlemmens profil och kan aktiveras/inaktiveras från [medlemskonsol](members.md). Nya medlemmar med en e-postadress från tillåtelselista i domäner begränsas aldrig.

   Standard är avmarkerat.

* **[!UICONTROL UGC Limit]**

   Högsta antal bidrag.

   Standard är 10 inlägg.

* **[!UICONTROL UGC Limit Frequency]**

   Den tidsperiod som begränsar UGC-gränsen.

   Standardvärdet är 60 minuter.

* **[!UICONTROL Domains]**

   En lista med tillåtelselista i en eller flera e-postdomäner. Markera +-ikonen om du vill göra ytterligare inmatningar.

   Användare med e-postadresser tillåtelselista i domäner påverkas inte när UGC-bidragsgränser tillämpas automatiskt. Exempel: om domän `mycompany.com` läggs till i listan över domäner och sedan en medlem med e-postadress `me@mycompany.com` begränsas aldrig från publicering.

   Standard är en tom tillåtelselista.

* **[!UICONTROL Messaging Recipients]**

   Lista över ett eller flera auktoriserbara ID:n för medlemmar som kan ändra bidragsgränserna för medlemmar. Markera +-ikonen om du vill göra ytterligare inmatningar.

   Medlemmar får endast nå ut till angivna medlemmar när deras gräns har nåtts.

   Standardvärdet är inga meddelandemottagare.

Obs! Standardkonfigurationen resulterar i högst 10 inlägg inom en timme.
