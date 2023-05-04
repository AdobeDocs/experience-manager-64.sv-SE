---
title: Uppdaterar allmänna inställningar
seo-title: Updating general settings
description: Uppdatera inställningar för AEM Forms-appar som hemskärmen och hämta starpunkter och alternativ för bilagor
seo-description: Update AEM Forms app settings such as the Home screen and fetch Startpoints and attachments options
uuid: 234cd2da-2b47-4d60-82ed-68363d782632
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: a3aac07e-7d67-4a4f-b941-ff25a981092f
exl-id: 5ca6212f-d3c7-4239-beba-9a0bdac4b1ec
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 0%

---

# Uppdaterar allmänna inställningar {#updating-general-settings}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Med de allmänna inställningarna för AEM Forms-appen kan du ange inställningar som hämtningsbilagor, offlineläge, landningsskärm, standardkategori och frekvens för autosparande.

## Uppdatera de allmänna inställningarna i din app {#working-with-the-form}

När du synkroniserar din app med AEM Forms-servern hämtas alla formulär och definierade uppgifter till din mobila enhet.

Den färdiga AEM Forms-applösningen hämtar inte de bilagor som är kopplade till varje formulär när appen synkroniseras.

Ändra inställningar för hämtning, offlineläge, landningsskärm, automatiskt sparande och synkronisering på fliken Allmänt. Du kan ändra [Hemskärm](/help/forms/using/home-screen.md) av appen.

**Navigera till fliken Allmänt på inställningsskärmen**

1. Om du vill gå till inställningsskärmen trycker du på menyknappen längst upp till vänster på startskärmen och sedan på **Inställningar**.
1. Tryck på fliken Allmänt på skärmen Inställningar.

   ![Allmänna inställningar i AEM Forms-appen](assets/gen-settings-2.png)

   >[!NOTE]
   >
   >Alternativen kan visas på olika mobila enheter.

### Allmänna inställningar {#general-settings}

Du kan göra följande ändringar i inställningarna för ditt program.

* **Hämta uppgiftsbilagor**: Anger om de associerade bilagorna ska hämtas eller inte när varje uppgift hämtas till din app.

* **Offlineläge**: Om du vill aktivera eller inaktivera offlinetjänsten för AEM Forms-programmet. Se [Arbeta i offlineläge](/help/forms/using/work-offline-mode.md) för mer information.

* **Landing screen**: Ange startplats ([Hemskärm](/help/forms/using/home-screen.md)) för appen.

   Tillgängliga alternativ:

   * Forms
   * Uppgifter
   * Favoriter

* **Standardkategori**: Här kan du välja vilken formulärkategori som ska visas på hemskärmen. När du väljer Alla kan du se alla formulär på hemskärmen. Kategorierna fylls i baserat på de formulär som läses in i appen. Forms är tillgängligt i appen baserat på de formulärinställningar som har angetts på AEM Forms-servern.

* **Spara automatiskt, frekvens**: Ange frekvensen för [mobilapp sparar formulärdata](/help/forms/using/autosave-data-app.md) lokalt.

* **Synkroniseringsfrekvens**: Ange frekvensen för [mobilappen är synkroniserad](/help/forms/using/sync-app.md) med AEM Forms-servern i online-läge.

**Rensa lokala data**: Rensa databasen, inklusive inställningar och lokala data för alla användare och fillagring från enheten.

>[!NOTE]
>
>Om du rensar cachen loggas du omedelbart ut från appen.
>
>Du uppmanas dock att bekräfta rensningen av cachen.
