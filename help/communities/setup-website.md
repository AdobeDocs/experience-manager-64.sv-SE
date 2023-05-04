---
title: Konfigurera webbplatsstruktur
seo-title: Setup Website Structure
description: Konfigurera kataloger
seo-description: Set up directories
uuid: a31edcd5-dab8-4a42-953b-1d076c2182b2
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: d18c0ece-4c4f-499c-ac94-a9aaa7f883c4
exl-id: 6d2226da-f691-4e8b-9494-a25e1c3d4b85
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 2%

---

# Konfigurera webbplatsstruktur {#setup-website-structure}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Instruktionerna nedan beskriver mapparna som ska skapas på följande platser när du konfigurerar webbplatsen:

* `/apps/an-scf-sandbox`
Här finns anpassade program och mallar

* `/etc/designs/an-scf-sandbox`
Här finns nedladdningsbara designelement

* `/content/an-scf-sandbox`
Det är här som de hämtningsbara webbsidorna finns

Koden i den här självstudien är beroende av att huvudmappnamnet är samma för programmet, designen och innehållet. Om du väljer något annat namn för webbplatsen ska du alltid ersätta `an-scf-sandbox` med det namn du har valt.

>[!NOTE]
>
>Om namn:
>
>* Namnen i CRXDE är nodnamn som utgör sökvägen till adresserbart innehåll
>* Nodnamn kan innehålla mellanslag, men när de används i en URI måste utrymmet kodas antingen som %20 eller +
>* Nodnamn kan innehålla bindestreck och understreck, men de måste kodas när de refereras som ett paketnamn i en Java-fil. Både bindestreck och understreck escape-konverteras med understreck följt av deras unicode-värde:
   >
   >   * bindestreck blir &#39;_002d&#39;
   >   * understreck blir &#39;_005f&#39;


## Konfigurera programkatalogen (/apps) {#setup-the-application-directory-apps}

Katalogen /apps i databasen innehåller koden som implementerar beteendet och återgivningen av de sidor som hanteras från katalogen /content.

Katalogen /apps är skyddad och inte allmänt tillgänglig, vilket är katalogerna /content och /etc/designs.

1. Skapa `/apps/an-scf-sandbox` mapp.

   Använda **[!UICONTROL CRXDE Lite]**, i utforskarfönstret

   1. Välj `/apps` mapp
   1. Högerklicka **[!UICONTROL Create]**... eller dra nedåt **[!UICONTROL Create...]** meny
   1. Välj **[!UICONTROL Create Folder...]** .
   1. I **[!UICONTROL Create Folder]** dialogruta, ange `an-scf-sandbox`
   1. Klicka på **[!UICONTROL OK]**

1. Skapa **[!UICONTROL components]** undermapp.

   1. Välj `/apps/an-scf-sandbox` mapp
   1. Klicka på **[!UICONTROL Create > Create Folder]**
   1. I **[!UICONTROL Create Folder]** dialogruta, ange **[!UICONTROL components]**
   1. Klicka på **[!UICONTROL OK]**

1. Skapa **[!UICONTROL templates]** undermapp.

   1. Välj `/apps/an-scf-sandbox` mapp
   1. Klicka på **[!UICONTROL Create > Create Folder]**
   1. I **[!UICONTROL Create Folder]** dialogruta, ange **[!UICONTROL templates]**
   1. Klicka på **[!UICONTROL OK]**
   1. Markera igen `/apps/an-scf-sandbox`
   1. Välj **[!UICONTROL Save All]**

   Spara ofta, precis som med andra redigeringsprocesser. Om du får problem med att ange data kan det bero på att tidsgränsen för inloggningen har överskridits eller på att du måste spara tidigare redigeringar.

1. Strukturen i utforskarpanelen i CRXDE Lite bör nu se ut ungefär så här:

   ![chlimage_1-44](assets/chlimage_1-44.png)

## Konfigurera designkatalogen (/etc/designs) {#setup-the-design-directory-etc-designs}

Katalogen /etc/designs innehåller de bilder, skript och formatmallar som ska hämtas tillsammans med sidinnehållet.

1. Om du vill använda verktyget Designer i det klassiska användargränssnittet går du till [https://&lt;server>:&lt;port>/miscadmin](http://localhost:4502/miscadmin).

   Obs! Om du använder CRXDE Lite för att skapa en nod av typen `cq:Page`, ställs inte åtkomstkontroll och replikering in på standardinställningar för en sida.

1. I rutan Utforskaren väljer du **[!UICONTROL Designs]** mapp och klicka sedan på **[!UICONTROL New > New Page]**.

   Ange:

   * Titel: **En SCF-sandlåda**
   * Namn: **an-scf-sandbox**
   * Välj **Designsidmall**

   Klicka på **[!UICONTROL Create]**

   ![chlimage_1-45](assets/chlimage_1-45.png)

1. Uppdatera utforskarfönstret om mappen &quot;An SCF Sandbox&quot; inte visas.

1. Gå tillbaka till CRXDE Lite (http:// localhost:4502/crx/de) och expandera /etc/designs för att se noden med namnet&quot;an-scf-sandbox&quot;.

   I den nedre högra rutan av CRXDE kan du visa fliken Egenskaper, fliken Åtkomstkontroll och fliken Replikering för att se vad som har definierats med hjälp av designsidmallen.

   ![chlimage_1-46](assets/chlimage_1-46.png)

## Konfigurera innehållskatalogen (/content) {#setup-the-content-directory-content}

Katalogen /content i databasen är den plats där webbplatsinnehållet finns. Sökvägarna under /content utgör sökvägarna till webbadressen för webbläsarbegäranden.

*Efter* den [sidmall](initial-app.md#createthepagetemplate) skapas som en del av det inledande programmet, kan det inledande sidinnehållet skapas baserat på mallen.... [**Mama**](initial-app.md)
