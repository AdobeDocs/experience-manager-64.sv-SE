---
title: Skapa en anpassad anpassad formulärmall
seo-title: Creating a custom adaptive form template
description: I den här artikeln beskrivs hur du skapar anpassade formulärmallar.
seo-description: This article describes how to create custom adaptive form templates.
uuid: 8f8c770f-984c-48e8-978c-7cdfcd1af95b
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: customization
discoiquuid: c6115b64-e06f-4b5e-b7f9-876553c7627f
exl-id: 83f978ca-d451-4d27-820f-3620331285cf
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1179'
ht-degree: 0%

---

# Skapa en anpassad anpassad formulärmall {#creating-a-custom-adaptive-form-template}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Förutsättningar {#prerequisites}

* AEM [Sidmall](/help/sites-authoring/templates.md) och [Adaptiv formulärredigering](https://helpx.adobe.com/aem-forms/6-1/introduction-forms-authoring.html)

* AEM [Klientbibliotek](/help/sites-developing/clientlibs.md)

## Adaptiv formulärmall {#adaptive-form-template}

En mall för anpassat formulär är en AEM sidmall med vissa egenskaper och innehållsstruktur som används för att skapa anpassningsbara formulär. Mallen innehåller förkonfigurerade layouter, format och grundläggande innehållsstruktur.

När du har skapat ett formulär återspeglas inte ändringarna i den ursprungliga mallinnehållsstrukturen i formuläret.

## Standardmallar för anpassningsbara formulär {#default-adaptive-form-templates}

AEM QuickStart innehåller följande adaptiva formulärmallar:

* Grundläggande: Gör att du kan skapa ett anpassat formulär med flera flikar i en tabbar-till-vänster-layout, där du kan besöka flikar i valfri slumpmässig ordning.
* Grundläggande med Acrobat Sign: Skapa ett formulär med flera flikar och guider. Den har en tabbar till vänster-layout där du kan gå till flikarna i valfri ordning. Den använder Adobe Document Cloud designtjänster för signering och verifiering.
* Tom mall: Gör att du kan skapa ett formulär utan sidhuvud, sidfot och ursprungligt innehåll. Du kan lägga till komponenter som textrutor, knappar och bilder. Med den tomma mallen kan du skapa ett formulär som du kan [bädda in AEM webbplatssidor](/help/forms/using/embed-adaptive-form-aem-sites.md).

De här mallarna har `sling:resourceType` -egenskapen ställs in på motsvarande sidkomponent. Sidkomponenten återger CQ-sidan med adaptiv formulärbehållare, som i sin tur återger adaptiv form.

I följande tabell räknas associationen mellan mallar och sidkomponenter upp:

<table> 
 <tbody> 
  <tr> 
   <td><p><strong>Mall</strong></p> </td> 
   <td><p><strong>Sidkomponent</strong></p> </td> 
  </tr> 
  <tr> 
   <td><p>/libs/fd/af/templates/surveyTemplate</p> </td> 
   <td><p>/libs/fd/af/components/page/survey</p> </td> 
  </tr> 
  <tr> 
   <td><p>/libs/fd/af/templates/simpleEnrollmentTemplate</p> </td> 
   <td><p>/libs/fd/af/components/page/base</p> </td> 
  </tr> 
  <tr> 
   <td><p>/libs/fd/af/templates/tabbedEnrollmentTemplate</p> </td> 
   <td><p>/libs/fd/af/components/page/tabbedenrollment</p> </td> 
  </tr> 
  <tr> 
   <td><p>/libs/fd/afaddon/templates/advancedEnrollmentTemplate</p> </td> 
   <td><p>/libs/fd/afaddon/components/page/advancedRotering</p> </td> 
  </tr> 
 </tbody> 
</table>

## Skapa en adaptiv formulärmall med mallredigeraren {#creating-an-adaptive-form-template-using-template-editor}

Du kan ange strukturen och det ursprungliga innehållet i ett anpassat formulär med hjälp av mallredigeraren. Du vill till exempel att alla formulärförfattare ska ha få textrutor, navigeringsknappar och en skicka-knapp i ett registreringsformulär. Du kan skapa en mall som författare kan använda för att skapa ett formulär som är konsekvent med andra registreringsformulär. Med AEM Template Editor kan du:

* Lägga till sidhuvud- och sidfotskomponenter i ett formulär i strukturlagret
* Ange formulärets ursprungliga innehåll.
* Ange ett tema.
* Ange åtgärder som att skicka, återställa och navigera.

Mer information finns i [Mallredigerare](/help/forms/using/template-editor.md).

## Skapa en adaptiv formulärmall från CRXDE {#creating-an-adaptive-form-template-from-crxde}

I stället för att använda de tillgängliga mallarna kan du skapa en mall och använda den för att skapa anpassade formulär. Anpassade mallar baseras på olika sidkomponenter som refererar till adaptiva formulärbehållare och sidelement, t.ex. sidhuvud och sidfot.

Du kan skapa de här komponenterna med bassidkomponenten för webbplatsen. Du kan också utöka sidkomponenten i det adaptiva formuläret som finns i rutmallarna.

Utför följande steg för att skapa en anpassad mall, till exempel simpleEnrollmentTemplate.

1. Navigera till CRXDE Lite i redigeringsinstansen.

1. Skapa mappstrukturen för programmet i katalogen /apps. Om programnamnet till exempel är mitt eget skapar du en mapp med det här namnet. Programmappen innehåller vanligtvis komponenter, konfiguration, mallar, src och installationskataloger. I det här exemplet skapar du mapparna för komponenter, konfiguration och mallar.

1. Navigera till mappen /libs/fd/af/templates.
1. Kopiera `simpleEnrollmentTemplate` nod.
1. Navigera till mappen /apps/mycompany/templates. Högerklicka på den och välj **[!UICONTROL Paste]**.
1. Om det behövs byter du namn på mallnoden som du kopierade. Du kan t.ex. byta namn på den som en registreringsmall.

1. Navigera till platsen /apps/mycompany/templates/enrollment-template.

1. Ändra `jcr:title` och `jcr:description` egenskaper för `jcr:content` för att skilja mallen från mallen som du kopierade.

1. The `jcr:content` noden i den ändrade mallen innehåller `guideContainer` och `guideformtitle` -komponenter. `guideContainer` är den behållare som innehåller det adaptiva formuläret. The `guideformtitle` -komponenten visar programnamnet, beskrivningen och så vidare.

   I stället för `guideformtitle`kan du ta med en anpassad komponent eller `parsys` -komponenten. Ta till exempel bort `guideformtitle`och lägga till en anpassad komponent eller `parsys` komponentnod. Se till att `sling:resourceType` -egenskapen för komponenten refererar till komponenten och det är definierat på sidan `component.jsp` -fil.

1. Navigera till platsen /apps/mycompany/templates/enrollment-template/jcr:content.

1. Öppna **[!UICONTROL Properties]** och ändra värdet på `cq:designPath` till /etc/designs/mincompany.

1. Skapa nu en /etc/designs/mycompany-nod för `cq:Page` typ.

## Skapa en adaptiv komponent för formulärsidor {#create-an-adaptive-form-page-component}

Den anpassade mallen har samma format som standardmallen eftersom mallen refererar till sidkomponenten /libs/fd/af/components/page/base. Du kan hitta komponentreferensen som egenskapen `sling:resourceType` definieras på noden /apps/mycompany/templates/enrollment-template/jcr:content. Eftersom basen är en kärnproduktkomponent bör du inte ändra den här komponenten.

1. Navigera till noden /apps/mycompany/templates/enrollment-template/jcr:content och ändra egenskapens värde `sling:resourceType` till /apps/mycompany/components/page/enrollmentpage
1. Kopiera noden /libs/fd/af/components/page/base till mappen /apps/mycompany/components/page.

1. Byt namn på den kopierade komponenten till `enrollmentpage`.

1. **(Endast om du redan har en innehållssida)** Utför följande steg (a-d) om du har en befintlig `contentpage`-komponent för din webbplats. Om du inte har någon befintlig `contentpage`kan du lämna `resourceSuperType`så att den pekar på OTB-bassidan.

   1. För `enrollmentpage` nod, ange egenskapens värde `sling:resourceSuperType` till mincompany/components/page/contentpage. The `contentpage` är bassidkomponenten för -platsen. Andra sidkomponenter kan utöka den. Ta bort skriptfiler under `enrollmentpage`, förutom `head.jsp`, `content.jsp`och `library.jsp`. The `sling:resourceSuperType` -komponent, som `contentpage` i det här fallet innehåller alla sådana skript. Sidhuvuden, inklusive navigeringsfält och sidfötter, ärvs från `contentpage` -komponenten.

   1. Öppna filen `head.jsp`.

      JSP-filen innehåller raden `<cq.include script="library.jsp"/>`.

      The `library.jsp` filen innehåller `guide.theme.simpleEnrollment` klientbibliotek, som innehåller formateringen för det adaptiva formuläret.

      Sidkomponenten `enrollmentpage` har en exklusiv `head.jsp` som åsidosätter `head.jsp` filen `contentpage` -komponenten.

   1. Inkludera alla skript i `head.jsp` filen för `contentpage` till `head.jsp` filen för `enrollmentpage` -komponenten.
   1. I `content.jsp` kan du lägga till ytterligare sidinnehåll eller referenser till andra komponenter som inkluderas när en sida återges. Om du till exempel lägger till den anpassade komponenten `applicationformheader`ska du se till att du lägger till följande referens till komponenten i JSP-filen:

      `<cq:include path="applicationformheader" resourceType="mycompany/components/applicationformheader"/>`

      Om du lägger till en `parsys` -komponenten i mallnodstrukturen, även den anpassade komponenten.

## Skapa ett adaptivt formulärklientbibliotek {#creating-an-adaptive-form-client-library}

The `head.jsp` filen `enrollmentpage` -komponenten för den nya mallen innehåller ett klientbibliotek `guide.theme.simpleEnrollment`. Standardmallen använder även det här klientbiblioteket. Ändra formatet i den nya mallen på något av följande sätt:

* Definiera ett anpassat tema och ersätt standardtemat `guide.theme.simpleEnrollment` med det anpassade temat.
* Definiera ett nytt klientbibliotek under /etc/designs/mincompany. Inkludera klientbiblioteket efter standardtemaposten på jsp-sidan. Inkludera alla åsidosatta format och ytterligare JavaScript-filer i det här klientbiblioteket.

>[!NOTE]
>
>Temat avser ett klientbibliotek som ingår i sidkomponenten som används för att återge ett anpassat formulär. Klientbiblioteket styr huvudsakligen utseendet på ett anpassat formulär.
