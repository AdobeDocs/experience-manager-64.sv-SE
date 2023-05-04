---
title: Skapar kapslade grupper
seo-title: Authoring Nested Groups
description: Skapa kapslade grupper
seo-description: Create nested groups
uuid: b478454a-24c6-4e1c-a6e0-afeb1bc4992c
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: introduction
content-type: reference
discoiquuid: 955a1876-4882-4926-82e9-846bc8bb332c
exl-id: 87be7ffe-d937-4e85-8d90-5b7c356f0876
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 2%

---

# Skapar kapslade grupper {#authoring-nested-groups}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Skapar grupper på författare {#creating-groups-on-author}

Från global navigering

* Välj **[!UICONTROL Communities > Sites]**
* Välj **[!UICONTROL engage folder]** för att öppna den
* Välj kort för **[!UICONTROL Getting Started Tutorial]**  Engelsk webbplats
   * Välj kortbilden
   * Gör *not* välj en ikon

Resultatet är att nå [Gruppkonsol](groups.md):

![chlimage_1-53](assets/chlimage_1-53.png)

Gruppfunktionen visas som en mapp där instanser av grupper skapas. Markera mappen Grupper för att öppna den. Gruppen som skapades vid publicering visas.

![chlimage_1-54](assets/chlimage_1-54.png)

## Skapa huvudkonst {#create-main-arts-group}

Den här gruppen kan skapas eftersom webbplatsstrukturen för interaktion innehåller en gruppfunktion. Konfigurationen av funktionen i platsens `Reference Template` Som standard tillåts val av aktiverade gruppmallar. Den mall som väljs för den nya gruppen blir `Reference Group`.

De här konsolerna liknar konsolen Webbplatser i Communities.

* Välj **[!UICONTROL Create Group]**
* `1 Community Group Template`:
   * Gruppnamn: Konstnärliga
   * Beskrivning av communitygrupp: En överordnad grupp för olika konstnärliga grupper.
   * Rotgrupp: *lämna som standard*
   * Fler tillgängliga språk för communitygrupper:använd listrutan för att välja tillgängliga språk för communitygrupper. Menyn innehåller alla språk som den överordnade communitywebbplatsen skapas i. Användarna kan välja mellan dessa språk för att skapa grupper i flera språkområden i det här steget. Samma grupp skapas på flera angivna språk i gruppkonsolen för respektive communityplats.
   * Gruppnamn: konst
   * Mall: dra nedåt för att välja `Reference Group`
   * Välj `Next`

      ![parenttonestedgrupp](assets/parenttonestedgroup.png)

Fortsätt genom de andra panelerna med följande inställningar:

* **2 Design**
   * Du kan ändra designen eller tillåta att den överordnade platsens design används som standard
   * Välj **[!UICONTROL Next]**
* **3 inställningar**
   * **Moderering**
      * Lämna tom (ärv från överordnad plats)
   * **medlemskap**
      * använd som standard `Optional Membership`
   * **Miniatyrbild**
      * `optional`
   * Välj `Next`
* Välj **[!UICONTROL Create]**

### Kapslade grupper inom konst {#nesting-groups-within-arts-group}

The `groups` bör nu innehålla två grupper (det kan vara nödvändigt att uppdatera sidan).

![createcommunitygroup](assets/createcommunitygroup.png)

#### Publicera grupp {#publish-group}

Innan du skapar grupper som är kapslade i `arts`grupp, hovra över `arts` och välj publiceringsikonen för att publicera det.

![chlimage_1-55](assets/chlimage_1-55.png)

Vänta på bekräftelse på att gruppen publicerades.

![chlimage_1-56](assets/chlimage_1-56.png)

The `arts` gruppen ska även innehålla `groups` men en som är tom och där nya grupper kan skapas. Navigera till gruppmappen för konst och skapa 3 kapslade grupper, där var och en har olika medlemsinställningar:

1. Visuell
   * Titel: `Visual Arts`
   * Namn: `visual`
   * Mall: `Reference Group`
   * Medlemskap: välj `Optional Membership`
En offentlig grupp, öppen för alla medlemmar
1. Revisoriska
   * Titel: `Auditory Arts`
   * Namn: `auditory`
   * Mall: `Reference Group`
   * Medlemskap: välj `Required Membership`
En öppen grupp, tillgänglig för medlemmar att gå med i

1. Historik

   * Titel: `Art History`
   * Namn: `history`
   * Mall: `Reference Group`
   * Medlemskap: välj `Restricted Membership`
En hemlig grupp, som bara visas för inbjudna medlemmar som exempel, bjuder in 
[demoanvändare](tutorials.md#demo-users) `emily.andrews@mailinator.com`

Uppdatera sidan om du vill se alla tre kapslade grupper (undergrupper).

Om det behövs kan du navigera till de kapslade grupperna från konsolen Webbplatser för Communities:

* Välj **[!UICONTROL engage folder]**
* Välj **[!UICONTROL Getting Started Tutorial]** kort
* Välj **[!UICONTROL Groups folder]**
* Välj **[!UICONTROL arts card]**
* Välj **[!UICONTROL Groups folder]**

![chlimage_1-57](assets/chlimage_1-57.png)

## Förlagskoncern {#publishing-groups}

![chlimage_1-58](assets/chlimage_1-58.png)

Efter publiceringen av den huvudsakliga communitywebbplatsen är det nödvändigt att

* Publicera varje grupp individuellt
   * Väntar på bekräftelse på att gruppen publicerades
* Publicera överordnad grupp innan någon grupp som är kapslad i publiceras
   * Alla grupper måste publiceras uppifrån och ned.

![chlimage_1-59](assets/chlimage_1-59.png)

## Experience on Publish {#experience-on-publish}

Det går att uppleva de olika grupperna när de loggas in, till exempel med [demoanvändare](tutorials.md#demo-users) används för

* Medlem i konst-/historikgrupp: emily.andrews@mailinator.com/lösenord
   * Den begränsade (hemliga) gruppen, konst/historik, visas
   * Kan se valfria (publika) grupper
   * Kan förena begränsade (öppna) grupper
* Gruppansvarig: aaron.mcdonald@mailinator.com/lösenord
   * Kan se valfria (publika) grupper
   * kan förena begränsade (öppna) grupper
   * Hittar inte hämtade (hemliga) grupper

Åtkomst till webbgrupper [Konsoler för medlemmar och grupper](members.md) om författare för att lägga till andra användare i olika medlemsgrupper som motsvarar communitygrupperna.
