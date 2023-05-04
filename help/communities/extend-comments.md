---
title: Komponenten Utöka kommentarer
seo-title: Extend Comments Component
description: Utöka komponenten Kommentarer för att ändra dess utseende eller beteende för specifika användningsområden
seo-description: Extend the Comments component to alter its appearance or behavior for specific uses
uuid: 6f439097-b1d0-4e7d-afcf-01d8f43aa866
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: developing
content-type: reference
discoiquuid: a07a4690-0e47-4a76-84cb-96abdc70b835
exl-id: f6722953-ff71-4fba-b76e-1d566f71f6d5
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 0%

---

# Komponenten Utöka kommentarer {#extend-comments-component}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Avsikten med [utöka](client-customize.md#extensions) en standardkomponent är att ändra en komponents utseende eller beteende för specifika användningsområden.

Sökvägen till komponenten är unik och refererar standardkomponenten som en överordnad resurstyp. Risken är mindre eftersom omfattningen är begränsad jämfört med den globala omfattningen för en komponentövertäckning.

>[!NOTE]
>
>Utöka en [överlagrad](client-customize.md#overlays) stöds inte.

## Exempel {#example}

Anta att rubriken för kommentarkomponenten måste visas med ett alternativt utseende på en plats i AEM, samtidigt som den visas med standardvisningen på en annan plats. I stället för att åsidosätta standardkommentaren, som ändrar kommentarkomponenten för alla instanser, är det bättre att se till att det finns flera kommentarskomponenter tillgängliga för användning på olika platser.

Om du vill implementera den här lösningen skapar du en ny komponent som utökar (åsidosätter) den befintliga och ändrar Handlebars-skriptet. Det område på webbplatsen som använder de nya kommentarerna kan använda det utökade området, medan de webbplatser som använder standardutseendet inte påverkas.

Kommentarskomponenten är i själva verket en av två komponenter som utgör kommentarssystemet. Det finns alltså två komponenter att utöka: *kommentarer* och *kommentar*. Skriptet som ska redigeras finns i *comment *-komponentens `header.hbs` -filen, medan den överordnade *kommentarer* -komponenten (kommentarsystemet) är det som en författare faktiskt lägger till på sidan.

Om du vill lägga in kommentarer måste du

1. [Skapa komponenterna](extend-create-components.md)
1. [Lägg till kommentar på exempelsida](extend-sample-page.md)
1. [Ändra utseendet](extend-alter-appearance.md)
