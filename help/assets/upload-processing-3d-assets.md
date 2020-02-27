---
title: Om överföring och bearbetning av 3D-resurser i AEM
seo-title: Om överföring och bearbetning av 3D-resurser i AEM
description: Bästa tillvägagångssätt för att överföra och bearbeta 3D-resurser.
seo-description: Bästa tillvägagångssätt för att överföra och bearbeta 3D-resurser.
uuid: d8abf460-adff-4f0f-92ae-2c8651a17488
contentOwner: Rick Brough
topic-tags: 3D
content-type: reference
products: SG_EXPERIENCEMANAGER/6.4/ASSETS
discoiquuid: a0319701-21eb-4b7f-8b2e-ac81a7a75875
translation-type: tm+mt
source-git-commit: 5acb16b1734331767554261bbcf9640947f2e23f

---


# Om överföring och bearbetning av 3D-resurser i AEM {#about-the-uploading-and-processing-of-d-assets-in-aem}

Använd standardfunktioner för överföring eller synkronisering för att överföra 3D-resurser och tillhörande refererade filer till AEM Assets.

Se [Överföra resurser](managing-assets-touch-ui.md#uploading-assets).

Adobe rekommenderar att du överför alla refererade filer före eller samtidigt som du överför den primära 3D-modellfilen. Detta är dock inget krav.

När överföringen är klar konverteras dina 3D-filer och ytterligare bearbetning utförs för att förbereda resursen för visning och återgivning.

## Bästa tillvägagångssätt för att överföra 3D-resurser {#best-practices-for-uploading-d-assets}

* I allmänhet finns det inga begränsningar för var du överför 3D-innehåll i mapphierarkin för AEM Resurser. AEM 3D:s automatiska upplösning av filberoenden har dock ett intervall som begränsar hur lång tid det tar att söka i stora resurslager. Därför rekommenderar Adobe att du när du överför 3D-resurser och deras filberoende resurser gör det inom rimlig avstånd från varje fil (vanlig indirekt överordnad mapp). När filberoenden är lösta kan du fritt flytta både 3D-resursen och dess underordnade objekt var som helst i databasen utan att förlora de etablerade relationerna.
* Adobe rekommenderar att du bestämmer dig för en konsekvent mappstruktur för 3D-innehåll *innan* du överför det. Följande tips är några förslag på metoder som du kan använda:

   * **Underhåll en separat mapp för varje 3D-resurs som du överför**.

      Mappen innehåller både den primära 3D-modellfilen och alla dess underordnade filer. Det är enkelt att implementera alla resurser och beroenden i en mapp, men det är besvärligt att söka efter innehåll. Det är också komplicerat att dela beroenden (texturscheman) mellan olika modeller.

   * **Förvara modellerna i en mapp och underordnade i en jämställd eller underordnad mapp**.

      Det här tillvägagångssättet stöder enkelt delning av beroenden mellan modeller. Det kan dock bli svårt att hitta specifika beroenden om antalet resurser är stort.

   * **Separata parallella mapphierarkier för modeller och underordnade**.

      Du kan modellera den här metoden för hur 3D-redigeringsprogram som Autodesk Maya föredrar att lagra innehåll.

* Beroende resurser ska inte tas bort såvida inte de associerade 3D-resurserna eller resurserna som refererar till dem också tas bort. Du kan dock ta bort 3D-resurser utan att behöva ta bort deras beroende resurser. Om ett beroende går förlorat av misstag kan du enkelt lösa det för att återställa det.

   Se Lösa filberoenden.

## Prestandaöverväganden vid överföring av 3D-filer {#performance-considerations-when-uploading-d-files}

När du konverterar och bearbetar 3D-filer förbrukas vanligtvis mycket processorkraft och minne på en server. Det tar också lång tid. Bearbetningstiden varierar ofta mycket beroende på modellens storlek och serverns kapacitet. En vanlig liten modell med mindre än 100 kB-ansikten är till exempel vanligtvis klar att visas på mindre än en minut. Den behandlas fullständigt på 2-3 minuter. En stor modell med mer än en miljon ansikten kan ta tiotals minuter att behandla helt.

Konverterings-, bearbetnings- och renderingsjobb köas efter behov för att förhindra att servern blir för långsam. Meddelandet&quot;Väntar på bearbetning..&quot; visas ibland i **[!UICONTROL kortvyn]** när du överförde resurser. Den här statusen anger att andra behandlings- eller återgivningsjobb måste avslutas innan den aktuella resursen bearbetas.

Det finns mekanismer för att begränsa processoranvändningen för matningsbearbetning och för återgivning. Mer information om hur du konfigurerar CPU-gränserna finns i [Avancerade konfigurationsinställningar](advanced-config-3d.md) .

## Övervaka bearbetningsstatus för dina överförda 3D-filer {#monitoring-the-processing-status-of-your-uploaded-d-files}

Endast i **[!UICONTROL kortvyn]** visas bearbetningsstatus och förlopp som en förloppsbanderoll på resurskortet. Varje överförd 3D-modell genomgår vanligtvis följande 4-6 beställda bearbetningssteg:

<table> 
 <tbody> 
  <tr> 
   <td><strong>Bearbetningsfas</strong><br /> </td> 
   <td><strong>Bearbetar namn</strong></td> 
   <td><strong>Beskrivning</strong></td> 
  </tr> 
  <tr> 
   <td>1</td> 
   <td>Bearbetar</td> 
   <td>Grundläggande inledande bearbetning och metadataextrahering.</td> 
  </tr> 
  <tr> 
   <td>2</td> 
   <td>Konverterar format</td> 
   <td>3D-modellen konverteras från ett inbyggt format (Autodesk® Maya® eller Autodesk® 3ds Max®) till ett mellanliggande format (FBX).</td> 
  </tr> 
  <tr> 
   <td>3</td> 
   <td>Skapa förhandsgranskning</td> 
   <td>FBX- eller OBJ-filen importeras och bearbetas. Filberoenden utvärderas och löses när det är möjligt som resursreferenser.</td> 
  </tr> 
  <tr> 
   <td>4</td> 
   <td>Skapa markskugga</td> 
   <td>valfritt. Gör att du kan generera en skugga för omgivande ocklusion på markplanet under 3D-objektet. Se <a href="/help/assets/advanced-config-3d.md">Avancerade konfigurationsinställningar</a> för att aktivera eller inaktivera den här bearbetningen.</td> 
  </tr> 
  <tr> 
   <td>5<br /> </td> 
   <td>Skapa ljusbord</td> 
   <td>valfritt. Gör att du kan förbättra kvaliteten på den interaktiva förhandsvisningen och få en snabbare återgivning med standardåtergivaren. Se <a href="/help/assets/advanced-config-3d.md">Avancerade konfigurationsinställningar</a> för att aktivera eller inaktivera den här bearbetningen.</td> 
  </tr> 
  <tr> 
   <td>6<br /> </td> 
   <td>Skapa animering</td> 
   <td>valfritt. Gör att du kan återge en enkel animering som sedan används som en visuell miniatyrbild i kortvyn. Se <a href="/help/assets/advanced-config-3d.md">Avancerade konfigurationsinställningar</a> för att aktivera eller inaktivera den här bearbetningen.</td> 
  </tr> 
  <tr> 
   <td>7<br /> </td> 
   <td>Väntar på bearbetning</td> 
   <td>Visas när andra 3D-resurser har bearbetningsprioritet. Till exempel resurser som har överförts tidigare men ännu inte slutfört bearbetningen.</td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Du kan visa en 3D-resurs i **[!UICONTROL detaljvyn]** eller återge den när förhandsgranskningssteget Skapa är klart. Du behöver inte vänta på att alla bearbetningsfaser ska slutföras.

