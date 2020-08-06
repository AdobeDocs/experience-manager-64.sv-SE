---
title: Integrera med Silverpop Engage
seo-title: Integrera med Silverpop Engage
description: Lär dig integrera AEM med Silverpop Engage
seo-description: Lär dig integrera AEM med Silverpop Engage
uuid: dfff7aaf-5264-4763-995f-5647f565c03b
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: dfff6bdc-0d5f-4338-aa8a-7d0eb04bc19a
translation-type: tm+mt
source-git-commit: f1a5e4c5c8411e10887efab517115fee0fd1890a
workflow-type: tm+mt
source-wordcount: '694'
ht-degree: 1%

---


# Integrera med Silverpop Engage{#integrating-with-silverpop-engage}

>[!NOTE]
>
>Integrering med Silverpop är **inte** tillgängligt direkt. Du måste hämta [Silverpop-integreringspaketet](https://www.adobeaemcloud.com/content/marketplace/marketplaceProxy.html?packagePath=/content/companies/public/adobe/packages/aem620/product/cq-mcm-integrations-silverpop-content) från paketresursen och installera det på din instans. När du har installerat paketet kan du konfigurera det enligt beskrivningen i det här dokumentet.

Genom att integrera AEM med Silverpop Engage kan du hantera och skicka e-postmeddelanden som skapats i AEM via Silverpop. Du kan också använda leadhanteringsfunktionerna i Silverpop via AEM på AEM sidor.

Integreringen ger dig följande funktioner:

* Möjlighet att skapa e-postmeddelanden i AEM och publicera dem på Silverpop för distribution.
* Möjlighet att ange åtgärd för ett AEM formulär för att skapa en Silverpop-prenumerant.

När Silverpop Engage har konfigurerats kan du publicera nyhetsbrev och e-postmeddelanden till Silverpop Engage.

## Skapa en Silverpop-konfiguration {#creating-a-silverpop-configuration}

Silverpop-konfigurationer kan läggas till via **Cloud-tjänster**, **verktyg** eller **API-slutpunkter**. Alla metoder beskrivs i det här avsnittet.

### Konfigurera Silverpop via molntjänster {#configuring-silverpop-via-cloudservices}

Så här skapar du en Silverpop-konfiguration i Cloud Services:

1. I AEM: tryck eller klicka på **Verktyg** > **Distribution** > **Cloud Services**. (Eller direkt åtkomst på `https://<hostname>:<port>/etc/cloudservices.html`.)
1. Under tredjepartstjänster klickar du på **Silverop Engage** och sedan **Configure**. Konfigurationsfönstret Silverpop öppnas.

   >[!NOTE]
   >
   >Silverpop Engage är inte tillgängligt som alternativ under tredjepartstjänster om du inte hämtar paketet från paketresursen.

1. Ange en titel och eventuellt ett namn och klicka på **Skapa**. Konfigurationsfönstret** Silverpop Settings** öppnas.
1. Ange användarnamn, lösenord och välj en API-slutpunkt i listrutan.
1. Klicka på **Anslut till Silverpop.** När du har anslutit visas en dialogruta om att anslutningen lyckades. Klicka på **OK** för att stänga fönstret. Du kan gå till Silverpop genom att klicka på **Gå till Silverpop Engage**.
1. Silverpop har konfigurerats. Du kan redigera konfigurationen genom att klicka på **Redigera**.
1. Dessutom kan Silverpop Engage-ramverket konfigureras för personaliserade åtgärder genom att tillhandahålla rubrik och namn (valfritt). Klicka på Skapa för att skapa ramverket för den Silverpop-anslutning som redan konfigurerats.

   Importerade datatilläggskolumner kan senare användas via AEM-komponenten - **Text och anpassning**.

### Konfigurera Silverpop via verktyg {#configuring-silverpop-via-tools}

Så här skapar du en Silverpop-konfiguration i Verktyg:

1. I AEM: tryck eller klicka på **Verktyg** > **Distribution** > **Cloud Services**. Eller navigera dit direkt genom att gå till `https://<hostname>:<port>/misadmin#/etc`.
1. Välj **Verktyg**, **Cloud Services, konfigurationer och** sedan **Silverpop Engage**.
1. Klicka på **Ny** för att öppna fönstret **Skapa sida** .

   ![chlimage_1-44](assets/chlimage_1-44.jpeg)

1. Ange **Titel** och eventuellt **Namn** och klicka på **Skapa**.
1. Ange konfigurationsinformationen enligt steg 4 i föregående procedur. Följ den proceduren för att slutföra konfigurationen av Silverpop.

### Lägga till flera konfigurationer {#adding-multiple-configurations}

Så här lägger du till flera konfigurationer:

1. Klicka på **Cloud Services** på välkomstsidan och klicka på **Silverpop Engage**. Klicka på knappen **Visa konfigurationer** som visas om en eller flera Silverpop-konfigurationer är tillgängliga. Alla tillgängliga konfigurationer visas.
1. Klicka på **+** -tecknet bredvid Tillgängliga konfigurationer. Då öppnas fönstret **Skapa konfigurationer** . Följ den tidigare konfigurationsproceduren för att skapa en ny konfiguration.

### Konfigurera API-slutpunkter för anslutning till Silverpop {#configuring-api-end-points-for-connecting-to-silverpop}

För närvarande har AEM sex osäkra slutpunkter (Engage 1 till 6). Silverpop har nu två nya slutpunkter samt ändrade slutpunkter för anslutningen för de befintliga.

Så här konfigurerar du API-slutpunkterna:

1. Gå till `/libs/mcm/silverpop/components/silverpoppage/dialog/items/general/items/apiendpoint/options node` den `https://<hostname>:<port>/crxde.`
1. Högerklicka och välj **Skapa** och sedan **Skapa nod**.
1. Ange **namnet** som `sp-e0` och välj **Text** som `cq:Widget`.
1. Lägg till två egenskaper i den nyligen tillagda noden:

   1. **Namn**: `text`, **Typ**: `String`, **värde**: `Engage 0`
   1. **Namn**: `value`, **Typ**: `String`, **värde**: `https://api0.silverpop.com`

   ![chlimage_1-286](assets/chlimage_1-286.png)

   Klicka på knappen &quot;Spara alla&quot;.

1. Skapa en till nod med **namnet** som `sp-e7` och **typen** som `cq:Widget`.

   Lägg till två egenskaper i den nyligen tillagda noden:

   1. **Namn**: `text`, **Typ**: `String`, **värde**: `Pilot`
   1. **Namn**: `value`, **Typ**: `String`, **värde**: `https://apipilot.silverpop.com/XMLAPI`

1. Om du vill ändra de befintliga API-slutpunkterna (aktivera 1 till 6) klickar du på var och en av dem en i taget och ersätter värdena enligt följande:

   | **Nodnamn** | **Befintligt slutpunktsvärde** | **Nytt slutpunktsvärde** |
   |---|---|---|
   | sp-e1 | https://api.engage1.silverpop.com/XMLAPI | https://api1.silverpop.com |
   | sp-e2 | https://api.engage2.silverpop.com/XMLAPI | https://api2.silverpop.com |
   | sp-e3 | https://api.engage3.silverpop.com/XMLAPI | https://api3.silverpop.com |
   | sp-e4 | https://api.engage4.silverpop.com/XMLAPI | https://api4.silverpop.com |
   | sp-e5 | https://api.engage5.silverpop.com/XMLAPI | https://api5.silverpop.com |
   | sp-e6 | https://api.pilot.silverpop.com/XMLAPI | https://api6.silverpop.com |

1. Klicka på **Spara alla**. AEM är nu redo att ansluta till Silverpop över skyddade slutpunkter.

   ![chlimage_1-45](assets/chlimage_1-45.jpeg)

