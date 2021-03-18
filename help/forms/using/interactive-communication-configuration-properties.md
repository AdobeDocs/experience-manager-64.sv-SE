---
title: Konfigurationsegenskaper för interaktiv kommunikation
seo-title: Egenskaper för konfiguration av interaktiv kommunikation
description: Redigera standardkonfigurationsegenskaper för interaktiv kommunikation
seo-description: Redigera standardkonfigurationsegenskaper för interaktiv kommunikation
uuid: 793da9c0-7e8b-464c-b41d-559a72fac9eb
contentOwner: anujkapo
products: SG_EXPERIENCEMANAGER/6.4/FORMS
content-type: reference
topic-tags: interactive-communications
discoiquuid: 1aef2a51-4391-4075-8841-a62ace5606f9
feature: Interaktiv kommunikation
translation-type: tm+mt
source-git-commit: 75312539136bb53cf1db1de03fc0f9a1dca49791
workflow-type: tm+mt
source-wordcount: '544'
ht-degree: 6%

---


# Egenskaper för konfiguration av interaktiv kommunikation {#interactive-communications-configuration-properties}

Redigera standardkonfigurationsegenskaper för interaktiv kommunikation

Interactive Communications innehåller egenskaper som konfigureras automatiskt efter installation av [AEM Forms-tilläggspaketet](/help/forms/using/installing-configuring-aem-forms-osgi.md). Författare av interaktiv kommunikation kan redigera dessa standardkonfigurationsegenskaper på sidan **Adobe Experience Manager Web Console Configuration**.

Öppna sidan **Konfiguration av Adobe Experience Manager Web Console** med följande URL:

https://&lt;server>:&lt;port>/&lt;contextPath>/system/console/configMgr

Konfigurationsegenskaperna omfattar:

* [Konfiguration av dokumentfragment](#document-fragments-configuration)
* [Skapa korrespondenskonfiguration](#create-correspondence-configuration)
* [Konfiguration av webbkanal för adaptiv form och interaktiv kommunikation](#adaptive-form-and-interactive-communication-web-channel-configuration)
* [Konfiguration av tema för adaptiv form och interaktiv kommunikation - webbkanal](#adaptive-form-and-interactive-communication-web-channel-theme-configuration)

## Konfiguration för dokumentfragment {#document-fragments-configuration}

Tryck på **Konfiguration av dokumentfragment** på sidan **Adobe Experience Manager Web Console Configuration** för att visa konfigurationsegenskaperna för dokumentfragment.

<table> 
 <tbody> 
  <tr> 
   <td>Egenskap</td> 
   <td>Beskrivning</td> 
   <td>Standard</td> 
   <td>Godtagbara värden</td> 
  </tr> 
  <tr> 
   <td>Datavisningsformat</td> 
   <td>Språkspecifikt visningsformat för fält, variabler och formulärdatamodellelement som är tillgängliga när du skapar en interaktiv kommunikation för tryck- och webbkanaler.</td> 
   <td> 
    <ul> 
     <li>locale = en_US, de_DE, fr_FR och ja_JP</li> 
     <li>dateFormat = dd-MM-yyy</li> 
     <li>numberDecimalSeparator = .</li> 
     <li>numberGroupSeparator = ,</li> 
     <li>numberUseGroupSeparator = true</li> 
    </ul> </td> 
   <td><p>—</p> </td> 
  </tr> 
  <tr> 
   <td>Indrag</td> 
   <td>Bredden på en enskild indragsenhet som används för text i listdokumentfragment.</td> 
   <td>12,7 mm</td> 
   <td>Siffra</td> 
  </tr> 
  <tr> 
   <td>Minsta bredd för romerska siffror</td> 
   <td>Minsta bredd som ska användas på punkt- eller nummerfältet när latinska nummer används i listdokumentfragment. </td> 
   <td>12,7 mm</td> 
   <td>Siffra</td> 
  </tr> 
  <tr> 
   <td>Minsta numerisk bredd</td> 
   <td>Minsta bredd som ska användas på punkt- eller nummerfältet när numrerade listor används, förutom latinska nummer i listdokumentfragment.</td> 
   <td>8,0 mm</td> 
   <td>Siffra</td> 
  </tr> 
 </tbody> 
</table>

## Skapa korrespondenskonfiguration {#create-correspondence-configuration}

Tryck på **Create Correspondence Configuration** på sidan **Adobe Experience Manager Web Console Configuration** för att visa konfigurationsegenskaperna för agentens användargränssnitt.

| Egenskap | Beskrivning | Standard | Godtagbara värden |
|---|---|---|---|
| Visa löst innehåll för redigering | Markera kryssrutan om du vill visa löst innehåll (faktiska värden i stället för platshållare) när du redigerar textmodulen i agentgränssnittet. | Inte markerad | Ej relevant |
| Använd vattenstämpel vid förhandsvisning | Markera kryssrutan om du vill använda vattenstämpel på kanalen Skriv ut i interaktiv kommunikation i förhandsgranskningsläget. | Inte markerad | Ej relevant |

## Konfiguration av webbkanalen för adaptiv form och interaktiv kommunikation {#adaptive-form-and-interactive-communication-web-channel-configuration}

Tryck på **Adaptive Form and Interactive Communication Web Channel Configuration** på sidan **Adobe Experience Manager Web Console Configuration** för att visa konfigurationsegenskaperna för Adaptive Forms och Interactive Communications Web channel. I följande tabell beskrivs egenskaperna för interaktiv kommunikation:

| Egenskap | Beskrivning | Standard | Godtagbara värden |
|---|---|---|---|
| Visa platshållare | Markera kryssrutan för att aktivera visning av platshållare för fält som ingår i adaptiva formulär och interaktiv kommunikation. | Markerad | Ej relevant |
| Maximalt antal cacheposter | Ange det maximala antalet adaptiva formulär och interaktiv kommunikation som kan hämtas med cacheminnet. | 100 | Siffra |
| Gör filnamnet unikt | Markera kryssrutan om du vill ha unika namn för filer inkluderade som bilagor i Adaptive Forms och Interactive Communications. | Inte markerad | Ej relevant |

## Konfiguration av temat för adaptiv form och interaktiv kommunikation i webbkanalen {#adaptive-form-and-interactive-communication-web-channel-theme-configuration}

Tryck på **Adaptiv form och Interactive Communication Web Channel Theme Configuration** på **Adobe Experience Manager Web Console Configuration**-sidan för att visa konfigurationsegenskaperna för Adaptiva Forms- och Interactive Communications-webbkanalteman.

<table> 
 <tbody> 
  <tr> 
   <td>Egenskap</td> 
   <td>Beskrivning</td> 
   <td>Standard</td> 
   <td>Godtagbara värden</td> 
  </tr> 
  <tr> 
   <td>Namn på teckensnittslista</td> 
   <td>Lista över teckensnitt som kan användas när Adaptive Forms och Interactive Communications skapas.</td> 
   <td><p>Georgien</p> <p>Book Antiqua</p> <p>Times New Roman</p> <p>Arial</p> <p>Arial Black</p> <p>Effekt</p> <p>Palation Linotype</p> </td> 
   <td>Alla giltiga Adobe-serverteckensnitt</td> 
  </tr> 
 </tbody> 
</table>

