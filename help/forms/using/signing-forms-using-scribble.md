---
title: Använda elektroniska signaturer i ett formulär med hjälp av klottersignaturer
seo-title: Apply electronic signatures to a form using scribble signatures
description: Signera formulär med klottrar
seo-description: Signing forms using scribble
uuid: e807d0de-6d5f-458e-be3e-273ed7a521c0
products: SG_EXPERIENCEMANAGER/6.4/FORMS
topic-tags: author
discoiquuid: 6a806727-28c5-430e-9a83-b43e0e9d9e1c
feature: Adaptive Forms
exl-id: a870c4b7-4040-4bd8-b477-286ebe6a4b01
source-git-commit: c5b816d74c6f02f85476d16868844f39b4c47996
workflow-type: tm+mt
source-wordcount: '533'
ht-degree: 0%

---

# Använda elektroniska signaturer i ett formulär med hjälp av klottersignaturer {#apply-electronic-signatures-to-a-form-using-scribble-signatures}

>[!CAUTION]
>
>AEM 6.4 har nått slutet på den utökade supporten och denna dokumentation är inte längre uppdaterad. Mer information finns i [teknisk supportperiod](https://helpx.adobe.com/support/programs/eol-matrix.html). Hitta de versioner som stöds [här](https://experienceleague.adobe.com/docs/).

Du kan använda **Klottersignatur** komponenter och **Signatursteg** -komponent för att rita (Klottra) signatur i ett anpassat formulär. Underskriftsstegkomponenten visar en PDF-version av det adaptiva formuläret. Du måste aktivera alternativet Dokument för post eller formulärmallsbaserade adaptiva formulär för att kunna använda signaturstegskomponenten.

Båda komponenterna har ett fönster som visas nedan för att signera ett formulär. Du kan också klicka på ikonen för geopositionering ![aem_6_3_geolocation](assets/aem_6_3_geolocation.png) för att lägga till geopositionering till signaturen.

![Dialogrutan Klottra signering](assets/scribble-signature.png)

## Konfigurera ett anpassningsbart formulär att använda en skriptsignatur {#configure-an-adaptive-form-to-use-scribble-signature}

1. Alternativet Skapa ett postdokument aktiverat eller ett anpassat formulär som bygger på en formulärmall. Stegvisa instruktioner finns i [Skapa ett anpassat formulär](/help/forms/using/creating-adaptive-form.md).
1. Dra och släpp **Klottersignatur** från komponentwebbläsaren till det adaptiva formuläret.
1. Tryck på **Konfigurera** ![konfigurera](assets/configure.png) ikon. Egenskaper öppnas i webbläsaren och egenskaper för komponenten Skriptsignatur visas. Konfigurera egenskaper för komponenten Scribble Signature.
1. Dra och släpp signaturstegskomponenten från komponentwebbläsaren till det anpassningsbara formuläret.

   >[!NOTE]
   >
   >Komponenten Signatursteg får full bredd som är tillgänglig för formuläret. Vi rekommenderar att du inte har någon annan komponent i avsnittet som innehåller komponenten Signatursteg.

1. Tryck på **Formulärbehållare** och trycker på **Konfigurera** ![konfigurera](assets/configure.png) ikon. Egenskaper öppnas i webbläsaren och egenskaper för behållare för adaptiva formulär visas. Navigera till **Adaptiv formulärbehållare** > **Elektronisk signatur** och avmarkera **Aktivera Acrobat Sign** alternativ. Tryck på Klar ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) om du vill spara ändringarna.

   >[!NOTE]
   >
   >När du lägger till en komponent för signatursteg i ett anpassat formulär markeras alternativet Aktivera Acrobat Sign automatiskt.

1. Tryck på **Konfigurera** ![konfigurera](assets/configure.png) ikon. Egenskaper öppnas i webbläsaren och egenskaper för signatursteg visas. Konfigurera följande egenskaper:

   * **Elementnamn**: Ange komponentens namn.
   * **Titel:** Ange komponentens unika namn.
   * **Mallmeddelande:** Ange meddelandet som ska visas medan signaturen PDF läses in. Acrobat Sign tjänster tar lite tid att förbereda och läsa in signaturen PDF.
   * **Underteckningstjänst:** Välj **Klottersignatur** alternativ.
   * **CSS-klass**: Ange CSS-klass för klientbiblioteket, om det finns någon. Det rekommenderas att använda [teman](/help/forms/using/themes.md) och [infogade format](/help/forms/using/inline-style-adaptive-forms.md) i stället för CSS-klassen.

   Tryck på Klar ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) om du vill spara ändringarna. Signaturen har konfigurerats.

   När du fyller i ett formulär visas nu en PDF-version av ett anpassat formulär och alternativ för att signera PDF-dokumentet finns. Mer information finns i [Signera ett anpassat formulär med Scribble Signature](/help/forms/using/signing-forms-using-scribble.md#p-sign-an-adaptive-form-using-scribble-signature-p).

## Signera ett anpassat formulär med Scribble Signature {#sign-an-adaptive-form-using-scribble-signature}

1. När du har fyllt i ett anpassat formulär och kommit till sidan Signatursteg visas signaturskärmen.

   ![Signaturskärm för EchoSign-sida](assets/esignscribblesign.jpg)

1. Klicka på **[!UICONTROL Sign]**. Dialogrutan för klottersignering visas. Signera formuläret och klicka på Klar ![aem_6_3_forms_save](assets/aem_6_3_forms_save.png) -ikonen för att spara signaturen.

   ![Dialogrutan Klottra signering](assets/scribblewidget.jpg)

1. Klicka på Slutför för att slutföra signeringsprocessen.

   ![Slutför signeringsprocessen](assets/scribblecomplete.jpg)

Signaturerna läggs till i formuläret och formulärkontrollen flyttas till nästa panel.
