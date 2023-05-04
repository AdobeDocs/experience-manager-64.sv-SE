---
title: Grundläggande om Rich Text Editor
seo-title: Rich Text Editor Essentials
description: Översikt över textredigeringsfunktionen
seo-description: Rich text Editor feature overview
uuid: f96015cc-114b-431a-a5ba-dc195c2a0b83
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: 0225a543-0fad-488b-8b0b-8b3512d44fbe
exl-id: d236a8d3-20ad-4568-a7c2-87d146aa0532
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 1%

---

# Grundläggande om Rich Text Editor {#rich-text-editor-essentials}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Översikt {#overview}

Med en textredigerare kan du skriva text med markeringar.

För webbgruppskomponenter, men liknande [textredigerare i redigeringsmiljön](../../help/sites-authoring/rich-text-editor.md)påverkar det text som anges i publiceringsmiljön.

![chlimage_1-410](assets/chlimage_1-410.png)

## Aktivera RTF-redigerare {#enabling-rich-text-editor}

Communities-komponenter som tillåter användargenererat innehåll (UGC) kan aktiveras för att tillåta RTE. Beroende på om komponenten har lagts till på en sida eller inkluderats i en [function](functions.md), RTE kanske är aktiverat som standard.

Om den inte är aktiverad skriver du [redigeringsläge för författare](sites-console.md#authoring-site-content), markerar komponenten för redigering och markerar `Rich Text Editor` kryssrutan.

RTE är tillgängligt för följande Communities-komponenter:

* [Blogg](blog-feature.md)
* [Kalender](calendar.md)
* [Kommentarer](comments.md)
* [Filbibliotek](file-library.md)
* [Forum](forum.md)
* [Meddelanden](configure-messaging.md)
* [QnA](working-with-qna.md)
* [Recensioner](reviews.md)

## Anpassning {#customization}

Det går att anpassa RTF-redigeraren eftersom implementeringen baseras på [CKEditor](https://www.ckeditor.com/).

Den aktuella konfigurationen för Communities-komponenter finns i `cq.social.  scf   clientlib`, som finns i databasen på

`/libs/clientlibs/social/commons/scf/ckrte.js`

Du bör inte ändra klientlib cq.social.scf eftersom framtida uppgraderingar kan åsidosätta redigeringar.

### Exempelanpassning: Textbundna länkar {#example-customization-inline-links}

På grund av säkerhetsproblem inkluderas inte hyperlänksalternativen i den uppsättning med textikoner som visas för medlemmar som standard. Förmågan till skada är stor när hrefs tillåts i UGC.

Så här lägger du till hyperlänksalternativen i verktygsfältet:

* Lägg till ett verktygsfält med namnet &quot; `links`&quot;
   * `{ name: 'links', items: [ 'Link','Unlink','Anchor' ] }`
* Välj **[!UICONTROL Save All]**

#### /libs/clientlibs/social/commons/scf/ckrte.js {#libs-clientlibs-social-commons-scf-ckrte-js}

```
CKRte.prototype.config = {
    toolbar: [
        { name: "basicstyles",
           items: ["Bold", "Italic", "Underline", "NumberedList", "BulletedList", "Outdent", "Indent", "JustifyLeft", "JustifyCenter", "JustifyRight", "JustifyBlock", "TextColor"]
        },
        { name: 'links', 
           items: [ 'Link','Unlink','Anchor' ] 
        }
    ],
    autoParagraph: false,
    autoUpdateElement: false,
    removePlugins: "elementspath",
    resize_enabled: false
};
```
