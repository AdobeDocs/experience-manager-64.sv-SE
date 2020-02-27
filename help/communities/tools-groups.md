---
title: Gruppmallar
seo-title: Gruppmallar
description: Åtkomst till konsolen Gruppmallar
seo-description: Åtkomst till konsolen Gruppmallar
uuid: a3c6dfe6-f973-4dcf-9c66-ea52cbe56630
contentOwner: Janice Kendall
products: SG_EXPERIENCEMANAGER/6.4/COMMUNITIES
topic-tags: administering
content-type: reference
discoiquuid: 9a862756-58e8-47c0-a4b4-5d4aaac021e4
translation-type: tm+mt
source-git-commit: 13d890d08a032fe4eef1dac793dcf2a3e682a52c

---


# Gruppmallar {#group-templates}

Konsolen Gruppmallar liknar konsolen [Platsmallar](sites.md) . Båda är skisser för en uppsättning färdiga sidor och funktioner som utgör en communitysajt. Skillnaden är att en webbplatsmall är för huvudcommunityn och en gruppmall är för en community-grupp, en undercommunity som är kapslad i huvudcommunityn.

En communitygrupp ingår i en webbplatsmall genom att inkludera funktionen [](functions.md#groups-function) Grupper (som kanske inte är den första eller enda funktionen i mallen).

Från och med [funktionspaket 1](deploy-communities.md#latestfeaturepack)för Communities är det möjligt att kapsla in grupper genom att inkludera funktionen Groups i en gruppmall.

När åtgärden utförs för att skapa en ny community-grupp väljs gruppens mall (struktur). Valet beror på hur funktionen Grupper konfigurerades när den lades till i plats- eller gruppmallen.

>[!NOTE]
>
>Konsolerna för att skapa [communitysajter](sites-console.md), [communitymallar](sites.md), mallar [för](tools-groups.md) communitygrupper [och](functions.md) communityfunktionerär endast avsedda att användas i författarmiljön.

## Konsolen Gruppmallar {#group-templates-console}

I författarmiljön kan du nå gruppmallskonsolen

* Från global navigering: **[!UICONTROL Verktyg > Communities > Group Templates]**

Den här konsolen visar mallarna som en [communitywebbplats](sites-console.md) kan skapas från och tillåter att nya gruppmallar skapas.

![gruppermall](assets/groupstemplate.png)

## Skapa gruppmall {#create-goup-template}

Om du vill börja skapa en ny gruppmall väljer du **[!UICONTROL Skapa]**

Då öppnas panelen Platsredigeraren som innehåller tre underpaneler:

### Grundläggande information {#basic-info}

![chlimage_1-96](assets/chlimage_1-96.png)

På panelen Grundläggande information konfigureras ett namn, en beskrivning och huruvida mallen är aktiverad eller inaktiverad:

* **[!UICONTROL Nytt gruppmallsnamn]** Mallens namn-ID

* **[!UICONTROL Beskrivning]** Mallbeskrivningen

* **[!UICONTROL Inaktiverad/aktiverad]** En växlingsväxling som styr om mallen kan refereras

### Miniatyrbild {#thumbnail}

![chlimage_1-97](assets/chlimage_1-97.png)

(Valfritt) Markera ikonen Överför bild om du vill visa en miniatyrbild tillsammans med namnet och beskrivningen för användare som skapar communitywebbplatser.

### Struktur {#structure}

>[!CAUTION]
>
>Om du arbetar med AEM 6.1 Communities FP4 eller tidigare ska du inte lägga till någon gruppfunktion i en gruppmall.
>
>Funktionen för kapslade grupper är tillgänglig från och med Communities [FP1](communities.md#latestfeaturepack).
>
>Det är fortfarande inte tillåtet att lägga till en gruppfunktion som den första eller enda funktionen i en mall.

![grptemplateEditor](assets/grptemplateeditor.png)

Om du vill lägga till communityfunktioner drar du från höger sida till vänster i den ordning som länkarna på webbplatsmenyn ska visas. Format används på mallen när webbplatsen skapas.

Om du till exempel vill ha ett forum drar du forumfunktionen från biblioteket och släpper under mallverktyget. Detta resulterar i att dialogrutan för forumkonfiguration öppnas. Mer information om konfigurationsdialogrutorna finns i [funktionskonsolen](functions.md) .

Fortsätt att dra och släppa andra communityfunktioner som du vill använda för en undergruppswebbplats (grupp) som är baserad på den här mallen.

![dragfunktioner](assets/dragfunctions.png)

När alla önskade funktioner har släppts i mallbyggarområdet och konfigurerats väljer du **[!UICONTROL Spara]** i det övre högra hörnet.

## Redigera gruppmall {#edit-group-template}

När du visar communitygrupper i huvudkonsolen [](#group-templates-console)Gruppmallar kan du välja en befintlig gruppmall för redigering.

Om du redigerar en gruppmall påverkas inte communitywebbplatser som redan skapats från mallen. Det går att [redigera strukturen för en community-webbplats](sites-console.md#modify-structure)direkt i stället.

I den här processen finns samma paneler som när du [skapar en gruppmall](#create-goup-template).
