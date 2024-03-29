---
title: Introduktion till [!DNL Adobe Experience Manager Assets]
description: Läs om vad som är digital resurshantering, användningsexempel och [!DNL Adobe Experience Manager Asset] erbjuder.
contentOwner: AG
feature: Asset Management
role: Leader,Architect,User
exl-id: 9292871d-3b10-49f8-ac1a-4770b4e44048
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '893'
ht-degree: 0%

---

# Om [!DNL Adobe Experience Manager Assets] som en DAM-lösning {#about-assets}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

[!DNL Assets] är ett DAM-verktyg (Digital Asset Management) som är en viktig del av [!DNL Experience Manager] och gör det möjligt att hantera och distribuera digitala resurser. Användare i en hel organisation kan hantera, lagra och få tillgång till många typer av digitalt material som bilder, videor, dokument, ljudklipp, 3D-filer och multimedia för användning på webben, i tryck och för digital distribution.

## Vad är Digital Asset Management? {#what-is-digital-asset-management}

[!DNL Assets] erbjuder företagsövergripande delning och distribution av en organisations viktigaste digitala resurser. Användare i en hel organisation kan lagra, hantera och komma åt digitala resurser som bilder, grafik, ljud, video och dokument via ett webbgränssnitt (eller en CIFS- eller WebDAV-mapp).

[!DNL Assets] kapacitet för [!DNL Experience Manager] gör följande:

* Lägg in och dela bilder, dokument, ljudfiler och videofiler i en mängd olika filformat.
* Hantera resurser genom att gruppera dem efter taggar, ljusbord eller stjärnor (dina favoriter). Lägg till anteckningar i resurser.
* Sök efter resurser genom att söka efter filnamn, den fullständiga texten i dokument och genom att söka efter datum, dokumenttyp och taggar.
* Lägg till eller redigera metadatainformation för resurser. Metadata versionshanteras automatiskt tillsammans med motsvarande resurs. Du kan importera eller exportera metadata för resurser.
* Utför bildredigeringsfunktioner som skalning och lägga till bildfilter. Importera och exportera flera digitala resurser samtidigt med en WebDAV- eller CIFS-mapp.
* Använd arbetsflöden och meddelanden för att möjliggöra gemensam bearbetning och hämtning av alla typer av resurser och hantera åtkomsträttigheter till resurser.

### [!DNL Experience Manager Assets] är integrerat med [!DNL Experience Manager Sites] {#aem-assets-fully-integrated-in-cq-wcm}

[!DNL Assets] helt integrerat med [!DNL Sites] och fungerar smidigt i alla situationer. När du t.ex. redigerar webbsidor [!DNL Sites] författare kan hitta och använda digitala resurser via Content Finder. Användargränssnittet i [!DNL Assets] är samma som [!DNL Sites]. Se [översikt över platser](/help/sites-authoring/qg-page-authoring.md) för fullständig information.

<!-- TBD: Update image for branding 

![screen_shot_2012-04-17at15946pm](assets/screen_shot_2012-04-17at15946pm.png) ![screen_shot_2012-04-17at20100pm](assets/screen_shot_2012-04-17at20100pm.png)

Assets managed within [!DNL Experience Manager] DAM can then be accessed via the content finder of WCM:

![screen_shot_2012-04-17at20214pm](assets/screen_shot_2012-04-17at20214pm.png) -->

### Digital Asset Management jämfört med Image-komponenten {#digital-asset-management-versus-image-component}

När du avgör om en bild ska placeras i DAM-databasen eller om bildkomponenten ska användas, bör du tänka på bildens livscykel:

* Om bilden har samma livscykel som sidan använder du bildkomponenten.
* Om bilden har en separat livscykel, till exempel om du använder bilden två gånger eller utanför WCM, ska du använda [!DNL Assets].

## Vad är digitala resurser? {#what-are-digital-assets}

En resurs är ett digitalt dokument, en bild, en video eller ett ljud (eller en del av ett) som kan ha flera återgivningar och kan ha underresurser (t.ex. lager i en Photoshop-fil, bilder i en PowerPoint-fil, sidor i en PDF-fil, filer i en ZIP-fil).

En resurs är i stort sett en binär resurs plus metadata plus återgivningar plus underresurser. Se [DAM Performance Guide](https://experienceleague.adobe.com/docs/experience-manager-64/assets/administer/performance-tuning-guidelines.html) för detaljerad information.

>[!CAUTION]
>
>Överföra och/eller redigera en stor mängd resurser (särskilt bilder) kan påverka prestandan för dina [!DNL Experience Manager] distribution.

### [!DNL Experience Manager Assets] terminologi {#aem-assets-terminology}

När du arbetar med digitala resurser i [!DNL Experience Manager]måste du förstå följande terminologi:

* **Samling**: En samling resurser, antingen baserat på fysisk plats (mapp), gemensamma egenskaper (sparad sökmapp) eller användarval (lightbox-mappar).

* **Metadata** [!DNL Assets] ha metadata, till exempel författare, förfallodatum, DRM-information (Digital Rights Management) och så vidare. Metadata är under åtkomstkontroll. [!DNL Assets] har stöd för följande vanliga metadatascheman:

   * Dublin Core: inklusive författare, beskrivning, datum, ämne och så vidare.
   * IPTC: inklusive händelse, modell, plats och så vidare.
   * WCM: inklusive sidegenskaper, [!UICONTROL On Time] och [!UICONTROL Off Time]och så vidare.

* **Taggning**: [!DNL Assets] kan taggas och klassificeras. Se [ordna resurser](/help/assets/organize-assets.md).

* **Återgivningar**: En återgivning är den binära representationen av en resurs. [!DNL Assets] har alltid en primär representation - den överförda filen. De kan ha valfritt antal ytterligare representationer som skapas, till exempel genom anpassade arbetsflödessteg eller när en resurs överförs. Återgivningar kan ha en annan storlek, med en annan upplösning, med en vattenstämpel eller någon annan förändrad egenskap.

* **Versioner**: Versionshantering skapar en ögonblicksbild av digitala resurser vid en viss tidpunkt. Du kan återställa resurser till tidigare versioner. Se [versionshantering in [!DNL Assets]](managing-assets-touch-ui.md#asset-versioning).

* **Deltillgångar**: Delresurser är resurser som utgör en resurs, till exempel lager i en [!DNL Adobe Photoshop] eller sidor i en PDF-fil. I [!DNL Assets]kan du hantera underresurser på samma sätt som du hanterar resurser.

### Så här arbetar du med digitala resurser {#how-to-work-with-assets}

Du utför en åtgärd på en resurs eller samling. Funktionsmakron kan skapa och ändra resurser, samlingar och återgivningar. Många av de grundläggande åtgärder du utför på resurser - överföra, ta bort, uppdatera, spara underresurser - utlöser förkonfigurerade arbetsflöden. Dessa är automatiskt påslagna [!DNL Assets] och beskrivs i detalj [!DNL Assets] mediehanterare.

De uppgifter du kan utföra med dessa förkonfigurerade arbetsflöden:

* Spara resursen i eller ta bort resursen från databasen.
* Extrahera och spara metadata för resursen; de enskilda metadataobjekten sparas som XMP.
* Generera återgivningar och miniatyrbilder för resursen. inklusive automatisk storleksändring och beskärning vid behov.
* Omkoda tillgången där det behövs. Video för mobil- och webbanvändning omkodas till exempel med 24 bildrutor per sekund, och video hämtas med 30 bildrutor per sekund. Ljud för mobil- och webbanvändning omkodas med 128 kbit/s, ljud för nedladdning med 192 kbit/s.

Du kan förstås även använda arbetsflöden manuellt. Se [Mediehanterare för resurser](media-handlers.md)för en lista med standardarbetsflöden.

## [!DNL Experience Manager Assets] och [!DNL Media Library] {#cq-dam-vs-cq-medialibrary}

Se [Resurser och Media Library](medialibrary.md) för information om skillnaderna.

>[!MORELIKETHIS]
>
>* [Videointroduktion - Experience Manager Assets som modern DAM](https://www.youtube.com/watch?v=PBwQqZgC-yo)

