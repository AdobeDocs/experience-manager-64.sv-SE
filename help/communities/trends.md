---
title: Aktivitetstrender
seo-title: Activity Trends
description: Lägga till en del av en lista över communityaktiviteter på en sida
seo-description: Adding a Community Activity List component to a page
uuid: 6a030340-0e69-432a-98f1-3effb2b97136
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 93a112fc-ef34-4281-89b8-a0f1b3d3aca9
exl-id: a2cb9738-98a5-4ea6-8d5a-a6c0aa04cd32
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 2%

---

# Aktivitetstrender {#activity-trends}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Introduktion {#introduction}

The `Community Activity List` -komponenten gör det möjligt att lägga till trendinformation om inlägg och vyer från medlemmar samt inlägg och vyer av innehåll.

Detta avsnitt i dokumentationen beskriver

* Lägga till `Community Activity List` till en [communitywebbplats](overview.md#community-sites)

* Konfigurationsinställningar för `Community Activity List` komponent

## Krav {#requirement}

Data för `Community Activity List` är endast tillgängligt när Adobe Analytics har licens och konfigurerats för communitywebbplatsen.

Se [Analyskonfiguration för communityfunktioner](analytics.md).

## Lägga till en lista med communityaktiviteter på en sida {#adding-a-community-activity-list-to-a-page}

Lägga till en `Community Activity List` till en sida i redigeringsläge, leta reda på komponenten `Communities / Community Activity List` och dra den till rätt plats på en sida.

Nödvändig information finns på [Grunderna för communitykomponenter](basics.md).

När komponenten placeras på en sida i en community-webbplats är det så här den visas:

![chlimage_1-227](assets/chlimage_1-227.png)

## Konfigurerar lista över communityaktiviteter  {#configuring-community-activity-list}

Markera den monterade `Community Activity List` -komponenten som ska få åtkomst till och markera `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-228](assets/chlimage_1-228.png)

Under **[!UICONTROL Comments]** anger du om och hur kommentarer för överförda filer ska visas:

![chlimage_1-229](assets/chlimage_1-229.png)

* **[!UICONTROL Type]**

   Ange om data ska visas för communitymedlemmar eller användargenererat innehåll (UGC).

   Välj  från
   * `Members`
   * `Content`

   Standard är `Members`.

* **[!UICONTROL Display title]**

   En beskrivande rubrik som ska visas ovanför data, till exempel `Trending Content`.

   Standard är ingen titel.

* **[!UICONTROL Display count]**

   Antalet objekt som ska listas.

   Standardvärdet är 10.

* **[!UICONTROL Activity type]**

   Välj en av
   * `Views`(sidbesök)
   * `Posts`(skapa UGC)
   * `Follows`
   * `Likes`

   Standardvärdet är Vyer.

* **[!UICONTROL Time period]**

   Välj en av
   * `Last 24 hours`
   * `Last 7 days`
   * `Last 30 days`
   * `Last 90 days`
   * `This year (since Jan 1st)`
   * `Total`

   Standard är `Total`.

* **[!UICONTROL Context path]**

   Gör det möjligt att omfång aktiviteten till en delmängd av platsen, t.ex. en viss blogg.

   Standard är hela communitywebbplatsen.

* **[!UICONTROL Member count aggregation]**

   När alternativet är avmarkerat (inaktiverat) räknas endast inlägg på den översta nivån. Om kontexten till exempel är rotsidan (standardvärdet), kan du `Activity Type`av `Posts`kommer aldrig att visa någon aktivitet eftersom det inte går att publicera innehåll på rotsidan. När du markerar det här alternativet inkluderas antalet på alla underordnade sidor.

   Standard är markerat.

## Exempelsida med 4 komponenter {#example-page-with-components}

**De vanligaste besökarna** config: Typ = Medlemmar, aktivitetstyp = Vyer

**Främsta bidragsgivare** config: Typ = Medlemmar, aktivitetstyp = Bokföring

**Övre innehåll** config: Typ = Innehåll, aktivitetstyp = Vyer,

**Trendinnehåll** config: Typ = innehåll, aktivitetstyp = inlägg

![chlimage_1-230](assets/chlimage_1-230.png)
