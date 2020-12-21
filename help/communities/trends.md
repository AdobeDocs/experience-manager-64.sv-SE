---
title: Aktivitetstrender
seo-title: Aktivitetstrender
description: Lägga till en del av en lista över communityaktiviteter på en sida
seo-description: Lägga till en del av en lista över communityaktiviteter på en sida
uuid: 6a030340-0e69-432a-98f1-3effb2b97136
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: authoring
content-type: reference
discoiquuid: 93a112fc-ef34-4281-89b8-a0f1b3d3aca9
translation-type: tm+mt
source-git-commit: 5ddbcb2addff2d6e3a3e9d7e100a6d9ba89fdd60
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 2%

---


# Aktivitetstrender {#activity-trends}

## Introduktion {#introduction}

Komponenten `Community Activity List` gör det möjligt att lägga till trendinformation om inlägg och vyer från medlemmar samt inlägg och vyer av innehåll.

Detta avsnitt i dokumentationen beskriver

* Lägga till komponenten `Community Activity List` i en [community-webbplats](overview.md#community-sites)

* Konfigurationsinställningar för komponenten `Community Activity List`

## Krav {#requirement}

Data för `Community Activity List` är bara tillgängliga när Adobe Analytics är licensierat och konfigurerat för communitywebbplatsen.

Se [Analyskonfiguration för communityfunktioner](analytics.md).

## Lägga till en lista med communityaktiviteter på en sida {#adding-a-community-activity-list-to-a-page}

Om du vill lägga till en `Community Activity List`-komponent på en sida i redigeringsläge letar du reda på komponenten `Communities / Community Activity List` och drar den till rätt plats på en sida.

Mer information finns på [Grunderna för communitykomponenter](basics.md).

När komponenten placeras på en sida i en community-webbplats är det så här den visas:

![chlimage_1-227](assets/chlimage_1-227.png)

## Konfigurerar community-aktivitetslista {#configuring-community-activity-list}

Markera den monterade `Community Activity List`-komponenten som ska öppnas och välj ikonen `Configure` som öppnar redigeringsdialogrutan.

![chlimage_1-228](assets/chlimage_1-228.png)

Under fliken **[!UICONTROL Comments]** anger du om och hur kommentarer för överförda filer ska visas:

![chlimage_1-229](assets/chlimage_1-229.png)

* **[!UICONTROL Type]**

   Ange om data ska visas för communitymedlemmar eller användargenererat innehåll (UGC).

   Välj  från
   * `Members`
   * `Content`

   Standardvärdet är `Members`.

* **[!UICONTROL Display title]**

   En beskrivande titel som ska visas ovanför data, till exempel `Trending Content`.

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

   Standardvärdet är `Total`.

* **[!UICONTROL Context path]**

   Gör det möjligt att omfång aktiviteten till en delmängd av platsen, t.ex. en viss blogg.

   Standard är hela communitywebbplatsen.

* **[!UICONTROL Member count aggregation]**

   När alternativet är avmarkerat (inaktiverat) räknas endast inlägg på den översta nivån. Om kontexten till exempel är rotsidan (standardvärdet) kommer en `Activity Type`av `Posts`aldrig att visa någon aktivitet eftersom det inte går att publicera innehåll på rotsidan. När du markerar det här alternativet inkluderas antalet på alla underordnade sidor.

   Standard är markerat.

## Exempelsida med 4 komponenter {#example-page-with-components}

**Konfiguration** för de vanligaste besökarna: Typ = Medlemmar, aktivitetstyp = Vyer

**Top** Contributorsconfig: Typ = Medlemmar, aktivitetstyp = Bokföring

**Övre** innehållskonfiguration: Typ = Innehåll, aktivitetstyp = Vyer,

**Trending** Contentconfig: Typ = innehåll, aktivitetstyp = inlägg

![chlimage_1-230](assets/chlimage_1-230.png)
