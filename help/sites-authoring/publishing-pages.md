---
title: Publicera sidor
seo-title: Publicera sidor
description: 'null'
seo-description: 'null'
uuid: 1222859d-ef8d-462e-a125-b76e6cfec26d
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 8f2714bc-9d6c-4e6f-97a1-3b4f977348c5
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340
workflow-type: tm+mt
source-wordcount: '1630'
ht-degree: 6%

---


# Publicera sidor{#publishing-pages}

När du har skapat och granskat ditt innehåll i författarmiljön är målet att [göra det tillgängligt på din offentliga webbplats](/help/sites-authoring/author.md#concept-of-authoring-and-publishing) (din publiceringsmiljö).

Detta kallas att publicera en sida. När du vill ta bort en sida från publiceringsmiljön kallas det för att avpublicera. När sidan publiceras och avpubliceras är den fortfarande tillgänglig i redigeringsmiljön för ytterligare ändringar tills du tar bort den.

Du kan även publicera/avpublicera en sida direkt eller vid ett fördefinierat datum/tid i framtiden.

>[!NOTE]
>
>Vissa termer om publicering kan vara förvirrade:
>
>* **Publicera/avpublicera**
   >  Detta är de primära villkoren för de åtgärder som gör innehållet tillgängligt för allmänheten i publiceringsmiljön (eller inte).
   >
   >
* **Aktivera/inaktivera**
   >  Dessa termer är synonyma med publicera/avpublicera.
   >
   >
* **Replikering/replikering**
   >  Detta är de tekniska termer som beskriver hur data (t.ex. sidinnehåll, filer, kod, användarkommentarer) flyttas från en miljö till en annan, t.ex. vid publicering eller omvänd replikering av användarkommentarer.
>



>[!NOTE]
>
>Om du inte har behörighet att publicera en viss sida:
>
>* Ett arbetsflöde kommer att utlösas för att meddela lämplig person om din begäran om publicering.
>* Det här [arbetsflödet kan ha anpassats](/help/sites-developing/workflows-models.md) av ditt utvecklingsteam.
>* Ett meddelande visas kort för att meddela dig att arbetsflödet har utlösts.

>



## Publicera sidor {#publishing-pages-2}

Beroende på var du befinner dig kan du publicera:

* [Från sidredigeraren](/help/sites-authoring/publishing-pages.md#publishing-from-the-editor)
* [Från webbplatskonsolen](/help/sites-authoring/publishing-pages.md#publishing-from-the-console)

### Publicera från Redigeraren {#publishing-from-the-editor}

Om du redigerar en sida kan den publiceras direkt från redigeraren.

1. Välj ikonen **Sidinformation** för att öppna menyn och sedan alternativet **Publicera sida** .

   ![screen_shot_2018-03-21at152734](assets/screen_shot_2018-03-21at152734.png)

1. Beroende på om sidan har referenser som behöver publiceras:

   * Sidan publiceras direkt om det inte finns några referenser att publicera.
   * Om sidan innehåller referenser som behöver publiceras visas dessa i **publiceringsguiden** där du kan antingen:

      * Ange vilket av resurserna/taggarna/etc. du vill publicera tillsammans med sidan och sedan använda **Publicera** för att slutföra processen.
      * Använd **Avbryt** om du vill avbryta åtgärden.

   ![chlimage_1-50](assets/chlimage_1-50.png)

1. Om du väljer **Publicera** kommer sidan att replikeras till publiceringsmiljön. I sidredigeraren visas en informationsbanderoll som bekräftar publiceringsåtgärden.

   ![screen_shot_2018-03-21at152840](assets/screen_shot_2018-03-21at152840.png)

   När du visar samma sida i konsolen visas den uppdaterade publiceringsstatusen.

   ![screen_shot_2018-03-21at152951](assets/screen_shot_2018-03-21at152951.png)

>[!NOTE]
>
>Publicering från redigeraren är en ytlig publicering, dvs endast den valda sidan/de markerade sidorna publiceras och inga underordnade sidor publiceras.

### Publicera från konsolen {#publishing-from-the-console}

I platskonsolen finns det två alternativ för publicering:

* [Snabbpublicering](/help/sites-authoring/publishing-pages.md#quick-publish)
* [Hantera publikation](/help/sites-authoring/publishing-pages.md#manage-publication)

#### Snabbpublicering {#quick-publish}

**Snabbpublicering** är avsett för enkla ärenden och publicerar den eller de markerade sidorna direkt utan ytterligare interaktion. Därför kommer alla icke-publicerade referenser också att publiceras automatiskt.

Så här publicerar du en sida med Snabbpublicering:

1. Markera sidan eller sidorna i webbplatskonsolen och klicka på knappen **Snabbpublicering** .

   ![screen_shot_2018-03-21at153115](assets/screen_shot_2018-03-21at153115.png)

1. I dialogrutan Snabbpublicering bekräftar du publikationen genom att klicka på **Publicera** eller Avbryt genom att klicka på **Avbryt**. Kom ihåg att alla opublicerade referenser också publiceras automatiskt.

   ![chlimage_1-51](assets/chlimage_1-51.png)

1. När sidan publiceras visas en varning som bekräftar publiceringen.

>[!NOTE]
>
>Snabbpublicering är en grund publicering, d.v.s. endast den valda sidan/de markerade sidorna publiceras och inga underordnade sidor publiceras.

#### Hantera publikation {#manage-publication}

**Med Hantera publikation** får du fler alternativ än Snabbpublicering, så att du kan inkludera underordnade sidor, anpassa referenserna och starta tillämpliga arbetsflöden samt erbjuda möjlighet att publicera vid ett senare tillfälle.

Så här publicerar eller avpublicerar du en sida med Hantera publikation:

1. Markera sidan eller sidorna i webbplatskonsolen och klicka på knappen **Hantera publikation** .

   ![screen_shot_2018-03-21at153309](assets/screen_shot_2018-03-21at153309.png)

1. Guiden **Hantera publikation** startar. I det första steget, **Alternativ**, kan du:

   * Välj om du vill publicera eller avpublicera de markerade sidorna.
   * Välj om du vill utföra åtgärden nu eller vid ett senare datum.

   När du publicerar senare startas ett arbetsflöde för publicering av den eller de valda sidorna vid den angivna tidpunkten. Om du inte publicerar senare startas ett arbetsflöde för att avpublicera den eller de valda sidorna vid en viss tidpunkt.

   Om du vill avbryta en publicering/avpublicering senare går du till [arbetsflödeskonsolen](/help/sites-administering/workflows.md) och avslutar motsvarande arbetsflöde.

   ![chlimage_1-52](assets/chlimage_1-52.png)

   Klicka på **Nästa** för att fortsätta.

1. I nästa steg i guiden Hantera publikation, **Omfång**, kan du definiera omfattningen för publikationen/borttagningen, till exempel att inkludera underordnade sidor och/eller inkludera referenser.

   ![screen_shot_2018-03-21at153354](assets/screen_shot_2018-03-21at153354.png)

   Du kan använda knappen **Lägg till innehåll** för att lägga till ytterligare sidor i listan över sidor som ska publiceras, om du inte valde någon innan du startade guiden Hantera publikation.

   När du klickar på knappen Lägg till innehåll startas [sökvägsläsaren](/help/sites-authoring/author-environment-tools.md#path-browser) så att du kan välja innehåll.

   Markera önskade sidor och klicka sedan på **Välj** för att lägga till innehållet i guiden eller **Avbryt **för att avbryta valet och återgå till guiden.

   I guiden kan du markera ett objekt i listan för att konfigurera ytterligare alternativ, till exempel:

   * Inkludera dess underordnade.
   * Ta bort den från markeringen.
   * Hantera dess publicerade referenser.

   ![screen_shot_2018-03-21at153450](assets/screen_shot_2018-03-21at153450.png)

   När du klickar på **Inkludera underordnade** öppnas en dialogruta där du kan:

   * Inkludera endast omedelbara barn.
   * Inkludera endast ändrade sidor.
   * Inkludera endast redan publicerade sidor.

   Klicka på **Lägg** till för att lägga till underordnade sidor i listan över sidor som ska publiceras eller avpubliceras baserat på de valda alternativen. Klicka på **Avbryt** om du vill avbryta markeringen och återgå till guiden.

   ![chlimage_1-53](assets/chlimage_1-53.png)

   När du återgår till guiden visas de sidor som lagts till baserat på dina val i dialogrutan Inkludera underordnade.

   Du kan visa och ändra referenserna som ska publiceras eller avpubliceras för en sida genom att markera den och sedan klicka på knappen **Publicerade referenser** .

   ![screen_shot_2018-03-21at153801](assets/screen_shot_2018-03-21at153801.png)

   I dialogrutan **Publicerade referenser** visas referenser för det markerade innehållet. Som standard är alla markerade och publiceras/avpubliceras, men du kan avmarkera dem så att de inte tas med i funktionsmakrot.

   Klicka på **Klar** för att spara ändringarna eller **Avbryt** för att avbryta markeringen och återgå till guiden.

   ![screen_shot_2018-03-21at153824](assets/screen_shot_2018-03-21at153824.png)

   I guiden uppdateras kolumnen **Referenser** så att den återspeglar ditt val av referenser som ska publiceras eller avpubliceras.

   ![screen_shot_2018-03-21at153925](assets/screen_shot_2018-03-21at153925.png)

1. Klicka på **Publicera** för att slutföra.

   I webbplatskonsolen bekräftar ett meddelande publikationen.

   ![screen_shot_2018-03-21at153951](assets/screen_shot_2018-03-21at153951.png)

1. Om de publicerade sidorna är kopplade till arbetsflöden kan de visas i ett **arbetsflödessteg** i publikationsguiden.

   >[!NOTE]
   >
   >Steget **Arbetsflöden** visas baserat på vilka rättigheter användaren har eller inte har. Mer information finns i den [föregående kommentaren på den här sidan](/help/sites-authoring/publishing-pages.md) om publiceringsrättigheter samt [Hantera åtkomst till arbetsflöden](/help/sites-administering/workflows-managing.md) och [Använda arbetsflöden på sidor](/help/sites-authoring/workflows-applying.md) .

   Resurserna grupperas efter de arbetsflöden som utlöses och de olika alternativen:

   * Definiera arbetsflödets rubrik.
   * Behåll arbetsflödespaketet, förutsatt att arbetsflödet har stöd [för](/help/sites-developing/workflows-models.md#configuring-a-workflow-for-multi-resource-support)flera resurser.
   * Definiera en titel på arbetsflödespaketet om alternativet att behålla arbetsflödespaketet har valts.

   Click **Publish** or **Publish Later **to complete the publication.

   ![chlimage_1-54](assets/chlimage_1-54.png)

## Avpublicerar sidor {#unpublishing-pages}

Om du avpublicerar en sida tas den bort från publiceringsmiljön så att den inte längre är tillgänglig för läsarna.

På ett [sätt som liknar publicering](/help/sites-authoring/publishing-pages.md#publishing-pages)kan en eller flera sidor avpubliceras:

* [Från sidredigeraren](/help/sites-authoring/publishing-pages.md#unpublishing-from-the-editor)
* [Från webbplatskonsolen](/help/sites-authoring/publishing-pages.md#unpublishing-from-the-console)

### Avpublicera från redigeraren {#unpublishing-from-the-editor}

När du redigerar en sida och vill avpublicera den väljer du **Avpublicera sida** på menyn **Sidinformation** , på samma sätt som du skulle [publicera sidan](/help/sites-authoring/publishing-pages.md#publishing-from-the-editor).

### Avpublicera från konsolen {#unpublishing-from-the-console}

På samma sätt som du [använder alternativet Hantera publikation för att publicera](/help/sites-authoring/publishing-pages.md#manage-publication)kan du även använda det för att avpublicera.

1. Markera sidan eller sidorna i webbplatskonsolen och klicka på knappen **Hantera publikation** .
1. Guiden **Hantera publikation** startar. I det första steget **Alternativ** väljer du **Avpublicera** i stället för standardalternativet **Publicera**.

   ![chlimage_1-55](assets/chlimage_1-55.png)

   På samma sätt som publiceringen senare startar ett arbetsflöde för att publicera den här versionen av sidan vid den angivna tidpunkten, startar inaktiveringen senare ett arbetsflöde för att avpublicera den valda sidan eller de valda sidorna vid en viss tidpunkt.

   Om du vill avbryta en publicering/avpublicering senare går du till [arbetsflödeskonsolen](/help/sites-administering/workflows.md) och avslutar motsvarande arbetsflöde.

1. Om du vill slutföra borttagningen fortsätter du med guiden på samma sätt som du [publicerar sidan](/help/sites-authoring/publishing-pages.md#manage-publication).

## Publicera och avpublicera ett träd {#publishing-and-unpublishing-a-tree}

När du har angett eller uppdaterat ett stort antal innehållssidor, som alla finns på samma rotsida, kan det vara enklare att publicera hela trädet i en åtgärd.

Du kan använda alternativet [Hantera publikation](/help/sites-authoring/publishing-pages.md#manage-publication) på webbplatskonsolen för att göra detta.

1. I webbplatskonsolen väljer du rotsidan för det träd som du vill publicera eller avpublicera och väljer **Hantera publikation**.
1. Guiden **Hantera publikation** startar. Välj om du vill publicera eller avpublicera och när det ska ske och välj **Nästa** för att fortsätta.
1. Markera rotsidan i **omfångssteget** och välj **Inkludera underordnade**.

   ![chlimage_1-56](assets/chlimage_1-56.png)

1. Avmarkera alternativen i dialogrutan **Inkludera underordnade** :

   * Inkludera endast omedelbart underordnade
   * Inkludera endast redan publicerade sidor

   Dessa alternativ är markerade som standard, så du måste komma ihåg att avmarkera dem. Klicka på **Lägg till** för att bekräfta och lägga till innehållet i publikationen/avpublikationen.

   ![chlimage_1-57](assets/chlimage_1-57.png)

1. Guiden **Hantera publikation** visar innehållet i trädet för granskning. Du kan anpassa markeringen ytterligare genom att lägga till ytterligare sidor eller ta bort de markerade sidorna.

   ![screen_shot_2018-03-21at154237](assets/screen_shot_2018-03-21at154237.png)

   Kom ihåg att du även kan granska referenser som ska publiceras via alternativet **Publicerade referenser** .

1. [Fortsätt med guiden Hantera publikation som vanligt](#manage-publication) för att slutföra publikationen eller avpublikationen av trädet.

## Bestämmer publiceringsstatus {#determining-publication-status}

Du kan ange en sidas publiceringsstatus:

* I [resursöversiktsinformationen på platskonsolen](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources)

   ![screen_shot_2018-03-21at154336](assets/screen_shot_2018-03-21at154336.png)

   Publikationsstatusen visas i [kort](/help/sites-authoring/basic-handling.md#card-view)-, [kolumn](/help/sites-authoring/basic-handling.md#column-view)- och [list](/help/sites-authoring/basic-handling.md#list-view)vyerna i Sites-konsolen.

* På [tidslinjen](/help/sites-authoring/basic-handling.md#timeline)

   ![screen_shot_2018-03-21at154420](assets/screen_shot_2018-03-21at154420.png)

* På menyn [](/help/sites-authoring/author-environment-tools.md#page-information) Sidinformation när du redigerar en sida

   ![screen_shot_2018-03-21at154456](assets/screen_shot_2018-03-21at154456.png)

