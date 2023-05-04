---
title: Använda automatiskt sparade i AEM Forms-appen
seo-title: Using autosave in AEM Forms app
description: Lär dig hur du använder funktionen Spara automatiskt i AEM Forms-appen för att undvika dataförlust.
seo-description: Learn how to use autosave feature in AEM Forms app that lets you avoid data loss.
uuid: f18ab6b4-dd4a-4dcb-88e6-e349777d47ea
contentOwner: sashanka
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: forms-app
discoiquuid: 133d93b0-512c-46db-b5f9-f981d77b565f
exl-id: 6eb00c31-6806-478a-99d1-55912798ea69
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 0%

---

# Använda automatiskt sparade i AEM Forms-appen {#using-autosave-in-aem-forms-app}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

När en användare matar in data i Adobe Experience Manager Forms-appen sparar funktionen automatiskt dem med regelbundna intervall. Funktionen Spara automatiskt i AEM Forms-appen hjälper dig att undvika dataförluster om appen stängs av misstag.

Ditt program kan stängas av misstag:

* Om enheten stängs av på grund av för lite batteri
* Om användaren dödar appen
* Om en oväntad krasch inträffar

Du kan ange de intervall efter vilka appen sparar de angivna data.

>[!NOTE]
>
>Välj autosparfrekvens med omdöme. Automatiska åtgärder som sparas ofta kan ha en märkbar inverkan på enhetens prestanda.

Så här använder du funktionen Spara automatiskt i AEM Forms-appen:

1. Logga in på appen och navigera till **[!UICONTROL Settings > General]**.
1. På skärmen Allmänt använder du **[!UICONTROL Autosave Frequency]** om du vill välja med vilka intervall appen ska spara de angivna data.
   [ ![Ställa in autosparfrekvens](assets/using-autosave-freq-07.png)](assets/using-autosave-freq-07-1.png)

1. När du startar om programmet och loggar in med samma användare uppmanas du att återställa uppgiften i dialogrutan Återställ osparad uppgift. Klicka **[!UICONTROL OK]** i dialogrutan Återställ osparad uppgift för att fortsätta arbeta med den sparade uppgiften. Du kan klicka **[!UICONTROL Cancel]** om du vill ta bort de sparade data som motsvarar den senast aktiverade autosparfunktionen och börja arbeta med en ny uppgift.

   När du klickar **[!UICONTROL OK]**återställs aktiviteten med de data som motsvarar den senaste autosparfunktionen som utlöstes innan appen kraschade. Den innehåller formulärdata och alla bilagor som är associerade med uppgiften.
   [ ![Hämta en uppgift som återställts ](assets/autosave-flow.png)](assets/using-autosave-freq-06.png)**S.** Ett pågående formulär **B.** Appen stängdes med tvång **C.** Programmet har startats om med dialogrutan Återställ osparad uppgift **D.** Formuläret har återställts med ursprungliga data
