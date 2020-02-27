---
title: Integrera med ExactTarget
seo-title: Integrera med ExactTarget
description: Lär dig hur du integrerar AEM med ExactTarget.
seo-description: Lär dig hur du integrerar AEM med ExactTarget.
uuid: dafa0a1a-2d1e-40fc-a729-f2ce7ebc7807
contentOwner: Guillaume Carlino
products: SG_EXPERIENCEMANAGER/6.4/SITES
topic-tags: integration
content-type: reference
discoiquuid: d1cff2bb-9fdf-49cb-a695-d437bba5653d
translation-type: tm+mt
source-git-commit: cdec5b3c57ce1c80c0ed6b5cb7650b52cf9bc340

---


# Integrera med ExactTarget{#integrating-with-exacttarget}

Genom att integrera AEM med Exact Target kan du hantera och skicka e-post som skapats i AEM via Exact Target. Du kan även använda leadhanteringsfunktionerna i Exact Target via AEM-formulär på AEM-sidor.

Integreringen ger dig följande funktioner:

* Möjlighet att skapa e-postmeddelanden i AEM och publicera dem på Exact Target för distribution.
* Möjlighet att ange åtgärd för ett AEM-formulär för att skapa en exakt målabonnent.

När ExactTarget har konfigurerats kan du publicera nyhetsbrev och e-postmeddelanden till ExactTarget. Se [Publicera nyhetsbrev till en e-posttjänst](/help/sites-authoring/personalization.md).

## Skapa en ExactTarget-konfiguration {#creating-an-exacttarget-configuration}

ExactTarget-konfigurationer kan läggas till via molntjänster eller verktyg. Båda metoderna beskrivs i det här avsnittet.

### Konfigurera ExactTarget via CloudServices {#configuring-exacttarget-via-cloudservices}

Så här skapar du en ExactTarget-konfiguration i molntjänster:

1. På välkomstsidan klickar du på **molntjänster**. (Eller direkt åtkomst på `https://<hostname>:<port>/etc/cloudservices.html`.)
1. Klicka på **ExactTarget** och sedan **Configure**. Konfigurationsfönstret ExactTarget öppnas.

   ![chlimage_1-182](assets/chlimage_1-182.png)

1. Ange en titel och eventuellt ett namn och klicka på **Skapa**. Konfigurationsfönstret* ExactTarget Settings** öppnas.

   ![chlimage_1-31](assets/chlimage_1-31.jpeg)

1. Ange användarnamn, lösenord och välj en API-slutpunkt (till exempel **https://webservice.exacttarget.com/Service.asmx**).
1. Klicka på **Anslut till ExactTarget.** När du har anslutit visas en dialogruta om att anslutningen lyckades. Klicka på **OK** för att stänga fönstret.

   ![chlimage_1-32](assets/chlimage_1-32.jpeg)

1. Välj ett konto, om det är tillgängligt. Kontot är till för Enterprise 2.0-kunder. Click **OK**.

   ExactTarget har konfigurerats. Du kan redigera konfigurationen genom att klicka på **Redigera**. Du kan gå till ExactTarget genom att klicka på **Gå till ExactTarget**.

1. AEM har nu en datatilläggsfunktion. Du kan importera ExactTarget-datatilläggskolumner. Detta kan konfigureras genom att klicka på plustecknet (+) som visas förutom den EXactTarget-konfiguration som skapades. Alla befintliga datatillägg kan väljas i listrutan. Mer information om hur du konfigurerar datatillägg finns i [ExactTarget-dokumentationen](https://help.exacttarget.com/en/documentation/exacttarget/subscribers/data_extensions_and_data_relationships).

   Importerade datatilläggskolumner kan senare användas via komponenten **Text och Personalization** .

   ![chlimage_1-33](assets/chlimage_1-33.jpeg)

### Konfigurera ExactTarget via verktyg {#configuring-exacttarget-via-tools}

Så här skapar du en ExactTarget-konfiguration i verktygen:

1. På välkomstsidan klickar du på **Verktyg**. Eller navigera dit direkt genom att gå till `https://<hostname>:<port>/misadmin#/etc`.
1. Välj **Verktyg**, **Cloud Services Configurations och** sedan **ExactTarget**.
1. Klicka på **Ny** för att öppna fönstret **Skapa sida **.

   ![chlimage_1-34](assets/chlimage_1-34.jpeg)

1. Ange **Titel** och eventuellt **Namn** och klicka på **Skapa**.
1. Ange konfigurationsinformationen enligt steg 4 i föregående procedur. Följ den proceduren för att slutföra konfigurationen av ExactTarget.

### Lägga till flera konfigurationer {#adding-multiple-configurations}

Så här lägger du till flera konfigurationer:

1. På välkomstsidan klickar du på **molntjänster** och sedan på **ExactTarget**. Klicka på knappen **Visa konfigurationer** som visas om en eller flera ExactTarget-konfigurationer är tillgängliga. Alla tillgängliga konfigurationer visas.
1. Klicka på **+** -tecknet bredvid Tillgängliga konfigurationer. Då öppnas fönstret **Skapa konfigurationer** . Följ den tidigare konfigurationsproceduren för att skapa en ny konfiguration.

