---
title: Konfigurera kontomiljön
seo-title: Configuring your account environment
description: AEM ger dig möjlighet att konfigurera ditt konto och vissa aspekter av författarmiljön
seo-description: AEM provides you with the capability to configure your account and certain aspects of the author environment
uuid: 01e76771-9ac8-4919-9e50-0a63826177d1
contentOwner: Chris Bohnert
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: introduction
content-type: reference
discoiquuid: 6afbc889-c613-40e6-8a25-1570dff32d60
exl-id: f620e85e-8c77-41a3-a238-9b93c819909d
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '517'
ht-degree: 1%

---

# Konfigurera kontomiljön{#configuring-your-account-environment}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

AEM ger dig möjlighet att konfigurera ditt konto och vissa aspekter av författarmiljön.

Använda [Användare](/help/sites-authoring/user-properties.md#user-settings) i [header](/help/sites-authoring/basic-handling.md#the-header) och associerade [Mina inställningar](#my-preferences) kan du ändra dina användaralternativ.

## Användarinställningar {#user-settings}

The **Användare** dialogrutan ger dig tillgång till:

* Personifiera som

   * Med [Personifiera som](/help/sites-administering/security.md#impersonating-another-user) funktioner som en användare kan arbeta för en annan användares räkning.

* Profil

   * En praktisk länk till [användarinställningar](/help/sites-administering/security.md))

* [Mina inställningar](/help/sites-authoring/user-properties.md#my-preferences)

   * Ange olika inställningar som är unika för din användare

![screen_shot_2018-03-20at103808](assets/screen_shot_2018-03-20at103808.png)

## Mina inställningar {#my-preferences}

The **Mina inställningar** öppnas via [Användare](/help/sites-authoring/user-properties.md#user-settings) i sidhuvudet.

Varje användare kan ange vissa egenskaper för sig själv.

![screen_shot_2018-03-20at102118](assets/screen_shot_2018-03-20at102118.png)

* **Språk**

   Detta definierar vilket språk som ska användas för redigeringsmiljöns användargränssnitt. Välj önskat språk i listan.

   Den här konfigurationen används även för det klassiska användargränssnittet.

* **Fönsterhantering**

   Detta definierar beteendet för att öppna fönster. Välj något av följande:

   * **Flera fönster** (Standard)

      * Sidorna öppnas i ett nytt fönster.
   * **Ett fönster**

      * Sidorna öppnas i det aktuella fönstret.


* **Visa skrivbordsåtgärder för Assets**

   Det här alternativet kräver AEM datorprogram.

* **Anteckningsfärg**

   Detta definierar den standardfärg som används när anteckningar görs.

   * Klicka på färgblocket för att öppna väljaren för färgrutor och markera en färg.
   * Du kan också ange hexkoden för önskad färg i fältet.

* **Relativ datumpresentation**

   För att förbättra läsbarheten kommer AEM att återge datum inom de senaste sju dagarna som relativa datum (t.ex. för tre dagar sedan) och äldre datum som exakta datum (t.ex. den 20 mars 2017).

   Det här alternativet definierar hur datum i systemet visas. Följande alternativ är tillgängliga:

   * **Visa alltid exakt datum**: Det exakta datumet visas alltid (aldrig ett relativt datum).
   * **1 dag**: Det relativa datumet visas för datum inom en dag, annars visas ett exakt datum.
   * **7 dagar (standard)**: Det relativa datumet visas för datum inom sju dagar, i annat fall visas ett exakt datum.
   * **1 månad**: Det relativa datumet visas för datum inom en månad, annars visas ett exakt datum.
   * **1 år**: Det relativa datumet visas för datum inom ett år, annars visas ett exakt datum.
   * **Visa alltid relativt datum**: Exakta datum visas aldrig och endast relativa datum visas.

* **Aktivera kortkommandon**

   AEM stöder ett antal kortkommandon som gör redigeringen effektivare.

   * [Kortkommandon för att redigera sidor](/help/sites-authoring/page-authoring-keyboard-shortcuts.md)
   * [Kortkommandon för konsoler](/help/sites-authoring/keyboard-shortcuts.md)

   Det här alternativet aktiverar kortkommandon. Som standard är de aktiverade, men kan inaktiveras om en användare har vissa tillgänglighetskrav.

* **Använd klassisk redigeringsmiljö**

   Det här alternativet aktiverar [klassiskt användargränssnitt](/help/sites-classic-ui-authoring/home.md)-baserad framtagning av sidor. Standardgränssnittet används som standard.

* **Aktivera startsidan för resurser**

   Det här alternativet är endast tillgängligt om systemadministratören har aktiverat Assets Home Page Experience för hela organisationen.
