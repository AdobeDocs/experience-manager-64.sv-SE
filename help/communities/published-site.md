---
title: Upplev den publicerade webbplatsen
seo-title: Experience the Published Site
description: Bläddra till en publicerad webbplats
seo-description: Browse to a published site
uuid: f510224c-d991-4528-864d-44672138740c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 4dc54701-68b9-49dd-a212-b0b53330c1c0
exl-id: 8f716a59-1116-4855-baeb-3997de71b55f
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '1158'
ht-degree: 1%

---

# Upplev den publicerade webbplatsen {#experience-the-published-site}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Bläddra till Ny webbplats vid publicering {#browse-to-new-site-on-publish}

Nu när den nyligen skapade communitywebbplatsen har publicerats bläddrar du till den URL som visas när du skapar webbplatsen, men på publiceringsservern, t.ex.

* Författar-URL = http://localhost:4502/content/sites/engage/en.html
* Publicera URL = http://localhost:4503/content/sites/engage/en.html

För att minimera förvirring om vilken medlem som är inloggad på författare och publicera bör du använda olika webbläsare för varje instans.

Vid första ankomsten till den publicerade webbplatsen är besökaren vanligtvis inte redan inloggad och anonym.

## http://localhost:4503/content/sites/engage/en.html {#http-localhost-content-sites-engage-en-html}

![chlimage_1-311](assets/chlimage_1-311.png)

## Anonym webbplatsbesökare {#anonymous-site-visitor}

En anonym besökare ser följande i användargränssnittet:

* Webbplatsens namn. Det här är självstudiekursen Komma igång
* Ingen profillänk
* Ingen meddelandelänk
* Ingen meddelandelänk
* Sökfält
* Inloggningslänk
* Varumärkesbanderollen
* Menylänkar för de komponenter som ingår i referenswebbplatsmallen

Om du markerar olika länkar är de skrivskyddade.

## Förhindra anonym åtkomst på JCR {#prevent-anonymous-access-on-jcr}

En känd begränsning exponerar communityinnehållet för anonyma besökare via jcr-innehåll och json, även om **tillåta anonym åtkomst** är inaktiverat för webbplatsens innehåll. Det här beteendet kan dock styras med delningsbegränsningar som en tillfällig lösning.

Följ de här stegen för att skydda communityplatsens innehåll från anonyma användare genom jcr-innehåll och json:

1. I AEM Author-instansen går du till https://&lt;host>:&lt;port>/editor.html/content/site/&lt;sitename>.html.

   >[!NOTE]
   >
   >Gå inte till den lokaliserade webbplatsen.

1. Gå till **[!UICONTROL Page Properties]**.

   ![webbplatsautentisering](assets/site-authentication.png)

1. Gå till **[!UICONTROL Advanced]** -fliken.

   ![page-properties](assets/page-properties.png)

1. Aktivera **[!UICONTROL Authentication Requirement]**.
1. Lägg till inloggningssidans sökväg. Till exempel, `/content/......./GetStarted`.
1. Publicera sidan.

## Betrodd medlem i användargruppen {#trusted-community-member}

Den här upplevelsen förutsätter [Aaron McDonald](tutorials.md#demo-users) tilldelades rollerna för [community manager och moderator](create-site.md#roles). Om inte, gå tillbaka till författarmiljön till [ändra platsinställningarna](sites-console.md#modifying-site-properties) och väljer Aaron McDonald som både community manager och moderator.

I det övre högra hörnet väljer du `Log in`och signera med användarnamnet&quot;aaron.mcdonald@mailinator.com&quot; och lösenordet&quot;password&quot;. Lägg märke till möjligheten att logga in med Twitter eller Facebook.

![chlimage_1-312](assets/chlimage_1-312.png)

Observera att det finns ett nytt menyalternativ när du har loggat in. `Administration`, vilket framgår av att medlemmen fick rollen som moderator. Nu är det intressantare att välja olika länkar.

![chlimage_1-313](assets/chlimage_1-313.png)

Observera att kalendersidan är hemsidan eftersom den valda referensplatsmallen inkluderade kalenderfunktionen först, följt av aktivitetsströmfunktion, forumfunktion osv. Den här strukturen visas från [Webbplatsmall](sites.md#edit-site-template) konsol eller när webbplatsegenskaper ändras i redigeringsmiljön:

![chlimage_1-314](assets/chlimage_1-314.png)

>[!NOTE]
>
>Mer information om Communities-komponenter och -funktioner finns på
>
>* [Communities-komponenter](author-communities.md) (för författare)
>* [Grundläggande om komponenter, funktioner och funktioner](essentials.md) (för utvecklare)
>


## Formlänk {#forum-link}

Visa den grundläggande forumfunktionen genom att välja länken Forum.

Medlemmarna kan publicera ett nytt ämne eller följa ett ämne.

Besökarna kan visa inlägg och sortera dem på olika sätt.

![chlimage_1-315](assets/chlimage_1-315.png)

## Länken Grupper {#groups-link}

Eftersom Aaron är gruppadministratör kan Aron skapa en ny community-grupp genom att välja länken Grupper, välja en gruppmall, bild, om gruppen är öppen eller hemlig och bjuda in medlemmar.

Detta är ett exempel där en grupp skapas i publiceringsmiljön.

Grupper kan också skapas i författarmiljön och hanteras i communitywebbplatsen i författarmiljön (den [Konsol för communitygrupper](groups.md)). Erfarenheten av [skapa grupper vid författare](nested-groups.md) är nästa i den här självstudiekursen.

![chlimage_1-316](assets/chlimage_1-316.png)

Skapa en referensgrupp:

1. Välj **[!UICONTROL New Group]**
1. **[!UICONTROL Settings tab]**
   * Gruppnamn: `Sports`
   * Beskrivning: `A parent group for various sporting groups`
   * Grupp-URL-namn: `sports`
   * välj `Open Group` (tillåt alla community-medlemmar att delta genom att gå med)
1. **[!UICONTROL Template tab]**
   * Välj `Reference Group` (innehåller en gruppfunktion i sin struktur för att tillåta kapslade grupper)
1. Välj **[!UICONTROL Create Group]**

![chlimage_1-317](assets/chlimage_1-317.png)

När en ny grupp har skapats **välj den nya Sports-gruppen** för att skapa två grupper (kapslade) inuti. Eftersom en platsstruktur inte kan börja med gruppfunktionen måste du välja länken Grupper när du har öppnat gruppen Sport:

![chlimage_1-318](assets/chlimage_1-318.png)

Den andra uppsättningen länkar, med början `Blog`, tillhör den markerade gruppen, `Sports`grupp. Genom att välja sportar `Groups` kan du kapsla två grupper i gruppen Sport.

Som ett exempel lägger du till två n `ew groups.`

* En namngiven `Baseball`
   * Låt det vara som `Open Group` (obligatoriskt medlemskap)
   * På fliken Mallar väljer du `Conversational Group`
* En namngiven `Gymnastics`
   * Ändra inställningen till `Member Only Group` (begränsat medlemskap)
   * På fliken Mallar väljer du `Conversational Group`

**Meddelande**:

* En uppdatering av sidan kan behövas innan båda grupperna visas
* Den här mallen innehåller inte *gruppfunktionen, så det går inte att kapsla in grupper ytterligare
* På författaren [Gruppkonsol](groups.md) har ett tredje val - en `Public Group` (valfritt medlemskap)

När båda grupperna har skapats väljer du Baseball-gruppen, en öppen grupp, och lägger märke till dess länkar: `Discussions` `What's New` `Members`
Gruppens länkar visas under huvudplatsens länkar och ger följande resultat:

![chlimage_1-319](assets/chlimage_1-319.png)

Vid författare - med administratörsbehörighet går du till [Konsol för webbgrupper](members.md) och lägg till Weston McCall i `Community Engage Gymnastics <uid> Members` grupp.

Fortsätt publicera, logga ut som Aaron McDonald och visa grupperna i Sports Group som en anonym besökare:

* Från startsidan
* Välj `Groups`link
* Välj `Sports`link
* Välj sport `Groups`link

Bara Baseball-gruppen syns.

Logga in som Weston McCall (weston.mccall@dodgit.com / lösenord) och navigera till samma plats. Observera att Weston kan `Join` öppna `Baseball` grupp och antingen `enter or Leave` private `Gymnastics`grupp.

![chlimage_1-320](assets/chlimage_1-320.png)

## Länk till webbsida {#web-page-link}

Visa den grundläggande webbsidan som finns på webbplatsen genom att välja länken Webbsida. Standardverktygen AEM kan användas för att lägga till innehåll på den här sidan i författarmiljön.

Till exempel, gå till **författare** -instans, öppna `engage` i [Konsolen Webbplatser i Communities](sites-console.md)väljer du **Öppna webbplats** om du vill öppna redigeringsläget. Välj sedan förhandsvisningsläget för att välja `Web Page`och välj sedan redigeringsläge för att lägga till titel- och textkomponenter. Publicera sedan om antingen bara sidan eller hela webbplatsen.

![chlimage_1-321](assets/chlimage_1-321.png)

## Administrationslänk {#administration-link}

När communitymedlemmen har modereringsbehörighet visas administrationslänken och om du väljer den visas det communityinnehåll som publicerats och det kan [modererad](moderate-ugc.md) på ett sätt som liknar [modereringskonsol](moderation.md) i redigeringsmiljön.

Använd webbläsarens bakåtknapp för att gå tillbaka till den publicerade webbplatsen. De flesta konsoler är inte tillgängliga via global navigering i publiceringsmiljön.

![chlimage_1-322](assets/chlimage_1-322.png)

## Självregistrering {#self-registration}

När du har loggat ut kan du skapa en ny användarregistrering.

* Välj `Log In`
* Välj `Sign up for a new account`

![chlimage_1-323](assets/chlimage_1-323.png) ![chlimage_1-324](assets/chlimage_1-324.png)

Som standard är e-postadressen inloggnings-ID. Om alternativet inte är markerat kan besökaren ange ett eget inloggnings-ID (användarnamn). Användarnamnet måste vara unikt i publiceringsmiljön.

När du har angett användarens namn, e-postadress och lösenord väljer du `Sign Up`skapar användaren och aktiverar den för signering.

När du har loggat in visas den första sidan `Profile`sida, som de kan personalisera.

![chlimage_1-325](assets/chlimage_1-325.png)

Om medlemmen glömmer sitt inloggnings-ID är det möjligt att återställa med sin e-postadress.

![chlimage_1-326](assets/chlimage_1-326.png)
