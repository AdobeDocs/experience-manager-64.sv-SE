---
title: Implementera Windows 10 Player
seo-title: Implementera Windows 10 Player
description: 'Följ den här sidan om du vill veta mer om hur du konfigurerar AEM Screens Windows 10 Player. '
seo-description: 'Följ den här sidan om du vill veta mer om hur du konfigurerar AEM Screens Windows 10 Player. '
uuid: cdd7e9f1-f836-4d52-8026-80537a6623ca
contentOwner: jsyal
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: administering
content-type: reference
discoiquuid: 9b66225a-a893-491b-b47c-ae7b3048ed80
translation-type: tm+mt
source-git-commit: c8694726dc29b391a157db3ef230f21517c957bd

---


# Implementera Windows 10 Player{#implementing-windows-player}

I det här avsnittet beskrivs hur du konfigurerar AEM Screens Windows 10 Player. Den innehåller information om konfigurationsfilen, tillgängliga alternativ och rekommendationer om vilka inställningar som ska användas för utveckling och testning.

## Installerar Windows Player {#installing-windows-player}

Installera Windows Player för AEM-skärmar om du vill implementera Windows Player för AEM-skärmar.

Gå till [**sidan AEM 6.4 Player Downloads **](https://download.macromedia.com/screens/).

### Ad-Hoc-metod {#ad-hoc-method}

Ad-Hoc-metoden för att installera den senaste versionen av Windows Player (*.exe*) finns på [**sidan AEM 6.4 Player Downloads **](https://download.macromedia.com/screens/).

När du har hämtat programmet följer du stegen på spelaren för att slutföra ad hoc-installationen:

1. Tryck länge på det övre vänstra hörnet för att öppna administrationspanelen.
1. Navigera till **Konfiguration** på den vänstra åtgärdsmenyn och ange platsen (adressen) för den AEM-instans som du vill ansluta till och klicka på **Spara**.

1. Klicka på länken **Registrering** i den vänstra åtgärdsmenyn för att slutföra enhetsregistreringsprocessen.

### Registrera flera Windows 10-spelare med en konfiguration {#registering-multiple-windows-players-with-one-configuration}

När du har installerat Windows Player kan du registrera flera spelare med en konfiguration.

>[!NOTE]
>
>**Massregistrering av Windows Player**
>
>När du implementerar Windows-spelaren behöver du inte konfigurera varje enskild spelare manuellt. I stället kan du uppdatera JSON-konfigurationsfilen när den har testats och är klar för distribution.
>
>Konfigurationen ser till att alla spelare pingar samma server som finns i konfigurationsfilen. Du måste fortfarande registrera varje spelare manuellt.

Följ stegen nedan för att konfigurera Windows 10 Player:

1. Installera Windows Player.
1. Hitta konfigurationsfilen under ***%appdata%\com.adobe.aem.screens.player\config.json***.
1. Uppdatera konfigurations-JSON med hjälp av informationen nedan och kopiera sedan samma mapp till alla system där spelaren finns.

### Principattribut {#policy-attributes}

I följande tabell sammanfattas principattributen med en exempelpolicy-JSON för referens:

| **Principnamn** | **Syfte** |
|---|---|
| server | URL:en till AEM-servern (Adobe Experience Manager). |
| upplösning | Enhetens upplösning. |
| rebootSchedule | Schemat för att starta om spelaren. |
| enableAdminUI | Aktivera administratörsgränssnittet för att konfigurera enheten på platsen. Anges till false när den är helt konfigurerad och i produktion. |
| enableOSD | Aktivera kanalväljarens användargränssnitt så att användare kan växla kanaler på enheten. Överväg att ställa in på false när den är helt konfigurerad och i produktion. |
| enableActivityUI | Aktivera om du vill visa förloppet för aktiviteter som hämtning och synkronisering. Aktivera för felsökning och inaktivera när den är helt konfigurerad och i produktion. |

#### Exempel på princip-JSON-fil {#example-policy-json-file}

```
{
    "server": "http://localhost:4502",
    "resolution": "auto",
    "rebootSchedule": "at 4:00 am",
    "enableAdminUI": false,
    "enableOSD": false,
    "enableActivityUI": false
}
```

