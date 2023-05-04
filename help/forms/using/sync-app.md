---
title: Synkroniserar appen
seo-title: Synchronizing the app
description: Synkronisera AEM Forms-appen på din mobila enhet med AEM Forms-servern.
seo-description: Synchronize the AEM Forms app on your mobile device with the AEM Forms server.
uuid: 7e1526e1-13bd-498a-a265-cd4f2d05ccdd
contentOwner: robhagat
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: dae1ce32-702e-4cf0-b3c6-976551208d09
exl-id: b5681fe5-69ba-4fc0-95e3-6ffdcdd95382
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 0%

---

# Synkroniserar appen {#synchronizing-the-app}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

## Synkroniserar appen {#synchronizing-the-app-1}

Formulären i din app hämtas från AEM Forms-servern. Formulären hämtas på flikarna Åtgärder och Forms. Utkast som skapas från formulär hämtas på fliken Utkast och utkast som skapas från uppgifter hämtas på fliken Åtgärder. För ett fristående formulär på OSGi-server hämtas formulär och utkast på flikarna Forms respektive Draft.

När du fyller i och skickar ett formulär överförs formuläret direkt till AEM Forms-servern om appen är online. Formulären hämtas från servern när appen synkroniseras. Utkasten synkroniseras emellertid direkt med servern om appen är online.

När du är online med AEM Forms-servern synkroniseras ditt program som standard var 15:e minut. Du kan dock ändra synkroniseringsfrekvensen. Du kan också när som helst synkronisera appen manuellt.

**Synkronisera appen manuellt**

Tryck på knappen Synkronisera ![sync-app](assets/sync-app.png) längst ned till höger på startskärmen.

**Ändra synkroniseringsfrekvensen**

1. Om du vill gå till inställningsskärmen trycker du på menyknappen längst upp till vänster på hemskärmen och sedan på **Inställningar**.
1. Tryck på fliken Allmänt på skärmen Inställningar.

   ![Inställningen för synkroniseringsfrekvens i fönstret Allmänna inställningar](assets/gen-settings-1.png)

1. Tryck på värdet till höger om synkroniseringsfrekvensen i alternativet Synkroniseringsfrekvens.
1. Välj den nya synkroniseringsfrekvensen i listrutan.

### Tekniska specifikationer {#technical-specifications}

* Den viktigaste logiken för att skicka offlineappdata till AEM Forms-servern finns i runtime/offline/util/offline.js.
* I .js-filen skickar anropet till funktionen processOfflineSubmitSavedTasks(...) de sparade/skickade uppgifterna till servern. Den hanterar även fel och konflikter i synkroniseringsprocessen. Om överföringen av en uppgift misslyckas markeras aktiviteten i programmet som misslyckad. Dessutom finns uppgiften kvar i Utkorgen.
* Funktionerna syncSubowedTask() och syncSavedTask() utför åtgärder på enskilda uppgifter.
* Anropet till funktionen processOfflineSubmitSavedTasks() initieras av uppgiftslistkomponenten efter att en användare har valt att synkronisera offlineläget med servern eller en automatisk synkronisering av bakgrundstråden.
