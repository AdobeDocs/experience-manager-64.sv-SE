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

---


# Aktivitetstrender {#activity-trends}

## Introduktion {#introduction}

Komponenten `Community Activity List` gör det möjligt att lägga till trendinformation om inlägg och vyer från medlemmar samt inlägg och vyer av innehåll.

Detta avsnitt i dokumentationen beskriver

* Lägga till `Community Activity List` komponenten på en [communitywebbplats](overview.md#community-sites)

* Konfigurationsinställningar för `Community Activity List` komponenten

## Krav {#requirement}

Data för webbplatsen `Community Activity List` är bara tillgängliga när Adobe Analytics är licensierat och konfigurerat för communitywebbplatsen.

Se [Analyskonfiguration för communityfunktioner](analytics.md).

## Lägga till en lista med communityaktiviteter på en sida {#adding-a-community-activity-list-to-a-page}

Om du vill lägga till en `Community Activity List` komponent på en sida i redigeringsläge, letar du reda på komponenten `Communities / Community Activity List` och drar den på plats på en sida.

Mer information finns i Grunderna för [communitykomponenter](basics.md).

När komponenten placeras på en sida i en community-webbplats är det så här den visas:

![chlimage_1-227](assets/chlimage_1-227.png)

## Konfigurerar lista över communityaktiviteter {#configuring-community-activity-list}

Markera den monterade `Community Activity List` komponent som du vill öppna och välj den `Configure` ikon som öppnar redigeringsdialogrutan.

![chlimage_1-228](assets/chlimage_1-228.png)

Under fliken **[!UICONTROL Kommentarer]** anger du om och hur kommentarer för överförda filer ska visas:

![chlimage_1-229](assets/chlimage_1-229.png)

* **[!UICONTROL Typ]**

   Ange om data ska visas för communitymedlemmar eller användargenererat innehåll (UGC).

   Välj från
   * `Members`
   * `Content`
   Standardvärdet är `Members`.

* **[!UICONTROL Visa titel]**

   En beskrivande rubrik som ska visas ovanför data, till exempel `Trending Content`.

   Standard är ingen titel.

* **[!UICONTROL Visa antal]**

   Antalet objekt som ska listas.

   Standardvärdet är 10.

* **[!UICONTROL Typ av aktivitet]**

   Välj en av
   * `Views`(sidbesök)
   * `Posts`(skapa UGC)
   * `Follows`
   * `Likes`
   Standardvärdet är Vyer.

* **[!UICONTROL Tidsperiod]**

   Välj en av
   * `Last 24 hours`
   * `Last 7 days`
   * `Last 30 days`
   * `Last 90 days`
   * `This year (since Jan 1st)`
   * `Total`
   Standardvärdet är `Total`.

* **[!UICONTROL Kontextbana]**

   Gör det möjligt att omfång aktiviteten till en delmängd av platsen, t.ex. en viss blogg.

   Standard är hela communitywebbplatsen.

* **[!UICONTROL Medlemsräkningsaggregering]**

   När alternativet är avmarkerat (inaktiverat) räknas endast inlägg på den översta nivån. Om till exempel kontexten är rotsidan (standardinställningen) `Activity Type`visas ingen aktivitet `Posts`i den, eftersom det inte går att publicera innehåll på rotsidan. När du markerar det här alternativet inkluderas antalet på alla underordnade sidor.

   Standard är markerat.

## Exempelsida med 4 komponenter {#example-page-with-components}

**Konfiguration för besökare** : Typ = Medlemmar, aktivitetstyp = Vyer

**Top Contributors** config: Typ = Medlemmar, aktivitetstyp = Bokföring

**Konfiguration för det övre innehållet** : Typ = Innehåll, aktivitetstyp = Vyer,

**Trending Content** config: Typ = innehåll, aktivitetstyp = inlägg

![chlimage_1-230](assets/chlimage_1-230.png)
