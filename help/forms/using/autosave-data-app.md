---
title: Använda automatiskt sparande i appen AEM Forms
seo-title: Använda automatiskt sparande i appen AEM Forms
description: 'Lär dig hur du använder funktionen för automatiskt sparande i appen AEM Forms för att undvika dataförlust. '
seo-description: 'Lär dig hur du använder funktionen för automatiskt sparande i appen AEM Forms för att undvika dataförlust. '
uuid: f18ab6b4-dd4a-4dcb-88e6-e349777d47ea
contentOwner: sashanka
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 133d93b0-512c-46db-b5f9-f981d77b565f
translation-type: tm+mt
source-git-commit: e2bb2f17035e16864b1dc54f5768a99429a3dd9f

---


# Använda automatiskt sparande i appen AEM Forms {#using-autosave-in-aem-forms-app}

När en användare anger data i appen Adobe Experience Manager Forms sparar funktionen automatiskt dem med regelbundna intervall. Funktionen för automatiskt sparande i appen AEM Forms hjälper dig att undvika dataförluster om appen stängs av misstag.

Ditt program kan stängas av misstag:

* Om enheten stängs av på grund av för lite batteri
* Om användaren dödar appen
* Om en oväntad krasch inträffar

Du kan ange de intervall efter vilka appen sparar de angivna data.

>[!NOTE]
>
>Välj autosparfrekvens med omdöme. Automatiska åtgärder som sparas ofta kan ha en märkbar inverkan på enhetens prestanda.

Utför följande steg för att använda funktionen för att spara automatiskt i appen AEM Forms:

1. Logga in på appen och gå till **[!UICONTROL Inställningar > Allmänt]**.
1. På skärmen Allmänt använder du alternativet **[!UICONTROL Spara frekvens]** automatiskt för att välja de intervall med vilka du vill att appen ska spara angivna data.
   [ Ange ![automatiskt sparad frekvens](assets/using-autosave-freq-07.png)](assets/using-autosave-freq-07-1.png)

1. När du startar om programmet och loggar in med samma användare uppmanas du att återställa uppgiften i dialogrutan Återställ osparad uppgift. Klicka på **[!UICONTROL OK]** i dialogrutan Återställ osparad uppgift för att fortsätta arbeta med den sparade uppgiften. Du kan klicka på **[!UICONTROL Avbryt]** om du vill ta bort de sparade data som motsvarar den senast aktiverade autosparfunktionen och börja arbeta med en ny uppgift.

   När du klickar på **[!UICONTROL OK]**återställs uppgiften med de data som motsvarar den senaste autosparfunktionen som utlöstes innan appen kraschade. Den innehåller formulärdata och alla bilagor som är associerade med uppgiften.
   [![](assets/autosave-flow.png)](assets/using-autosave-freq-06.png)****** Hämtning av en uppgift **har återställtsA. Ett pågående formulär** B. Programmet stängdes med tvång **C.** Programmet startades om med dialogrutan Återställ osparad uppgift **D. Formuläret har återställts med ursprungliga data

