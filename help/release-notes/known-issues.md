---
title: Kända fel i AEM 6.4
seo-title: Kända fel i AEM 6.4
description: Kända fel i Adobe Experience Manager 6.4
seo-description: Kända fel i Adobe Experience Manager 6.4.
uuid: 1733f15e-9c4f-4db3-98ee-25c2ea606f0d
contentOwner: msm-service
products: SG_EXPERIENCEMANAGER/6.4
topic-tags: release-notes
content-type: reference
discoiquuid: 266634ab-21d3-4aac-acfa-b799a7485507
translation-type: tm+mt
source-git-commit: f8ba597c62379ba413309303c2ad066ab7afce1e
workflow-type: tm+mt
source-wordcount: '1034'
ht-degree: 0%

---


# Kända fel {#known-issues}

På den här sidan finns en lista över kända fel i Adobe Experience Manager 6.4 som släpptes i april 2018. Mer information om kända fel [får du av supporten](https://helpx.adobe.com/support/experience-manager.html).

## Hybridenheter {#hybrid-devices}

Hybridenheter stöds inte. Olika problem kan uppstå vid användning av sådana enheter. Följande föreslagna procedurer hjälper dig att lösa många problem:

Om du använder Google Chrome som webbläsare:

* Skriv `chrome://flags/` i adressfältet och tryck på Retur.
* Klicka på Aktivera pekhändelser > Inaktiverad.
* Starta om webbläsaren (alla flikar och fönster).

Om du använder Mozilla Firefox som webbläsare:

* Skriv `about:config` i adressfältet och tryck på Retur.
* Filtrera inställningarna till `dom.w3c`.
* Kontrollera att inställningarna är `0` och `false`.
* Starta om webbläsaren.

Om du använder Microsoft Edge som webbläsare:

* Skriv `about:flags` i adressfältet och tryck på Retur.
* Bläddra sedan till Experimentella funktioner **[!UICONTROL Touch]**.
* Klicka på **[!UICONTROL Enable touch events]**.
* Välj **[!UICONTROL Always Off]**.
* Starta om webbläsaren.

## Platform {#platform}

* **Kontrollpanel för åtgärder:** Förloppsindikatorn visas inte när säkerhetskopieringsfilen saknar ZIP-tillägg. (GRANITE-10713)
* **HTML:** Java Use-objektet med efterföljande tomt utrymme i paketdeklarationen fryser SightlyJavaCompilerService (GRANITE-20836)
* **Apache Felix/Sling:** Konfigurationsfilen finns fortfarande i databasen även efter configuration.delete() (GRANITE-20618)
* **Molninställningar:** Konsolen bryts efter redigering av konfigurationsbehållaren (GRANITE-20726)
* **Säkerhet:** IMS-integrering misslyckas med anpassad kontextsökväg (GRANITE-20639)
* **Säkerhet:** Förbättra JAAS-standardrankningen för SSO, externa och standardinloggningsmoduler (GRANITE-20590)
* **Tooling - CRX DE Lite:** Vyn Egenskaper fortsätter att röra sig uppåt (GRANITE-12040)
* **Tooling - CRX DE Lite:** Det går inte att spara ändringar i Long-värdetyper om du inte dubbelklickar på Property Name (GRANITE-12351)

* **Tooling - CRX DE Lite:** Ctrl+F-sökning i öppna textfiler fastnar vid RegExp-sökning (GRANITE-5996)

* **Tooling - CRX DE Lite:** Nodegenskapen visas inte efter namnbyte av noden (GRANITE-7160)
* **Gränssnitt:** Pulldown &quot;more..&quot; visar inte alla element när de öppnas i ett pover-element i IE och Firefox (GRANITE-16326)
* **Gränssnitt:** Verktygstipset Info döljs när du använder fast kolumnlayout med två spalter sida vid sida (GRANITE-16869)
* **Gränssnitt:** Ohanterat fel vid personifiering som en användare som inte finns (GRANITE-23228). Tillfällig lösning genom att [implementera en felhanterare](/help/sites-developing/customizing-errorhandler-pages.md) för att anpassa felmeddelandet.

* **Omnissearch:** Sökningar med omvänt snedstreck orsakar undantag (GRANITE-11769)
* **Omnissearch:** Öppna Visa inställningar i listvyn så ändras sökfiltret (GRANITE-16524)
* **Omnissearch:** Fel lista över kolumnkonfigurationer som visas vid resurssökning från platser (GRANITE-16527)

* **Omnissearch:** Predikaten för vänster spår följer med Omnisearch-serverns begäran (GRANITE-20524)
* **Omnissearch:** Omnisearch stöder inte kontextsökvägar (GRANITE-16044)

## Assets {#assets}

* **Sök**: Sökningen returnerar inga resultat om söksträngen börjar med ett blanktecken [OAK-4786](https://issues.apache.org/jira/browse/OAK-4786)

* **Sök**: I klassiskt användargränssnitt och -taggar visas inte i sökningen (CQ-4235239)

* **Gränssnitt**: Resursgränssnittet slutar svara efter kopiera, klistra in och Markera allt (CQ-4236142)

* **Gränssnitt**: Det går inte att flytta resurser efter en lat inläsning (CQ-4236134)

* **Rapporter**: Fel vid skapande av resursändringsrapport (CQ-4239744)

* **Rapporter**: Schemalagd, regelbunden rapportgenerering av tillgångar misslyckas inkonsekvent (vissa rapporter står kvar i kö) (CQ-4239089)

* **Metadata**: När textfält med flera värden läggs till i tillgångsschema fungerar inte den obligatoriska fältöverlappningsregeln (CQ-4239333)

* **BrandPortal**: Publicera på BrandPortal fungerar inte för samlingar (CQ-4238731)

* **Överför**: När du överför resurser med specialtecken i filnamnet visas inte valideringsfelmeddelandet om otillåtna tecken för varje resurs. Medan det bara visas för den första resursen anger gränssnittet tydligt för användaren att filnamnet för den angivna resursen inte är tillåtet. (CQ-4256876)

## Communities {#communities}

* **Moderering** - Det går inte att ta bort överordnat inlägg som en enda borttagningsåtgärd från gränssnittet för massmoderering (CQ-4236797)

* **Konsol** - länken Glömt användarnamn eller lösenord dirigeras om till inloggningssidan i stället för till motsvarande formulär för hämtning av lösenord (CQ-4237682)

## Forms {#forms}

### Installation och driftsättning

* (Endast AEM Forms JEE) När JBoss-programservern startas om medan Configuration Manager körs returneras fel för EJB-anrop och startfel. Du kan dock ignorera dem. (Ref# CQ-4229793)
* När AEM Forms startas visas en varning `SAX Security Manager could not be setup` . (CQ-4297403)

### Interaktiv kommunikation

* Agentgränssnittet tar en stund att läsa in interaktiv kommunikation som innehåller diagram eller bildelement. (CQ-4236630)
* Visningsformatet för data i förhandsgranskning är dd-mm-åååå medan webbförhandsvisningen är `dd-mmm-yy` (CQ-4237045)
* Webbkanalen Interactive Communication har endast stöd för sorterade och osorterade listor. I listdokumentfragment stöds inte sammansatta listor och indrag för webbkanalen i den interaktiva kommunikationen. (CQ-4233672)
* Följande problem uppstår när webbkanaler synkroniseras med utskriftskanalen:

   * Webbkanalen tar en stund att synkronisera när du byter från en utskriftskanal för första gången.
   * Webbkanalen synkroniseras inte om utskriftskanalen innehåller en okonfigurerad diagramkomponent. Åtgärda problemet genom att ta bort diagramkomponenten och synkronisera igen.
   * Synkroniseringen misslyckas ibland med felet&quot;Ett fel uppstod när Live Copy synkroniserades&quot;. Uppdatera sidan för att lösa problemet.
   * Den statiska texten i ett layoutfragment ersätts med tabellcellens namn när den första kolumnen i tabellen är en rubrikrad i utskriftskanalmallen.
   * Det går inte att lägga till komponenter eller resurser på någon annan plats än längst ned i en webbkanalskommunikation. Om du vill placera den på en annan plats lägger du till en panel längst ned i webbkanalen och ändrar ordning med hjälp av innehållsträdet.
   * Kan flytta innehåll till det ärvda målområdet i webbkanalen utan att ta bort live-kopiarv.

(CQ-4239780)

### Dataintegrering

* Autentiseringskonfigurationer för SOAP-baserade webbtjänster är inte synliga och kan därför inte konfigureras i molntjänster. Så här löser du problemet:

   1. Gå till följande nod i CRXDE Lite-konsolen.\
      /libs/fd/fdm/gui/components/admin/fdmcloudservice/createcloudconfigwizard/cloudServices/\
      wsdlauthenticationsettings/items/fixedcolumns/items/container/items/wsdl/items/\
      selectAuthentication/items/custom.
   1. Uppdatera värdet för value-egenskapen till samma som värdet för text-egenskapen.
   1. Klicka på Spara alla för att spara konfigurationen.

(CQ-4238462)

### Integrering med Adobe Sign

* Adobe Sign-schemaläggaren slutar fungera regelbundet och därför flyttas inte väntande signaturer till överföring. Lös problemet genom att starta om **stödpaketet för schemaläggaren** för Apache Sling från AEM webbkonsol på https://[*server*]:[*port*]/system/konsol/bundles.

### Skapa anpassningsbara Forms-program

* Diagramkomponenten i anpassningsbara formulär tar mer utrymme än vad den normalt gör.
* Ett undantag returneras när egenskaper sparas för adaptiva formulär, adaptiva formulärfragment eller interaktiv kommunikation i användargränssnittet i Forms Manager.
* Det angivna maximala antalet tecken för en textruta med anpassningsbara formulär stöds inte på Android 6.0 Samsung-enheter. (Ref# CQ-4235205)
