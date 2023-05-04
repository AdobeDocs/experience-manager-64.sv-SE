---
title: Länka viktiga
seo-title: Liking Essentials
description: Länka komponentöversikt
seo-description: Liking component overview
uuid: 89f16859-c901-4090-8e16-363b95c508de
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: f176c42b-b16b-42c9-af22-4b6421de5a90
pagetitle: Liking Essentials
exl-id: 509d1fb4-a88d-4438-a618-ba063adb6fb9
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '326'
ht-degree: 0%

---

# Länka viktiga {#liking-essentials}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Den länkade komponenten, en [tally](tally.md) underklass, är ett användbart verktyg som gör att medlemmar kan uttrycka en positiv åsikt om en viss del av innehållet genom att helt enkelt välja hjärtikonen.

Det är tillåtet att placera flera förekomster av en likartad komponent på samma sida. varje instans måste konfigureras med en unik `tally name` -egenskap.

Anonym publicering av en gilla-markering stöds inte. Besökare på webbplatsen måste registrera sig och logga in för att kunna delta. Den inloggade besökaren (medlemmen) kan när som helst växla som på och av.

## Grundläggande för klientsidan {#essentials-for-client-side}

<table> 
 <tbody> 
  <tr> 
   <td> <strong>resourceType</strong></td> 
   <td>social/tally/components/hbs/like</td> 
  </tr> 
  <tr> 
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>oklanderlig</strong></a></td> 
   <td>Ja - egenskaper kan redigeras i <i>design </i>läge</td> 
  </tr> 
  <tr> 
   <td> <a href="client-customize.md#clientlibs-for-scf"><strong>klientlibs</strong></a></td> 
   <td> cq.social.hbs.liking</td> 
  </tr> 
  <tr> 
   <td> <strong>mallar</strong></td> 
   <td><p> /libs/social/tally/components/hbs/liking/liking.hbs<br /> /libs/social/tally/components/hbs/liking/activity-icon.hbs<br /> /libs/social/tally/components/hbs/liking/activity-title.hbs</p> </td> 
  </tr> 
  <tr> 
   <td><strong>CSS</strong></td> 
   <td> /libs/social/tally/components/hbs/liking/clientlibs/likingcomponent.css</td> 
  </tr> 
  <tr> 
   <td><strong>egenskaper</strong></td> 
   <td><p>Se <a href="liking.md">Använda Länk</a></p> </td> 
  </tr> 
 </tbody> 
</table>

* [Anpassningar på klientsidan](client-customize.md)

## Grundläggande för serversidan {#essentials-for-server-side}

* [Tally API:er](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/api/package-summary.html)

* [Slutpunkter](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/tally/client/endpoints/package-summary.html)

* [Anpassningar på serversidan](server-customize.md)

### Åtkomst till bokförd röstning (UGC) {#accessing-posted-voting-ugc}

UGC bör modereras med någon av standardmetoderna för moderering.\
Se [Modererar användargenererat innehåll](moderate-ugc.md).

Från och med AEM 6.1 Communities används [gemensam lagringsplats](working-with-srp.md) för UGC omfattar programmatisk åtkomst till UGC oavsett vilket lagringsalternativ som valts (till exempel ASRP, MSRP eller JSRP).

**Platsen och formatet för användargenererat innehåll i databasen kan ändras utan förvarning**.

Se:

* [Översikt över lagringsresursprovider](srp.md) - introduktion och databasanvändning - översikt
* [SRP och UGC Essentials](srp-and-ugc.md) - SRP-verktygsmetoder och exempel
* [Åtkomst till UGC med SRP](accessing-ugc-with-srp.md) - riktlinjer för kodning
* [Omfaktorisering för SocialUtils](socialutils.md) - mappning av borttagna verktygsmetoder till aktuella SRP-verktygsmetoder
