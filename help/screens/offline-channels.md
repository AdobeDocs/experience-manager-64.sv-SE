---
title: Offlinekanaler
seo-title: Offlinekanaler
description: 'AEM Screens Player ger offlinesupport för kanalerna genom att utnyttja tekniken ContentSync. Följ den här sidan för att lära dig mer om uppdateringshanterare och aktivering av offlinekonfiguration för en kanal.  '
seo-description: 'AEM Screens Player ger offlinesupport för kanalerna genom att utnyttja tekniken ContentSync. Följ den här sidan för att lära dig mer om uppdateringshanterare och aktivering av offlinekonfiguration för en kanal.  '
uuid: 25766e79-a5a5-4b84-b235-e3050f725fbe
contentOwner: Jyotika Syal
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/SCREENS
topic-tags: developing
discoiquuid: 609d5405-138f-47f7-9ac0-efaa32f8715b
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Offlinekanaler{#offline-channels}

Skärmspelaren tillhandahåller offlinesupport för kanalerna genom att utnyttja ***ContentSync*** -tekniken.

Spelarna använder en lokal http-server för att hantera det uppackade innehållet.

När en kanal är konfigurerad för att köras *online*, skickar spelaren kanalresurserna genom åtkomst till AEM-servern, men när kanalen är konfigurerad för att köras *offline*, visar spelaren kanalresurserna från en lokal http-server.

Arbetsflödet för processen är följande:

1. Tolka de önskade sidorna
1. Samla in alla relaterade resurser
1. Paketera allt i en zip-fil
1. Ladda ned zip-filen och extrahera den lokalt
1. Visa lokal kopia av innehållet

## Uppdatera hanterare {#update-handlers}

I ***ContentSync*** används uppdateringshanterare för att analysera och samla in alla nödvändiga sidor och resurser för ett visst projekt. AEM Screens använder följande uppdateringshanterare:

### Vanliga alternativ {#common-options}

* *typ*: den uppdateringshanterartyp som ska användas
* *sökväg*: sökväg till resursen
* *[targetRootDirectory]*: målmapp i zip-filen

<table> 
 <tbody>
  <tr>
   <td><strong>Typ</strong></td> 
   <td><strong>Beskrivning</strong></td> 
   <td><strong>Alternativ</strong></td> 
  </tr>
  <tr>
   <td> kanaler</td> 
   <td>samlar in en kanal</td> 
   <td>tillägg: tillägg för resursen som ska samla in<br /> [pathSuffix='']: suffix som ska läggas till i kanalsökvägen<br /> [deep=true]: huruvida underordnade sidor ska tolkas rekursivt<br /> [includeImages=true]: inkludera alla bilder i kanalen<br /> [includeVideos=true]: inkludera alla videoklipp i kanalen<br /> [includeProducts=true]: inkludera alla produkter i kanalen</td> 
  </tr>
  <tr>
   <td>clientlib</td> 
   <td>samla in det angivna klientbiblioteket</td> 
   <td>[extension='']: kan vara antingen css eller js, för att endast samla in den första, eller bara den senare</td> 
  </tr>
  <tr>
   <td>assetrenditions</td> 
   <td>samla in resursåtergivningar</td> 
   <td>[renditions=[]]: lista över återgivningar som ska samlas in. Standardvärdet är den ursprungliga återgivningen</td> 
  </tr>
  <tr>
   <td>copy</td> 
   <td>kopiera den angivna strukturen från sökvägen</td> 
   <td> </td> 
  </tr>
 </tbody>
</table>

### Testar konfigurationen av ContentSync {#testing-contentsync-configuration}

Följ stegen nedan för att testa ContentSync-konfigurationen:

1. Öppna [http://localhost:4502/libs/cq/contentsync/content/console.html](http://localhost:4502/libs/cq/contentsync/content/console.html)
1. Välj din konfiguration i listan
1. Klicka på Rensa cache
1. Klicka på Uppdatera cache
1. Klicka på Hämta fullständig
1. Extrahera zip-filen
1. Starta en lokal server i den extraherade mappen
1. Öppna din startsida och kontrollera din appstatus

## Aktivera offlinekonfiguration för en kanal {#enabling-offline-config-for-a-channel}

Följ stegen nedan för att aktivera offlinekonfiguration för en kanal:

1. Granska kanalinnehållet och kontrollera om det efterfrågas från en AEM-instans (online).

   ![chlimage_1-15](assets/chlimage_1-15.png)

1. Navigera till kanalkontrollpanelen och klicka på **... i **panelen** KANALINFORMATION **för att ändra egenskaperna.

   ![chlimage_1-16](assets/chlimage_1-16.png)

1. Navigera till kanalegenskaperna och se till att kryssrutan är inaktiverad på fliken **Kanal** . Klicka på **Spara och stäng**.

   ![screen_shot_2017-12-19at122422pm](assets/screen_shot_2017-12-19at122422pm.png)

   Klicka på **Uppdatera offlineinnehåll** innan innehållet distribueras på rätt sätt till enheten.

   ![screen_shot_2017-12-19at122637pm](assets/screen_shot_2017-12-19at122637pm.png)

   Statusen **Offline** under **EGENSKAPER** uppdateras också i enlighet med detta.

   ![screen_shot_2017-12-19at124735pm](assets/screen_shot_2017-12-19at124735pm.png)

1. Granska kanalinnehållet och kontrollera om det efterfrågas från den lokala spelarcachen.

   ![chlimage_1-17](assets/chlimage_1-17.png)

