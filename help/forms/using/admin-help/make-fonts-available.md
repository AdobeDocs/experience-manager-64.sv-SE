---
title: Göra teckensnitt tillgängliga
seo-title: Make fonts available
description: Kontrollera att teckensnitten som används i ett formulär är tillgängliga för användning på J2EE-programservern som är värd AEM formulär.
seo-description: Ensure that the fonts used within a form are available for use on the J2EE application server hosting AEM forms.
uuid: 6588b4b6-f866-4253-91c8-3aa174340e8c
contentOwner: admin
content-type: reference
geptopics: SG_AEMFORMS/categories/configuring_output
products: SG_EXPERIENCEMANAGER/6.4/FORMS
discoiquuid: 9f58a6c4-3190-49d4-800c-4a55dca7c296
exl-id: 33d63ec9-b100-48b4-b84d-a9de82c24f86
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '255'
ht-degree: 0%

---

# Göra teckensnitt tillgängliga {#make-fonts-available}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Kontrollera att teckensnitten som används i ett formulär är tillgängliga för användning på J2EE-programservern som är värd AEM formulär. Ta till exempel följande scenario. En formulärdesigner lägger till ett teckensnitt i teckensnittskatalogen som Designer använder och skapar ett formulär som använder teckensnittet på en separat dator. För att Output-tjänsten ska kunna använda teckensnittet placerar du det i kundens teckensnittskatalog. Om kundens teckensnittskatalog inte finns skapar du en katalog på J2EE-programservern som AEM formulär.

Mer information om ytterligare teckensnittsinställningar finns i [Konfigurera allmänna inställningar AEM formulär](/help/forms/using/admin-help/configure-general-aem-forms-settings.md#configure-general-aem-forms-settings).

**Ange platsen för kundens teckensnittskatalog**

1. I administrationskonsolen klickar du på Inställningar > Core Systems Settings > Configurations.
1. Ange sökvägen till kundens teckensnittskatalog i rutan Plats för systemteckensnittskatalogen. Flera kataloger kan läggas till, avgränsade med semikolon **;**
1. Klicka på OK.
1. Starta om datorn där AEM har installerats.

>[!NOTE]
>
>Teckensnitt hämtas från Windows-systemets teckensnittscache och en systemomstart krävs för att uppdatera cachen. När du har angett kundens teckensnittskatalog måste du starta om systemet där AEM är installerat.
