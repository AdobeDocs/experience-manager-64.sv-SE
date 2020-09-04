---
title: Lägg till klienter
seo-title: Lägg till klienter
description: Lägg till en ClientLibraryFolder
seo-description: Lägg till en ClientLibraryFolder
uuid: cdc1d258-2011-4517-9206-dd2b5d1f7e0d
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: c84040b0-7850-4960-b676-ffa0a74c8cb2
translation-type: tm+mt
source-git-commit: 805e4411930749ff4b6b05ea4a8b87b4f96d72fd
workflow-type: tm+mt
source-wordcount: '652'
ht-degree: 5%

---


# Lägg till klienter {#add-clientlibs}

## Lägg till en ClientLibraryFolder (clientlibs) {#add-a-clientlibraryfolder-clientlibs}

Skapa en ClientLibraryFolder med namnet `clientlibs`som innehåller den JS och CSS som används för att återge platsens sidor.

Det `categories`egenskapsvärde som anges för det här klientbiblioteket är den identifierare som används för att ta med klientlibben direkt från en innehållssida eller för att bädda in den i andra klientlibs.

1. Använda **[!UICONTROL CRXDE Lite]** expanderar `/etc/designs`

1. Högerklicka på `an-scf-sandbox` och välj `Create Node`

   * Namn: `clientlibs`
   * Typ: `cq:ClientLibraryFolder`

1. Klicka på **[!UICONTROL OK]**

![chlimage_1-220](assets/chlimage_1-220.png)

På fliken **[!UICONTROL Properties]** för den nya `clientlibs` noden anger du **`categories`** egenskapen:

* Namn: **[!UICONTROL categories]**
* Typ: **[!UICONTROL String]**
* Värde: **[!UICONTROL apps.an-scf-sandbox]**
* Klicka på **[!UICONTROL Add]**
* Klicka på **[!UICONTROL Save All]**

Obs! för att visa kategorivärdet med appar. är en konvention som identifierar att det ägande programmet finns i /apps-mappen, inte /libs.  VIKTIGT! Lägg till platshållare `js.txt` och `css.txt` filer. (Det är inte officiellt en cq:ClientLibraryFolder utan dem.)


1. Högerklicka på **`/etc/designs/an-scf-sandbox/clientlibs`**
1. Välj **[!UICONTROL Create File...]**
1. Enter **[!UICONTROL Name]**: `css.txt`

1. Välj **[!UICONTROL Create File...]**
1. Enter **[!UICONTROL Name]**: `js.txt`

1. Klicka på **[!UICONTROL Save All]**

![chlimage_1-221](assets/chlimage_1-221.png)

Den första raden i css.txt och js.txt identifierar den basplats från vilken följande fillistor ska hittas.

Försök att ange innehållet i css.txt till:

```
#base=.
 style.css
```

Skapa sedan en fil under clientlibs med namnet style.css och ställ in innehållet på:

`body {`

`background-color: #b0c4de;`

`}`

## Bädda in SCF-klienter {#embed-scf-clientlibs}

Ange egenskapen String med flera värden på fliken **[!UICONTROL Properties]** för `clientlibs` noden **[!UICONTROL embed]**. Då bäddas nödvändiga [klientbibliotek (klientlibs) in för SCF-komponenter](client-customize.md#clientlibs-for-scf). I den här självstudiekursen ska vi lägga till många av de klientlibs som behövs för webbkomponenterna.

**Observera** att detta kan vara det önskade tillvägagångssättet för en produktionsplats, eftersom det kan vara en god idé jämfört med storleken/hastigheten på de klienter som laddas ned för varje sida.

Om du bara använder en funktion på en sida kan du inkludera den funktionens fullständiga klientlib direkt på sidan, t.ex. &lt;% ui:includeClientLib categories=cq.social.hbs.forum&quot; %>

I det här fallet tar vi med alla, och föredrar därför de mer grundläggande SCF-klientlibs som är författarens klientlibs:

* Namn: **`embed`**
* Typ: **`String`**

* Klicka på **`Multi`**
* Värde: **`cq.social.scf`**

   *&lt;enter> öppnar en dialogruta*

   *Klicka **[+]**efter varje post för att lägga till följande kategorier för klientlib:*

   * **`cq.ckeditor`**
   * **`cq.social.author.hbs.comments`**
   * **`cq.social.author.hbs.forum`**
   * **`cq.social.author.hbs.rating`**
   * **`cq.social.author.hbs.reviews`**
   * **`cq.social.author.hbs.voting`**
   * Klicka på **[!UICONTROL OK]**

* Klicka på **[!UICONTROL Save All]**

![chlimage_1-222](assets/chlimage_1-222.png)

Så här `/etc/designs/an-scf-sandbox/clientlibs` ska nu visas i databasen:

![chlimage_1-223](assets/chlimage_1-223.png)

## Inkludera klienter i PlayPage-mallen {#include-clientlibs-in-playpage-template}

Utan att ta med kategorin `apps.an-scf-sandbox` ClientLibraryFolder på sidan kommer SCF-komponenterna inte att fungera och inte formateras, eftersom de JavaScript och format som behövs inte kommer att vara tillgängliga.

Utan att ta med clientlibs ser SCF-kommentarskomponenten till exempel formaterad ut:

![chlimage_1-224](assets/chlimage_1-224.png)

När clientlibs för apps.an-scf-sandbox ingår formateras SCF-kommentarskomponenten:

![chlimage_1-225](assets/chlimage_1-225.png)

Programsatsen include tillhör i `<head>` avsnittet i `<html>` skriptet. Standardvärdet **`foundation head.jsp`** innehåller ett skript som kan överlappas: **`headlibs.jsp`**.

**Copy headlibs.jsp and include clientlibs:**

1. Använd **[!UICONTROL CRXDE Lite]** och markera **`/libs/foundation/components/page/headlibs.jsp`**
1. Högerklicka och välj **[!UICONTROL Copy]** (eller välj Kopiera från verktygsfältet)
1. Välj **`/apps/an-scf-sandbox/components/playpage`**
1. Högerklicka och välj **[!UICONTROL Paste]** (eller välj Klistra in i verktygsfältet)
1. Dubbelklicka på **`headlibs.jsp`** för att öppna den
1. Lägg till följande rad i slutet av filen

   **`<ui:includeClientLib categories="apps.an-scf-sandbox"/>`**

1. Klicka på **[!UICONTROL Save All]**


```xml
<%@ page session="false" %><%
%><%@include file="/libs/foundation/global.jsp" %><%
%><ui:includeClientLib categories="cq.foundation-main"/><%
%>
<cq:include script="/libs/cq/cloudserviceconfigs/components/servicelibs/servicelibs.jsp"/>
<% currentDesign.writeCssIncludes(pageContext); %>
<ui:includeClientLib categories="apps.an-scf-sandbox"/>
```

Läs in webbplatsen i webbläsaren och se om bakgrunden inte är en blå nyans.

[http://localhost:4502/content/an-scf-sandbox/en/play.html](http://localhost:4502/content/an-scf-sandbox/en/play.html)

![chlimage_1-226](assets/chlimage_1-226.png)

## Spara ditt arbete hittills {#saving-your-work-so-far}

Nu finns det en minimalistisk sandlåda, och det kan vara värt att spara som ett paket så att du, när du spelar upp, kan aktivera servern om din databas blir skadad och du vill börja om, stänga av servern, byta namn på eller ta bort mappen crx-quickstart/, aktivera servern, ladda upp och installera det här sparade paketet och inte behöver upprepa dessa mest grundläggande steg.

Paketet finns i självstudiekursen [Skapa en exempelsida](create-sample-page.md) för dem som inte vill vänta på att bara hoppa in och börja spela upp!..

Så här skapar du ett paket:


* Klicka **[!UICONTROL CRXDE Lite]** på [paketikonen](http://localhost:4502/crx/packmgr/)
* Klicka på **[!UICONTROL Create Package]**

   * Paketnamn: `an-scf-sandbox-minimal-pkg`
   * Version: `0.1`
   * Grupp: &lt;lämna som standard>
   * Klicka på **[!UICONTROL OK]**

* Klicka på **[!UICONTROL Edit]**

   * Välj **[!UICONTROL Filters]** flik

      * Klicka på **[!UICONTROL Add filter]**
      * Rotsökväg: &lt;bläddra till `/apps/an-scf-sandbox`>
      * Klicka på **[!UICONTROL Done]**
      * Klicka på **[!UICONTROL Add filter]**
      * Rotsökväg: &lt;bläddra till `/etc/designs/an-scf-sandbox`>
      * Klicka på **[!UICONTROL Done]**
      * Klicka på **[!UICONTROL Add filter]**
      * Rotsökväg: &lt;bläddra till `/content/an-scf-sandbox`>
      * Klicka på **[!UICONTROL Done]**
   * Klicka på **[!UICONTROL Save]**


* Klicka på **[!UICONTROL Build]**

Nu kan du välja **[!UICONTROL Download]** att spara den på disk och **[!UICONTROL Upload Package]** någon annanstans, samt välja **[!UICONTROL More > Replicate]** för att överföra sandlådan till en lokal publiceringsinstans för att utöka sandlådans sfär.
