---
title: Redigera sidegenskaper
seo-title: Editing Page Properties
description: Definiera de egenskaper som krävs för en sida
seo-description: Define the required properties for a page
uuid: c0386cd6-ca01-4741-b8c8-36edb66e50ef
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: page-authoring
content-type: reference
discoiquuid: 8e85ea7f-80ea-43b6-a67c-366852ef86ce
exl-id: b0e579a4-f5bd-4a55-a003-0496224bc940
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1825'
ht-degree: 3%

---

# Redigera sidegenskaper{#editing-page-properties}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan definiera de egenskaper som krävs för en sida. Dessa kan variera beroende på sidans beskaffenhet. Vissa sidor kan till exempel vara kopplade till en live-kopia medan andra inte är det och live-kopieringsinformationen är tillgänglig efter behov.

## Sidegenskaper {#page-properties}

Egenskaperna fördelas på flera flikar.

### Grundläggande {#basic}

* **Titel**

   Sidans rubrik visas på olika platser. Till exempel **Webbplatser** tabblista och **Webbplatser** kort-/listvyer.

   Detta är ett obligatoriskt fält.

* **Taggar**

   Här kan du lägga till eller ta bort taggar från sidan genom att uppdatera listan i valrutan:

   * När du har valt en tagg visas den under markeringsrutan. Du kan ta bort en tagg från den här listan med hjälp av x.
   * Du kan ange en helt ny tagg genom att skriva namnet i en tom markeringsruta.

      * Den nya taggen skapas när du trycker på Retur.
      * Den nya taggen visas sedan med en liten stjärna till höger som anger att det är en ny tagg.
   * Med den nedrullningsbara menyn kan du välja bland befintliga taggar.
   * Ett x-tecken visas när du för musen över en taggpost i markeringsrutan, som kan användas för att ta bort taggen för den här sidan.

   Mer information om taggar finns i [Använda taggar](/help/sites-authoring/tags.md).

* **Dölj i navigering**

   Anger om sidan visas eller döljs i sidnavigeringen på den slutliga platsen.

* **Varumärke**

   Använd en enhetlig varumärkesidentitet på alla sidor genom att lägga till en instruktionsmarginal till varje sidrubrik. Den här funktionen kräver att du använder Page Component från version 2.14.0 eller senare av [Kärnkomponenter.](https://experienceleague.adobe.com/docs/experience-manager-core-components/using/introduction.html)

   * **Åsidosätt** - Markera för att definiera instruktionsmarginalen för varumärket på den här sidan.
      * Värdet ärvs av alla underordnade sidor såvida de inte också har sina **Åsidosätt** värden anges.
   * **Åsidosätt värde** - Texten i instruktionsmarginalen som ska läggas till i sidrubriken.
      * Värdet läggs till i sidrubriken efter ett lodstreck som &quot;Cycling Tuscany&quot; | Alltid redo för WKND&quot;

* **Sidrubrik**

   En rubrik som ska användas på sidan. Används vanligtvis av titelkomponenter. Om den är tom **Titel** kommer att användas.

* **Navigeringsrubrik**

   Du kan ange en separat rubrik som ska användas i navigeringen (om du till exempel vill ha något mer koncist). Om den är tom visas **Titel** kommer att användas.

* **Underrubrik**

   En underrubrik som ska användas på sidan.

* **Beskrivning**

   Din beskrivning av sidan, dess syfte eller annan information som du vill lägga till.

* **I tid**

   Det datum och den tidpunkt då den publicerade sidan ska aktiveras. När den publiceras kommer den här sidan att vara vilande tills den angivna tiden.

   Lämna dessa fält tomma för sidor som du vill publicera omedelbart (det normala scenariot).

* **Fråntid**

   Den tidpunkt då den publicerade sidan inaktiveras.

   Lämna dessa fält tomma igen så att du kan agera direkt.

* **Vanity URL**

   Gör att du kan ange en egen URL för den här sidan, vilket kan göra att du kan ha en kortare och/eller mer uttrycksfull URL.

   Om Vanity-URL:en till exempel är inställd på w `elcome`till den sida som identifieras av sökvägen / `v1.0/startpage`för webbplatsen h `ttp://example.com,` sedan h `ttp://example.com/welcome`skulle vara den vanligaste URL:en för h `ttp://example.com/content/v1.0/startpage`

   >[!CAUTION]
   >
   >Alternativa URL:er:
   >
   >* Måste vara unikt så du bör vara försiktig med att värdet inte redan används av en annan sida.
   >* Använd inte regex-mönster.


* **URL för omdirigering**

   Anger om du vill att sidan ska använda fågel-URL:en.

### Avancerat {#advanced}

* **Språk**

   Sidspråket.

* **Omdirigering**

   Ange den sida som den här sidan automatiskt ska omdirigeras till.

* **Design**

   Ange [design](/help/sites-developing/designer.md) som ska användas för den här sidan.

* **Alias**

   Ange ett alias som ska användas med den här sidan.

   * Om du till exempel definierar ett alias för `private` för sidan `/content/wknd/us/en/magazine/members-only`kan den här sidan också öppnas via `/content/wknd/us/en/magazine/private`.
   * När du skapar ett alias anges `sling:alias` på sidnoden, vilket bara påverkar resursen, inte databassökvägen.
   * Sidor som används av alias i redigeraren kan inte publiceras. [Publiceringsalternativ](/help/sites-authoring/publishing-pages.md) i redigeraren är bara tillgängliga för sidor som du kommer åt via de faktiska sökvägarna.
   * Mer information finns i [Lokaliserade sidnamn under SEO och URL Management Best Practices](/help/managing/seo-and-url-management.md#localized-page-names)

* **Tillåtna mallar**

   [Definiera listan med mallar som ska vara tillgängliga](/help/sites-authoring/templates.md#enabling-and-allowing-a-template-template-author) inom denna underavdelning.

* **Autentiseringskrav**

   Aktiverar (eller inaktiverar) användning av autentisering för att få åtkomst till sidan.

   Kravet på autentisering kan anges här tillsammans med en angiven inloggningssida. Stängda användargrupper för sidan definieras på **[Behörigheter](/help/sites-authoring/editing-page-properties.md#permissions)** -fliken.

   >[!CAUTION]
   >
   >The **[Behörigheter](/help/sites-authoring/editing-page-properties.md#permissions)** -fliken tillåter redigering av CUG-konfigurationer baserat på närvaron av `granite:AuthenticationRequired` blanda. Om sidbehörigheter konfigureras med inaktuella CUG-konfigurationer, baserat på förekomsten av egenskapen cq:cugEnabled, visas ett varningsmeddelande under **Autentiseringskrav** och alternativet går inte att redigera, inte heller [Behörigheter](/help/sites-authoring/editing-page-properties.md#permissions) vara redigerbar.
   >
   >
   >I så fall måste CUG-behörigheterna redigeras i [klassiskt användargränssnitt](/help/sites-classic-ui-authoring/classic-page-author-edit-page-properties.md).

* **Inloggningssida**

   Den sida som ska användas för inloggning.

* **Exportera konfiguration**

   Ange en exportkonfiguration.

### Miniatyrbild {#thumbnail}

1. **Sidminiatyr**

   Visar sidminiatyrbilden. Du kan:

   * **Generera förhandsgranskning**

      Generera en förhandsgranskning av sidan som ska användas som miniatyrbild.

   * **Överför bild**

      Överför en bild som ska användas som miniatyrbild.

### Sociala medier {#social-media}

* **Delning i sociala medier**

   Definierar de delningsalternativ som är tillgängliga på sidan. Visar de alternativ som är tillgängliga för [Dela kärnkomponent](https://helpx.adobe.com/experience-manager/core-components/using/sharing.html).

   * **Aktivera användardelning för Facebook**
   * **Aktivera användardelning för Pinterest**
   * **Önskad XF-variation**
Definiera variant av upplevelsefragment som används för att generera metadata för sidan

### Cloud Services {#cloud-services}

* **Cloud Services**

   Definiera egenskaper för [molntjänster](/help/sites-developing/extending-cloud-config.md).

### Personanpassning {#personalization}

* **Personanpassning**

   Välj en [Varumärke som anger ett omfång för målanpassning](/help/sites-authoring/personalization.md).

### Behörigheter {#permissions}

* **Behörigheter**

   På den här fliken kan du:

   * [Lägg till behörigheter](/help/sites-administering/user-group-ac-admin.md)
   * [Redigera stängd användargrupp](/help/sites-administering/cug.md#applying-your-closed-user-group-to-content-pages)
   * Visa [Effektiva behörigheter](/help/sites-administering/user-group-ac-admin.md)

   >[!CAUTION]
   >
   >The **Behörigheter** -fliken tillåter redigering av CUG-konfigurationer baserat på närvaron av `granite:AuthenticationRequired` blanda. Om sidbehörigheter konfigureras med hjälp av inaktuella CUG-konfigurationer, baserat på förekomsten av `cq:cugEnabled` -egenskapen visas ett varningsmeddelande och CUG-behörigheterna kan inte redigeras. Autentiseringskravet på [Avancerat](/help/sites-authoring/editing-page-properties.md#advanced) kan redigeras.
   >
   >
   >I så fall måste CUG-behörigheterna redigeras i [klassiskt användargränssnitt](/help/sites-classic-ui-authoring/classic-page-author-edit-page-properties.md).

   >[!NOTE]
   >
   >På fliken Behörigheter går det inte att skapa tomma CUG-grupper, vilket kan vara ett enkelt sätt att neka alla användare åtkomst. För att kunna göra detta måste Utforskaren för CRX användas. Se dokumentet [Behörighetsadministration för användare, grupp och åtkomst](/help/sites-administering/user-group-ac-admin.md) för mer information.

### Blueprint {#blueprint}

* **Blueprint**

   Definiera egenskaper för en designsida i [hantering av flera webbplatser](/help/sites-administering/msm.md). Styr under vilka omständigheter ändringar ska spridas till Live Copy.

### Live Copy {#live-copy}

* **Livecopy**

   Definiera egenskaper för en Live Copy-sida i [hantering av flera webbplatser](/help/sites-administering/msm.md). Styr under vilka omständigheter ändringar ska spridas från utkast.

### Webbplatsstruktur {#site-structure}

* Tillhandahålla länkar till sidor som innehåller funktioner för hela webbplatsen, som **Registreringssida**, **Offlinesida**, bland annat.

## Redigera sidegenskaper {#editing-page-properties-2}

Du kan definiera sidegenskaper:

* Från **Webbplatser** konsol:

   * [Skapa en ny sida](/help/sites-authoring/managing-pages.md#creating-a-new-page) (en delmängd av egenskaperna)
   * Klicka eller peka **Egenskaper**

      * För en enstaka sida
      * För flera sidor (endast en deluppsättning av egenskaperna är tillgängliga för redigering av en masse)

* Från sidredigeraren:

   * Med **Sidinformation** (och sedan **Öppna egenskaper**)

### Från webbplatskonsolen - en sida {#from-the-sites-console-single-page}

Klicka eller peka **Egenskaper** för att definiera sidegenskaperna:

1. Använda **Webbplatser** navigera till platsen för sidan som du vill visa och redigera egenskaper för.

1. Välj **Egenskaper** för den önskade sidan med något av följande alternativ:

   * [Snabbåtgärder](/help/sites-authoring/basic-handling.md#quick-actions)
   * [Markeringsläge](/help/sites-authoring/basic-handling.md#viewing-and-selecting-resources)

   Sidegenskaperna visas med rätt flikar.

1. Visa eller redigera egenskaperna efter behov.

1. Använd sedan **Spara** för att spara uppdateringar följt av **Stäng** för att återgå till konsolen.

### När en sida redigeras {#when-editing-a-page}

När du redigerar en sida kan du använda **Sidinformation** för att definiera sidegenskaperna:

1. Öppna sidan som du vill redigera egenskaper för.

1. Välj **Sidinformation** -ikon för att öppna markeringsmenyn:

   ![screen_shot_2018-03-22at095740](assets/screen_shot_2018-03-22at095740.png)

1. Välj **Öppna egenskaper** och en dialogruta öppnas där du kan redigera egenskaperna, sorterade efter lämplig flik. Följande knappar finns också till höger om verktygsfältet:

   * **Avbryt**
   * **Spara och stäng**

1. Använd **Spara och stäng** för att spara ändringarna.

### Från webbplatskonsolen - flera sidor {#from-the-sites-console-multiple-pages}

På **Sites**-konsolen kan du markera flera sidor och sedan använda **Visa egenskaper** för att visa och/eller redigera sidegenskaperna. Detta kallas massredigering av sidegenskaper.

>[!NOTE]
>
>Det finns även massredigering av egenskaper för Assets. Den är mycket lik, men skiljer sig på några punkter. Se [Redigera egenskaper för flera resurser](/help/assets/managing-multiple-assets.md) för mer information.
>
>Det finns också [Massredigerare](/help/sites-administering/bulk-editor.md), som gör att du kan söka efter innehåll från flera sidor med hjälp av GQL (Google Query Language) och sedan redigera innehållet direkt i gruppredigeraren innan du sparar ändringarna på originalsidorna.

Du kan välja flera sidor för massredigering på olika sätt, bland annat:

* När du bläddrar **Webbplatser** konsol
* Efter användning **Sök** för att hitta en uppsättning sidor

![screen_shot_2018-03-22at100039](assets/screen_shot_2018-03-22at100039.png)

När du har markerat sidorna och sedan klickat eller tryckt på **Egenskaper** kan bulkegenskaperna visas:

![screen_shot_2018-03-22at100114](assets/screen_shot_2018-03-22at100114.png)

Du kan bara redigera sidor som:

* Dela samma resurstyp
* Är inte en del av en livecopy

   * Om någon av sidorna finns i en live-kopia visas ett meddelande när egenskaperna öppnas.

När du har valt Massredigering kan du:

* **Visa**

   När du visar Sidegenskaper för flera sidor kan du se:

   * En lista över de sidor som påverkas

      * Du kan markera/avmarkera vid behov
   * Tabbar

      * På samma sätt som när du visar egenskaper för en enskild sida ordnas egenskaperna under flikar.
   * En deluppsättning med egenskaper

      * Egenskaper som är tillgängliga på alla markerade sidor och som uttryckligen har definierats som tillgängliga för massredigering visas.
      * Om du minskar sidmarkeringen till en sida visas alla egenskaper.
   * Vanliga egenskaper med ett gemensamt värde

      * Endast egenskaper med ett gemensamt värde visas i visningsläget.
      * När fältet har flera värden (till exempel Taggar) visas värden endast när *alla* är vanliga. Om bara vissa är vanliga visas de bara när du redigerar.

   När det inte finns några egenskaper med ett gemensamt värde visas ett meddelande.

* **Redigera**

   När du redigerar Sidegenskaper för flera sidor:

   * Du kan uppdatera värdena i de tillgängliga fälten.

      * De nya värdena tillämpas på alla markerade sidor när du markerar **Klar**.
      * När fältet har flera värden (till exempel Taggar) kan du antingen lägga till ett nytt värde eller ta bort ett gemensamt värde.
   * Fält som är gemensamma, men har olika värden på de olika sidorna, markeras med ett särskilt värde, t.ex. texten `<Mixed Entries>`. Du bör vara försiktig när du redigerar sådana fält för att förhindra dataförlust.


>[!NOTE]
>
>Sidkomponenten kan konfigureras för att ange de fält som är tillgängliga för massredigering. Se [Konfigurera sidan för massredigering av sidegenskaper](/help/sites-developing/bulk-editing.md).
