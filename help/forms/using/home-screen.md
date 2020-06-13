---
title: Hemskärm
seo-title: Hemskärm
description: Beskrivning av komponenterna i AEM Forms-appen - startsida
seo-description: Beskrivning av komponenterna i AEM Forms-appen - startsida
uuid: 7705b499-8b38-4c2e-abd8-6901cf268428
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: e4636b25-20a4-4326-82fb-f22f735e43c0
translation-type: tm+mt
source-git-commit: 79dcf6816e1156604c0c9279b727ea436ad1826a
workflow-type: tm+mt
source-wordcount: '347'
ht-degree: 0%

---


# Hemskärm {#home-screen}

När du loggar in på appen AEM Forms omdirigeras du till hemskärmen.

## Standardhemskärm {#default-home-screen}

Som standard visas alla formulär, inklusive startpunkter och uppgifter (om den anslutna servern är AEM Forms Workflow aktiverad) på startskärmen, tillsammans med tillhörande miniatyrbilder. Du kan ange miniatyrbilder på AEM Forms-servern.

Följande bild är kommenterad med utanrop till de viktigaste komponenterna på startskärmen.
![Startskärmen](assets/home-screen-1.png)för appen Formulär[Klicka för att förstora](assets/home-screen-1-1.png)

1. **Menyknapp**: Tryck på knappen **Meny** för att navigera till Åtgärder, Formulär, Utkorgen och Inställningar. Om din AEM Forms-app är ansluten till en AEM Forms JEE-server kan du se alternativet Åtgärder. Alternativet Uppgifter lagrar även utkast som skapats från uppgifter i en process. För AEM Forms OSGi-servrar är aktivitetsalternativet dolt. I Outbox lagras de sparade formulären och utkasten innan de synkroniseras med servern. Alla sparade formulär och utkast i Utkorgen överförs till AEM Forms-servern när appen [synkroniseras med servern](/help/forms/using/sync-app.md). Mer information om inställningar finns i [Uppdatera allmänna inställningar](/help/forms/using/update-general-settings.md).
1. **Uppgift eller formulär**: Tryck på uppgiften eller formuläret som du vill arbeta med.
1. **Vågrät ellips**: Anger att åtgärder är tillgängliga för formuläret. När du trycker på ellipsen visas de åtgärder och den som har skrivit beskrivningen. Alternativet **Ta bort utkast** och **fullständigt** visas när du trycker på ellipsen.
1. **Ikonen** Uppdatera: Tryck på uppdateringsikonen för att synkronisera din app med AEM Forms-servern.

## Anpassa hemskärmen {#customizing-the-home-screen}

![Allmänna inställningar](assets/gen-settings.png)

Du kan ändra programmets standardhemskärm antingen från programmets **[allmänna inställningar](/help/forms/using/update-general-settings.md)**eller från fliken **Inställningar**på HTML-arbetsytan.

Ändringen av inställningen för startskärmen i appen påverkar startskärmen för den inloggade användaren eller användaren på den aktuella mobila enheten.

Ändringen i HTML Workspace påverkar dock alla AEM Forms-appanvändare som är inloggade på AEM Forms-servern.

