---
title: Hemskärm
seo-title: Home screen
description: Beskrivning av komponenterna i startskärmen för AEM Forms-appen
seo-description: Description of the components of the AEM Forms app Home screen
uuid: 7705b499-8b38-4c2e-abd8-6901cf268428
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: e4636b25-20a4-4326-82fb-f22f735e43c0
exl-id: b8f515fd-7ab7-4237-9a35-2840f708e856
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 0%

---

# Hemskärm {#home-screen}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När du loggar in på AEM Forms omdirigeras du till hemskärmen.

## Standardhemskärm {#default-home-screen}

Som standard visas alla formulär, inklusive startpunkter och uppgifter, på startskärmen (om den anslutna servern är AEM Forms Workflow aktiverad) tillsammans med tillhörande miniatyrbilder. Du kan ange miniatyrbilder på AEM Forms-servern.

Följande bild är kommenterad med utanrop till de viktigaste komponenterna på startskärmen.
![Forms app - startskärm](assets/home-screen-1.png)
[Klicka för att förstora](assets/home-screen-1-1.png)

1. **Menyknapp**: Tryck på **Meny** för att navigera till Uppgifter, Forms, Utkorgen och Inställningar. Om din AEM Forms-app är ansluten till en AEM Forms JEE-server kan du se alternativet Åtgärder. Alternativet Uppgifter lagrar även utkast som skapats från uppgifter i en process. För AEM Forms OSGi-servrar är aktivitetsalternativet dolt. I Outbox lagras de sparade formulären och utkasten innan de synkroniseras med servern. Alla sparade formulär och utkast i Utkorgen överförs till AEM Forms-servern när appen [synkroniserad med servern](/help/forms/using/sync-app.md). Mer information om inställningar finns i [Uppdatera allmänna inställningar](/help/forms/using/update-general-settings.md).
1. **Uppgift eller formulär**: Tryck på uppgiften eller formuläret som du vill arbeta med.
1. **Vågrät ellips**: Anger att åtgärder är tillgängliga för formuläret. När du trycker på ellipsen visas de åtgärder och den som har skrivit beskrivningen. The **Ta bort utkast** och **Slutförd** är synligt när du trycker på ellipsen.
1. **Ikonen Uppdatera**: Tryck på uppdateringsikonen för att synkronisera appen med AEM Forms-servern.

## Anpassa hemskärmen {#customizing-the-home-screen}

![Allmänna inställningar](assets/gen-settings.png)

Du kan ändra standardhemskärmen för programmet antingen från **[Allmänna inställningar](/help/forms/using/update-general-settings.md)** från appen eller från **Inställningar** på arbetsytan i HTML.

Ändringen av inställningen för startskärmen i appen påverkar startskärmen för den inloggade användaren eller användaren på den aktuella mobila enheten.

Ändringen i HTML Workspace påverkar dock alla AEM Forms-appanvändare som är inloggade på AEM Forms-servern.
