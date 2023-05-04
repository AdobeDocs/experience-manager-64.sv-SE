---
title: Adobe-klassificeringar
seo-title: Adobe Classifications
description: Läs mer om Adobe Classifications.
seo-description: Learn about Adobe Classifications.
uuid: 57fb59f4-da90-4fe7-a5b1-c3bd51159a16
contentOwner: User
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: 6787511a-2ce0-421a-bcfb-90d5f32ad35e
exl-id: 25e58c68-5c67-4894-9a54-1717d90d7831
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 1%

---

# Adobe-klassificeringar{#adobe-classifications}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Klassificeringar i Adobe exporterar klassificeringsdata till [Adobe Analytics](/help/sites-administering/adobeanalytics.md) på ett planerat sätt. Exportören är en tillämpning av **com.adobe.cq.scheduled.exporting.Exporter**.

Så här konfigurerar du:

1. Navigera via **verktyg, molntjänster** till **Adobe Analytics** -avsnitt.
1. Lägg till en ny konfiguration. Du kommer att se att **Adobe Analytics Classifications** Konfigurationsmallen visas under **Adobe Analytics Framework** konfiguration. Ange en **Titel** och **Namn** efter behov:

   ![aa-25](assets/aa-25.png)

1. Klicka **Skapa** för att konfigurera inställningarna.

   ![chlimage_1](assets/chlimage_1.png)

   Egenskaperna är följande:

   | **Fält** | **Beskrivning** |
   |---|---|
   | Aktiverad | Välj **Ja** om du vill aktivera inställningarna för klassificering i Adobe. |
   | Skriv över vid konflikt | Välj **Ja** för att skriva över datakollisioner. Som standard är detta inställt på **Nej**. |
   | Ta bort bearbetade | Om inställt på **Ja**, tar bort bearbetade noder när de har exporterats. Standardvärdet är **Falskt**. |
   | Exportera jobbbeskrivning | Ange en beskrivning för jobbet Adobe Classifications. |
   | E-postmeddelande | Ange en e-postadress för Adobe Classifications-meddelanden. |
   | Report Suite | Ange den rapportsvit som du vill köra importjobbet för. |
   | Datauppsättning | Ange det datauppsättningsrelations-ID som importjobbet ska köras för. |
   | Transformator | Välj en transformatorimplementering i listrutan. |
   | Datakälla | Navigera till sökvägen för databehållaren. |
   | Exportera schema | Välj schema för exporten. Standardvärdet är var 30:e minut. |

1. Klicka **OK** för att spara inställningarna.

## Ändra sidstorlek {#modifying-page-size}

Poster behandlas på sidor. Som standard skapas sidor med sidstorleken 1 000 i Adobe Classifications.

En sida kan vara högst 25000, per definition i Adobe Classifications och kan ändras från Felix-konsolen. Vid exporten låses källnoden med Adobe-klassificeringar för att förhindra samtidiga ändringar. Noden låses upp efter export, vid fel eller när sessionen stängs.

Så här ändrar du sidstorlek:

1. Gå till OSGI-konsolen på **https://&lt;host>:&lt;port>/system/console/configMgr** och markera **Export av Adobe-AEM**.

   ![aa-26](assets/aa-26.png)

1. Uppdatera **Exportera sidstorlek** efter behov, klicka sedan på **Spara**.

## SAINTDefaultTransformer {#saintdefaulttransformer}

>[!NOTE]
>
>Adobe-klassificeringar kallades tidigare för SAINT Exporter.

En exportör kan använda en transformator för att omforma exportdata till ett visst format. Ett undergränssnitt för Adobe-klassificeringar `SAINTTransformer<String[]>` implementering av Transformer-gränssnittet har angetts. Det här gränssnittet används för att begränsa datatypen till `String[]` som används av API:t för SAINT och har ett markörgränssnitt för att hitta sådana tjänster för markering.

I standardimplementeringen SAINTDefaultTransformer behandlas de underordnade resurserna för exportörkällan som poster med egenskapsnamn som nycklar och egenskapsvärden som värden. The **Nyckel** kolumnen läggs automatiskt till som första kolumn - dess värde blir nodnamnet. Namngivna egenskaper (som innehåller :) ignoreras.

*Nodstruktur:*

* id-klassificering `nt:unstructured`

   * 1 `nt:unstructured`

      * Produkt = Mitt produktnamn (sträng)
      * Price = 120.90 (String)
      * Size = M (String)
      * Color = black (String)
      * Color^Code = 101 (String)

**SAINT Header &amp; Record:**

| **Nyckel** | **Produkt** | **Pris** | **Storlek** | **Färg** | **Color^Code** |
|---|---|---|---|---|---|
| 1 | Mitt produktnamn | 120.90 | M | svart | 101 |

Egenskaperna är följande:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Egenskapssökväg</strong></td> 
   <td><strong>Beskrivning</strong></td> 
  </tr> 
  <tr> 
   <td>transformator</td> 
   <td>Ett klassnamn för en SAINTTransformer-implementering</td> 
  </tr> 
  <tr> 
   <td>e-post</td> 
   <td>E-postadress för avisering.</td> 
  </tr> 
  <tr> 
   <td>reportsuites</td> 
   <td>Rapportera Suite-ID:n som importjobbet ska köras för. </td> 
  </tr> 
  <tr> 
   <td>datauppsättning</td> 
   <td>Datauppsättningsrelations-ID som importjobbet ska köras för. </td> 
  </tr> 
  <tr> 
   <td>description</td> 
   <td>Jobbbeskrivning. <br /> </td> 
  </tr> 
  <tr> 
   <td>skriv över</td> 
   <td>Flagga för att skriva över datakollisioner. Standard är <strong>false</strong>.</td> 
  </tr> 
  <tr> 
   <td>indelningar</td> 
   <td>Flagga för att kontrollera om rapportsviterna är kompatibla. Standard är <strong>true</strong>.</td> 
  </tr> 
  <tr> 
   <td>borttagen</td> 
   <td>Flagga för att ta bort de bearbetade noderna efter exporten. Standard är <strong>false</strong>.</td> 
  </tr> 
 </tbody> 
</table>

## Automatisera export av Adobe-klassificeringar {#automating-adobe-classifications-export}

Du kan skapa ett eget arbetsflöde, så att alla nya importer startar arbetsflödet för att skapa rätt, och korrekt strukturerade, data i **/var/export/** så att den kan exporteras till Adobe-klassificeringar.
