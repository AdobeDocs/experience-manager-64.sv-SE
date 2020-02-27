---
title: Inbäddade sekvenser
seo-title: Inbäddade sekvenser
description: Följ den här sidan om du vill veta mer om inbäddade sekvenser för kanaler som gör att användaren kan lägga till komponenter i den överordnade kanalen och även återanvända innehållet från en annan kanal och bädda in det i den överordnade kanalen.
seo-description: Följ den här sidan om du vill veta mer om inbäddade sekvenser för kanaler som gör att användaren kan lägga till komponenter i den överordnade kanalen och även återanvända innehållet från en annan kanal och bädda in det i den överordnade kanalen.
uuid: 3ffbe937-6b60-4eea-acfb-633270b4ded3
contentOwner: jsyal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: authoring
discoiquuid: 76be4cc1-4b34-4f1d-b2d3-754a84105dec
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# Inbäddade sekvenser{#embedded-sequences}

Om du använder ***inbäddade sekvenser*** för kanaler kan användaren lägga till komponenter i den överordnade kanalen och även återanvända innehållet från en annan kanal och bädda in det i den överordnade kanalen.

## Lägga till inbäddade sekvenser {#adding-embedded-sequences}

Du kan lägga till följande komponenter i sekvenskanalen:

* Inbäddad sekvens
* Dynamisk inbäddad sekvens

>[!NOTE]
>
>Mer information om hur du använder andra komponenter i ditt skärmsprojekt finns i [Lägga till komponenter i en kanal](/help/screens/adding-components-to-a-channel.md).

### Lägga till en inbäddad sekvens {#adding-an-embedded-sequence}

Du kan lägga till en inbäddad sekvens i kanalen. En inbäddad sekvens via en annan kanal som innehåller resurser som bilder eller videoklipp. Genom att lägga till en inbäddad sekvens kan användaren lägga till sekvensen i en kanal via ***kanalsökväg***.

>[!NOTE]
>
>***Kanalsökväg ***definierar en explicit referens till kanalen.
>
>Mer information om *kanalsökväg* finns i [Kanaltilldelning](/help/screens/channel-assignment.md) i redigeringsskärmar.

Följ stegen nedan för att lägga till en inbäddad sekvens i kanalen:

1. Markera kanalen där du vill bädda in en sida. Exempel: **We.Retail In-Store** —> **Channels** —>** Idle Channel**.

1. Klicka på **Redigera** i åtgärdsfältet för att öppna kanalen i redigeringsläget.
1. Klicka på komponentikonen i det vänstra fältet för att lägga till den inbäddade sidan. Dra och släpp den **inbäddade sekvensen** till redigeraren.
1. Dubbelklicka på komponenten **Inbäddad sekvens** för att lägga till kanalen i den ursprungliga sekvenskanalen.
1. Markera kanalens **kanalsökväg** .
1. Välj **Varaktighet (ms)** för den inbäddade kanalen på fliken **Sekvens** . Som standard är längden inställd på **-1**, vilket innebär att inbäddad kanal körs helt. Om användaren anger en varaktighet kommer efterföljande att avbrytas (d.v.s. brytfrekvens) vid den angivna tiden.

1. Ställ in **Metered Playback Strategy** på **normal**.

Som standard är den inställd på **normal**. Om du ställer in värdet på **normal*** (Spela upp alla objekt)* innebär det att efterföljande kommer att köras helt i varje cykel i den överordnade sekvensen. Det andra möjliga värdet är **Spela upp ett enstaka objekt*** (Spela upp ett enstaka objekt)* och som bara visar ett objekt i efterföljande körning (till exempel det första objektet i den första slingan, det andra objektet i den andra slingan och så vidare).

I följande exempel visas hur en inbäddad sekvens (**Inaktiv kanal - Natt**) läggs till i en befintlig kanal (**Inaktiv kanal**).

![new2](assets/new2.gif)

### Lägga till en dynamisk inbäddad sekvens {#adding-a-dynamic-embedded-sequence}

Du kan lägga till en dynamisk inbäddad sekvens i kanalen. En dynamisk inbäddad sekvens liknar en inbäddad sekvens men gör det möjligt för användaren att följa en hierarki där ändringar/uppdateringar som görs i en kanal sprids till en annan i relation till den. Den följer hierarkin för överordnade och underordnade och innehåller även resurser som bilder eller videor. Genom att lägga till en dynamisk sekvens kan användaren lägga till en kanal per kanalroll.

>[!NOTE]
>
>***Kanalrollen*** definierar den kanalroll som definierar visningssammanhanget.
>
>Mer information om *kanalroll* finns i [Kanaltilldelning](/help/screens/channel-assignment.md) i redigeringsskärmar.

Följ stegen nedan för att lägga till en inbäddad sekvens i kanalen:

1. Markera kanalen där du vill bädda in en dynamisk sekvens. Exempel: **We.Retail In-Store** —> **Channels** —> **Idle Channel**.

1. Klicka på **Redigera** i åtgärdsfältet för att öppna kanalen i redigeringsläget.
1. Klicka på komponentikonen i det vänstra fältet för att lägga till den dynamiska inbäddade sekvensen. Dra och släpp den **dynamiska inbäddade sekvensen** till redigeraren.

1. Dubbelklicka på komponenten **Dynamic Embedded Sequence** för att lägga till sidan i sekvenskanalen.

1. Ange **kanaltilldelningsrollen**.
1. Ställ in **Metered Playback Strategy** på **normal**. Som standard är den inställd på **normal**. Om du ställer in värdet på **normal*** (Spela upp alla objekt)* innebär det att efterföljande kommer att köras helt i varje cykel i den överordnade sekvensen. Det andra möjliga värdet är **Spela upp ett enskilt objekt** *(Spela upp ett enskilt objekt)* och visar bara ett objekt i efterföljande körning (till exempel det första objektet i den första slingan, det andra objektet i den andra slingan och så vidare).

1. Välj **Varaktighet (ms)** på fliken **Sekvens** för den inbäddade kanalen i sekvensen.

![senaste](assets/latest.gif)

