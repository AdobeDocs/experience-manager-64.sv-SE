---
title: Konfigurera och distribuera AEM-skärmar
seo-title: Konfigurera och distribuera skärmar
description: AEM Screens Player är tillgänglig för Android, Chrome OS, iOS och Windows. Den här sidan beskriver konfiguration och distribution av AEM-skärmar och sammanfattar även riktlinjerna för maskinvaruval för spelarenheter.
seo-description: AEM Screens Player är tillgänglig för Android, Chrome OS, iOS och Windows. Den här sidan beskriver konfiguration och distribution av AEM-skärmar och sammanfattar även riktlinjerna för maskinvaruval för spelarenheter.
uuid: 8ee5311f-b377-4035-af77-e1391a840745
contentOwner: Jyotika syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: administering
discoiquuid: a94d0891-d75f-482e-8d2a-e0cbf953a9de
translation-type: tm+mt
source-git-commit: 1ebe1e871767605dd4295429c3d0b4de4dd66939

---


# Konfigurera och distribuera AEM-skärmar{#configuring-and-deploying-aem-screens}

På den här sidan visas hur du installerar och konfigurerar skärmspelarna på dina enheter. Här beskrivs följande avsnitt:

* Installera AEM Screens Player
* Serverkonfiguration
* Riktlinjer för val av maskinvara för spelarenhet
* Nästa steg

## Installera AEM Screens Player {#installing-aem-screens-player}

AEM Screens Player är tillgänglig för Android, Chrome OS, iOS och Windows.

Om du vill hämta **AEM Screens Player** går du till [**sidan AEM 6.4 Player Downloads **](https://download.macromedia.com/screens/).

>[!NOTE]
>
>När du har laddat ned den senaste spelaren (*.exe*) följer du stegen på spelaren för att slutföra ad hoc-installationen:
>
>1. Tryck länge på det övre vänstra hörnet för att öppna administrationspanelen.
>1. Navigera till **Konfiguration** på den vänstra åtgärdsmenyn, ange platsadressen för AEM-instansen i **Server** och klicka på **Spara**.
   >
   >
1. Klicka på länken **Registrering** i den vänstra åtgärdsmenyn och på stegen nedan för att slutföra enhetsregistreringsprocessen.
>



### Additional Resources {#additional-resources}

Mer information finns i följande avsnitt:

* Om du vill hämta Android Player går du till **Google Play**. Mer information om hur du implementerar Android-övervakning finns i **[Implementera Android-spelare](implementing-android-player.md)**.

* Mer information om hur du implementerar Chrome OS Player finns i [Chrome Management Console](implementing-chrome-os-player.md) .
* Mer information om hur du konfigurerar AEM Screens Windows Player finns i [Implementera Windows Player](implementing-windows-player.md).

## Serverkonfiguration {#server-configuration}

>[!NOTE]
>
>**Viktigt**:
>
>AEM Screens Player använder inte CSRF-token (Cross-Site Request Forgery). Om du vill konfigurera och AEM-servern ska vara klar att användas för AEM-skärmar hoppar du över referensfiltret genom att tillåta tomma referenter.

### Förutsättningar {#prerequisites}

Följande huvudpunkter nedan hjälper dig att konfigurera och använda AEM-servern för AEM-skärmar:

#### Tillåt tomma referentförfrågningar {#allow-empty-referrer-requests}

Följ stegen nedan för att aktivera Apache Sling Referrer-filtret Tillåt tomt. Detta krävs för att kontrollprotokollet mellan AEM Screens Player och AEM Screens Server ska fungera optimalt.

1. Gå till **Adobe Experience Manager Web Console Configuration **via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

   ![screen_shot_2019-02-11at15405pm](assets/screen_shot_2019-02-11at15405pm.png)

1. **Adobe Experience Manager Web Console Configuration** öppnas. Sök efter försäljningsreferent.

   Om du vill söka efter egenskapen för Sing-refereraren trycker du på **Command+F** för **Mac** och **Ctrl+F** för **Windows**.

   ![screen_shot_2019-02-11at15629pm](assets/screen_shot_2019-02-11at15629pm.png)

1. Markera alternativet **Tillåt tomt** , så som visas i bilden nedan.

   ![screen_shot_2018-12-04at22911pm](assets/screen_shot_2018-12-04at22911pm.png)

1. Klicka på **Spara** för att aktivera Apache Sling Referer-filtret Tillåt tomt.

#### Aktivera Touch UI för AEM-skärmar {#enable-touch-ui-for-aem-screens}

AEM-skärmar kräver TOUCH-gränssnitt och fungerar inte med CLASSIC-gränssnittet i Adobe Experience Manager (AEM).

1. Navigera till *&lt;yourAuthorInstance>/system/console/configMgr/com.day.cq.wcm.core.impl.AuthoringUIModeServiceImpl*
1. Kontrollera att standardläget **för** redigeringsgränssnittet är inställt på **TOUCH**, vilket visas i figuren nedan

Du kan också göra samma inställning med*&lt;yourAuthorInstance> *->* verktyg (hammer-ikon)* -> **Åtgärder** ->**Webbkonsolen** och söka efter **WCM-redigeringens användargränssnittstjänst**.

![screen_shot_2018-12-04at22425pm](assets/screen_shot_2018-12-04at22425pm.png)

>[!NOTE]
>
>Du kan alltid aktivera klassiskt gränssnitt för specifika användare med hjälp av användarinställningarna.

#### AEM i NOSAMPLECONTENT, körningsläge {#aem-in-nosamplecontent-runmode}

När du kör AEM i produktion används körningsläget **NOSAMPLECONTENT** . Ta bort sidhuvudet *X-Frame-Options=SAMEORIGIN* (i det extra svarshuvudet) från

[http://localhost:4502/system/console/configMgr/org.apache.sling.engine.impl.SlingMainServlet](http://localhost:4502/system/console/configMgr/org.apache.sling.engine.impl.SlingMainServlet).

Detta krävs för att AEM Screens Player ska kunna spela upp onlinekanaler.

#### Lösenordsbegränsningar {#password-restrictions}

Med de senaste ändringarna av ***DeviceServiceImpl*** behöver du inte ta bort lösenordsbegränsningarna.

Du kan konfigurera ***DeviceServiceImpl*** från länken nedan för att aktivera lösenordsbegränsning när du skapar lösenordet för skärmenhetsanvändare:

[http://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.impl.DeviceService](http://localhost:4502/system/console/configMgr/com.adobe.cq.screens.device.impl.DeviceService)

Följ stegen nedan för att konfigurera ***DeviceServiceImpl***:

1. Navigera till **Adobe Experience Manager Web Console Configuration** via AEM instance —> hammer icon —> **Operations** —> **Web Console**.

1. **Adobe Experience Manager Web Console Configuration** öppnas. Sök efter enhetstjänst. Om du vill söka efter egenskapen trycker du på **Command+F** för **Mac** och **Ctrl+F** för **Windows**.

![screen_shot_2019-02-21at24951pm](assets/screen_shot_2019-02-21at24951pm.png)

#### Dispatcher-konfiguration {#dispatcher-configuration}

För **Dispatcher, **lägg till klientrubriker i .any-filen. Tillåt följande rubriker via:

* &quot;X-Requested-With&quot;
* &quot;X-SET-HEARTBEAT&quot;
* &quot;X-REQUEST-COMMAND&quot;

#### Java-kodning {#java-encoding}

Ställ in Unicode för ***Java-kodning*** . Dfile. *encoding=Cp1252* fungerar till exempel inte.

>[!NOTE]
>
>**Rekommendation:**
>
>Du bör använda HTTPS för AEM Screens Server i produktionen.

## Riktlinjer för val av maskinvara för spelarenhet {#hardware-selection-guidelines-for-player-device}

Följande avsnitt innehåller riktlinjer för val av maskinvara för ett skärmsprojekt:

* Källa alltid till ***kommersiella*** eller ***industriella*** komponenter för både PC Player och Display Panel eller Projector.

* Samarbeta alltid med leverantörer som levererar digitala signaturer.
* Ta alltid hänsyn till miljöfaktorer som omgivningstemperatur och relativ luftfuktighet.
* Granska alltid effektkrav och energikonditionering.
* Granska noggrant prestandabehov och I/O-portar som krävs för programmet.

I följande tabell sammanfattas maskinvarukonfigurationerna med typiska användningsfall för ett AEM-skärmsprojekt:

<table> 
 <tbody> 
  <tr> 
   <td>Spelarkonfiguration</td> 
   <td>Processor</td> 
   <td>Minne</td> 
   <td>Lagring SSD</td> 
   <td>GPU</td> 
   <td>Visa</td> 
   <td>I/O</td> 
   <td>Vanliga användningsområden</td> 
  </tr> 
  <tr> 
   <td>Grundläggande</td> 
   <td>Intel® Atom-processor med dubbla kärnor, i3 eller fyra kärnor på ingångsnivå</td> 
   <td><p>4 GB minne</p> <p>2 MB cache</p> </td> 
   <td><p>・ChromeOS 32 GB</p> <p>・Windows 128 GB</p> </td> 
   <td>OnBoard</td> 
   <td>1920 x 1080</td> 
   <td>DVI, <br /> Ethernet/trådlöst,<br /> 2 x USB</td> 
   <td> 
    <ul> 
     <li>Helskärmsloop som standard <br /> </li> 
     <li>Dag-parsning</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Standard</td> 
   <td>Processor med fyra kärnor, Intel® Core i5</td> 
   <td><p>8 GB minne</p> <p>4 MB cache</p> </td> 
   <td>128 GBB</td> 
   <td>OnBoard</td> 
   <td>3840x2160 (4K)</td> 
   <td>DVI, HDMI<br /> Ethernet/trådlöst,<br /> 2 x USB</td> 
   <td> 
    <ul> 
     <li>Dynamiskt innehåll med en källa </li> 
     <li>Enkel interaktiv</li> 
     <li> 1-3 zonlayouter</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td>Avancerat</td> 
   <td>Intel® Core i7-processor med fyra kärnor och hypertrådning</td> 
   <td><p>16 GB minne</p> <p>8 MB cache</p> </td> 
   <td>256 GB</td> 
   <td>Discreet GPU</td> 
   <td>3840x2160 (4K)</td> 
   <td>DVI, HDMI<br /> Ethernet/trådlöst,<br /> 4x USB</td> 
   <td> 
    <ul> 
     <li>4 eller fler innehållszoner, samtidiga videouppspelningar</li> 
     <li> Interaktiv flersidig</li> 
     <li>Datautlösare med flera källor</li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Nästa steg {#the-next-steps}

När du har installerat och konfigurerat Skärmspelaren följer du nedanstående avsnitt för att komma igång:

1. [Skapa och hantera skärmsprojekt](creating-a-screens-project.md)
1. [Skapa och hantera kanaler](managing-channels.md)
1. [Skapa och hantera platser](managing-locations.md)
1. [Skapa och hantera bildskärmar](managing-displays.md)
1. [Tilldela kanaler](channel-assignment.md)
1. [Hantera enheter](managing-devices.md)
1. [Registrera en enhet](device-registration.md)
1. [Tilldela enheter](managing-devices.md)
1. [Skapa och hantera scheman](managing-schedules.md)
1. [AEM Screens Player](working-with-screens-player.md)
1. [Felsöka Device Control Center](monitoring-screens.md)

