---
title: Blog Essentials
seo-title: Blog Essentials
description: Översikt över bloggar
seo-description: Blog overview
uuid: ce0885de-6276-47a2-8f6c-358f0beb2b89
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: de8d0e6d-827b-45fe-a538-d3fe1dec8427
exl-id: 8cff0b7b-c120-462f-8fce-13822073eabb
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 0%

---

# Blog Essentials {#blog-essentials}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Från och med AEM 6.1 Communities är en blogg en community-aktivitet. Bloggartiklar publiceras nu från publiceringsmiljön, där bloggartiklar tidigare bara kunde skapas i författarmiljön och publiceras.

Bloggartiklar kan nu skapas av alla communitymedlemmar, såvida de inte är begränsade till behöriga medlemmar.

Den här sidan innehåller viktig information om hur du arbetar med bloggfunktionen.

>[!NOTE]
>
>Den underliggande infrastrukturen för bloggfunktionen är journalfunktionen.

## Grundläggande för klientsidan {#essentials-for-client-side}

Bloggfunktionen består av två huvudkomponenter som är tillgängliga genom att lägga till [Bloggfunktion](functions.md#blog-function) eller genom att lägga till komponenterna på en sida i redigeringsläge.

### Blogg {#blog}

<table> 
 <tbody>
  <tr>
   <td> <strong>resourceType</strong></td> 
   <td>social/journal/components/hbs/journal</td> 
  </tr>
  <tr>
   <td> <a href="scf.md#add-or-include-a-communities-component"><strong>oklanderlig</strong></a></td> 
   <td>Nej</td> 
  </tr>
  <tr>
   <td> <a href="clientlibs.md"><strong>klientlibs</strong></a></td> 
   <td>cq.ckeditor<br /> cq.social.hbs.röstning<br /> cq.social.hbs.journal</td> 
  </tr>
  <tr>
   <td> <strong>mallar</strong></td> 
   <td> /libs/social/journal/components/hbs/journal/journal.hbs<br /> /libs/social/journal/components/hbs/entry_topic/list-item.hbs</td> 
  </tr>
  <tr>
   <td> <strong>css</strong></td> 
   <td> /libs/social/journal/components/hbs/journal/clientlibs/journal.css</td> 
  </tr>
  <tr>
   <td><strong> egenskaper</strong></td> 
   <td>se <a href="blog-feature.md">Bloggfunktion</a></td> 
  </tr>
 </tbody>
</table>

### Blogg, marginallist {#blog-sidebar}

| **resourceType** | social/journal/components/hbs/sidebar |
|---|---|
| [**oklanderlig**](scf.md#add-or-include-a-communities-component) | Nej |
| [**klientlibs**](clientlibs.md) | cq.social.hbs.journal_sidebar |
| **mallar** | /libs/social/journal/components/hbs/sidebar/sidebar.hbs |
| **css** | /libs/social/journal/components/hbs/sidebar/clientlibs/sidebar.css |
| **egenskaper** | se [Bloggfunktion](blog-feature.md) |

* [Anpassningar på klientsidan](client-customize.md)

## Grundläggande för serversidan {#essentials-for-server-side}

* [Blogg-API](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/journal/client/api/package-summary.html)

* [Bloggslutpunkter](https://helpx.adobe.com/experience-manager/6-4/sites/developing/using/reference-materials/javadoc/com/adobe/cq/social/journal/client/endpoints/package-summary.html)

* [Anpassningar på serversidan](server-customize.md)

### Bloggfunktion {#blog-function}

En community-webbplatsstruktur som innehåller [Funktionen Bog](functions.md#blog-function) har konfigurerats `Blog` och `Blog Sidebar` -komponenter. Funktionen Blog har stöd för att identifiera en [privilegierad medlemsanvändargrupp](users.md#privileged-members-group).

### Åtkomst till blogginlägg (UGC) {#accessing-blog-entries-ugc}

UGC bör modereras med någon av standardmetoderna för moderering.\
Se [Modererar användargenererat innehåll](moderate-ugc.md).

Från och med AEM 6.1 Communities används [gemensam lagringsplats](working-with-srp.md) för UGC omfattar programmatisk åtkomst till UGC oavsett vilket lagringsalternativ som valts (till exempel ASRP, MSRP eller JSRP).

**Platsen och formatet för användargenererat innehåll i databasen kan ändras utan förvarning**.

Se:

* [Översikt över lagringsresursprovider](srp.md) - introduktion och databasanvändning - översikt
* [SRP och UGC Essentials](srp-and-ugc.md) - SRP-verktygsmetoder och exempel
* [Åtkomst till UGC med SRP](accessing-ugc-with-srp.md) - riktlinjer för kodning
* [Omfaktorisering för SocialUtils](socialutils.md) - mappning av borttagna verktygsmetoder till aktuella SRP-verktygsmetoder

## Primär utgivare {#primary-publisher}

När distributionen är en publiceringsgrupp är det nödvändigt att identifiera en primär utgivare som söker efter artiklar som är schemalagda att publiceras.

Se [Primär utgivare](deploy-communities.md#primary-publisher) för mer information.

## Tillåta multimedia {#allowing-rich-media}

Den AEM plattformen blockerar länkar från andra webbplatser för att förhindra XSS-attacker enligt beskrivningen i

* [Protect mot XSS (Cross-Site Scripting)](../../help/sites-developing/security.md#protect-against-cross-site-scripting-xss)

Från och med AEM 6.2 inkluderas de ändringar som tidigare krävdes för att göras manuellt i standardkonfigurationsfilen för AntiSamy.

Multimedia är inbäddade i en bloggartikel genom att välja `Embed Media from External Sites` ikon:  ![chlimage_1-471](assets/chlimage_1-471.png)
